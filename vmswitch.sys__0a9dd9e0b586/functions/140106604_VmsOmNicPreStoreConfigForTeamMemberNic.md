# VmsOmNicPreStoreConfigForTeamMemberNic

- ea: `0x140106604`
- end: `0x1401068b1`
- name: `VmsOmNicPreStoreConfigForTeamMemberNic`
- size: `685`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING, PCUNICODE_STRING)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400c3694`

## callees

- `0x14001484c`
- `0x14002e45c`
- `0x140047038`
- `0x14008d760`
- `0x14008d810`
- `0x1400a6eb8`
- `0x1400a6f34`
- `0x1400a9ea0`
- `0x140105934`
- `0x140106604`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140106714`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106728`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010673b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106714`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140106728`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14010673b`
- `ntoskrnl!KeReleaseMutex` at `0x140106875`
- `ntoskrnl!KeReleaseMutex` at `0x140106875`
- `ntoskrnl!KeWaitForSingleObject` at `0x140106765`
- `ntoskrnl!KeWaitForSingleObject` at `0x140106765`

## pseudocode

```c
__int64 __fastcall VmsOmNicPreStoreConfigForTeamMemberNic(
        PCUNICODE_STRING SourceString,
        PCUNICODE_STRING a2,
        PCUNICODE_STRING a3)
{
  __int64 v6; // rbx
  unsigned int SwitchInitialized; // eax
  int v8; // edx
  int v9; // r8d
  __int64 v10; // rdi
  char v11; // si
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int v15; // [rsp+50h] [rbp-B0h]
  __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v19; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING v20; // [rsp+88h] [rbp-78h] BYREF
  __int64 v21[3]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v22[256]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v23[256]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v24[256]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v25[512]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v6 = 0;
  v16 = 0;
  v18 = 0;
  memset(v22, 0, 0xFEu);
  *(_QWORD *)&DestinationString.Length = 16646144;
  DestinationString.Buffer = (wchar_t *)v22;
  memset(v25, 0, 0x1FEu);
  v21[0] = 33423360;
  v21[1] = (__int64)v25;
  memset(v23, 0, 0xFEu);
  *(_QWORD *)&v19.Length = 16646144;
  v19.Buffer = (wchar_t *)v23;
  memset(v24, 0, 0xFEu);
  *(_QWORD *)&v20.Length = 16646144;
  v20.Buffer = (wchar_t *)v24;
  SwitchInitialized = VmsOmFindSwitchInitialized(a2, 0, &v18);
  v10 = v18;
  v15 = SwitchInitialized;
  if ( SwitchInitialized )
  {
    v11 = 0;
LABEL_7:
    if ( !SwitchInitialized )
      goto LABEL_12;
    goto LABEL_8;
  }
  RtlCopyUnicodeString(&DestinationString, SourceString);
  RtlCopyUnicodeString(&v19, a2);
  RtlCopyUnicodeString(&v20, a3);
  VmsUtilStrMakeRegistryCompliant(&DestinationString);
  KeWaitForSingleObject((PVOID)(v10 + 1144), Executive, 0, 0, 0);
  v11 = 1;
  v12 = VmsOmCreateObjectRegistryKey(0, 0, &DestinationString, &v16);
  v6 = v16;
  v15 = v12;
  if ( !v12 )
  {
    v15 = VmsCsAttrValueWriteString(v16, &VmsOmSwitchNameStr, &v19);
    if ( !v15 )
    {
      v15 = VmsCsAttrValueWriteString(v6, &VmsOmPortNameStr, &v20);
      if ( !v15 )
      {
        SwitchInitialized = VmsCsAttrValueWriteULong(v6, &VmsOmNicTypeStr, 2);
        v15 = SwitchInitialized;
        goto LABEL_7;
      }
    }
  }
LABEL_8:
  if ( v10 )
    v13 = *(_QWORD *)(v10 + 9096);
  else
    LODWORD(v13) = VmsIfrLog;
  WPP_RECORDER_SF_ZZZd(
    v13,
    v8,
    v9,
    66,
    (__int64)WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids,
    (__int64)a2,
    (__int64)a3,
    (__int64)SourceString,
    v15);
  VmsEtwTraceSwitchFailure(&VM_FAILED_TO_STORE_CONFIG_FOR_NIC, 0, (__int64)&DestinationString, (__int64)v21);
LABEL_12:
  if ( v6 )
    VmsCsKeyClose(v6);
  if ( v11 )
  {
    KeReleaseMutex((PRKMUTEX)(v10 + 1144), 0);
    VmsOmpObjectDereference(v10, 0);
  }
  return v15;
}

```

## disassembly

