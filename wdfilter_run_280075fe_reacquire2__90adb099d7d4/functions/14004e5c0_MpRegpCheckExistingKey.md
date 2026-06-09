# MpRegpCheckExistingKey

- ea: `0x14004e5c0`
- end: `0x14004ea56`
- name: `MpRegpCheckExistingKey`
- size: `1174`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004dda0`
- `0x14004ef30`

## callees

- `0x140003460`
- `0x1400051bc`
- `0x140011890`
- `0x1400118d0`
- `0x14004b6d0`
- `0x14004e5c0`
- `0x14004f6bc`
- `0x14004fcd0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14004e6d6`
- `ntoskrnl!ZwOpenKey` at `0x14004e6d6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14004e693`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14004e693`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e61e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e81d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e61e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004e81d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004e634`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004e634`
- `ntoskrnl!ZwClose` at `0x14004e705`
- `ntoskrnl!ZwClose` at `0x14004e738`
- `ntoskrnl!ZwClose` at `0x14004e705`
- `ntoskrnl!ZwClose` at `0x14004e738`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e7ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e7c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ea2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e7ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e7c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ea2f`

## string_xrefs

- `0x14004e608`: `\Registry`

## pseudocode

```c
__int64 __fastcall MpRegpCheckExistingKey(struct _UNICODE_STRING **a1, _BYTE *a2, _QWORD *a3)
{
  void *v3; // rdi
  void *v4; // rbx
  int appended; // r13d
  struct _UNICODE_STRING *v8; // r15
  struct _UNICODE_STRING *v9; // rsi
  HANDLE v10; // rax
  NTSTATUS v11; // eax
  NTSTATUS v12; // esi
  PVOID v13; // rbx
  void (__fastcall *v14)(PVOID); // rax
  int KeyName; // eax
  __int64 v17; // rdx
  void *v18; // rcx
  void *v19; // [rsp+40h] [rbp-69h] BYREF
  void *v20; // [rsp+48h] [rbp-61h] BYREF
  _QWORD *v21; // [rsp+50h] [rbp-59h]
  HANDLE Handle; // [rsp+58h] [rbp-51h] BYREF
  PVOID Entry; // [rsp+60h] [rbp-49h]
  void *KeyHandle; // [rsp+68h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-9h] BYREF
  struct _UNICODE_STRING v27; // [rsp+B0h] [rbp+7h] BYREF

  v3 = 0;
  v21 = a3;
  v4 = 0;
  *a3 = 0;
  *a2 = 0;
  Entry = 0;
  v20 = 0;
  v19 = 0;
  appended = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry");
  if ( RtlPrefixUnicodeString(&DestinationString, *a1, 1u) )
    v8 = 0;
  else
    v8 = a1[1];
  v9 = *a1;
  v10 = 0;
  KeyHandle = 0;
  Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( v8 )
  {
    v11 = ObOpenObjectByPointer(v8, 0x200u, 0, 0x20019u, 0, 0, &Handle);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_0bb7950fbf1c3ce6de4fbf0752af6f2f_Traceguids,
          KeGetCurrentThread(),
          v11);
      }
      goto LABEL_26;
    }
    v10 = Handle;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v10;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = v9;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = ZwOpenKey(&KeyHandle, 0x82000000, &ObjectAttributes);
  if ( Handle
    && ((*(_DWORD *)(MpData + 864) & 2) != 0 || (((unsigned __int64)Handle + 2147483568) & 0xFFFFFFFFFFFFFFEFuLL) != 0) )
  {
    ZwClose(Handle);
  }
  if ( v12 >= 0 )
  {
    if ( KeyHandle
      && ((*(_DWORD *)(MpData + 864) & 2) != 0
       || (((unsigned __int64)KeyHandle + 2147483568) & 0xFFFFFFFFFFFFFFEFuLL) != 0) )
    {
      ZwClose(KeyHandle);
    }
    *a2 = 1;
    goto LABEL_14;
  }
  if ( !v8 )
  {
    appended = MpRegpCopyUnicodeString(*a1);
    if ( appended >= 0 )
    {
LABEL_25:
      *v21 = v19;
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v17 = 19;
      goto LABEL_46;
    }
    goto LABEL_47;
  }
