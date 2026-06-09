# WfpAleProcessTokenReference

- ea: `0x14017b620`
- end: `0x14017b87a`
- name: `WfpAleProcessTokenReference`
- size: `602`
- prototype: `__int64 __fastcall(unsigned int *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140124de8`

## callees

- `0x140014a90`
- `0x1400c3a08`
- `0x1400c3ad8`
- `0x1400c4750`
- `0x1400c7fe0`
- `0x14017b620`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x14017b80a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14017b80a`
- `ntoskrnl!ZwDuplicateToken` at `0x14017b767`
- `ntoskrnl!ZwDuplicateToken` at `0x14017b767`
- `ntoskrnl!KeStackAttachProcess` at `0x14017b738`
- `ntoskrnl!KeStackAttachProcess` at `0x14017b738`
- `ntoskrnl!ZwOpenProcess` at `0x14017b6c5`
- `ntoskrnl!ZwOpenProcess` at `0x14017b6c5`
- `ntoskrnl!ZwClose` at `0x14017b7f5`
- `ntoskrnl!ZwClose` at `0x14017b833`
- `ntoskrnl!ZwClose` at `0x14017b7f5`
- `ntoskrnl!ZwClose` at `0x14017b833`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14017b714`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14017b714`
- `ntoskrnl!ObfDereferenceObject` at `0x14017b81e`
- `ntoskrnl!ObfDereferenceObject` at `0x14017b81e`

## string_xrefs

- `0x14017b777`: `ZwDuplicateToken`
- `0x14017b6d7`: `ZwOpenProcess`
- `0x14017b844`: `WfpAleProcessTokenReference`

## pseudocode

```c
__int64 __fastcall WfpAleProcessTokenReference(unsigned int *a1, _QWORD *a2)
{
  void *v2; // rbx
  char v4; // r14
  unsigned int v5; // eax
  __int64 v6; // rcx
  PVOID v7; // rdi
  const char *v8; // rdx
  __int64 inserted; // rbx
  __int64 v10; // rsi
  char v12[8]; // [rsp+30h] [rbp-79h] BYREF
  void *NewTokenHandle; // [rsp+38h] [rbp-71h] BYREF
  void *ProcessHandle; // [rsp+40h] [rbp-69h] BYREF
  PVOID Object; // [rsp+48h] [rbp-61h] BYREF
  __int64 v16; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v17[2]; // [rsp+58h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-41h] BYREF
  _CLIENT_ID ClientId; // [rsp+98h] [rbp-11h] BYREF
  _KAPC_STATE ApcState; // [rsp+A8h] [rbp-1h] BYREF

  v2 = (void *)*((_QWORD *)a1 + 1);
  ProcessHandle = 0;
  NewTokenHandle = 0;
  v16 = 0;
  ClientId.UniqueProcess = (HANDLE)*a1;
  *a2 = ALE_LUID_NULL;
  v4 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  v12[0] = 1;
  memset(&ApcState, 0, sizeof(ApcState));
  ClientId.UniqueThread = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
  if ( v5 )
  {
    v7 = 0;
    v8 = "ZwOpenProcess";
LABEL_3:
    inserted = WfpReportSysErrorAsNtStatus(v6, v8, v5);
    goto LABEL_12;
  }
  Object = 0;
  v5 = ObReferenceObjectByHandle(ProcessHandle, 0x400u, 0, 0, &Object, 0);
  v7 = Object;
  if ( v5 )
  {
    v8 = "_ObReferenceObjectByHandle";
    goto LABEL_3;
  }
  KeStackAttachProcess((PRKPROCESS)Object, &ApcState);
  v4 = 1;
  v5 = ZwDuplicateToken(v2, 0xF01FFu, &ObjectAttributes, 0, TokenPrimary, &NewTokenHandle);
  if ( v5 )
  {
    v8 = "ZwDuplicateToken";
    goto LABEL_3;
  }
  v17[0] = ALE_LUID_NULL;
  v17[1] = ALE_LUID_NULL;
  inserted = WfpAleCaptureTokenIdByHandle(NewTokenHandle);
  if ( !inserted )
  {
    inserted = WfpAleAcquireTokenInformationFromToken(0, (__int64)NewTokenHandle, v17, &v16, v12);
    if ( !inserted )
    {
      v10 = v16;
      inserted = WfpAleInsertTokenInformationByUserTokenIdIfNeeded(v16);
      if ( !inserted )
        *a2 = *(_QWORD *)(v10 + 20);
    }
  }
LABEL_12:
  if ( NewTokenHandle && v12[0] )
    ZwClose(NewTokenHandle);
  if ( v4 )
    KeUnstackDetachProcess(&ApcState);
  if ( v7 )
    ObfDereferenceObject(v7);
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( inserted )
    WfpReportError(inserted, "WfpAleProcessTokenReference");
  return inserted;
}