```asm
0x140106604  push    rbp
0x140106606  push    rbx
0x140106607  push    rsi
0x140106608  push    rdi
0x140106609  push    r12
0x14010660b  push    r14
0x14010660d  push    r15
0x14010660f  lea     rbp, [rsp-4C0h]
0x140106617  sub     rsp, 5C0h
0x14010661e  mov     rax, cs:__security_cookie
0x140106625  xor     rax, rsp
0x140106628  mov     [rbp+4F0h+var_40], rax
0x14010662f  xor     eax, eax
0x140106631  mov     [rsp+5F0h+var_5A0], 0
0x140106639  mov     r12, r8
0x14010663c  mov     [rsp+5F0h+var_59C], ax
0x140106641  mov     r14, rdx
0x140106644  mov     [rsp+5F0h+var_59A], al
0x140106648  mov     r15, rcx
0x14010664b  xor     ebx, ebx
0x14010664d  mov     esi, 0FEh
0x140106652  mov     [rsp+5F0h+var_598], rbx
0x140106657  mov     r8d, esi; Size
0x14010665a  mov     [rsp+5F0h+var_580], rbx
0x14010665f  xor     edx, edx; Val
0x140106661  lea     rcx, [rbp+4F0h+var_540]; void *
0x140106665  call    memset
0x14010666a  lea     rax, [rbp+4F0h+var_540]
0x14010666e  mov     qword ptr [rsp+5F0h+DestinationString.Length], 0FE0000h
0x140106677  xor     edx, edx; Val
0x140106679  mov     [rsp+5F0h+DestinationString.Buffer], rax
0x14010667e  mov     r8d, 1FEh; Size
0x140106684  lea     rcx, [rbp+4F0h+var_240]; void *
0x14010668b  call    memset
0x140106690  lea     rax, [rbp+4F0h+var_240]
0x140106697  mov     [rbp+4F0h+var_558], 1FE0000h
0x14010669f  mov     r8d, esi; Size
0x1401066a2  mov     [rbp+4F0h+var_550], rax
0x1401066a6  xor     edx, edx; Val
0x1401066a8  lea     rcx, [rbp+4F0h+var_440]; void *
0x1401066af  call    memset
0x1401066b4  lea     rax, [rbp+4F0h+var_440]
0x1401066bb  mov     qword ptr [rsp+5F0h+var_578.Length], 0FE0000h
0x1401066c4  mov     r8d, esi; Size
0x1401066c7  mov     [rbp+4F0h+var_578.Buffer], rax
0x1401066cb  xor     edx, edx; Val
0x1401066cd  lea     rcx, [rbp+4F0h+var_340]; void *
0x1401066d4  call    memset
0x1401066d9  lea     rax, [rbp+4F0h+var_340]
0x1401066e0  mov     qword ptr [rbp+4F0h+var_568.Length], 0FE0000h
0x1401066e8  lea     r8, [rsp+5F0h+var_580]
0x1401066ed  mov     [rbp+4F0h+var_568.Buffer], rax
0x1401066f1  xor     edx, edx
0x1401066f3  mov     rcx, r14
0x1401066f6  call    VmsOmFindSwitchInitialized
0x1401066fb  mov     rdi, [rsp+5F0h+var_580]
0x140106700  mov     [rsp+5F0h+var_5A0], eax
0x140106704  test    eax, eax
0x140106706  jnz     loc_1401067E4
0x14010670c  mov     rdx, r15; SourceString
0x14010670f  lea     rcx, [rsp+5F0h+DestinationString]; DestinationString
0x140106714  call    cs:__imp_RtlCopyUnicodeString
0x14010671b  nop     dword ptr [rax+rax+00h]
0x140106720  mov     rdx, r14; SourceString
0x140106723  lea     rcx, [rsp+5F0h+var_578]; DestinationString
0x140106728  call    cs:__imp_RtlCopyUnicodeString
0x14010672f  nop     dword ptr [rax+rax+00h]
0x140106734  mov     rdx, r12; SourceString
0x140106737  lea     rcx, [rbp+4F0h+var_568]; DestinationString
0x14010673b  call    cs:__imp_RtlCopyUnicodeString
0x140106742  nop     dword ptr [rax+rax+00h]
0x140106747  lea     rcx, [rsp+5F0h+DestinationString]
0x14010674c  call    VmsUtilStrMakeRegistryCompliant
0x140106751  xor     r8d, r8d; WaitMode
0x140106754  mov     [rsp+5F0h+Timeout], rbx; Timeout
0x140106759  xor     edx, edx; WaitReason
0x14010675b  lea     rcx, [rdi+478h]; Object
0x140106762  xor     r9d, r9d; Alertable
0x140106765  call    cs:__imp_KeWaitForSingleObject
0x14010676c  nop     dword ptr [rax+rax+00h]
0x140106771  lea     r9, [rsp+5F0h+var_598]
0x140106776  xor     edx, edx
0x140106778  lea     r8, [rsp+5F0h+DestinationString]
0x14010677d  xor     ecx, ecx
0x14010677f  mov     sil, 1
0x140106782  call    VmsOmCreateObjectRegistryKey
0x140106787  mov     rbx, [rsp+5F0h+var_598]
0x14010678c  mov     [rsp+5F0h+var_5A0], eax
0x140106790  test    eax, eax
0x140106792  jnz     short loc_1401067EB
0x140106794  lea     r8, [rsp+5F0h+var_578]
0x140106799  mov     rcx, rbx
0x14010679c  lea     rdx, VmsOmSwitchNameStr
0x1401067a3  call    VmsCsAttrValueWriteString
0x1401067a8  mov     [rsp+5F0h+var_5A0], eax
0x1401067ac  test    eax, eax
0x1401067ae  jnz     short loc_1401067EB
0x1401067b0  lea     r8, [rbp+4F0h+var_568]
0x1401067b4  mov     rcx, rbx
0x1401067b7  lea     rdx, VmsOmPortNameStr
0x1401067be  call    VmsCsAttrValueWriteString
0x1401067c3  mov     [rsp+5F0h+var_5A0], eax
0x1401067c7  test    eax, eax
0x1401067c9  jnz     short loc_1401067EB
0x1401067cb  lea     r8d, [rax+2]
0x1401067cf  mov     rcx, rbx
0x1401067d2  lea     rdx, VmsOmNicTypeStr
0x1401067d9  call    VmsCsAttrValueWriteULong
0x1401067de  mov     [rsp+5F0h+var_5A0], eax
0x1401067e2  jmp     short loc_1401067E7
0x1401067e4  xor     sil, sil
0x1401067e7  test    eax, eax
0x1401067e9  jz      short loc_14010685A
0x1401067eb  test    rdi, rdi
0x1401067ee  jz      short loc_1401067F9
0x1401067f0  mov     rcx, [rdi+2388h]
0x1401067f7  jmp     short loc_140106800
0x1401067f9  mov     rcx, cs:VmsIfrLog
0x140106800  mov     eax, [rsp+5F0h+var_5A0]
0x140106804  mov     r9d, 42h ; 'B'
0x14010680a  mov     [rsp+5F0h+var_5B0], eax
0x14010680e  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x140106815  mov     [rsp+5F0h+var_5B8], r15
0x14010681a  mov     [rsp+5F0h+var_5C0], r12
0x14010681f  mov     [rsp+5F0h+var_5C8], r14
0x140106824  mov     [rsp+5F0h+Timeout], rax
0x140106829  call    WPP_RECORDER_SF_ZZZd
0x14010682e  lea     rax, [rbp+4F0h+var_558]
0x140106832  mov     [rsp+5F0h+var_5C0], rax; __int64
0x140106837  lea     r9, [rsp+5F0h+var_5A0]
0x14010683c  lea     rax, [rsp+5F0h+DestinationString]
0x140106841  mov     [rsp+5F0h+var_5C8], rax; __int64
0x140106846  lea     rcx, VM_FAILED_TO_STORE_CONFIG_FOR_NIC; EventDescriptor
0x14010684d  mov     dword ptr [rsp+5F0h+Timeout], 0; char
0x140106855  call    VmsEtwTraceSwitchFailure
0x14010685a  test    rbx, rbx
0x14010685d  jz      short loc_140106867
0x14010685f  mov     rcx, rbx
0x140106862  call    VmsCsKeyClose
0x140106867  test    sil, sil
0x14010686a  jz      short loc_14010688B
0x14010686c  lea     rcx, [rdi+478h]; Mutex
0x140106873  xor     edx, edx; Wait
0x140106875  call    cs:__imp_KeReleaseMutex
0x14010687c  nop     dword ptr [rax+rax+00h]
0x140106881  xor     edx, edx
0x140106883  mov     rcx, rdi
0x140106886  call    VmsOmpObjectDereference
0x14010688b  mov     eax, [rsp+5F0h+var_5A0]
0x14010688f  mov     rcx, [rbp+4F0h+var_40]
0x140106896  xor     rcx, rsp; StackCookie
0x140106899  call    __security_check_cookie
0x14010689e  add     rsp, 5C0h
0x1401068a5  pop     r15
0x1401068a7  pop     r14
0x1401068a9  pop     r12
0x1401068ab  pop     rdi
0x1401068ac  pop     rsi
0x1401068ad  pop     rbx
0x1401068ae  pop     rbp
0x1401068af  retn
```