LABEL_26:
  v27 = 0;
  RtlInitUnicodeString(&v27, L"\\");
  KeyName = MpRegpGetKeyName(v8);
  appended = KeyName;
  if ( KeyName < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        KeyName);
    }
  }
  else
  {
    appended = MpAppendUnicodeStringToUnicodeString(Entry, &v27, &v20, 1399083085);
    if ( appended >= 0 )
    {
      v4 = v20;
      appended = MpAppendUnicodeStringToUnicodeString(v20, *a1, &v19, 1399083085);
      if ( appended >= 0 )
        goto LABEL_25;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v17 = 18;
LABEL_46:
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v17,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          appended);
      }
LABEL_47:
      v3 = v19;
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        17,
        WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
        KeGetCurrentThread(),
        appended);
    }
    v4 = v20;
  }
LABEL_14:
  if ( v4 )
    ExFreePoolWithTag(v4, 0x5364504Du);
  v13 = Entry;
  if ( Entry )
  {
    v14 = (void (__fastcall *)(PVOID))*((_QWORD *)MpRegData + 5);
    if ( v14 )
    {
      v14(Entry);
    }
    else
    {
      v18 = (void *)*((_QWORD *)Entry + 2);
      if ( v18 )
        ExFreePoolWithTag(v18, 0x4B72504Du);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v13);
    }
  }
  if ( v3 )
    ExFreePoolWithTag(v3, 0x5364504Du);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14004e5c0  mov     [rsp-8+arg_18], rbx
