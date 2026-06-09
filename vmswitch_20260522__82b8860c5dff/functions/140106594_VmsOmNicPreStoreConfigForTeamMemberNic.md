# VmsOmNicPreStoreConfigForTeamMemberNic

- ea: `0x140106594`
- end: `0x140106841`
- name: `VmsOmNicPreStoreConfigForTeamMemberNic`
- size: `685`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, PCUNICODE_STRING, PCUNICODE_STRING)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400c3624`

## callees

- `0x14001484c`
- `0x14002e45c`
- `0x140047038`
- `0x14008d760`
- `0x14008d810`
- `0x1400a6e48`
- `0x1400a6ec4`
- `0x1400a9e30`
- `0x1401058c4`
- `0x140106594`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1401066a4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401066b8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401066cb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401066a4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401066b8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401066cb`
- `ntoskrnl!KeReleaseMutex` at `0x140106805`
- `ntoskrnl!KeReleaseMutex` at `0x140106805`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401066f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401066f5`

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
0x140106594  push    rbp
0x140106596  push    rbx
0x140106597  push    rsi
0x140106598  push    rdi
0x140106599  push    r12
0x14010659b  push    r14
0x14010659d  push    r15
0x14010659f  lea     rbp, [rsp-4C0h]
0x1401065a7  sub     rsp, 5C0h
0x1401065ae  mov     rax, cs:__security_cookie
0x1401065b5  xor     rax, rsp
0x1401065b8  mov     [rbp+4F0h+var_40], rax
0x1401065bf  xor     eax, eax
0x1401065c1  mov     [rsp+5F0h+var_5A0], 0
0x1401065c9  mov     r12, r8
0x1401065cc  mov     [rsp+5F0h+var_59C], ax
0x1401065d1  mov     r14, rdx
0x1401065d4  mov     [rsp+5F0h+var_59A], al
0x1401065d8  mov     r15, rcx
0x1401065db  xor     ebx, ebx
0x1401065dd  mov     esi, 0FEh
0x1401065e2  mov     [rsp+5F0h+var_598], rbx
0x1401065e7  mov     r8d, esi; Size
0x1401065ea  mov     [rsp+5F0h+var_580], rbx
0x1401065ef  xor     edx, edx; Val
0x1401065f1  lea     rcx, [rbp+4F0h+var_540]; void *
0x1401065f5  call    memset
0x1401065fa  lea     rax, [rbp+4F0h+var_540]
0x1401065fe  mov     qword ptr [rsp+5F0h+DestinationString.Length], 0FE0000h
0x140106607  xor     edx, edx; Val
0x140106609  mov     [rsp+5F0h+DestinationString.Buffer], rax
0x14010660e  mov     r8d, 1FEh; Size
0x140106614  lea     rcx, [rbp+4F0h+var_240]; void *
0x14010661b  call    memset
0x140106620  lea     rax, [rbp+4F0h+var_240]
0x140106627  mov     [rbp+4F0h+var_558], 1FE0000h
0x14010662f  mov     r8d, esi; Size
0x140106632  mov     [rbp+4F0h+var_550], rax
0x140106636  xor     edx, edx; Val
0x140106638  lea     rcx, [rbp+4F0h+var_440]; void *
0x14010663f  call    memset
0x140106644  lea     rax, [rbp+4F0h+var_440]
0x14010664b  mov     qword ptr [rsp+5F0h+var_578.Length], 0FE0000h
0x140106654  mov     r8d, esi; Size
0x140106657  mov     [rbp+4F0h+var_578.Buffer], rax
0x14010665b  xor     edx, edx; Val
0x14010665d  lea     rcx, [rbp+4F0h+var_340]; void *
0x140106664  call    memset
0x140106669  lea     rax, [rbp+4F0h+var_340]
0x140106670  mov     qword ptr [rbp+4F0h+var_568.Length], 0FE0000h
0x140106678  lea     r8, [rsp+5F0h+var_580]
0x14010667d  mov     [rbp+4F0h+var_568.Buffer], rax
0x140106681  xor     edx, edx
0x140106683  mov     rcx, r14
0x140106686  call    VmsOmFindSwitchInitialized
0x14010668b  mov     rdi, [rsp+5F0h+var_580]
0x140106690  mov     [rsp+5F0h+var_5A0], eax
0x140106694  test    eax, eax
0x140106696  jnz     loc_140106774
0x14010669c  mov     rdx, r15; SourceString
0x14010669f  lea     rcx, [rsp+5F0h+DestinationString]; DestinationString
0x1401066a4  call    cs:__imp_RtlCopyUnicodeString
0x1401066ab  nop     dword ptr [rax+rax+00h]
0x1401066b0  mov     rdx, r14; SourceString
0x1401066b3  lea     rcx, [rsp+5F0h+var_578]; DestinationString
0x1401066b8  call    cs:__imp_RtlCopyUnicodeString
0x1401066bf  nop     dword ptr [rax+rax+00h]
0x1401066c4  mov     rdx, r12; SourceString
0x1401066c7  lea     rcx, [rbp+4F0h+var_568]; DestinationString
0x1401066cb  call    cs:__imp_RtlCopyUnicodeString
0x1401066d2  nop     dword ptr [rax+rax+00h]
0x1401066d7  lea     rcx, [rsp+5F0h+DestinationString]
0x1401066dc  call    VmsUtilStrMakeRegistryCompliant
0x1401066e1  xor     r8d, r8d; WaitMode
0x1401066e4  mov     [rsp+5F0h+Timeout], rbx; Timeout
0x1401066e9  xor     edx, edx; WaitReason
0x1401066eb  lea     rcx, [rdi+478h]; Object
0x1401066f2  xor     r9d, r9d; Alertable
0x1401066f5  call    cs:__imp_KeWaitForSingleObject
0x1401066fc  nop     dword ptr [rax+rax+00h]
0x140106701  lea     r9, [rsp+5F0h+var_598]
0x140106706  xor     edx, edx
0x140106708  lea     r8, [rsp+5F0h+DestinationString]
0x14010670d  xor     ecx, ecx
0x14010670f  mov     sil, 1
0x140106712  call    VmsOmCreateObjectRegistryKey
0x140106717  mov     rbx, [rsp+5F0h+var_598]
0x14010671c  mov     [rsp+5F0h+var_5A0], eax
0x140106720  test    eax, eax
0x140106722  jnz     short loc_14010677B
0x140106724  lea     r8, [rsp+5F0h+var_578]
0x140106729  mov     rcx, rbx
0x14010672c  lea     rdx, VmsOmSwitchNameStr
0x140106733  call    VmsCsAttrValueWriteString
0x140106738  mov     [rsp+5F0h+var_5A0], eax
0x14010673c  test    eax, eax
0x14010673e  jnz     short loc_14010677B
0x140106740  lea     r8, [rbp+4F0h+var_568]
0x140106744  mov     rcx, rbx
0x140106747  lea     rdx, VmsOmPortNameStr
0x14010674e  call    VmsCsAttrValueWriteString
0x140106753  mov     [rsp+5F0h+var_5A0], eax
0x140106757  test    eax, eax
0x140106759  jnz     short loc_14010677B
0x14010675b  lea     r8d, [rax+2]
0x14010675f  mov     rcx, rbx
0x140106762  lea     rdx, VmsOmNicTypeStr
0x140106769  call    VmsCsAttrValueWriteULong
0x14010676e  mov     [rsp+5F0h+var_5A0], eax
0x140106772  jmp     short loc_140106777
0x140106774  xor     sil, sil
0x140106777  test    eax, eax
0x140106779  jz      short loc_1401067EA
0x14010677b  test    rdi, rdi
0x14010677e  jz      short loc_140106789
0x140106780  mov     rcx, [rdi+2388h]
0x140106787  jmp     short loc_140106790
0x140106789  mov     rcx, cs:VmsIfrLog
0x140106790  mov     eax, [rsp+5F0h+var_5A0]
0x140106794  mov     r9d, 42h ; 'B'
0x14010679a  mov     [rsp+5F0h+var_5B0], eax
0x14010679e  lea     rax, WPP_b611aa96bbb53e16652f3c6e68c2f217_Traceguids
0x1401067a5  mov     [rsp+5F0h+var_5B8], r15
0x1401067aa  mov     [rsp+5F0h+var_5C0], r12
0x1401067af  mov     [rsp+5F0h+var_5C8], r14
0x1401067b4  mov     [rsp+5F0h+Timeout], rax
0x1401067b9  call    WPP_RECORDER_SF_ZZZd
0x1401067be  lea     rax, [rbp+4F0h+var_558]
0x1401067c2  mov     [rsp+5F0h+var_5C0], rax; __int64
0x1401067c7  lea     r9, [rsp+5F0h+var_5A0]
0x1401067cc  lea     rax, [rsp+5F0h+DestinationString]
0x1401067d1  mov     [rsp+5F0h+var_5C8], rax; __int64
0x1401067d6  lea     rcx, VM_FAILED_TO_STORE_CONFIG_FOR_NIC; EventDescriptor
0x1401067dd  mov     dword ptr [rsp+5F0h+Timeout], 0; char
0x1401067e5  call    VmsEtwTraceSwitchFailure
0x1401067ea  test    rbx, rbx
0x1401067ed  jz      short loc_1401067F7
0x1401067ef  mov     rcx, rbx
0x1401067f2  call    VmsCsKeyClose
0x1401067f7  test    sil, sil
0x1401067fa  jz      short loc_14010681B
0x1401067fc  lea     rcx, [rdi+478h]; Mutex
0x140106803  xor     edx, edx; Wait
0x140106805  call    cs:__imp_KeReleaseMutex
0x14010680c  nop     dword ptr [rax+rax+00h]
0x140106811  xor     edx, edx
0x140106813  mov     rcx, rdi
0x140106816  call    VmsOmpObjectDereference
0x14010681b  mov     eax, [rsp+5F0h+var_5A0]
0x14010681f  mov     rcx, [rbp+4F0h+var_40]
0x140106826  xor     rcx, rsp; StackCookie
0x140106829  call    __security_check_cookie
0x14010682e  add     rsp, 5C0h
0x140106835  pop     r15
0x140106837  pop     r14
0x140106839  pop     r12
0x14010683b  pop     rdi
0x14010683c  pop     rsi
0x14010683d  pop     rbx
0x14010683e  pop     rbp
0x14010683f  retn
```
