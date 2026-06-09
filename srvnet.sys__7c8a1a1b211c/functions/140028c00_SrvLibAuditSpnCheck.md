# SrvLibAuditSpnCheck

- ea: `0x140028c00`
- end: `0x140028e99`
- name: `SrvLibAuditSpnCheck`
- size: `665`
- prototype: `__int64 __fastcall(PVOID Data, PVOID, PVOID, PVOID, PVOID)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140024654`

## callees

- `0x140028c00`
- `0x14002a3e0`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140028c8f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028c8f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140028cc4`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140028cc4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028e67`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028e67`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140028ce6`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140028ce6`
- `ntoskrnl!SeSetAuditParameter` at `0x140028d0e`
- `ntoskrnl!SeSetAuditParameter` at `0x140028d4f`
- `ntoskrnl!SeSetAuditParameter` at `0x140028d7b`
- `ntoskrnl!SeSetAuditParameter` at `0x140028db6`
- `ntoskrnl!SeSetAuditParameter` at `0x140028df1`
- `ntoskrnl!SeSetAuditParameter` at `0x140028e28`
- `ntoskrnl!SeSetAuditParameter` at `0x140028d0e`
- `ntoskrnl!SeSetAuditParameter` at `0x140028d4f`
- `ntoskrnl!SeSetAuditParameter` at `0x140028d7b`
- `ntoskrnl!SeSetAuditParameter` at `0x140028db6`
- `ntoskrnl!SeSetAuditParameter` at `0x140028df1`
- `ntoskrnl!SeSetAuditParameter` at `0x140028e28`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140028e54`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140028e54`

## string_xrefs

- `0x140028c6f`: `Security`

## pseudocode

```c
__int64 __fastcall SrvLibAuditSpnCheck(_WORD *Data, _WORD *a2, _WORD *a3, _WORD *a4, int *Dataa)
{
  USHORT v9; // ax
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v11; // ebx
  ULONG v12; // r8d
  ULONG v13; // r8d
  ULONG v14; // r8d
  ULONG v15; // r8d
  ULONG v16; // r8d
  NTSTATUS v17; // eax
  _QWORD v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _LUID AuthenticationId; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-A8h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+80h] [rbp-80h] BYREF

  DestinationString = 0;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  v19[0] = 393222;
  v19[1] = L"N/A";
  AuthenticationId = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  RtlInitUnicodeString(&DestinationString, L"Security");
  v9 = 8;
  AuditParameters.AuditId = 5168;
  AuditParameters.CategoryId = 3;
  AuditParameters.ParameterCount = 0;
  if ( *Dataa < 0 )
    v9 = 16;
  AuditParameters.Type = v9;
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  v11 = SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  if ( v11 >= 0 )
  {
    v11 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeLogonId, AuditParameters.ParameterCount, &AuthenticationId);
    v12 = ++AuditParameters.ParameterCount;
    if ( v11 >= 0 )
    {
      if ( !Data || !*Data )
        Data = v19;
      v11 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v12, Data);
      v13 = ++AuditParameters.ParameterCount;
      if ( v11 >= 0 )
      {
        v11 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeHexUlong, v13, Dataa);
        v14 = ++AuditParameters.ParameterCount;
        if ( v11 >= 0 )
        {
          if ( !a2 || !*a2 )
            a2 = v19;
          v11 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v14, a2);
          v15 = ++AuditParameters.ParameterCount;
          if ( v11 >= 0 )
          {
            if ( !a3 || !*a3 )
              a3 = v19;
            v11 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v15, a3);
            v16 = ++AuditParameters.ParameterCount;
            if ( v11 >= 0 )
            {
              if ( !a4 || !*a4 )
                a4 = v19;
              v17 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v16, a4);
              ++AuditParameters.ParameterCount;
              v11 = v17;
              if ( v17 >= 0 )
                v11 = SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, &AuditParameters, 0x7Du);
            }
          }
        }
      }
    }
  }
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140028c00  push    rbp
0x140028c02  push    rbx
0x140028c03  push    rsi
0x140028c04  push    rdi
0x140028c05  push    r12
0x140028c07  push    r13
0x140028c09  push    r14
0x140028c0b  push    r15
0x140028c0d  lea     rbp, [rsp-3B8h]
0x140028c15  sub     rsp, 4B8h
0x140028c1c  mov     rax, cs:__security_cookie
0x140028c23  xor     rax, rsp
0x140028c26  mov     [rbp+3F0h+var_50], rax
0x140028c2d  mov     r12, [rbp+3F0h+Data]
0x140028c34  mov     rsi, r8
0x140028c37  mov     r14, rdx
0x140028c3a  mov     r15, rcx
0x140028c3d  xorps   xmm0, xmm0
0x140028c40  lea     rcx, [rbp+3F0h+AuditParameters]; void *
0x140028c44  xor     edx, edx; Val
0x140028c46  mov     r8d, 418h; Size
0x140028c4c  movups  xmmword ptr [rsp+4F0h+DestinationString.Length], xmm0
0x140028c51  mov     rdi, r9
0x140028c54  call    memset
0x140028c59  xorps   xmm0, xmm0
0x140028c5c  mov     [rsp+4F0h+var_4C0], 60006h
0x140028c65  lea     rax, aNA; "N/A"
0x140028c6c  xor     r13d, r13d
0x140028c6f  lea     rdx, SourceString; "Security"
0x140028c76  mov     [rsp+4F0h+var_4B8], rax
0x140028c7b  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x140028c80  mov     qword ptr [rsp+4F0h+AuthenticationId.LowPart], r13
0x140028c85  movups  xmmword ptr [rsp+4F0h+SubjectContext.ClientToken], xmm0
0x140028c8a  movups  xmmword ptr [rsp+4F0h+SubjectContext.PrimaryToken], xmm0
0x140028c8f  call    cs:__imp_RtlInitUnicodeString
0x140028c96  nop     dword ptr [rax+rax+00h]
0x140028c9b  lea     eax, [r13+8]
0x140028c9f  mov     [rbp+3F0h+AuditParameters.AuditId], 1430h
0x140028ca6  mov     [rbp+3F0h+AuditParameters.CategoryId], 3
0x140028cad  mov     [rbp+3F0h+AuditParameters.ParameterCount], r13d
0x140028cb1  cmp     [r12], r13d
0x140028cb5  jge     short loc_140028CBB
0x140028cb7  lea     eax, [r13+10h]
0x140028cbb  lea     rcx, [rsp+4F0h+SubjectContext]; SubjectContext
0x140028cc0  mov     [rbp+3F0h+AuditParameters.Type], ax
0x140028cc4  call    cs:__imp_SeCaptureSubjectContext
0x140028ccb  nop     dword ptr [rax+rax+00h]
0x140028cd0  mov     rax, [rsp+4F0h+SubjectContext.ClientToken]
0x140028cd5  lea     rdx, [rsp+4F0h+AuthenticationId]; AuthenticationId
0x140028cda  mov     rcx, [rsp+4F0h+SubjectContext.PrimaryToken]
0x140028cdf  test    rax, rax
0x140028ce2  cmovnz  rcx, rax; Token
0x140028ce6  call    cs:__imp_SeQueryAuthenticationIdToken
0x140028ced  nop     dword ptr [rax+rax+00h]
0x140028cf2  mov     ebx, eax
0x140028cf4  test    eax, eax
0x140028cf6  js      loc_140028E62
0x140028cfc  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]; Index
0x140028d00  lea     r9, [rsp+4F0h+AuthenticationId]; Data
0x140028d05  mov     edx, 5; Type
0x140028d0a  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140028d0e  call    cs:__imp_SeSetAuditParameter
0x140028d15  nop     dword ptr [rax+rax+00h]
0x140028d1a  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x140028d1e  mov     ebx, eax
0x140028d20  inc     r8d; Index
0x140028d23  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x140028d27  test    eax, eax
0x140028d29  js      loc_140028E62
0x140028d2f  test    r15, r15
0x140028d32  jz      short loc_140028D3A
0x140028d34  cmp     [r15], r13w
0x140028d38  jnz     short loc_140028D3F
0x140028d3a  lea     r15, [rsp+4F0h+var_4C0]
0x140028d3f  mov     r9, r15; Data
0x140028d42  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140028d46  mov     r15d, 1
0x140028d4c  mov     edx, r15d; Type
0x140028d4f  call    cs:__imp_SeSetAuditParameter
0x140028d56  nop     dword ptr [rax+rax+00h]
0x140028d5b  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x140028d5f  mov     ebx, eax
0x140028d61  add     r8d, r15d; Index
0x140028d64  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x140028d68  test    eax, eax
0x140028d6a  js      loc_140028E62
0x140028d70  mov     r9, r12; Data
0x140028d73  lea     edx, [r15+9]; Type
0x140028d77  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140028d7b  call    cs:__imp_SeSetAuditParameter
0x140028d82  nop     dword ptr [rax+rax+00h]
0x140028d87  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x140028d8b  mov     ebx, eax
0x140028d8d  add     r8d, r15d; Index
0x140028d90  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x140028d94  test    eax, eax
0x140028d96  js      loc_140028E62
0x140028d9c  test    r14, r14
0x140028d9f  jz      short loc_140028DA7
0x140028da1  cmp     [r14], r13w
0x140028da5  jnz     short loc_140028DAC
0x140028da7  lea     r14, [rsp+4F0h+var_4C0]
0x140028dac  mov     r9, r14; Data
0x140028daf  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140028db3  mov     edx, r15d; Type
0x140028db6  call    cs:__imp_SeSetAuditParameter
0x140028dbd  nop     dword ptr [rax+rax+00h]
0x140028dc2  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x140028dc6  mov     ebx, eax
0x140028dc8  add     r8d, r15d; Index
0x140028dcb  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x140028dcf  test    eax, eax
0x140028dd1  js      loc_140028E62
0x140028dd7  test    rsi, rsi
0x140028dda  jz      short loc_140028DE2
0x140028ddc  cmp     [rsi], r13w
0x140028de0  jnz     short loc_140028DE7
0x140028de2  lea     rsi, [rsp+4F0h+var_4C0]
0x140028de7  mov     r9, rsi; Data
0x140028dea  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140028dee  mov     edx, r15d; Type
0x140028df1  call    cs:__imp_SeSetAuditParameter
0x140028df8  nop     dword ptr [rax+rax+00h]
0x140028dfd  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x140028e01  mov     ebx, eax
0x140028e03  add     r8d, r15d; Index
0x140028e06  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x140028e0a  test    eax, eax
0x140028e0c  js      short loc_140028E62
0x140028e0e  test    rdi, rdi
0x140028e11  jz      short loc_140028E19
0x140028e13  cmp     [rdi], r13w
0x140028e17  jnz     short loc_140028E1E
0x140028e19  lea     rdi, [rsp+4F0h+var_4C0]
0x140028e1e  mov     r9, rdi; Data
0x140028e21  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140028e25  mov     edx, r15d; Type
0x140028e28  call    cs:__imp_SeSetAuditParameter
0x140028e2f  nop     dword ptr [rax+rax+00h]
0x140028e34  add     [rbp+3F0h+AuditParameters.ParameterCount], r15d
0x140028e38  mov     ebx, eax
0x140028e3a  test    eax, eax
0x140028e3c  js      short loc_140028E62
0x140028e3e  lea     r9, [rbp+3F0h+AuditParameters]; AuditParameters
0x140028e42  mov     [rsp+4F0h+AuditSubcategoryId], 7Dh ; '}'; AuditSubcategoryId
0x140028e4a  xor     r8d, r8d; UserSid
0x140028e4d  lea     rdx, [rsp+4F0h+DestinationString]; SourceName
0x140028e52  xor     ecx, ecx; Flags
0x140028e54  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x140028e5b  nop     dword ptr [rax+rax+00h]
0x140028e60  mov     ebx, eax
0x140028e62  lea     rcx, [rsp+4F0h+SubjectContext]; SubjectContext
0x140028e67  call    cs:__imp_SeReleaseSubjectContext
0x140028e6e  nop     dword ptr [rax+rax+00h]
0x140028e73  mov     eax, ebx
0x140028e75  mov     rcx, [rbp+3F0h+var_50]
0x140028e7c  xor     rcx, rsp; StackCookie
0x140028e7f  call    __security_check_cookie
0x140028e84  add     rsp, 4B8h
0x140028e8b  pop     r15
0x140028e8d  pop     r14
0x140028e8f  pop     r13
0x140028e91  pop     r12
0x140028e93  pop     rdi
0x140028e94  pop     rsi
0x140028e95  pop     rbx
0x140028e96  pop     rbp
0x140028e97  retn
```
