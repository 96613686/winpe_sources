# CDiagnosticXmlParser::ReadXmlStringArrayElement(ushort const *,tagSAFEARRAY * *)

- ea: `0x180017080`
- end: `0x180017373`
- name: `?ReadXmlStringArrayElement@CDiagnosticXmlParser@@AEAAJPEBGPEAPEAUtagSAFEARRAY@@@Z`
- size: `755`
- prototype: `__int64 __fastcall(CDiagnosticXmlParser *this, const unsigned __int16 *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800178c8`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180017080`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001712a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001712a`
- `OLEAUT32!__imp_SysFreeString` at `0x180017165`
- `OLEAUT32!__imp_SysFreeString` at `0x180017165`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001718b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001718b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001725a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001725a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180017175`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800172da`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180017175`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800172da`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180017241`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180017241`

## string_xrefs

- `0x1800170d2`: `CDiagnosticXmlParser::ReadXmlStringArrayElement`
- `0x180017114`: `CDiagnosticXmlParser::ReadXmlStringArrayElement`
- `0x18001714a`: `CDiagnosticXmlParser::ReadXmlStringArrayElement`
- `0x180017319`: `CDiagnosticXmlParser::ReadXmlStringArrayElement`
- `0x180017337`: `CDiagnosticXmlParser::ReadXmlStringArrayElement`
- `0x180017362`: `CDiagnosticXmlParser::ReadXmlStringArrayElement`

## pseudocode