```

## disassembly

```asm
0x14017b620  mov     [rsp-8+arg_10], rbx
0x14017b625  push    rbp
0x14017b626  push    rsi
0x14017b627  push    rdi
0x14017b628  push    r14
0x14017b62a  push    r15
0x14017b62c  lea     rbp, [rsp-37h]
0x14017b631  sub     rsp, 0E0h
0x14017b638  mov     rax, cs:__security_cookie
0x14017b63f  xor     rax, rsp
0x14017b642  mov     [rbp+57h+var_28], rax
0x14017b646  mov     rbx, [rcx+8]
0x14017b64a  lea     r9, [rbp+57h+ClientId]; ClientId
0x14017b64e  xor     eax, eax
0x14017b650  mov     [rbp+57h+ProcessHandle], 0
0x14017b658  xorps   xmm0, xmm0
0x14017b65b  mov     [rbp+57h+NewTokenHandle], rax
0x14017b65f  mov     [rbp+57h+var_B0], rax
0x14017b663  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14017b667  mov     eax, [rcx]
0x14017b669  mov     r15, rdx
0x14017b66c  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x14017b670  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x14017b674  mov     rax, cs:ALE_LUID_NULL
0x14017b67b  mov     edi, 400h
0x14017b680  mov     [rdx], rax
0x14017b683  xor     r14b, r14b
0x14017b686  mov     edx, edi; DesiredAccess
0x14017b688  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14017b690  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x14017b698  mov     [rbp+57h+var_D0], 1
0x14017b69c  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x14017b6a0  mov     [rbp+57h+ClientId.UniqueThread], 0
0x14017b6a8  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x14017b6ac  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14017b6b4  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x14017b6b8  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x14017b6c0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14017b6c5  call    cs:__imp_ZwOpenProcess
0x14017b6cc  nop     dword ptr [rax+rax+00h]
0x14017b6d1  test    eax, eax
0x14017b6d3  jz      short loc_14017B6EE
0x14017b6d5  xor     edi, edi
0x14017b6d7  lea     rdx, aZwopenprocess; "ZwOpenProcess"
0x14017b6de  mov     r8d, eax
0x14017b6e1  call    WfpReportSysErrorAsNtStatus
0x14017b6e6  mov     rbx, rax
0x14017b6e9  jmp     loc_14017B7E6
0x14017b6ee  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14017b6f2  lea     rax, [rbp+57h+var_B8]
0x14017b6f6  mov     [rsp+100h+HandleInformation], 0; HandleInformation
0x14017b6ff  xor     r9d, r9d; AccessMode
0x14017b702  xor     r8d, r8d; ObjectType
0x14017b705  mov     [rsp+100h+Object], rax; Object
0x14017b70a  mov     edx, edi; DesiredAccess
0x14017b70c  mov     [rbp+57h+var_B8], 0
0x14017b714  call    cs:__imp_ObReferenceObjectByHandle
0x14017b71b  nop     dword ptr [rax+rax+00h]
0x14017b720  mov     rdi, [rbp+57h+var_B8]
0x14017b724  test    eax, eax
0x14017b726  jz      short loc_14017B731
0x14017b728  lea     rdx, aObreferenceobj; "_ObReferenceObjectByHandle"
0x14017b72f  jmp     short loc_14017B6DE
0x14017b731  lea     rdx, [rbp+57h+ApcState]; ApcState
0x14017b735  mov     rcx, rdi; PROCESS
0x14017b738  call    cs:__imp_KeStackAttachProcess
0x14017b73f  nop     dword ptr [rax+rax+00h]
0x14017b744  lea     rax, [rbp+57h+NewTokenHandle]
0x14017b748  xor     r9d, r9d; EffectiveOnly
0x14017b74b  mov     [rsp+100h+HandleInformation], rax; NewTokenHandle
0x14017b750  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14017b754  mov     edx, 0F01FFh; DesiredAccess
0x14017b759  mov     dword ptr [rsp+100h+Object], 1; TokenType
0x14017b761  mov     rcx, rbx; ExistingTokenHandle
0x14017b764  mov     r14b, 1
0x14017b767  call    cs:__imp_ZwDuplicateToken
0x14017b76e  nop     dword ptr [rax+rax+00h]
0x14017b773  test    eax, eax
0x14017b775  jz      short loc_14017B783
0x14017b777  lea     rdx, aZwduplicatetok; "ZwDuplicateToken"
0x14017b77e  jmp     loc_14017B6DE
0x14017b783  mov     rax, cs:ALE_LUID_NULL
0x14017b78a  lea     rdx, [rbp+57h+var_A8]
0x14017b78e  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x14017b792  mov     [rbp+57h+var_A8], rax
0x14017b796  mov     [rbp+57h+var_A0], rax
0x14017b79a  call    WfpAleCaptureTokenIdByHandle
0x14017b79f  mov     rbx, rax
0x14017b7a2  test    rax, rax
0x14017b7a5  jnz     short loc_14017B7E6
0x14017b7a7  mov     rdx, [rbp+57h+NewTokenHandle]
0x14017b7ab  lea     rax, [rbp+57h+var_D0]
0x14017b7af  lea     r9, [rbp+57h+var_B0]
0x14017b7b3  mov     [rsp+100h+Object], rax
0x14017b7b8  lea     r8, [rbp+57h+var_A8]
0x14017b7bc  xor     ecx, ecx
0x14017b7be  call    WfpAleAcquireTokenInformationFromToken
0x14017b7c3  mov     rbx, rax
0x14017b7c6  test    rax, rax
0x14017b7c9  jnz     short loc_14017B7E6
0x14017b7cb  mov     rsi, [rbp+57h+var_B0]
0x14017b7cf  mov     rcx, rsi
0x14017b7d2  call    WfpAleInsertTokenInformationByUserTokenIdIfNeeded
0x14017b7d7  mov     rbx, rax
0x14017b7da  test    rax, rax
0x14017b7dd  jnz     short loc_14017B7E6
0x14017b7df  mov     rax, [rsi+14h]
0x14017b7e3  mov     [r15], rax
0x14017b7e6  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x14017b7ea  test    rcx, rcx
0x14017b7ed  jz      short loc_14017B801
0x14017b7ef  cmp     [rbp+57h+var_D0], 0
0x14017b7f3  jz      short loc_14017B801
0x14017b7f5  call    cs:__imp_ZwClose
0x14017b7fc  nop     dword ptr [rax+rax+00h]
0x14017b801  test    r14b, r14b
0x14017b804  jz      short loc_14017B816
0x14017b806  lea     rcx, [rbp+57h+ApcState]; ApcState
0x14017b80a  call    cs:__imp_KeUnstackDetachProcess
0x14017b811  nop     dword ptr [rax+rax+00h]
0x14017b816  test    rdi, rdi
0x14017b819  jz      short loc_14017B82A
0x14017b81b  mov     rcx, rdi; Object
0x14017b81e  call    cs:__imp_ObfDereferenceObject
0x14017b825  nop     dword ptr [rax+rax+00h]
0x14017b82a  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x14017b82e  test    rcx, rcx
0x14017b831  jz      short loc_14017B83F
0x14017b833  call    cs:__imp_ZwClose
0x14017b83a  nop     dword ptr [rax+rax+00h]
0x14017b83f  test    rbx, rbx
0x14017b842  jz      short loc_14017B853
0x14017b844  lea     rdx, aWfpaleprocesst; "WfpAleProcessTokenReference"
0x14017b84b  mov     rcx, rbx
0x14017b84e  call    WfpReportError
0x14017b853  mov     rax, rbx
0x14017b856  mov     rcx, [rbp+57h+var_28]
0x14017b85a  xor     rcx, rsp; StackCookie
0x14017b85d  call    __security_check_cookie
0x14017b862  mov     rbx, [rsp+100h+arg_10]
0x14017b86a  add     rsp, 0E0h
0x14017b871  pop     r15
0x14017b873  pop     r14
0x14017b875  pop     rdi
0x14017b876  pop     rsi
0x14017b877  pop     rbp
0x14017b878  retn
```
