# SrvLibAuditShareConnect

- ea: `0x140003f70`
- end: `0x14000423b`
- name: `SrvLibAuditShareConnect`
- size: `715`
- prototype: `__int64 __usercall@<rax>(PVOID Data@<rcx>, PVOID@<rdx>, PVOID@<r8>, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140003f70`
- `0x14002a3e0`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140003fe3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003ffb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003fe3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003ffb`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004032`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004032`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400040ba`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400040ba`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140004054`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140004054`
- `ntoskrnl!SeSetAuditParameter` at `0x140004078`
- `ntoskrnl!SeSetAuditParameter` at `0x1400040a3`
- `ntoskrnl!SeSetAuditParameter` at `0x140004109`
- `ntoskrnl!SeSetAuditParameter` at `0x140004136`
- `ntoskrnl!SeSetAuditParameter` at `0x140004163`
- `ntoskrnl!SeSetAuditParameter` at `0x140004192`
- `ntoskrnl!SeSetAuditParameter` at `0x140004078`
- `ntoskrnl!SeSetAuditParameter` at `0x1400040a3`
- `ntoskrnl!SeSetAuditParameter` at `0x140004109`
- `ntoskrnl!SeSetAuditParameter` at `0x140004136`
- `ntoskrnl!SeSetAuditParameter` at `0x140004163`
- `ntoskrnl!SeSetAuditParameter` at `0x140004192`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140004204`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140004204`

## string_xrefs

- `0x140003fc1`: `Security`

## pseudocode

```c
__int64 __fastcall SrvLibAuditShareConnect(PVOID Data, PVOID a2, PVOID a3, unsigned int a4, char a5)
{
  USHORT v8; // ax
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v10; // ebx
  ULONG v11; // r8d
  ULONG v13; // r15d
  ULONG v14; // r8d
  ULONG v15; // r8d
  ULONG v16; // r8d
  __int64 v17; // rax
  ULONG_PTR v18; // rcx
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  struct _LUID AuthenticationId; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING Dataa; // [rsp+40h] [rbp-C0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+60h] [rbp-A0h] BYREF
  _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+80h] [rbp-80h] BYREF

  v19 = a4;
  DestinationString = 0;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AuthenticationId = 0;
  Dataa = 0;
  RtlInitUnicodeString(&DestinationString, L"Security");
  RtlInitUnicodeString(&Dataa, L"File");
  AuditParameters.AuditId = 5140;
  AuditParameters.CategoryId = 3;
  if ( a5 )
    v8 = 8;
  else
    v8 = 16;
  AuditParameters.Type = v8;
  AuditParameters.ParameterCount = 0;
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  v10 = SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  if ( v10 >= 0 )
  {
    v10 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeLogonId, AuditParameters.ParameterCount, &AuthenticationId);
    v11 = ++AuditParameters.ParameterCount;
    if ( v10 >= 0 )
    {
      v10 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v11, &Dataa);
      if ( v10 >= 0 )
      {
        v13 = AuditParameters.ParameterCount + 2;
        v10 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeSockAddr, ++AuditParameters.ParameterCount, a2);
        v14 = ++AuditParameters.ParameterCount;
        if ( v10 >= 0 )
        {
          v10 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v14, Data);
          v15 = ++AuditParameters.ParameterCount;
          if ( v10 >= 0 )
          {
            v10 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v15, a3);
            v16 = ++AuditParameters.ParameterCount;
            if ( v10 >= 0 )
            {
              v10 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeHexUlong, v16, &v19);
              v17 = ++AuditParameters.ParameterCount;
              if ( v10 >= 0 )
              {
                if ( (unsigned int)v17 >= 0x1F )
                {
                  v10 = -2147483643;
                }
                else
                {
                  v18 = v19;
                  AuditParameters.Parameters[v17].Type = SeAdtParmTypeAccessMask;
                  AuditParameters.Parameters[AuditParameters.ParameterCount].Length = 4;
                  AuditParameters.Parameters[AuditParameters.ParameterCount].Data[0] = v18;
                  AuditParameters.Parameters[AuditParameters.ParameterCount++].Data[1] = v13;
                  v10 = SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, &AuditParameters, 0x7Du);
                }
              }
            }
          }
        }
      }
    }
  }
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140003f70  push    rbp
0x140003f72  push    rbx
0x140003f73  push    rsi
0x140003f74  push    rdi
0x140003f75  push    r14
0x140003f77  lea     rbp, [rsp-3C0h]
0x140003f7f  sub     rsp, 4C0h
0x140003f86  mov     rax, cs:__security_cookie
0x140003f8d  xor     rax, rsp
0x140003f90  mov     [rbp+3E0h+var_40], rax
0x140003f97  mov     r14, r8
0x140003f9a  mov     [rsp+4E0h+var_4B0], r9d
0x140003f9f  mov     rsi, rdx
0x140003fa2  mov     rdi, rcx
0x140003fa5  xorps   xmm0, xmm0
0x140003fa8  lea     rcx, [rbp+3E0h+AuditParameters]; void *
0x140003fac  xor     edx, edx; Val
0x140003fae  mov     r8d, 418h; Size
0x140003fb4  movups  xmmword ptr [rsp+4E0h+DestinationString.Length], xmm0
0x140003fb9  call    memset
0x140003fbe  xorps   xmm0, xmm0
0x140003fc1  lea     rdx, SourceString; "Security"
0x140003fc8  xor     ebx, ebx
0x140003fca  lea     rcx, [rsp+4E0h+DestinationString]; DestinationString
0x140003fcf  movups  xmmword ptr [rsp+4E0h+SubjectContext.ClientToken], xmm0
0x140003fd4  mov     qword ptr [rsp+4E0h+AuthenticationId.LowPart], rbx
0x140003fd9  movups  xmmword ptr [rsp+4E0h+SubjectContext.PrimaryToken], xmm0
0x140003fde  movups  xmmword ptr [rsp+4E0h+Data.Length], xmm0
0x140003fe3  call    cs:__imp_RtlInitUnicodeString
0x140003fea  nop     dword ptr [rax+rax+00h]
0x140003fef  lea     rdx, aFile; "File"
0x140003ff6  lea     rcx, [rsp+4E0h+Data]; DestinationString
0x140003ffb  call    cs:__imp_RtlInitUnicodeString
0x140004002  nop     dword ptr [rax+rax+00h]
0x140004007  mov     [rbp+3E0h+AuditParameters.AuditId], 1414h
0x14000400e  mov     [rbp+3E0h+AuditParameters.CategoryId], 3
0x140004015  cmp     [rbp+3E0h+arg_20], bl
0x14000401b  jnz     loc_140004231
0x140004021  mov     eax, 10h
0x140004026  lea     rcx, [rsp+4E0h+SubjectContext]; SubjectContext
0x14000402b  mov     [rbp+3E0h+AuditParameters.Type], ax
0x14000402f  mov     [rbp+3E0h+AuditParameters.ParameterCount], ebx
0x140004032  call    cs:__imp_SeCaptureSubjectContext
0x140004039  nop     dword ptr [rax+rax+00h]
0x14000403e  mov     rax, [rsp+4E0h+SubjectContext.ClientToken]
0x140004043  lea     rdx, [rsp+4E0h+AuthenticationId]; AuthenticationId
0x140004048  mov     rcx, [rsp+4E0h+SubjectContext.PrimaryToken]
0x14000404d  test    rax, rax
0x140004050  cmovnz  rcx, rax; Token
0x140004054  call    cs:__imp_SeQueryAuthenticationIdToken
0x14000405b  nop     dword ptr [rax+rax+00h]
0x140004060  mov     ebx, eax
0x140004062  test    eax, eax
0x140004064  js      short loc_1400040B5
0x140004066  mov     r8d, [rbp+3E0h+AuditParameters.ParameterCount]; Index
0x14000406a  lea     r9, [rsp+4E0h+AuthenticationId]; Data
0x14000406f  mov     edx, 5; Type
0x140004074  lea     rcx, [rbp+3E0h+AuditParameters]; AuditParameters
0x140004078  call    cs:__imp_SeSetAuditParameter
0x14000407f  nop     dword ptr [rax+rax+00h]
0x140004084  mov     r8d, [rbp+3E0h+AuditParameters.ParameterCount]
0x140004088  mov     ebx, eax
0x14000408a  inc     r8d; Index
0x14000408d  mov     [rbp+3E0h+AuditParameters.ParameterCount], r8d
0x140004091  test    eax, eax
0x140004093  js      short loc_1400040B5
0x140004095  lea     r9, [rsp+4E0h+Data]; Data
0x14000409a  mov     edx, 1; Type
0x14000409f  lea     rcx, [rbp+3E0h+AuditParameters]; AuditParameters
0x1400040a3  call    cs:__imp_SeSetAuditParameter
0x1400040aa  nop     dword ptr [rax+rax+00h]
0x1400040af  mov     ebx, eax
0x1400040b1  test    eax, eax
0x1400040b3  jns     short loc_1400040E6
0x1400040b5  lea     rcx, [rsp+4E0h+SubjectContext]; SubjectContext
0x1400040ba  call    cs:__imp_SeReleaseSubjectContext
0x1400040c1  nop     dword ptr [rax+rax+00h]
0x1400040c6  mov     eax, ebx
0x1400040c8  mov     rcx, [rbp+3E0h+var_40]
0x1400040cf  xor     rcx, rsp; StackCookie
0x1400040d2  call    __security_check_cookie
0x1400040d7  add     rsp, 4C0h
0x1400040de  pop     r14
0x1400040e0  pop     rdi
0x1400040e1  pop     rsi
0x1400040e2  pop     rbx
0x1400040e3  pop     rbp
0x1400040e4  retn
0x1400040e6  mov     r8d, [rbp+3E0h+AuditParameters.ParameterCount]
0x1400040ea  lea     rcx, [rbp+3E0h+AuditParameters]; AuditParameters
0x1400040ee  mov     [rsp+4E0h+var_28], r15
0x1400040f6  mov     r9, rsi; Data
0x1400040f9  mov     edx, 17h; Type
0x1400040fe  lea     r15d, [r8+2]
0x140004102  inc     r8d; Index
0x140004105  mov     [rbp+3E0h+AuditParameters.ParameterCount], r8d
0x140004109  call    cs:__imp_SeSetAuditParameter
0x140004110  nop     dword ptr [rax+rax+00h]
0x140004115  mov     r8d, [rbp+3E0h+AuditParameters.ParameterCount]
0x140004119  mov     ebx, eax
0x14000411b  inc     r8d; Index
0x14000411e  mov     [rbp+3E0h+AuditParameters.ParameterCount], r8d
0x140004122  test    eax, eax
0x140004124  js      loc_140004212
0x14000412a  mov     r9, rdi; Data
0x14000412d  lea     rcx, [rbp+3E0h+AuditParameters]; AuditParameters
0x140004131  mov     edx, 1; Type
0x140004136  call    cs:__imp_SeSetAuditParameter
0x14000413d  nop     dword ptr [rax+rax+00h]
0x140004142  mov     r8d, [rbp+3E0h+AuditParameters.ParameterCount]
0x140004146  mov     ebx, eax
0x140004148  inc     r8d; Index
0x14000414b  mov     [rbp+3E0h+AuditParameters.ParameterCount], r8d
0x14000414f  test    eax, eax
0x140004151  js      loc_140004212
0x140004157  mov     r9, r14; Data
0x14000415a  lea     rcx, [rbp+3E0h+AuditParameters]; AuditParameters
0x14000415e  mov     edx, 1; Type
0x140004163  call    cs:__imp_SeSetAuditParameter
0x14000416a  nop     dword ptr [rax+rax+00h]
0x14000416f  mov     r8d, [rbp+3E0h+AuditParameters.ParameterCount]
0x140004173  mov     ebx, eax
0x140004175  inc     r8d; Index
0x140004178  mov     [rbp+3E0h+AuditParameters.ParameterCount], r8d
0x14000417c  test    eax, eax
0x14000417e  js      loc_140004212
0x140004184  lea     r9, [rsp+4E0h+var_4B0]; Data
0x140004189  mov     edx, 0Ah; Type
0x14000418e  lea     rcx, [rbp+3E0h+AuditParameters]; AuditParameters
0x140004192  call    cs:__imp_SeSetAuditParameter
0x140004199  nop     dword ptr [rax+rax+00h]
0x14000419e  mov     ebx, eax
0x1400041a0  mov     eax, [rbp+3E0h+AuditParameters.ParameterCount]
0x1400041a3  inc     eax
0x1400041a5  mov     [rbp+3E0h+AuditParameters.ParameterCount], eax
0x1400041a8  test    ebx, ebx
0x1400041aa  js      short loc_140004212
0x1400041ac  cmp     eax, 1Fh
0x1400041af  jnb     short loc_14000421F
0x1400041b1  mov     ecx, [rsp+4E0h+var_4B0]
0x1400041b5  lea     r9, [rbp+3E0h+AuditParameters]; AuditParameters
0x1400041b9  shl     rax, 5
0x1400041bd  lea     rdx, [rsp+4E0h+DestinationString]; SourceName
0x1400041c2  xor     r8d, r8d; UserSid
0x1400041c5  mov     [rsp+4E0h+AuditSubcategoryId], 7Dh ; '}'; AuditSubcategoryId
0x1400041cd  mov     [rbp+rax+3E0h+AuditParameters.Parameters.Type], 7
0x1400041d5  mov     eax, [rbp+3E0h+AuditParameters.ParameterCount]
0x1400041d8  shl     rax, 5
0x1400041dc  mov     [rbp+rax+3E0h+AuditParameters.Parameters.Length], 4
0x1400041e4  mov     eax, [rbp+3E0h+AuditParameters.ParameterCount]
0x1400041e7  shl     rax, 5
0x1400041eb  mov     [rbp+rax+3E0h+AuditParameters.Parameters.Data], rcx
0x1400041f0  mov     eax, [rbp+3E0h+AuditParameters.ParameterCount]
0x1400041f3  mov     ecx, r15d
0x1400041f6  shl     rax, 5
0x1400041fa  mov     [rbp+rax+3E0h+AuditParameters.Parameters.Data+8], rcx
0x1400041ff  xor     ecx, ecx; Flags
0x140004201  inc     [rbp+3E0h+AuditParameters.ParameterCount]
0x140004204  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x14000420b  nop     dword ptr [rax+rax+00h]
0x140004210  mov     ebx, eax
0x140004212  mov     r15, [rsp+4E0h+var_28]
0x14000421a  jmp     loc_1400040B5
0x14000421f  mov     r15, [rsp+4E0h+var_28]
0x140004227  mov     ebx, 80000005h
0x14000422c  jmp     loc_1400040B5
0x140004231  mov     eax, 8
0x140004236  jmp     loc_140004026
```
