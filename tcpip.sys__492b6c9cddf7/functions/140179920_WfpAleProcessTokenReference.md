# WfpAleProcessTokenReference

- ea: `0x140179920`
- end: `0x140179b7a`
- name: `WfpAleProcessTokenReference`
- size: `602`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14011b1b8`

## callees

- `0x140053f20`
- `0x1400ba2b8`
- `0x1400ba388`
- `0x1400bb000`
- `0x1400be890`
- `0x140179920`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x140179b0a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140179b0a`
- `ntoskrnl!ZwDuplicateToken` at `0x140179a67`
- `ntoskrnl!ZwDuplicateToken` at `0x140179a67`
- `ntoskrnl!KeStackAttachProcess` at `0x140179a38`
- `ntoskrnl!KeStackAttachProcess` at `0x140179a38`
- `ntoskrnl!ZwOpenProcess` at `0x1401799c5`
- `ntoskrnl!ZwOpenProcess` at `0x1401799c5`
- `ntoskrnl!ZwClose` at `0x140179af5`
- `ntoskrnl!ZwClose` at `0x140179b33`
- `ntoskrnl!ZwClose` at `0x140179af5`
- `ntoskrnl!ZwClose` at `0x140179b33`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140179a14`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140179a14`
- `ntoskrnl!ObfDereferenceObject` at `0x140179b1e`
- `ntoskrnl!ObfDereferenceObject` at `0x140179b1e`

## string_xrefs