0x14004e5c5  push    rbp
0x14004e5c6  push    rsi
0x14004e5c7  push    rdi
0x14004e5c8  push    r12
0x14004e5ca  push    r13
0x14004e5cc  push    r14
0x14004e5ce  push    r15
0x14004e5d0  lea     rbp, [rsp-27h]
0x14004e5d5  sub     rsp, 0D0h
0x14004e5dc  mov     rax, cs:__security_cookie
0x14004e5e3  xor     rax, rsp
0x14004e5e6  mov     [rbp+57h+var_40], rax
0x14004e5ea  xor     edi, edi
0x14004e5ec  mov     [rbp+57h+var_B0], r8
0x14004e5f0  mov     ebx, edi
0x14004e5f2  mov     [r8], rdi
0x14004e5f5  mov     [rdx], bl
0x14004e5f7  mov     r12, rdx
0x14004e5fa  mov     r14, rcx
0x14004e5fd  mov     [rbp+57h+Entry], rdi
0x14004e601  xorps   xmm0, xmm0
0x14004e604  mov     [rbp+57h+var_B8], rbx
0x14004e608  lea     rdx, aRegistry; "\\Registry"
0x14004e60f  mov     [rbp+57h+var_C0], rdi
0x14004e613  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004e617  mov     r13d, edi
0x14004e61a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004e61e  call    cs:__imp_RtlInitUnicodeString
0x14004e625  nop     dword ptr [rax+rax+00h]
0x14004e62a  mov     rdx, [r14]; String2
0x14004e62d  lea     rcx, [rbp+57h+DestinationString]; String1
0x14004e631  mov     r8b, 1; CaseInSensitive
0x14004e634  call    cs:__imp_RtlPrefixUnicodeString
0x14004e63b  nop     dword ptr [rax+rax+00h]
0x14004e640  test    al, al
0x14004e642  jnz     loc_14004E7D0
0x14004e648  mov     r15, [r14+8]
0x14004e64c  mov     rsi, [r14]
0x14004e64f  xor     eax, eax
0x14004e651  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x14004e655  xorps   xmm0, xmm0
0x14004e658  mov     dword ptr [rbp+57h+ObjectAttributes.SecurityQualityOfService], eax
0x14004e65b  mov     [rbp+57h+KeyHandle], rdi
0x14004e65f  mov     [rbp+57h+var_A8], rax
0x14004e663  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14004e667  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004e66b  test    r15, r15
0x14004e66e  jz      short loc_14004E6AB
0x14004e670  lea     rax, [rbp+57h+var_A8]
0x14004e674  mov     r9d, 20019h; DesiredAccess
0x14004e67a  mov     [rsp+100h+Handle], rax; Handle
0x14004e67f  xor     r8d, r8d; PassedAccessState
0x14004e682  mov     [rsp+100h+AccessMode], bl; AccessMode
0x14004e686  mov     edx, 200h; HandleAttributes
0x14004e68b  mov     rcx, r15; Object
0x14004e68e  mov     [rsp+100h+ObjectType], rdi; ObjectType
0x14004e693  call    cs:__imp_ObOpenObjectByPointer
0x14004e69a  nop     dword ptr [rax+rax+00h]
0x14004e69f  test    eax, eax
0x14004e6a1  js      loc_14004E8C0
0x14004e6a7  mov     rax, [rbp+57h+var_A8]
0x14004e6ab  xorps   xmm0, xmm0
0x14004e6ae  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004e6b5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004e6b9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14004e6bd  mov     edx, 82000000h; DesiredAccess
0x14004e6c2  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14004e6c9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14004e6cd  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x14004e6d1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004e6d6  call    cs:__imp_ZwOpenKey
0x14004e6dd  nop     dword ptr [rax+rax+00h]
0x14004e6e2  mov     rcx, [rbp+57h+var_A8]; Handle
0x14004e6e6  mov     esi, eax
0x14004e6e8  test    rcx, rcx
0x14004e6eb  jz      short loc_14004E711
0x14004e6ed  mov     rdx, cs:MpData
0x14004e6f4  mov     r8d, [rdx+360h]
0x14004e6fb  test    r8b, 2
0x14004e6ff  jz      loc_14004E914
0x14004e705  call    cs:__imp_ZwClose
0x14004e70c  nop     dword ptr [rax+rax+00h]
0x14004e711  test    esi, esi
0x14004e713  js      loc_14004E7D8
0x14004e719  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14004e71d  test    rcx, rcx
0x14004e720  jz      short loc_14004E744
0x14004e722  mov     rax, cs:MpData
0x14004e729  mov     edx, [rax+360h]
0x14004e72f  test    dl, 2
0x14004e732  jz      loc_14004E92D
0x14004e738  call    cs:__imp_ZwClose
0x14004e73f  nop     dword ptr [rax+rax+00h]
0x14004e744  mov     byte ptr [r12], 1
0x14004e749  test    rbx, rbx
0x14004e74c  jnz     short loc_14004E7A4
0x14004e74e  mov     rbx, [rbp+57h+Entry]
0x14004e752  test    rbx, rbx
0x14004e755  jz      short loc_14004E774
0x14004e757  mov     rax, cs:MpRegData
0x14004e75e  mov     rax, [rax+28h]
0x14004e762  test    rax, rax
0x14004e765  jz      loc_14004EA21
0x14004e76b  mov     rcx, rbx
0x14004e76e  call    cs:__guard_dispatch_icall_fptr
0x14004e774  test    rdi, rdi
0x14004e777  jnz     short loc_14004E7BA
0x14004e779  mov     eax, r13d
0x14004e77c  mov     rcx, [rbp+57h+var_40]
0x14004e780  xor     rcx, rsp; StackCookie
0x14004e783  call    __security_check_cookie
0x14004e788  mov     rbx, [rsp+100h+arg_18]
0x14004e790  add     rsp, 0D0h
0x14004e797  pop     r15
0x14004e799  pop     r14
0x14004e79b  pop     r13
0x14004e79d  pop     r12
0x14004e79f  pop     rdi
0x14004e7a0  pop     rsi
0x14004e7a1  pop     rbp
0x14004e7a2  retn
0x14004e7a4  mov     edx, 5364504Dh; Tag
0x14004e7a9  mov     rcx, rbx; P
0x14004e7ac  call    cs:__imp_ExFreePoolWithTag
0x14004e7b3  nop     dword ptr [rax+rax+00h]
0x14004e7b8  jmp     short loc_14004E74E
0x14004e7ba  mov     edx, 5364504Dh; Tag
0x14004e7bf  mov     rcx, rdi; P
0x14004e7c2  call    cs:__imp_ExFreePoolWithTag
0x14004e7c9  nop     dword ptr [rax+rax+00h]
0x14004e7ce  jmp     short loc_14004E779
0x14004e7d0  mov     r15, rdi
0x14004e7d3  jmp     loc_14004E64C
0x14004e7d8  test    r15, r15
0x14004e7db  jnz     short loc_14004E804
0x14004e7dd  mov     rcx, [r14]; SourceString
0x14004e7e0  lea     rdx, [rbp+57h+var_C0]
0x14004e7e4  call    MpRegpCopyUnicodeString
0x14004e7e9  mov     r13d, eax
0x14004e7ec  test    eax, eax
0x14004e7ee  js      loc_14004EA05
0x14004e7f4  mov     rcx, [rbp+57h+var_B0]
0x14004e7f8  mov     rax, [rbp+57h+var_C0]
0x14004e7fc  mov     [rcx], rax
0x14004e7ff  jmp     loc_14004E749
0x14004e804  lea     rsi, WPP_GLOBAL_Control
0x14004e80b  xorps   xmm0, xmm0
0x14004e80e  lea     rdx, Source; "\\"
0x14004e815  lea     rcx, [rbp+57h+var_50]; DestinationString
0x14004e819  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x14004e81d  call    cs:__imp_RtlInitUnicodeString
0x14004e824  nop     dword ptr [rax+rax+00h]
0x14004e829  lea     rdx, [rbp+57h+Entry]
0x14004e82d  mov     rcx, r15; Object
0x14004e830  call    MpRegpGetKeyName
0x14004e835  mov     r13d, eax
0x14004e838  test    eax, eax
0x14004e83a  js      loc_14004E945
0x14004e840  mov     rcx, [rbp+57h+Entry]
0x14004e844  lea     r8, [rbp+57h+var_B8]
0x14004e848  mov     r9d, 5364504Dh
0x14004e84e  lea     rdx, [rbp+57h+var_50]
0x14004e852  call    MpAppendUnicodeStringToUnicodeString
0x14004e857  mov     r13d, eax
0x14004e85a  test    eax, eax
0x14004e85c  js      short loc_14004E8A7
0x14004e85e  mov     rbx, [rbp+57h+var_B8]
0x14004e862  lea     r8, [rbp+57h+var_C0]
0x14004e866  mov     rdx, [r14]
0x14004e869  mov     rcx, rbx
0x14004e86c  mov     r9d, 5364504Dh
0x14004e872  call    MpAppendUnicodeStringToUnicodeString
0x14004e877  mov     r13d, eax
0x14004e87a  test    eax, eax
0x14004e87c  jns     loc_14004E7F4
0x14004e882  mov     rax, cs:WPP_GLOBAL_Control
0x14004e889  cmp     rax, rsi
0x14004e88c  jz      loc_14004E9FC
0x14004e892  mov     eax, [rax+2Ch]
0x14004e895  test    al, 1
0x14004e897  jz      loc_14004E9FC
0x14004e89d  mov     edx, 12h
0x14004e8a2  jmp     loc_14004E9D4
0x14004e8a7  mov     rax, cs:WPP_GLOBAL_Control
0x14004e8ae  cmp     rax, rsi
0x14004e8b1  jnz     loc_14004E992
0x14004e8b7  mov     rbx, [rbp+57h+var_B8]
0x14004e8bb  jmp     loc_14004E749
0x14004e8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e8c7  lea     rsi, WPP_GLOBAL_Control
0x14004e8ce  cmp     rcx, rsi
0x14004e8d1  jz      loc_14004E80B
0x14004e8d7  mov     ecx, [rcx+2Ch]
0x14004e8da  test    cl, 1
0x14004e8dd  jz      loc_14004E80B
0x14004e8e3  lfence
0x14004e8e6  mov     r9, gs:188h
0x14004e8ef  lea     r8, WPP_0bb7950fbf1c3ce6de4fbf0752af6f2f_Traceguids
0x14004e8f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e8fd  mov     edx, 0Eh
0x14004e902  mov     dword ptr [rsp+100h+ObjectType], eax
0x14004e906  mov     rcx, [rcx+18h]
0x14004e90a  call    WPP_SF_qD
0x14004e90f  jmp     loc_14004E80B
0x14004e914  lea     rdx, [rcx+7FFFFFB0h]
0x14004e91b  test    rdx, 0FFFFFFFFFFFFFFEFh
0x14004e922  jz      loc_14004E711
0x14004e928  jmp     loc_14004E705
0x14004e92d  lea     rax, [rcx+7FFFFFB0h]
0x14004e934  test    rax, 0FFFFFFFFFFFFFFEFh
0x14004e93a  jz      loc_14004E744
0x14004e940  jmp     loc_14004E738
0x14004e945  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e94c  cmp     rcx, rsi
0x14004e94f  jz      loc_14004E749
0x14004e955  mov     ecx, [rcx+2Ch]
0x14004e958  test    cl, 4
0x14004e95b  jz      loc_14004E749
0x14004e961  lfence
0x14004e964  mov     r9, gs:188h
0x14004e96d  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004e974  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e97b  mov     edx, 10h
0x14004e980  mov     dword ptr [rsp+100h+ObjectType], eax
0x14004e984  mov     rcx, [rcx+18h]
0x14004e988  call    WPP_SF_qD
0x14004e98d  jmp     loc_14004E749
0x14004e992  mov     eax, [rax+2Ch]
0x14004e995  test    al, 1
0x14004e997  jz      loc_14004E8B7
0x14004e99d  lfence
0x14004e9a0  mov     r9, gs:188h
0x14004e9a9  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004e9b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e9b7  mov     edx, 11h
0x14004e9bc  mov     dword ptr [rsp+100h+ObjectType], r13d
0x14004e9c1  mov     rcx, [rcx+18h]
0x14004e9c5  call    WPP_SF_qD
0x14004e9ca  jmp     loc_14004E8B7
0x14004e9cf  mov     edx, 13h
0x14004e9d4  lfence
0x14004e9d7  mov     r9, gs:188h
0x14004e9e0  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004e9e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e9ee  mov     dword ptr [rsp+100h+ObjectType], r13d
0x14004e9f3  mov     rcx, [rcx+18h]
0x14004e9f7  call    WPP_SF_qD
0x14004e9fc  mov     rdi, [rbp+57h+var_C0]
0x14004ea00  jmp     loc_14004E749
0x14004ea05  mov     rax, cs:WPP_GLOBAL_Control
0x14004ea0c  lea     rsi, WPP_GLOBAL_Control
0x14004ea13  cmp     rax, rsi
0x14004ea16  jz      short loc_14004E9FC
0x14004ea18  mov     eax, [rax+2Ch]
0x14004ea1b  test    al, 1
0x14004ea1d  jz      short loc_14004E9FC
0x14004ea1f  jmp     short loc_14004E9CF
0x14004ea21  mov     rcx, [rbx+10h]; P
0x14004ea25  test    rcx, rcx
0x14004ea28  jz      short loc_14004EA3B
0x14004ea2a  mov     edx, 4B72504Dh; Tag
0x14004ea2f  call    cs:__imp_ExFreePoolWithTag
0x14004ea36  nop     dword ptr [rax+rax+00h]
0x14004ea3b  mov     rcx, cs:MpRegData
0x14004ea42  mov     rdx, rbx; Entry
0x14004ea45  add     rcx, 400h; Lookaside
0x14004ea4c  call    ExFreeToNPagedLookasideList
0x14004ea51  jmp     loc_14004E774
```
