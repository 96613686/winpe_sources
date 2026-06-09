# SrvLibAuditShareAddOrDelete

- ea: `0x1400088f0`
- end: `0x140008ba9`
- name: `SrvLibAuditShareAddOrDelete`
- size: `697`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005570`
- `0x140025990`

## callees

- `0x140007360`
- `0x140007c60`
- `0x1400088f0`
- `0x14002a3e0`
- `0x14002a540`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140008a47`
- `ntoskrnl!RtlInitUnicodeString` at `0x140008a47`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140008a76`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140008a76`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140008b7b`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140008b7b`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140008a98`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140008a98`
- `ntoskrnl!SeSetAuditParameter` at `0x140008ac0`
- `ntoskrnl!SeSetAuditParameter` at `0x140008aed`
- `ntoskrnl!SeSetAuditParameter` at `0x140008b13`
- `ntoskrnl!SeSetAuditParameter` at `0x140008ac0`
- `ntoskrnl!SeSetAuditParameter` at `0x140008aed`
- `ntoskrnl!SeSetAuditParameter` at `0x140008b13`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140008b3e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140008b3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b6a`

## string_xrefs

- `0x140008a36`: `Security`

## pseudocode

```c
__int64 __fastcall SrvLibAuditShareAddOrDelete(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4)
{
  __int16 v8; // cx
  _QWORD *v9; // rsi
  _DWORD *PoolWithTag; // rax
  size_t v12; // r8
  const void *v13; // rdx
  size_t v14; // r8
  const void *v15; // rdx
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v17; // edi
  NTSTATUS v18; // eax
  ULONG v19; // r8d
  ULONG v20; // r8d
  NTSTATUS v21; // eax
  __int64 v22; // rbx
  __int128 Data; // [rsp+30h] [rbp-D0h] BYREF
  struct _LUID AuthenticationId; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v25[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp-98h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+90h] [rbp-70h] BYREF

  DestinationString = 0;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  v8 = *a3;
  AuthenticationId = 0;
  v25[0] = 393222;
  Data = 0;
  v25[1] = L"N/A";
  v9 = v25;
  if ( a4 )
    v9 = a4;
  WORD1(Data) = *a2 + v8 + 6;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  PoolWithTag = (_DWORD *)SrvNetAllocatePoolWithTag(258, WORD1(Data), 1651266380);
  *((_QWORD *)&Data + 1) = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  *PoolWithTag = 6029404;
  v12 = *a3;
  v13 = (const void *)*((_QWORD *)a3 + 1);
  LOWORD(Data) = Data + 4;
  memmove((void *)(*((_QWORD *)&Data + 1) + 2 * ((unsigned __int64)(unsigned __int16)Data >> 1)), v13, v12);
  LOWORD(Data) = *a3 + Data;
  *(_WORD *)(((unsigned __int16)Data & 0xFFFE) + *((_QWORD *)&Data + 1)) = asc_14002F3C0[0];
  v14 = *a2;
  v15 = (const void *)*((_QWORD *)a2 + 1);
  LOWORD(Data) = Data + 2;
  memmove((void *)(*((_QWORD *)&Data + 1) + 2 * ((unsigned __int64)(unsigned __int16)Data >> 1)), v15, v14);
  LOWORD(Data) = *a2 + Data;
  RtlInitUnicodeString(&DestinationString, L"Security");
  AuditParameters.AuditId = *a1;
  AuditParameters.Type = 8;
  AuditParameters.CategoryId = 3;
  AuditParameters.ParameterCount = 0;
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  v17 = SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  if ( v17 >= 0 )
  {
    v18 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeLogonId, AuditParameters.ParameterCount, &AuthenticationId);
    v19 = AuditParameters.ParameterCount + 1;
    v17 = v18;
    ++AuditParameters.ParameterCount;
    if ( v18 >= 0 )
    {
      v17 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v19, &Data);
      v20 = ++AuditParameters.ParameterCount;
      if ( v17 >= 0 )
      {
        v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v20, v9);
        ++AuditParameters.ParameterCount;
        v17 = v21;
        if ( v21 >= 0 )
          v17 = SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, &AuditParameters, 0x7Du);
      }
    }
  }
  v22 = *((_QWORD *)&Data + 1);
  if ( *((_QWORD *)&Data + 1) )
  {
    SrvNetUpdateMemStatistics(
      *(unsigned int *)(*((_QWORD *)&Data + 1) - 12LL),
      *(unsigned int *)(*((_QWORD *)&Data + 1) - 16LL),
      0);
    ExFreePoolWithTag((PVOID)(v22 - 16), 0);
  }
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400088f0  push    rbp
0x1400088f2  push    rbx
0x1400088f3  push    rsi
0x1400088f4  push    rdi
0x1400088f5  push    r14
0x1400088f7  push    r15
0x1400088f9  lea     rbp, [rsp-3C8h]
0x140008901  sub     rsp, 4C8h
0x140008908  mov     rax, cs:__security_cookie
0x14000890f  xor     rax, rsp
0x140008912  mov     [rbp+3F0h+var_40], rax
0x140008919  mov     r14, r8
0x14000891c  mov     rdi, rdx
0x14000891f  mov     r15, rcx
0x140008922  xorps   xmm0, xmm0
0x140008925  xor     edx, edx; Val
0x140008927  lea     rcx, [rbp+3F0h+AuditParameters]; void *
0x14000892b  mov     r8d, 418h; Size
0x140008931  mov     rbx, r9
0x140008934  movups  xmmword ptr [rsp+4F0h+DestinationString.Length], xmm0
0x140008939  call    memset
0x14000893e  movzx   ecx, word ptr [r14]
0x140008942  lea     rax, aNA; "N/A"
0x140008949  xorps   xmm0, xmm0
0x14000894c  mov     qword ptr [rsp+4F0h+AuthenticationId.LowPart], 0
0x140008955  mov     edx, 6
0x14000895a  mov     [rsp+4F0h+var_4A8], 60006h
0x140008963  movups  [rsp+4F0h+Data], xmm0
0x140008968  test    rbx, rbx
0x14000896b  mov     [rsp+4F0h+var_4A0], rax
0x140008970  lea     rsi, [rsp+4F0h+var_4A8]
0x140008975  mov     r8d, 626C534Ch
0x14000897b  cmovnz  rsi, rbx
0x14000897f  add     cx, [rdi]
0x140008982  add     cx, dx
0x140008985  movzx   edx, cx
0x140008988  mov     ecx, 102h
0x14000898d  mov     word ptr [rsp+4F0h+Data+2], dx
0x140008992  movups  xmmword ptr [rsp+4F0h+SubjectContext.ClientToken], xmm0
0x140008997  movups  xmmword ptr [rsp+4F0h+SubjectContext.PrimaryToken], xmm0
0x14000899c  call    SrvNetAllocatePoolWithTag
0x1400089a1  mov     qword ptr [rsp+4F0h+Data+8], rax
0x1400089a6  test    rax, rax
0x1400089a9  jnz     short loc_1400089B5
0x1400089ab  mov     eax, 0C000009Ah
0x1400089b0  jmp     loc_140008B89
0x1400089b5  mov     dword ptr [rax], 5C005Ch
0x1400089bb  movzx   eax, word ptr [rsp+4F0h+Data]
0x1400089c0  movzx   r8d, word ptr [r14]; Size
0x1400089c4  add     ax, 4
0x1400089c8  mov     rdx, [r14+8]; Src
0x1400089cc  movzx   ecx, ax
0x1400089cf  mov     word ptr [rsp+4F0h+Data], ax
0x1400089d4  mov     rax, qword ptr [rsp+4F0h+Data+8]
0x1400089d9  shr     rcx, 1
0x1400089dc  lea     rcx, [rax+rcx*2]; void *
0x1400089e0  call    memmove
0x1400089e5  movzx   eax, word ptr [rsp+4F0h+Data]
0x1400089ea  add     ax, [r14]
0x1400089ee  mov     rcx, qword ptr [rsp+4F0h+Data+8]
0x1400089f3  mov     word ptr [rsp+4F0h+Data], ax
0x1400089f8  movzx   edx, ax
0x1400089fb  mov     eax, dword ptr cs:asc_14002F3C0; "\\"
0x140008a01  and     rdx, 0FFFFFFFFFFFFFFFEh
0x140008a05  mov     [rdx+rcx], ax
0x140008a09  movzx   eax, word ptr [rsp+4F0h+Data]
0x140008a0e  movzx   r8d, word ptr [rdi]; Size
0x140008a12  add     ax, 2
0x140008a16  mov     rdx, [rdi+8]; Src
0x140008a1a  movzx   ecx, ax
0x140008a1d  mov     word ptr [rsp+4F0h+Data], ax
0x140008a22  mov     rax, qword ptr [rsp+4F0h+Data+8]
0x140008a27  shr     rcx, 1
0x140008a2a  lea     rcx, [rax+rcx*2]; void *
0x140008a2e  call    memmove
0x140008a33  movzx   eax, word ptr [rdi]
0x140008a36  lea     rdx, SourceString; "Security"
0x140008a3d  add     word ptr [rsp+4F0h+Data], ax
0x140008a42  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x140008a47  call    cs:__imp_RtlInitUnicodeString
0x140008a4e  nop     dword ptr [rax+rax+00h]
0x140008a53  movzx   eax, word ptr [r15]
0x140008a57  lea     rcx, [rsp+4F0h+SubjectContext]; SubjectContext
0x140008a5c  mov     [rbp+3F0h+AuditParameters.AuditId], eax
0x140008a5f  mov     eax, 8
0x140008a64  mov     [rbp+3F0h+AuditParameters.Type], ax
0x140008a68  mov     [rbp+3F0h+AuditParameters.CategoryId], 3
0x140008a6f  mov     [rbp+3F0h+AuditParameters.ParameterCount], 0
0x140008a76  call    cs:__imp_SeCaptureSubjectContext
0x140008a7d  nop     dword ptr [rax+rax+00h]
0x140008a82  mov     rax, [rsp+4F0h+SubjectContext.ClientToken]
0x140008a87  lea     rdx, [rsp+4F0h+AuthenticationId]; AuthenticationId
0x140008a8c  mov     rcx, [rsp+4F0h+SubjectContext.PrimaryToken]
0x140008a91  test    rax, rax
0x140008a94  cmovnz  rcx, rax; Token
0x140008a98  call    cs:__imp_SeQueryAuthenticationIdToken
0x140008a9f  nop     dword ptr [rax+rax+00h]
0x140008aa4  mov     edi, eax
0x140008aa6  test    eax, eax
0x140008aa8  js      loc_140008B4C
0x140008aae  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]; Index
0x140008ab2  lea     r9, [rsp+4F0h+AuthenticationId]; Data
0x140008ab7  mov     edx, 5; Type
0x140008abc  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140008ac0  call    cs:__imp_SeSetAuditParameter
0x140008ac7  nop     dword ptr [rax+rax+00h]
0x140008acc  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x140008ad0  mov     ebx, 1
0x140008ad5  add     r8d, ebx; Index
0x140008ad8  mov     edi, eax
0x140008ada  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x140008ade  test    eax, eax
0x140008ae0  js      short loc_140008B4C
0x140008ae2  lea     r9, [rsp+4F0h+Data]; Data
0x140008ae7  mov     edx, ebx; Type
0x140008ae9  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140008aed  call    cs:__imp_SeSetAuditParameter
0x140008af4  nop     dword ptr [rax+rax+00h]
0x140008af9  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x140008afd  mov     edi, eax
0x140008aff  add     r8d, ebx; Index
0x140008b02  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x140008b06  test    eax, eax
0x140008b08  js      short loc_140008B4C
0x140008b0a  mov     r9, rsi; Data
0x140008b0d  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140008b11  mov     edx, ebx; Type
0x140008b13  call    cs:__imp_SeSetAuditParameter
0x140008b1a  nop     dword ptr [rax+rax+00h]
0x140008b1f  add     [rbp+3F0h+AuditParameters.ParameterCount], ebx
0x140008b22  mov     edi, eax
0x140008b24  test    eax, eax
0x140008b26  js      short loc_140008B4C
0x140008b28  lea     r9, [rbp+3F0h+AuditParameters]; AuditParameters
0x140008b2c  mov     [rsp+4F0h+AuditSubcategoryId], 7Dh ; '}'; AuditSubcategoryId
0x140008b34  xor     r8d, r8d; UserSid
0x140008b37  lea     rdx, [rsp+4F0h+DestinationString]; SourceName
0x140008b3c  xor     ecx, ecx; Flags
0x140008b3e  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x140008b45  nop     dword ptr [rax+rax+00h]
0x140008b4a  mov     edi, eax
0x140008b4c  mov     rbx, qword ptr [rsp+4F0h+Data+8]
0x140008b51  test    rbx, rbx
0x140008b54  jz      short loc_140008B76
0x140008b56  mov     ecx, [rbx-0Ch]
0x140008b59  xor     r8d, r8d
0x140008b5c  mov     edx, [rbx-10h]
0x140008b5f  call    SrvNetUpdateMemStatistics
0x140008b64  xor     edx, edx; Tag
0x140008b66  lea     rcx, [rbx-10h]; P
0x140008b6a  call    cs:__imp_ExFreePoolWithTag
0x140008b71  nop     dword ptr [rax+rax+00h]
0x140008b76  lea     rcx, [rsp+4F0h+SubjectContext]; SubjectContext
0x140008b7b  call    cs:__imp_SeReleaseSubjectContext
0x140008b82  nop     dword ptr [rax+rax+00h]
0x140008b87  mov     eax, edi
0x140008b89  mov     rcx, [rbp+3F0h+var_40]
0x140008b90  xor     rcx, rsp; StackCookie
0x140008b93  call    __security_check_cookie
0x140008b98  add     rsp, 4C8h
0x140008b9f  pop     r15
0x140008ba1  pop     r14
0x140008ba3  pop     rdi
0x140008ba4  pop     rsi
0x140008ba5  pop     rbx
0x140008ba6  pop     rbp
0x140008ba7  retn
```
