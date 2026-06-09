# TmpRecoverResourceManagerFromEnlistmentRecord

- ea: `0x14000ebd4`
- end: `0x14000eda7`
- name: `TmpRecoverResourceManagerFromEnlistmentRecord`
- size: `467`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE TmHandle, __int64, PHANDLE ResourceManagerHandle, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000ea5c`

## callees

- `0x14000ebd4`
- `0x14000edb0`
- `0x14000f0a4`
- `0x140019a5c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000ed81`
- `ntoskrnl!ZwClose` at `0x14000ed81`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000ec79`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14000ec79`
- `ntoskrnl!ZwCreateResourceManager` at `0x14000ed32`
- `ntoskrnl!ZwCreateResourceManager` at `0x14000ed32`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000ed65`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000ed65`

## pseudocode

```c
int __fastcall TmpRecoverResourceManagerFromEnlistmentRecord(
        _DWORD *a1,
        unsigned int a2,
        __int64 a3,
        _DWORD *a4,
        HANDLE TmHandle,
        __int64 a6,
        PHANDLE ResourceManagerHandle,
        PVOID *a8,
        _BYTE *a9)
{
  PVOID *v9; // r15
  void **Handle; // rdi
  _BYTE *v11; // r14
  __int64 v15; // rcx
  int result; // eax
  NTSTATUS v18; // ebx
  bool v19; // zf
  UNICODE_STRING *v20; // rcx
  void *v21; // rcx
  __int128 v22; // [rsp+40h] [rbp-41h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR v24; // [rsp+E0h] [rbp+5Fh] BYREF

  v9 = a8;
  Handle = ResourceManagerHandle;
  v11 = a9;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  v15 = a6;
  *ResourceManagerHandle = 0;
  *v9 = 0;
  v24 = 0;
  v22 = 0;
  *v11 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (int)TmpFindResourceManagerTm(v15, a3 + 16, v9) >= 0 )
  {
    result = ObOpenObjectByPointer(*v9, 0x200u, 0, 0x1F007Fu, (POBJECT_TYPE)TmResourceManagerObjectType, 0, Handle);
    v18 = result;
    if ( result < 0 )
      return result;
    *v11 = 1;
    return v18;
  }
  result = TmpRecoverSecurityDescriptor((__int64)a1, a2, *(_DWORD *)(a3 + 108), *(_DWORD *)(a3 + 104), &v24);
  if ( result < 0 )
    return result;
  v19 = *a1 == 260;
  v20 = 0;
  ObjectAttributes.SecurityDescriptor = v24;
  if ( v19 && a1[9] >= 0x48u && a1[13] >= 0x10000001u && *a4 )
  {
    result = TmpRecoverUnicodeString((_DWORD)a1, a2, a4[1], *a4, (__int64)&v22);
    if ( result < 0 )
      return result;
    v20 = (UNICODE_STRING *)&v22;
  }
  result = ZwCreateResourceManager(Handle, 0x1F007Fu, TmHandle, (LPGUID)(a3 + 16), &ObjectAttributes, 0, v20);
  if ( result >= 0 )
  {
    v21 = *Handle;
    ResourceManagerHandle = 0;
    v18 = ObReferenceObjectByHandle(
            v21,
            2u,
            (POBJECT_TYPE)TmResourceManagerObjectType,
            0,
            (PVOID *)&ResourceManagerHandle,
            0);
    *v9 = ResourceManagerHandle;
    if ( v18 < 0 )
    {
      ZwClose(*Handle);
      *Handle = 0;
    }
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x14000ebd4  push    rbp
0x14000ebd6  push    rbx
0x14000ebd7  push    rsi
0x14000ebd8  push    rdi
0x14000ebd9  push    r12
0x14000ebdb  push    r13
0x14000ebdd  push    r14
0x14000ebdf  push    r15
0x14000ebe1  lea     rbp, [rsp-7]
0x14000ebe6  sub     rsp, 88h
0x14000ebed  mov     r15, [rbp+3Fh+arg_38]
0x14000ebf4  xor     eax, eax
0x14000ebf6  mov     rdi, [rbp+3Fh+ResourceManagerHandle]
0x14000ebfa  xorps   xmm0, xmm0
0x14000ebfd  mov     r14, [rbp+3Fh+arg_40]
0x14000ec04  mov     r13d, edx
0x14000ec07  mov     rsi, r8
0x14000ec0a  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x14000ec12  mov     rbx, rcx
0x14000ec15  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 200h
0x14000ec1d  mov     rcx, [rbp+3Fh+arg_28]
0x14000ec21  lea     rdx, [r8+10h]
0x14000ec25  mov     [rdi], rax
0x14000ec28  mov     r8, r15
0x14000ec2b  mov     [r15], rax
0x14000ec2e  mov     r12, r9
0x14000ec31  mov     [rbp+3Fh+arg_10], rax
0x14000ec35  movups  [rbp+3Fh+var_80], xmm0
0x14000ec39  mov     [r14], al
0x14000ec3c  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x14000ec40  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x14000ec44  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x14000ec49  call    TmpFindResourceManagerTm
0x14000ec4e  test    eax, eax
0x14000ec50  js      short loc_14000EC98
0x14000ec52  mov     rax, cs:TmResourceManagerObjectType
0x14000ec59  mov     r9d, 1F007Fh; DesiredAccess
0x14000ec5f  mov     rcx, [r15]; Object
0x14000ec62  xor     r8d, r8d; PassedAccessState
0x14000ec65  mov     [rsp+0C0h+Handle], rdi; Handle
0x14000ec6a  mov     edx, 200h; HandleAttributes
0x14000ec6f  mov     [rsp+0C0h+AccessMode], 0; AccessMode
0x14000ec74  mov     [rsp+0C0h+ObjectType], rax; ObjectType
0x14000ec79  call    cs:__imp_ObOpenObjectByPointer
0x14000ec80  nop     dword ptr [rax+rax+00h]
0x14000ec85  mov     ebx, eax
0x14000ec87  test    eax, eax
0x14000ec89  js      loc_14000ED92
0x14000ec8f  mov     byte ptr [r14], 1
0x14000ec93  jmp     loc_14000ED90
0x14000ec98  mov     r9d, [rsi+68h]
0x14000ec9c  lea     rax, [rbp+3Fh+arg_10]
0x14000eca0  mov     r8d, [rsi+6Ch]
0x14000eca4  mov     edx, r13d
0x14000eca7  mov     rcx, rbx
0x14000ecaa  mov     [rsp+0C0h+ObjectType], rax
0x14000ecaf  call    TmpRecoverSecurityDescriptor
0x14000ecb4  xor     r14d, r14d
0x14000ecb7  test    eax, eax
0x14000ecb9  js      loc_14000ED92
0x14000ecbf  cmp     dword ptr [rbx], 104h
0x14000ecc5  mov     ecx, r14d
0x14000ecc8  mov     rax, [rbp+3Fh+arg_10]
0x14000eccc  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x14000ecd0  jnz     short loc_14000ED0F
0x14000ecd2  cmp     dword ptr [rbx+24h], 48h ; 'H'
0x14000ecd6  jb      short loc_14000ED0F
0x14000ecd8  cmp     dword ptr [rbx+34h], 10000001h
0x14000ecdf  jb      short loc_14000ED0F
0x14000ece1  mov     r9d, [r12]
0x14000ece5  test    r9d, r9d
0x14000ece8  jz      short loc_14000ED0F
0x14000ecea  mov     r8d, [r12+4]
0x14000ecef  lea     rax, [rbp+3Fh+var_80]
0x14000ecf3  mov     edx, r13d
0x14000ecf6  mov     [rsp+0C0h+ObjectType], rax
0x14000ecfb  mov     rcx, rbx
0x14000ecfe  call    TmpRecoverUnicodeString
0x14000ed03  test    eax, eax
0x14000ed05  js      loc_14000ED92
0x14000ed0b  lea     rcx, [rbp+3Fh+var_80]
0x14000ed0f  mov     r8, [rbp+3Fh+TmHandle]; TmHandle
0x14000ed13  lea     rax, [rbp+3Fh+ObjectAttributes]
0x14000ed17  mov     [rsp+0C0h+Handle], rcx; Description
0x14000ed1c  lea     r9, [rsi+10h]; ResourceManagerGuid
0x14000ed20  mov     dword ptr [rsp+0C0h+AccessMode], r14d; CreateOptions
0x14000ed25  mov     rcx, rdi; ResourceManagerHandle
0x14000ed28  mov     edx, 1F007Fh; DesiredAccess
0x14000ed2d  mov     [rsp+0C0h+ObjectType], rax; ObjectAttributes
0x14000ed32  call    cs:__imp_ZwCreateResourceManager
0x14000ed39  nop     dword ptr [rax+rax+00h]
0x14000ed3e  test    eax, eax
0x14000ed40  js      short loc_14000ED92
0x14000ed42  mov     r8, cs:TmResourceManagerObjectType; ObjectType
0x14000ed49  lea     rax, [rbp+3Fh+ResourceManagerHandle]
0x14000ed4d  mov     rcx, [rdi]; Handle
0x14000ed50  xor     r9d, r9d; AccessMode
0x14000ed53  mov     qword ptr [rsp+0C0h+AccessMode], r14; HandleInformation
0x14000ed58  mov     [rbp+3Fh+ResourceManagerHandle], r14
0x14000ed5c  mov     [rsp+0C0h+ObjectType], rax; Object
0x14000ed61  lea     edx, [r9+2]; DesiredAccess
0x14000ed65  call    cs:__imp_ObReferenceObjectByHandle
0x14000ed6c  nop     dword ptr [rax+rax+00h]
0x14000ed71  mov     ebx, eax
0x14000ed73  mov     rax, [rbp+3Fh+ResourceManagerHandle]
0x14000ed77  mov     [r15], rax
0x14000ed7a  test    ebx, ebx
0x14000ed7c  jns     short loc_14000ED90
0x14000ed7e  mov     rcx, [rdi]; Handle
0x14000ed81  call    cs:__imp_ZwClose
0x14000ed88  nop     dword ptr [rax+rax+00h]
0x14000ed8d  mov     [rdi], r14
0x14000ed90  mov     eax, ebx
0x14000ed92  add     rsp, 88h
0x14000ed99  pop     r15
0x14000ed9b  pop     r14
0x14000ed9d  pop     r13
0x14000ed9f  pop     r12
0x14000eda1  pop     rdi
0x14000eda2  pop     rsi
0x14000eda3  pop     rbx
0x14000eda4  pop     rbp
0x14000eda5  retn
```
