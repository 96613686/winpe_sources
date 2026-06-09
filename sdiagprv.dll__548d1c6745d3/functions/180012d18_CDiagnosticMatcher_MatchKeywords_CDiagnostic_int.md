# CDiagnosticMatcher::MatchKeywords(CDiagnostic *,int *)

- ea: `0x180012d18`
- end: `0x180012ee7`
- name: `?MatchKeywords@CDiagnosticMatcher@@AEBAJPEAVCDiagnostic@@PEAH@Z`
- size: `463`
- prototype: `__int64 __fastcall(CDiagnosticMatcher *__hidden this, struct CDiagnostic *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012aac`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180012d18`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180012e26`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180012e3a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180012e26`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180012e3a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012de3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012dfe`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012de3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180012dfe`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180012e79`
- `OLEAUT32!__imp_VarBstrCmp` at `0x180012e79`

## pseudocode

```c
__int64 __fastcall CDiagnosticMatcher::MatchKeywords(CDiagnosticMatcher *this, struct CDiagnostic *a2, int *a3)
{
  SAFEARRAY *v3; // rsi
  HRESULT v6; // ebx
  const char *v7; // rax
  __int64 v9; // rbp
  __int64 v10; // r15
  OLECHAR *v11; // r12
  __int64 v12; // r9
  void *v13; // [rsp+68h] [rbp+10h] BYREF
  void *ppvData; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  ppvData = 0;
  v13 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return (unsigned int)v6;
    v7 = "Diagnostic";
    goto LABEL_9;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    goto LABEL_6;
  }
  v3 = (SAFEARRAY *)*((_QWORD *)a2 + 20);
  v6 = 0;
  *a3 = 0;
  if ( !v3 )
  {
LABEL_13:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
      McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CDiagnosticMatcher::MatchKeywords");
    goto LABEL_15;
  }
  if ( *((_DWORD *)this + 8) )
  {
    *a3 = 1;
    goto LABEL_13;
  }
  v6 = SafeArrayAccessData(*((SAFEARRAY **)this + 3), &ppvData);
  if ( v6 >= 0 )
  {
    v6 = SafeArrayAccessData(v3, &v13);
    if ( v6 >= 0 )
    {
      v9 = 0;
LABEL_23:
      if ( (unsigned int)v9 >= *(_DWORD *)(*((_QWORD *)this + 3) + 24LL) )
      {
        *a3 = 0;
      }
      else
      {
        v10 = 0;
        v11 = (OLECHAR *)*((_QWORD *)ppvData + v9);
        while ( 1 )
        {
          if ( (unsigned int)v10 >= v3->rgsabound[0].cElements )
          {
            v9 = (unsigned int)(v9 + 1);
            goto LABEL_23;
          }
          if ( VarBstrCmp(v11, *((BSTR *)v13 + v10), *((_DWORD *)this + 2), 1u) == 1 )
            break;
          v10 = (unsigned int)(v10 + 1);
        }
        *a3 = 1;
      }
LABEL_32:
      if ( v6 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_15;
        v12 = (unsigned int)v6;
LABEL_35:
        McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticMatcher::MatchKeywords", v12);
        goto LABEL_15;
      }
      goto LABEL_13;
    }
  }
  if ( v6 != -2147024809 )
    goto LABEL_32;
LABEL_6:
  if ( a3 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_15;
    v12 = 2147942487LL;
    goto LABEL_35;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v7 = "IsMatch";
LABEL_9:
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)"CDiagnosticMatcher::MatchKeywords",
      -2147024809,
      (__int64)v7);
  }
LABEL_15:
  if ( v13 )
  {
    SafeArrayUnaccessData(v3);
    v13 = 0;
  }
  if ( ppvData )
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 3));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012d18  mov     rax, rsp
0x180012d1b  mov     [rax+8], rbx
0x180012d1f  mov     [rax+18h], rbp
0x180012d23  push    rsi
0x180012d24  push    rdi
0x180012d25  push    r12
0x180012d27  push    r14
0x180012d29  push    r15
0x180012d2b  sub     rsp, 30h
0x180012d2f  xor     esi, esi
0x180012d31  mov     qword ptr [rax+20h], 0
0x180012d39  mov     [rax+10h], rsi
0x180012d3d  mov     rdi, r8
0x180012d40  mov     r14, rcx
0x180012d43  test    rdx, rdx
0x180012d46  jnz     short loc_180012D63
0x180012d48  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012d4f  mov     ebx, 80070057h
0x180012d54  jz      loc_180012E04
0x180012d5a  lea     rax, aDiagnostic; "Diagnostic"
0x180012d61  jmp     short loc_180012D86
0x180012d63  test    rdi, rdi
0x180012d66  jnz     short loc_180012D9F
0x180012d68  mov     ebx, 80070057h
0x180012d6d  test    rdi, rdi
0x180012d70  jnz     loc_180012ED2
0x180012d76  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012d7d  jz      short loc_180012DD8
0x180012d7f  lea     rax, aIsmatch; "IsMatch"
0x180012d86  mov     r9d, 80070057h
0x180012d8c  mov     [rsp+58h+var_38], rax
0x180012d91  lea     r8, aCdiagnosticmat_0; "CDiagnosticMatcher::MatchKeywords"
0x180012d98  call    McTemplateU0sqs_EventWriteTransfer
0x180012d9d  jmp     short loc_180012DD8
0x180012d9f  mov     rsi, [rdx+0A0h]
0x180012da6  xor     ebx, ebx
0x180012da8  mov     [r8], ebx
0x180012dab  test    rsi, rsi
0x180012dae  jz      short loc_180012DBC
0x180012db0  cmp     [rcx+20h], ebx
0x180012db3  jz      short loc_180012E1D
0x180012db5  mov     dword ptr [r8], 1
0x180012dbc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180012dc3  jz      short loc_180012DD8
0x180012dc5  lea     r8, aCdiagnosticmat_0; "CDiagnosticMatcher::MatchKeywords"
0x180012dcc  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180012dd3  call    McTemplateU0s_EventWriteTransfer
0x180012dd8  cmp     [rsp+58h+arg_8], 0
0x180012dde  jz      short loc_180012DF2
0x180012de0  mov     rcx, rsi; psa
0x180012de3  call    cs:__imp_SafeArrayUnaccessData
0x180012de9  mov     [rsp+58h+arg_8], 0
0x180012df2  cmp     [rsp+58h+ppvData], 0
0x180012df8  jz      short loc_180012E04
0x180012dfa  mov     rcx, [r14+18h]; psa
0x180012dfe  call    cs:__imp_SafeArrayUnaccessData
0x180012e04  mov     rbp, [rsp+58h+arg_10]
0x180012e09  mov     eax, ebx
0x180012e0b  mov     rbx, [rsp+58h+arg_0]
0x180012e10  add     rsp, 30h
0x180012e14  pop     r15
0x180012e16  pop     r14
0x180012e18  pop     r12
0x180012e1a  pop     rdi
0x180012e1b  pop     rsi
0x180012e1c  retn
0x180012e1d  mov     rcx, [rcx+18h]; psa
0x180012e21  lea     rdx, [rsp+58h+ppvData]; ppvData
0x180012e26  call    cs:__imp_SafeArrayAccessData
0x180012e2c  mov     ebx, eax
0x180012e2e  test    eax, eax
0x180012e30  js      short loc_180012E9D
0x180012e32  lea     rdx, [rsp+58h+arg_8]; ppvData
0x180012e37  mov     rcx, rsi; psa
0x180012e3a  call    cs:__imp_SafeArrayAccessData
0x180012e40  mov     ebx, eax
0x180012e42  test    eax, eax
0x180012e44  js      short loc_180012E9D
0x180012e46  xor     ebp, ebp
0x180012e48  mov     rax, [r14+18h]
0x180012e4c  cmp     ebp, [rax+18h]
0x180012e4f  jnb     short loc_180012E95
0x180012e51  mov     rax, [rsp+58h+ppvData]
0x180012e56  xor     r15d, r15d
0x180012e59  mov     r12, [rax+rbp*8]
0x180012e5d  cmp     r15d, [rsi+18h]
0x180012e61  jnb     short loc_180012E89
0x180012e63  mov     rdx, [rsp+58h+arg_8]
0x180012e68  mov     r9d, 1; dwFlags
0x180012e6e  mov     r8d, [r14+8]; lcid
0x180012e72  mov     rcx, r12; bstrLeft
0x180012e75  mov     rdx, [rdx+r15*8]; bstrRight
0x180012e79  call    cs:__imp_VarBstrCmp
0x180012e7f  cmp     eax, 1
0x180012e82  jz      short loc_180012E8D
0x180012e84  inc     r15d
0x180012e87  jmp     short loc_180012E5D
0x180012e89  inc     ebp
0x180012e8b  jmp     short loc_180012E48
0x180012e8d  mov     dword ptr [rdi], 1
0x180012e93  jmp     short loc_180012EA9
0x180012e95  mov     dword ptr [rdi], 0
0x180012e9b  jmp     short loc_180012EA9
0x180012e9d  cmp     ebx, 80070057h
0x180012ea3  jz      loc_180012D6D
0x180012ea9  test    ebx, ebx
0x180012eab  jz      loc_180012DBC
0x180012eb1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012eb8  jz      loc_180012DD8
0x180012ebe  mov     r9d, ebx
0x180012ec1  lea     r8, aCdiagnosticmat_0; "CDiagnosticMatcher::MatchKeywords"
0x180012ec8  call    McTemplateU0sq_EventWriteTransfer
0x180012ecd  jmp     loc_180012DD8
0x180012ed2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012ed9  jz      loc_180012DD8
0x180012edf  mov     r9d, 80070057h
0x180012ee5  jmp     short loc_180012EC1
```
