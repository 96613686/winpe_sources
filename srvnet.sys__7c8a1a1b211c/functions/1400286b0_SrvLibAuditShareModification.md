# SrvLibAuditShareModification

- ea: `0x1400286b0`
- end: `0x140028bf9`
- name: `SrvLibAuditShareModification`
- size: `1353`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140025b80`

## callees

- `0x140007360`
- `0x140007c60`
- `0x1400286b0`
- `0x14002a3e0`
- `0x14002a540`
- `0x14002a840`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140028838`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028850`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028838`
- `ntoskrnl!RtlInitUnicodeString` at `0x140028850`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140028adf`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140028b37`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140028adf`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140028b37`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140028a98`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140028a98`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002887e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002887e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028bc7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140028bc7`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14002889e`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14002889e`
- `ntoskrnl!SeSetAuditParameter` at `0x1400288c5`
- `ntoskrnl!SeSetAuditParameter` at `0x1400288f5`
- `ntoskrnl!SeSetAuditParameter` at `0x140028925`
- `ntoskrnl!SeSetAuditParameter` at `0x140028951`
- `ntoskrnl!SeSetAuditParameter` at `0x140028987`
- `ntoskrnl!SeSetAuditParameter` at `0x1400289be`
- `ntoskrnl!SeSetAuditParameter` at `0x1400289ef`
- `ntoskrnl!SeSetAuditParameter` at `0x140028a1d`
- `ntoskrnl!SeSetAuditParameter` at `0x140028a4b`
- `ntoskrnl!SeSetAuditParameter` at `0x140028a79`
- `ntoskrnl!SeSetAuditParameter` at `0x1400288c5`
- `ntoskrnl!SeSetAuditParameter` at `0x1400288f5`
- `ntoskrnl!SeSetAuditParameter` at `0x140028925`
- `ntoskrnl!SeSetAuditParameter` at `0x140028951`
- `ntoskrnl!SeSetAuditParameter` at `0x140028987`
- `ntoskrnl!SeSetAuditParameter` at `0x1400289be`
- `ntoskrnl!SeSetAuditParameter` at `0x1400289ef`
- `ntoskrnl!SeSetAuditParameter` at `0x140028a1d`
- `ntoskrnl!SeSetAuditParameter` at `0x140028a4b`
- `ntoskrnl!SeSetAuditParameter` at `0x140028a79`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140028b8b`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140028b8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028bb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028bb7`

## string_xrefs

- `0x140028827`: `Security`
- `0x140028844`: `Directory`

## pseudocode

```c
__int64 SrvLibAuditShareModification(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        _QWORD *a3,
        _OWORD *a4,
        _OWORD *a5,
        ...)
{
  _WORD *v6; // rsi
  _WORD *v8; // r14
  __int16 v11; // cx
  _QWORD *v12; // rax
  __int16 v13; // cx
  _DWORD *PoolWithTag; // rax
  size_t v16; // r8
  const void *v17; // rdx
  size_t v18; // r8
  const void *v19; // rdx
  PACCESS_TOKEN PrimaryToken; // rcx
  NTSTATUS v21; // edi
  NTSTATUS v22; // eax
  ULONG v23; // r8d
  ULONG v24; // r13d
  ULONG v25; // eax
  ULONG v26; // eax
  _QWORD *v27; // r9
  ULONG v28; // eax
  _QWORD *v29; // r9
  ULONG v30; // eax
  ULONG v31; // eax
  ULONG v32; // eax
  ULONG v33; // eax
  NTSTATUS v34; // eax
  _OWORD *v35; // rbx
  _OWORD *v36; // rdi
  ULONG v37; // eax
  __int64 v38; // rcx
  ULONG v39; // eax
  __int64 v40; // rbx
  __int128 v41; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v42[2]; // [rsp+40h] [rbp-C0h] BYREF
  struct _LUID AuthenticationId; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v44; // [rsp+58h] [rbp-A8h]
  struct _UNICODE_STRING Data; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+80h] [rbp-80h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+C0h] [rbp-40h]
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+578h] [rbp+478h] BYREF
  va_list va; // [rsp+578h] [rbp+478h]
  __int64 v53; // [rsp+580h] [rbp+480h] BYREF
  va_list va1; // [rsp+580h] [rbp+480h]
  PVOID v55; // [rsp+588h] [rbp+488h]
  PVOID v56; // [rsp+590h] [rbp+490h]
  __int64 v57; // [rsp+598h] [rbp+498h] BYREF
  va_list va2; // [rsp+598h] [rbp+498h]
  va_list va3; // [rsp+5A0h] [rbp+4A0h] BYREF

  va_start(va3, a5);
  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v51 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v53 = va_arg(va2, _QWORD);
  v55 = va_arg(va2, PVOID);
  v56 = va_arg(va2, PVOID);
  va_copy(va3, va2);
  v57 = va_arg(va3, _QWORD);
  v6 = v56;
  v8 = v55;
  DestinationString = 0;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  v42[0] = 393222;
  AuthenticationId = 0;
  v42[1] = L"N/A";
  v49 = 0;
  v11 = *a1;
  v12 = v42;
  v41 = 0;
  *(_OWORD *)&SubjectContext.ClientToken = 0;
  if ( a3 )
    v12 = a3;
  v13 = *a2 + v11;
  v44 = v12;
  WORD1(v41) = v13 + 6;
  *(_OWORD *)&SubjectContext.PrimaryToken = 0;
  Data = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  PoolWithTag = (_DWORD *)SrvNetAllocatePoolWithTag(258, (unsigned __int16)(v13 + 6), 1651266380);
  *((_QWORD *)&v41 + 1) = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  *PoolWithTag = 6029404;
  v16 = *a2;
  v17 = (const void *)*((_QWORD *)a2 + 1);
  LOWORD(v41) = v41 + 4;
  memmove((void *)(*((_QWORD *)&v41 + 1) + 2 * ((unsigned __int64)(unsigned __int16)v41 >> 1)), v17, v16);
  LOWORD(v41) = *a2 + v41;
  *(_WORD *)(((unsigned __int16)v41 & 0xFFFE) + *((_QWORD *)&v41 + 1)) = asc_14002F3C0[0];
  v18 = *a1;
  v19 = (const void *)*((_QWORD *)a1 + 1);
  LOWORD(v41) = v41 + 2;
  memmove((void *)(*((_QWORD *)&v41 + 1) + 2 * ((unsigned __int64)(unsigned __int16)v41 >> 1)), v19, v18);
  LOWORD(v41) = *a1 + v41;
  RtlInitUnicodeString(&DestinationString, L"Security");
  RtlInitUnicodeString(&Data, L"Directory");
  AuditParameters.AuditId = 5143;
  AuditParameters.Type = 8;
  AuditParameters.CategoryId = 3;
  AuditParameters.ParameterCount = 0;
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  v21 = SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  if ( v21 >= 0 )
  {
    v22 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeLogonId, AuditParameters.ParameterCount, &AuthenticationId);
    v23 = AuditParameters.ParameterCount + 1;
    v21 = v22;
    ++AuditParameters.ParameterCount;
    if ( v22 >= 0 )
    {
      v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v23, &Data);
      if ( v21 >= 0 )
      {
        v24 = AuditParameters.ParameterCount + 2;
        v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, ++AuditParameters.ParameterCount, &v41);
        v25 = ++AuditParameters.ParameterCount;
        if ( v21 >= 0 )
        {
          v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v25, v44);
          v26 = ++AuditParameters.ParameterCount;
          if ( v21 >= 0 )
          {
            v27 = v42;
            if ( *v8 )
              v27 = v8;
            v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v26, v27);
            v28 = ++AuditParameters.ParameterCount;
            if ( v21 >= 0 )
            {
              v29 = v42;
              if ( *v6 )
                v29 = v6;
              v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v28, v29);
              v30 = ++AuditParameters.ParameterCount;
              if ( v21 >= 0 )
              {
                v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeHexUlong, v30, va);
                v31 = ++AuditParameters.ParameterCount;
                if ( v21 >= 0 )
                {
                  v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeHexUlong, v31, va1);
                  v32 = ++AuditParameters.ParameterCount;
                  if ( v21 >= 0 )
                  {
                    v21 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeHexUlong, v32, va2);
                    v33 = ++AuditParameters.ParameterCount;
                    if ( v21 >= 0 )
                    {
                      v34 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeHexUlong, v33, va3);
                      ++AuditParameters.ParameterCount;
                      v21 = v34;
                      if ( v34 >= 0 )
                      {
                        RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                        v35 = SecurityDescriptor;
                        v36 = SecurityDescriptor;
                        if ( a4 )
                          v35 = a4;
                        if ( a5 )
                          v36 = a5;
                        if ( AuditParameters.ParameterCount < 0x1E )
                        {
                          AuditParameters.Parameters[AuditParameters.ParameterCount].Type = SeAdtParmTypeSD;
                          v37 = RtlLengthSecurityDescriptor(v35);
                          AuditParameters.Parameters[AuditParameters.ParameterCount].Length = v37;
                          AuditParameters.Parameters[AuditParameters.ParameterCount].Address = v35;
                          AuditParameters.Parameters[AuditParameters.ParameterCount].Data[0] = 15;
                          AuditParameters.Parameters[AuditParameters.ParameterCount].Data[1] = v24;
                          v38 = ++AuditParameters.ParameterCount;
                          AuditParameters.Parameters[v38].Type = SeAdtParmTypeSD;
                          v39 = RtlLengthSecurityDescriptor(v36);
                          AuditParameters.Parameters[AuditParameters.ParameterCount].Length = v39;
                          AuditParameters.Parameters[AuditParameters.ParameterCount].Address = v36;
                          AuditParameters.Parameters[AuditParameters.ParameterCount].Data[0] = 15;
                          AuditParameters.Parameters[AuditParameters.ParameterCount++].Data[1] = v24;
                          v21 = SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, &AuditParameters, 0x7Du);
                        }
                        else
                        {
                          v21 = -2147483643;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v40 = *((_QWORD *)&v41 + 1);
  if ( *((_QWORD *)&v41 + 1) )
  {
    SrvNetUpdateMemStatistics(
      *(unsigned int *)(*((_QWORD *)&v41 + 1) - 12LL),
      *(unsigned int *)(*((_QWORD *)&v41 + 1) - 16LL),
      0);
    ExFreePoolWithTag((PVOID)(v40 - 16), 0);
  }
  SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1400286b0  push    rbp
0x1400286b2  push    rbx
0x1400286b3  push    rsi
0x1400286b4  push    rdi
0x1400286b5  push    r12
0x1400286b7  push    r13
0x1400286b9  push    r14
0x1400286bb  push    r15
0x1400286bd  lea     rbp, [rsp-408h]
0x1400286c5  sub     rsp, 508h
0x1400286cc  mov     rax, cs:__security_cookie
0x1400286d3  xor     rax, rsp
0x1400286d6  mov     [rbp+440h+var_50], rax
0x1400286dd  mov     r12, [rbp+440h+arg_20]
0x1400286e4  mov     rbx, r8
0x1400286e7  mov     rsi, [rbp+440h+arg_40]
0x1400286ee  mov     r13, rdx
0x1400286f1  mov     r14, [rbp+440h+arg_38]
0x1400286f8  mov     rdi, rcx
0x1400286fb  xorps   xmm0, xmm0
0x1400286fe  lea     rcx, [rbp+440h+AuditParameters]; void *
0x140028702  xor     edx, edx; Val
0x140028704  mov     r8d, 418h; Size
0x14002870a  movups  xmmword ptr [rsp+540h+DestinationString.Length], xmm0
0x14002870f  mov     r15, r9
0x140028712  call    memset
0x140028717  xor     ecx, ecx
0x140028719  mov     [rsp+540h+var_500], 60006h
0x140028722  mov     qword ptr [rsp+540h+AuthenticationId.LowPart], rcx
0x140028727  lea     rax, aNA; "N/A"
0x14002872e  xorps   xmm0, xmm0
0x140028731  mov     [rsp+540h+var_4F8], rax
0x140028736  xor     eax, eax
0x140028738  xorps   xmm1, xmm1
0x14002873b  lea     edx, [rcx+6]
0x14002873e  mov     [rbp+440h+var_480], rax
0x140028742  movzx   ecx, word ptr [rdi]
0x140028745  lea     rax, [rsp+540h+var_500]
0x14002874a  movups  [rsp+540h+var_510], xmm0
0x14002874f  test    rbx, rbx
0x140028752  mov     r8d, 626C534Ch
0x140028758  movups  xmmword ptr [rbp+440h+SubjectContext.ClientToken], xmm0
0x14002875c  cmovnz  rax, rbx
0x140028760  add     cx, [r13+0]
0x140028765  add     cx, dx
0x140028768  mov     [rsp+540h+var_4E8], rax
0x14002876d  movzx   edx, cx
0x140028770  mov     ecx, 102h
0x140028775  mov     word ptr [rsp+540h+var_510+2], dx
0x14002877a  movups  xmmword ptr [rbp+440h+SubjectContext.PrimaryToken], xmm0
0x14002877e  movups  xmmword ptr [rsp+540h+Data.Length], xmm0
0x140028783  movups  [rbp+440h+SecurityDescriptor], xmm1
0x140028787  movups  [rbp+440h+var_490], xmm1
0x14002878b  call    SrvNetAllocatePoolWithTag
0x140028790  mov     qword ptr [rsp+540h+var_510+8], rax
0x140028795  test    rax, rax
0x140028798  jnz     short loc_1400287A4
0x14002879a  mov     eax, 0C000009Ah
0x14002879f  jmp     loc_140028BD5
0x1400287a4  mov     dword ptr [rax], 5C005Ch
0x1400287aa  movzx   eax, word ptr [rsp+540h+var_510]
0x1400287af  movzx   r8d, word ptr [r13+0]; Size
0x1400287b4  add     ax, 4
0x1400287b8  mov     rdx, [r13+8]; Src
0x1400287bc  movzx   ecx, ax
0x1400287bf  mov     word ptr [rsp+540h+var_510], ax
0x1400287c4  mov     rax, qword ptr [rsp+540h+var_510+8]
0x1400287c9  shr     rcx, 1
0x1400287cc  lea     rcx, [rax+rcx*2]; void *
0x1400287d0  call    memmove
0x1400287d5  movzx   eax, word ptr [rsp+540h+var_510]
0x1400287da  add     ax, [r13+0]
0x1400287df  mov     rcx, qword ptr [rsp+540h+var_510+8]
0x1400287e4  mov     word ptr [rsp+540h+var_510], ax
0x1400287e9  movzx   edx, ax
0x1400287ec  mov     eax, dword ptr cs:asc_14002F3C0; "\\"
0x1400287f2  and     rdx, 0FFFFFFFFFFFFFFFEh
0x1400287f6  mov     [rdx+rcx], ax
0x1400287fa  movzx   eax, word ptr [rsp+540h+var_510]
0x1400287ff  movzx   r8d, word ptr [rdi]; Size
0x140028803  add     ax, 2
0x140028807  mov     rdx, [rdi+8]; Src
0x14002880b  movzx   ecx, ax
0x14002880e  mov     word ptr [rsp+540h+var_510], ax
0x140028813  mov     rax, qword ptr [rsp+540h+var_510+8]
0x140028818  shr     rcx, 1
0x14002881b  lea     rcx, [rax+rcx*2]; void *
0x14002881f  call    memmove
0x140028824  movzx   eax, word ptr [rdi]
0x140028827  lea     rdx, SourceString; "Security"
0x14002882e  add     word ptr [rsp+540h+var_510], ax
0x140028833  lea     rcx, [rsp+540h+DestinationString]; DestinationString
0x140028838  call    cs:__imp_RtlInitUnicodeString
0x14002883f  nop     dword ptr [rax+rax+00h]
0x140028844  lea     rdx, aDirectory; "Directory"
0x14002884b  lea     rcx, [rsp+540h+Data]; DestinationString
0x140028850  call    cs:__imp_RtlInitUnicodeString
0x140028857  nop     dword ptr [rax+rax+00h]
0x14002885c  mov     eax, 8
0x140028861  mov     [rbp+440h+AuditParameters.AuditId], 1417h
0x140028868  xor     r13d, r13d
0x14002886b  mov     [rbp+440h+AuditParameters.Type], ax
0x14002886f  lea     rcx, [rbp+440h+SubjectContext]; SubjectContext
0x140028873  mov     [rbp+440h+AuditParameters.CategoryId], 3
0x14002887a  mov     [rbp+440h+AuditParameters.ParameterCount], r13d
0x14002887e  call    cs:__imp_SeCaptureSubjectContext
0x140028885  nop     dword ptr [rax+rax+00h]
0x14002888a  mov     rax, [rbp+440h+SubjectContext.ClientToken]
0x14002888e  lea     rdx, [rsp+540h+AuthenticationId]; AuthenticationId
0x140028893  mov     rcx, [rbp+440h+SubjectContext.PrimaryToken]
0x140028897  test    rax, rax
0x14002889a  cmovnz  rcx, rax; Token
0x14002889e  call    cs:__imp_SeQueryAuthenticationIdToken
0x1400288a5  nop     dword ptr [rax+rax+00h]
0x1400288aa  mov     edi, eax
0x1400288ac  test    eax, eax
0x1400288ae  js      loc_140028B99
0x1400288b4  mov     r8d, [rbp+440h+AuditParameters.ParameterCount]; Index
0x1400288b8  lea     r9, [rsp+540h+AuthenticationId]; Data
0x1400288bd  lea     edx, [r13+5]; Type
0x1400288c1  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x1400288c5  call    cs:__imp_SeSetAuditParameter
0x1400288cc  nop     dword ptr [rax+rax+00h]
0x1400288d1  mov     r8d, [rbp+440h+AuditParameters.ParameterCount]
0x1400288d5  lea     ebx, [r13+1]
0x1400288d9  add     r8d, ebx; Index
0x1400288dc  mov     edi, eax
0x1400288de  mov     [rbp+440h+AuditParameters.ParameterCount], r8d
0x1400288e2  test    eax, eax
0x1400288e4  js      loc_140028B99
0x1400288ea  lea     r9, [rsp+540h+Data]; Data
0x1400288ef  mov     edx, ebx; Type
0x1400288f1  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x1400288f5  call    cs:__imp_SeSetAuditParameter
0x1400288fc  nop     dword ptr [rax+rax+00h]
0x140028901  mov     edi, eax
0x140028903  test    eax, eax
0x140028905  js      loc_140028B99
0x14002890b  mov     r8d, [rbp+440h+AuditParameters.ParameterCount]
0x14002890f  lea     r9, [rsp+540h+var_510]; Data
0x140028914  mov     edx, ebx; Type
0x140028916  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x14002891a  lea     r13d, [r8+2]
0x14002891e  add     r8d, ebx; Index
0x140028921  mov     [rbp+440h+AuditParameters.ParameterCount], r8d
0x140028925  call    cs:__imp_SeSetAuditParameter
0x14002892c  nop     dword ptr [rax+rax+00h]
0x140028931  mov     edi, eax
0x140028933  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028936  add     eax, ebx
0x140028938  mov     [rbp+440h+AuditParameters.ParameterCount], eax
0x14002893b  test    edi, edi
0x14002893d  js      loc_140028B99
0x140028943  mov     r9, [rsp+540h+var_4E8]; Data
0x140028948  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x14002894c  mov     r8d, eax; Index
0x14002894f  mov     edx, ebx; Type
0x140028951  call    cs:__imp_SeSetAuditParameter
0x140028958  nop     dword ptr [rax+rax+00h]
0x14002895d  mov     edi, eax
0x14002895f  xor     ecx, ecx
0x140028961  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028964  add     eax, ebx
0x140028966  mov     [rbp+440h+AuditParameters.ParameterCount], eax
0x140028969  test    edi, edi
0x14002896b  js      loc_140028B99
0x140028971  cmp     [r14], cx
0x140028975  lea     r9, [rsp+540h+var_500]
0x14002897a  mov     r8d, eax; Index
0x14002897d  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x140028981  cmovnz  r9, r14; Data
0x140028985  mov     edx, ebx; Type
0x140028987  call    cs:__imp_SeSetAuditParameter
0x14002898e  nop     dword ptr [rax+rax+00h]
0x140028993  mov     edi, eax
0x140028995  xor     r14d, r14d
0x140028998  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x14002899b  add     eax, ebx
0x14002899d  mov     [rbp+440h+AuditParameters.ParameterCount], eax
0x1400289a0  test    edi, edi
0x1400289a2  js      loc_140028B99
0x1400289a8  cmp     [rsi], r14w
0x1400289ac  lea     r9, [rsp+540h+var_500]
0x1400289b1  mov     r8d, eax; Index
0x1400289b4  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x1400289b8  cmovnz  r9, rsi; Data
0x1400289bc  mov     edx, ebx; Type
0x1400289be  call    cs:__imp_SeSetAuditParameter
0x1400289c5  nop     dword ptr [rax+rax+00h]
0x1400289ca  mov     edi, eax
0x1400289cc  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x1400289cf  add     eax, ebx
0x1400289d1  mov     [rbp+440h+AuditParameters.ParameterCount], eax
0x1400289d4  test    edi, edi
0x1400289d6  js      loc_140028B99
0x1400289dc  lea     esi, [rbx+9]
0x1400289df  mov     r8d, eax; Index
0x1400289e2  mov     edx, esi; Type
0x1400289e4  lea     r9, [rbp+440h+arg_28]; Data
0x1400289eb  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x1400289ef  call    cs:__imp_SeSetAuditParameter
0x1400289f6  nop     dword ptr [rax+rax+00h]
0x1400289fb  mov     edi, eax
0x1400289fd  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028a00  add     eax, ebx
0x140028a02  mov     [rbp+440h+AuditParameters.ParameterCount], eax
0x140028a05  test    edi, edi
0x140028a07  js      loc_140028B99
0x140028a0d  lea     r9, [rbp+440h+arg_30]; Data
0x140028a14  mov     r8d, eax; Index
0x140028a17  mov     edx, esi; Type
0x140028a19  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x140028a1d  call    cs:__imp_SeSetAuditParameter
0x140028a24  nop     dword ptr [rax+rax+00h]
0x140028a29  mov     edi, eax
0x140028a2b  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028a2e  add     eax, ebx
0x140028a30  mov     [rbp+440h+AuditParameters.ParameterCount], eax
0x140028a33  test    edi, edi
0x140028a35  js      loc_140028B99
0x140028a3b  lea     r9, [rbp+440h+arg_48]; Data
0x140028a42  mov     r8d, eax; Index
0x140028a45  mov     edx, esi; Type
0x140028a47  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x140028a4b  call    cs:__imp_SeSetAuditParameter
0x140028a52  nop     dword ptr [rax+rax+00h]
0x140028a57  mov     edi, eax
0x140028a59  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028a5c  add     eax, ebx
0x140028a5e  mov     [rbp+440h+AuditParameters.ParameterCount], eax
0x140028a61  test    edi, edi
0x140028a63  js      loc_140028B99
0x140028a69  lea     r9, [rbp+440h+arg_50]; Data
0x140028a70  mov     r8d, eax; Index
0x140028a73  mov     edx, esi; Type
0x140028a75  lea     rcx, [rbp+440h+AuditParameters]; AuditParameters
0x140028a79  call    cs:__imp_SeSetAuditParameter
0x140028a80  nop     dword ptr [rax+rax+00h]
0x140028a85  add     [rbp+440h+AuditParameters.ParameterCount], ebx
0x140028a88  mov     edi, eax
0x140028a8a  test    eax, eax
0x140028a8c  js      loc_140028B99
0x140028a92  mov     edx, ebx; Revision
0x140028a94  lea     rcx, [rbp+440h+SecurityDescriptor]; SecurityDescriptor
0x140028a98  call    cs:__imp_RtlCreateSecurityDescriptor
0x140028a9f  nop     dword ptr [rax+rax+00h]
0x140028aa4  test    r15, r15
0x140028aa7  lea     rbx, [rbp+440h+SecurityDescriptor]
0x140028aab  lea     rdi, [rbp+440h+SecurityDescriptor]
0x140028aaf  cmovnz  rbx, r15
0x140028ab3  test    r12, r12
0x140028ab6  cmovnz  rdi, r12
0x140028aba  cmp     [rbp+440h+AuditParameters.ParameterCount], 1Eh
0x140028abe  jb      short loc_140028ACA
0x140028ac0  mov     edi, 80000005h
0x140028ac5  jmp     loc_140028B99
0x140028aca  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028acd  mov     r14d, 18h
0x140028ad3  shl     rax, 5
0x140028ad7  mov     rcx, rbx; SecurityDescriptor
0x140028ada  mov     [rbp+rax+440h+AuditParameters.Parameters.Type], r14d
0x140028adf  call    cs:__imp_RtlLengthSecurityDescriptor
0x140028ae6  nop     dword ptr [rax+rax+00h]
0x140028aeb  mov     ecx, [rbp+440h+AuditParameters.ParameterCount]
0x140028aee  lea     esi, [r14-9]
0x140028af2  shl     rcx, 5
0x140028af6  mov     [rbp+rcx+440h+AuditParameters.Parameters.Length], eax
0x140028afa  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028afd  shl     rax, 5
0x140028b01  mov     [rbp+rax+440h+AuditParameters.Parameters.Address], rbx
0x140028b06  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028b09  shl     rax, 5
0x140028b0d  mov     ebx, r13d
0x140028b10  mov     [rbp+rax+440h+AuditParameters.Parameters.Data], rsi
0x140028b15  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028b18  shl     rax, 5
0x140028b1c  mov     [rbp+rax+440h+AuditParameters.Parameters.Data+8], rbx
0x140028b21  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028b24  inc     eax
0x140028b26  mov     ecx, eax
0x140028b28  shl     rcx, 5
0x140028b2c  mov     [rbp+440h+AuditParameters.ParameterCount], eax
0x140028b2f  mov     [rbp+rcx+440h+AuditParameters.Parameters.Type], r14d
0x140028b34  mov     rcx, rdi; SecurityDescriptor
0x140028b37  call    cs:__imp_RtlLengthSecurityDescriptor
0x140028b3e  nop     dword ptr [rax+rax+00h]
0x140028b43  mov     ecx, [rbp+440h+AuditParameters.ParameterCount]
0x140028b46  lea     r9, [rbp+440h+AuditParameters]; AuditParameters
0x140028b4a  shl     rcx, 5
0x140028b4e  lea     rdx, [rsp+540h+DestinationString]; SourceName
0x140028b53  xor     r8d, r8d; UserSid
0x140028b56  mov     [rsp+540h+AuditSubcategoryId], 7Dh ; '}'; AuditSubcategoryId
0x140028b5e  mov     [rbp+rcx+440h+AuditParameters.Parameters.Length], eax
0x140028b62  xor     ecx, ecx; Flags
0x140028b64  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028b67  shl     rax, 5
0x140028b6b  mov     [rbp+rax+440h+AuditParameters.Parameters.Address], rdi
0x140028b70  mov     eax, [rbp+440h+AuditParameters.ParameterCount]
0x140028b73  shl     rax, 5
0x140028b77  mov     [rbp+rax+440h+AuditParameters.Parameters.Data], rsi
  ... truncated ...
```