- `0x140179a77`: `ZwDuplicateToken`
- `0x1401799d7`: `ZwOpenProcess`
- `0x140179b44`: `WfpAleProcessTokenReference`

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
    inserted = WfpAleAcquireTokenInformationFromToken(
                 0,
                 (_DWORD)NewTokenHandle,
                 (unsigned int)v17,
                 (unsigned int)&v16,
                 (__int64)v12);
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
0x140179920  mov     [rsp-8+arg_10], rbx
0x140179925  push    rbp
0x140179926  push    rsi
0x140179927  push    rdi
0x140179928  push    r14
0x14017992a  push    r15
0x14017992c  lea     rbp, [rsp-37h]
0x140179931  sub     rsp, 0E0h
0x140179938  mov     rax, cs:__security_cookie
0x14017993f  xor     rax, rsp
0x140179942  mov     [rbp+57h+var_28], rax
0x140179946  mov     rbx, [rcx+8]
0x14017994a  lea     r9, [rbp+57h+ClientId]; ClientId
0x14017994e  xor     eax, eax
0x140179950  mov     [rbp+57h+ProcessHandle], 0
0x140179958  xorps   xmm0, xmm0
0x14017995b  mov     [rbp+57h+NewTokenHandle], rax
0x14017995f  mov     [rbp+57h+var_B0], rax
0x140179963  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140179967  mov     eax, [rcx]
0x140179969  mov     r15, rdx
0x14017996c  mov     [rbp+57h+ClientId.UniqueProcess], rax
0x140179970  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140179974  mov     rax, cs:ALE_LUID_NULL
0x14017997b  mov     edi, 400h
0x140179980  mov     [rdx], rax
0x140179983  xor     r14b, r14b
0x140179986  mov     edx, edi; DesiredAccess
0x140179988  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140179990  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x140179998  mov     [rbp+57h+var_D0], 1
0x14017999c  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm0
0x1401799a0  mov     [rbp+57h+ClientId.UniqueThread], 0
0x1401799a8  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm0
0x1401799ac  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1401799b4  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm0
0x1401799b8  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x1401799c0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401799c5  call    cs:__imp_ZwOpenProcess
0x1401799cc  nop     dword ptr [rax+rax+00h]
0x1401799d1  test    eax, eax
0x1401799d3  jz      short loc_1401799EE
0x1401799d5  xor     edi, edi
0x1401799d7  lea     rdx, aZwopenprocess; "ZwOpenProcess"
0x1401799de  mov     r8d, eax
0x1401799e1  call    WfpReportSysErrorAsNtStatus
0x1401799e6  mov     rbx, rax
0x1401799e9  jmp     loc_140179AE6
0x1401799ee  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x1401799f2  lea     rax, [rbp+57h+var_B8]
0x1401799f6  mov     [rsp+100h+HandleInformation], 0; HandleInformation
0x1401799ff  xor     r9d, r9d; AccessMode
0x140179a02  xor     r8d, r8d; ObjectType
0x140179a05  mov     [rsp+100h+Object], rax; Object
0x140179a0a  mov     edx, edi; DesiredAccess
0x140179a0c  mov     [rbp+57h+var_B8], 0
0x140179a14  call    cs:__imp_ObReferenceObjectByHandle
0x140179a1b  nop     dword ptr [rax+rax+00h]
0x140179a20  mov     rdi, [rbp+57h+var_B8]
0x140179a24  test    eax, eax
0x140179a26  jz      short loc_140179A31
0x140179a28  lea     rdx, aObreferenceobj; "_ObReferenceObjectByHandle"
0x140179a2f  jmp     short loc_1401799DE
0x140179a31  lea     rdx, [rbp+57h+ApcState]; ApcState
0x140179a35  mov     rcx, rdi; PROCESS
0x140179a38  call    cs:__imp_KeStackAttachProcess
0x140179a3f  nop     dword ptr [rax+rax+00h]
0x140179a44  lea     rax, [rbp+57h+NewTokenHandle]
0x140179a48  xor     r9d, r9d; EffectiveOnly
0x140179a4b  mov     [rsp+100h+HandleInformation], rax; NewTokenHandle
0x140179a50  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140179a54  mov     edx, 0F01FFh; DesiredAccess
0x140179a59  mov     dword ptr [rsp+100h+Object], 1; TokenType
0x140179a61  mov     rcx, rbx; ExistingTokenHandle
0x140179a64  mov     r14b, 1
0x140179a67  call    cs:__imp_ZwDuplicateToken
0x140179a6e  nop     dword ptr [rax+rax+00h]
0x140179a73  test    eax, eax
0x140179a75  jz      short loc_140179A83
0x140179a77  lea     rdx, aZwduplicatetok; "ZwDuplicateToken"
0x140179a7e  jmp     loc_1401799DE
0x140179a83  mov     rax, cs:ALE_LUID_NULL
0x140179a8a  lea     rdx, [rbp+57h+var_A8]
0x140179a8e  mov     rcx, [rbp+57h+NewTokenHandle]; TokenHandle
0x140179a92  mov     [rbp+57h+var_A8], rax
0x140179a96  mov     [rbp+57h+var_A0], rax
0x140179a9a  call    WfpAleCaptureTokenIdByHandle
0x140179a9f  mov     rbx, rax
0x140179aa2  test    rax, rax
0x140179aa5  jnz     short loc_140179AE6
0x140179aa7  mov     rdx, [rbp+57h+NewTokenHandle]
0x140179aab  lea     rax, [rbp+57h+var_D0]
0x140179aaf  lea     r9, [rbp+57h+var_B0]
0x140179ab3  mov     [rsp+100h+Object], rax
0x140179ab8  lea     r8, [rbp+57h+var_A8]
0x140179abc  xor     ecx, ecx
0x140179abe  call    WfpAleAcquireTokenInformationFromToken
0x140179ac3  mov     rbx, rax
0x140179ac6  test    rax, rax
0x140179ac9  jnz     short loc_140179AE6
0x140179acb  mov     rsi, [rbp+57h+var_B0]
0x140179acf  mov     rcx, rsi
0x140179ad2  call    WfpAleInsertTokenInformationByUserTokenIdIfNeeded
0x140179ad7  mov     rbx, rax
0x140179ada  test    rax, rax
0x140179add  jnz     short loc_140179AE6
0x140179adf  mov     rax, [rsi+14h]
0x140179ae3  mov     [r15], rax
0x140179ae6  mov     rcx, [rbp+57h+NewTokenHandle]; Handle
0x140179aea  test    rcx, rcx
0x140179aed  jz      short loc_140179B01
0x140179aef  cmp     [rbp+57h+var_D0], 0
0x140179af3  jz      short loc_140179B01
0x140179af5  call    cs:__imp_ZwClose
0x140179afc  nop     dword ptr [rax+rax+00h]
0x140179b01  test    r14b, r14b
0x140179b04  jz      short loc_140179B16
0x140179b06  lea     rcx, [rbp+57h+ApcState]; ApcState
0x140179b0a  call    cs:__imp_KeUnstackDetachProcess
0x140179b11  nop     dword ptr [rax+rax+00h]
0x140179b16  test    rdi, rdi
0x140179b19  jz      short loc_140179B2A
0x140179b1b  mov     rcx, rdi; Object
0x140179b1e  call    cs:__imp_ObfDereferenceObject
0x140179b25  nop     dword ptr [rax+rax+00h]
0x140179b2a  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140179b2e  test    rcx, rcx
0x140179b31  jz      short loc_140179B3F
0x140179b33  call    cs:__imp_ZwClose
0x140179b3a  nop     dword ptr [rax+rax+00h]
0x140179b3f  test    rbx, rbx
0x140179b42  jz      short loc_140179B53
0x140179b44  lea     rdx, aWfpaleprocesst; "WfpAleProcessTokenReference"
0x140179b4b  mov     rcx, rbx
0x140179b4e  call    WfpReportError
0x140179b53  mov     rax, rbx
0x140179b56  mov     rcx, [rbp+57h+var_28]
0x140179b5a  xor     rcx, rsp; StackCookie
0x140179b5d  call    __security_check_cookie
0x140179b62  mov     rbx, [rsp+100h+arg_10]
0x140179b6a  add     rsp, 0E0h
0x140179b71  pop     r15
0x140179b73  pop     r14
0x140179b75  pop     rdi
0x140179b76  pop     rsi
0x140179b77  pop     rbp
0x140179b78  retn
```