```c
__int64 __fastcall CDiagnosticXmlParser::ReadXmlStringArrayElement(
        CDiagnosticXmlParser *this,
        const unsigned __int16 *a2,
        struct tagSAFEARRAY **a3)
{
  SAFEARRAY *v3; // rdi
  CDiagnosticXmlParser *v5; // rbx
  HRESULT v6; // ebx
  OLECHAR *v7; // r14
  BSTR v8; // rax
  SAFEARRAY *Vector; // rax
  signed int i; // esi
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  CDiagnosticXmlParser *v13; // [rsp+38h] [rbp-8h] BYREF
  ULONG cElements; // [rsp+78h] [rbp+38h] BYREF
  void *ppvData; // [rsp+88h] [rbp+48h] BYREF

  v3 = 0;
  cElements = 0;
  ppvData = 0;
  v12 = 0;
  v5 = this;
  v13 = 0;
  if ( a2 )
  {
    if ( !a3 )
    {
      v7 = 0;
      v6 = -2147024809;
      goto LABEL_6;
    }
    v8 = SysAllocString(a2);
    v7 = v8;
    if ( !v8 )
      goto LABEL_10;
    v6 = (*(__int64 (__fastcall **)(_QWORD, BSTR, CDiagnosticXmlParser **))(**((_QWORD **)v5 + 1) + 288LL))(
           *((_QWORD *)v5 + 1),
           v8,
           &v13);
    if ( v6 >= 0 )
    {
      this = v13;
      if ( !v13 )
      {
        v6 = -2147467259;
        goto LABEL_45;
      }
      v6 = (*(__int64 (__fastcall **)(CDiagnosticXmlParser *, ULONG *))(*(_QWORD *)v13 + 64LL))(v13, &cElements);
      if ( v6 >= 0 )
      {
        if ( (int)cElements <= 0 )
        {
          v6 = -2147024637;
          goto LABEL_45;
        }
        Vector = SafeArrayCreateVector(8u, 0, cElements);
        v3 = Vector;
        if ( !Vector )
        {
LABEL_10:
          v6 = -2147024882;
          goto LABEL_11;
        }
        v6 = SafeArrayAccessData(Vector, &ppvData);
        if ( v6 >= 0 )
        {
          for ( i = 0; i < (int)cElements; ++i )
          {
            if ( v12 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
              v12 = 0;
            }
            v6 = (*(__int64 (__fastcall **)(CDiagnosticXmlParser *, __int64 *))(*(_QWORD *)v13 + 72LL))(v13, &v12);
            if ( v6 < 0 )
              goto LABEL_42;
            v6 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 208LL))(v12, (char *)ppvData + 8 * i);
            if ( v6 < 0 )
              goto LABEL_42;
          }
          if ( ppvData )
          {
            SafeArrayUnaccessData(v3);
            ppvData = 0;
          }
          *a3 = v3;
          v3 = 0;
        }
      }
    }
LABEL_42:
    switch ( v6 )
    {
      case -2147024882:
LABEL_11:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          McTemplateU0s_EventWriteTransfer(
            this,
            SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
            "CDiagnosticXmlParser::ReadXmlStringArrayElement");
LABEL_13:
        if ( !v7 )
          goto LABEL_15;
LABEL_14:
        SysFreeString(v7);
        goto LABEL_15;
      case -2147024809:
LABEL_6:
        if ( a3 )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
            McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticXmlParser::ReadXmlStringArrayElement", 2147942487LL);
        }
        else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        {
          McTemplateU0sqs_EventWriteTransfer(
            (_DWORD)this,
            (_DWORD)a2,
            (unsigned int)"CDiagnosticXmlParser::ReadXmlStringArrayElement",
            -2147024809,
            (__int64)"Value");
        }
        goto LABEL_13;
      case 0:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
          McTemplateU0s_EventWriteTransfer(
            this,
            SDIAGPRV_EVENT_DEBUG_SUCCESS,
            "CDiagnosticXmlParser::ReadXmlStringArrayElement");
        goto LABEL_14;
    }
LABEL_45:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticXmlParser::ReadXmlStringArrayElement", (unsigned int)v6);
    goto LABEL_14;
  }
  v6 = -2147024809;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    return (unsigned int)v6;
  McTemplateU0sqs_EventWriteTransfer(
    (_DWORD)this,
    0,
    (unsigned int)"CDiagnosticXmlParser::ReadXmlStringArrayElement",
    -2147024809,
    (__int64)"FieldName");
LABEL_15:
  if ( ppvData )
  {
    SafeArrayUnaccessData(v3);
    ppvData = 0;
  }
  if ( v3 )
    SafeArrayDestroy(v3);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
    (*(void (__fastcall **)(CDiagnosticXmlParser *))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017080  mov     [rsp-28h+arg_0], rbx
0x180017085  push    rbp
0x180017086  push    rsi
0x180017087  push    rdi
0x180017088  push    r14
0x18001708a  push    r15
0x18001708c  mov     rbp, rsp
0x18001708f  sub     rsp, 40h
0x180017093  xor     edi, edi
0x180017095  mov     [rbp+cElements], 0
0x18001709c  mov     [rbp+ppvData], rdi
0x1800170a0  mov     r15, r8
0x1800170a3  mov     [rbp+var_10], rdi
0x1800170a7  mov     rbx, rcx
0x1800170aa  mov     [rbp+var_8], rdi
0x1800170ae  test    rdx, rdx
0x1800170b1  jnz     short loc_1800170E8
0x1800170b3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800170ba  mov     ebx, 80070057h
0x1800170bf  jz      loc_1800171C3
0x1800170c5  lea     rax, aFieldname; "FieldName"
0x1800170cc  mov     r9d, 80070057h
0x1800170d2  lea     r8, aCdiagnosticxml_0; "CDiagnosticXmlParser::ReadXmlStringArra"...
0x1800170d9  mov     [rsp+40h+var_20], rax
0x1800170de  call    McTemplateU0sqs_EventWriteTransfer
0x1800170e3  jmp     loc_18001716B
0x1800170e8  test    r15, r15
0x1800170eb  jnz     short loc_180017127
0x1800170ed  xor     r14d, r14d
0x1800170f0  mov     ebx, 80070057h
0x1800170f5  test    r15, r15
0x1800170f8  jnz     loc_18001734F
0x1800170fe  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017105  jz      short loc_18001715D
0x180017107  lea     rax, aValue; "Value"
0x18001710e  mov     r9d, 80070057h
0x180017114  lea     r8, aCdiagnosticxml_0; "CDiagnosticXmlParser::ReadXmlStringArra"...
0x18001711b  mov     [rsp+40h+var_20], rax
0x180017120  call    McTemplateU0sqs_EventWriteTransfer
0x180017125  jmp     short loc_18001715D
0x180017127  mov     rcx, rdx; psz
0x18001712a  call    cs:__imp_SysAllocString
0x180017130  mov     r14, rax
0x180017133  test    rax, rax
0x180017136  jnz     loc_1800171D6
0x18001713c  mov     ebx, 8007000Eh
0x180017141  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017148  jz      short loc_18001715D
0x18001714a  lea     r8, aCdiagnosticxml_0; "CDiagnosticXmlParser::ReadXmlStringArra"...
0x180017151  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180017158  call    McTemplateU0s_EventWriteTransfer
0x18001715d  test    r14, r14
0x180017160  jz      short loc_18001716B
0x180017162  mov     rcx, r14; bstrString
0x180017165  call    cs:__imp_SysFreeString
0x18001716b  cmp     [rbp+ppvData], 0
0x180017170  jz      short loc_180017183
0x180017172  mov     rcx, rdi; psa
0x180017175  call    cs:__imp_SafeArrayUnaccessData
0x18001717b  mov     [rbp+ppvData], 0
0x180017183  test    rdi, rdi
0x180017186  jz      short loc_180017191
0x180017188  mov     rcx, rdi; psa
0x18001718b  call    cs:__imp_SafeArrayDestroy
0x180017191  mov     rcx, [rbp+var_10]
0x180017195  test    rcx, rcx
0x180017198  jz      short loc_1800171AE
0x18001719a  mov     rax, [rcx]
0x18001719d  mov     rax, [rax+10h]
0x1800171a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171a6  mov     [rbp+var_10], 0
0x1800171ae  mov     rcx, [rbp+var_8]
0x1800171b2  test    rcx, rcx
0x1800171b5  jz      short loc_1800171C3
0x1800171b7  mov     rax, [rcx]
0x1800171ba  mov     rax, [rax+10h]
0x1800171be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171c3  mov     eax, ebx
0x1800171c5  mov     rbx, [rsp+40h+arg_0]
0x1800171ca  add     rsp, 40h
0x1800171ce  pop     r15
0x1800171d0  pop     r14
0x1800171d2  pop     rdi
0x1800171d3  pop     rsi
0x1800171d4  pop     rbp
0x1800171d5  retn
0x1800171d6  mov     rcx, [rbx+8]
0x1800171da  lea     r8, [rbp+var_8]
0x1800171de  mov     rdx, r14
0x1800171e1  mov     rax, [rcx]
0x1800171e4  mov     rax, [rax+120h]
0x1800171eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171f0  mov     ebx, eax
0x1800171f2  test    eax, eax
0x1800171f4  js      loc_1800172ED
0x1800171fa  mov     rcx, [rbp+var_8]
0x1800171fe  test    rcx, rcx
0x180017201  jnz     short loc_18001720D
0x180017203  mov     ebx, 80004005h
0x180017208  jmp     loc_180017309
0x18001720d  mov     rax, [rcx]
0x180017210  lea     rdx, [rbp+cElements]
0x180017214  mov     rax, [rax+40h]
0x180017218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001721d  mov     ebx, eax
0x18001721f  test    eax, eax
0x180017221  js      loc_1800172ED
0x180017227  mov     r8d, [rbp+cElements]; cElements
0x18001722b  test    r8d, r8d
0x18001722e  jg      short loc_18001723A
0x180017230  mov     ebx, 80070103h
0x180017235  jmp     loc_180017309
0x18001723a  mov     ecx, 8; vt
0x18001723f  xor     edx, edx; lLbound
0x180017241  call    cs:__imp_SafeArrayCreateVector
0x180017247  mov     rdi, rax
0x18001724a  test    rax, rax
0x18001724d  jz      loc_18001713C
0x180017253  lea     rdx, [rbp+ppvData]; ppvData
0x180017257  mov     rcx, rax; psa
0x18001725a  call    cs:__imp_SafeArrayAccessData
0x180017260  mov     ebx, eax
0x180017262  test    eax, eax
0x180017264  js      loc_1800172ED
0x18001726a  xor     esi, esi
0x18001726c  cmp     esi, [rbp+cElements]
0x18001726f  jge     short loc_1800172D0
0x180017271  mov     rcx, [rbp+var_10]
0x180017275  test    rcx, rcx
0x180017278  jz      short loc_18001728E
0x18001727a  mov     rax, [rcx]
0x18001727d  mov     rax, [rax+10h]
0x180017281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017286  mov     [rbp+var_10], 0
0x18001728e  mov     rcx, [rbp+var_8]
0x180017292  lea     rdx, [rbp+var_10]
0x180017296  mov     rax, [rcx]
0x180017299  mov     rax, [rax+48h]
0x18001729d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a2  mov     ebx, eax
0x1800172a4  test    eax, eax
0x1800172a6  js      short loc_1800172ED
0x1800172a8  mov     rax, [rbp+ppvData]
0x1800172ac  mov     rcx, [rbp+var_10]
0x1800172b0  movsxd  rdx, esi
0x1800172b3  mov     r8, [rcx]
0x1800172b6  lea     rdx, [rax+rdx*8]
0x1800172ba  mov     rax, [r8+0D0h]
0x1800172c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172c6  mov     ebx, eax
0x1800172c8  test    eax, eax
0x1800172ca  js      short loc_1800172ED
0x1800172cc  inc     esi
0x1800172ce  jmp     short loc_18001726C
0x1800172d0  cmp     [rbp+ppvData], 0
0x1800172d5  jz      short loc_1800172E8
0x1800172d7  mov     rcx, rdi; psa
0x1800172da  call    cs:__imp_SafeArrayUnaccessData
0x1800172e0  mov     [rbp+ppvData], 0
0x1800172e8  mov     [r15], rdi
0x1800172eb  xor     edi, edi
0x1800172ed  cmp     ebx, 8007000Eh
0x1800172f3  jz      loc_180017141
0x1800172f9  cmp     ebx, 80070057h
0x1800172ff  jz      loc_1800170F5
0x180017305  test    ebx, ebx
0x180017307  jz      short loc_18001732A
0x180017309  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017310  jz      loc_180017162
0x180017316  mov     r9d, ebx
0x180017319  lea     r8, aCdiagnosticxml_0; "CDiagnosticXmlParser::ReadXmlStringArra"...
0x180017320  call    McTemplateU0sq_EventWriteTransfer
0x180017325  jmp     loc_180017162
0x18001732a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180017331  jz      loc_180017162
0x180017337  lea     r8, aCdiagnosticxml_0; "CDiagnosticXmlParser::ReadXmlStringArra"...
0x18001733e  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180017345  call    McTemplateU0s_EventWriteTransfer
0x18001734a  jmp     loc_180017162
0x18001734f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180017356  jz      loc_18001715D
0x18001735c  mov     r9d, 80070057h
0x180017362  lea     r8, aCdiagnosticxml_0; "CDiagnosticXmlParser::ReadXmlStringArra"...
0x180017369  call    McTemplateU0sq_EventWriteTransfer
0x18001736e  jmp     loc_18001715D
```
