# TmpRecoverEnlistmentFromEnlistmentRecord

- ea: `0x14000e758`
- end: `0x14000ea56`
- name: `TmpRecoverEnlistmentFromEnlistmentRecord`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000ea5c`

## callees

- `0x140001a0c`
- `0x140001a3c`
- `0x14000e758`
- `0x14000edb0`
- `0x140019a30`
- `0x14001ea40`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000e842`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e842`
- `ntoskrnl!ZwClose` at `0x14000e827`
- `ntoskrnl!ZwClose` at `0x14000e827`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000e7fa`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000e7fa`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000e904`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000e904`
- `ntoskrnl!ZwCreateEnlistment` at `0x14000e8c7`
- `ntoskrnl!ZwCreateEnlistment` at `0x14000e8c7`
- `ntoskrnl!ZwSetInformationEnlistment` at `0x14000e9ac`
- `ntoskrnl!ZwSetInformationEnlistment` at `0x14000e9ac`

## pseudocode

```c
int __fastcall TmpRecoverEnlistmentFromEnlistmentRecord(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        HANDLE TransactionHandle,
        PSECURITY_DESCRIPTOR a7,
        __int64 a8,
        PHANDLE EnlistmentHandle,
        _BYTE *a10)
{
  void **Handle; // r14
  _BYTE *v11; // r12
  __int64 v15; // rcx
  char *v17; // rdi
  int result; // eax
  NTSTATUS v19; // ebx
  ULONG v20; // edx
  void *v21; // rcx
  NTSTATUS v22; // eax
  __int64 v23; // r8
  ULONG v24; // r9d
  __int64 v25; // rcx
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  PVOID Object; // [rsp+D0h] [rbp+58h] BYREF

  Handle = EnlistmentHandle;
  v11 = a10;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  v15 = a5;
  *EnlistmentHandle = 0;
  *v11 = 0;
  a7 = 0;
  Object = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (int)TmpFindEnlistmentResourceManager(v15, a3, &Object) < 0 )
  {
    result = TmpRecoverSecurityDescriptor(a1, a2, *(_DWORD *)(a3 + 100), *(_DWORD *)(a3 + 96), &a7);
    if ( result < 0 )
      return result;
    v20 = *(_DWORD *)(a3 + 80) & 1;
    ObjectAttributes.SecurityDescriptor = a7;
    result = ZwCreateEnlistment(
               Handle,
               0xF001Fu,
               a4,
               TransactionHandle,
               &ObjectAttributes,
               v20,
               v20 != 0 ? 536871112 : 16398,
               0);
    if ( result < 0 )
      return result;
    v21 = *Handle;
    EnlistmentHandle = 0;
    v22 = ObReferenceObjectByHandle(v21, 2u, (POBJECT_TYPE)TmEnlistmentObjectType, 0, (PVOID *)&EnlistmentHandle, 0);
    v17 = (char *)EnlistmentHandle;
    v19 = v22;
    if ( v22 < 0 )
      goto LABEL_5;
    v19 = TmpNamespaceRename((PRTL_AVL_TABLE)((char *)EnlistmentHandle[19] + 384));
    if ( v19 < 0 )
    {
      v19 = -1072103341;
      goto LABEL_5;
    }
    if ( (*(_DWORD *)(a3 + 80) & 0x20) != 0 )
    {
      *(_OWORD *)(v17 + 264) = *(_OWORD *)(a3 + 32);
      *(_OWORD *)(v17 + 280) = *(_OWORD *)(a3 + 64);
      *(_OWORD *)(v17 + 296) = *(_OWORD *)(a3 + 48);
      _InterlockedOr((volatile signed __int32 *)v17 + 43, 0x20u);
    }
    v24 = *(_DWORD *)(a3 + 88);
    if ( !v24 )
      goto LABEL_4;
    v25 = *(unsigned int *)(a3 + 92);
    if ( (unsigned int)v25 + v24 > a2 || (unsigned int)v25 > a2 || v24 > a2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 17, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids);
      v19 = -1072103376;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
        goto LABEL_5;
      v27 = 18;
      v28 = 3222863920LL;
    }
    else
    {
      v19 = ZwSetInformationEnlistment(*Handle, EnlistmentRecoveryInformation, (PVOID)(v25 + a1), v24);
      if ( v19 >= 0 )
        goto LABEL_4;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 8) == 0 )
      {
LABEL_5:
        if ( *Handle )
        {
          ZwClose(*Handle);
          *Handle = 0;
        }
        goto LABEL_7;
      }
      v27 = 19;
      v28 = (unsigned int)v19;
    }
    WPP_SF_d(v26[3], v27, v23, v28);
    goto LABEL_5;
  }
  v17 = (char *)Object;
  result = ObOpenObjectByPointer(Object, 0x200u, 0, 0xF001Fu, (POBJECT_TYPE)TmEnlistmentObjectType, 0, Handle);
  v19 = result;
  if ( result < 0 )
    return result;
  *v11 = 1;
