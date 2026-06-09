# Utils::CreateSidString(ushort const * *)

- ea: `0x140004bc0`
- end: `0x140004e8d`
- name: `?CreateSidString@Utils@@SAJPEAPEBG@Z`
- size: `717`
- prototype: `__int64 __fastcall(const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400038e0`

## callees

- `0x140004bc0`
- `0x1400454a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140004c91`
- `ntoskrnl!ExAllocatePool2` at `0x140004d88`
- `ntoskrnl!ExAllocatePool2` at `0x140004c91`
- `ntoskrnl!ExAllocatePool2` at `0x140004d88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e18`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004c18`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004c18`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004d01`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140004d01`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004c63`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004c63`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004ce4`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004ce4`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140004d42`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140004d42`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004e29`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140004e29`
- `ntoskrnl!ZwClose` at `0x140004d1a`
- `ntoskrnl!ZwClose` at `0x140004d1a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004be6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140004be6`

## pseudocode

```c
__int64 __fastcall Utils::CreateSidString(unsigned __int16 **a1)
{
  unsigned __int16 *v2; // rsi
  void *v3; // rdi
  PSID *v4; // r14
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v6; // ebx
  _QWORD *Pool2; // rax
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // r9
  PWSTR Buffer; // rdx
  __int64 Length; // rcx
  __int64 v13; // r8
  unsigned __int16 *v14; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-48h] BYREF
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+0h]
  ULONG ReturnLength; // [rsp+A8h] [rbp+10h] BYREF
  HANDLE TokenHandle; // [rsp+B0h] [rbp+18h] BYREF

  v2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  ReturnLength = 0;
  TokenHandle = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v3 = 0;
  v4 = 0;
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  if ( PrimaryToken )
  {
    v6 = ObOpenObjectByPointer(PrimaryToken, 0x200u, 0, 8u, 0, 0, &TokenHandle);
    if ( v6 >= 0 )
    {
      Pool2 = (_QWORD *)ExAllocatePool2(257, 100, 1349349460);
      v3 = Pool2;
      if ( Pool2 )
      {
        *Pool2 = retaddr;
        Pool2[1] = retaddr;
        v3 = Pool2 + 2;
      }
      if ( v3 )
      {
        v6 = ZwQueryInformationToken(TokenHandle, TokenUser, v3, 0x54u, &ReturnLength);
        if ( v6 >= 0 )
        {
          v4 = (PSID *)v3;
          v3 = 0;
        }
      }
      else
      {
        v6 = -1073741670;
      }
    }
  }
  else
  {
    v6 = -1073741790;
  }
  SeReleaseSubjectContext(&SubjectContext);
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( v3 )
    TpmFree(v3);
  if ( v6 >= 0 )
  {
    v6 = RtlConvertSidToUnicodeString(&DestinationString, *v4, 1u);
    if ( v6 >= 0 )
    {
      v8 = 2LL * ((unsigned int)DestinationString.Length + 1);
      if ( !v8 || v8 + 16 < v8 )
        goto LABEL_34;
      v9 = (unsigned __int16 *)ExAllocatePool2(257, v8 + 16, 1349349460);
      v2 = v9;
      if ( v9 )
      {
        *(_QWORD *)v9 = retaddr;
        *((_QWORD *)v9 + 1) = retaddr;
        v2 = v9 + 8;
      }
      if ( v2 )
      {
        v10 = v2;
        Buffer = DestinationString.Buffer;
        Length = DestinationString.Length;
        v13 = (unsigned int)DestinationString.Length + 1;
        do
        {
          if ( !Length )
            break;
          if ( !*Buffer )
            break;
          *v10++ = *Buffer++;
          --Length;
          --v13;
        }
        while ( v13 );
        v14 = v10 - 1;
        v6 = -2147483643;
        if ( v13 )
        {
          v14 = v10;
          v6 = 0;
        }
        *v14 = 0;
        if ( v13 )
        {
          *a1 = v2;
          v6 = 0;
          v2 = 0;
        }
      }
      else
      {
LABEL_34:
        v6 = -1073741670;
      }
    }
  }
  if ( v4 )
    ExFreePoolWithTag(v4 - 2, 0x506D7054u);
  RtlFreeUnicodeString(&DestinationString);
  if ( v2 )
    TpmFree(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140004bc0  mov     [rsp+arg_0], rbx
0x140004bc5  push    rbp
0x140004bc6  push    rsi
0x140004bc7  push    rdi
0x140004bc8  push    r14
0x140004bca  push    r15
0x140004bcc  sub     rsp, 70h
0x140004bd0  mov     r15, rcx
0x140004bd3  xorps   xmm0, xmm0
0x140004bd6  xor     ebp, ebp
0x140004bd8  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x140004bdd  xor     edx, edx; SourceString
0x140004bdf  mov     esi, ebp
0x140004be1  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x140004be6  call    cs:__imp_RtlInitUnicodeString
0x140004bed  nop     dword ptr [rax+rax+00h]
0x140004bf2  xorps   xmm0, xmm0
0x140004bf5  mov     [rsp+98h+ReturnLength], ebp
0x140004bfc  lea     rcx, [rsp+98h+SubjectContext]; SubjectContext
0x140004c01  mov     [rsp+98h+TokenHandle], rbp
0x140004c09  movups  xmmword ptr [rsp+98h+SubjectContext.ClientToken], xmm0
0x140004c0e  mov     edi, ebp
0x140004c10  mov     r14d, ebp
0x140004c13  movups  xmmword ptr [rsp+98h+SubjectContext.PrimaryToken], xmm0
0x140004c18  call    cs:__imp_SeCaptureSubjectContext
0x140004c1f  nop     dword ptr [rax+rax+00h]
0x140004c24  mov     rax, [rsp+98h+SubjectContext.ClientToken]
0x140004c29  mov     rcx, [rsp+98h+SubjectContext.PrimaryToken]
0x140004c2e  test    rax, rax
0x140004c31  cmovnz  rcx, rax; Object
0x140004c35  test    rcx, rcx
0x140004c38  jz      loc_140004E62
0x140004c3e  lea     rax, [rsp+98h+TokenHandle]
0x140004c46  mov     r9d, 8; DesiredAccess
0x140004c4c  mov     [rsp+98h+Handle], rax; Handle
0x140004c51  xor     r8d, r8d; PassedAccessState
0x140004c54  mov     [rsp+98h+AccessMode], sil; AccessMode
0x140004c59  mov     edx, 200h; HandleAttributes
0x140004c5e  mov     [rsp+98h+ObjectType], rbp; ObjectType
0x140004c63  call    cs:__imp_ObOpenObjectByPointer
0x140004c6a  nop     dword ptr [rax+rax+00h]
0x140004c6f  mov     ebx, eax
0x140004c71  test    eax, eax
0x140004c73  js      loc_140004CFC
0x140004c79  mov     rbx, [rsp+98h]
0x140004c81  mov     edx, 64h ; 'd'
0x140004c86  mov     ecx, 101h
0x140004c8b  mov     r8d, 506D7054h
0x140004c91  call    cs:__imp_ExAllocatePool2
0x140004c98  nop     dword ptr [rax+rax+00h]
0x140004c9d  mov     rdi, rax
0x140004ca0  test    rax, rax
0x140004ca3  jz      short loc_140004CB8
0x140004ca5  mov     [rax], rbx
0x140004ca8  mov     rax, [rsp+98h]
0x140004cb0  mov     [rdi+8], rax
0x140004cb4  add     rdi, 10h
0x140004cb8  test    rdi, rdi
0x140004cbb  jz      loc_140004E6C
0x140004cc1  mov     rcx, [rsp+98h+TokenHandle]; TokenHandle
0x140004cc9  lea     rax, [rsp+98h+ReturnLength]
0x140004cd1  mov     r9d, 54h ; 'T'; TokenInformationLength
0x140004cd7  mov     [rsp+98h+ObjectType], rax; ReturnLength
0x140004cdc  mov     r8, rdi; TokenInformation
0x140004cdf  mov     edx, 1; TokenInformationClass
0x140004ce4  call    cs:__imp_ZwQueryInformationToken
0x140004ceb  nop     dword ptr [rax+rax+00h]
0x140004cf0  mov     ebx, eax
0x140004cf2  test    eax, eax
0x140004cf4  js      short loc_140004CFC
0x140004cf6  mov     r14, rdi
0x140004cf9  mov     rdi, rbp
0x140004cfc  lea     rcx, [rsp+98h+SubjectContext]; SubjectContext
0x140004d01  call    cs:__imp_SeReleaseSubjectContext
0x140004d08  nop     dword ptr [rax+rax+00h]
0x140004d0d  mov     rcx, [rsp+98h+TokenHandle]; Handle
0x140004d15  test    rcx, rcx
0x140004d18  jz      short loc_140004D26
0x140004d1a  call    cs:__imp_ZwClose
0x140004d21  nop     dword ptr [rax+rax+00h]
0x140004d26  test    rdi, rdi
0x140004d29  jnz     loc_140004E76
0x140004d2f  test    ebx, ebx
0x140004d31  js      loc_140004E0A
0x140004d37  mov     rdx, [r14]; Sid
0x140004d3a  lea     rcx, [rsp+98h+DestinationString]; UnicodeString
0x140004d3f  mov     r8b, 1; AllocateDestinationString
0x140004d42  call    cs:__imp_RtlConvertSidToUnicodeString
0x140004d49  nop     dword ptr [rax+rax+00h]
0x140004d4e  mov     ebx, eax
0x140004d50  test    eax, eax
0x140004d52  js      loc_140004E0A
0x140004d58  movzx   eax, [rsp+98h+DestinationString.Length]
0x140004d5d  mov     rbx, [rsp+98h]
0x140004d65  inc     eax
0x140004d67  add     rax, rax
0x140004d6a  jz      loc_140004E51
0x140004d70  lea     rdx, [rax+10h]
0x140004d74  cmp     rdx, rax
0x140004d77  jb      loc_140004E51
0x140004d7d  mov     ecx, 101h
0x140004d82  mov     r8d, 506D7054h
0x140004d88  call    cs:__imp_ExAllocatePool2
0x140004d8f  nop     dword ptr [rax+rax+00h]
0x140004d94  mov     rsi, rax
0x140004d97  test    rax, rax
0x140004d9a  jz      short loc_140004DAF
0x140004d9c  mov     [rax], rbx
0x140004d9f  mov     rax, [rsp+98h]
0x140004da7  mov     [rsi+8], rax
0x140004dab  add     rsi, 10h
0x140004daf  test    rsi, rsi
0x140004db2  jz      loc_140004E51
0x140004db8  movzx   eax, [rsp+98h+DestinationString.Length]
0x140004dbd  mov     r9, rsi
0x140004dc0  mov     rdx, [rsp+98h+DestinationString.Buffer]
0x140004dc5  mov     ecx, eax
0x140004dc7  lea     r8d, [rax+1]
0x140004dcb  nop     dword ptr [rax+rax+00h]
0x140004dd0  test    rcx, rcx
0x140004dd3  jz      short loc_140004DF2
0x140004dd5  movzx   eax, word ptr [rdx]
0x140004dd8  test    ax, ax
0x140004ddb  jz      short loc_140004DF2
0x140004ddd  mov     [r9], ax
0x140004de1  add     rdx, 2
0x140004de5  add     r9, 2
0x140004de9  dec     rcx
0x140004dec  sub     r8, 1
0x140004df0  jnz     short loc_140004DD0
0x140004df2  test    r8, r8
0x140004df5  lea     rcx, [r9-2]
0x140004df9  mov     ebx, 80000005h
0x140004dfe  cmovnz  rcx, r9
0x140004e02  cmovnz  ebx, ebp
0x140004e05  mov     [rcx], bp
0x140004e08  jnz     short loc_140004E58
0x140004e0a  test    r14, r14
0x140004e0d  jz      short loc_140004E24
0x140004e0f  lea     rcx, [r14-10h]; P
0x140004e13  mov     edx, 506D7054h; Tag
0x140004e18  call    cs:__imp_ExFreePoolWithTag
0x140004e1f  nop     dword ptr [rax+rax+00h]
0x140004e24  lea     rcx, [rsp+98h+DestinationString]; UnicodeString
0x140004e29  call    cs:__imp_RtlFreeUnicodeString
0x140004e30  nop     dword ptr [rax+rax+00h]
0x140004e35  test    rsi, rsi
0x140004e38  jnz     short loc_140004E83
0x140004e3a  mov     eax, ebx
0x140004e3c  mov     rbx, [rsp+98h+arg_0]
0x140004e44  add     rsp, 70h
0x140004e48  pop     r15
0x140004e4a  pop     r14
0x140004e4c  pop     rdi
0x140004e4d  pop     rsi
0x140004e4e  pop     rbp
0x140004e4f  retn
0x140004e51  mov     ebx, 0C000009Ah
0x140004e56  jmp     short loc_140004E0A
0x140004e58  mov     [r15], rsi
0x140004e5b  mov     ebx, ebp
0x140004e5d  mov     rsi, rbp
0x140004e60  jmp     short loc_140004E0A
0x140004e62  mov     ebx, 0C0000022h
0x140004e67  jmp     loc_140004CFC
0x140004e6c  mov     ebx, 0C000009Ah
0x140004e71  jmp     loc_140004CFC
0x140004e76  mov     rcx, rdi; void *
0x140004e79  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140004e7e  jmp     loc_140004D2F
0x140004e83  mov     rcx, rsi; void *
0x140004e86  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x140004e8b  jmp     short loc_140004E3A
```