LABEL_4:
  *((_DWORD *)v17 + 42) = 268;
  if ( v19 < 0 )
    goto LABEL_5;
LABEL_7:
  if ( v17 )
    ObfDereferenceObject(v17);
  return v19;
}

```

## disassembly

```asm
0x14000e758  push    rbp
0x14000e75a  push    rbx
0x14000e75b  push    rsi
0x14000e75c  push    rdi
0x14000e75d  push    r12
0x14000e75f  push    r13
0x14000e761  push    r14
0x14000e763  push    r15
0x14000e765  mov     rbp, rsp
0x14000e768  sub     rsp, 78h
0x14000e76c  mov     r14, [rbp+EnlistmentHandle]
0x14000e773  xor     edi, edi
0x14000e775  mov     r12, [rbp+arg_48]
0x14000e77c  mov     rsi, r8
0x14000e77f  mov     r15d, edx
0x14000e782  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000e78a  mov     r13, rcx
0x14000e78d  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14000e795  mov     rcx, [rbp+arg_20]
0x14000e799  lea     r8, [rbp+Object]
0x14000e79d  xorps   xmm0, xmm0
0x14000e7a0  mov     [r14], rdi
0x14000e7a3  mov     rdx, rsi
0x14000e7a6  mov     [r12], dil
0x14000e7aa  mov     rbx, r9
0x14000e7ad  mov     [rbp+arg_30], rdi
0x14000e7b1  mov     [rbp+Object], rdi
0x14000e7b5  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x14000e7b9  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x14000e7bd  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e7c2  call    TmpFindEnlistmentResourceManager
0x14000e7c7  test    eax, eax
0x14000e7c9  js      loc_14000E862
0x14000e7cf  mov     rax, cs:TmEnlistmentObjectType
0x14000e7d6  mov     r9d, 0F001Fh; DesiredAccess
0x14000e7dc  mov     [rsp+78h+Handle], r14; Handle
0x14000e7e1  xor     r8d, r8d; PassedAccessState
0x14000e7e4  mov     [rsp+78h+AccessMode], dil; AccessMode
0x14000e7e9  mov     edx, 200h; HandleAttributes
0x14000e7ee  mov     rdi, [rbp+Object]
0x14000e7f2  mov     rcx, rdi; Object
0x14000e7f5  mov     [rsp+78h+ObjectType], rax; ObjectType
0x14000e7fa  call    cs:__imp_ObOpenObjectByPointer
0x14000e801  nop     dword ptr [rax+rax+00h]
0x14000e806  mov     ebx, eax
0x14000e808  test    eax, eax
0x14000e80a  js      short loc_14000E850
0x14000e80c  mov     byte ptr [r12], 1
0x14000e811  mov     dword ptr [rdi+0A8h], 10Ch
0x14000e81b  test    ebx, ebx
0x14000e81d  jns     short loc_14000E83A
0x14000e81f  mov     rcx, [r14]; Handle
0x14000e822  test    rcx, rcx
0x14000e825  jz      short loc_14000E83A
0x14000e827  call    cs:__imp_ZwClose
0x14000e82e  nop     dword ptr [rax+rax+00h]
0x14000e833  mov     qword ptr [r14], 0
0x14000e83a  test    rdi, rdi
0x14000e83d  jz      short loc_14000E84E
0x14000e83f  mov     rcx, rdi; Object
0x14000e842  call    cs:__imp_ObfDereferenceObject
0x14000e849  nop     dword ptr [rax+rax+00h]
0x14000e84e  mov     eax, ebx
0x14000e850  add     rsp, 78h
0x14000e854  pop     r15
0x14000e856  pop     r14
0x14000e858  pop     r13
0x14000e85a  pop     r12
0x14000e85c  pop     rdi
0x14000e85d  pop     rsi
0x14000e85e  pop     rbx
0x14000e85f  pop     rbp
0x14000e860  retn
0x14000e862  mov     r9d, [rsi+60h]
0x14000e866  lea     rax, [rbp+arg_30]
0x14000e86a  mov     r8d, [rsi+64h]
0x14000e86e  mov     edx, r15d
0x14000e871  mov     rcx, r13
0x14000e874  mov     [rsp+78h+ObjectType], rax
0x14000e879  call    TmpRecoverSecurityDescriptor
0x14000e87e  test    eax, eax
0x14000e880  js      short loc_14000E850
0x14000e882  mov     rax, [rbp+arg_30]
0x14000e886  mov     r8, rbx; ResourceManagerHandle
0x14000e889  mov     edx, [rsi+50h]
0x14000e88c  mov     r9, [rbp+TransactionHandle]; TransactionHandle
0x14000e890  and     edx, 1
0x14000e893  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x14000e897  mov     eax, edx
0x14000e899  neg     eax
0x14000e89b  mov     [rsp+78h+EnlistmentKey], rdi; EnlistmentKey
0x14000e8a0  lea     rax, [rbp+ObjectAttributes]
0x14000e8a4  sbb     ecx, ecx
0x14000e8a6  and     ecx, 1FFFC0BAh
0x14000e8ac  add     ecx, 400Eh
0x14000e8b2  mov     dword ptr [rsp+78h+Handle], ecx; NotificationMask
0x14000e8b6  mov     rcx, r14; EnlistmentHandle
0x14000e8b9  mov     dword ptr [rsp+78h+AccessMode], edx; CreateOptions
0x14000e8bd  mov     edx, 0F001Fh; DesiredAccess
0x14000e8c2  mov     [rsp+78h+ObjectType], rax; ObjectAttributes
0x14000e8c7  call    cs:__imp_ZwCreateEnlistment
0x14000e8ce  nop     dword ptr [rax+rax+00h]
0x14000e8d3  test    eax, eax
0x14000e8d5  js      loc_14000E850
0x14000e8db  mov     r8, cs:TmEnlistmentObjectType; ObjectType
0x14000e8e2  lea     rax, [rbp+EnlistmentHandle]
0x14000e8e9  mov     rcx, [r14]; Handle
0x14000e8ec  xor     r9d, r9d; AccessMode
0x14000e8ef  mov     qword ptr [rsp+78h+AccessMode], rdi; HandleInformation
0x14000e8f4  mov     [rbp+EnlistmentHandle], rdi
0x14000e8fb  mov     [rsp+78h+ObjectType], rax; Object
0x14000e900  lea     edx, [r9+2]; DesiredAccess
0x14000e904  call    cs:__imp_ObReferenceObjectByHandle
0x14000e90b  nop     dword ptr [rax+rax+00h]
0x14000e910  mov     rdi, [rbp+EnlistmentHandle]
0x14000e917  mov     ebx, eax
0x14000e919  test    eax, eax
0x14000e91b  js      loc_14000E81F
0x14000e921  mov     rcx, [rdi+98h]
0x14000e928  mov     r8, rsi
0x14000e92b  add     rcx, 180h; Table
0x14000e932  mov     rdx, rdi
0x14000e935  call    TmpNamespaceRename
0x14000e93a  mov     ebx, eax
0x14000e93c  test    eax, eax
0x14000e93e  jns     short loc_14000E94A
0x14000e940  mov     ebx, 0C0190053h
0x14000e945  jmp     loc_14000E81F
0x14000e94a  mov     eax, [rsi+50h]
0x14000e94d  test    al, 20h
0x14000e94f  jz      short loc_14000E97D
0x14000e951  movups  xmm0, xmmword ptr [rsi+20h]
0x14000e955  movdqu  xmmword ptr [rdi+108h], xmm0
0x14000e95d  movups  xmm1, xmmword ptr [rsi+40h]
0x14000e961  movdqu  xmmword ptr [rdi+118h], xmm1
0x14000e969  movups  xmm0, xmmword ptr [rsi+30h]
0x14000e96d  movdqu  xmmword ptr [rdi+128h], xmm0
0x14000e975  lock or dword ptr [rdi+0ACh], 20h
0x14000e97d  mov     r9d, [rsi+58h]; EnlistmentInformationLength
0x14000e981  test    r9d, r9d
0x14000e984  jz      loc_14000E811
0x14000e98a  mov     ecx, [rsi+5Ch]
0x14000e98d  lea     eax, [rcx+r9]
0x14000e991  cmp     eax, r15d
0x14000e994  ja      short loc_14000E9EE
0x14000e996  cmp     ecx, r15d
0x14000e999  ja      short loc_14000E9EE
0x14000e99b  cmp     r9d, r15d
0x14000e99e  ja      short loc_14000E9EE
0x14000e9a0  lea     r8, [rcx+r13]; EnlistmentInformation
0x14000e9a4  mov     edx, 1; EnlistmentInformationClass
0x14000e9a9  mov     rcx, [r14]; EnlistmentHandle
0x14000e9ac  call    cs:__imp_ZwSetInformationEnlistment
0x14000e9b3  nop     dword ptr [rax+rax+00h]
0x14000e9b8  mov     ebx, eax
0x14000e9ba  test    eax, eax
0x14000e9bc  jns     loc_14000E811
0x14000e9c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9c9  lea     rsi, WPP_GLOBAL_Control
0x14000e9d0  cmp     rcx, rsi
0x14000e9d3  jz      loc_14000E81F
0x14000e9d9  mov     eax, [rcx+2Ch]
0x14000e9dc  test    al, 8
0x14000e9de  jz      loc_14000E81F
0x14000e9e4  mov     edx, 13h
0x14000e9e9  mov     r9d, ebx
0x14000e9ec  jmp     short loc_14000EA48
0x14000e9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9f5  lea     rsi, WPP_GLOBAL_Control
0x14000e9fc  cmp     rcx, rsi
0x14000e9ff  jz      short loc_14000EA1D
0x14000ea01  mov     eax, [rcx+2Ch]
0x14000ea04  test    al, 8
0x14000ea06  jz      short loc_14000EA1D
0x14000ea08  mov     rcx, [rcx+18h]
0x14000ea0c  lea     r8, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids
0x14000ea13  mov     edx, 11h
0x14000ea18  call    WPP_SF_
0x14000ea1d  mov     ebx, 0C0190030h
0x14000ea22  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea29  cmp     rcx, rsi
0x14000ea2c  jz      loc_14000E81F
0x14000ea32  mov     eax, [rcx+2Ch]
0x14000ea35  test    al, 8
0x14000ea37  jz      loc_14000E81F
0x14000ea3d  mov     edx, 12h
0x14000ea42  mov     r9d, 0C0190030h
0x14000ea48  mov     rcx, [rcx+18h]
0x14000ea4c  call    WPP_SF_d
0x14000ea51  jmp     loc_14000E81F
```
