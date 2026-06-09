# Enumerator::GetIndex<IDiagnosticMetadata>(tagVARIANT,long (IDiagnosticMetadata::*)(ushort * *),ulong *)

- ea: `0x18000401c`
- end: `0x1800042bc`
- name: `??$GetIndex@UIDiagnosticMetadata@@@Enumerator@@IEAAJUtagVARIANT@@P8IDiagnosticMetadata@@EAAJPEAPEAG@ZPEAK@Z`
- size: `672`
- prototype: `__int64(char *, VARIANTARG *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800043a8`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x18000401c`
- `0x180019010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000420e`
- `msvcrt!_wcsicmp` at `0x18000420e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000428a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000428a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800041fc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800041fc`
- `OLEAUT32!__imp_VariantChangeType` at `0x180004104`
- `OLEAUT32!__imp_VariantChangeType` at `0x180004104`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800040b1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800040b1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180004277`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180004277`

## pseudocode

```c
__int64 Enumerator::GetIndex<IDiagnosticMetadata>(char *a1, VARIANTARG *a2, ...)
{
  int vt; // r8d
  unsigned int *v3; // r13
  VARIANTARG *v4; // r14
  char *v5; // r15
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  HRESULT v12; // edi
  SAFEARRAY **v13; // rbx
  unsigned int i; // esi
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rcx
  void *ppvData; // [rsp+70h] [rbp+48h] BYREF
  __int64 v18; // [rsp+78h] [rbp+50h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+58h] BYREF
  va_list bstrStringa; // [rsp+80h] [rbp+58h]
  unsigned int *v21; // [rsp+88h] [rbp+60h]
  va_list va1; // [rsp+90h] [rbp+68h] BYREF

  va_start(va1, a2);
  va_start(bstrStringa, a2);
  bstrString = va_arg(va1, BSTR);
  v21 = va_arg(va1, unsigned int *);
  vt = a2->vt;
  bstrString = 0;
  v3 = v21;
  ppvData = 0;
  v4 = a2;
  v18 = 0;
  v5 = a1;
  v6 = vt - 2;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 5;
      if ( !v8 || (v9 = v8 - 1) != 0 && (v10 = v9 - 7) != 0 && (v11 = v10 - 1) != 0 && (unsigned int)(v11 - 1) >= 2 )
      {
        v12 = -2147024809;
        v13 = (SAFEARRAY **)(a1 + 72);
        goto LABEL_43;
      }
    }
  }
  v13 = (SAFEARRAY **)(a1 + 72);
  a1 = (char *)*((_QWORD *)a1 + 9);
  if ( !a1 )
    goto LABEL_10;
  i = *((_DWORD *)v5 + 21);
  v12 = SafeArrayAccessData((SAFEARRAY *)a1, &ppvData);
  if ( v12 < 0 )
    goto LABEL_42;
  if ( v4->vt == 2 || v4->vt == 3 )
    goto LABEL_19;
  a2 = (VARIANTARG *)((unsigned int)v4->vt - 8);
  if ( v4->vt == 8 )
  {
    for ( i = 0; i < *((_DWORD *)v5 + 21); ++i )
    {
      if ( *((_WORD *)ppvData + 12 * i) == 9 )
      {
        if ( v18 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v18 = 0;
        }
        v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)ppvData + 3 * i + 1);
        v12 = (**v15)(v15, &GUID_140bfe8b_54ec_11dc_b924_001438c29fab, &v18);
        if ( v12 >= 0 )
        {
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          v12 = MEMORY[0](v18, (BSTR *)bstrStringa);
          if ( v12 >= 0 )
          {
            a1 = (char *)bstrString;
            if ( bstrString )
            {
              if ( SysStringLen(bstrString) && !_wcsicmp(bstrString, v4->bstrVal) )
                break;
            }
          }
        }
      }
    }
    v3 = v21;
  }
  else
  {
    a2 = (VARIANTARG *)((unsigned int)v4->vt - 9);
    if ( v4->vt == 9 )
    {
      for ( i = 0; i < *((_DWORD *)v5 + 21); ++i )
      {
        a1 = (char *)ppvData;
        if ( *((_WORD *)ppvData + 12 * i) == 9 && v4->llVal == *((_QWORD *)ppvData + 3 * i + 1) )
          break;
      }
    }
    else if ( v4->vt == 16 || v4->vt == 17 || (a2 = (VARIANTARG *)((unsigned int)v4->vt - 18), (unsigned int)a2 <= 1) )
    {
LABEL_19:
      v12 = VariantChangeType(v4, v4, 0, 0x13u);
      if ( v12 < 0 )
        goto LABEL_42;
      i = v4->cyVal.Lo;
    }
  }
  if ( i >= *((_DWORD *)v5 + 21) )
  {
LABEL_10:
    v12 = -2147023728;
    goto LABEL_43;
  }
  *v3 = i;
LABEL_42:
  if ( v12 )
  {
LABEL_43:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(a1, a2, "Enumerator::GetIndex", (unsigned int)v12);
    goto LABEL_47;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(a1, SDIAGPRV_EVENT_DEBUG_SUCCESS, "Enumerator::GetIndex");
LABEL_47:
  if ( ppvData )
  {
    SafeArrayUnaccessData(*v13);
    ppvData = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000401c  mov     [rsp-40h+arg_18], r9
0x180004021  mov     [rsp-40h+bstrString], r8
0x180004026  push    rbp
0x180004027  push    rbx
0x180004028  push    rsi
0x180004029  push    rdi
0x18000402a  push    r12
0x18000402c  push    r13
0x18000402e  push    r14
0x180004030  push    r15
0x180004032  mov     rbp, rsp
0x180004035  sub     rsp, 28h
0x180004039  movzx   r8d, word ptr [rdx]
0x18000403d  xor     r12d, r12d
0x180004040  mov     [rbp+bstrString], r12
0x180004044  mov     r13, r9
0x180004047  mov     [rbp+ppvData], r12
0x18000404b  mov     r14, rdx
0x18000404e  mov     [rbp+arg_8], r12
0x180004052  mov     r15, rcx
0x180004055  sub     r8d, 2
0x180004059  jz      short loc_180004093
0x18000405b  sub     r8d, 1
0x18000405f  jz      short loc_180004093
0x180004061  sub     r8d, 5
0x180004065  jz      short loc_180004085
0x180004067  sub     r8d, 1
0x18000406b  jz      short loc_180004093
0x18000406d  sub     r8d, 7
0x180004071  jz      short loc_180004093
0x180004073  sub     r8d, 1
0x180004077  jz      short loc_180004093
0x180004079  sub     r8d, 1
0x18000407d  jz      short loc_180004093
0x18000407f  cmp     r8d, 1
0x180004083  jz      short loc_180004093
0x180004085  mov     edi, 80070057h
0x18000408a  lea     rbx, [rcx+48h]
0x18000408e  jmp     loc_180004238
0x180004093  lea     rbx, [rcx+48h]
0x180004097  mov     rcx, [rbx]; psa
0x18000409a  test    rcx, rcx
0x18000409d  jnz     short loc_1800040A9
0x18000409f  mov     edi, 80070490h
0x1800040a4  jmp     loc_180004238
0x1800040a9  mov     esi, [r15+54h]
0x1800040ad  lea     rdx, [rbp+ppvData]; ppvData
0x1800040b1  call    cs:__imp_SafeArrayAccessData
0x1800040b7  mov     edi, eax
0x1800040b9  test    eax, eax
0x1800040bb  js      loc_180004234
0x1800040c1  movzx   edx, word ptr [r14]
0x1800040c5  sub     edx, 2
0x1800040c8  jz      short loc_1800040F5
0x1800040ca  sub     edx, 1
0x1800040cd  jz      short loc_1800040F5
0x1800040cf  sub     edx, 5
0x1800040d2  jz      loc_18000415D
0x1800040d8  sub     edx, 1
0x1800040db  jz      short loc_18000411D
0x1800040dd  sub     edx, 7
0x1800040e0  jz      short loc_1800040F5
0x1800040e2  sub     edx, 1
0x1800040e5  jz      short loc_1800040F5
0x1800040e7  sub     edx, 1
0x1800040ea  jz      short loc_1800040F5
0x1800040ec  cmp     edx, 1
0x1800040ef  jnz     loc_180004223
0x1800040f5  mov     r9d, 13h; vt
0x1800040fb  xor     r8d, r8d; wFlags
0x1800040fe  mov     rdx, r14; pvarSrc
0x180004101  mov     rcx, r14; pvargDest
0x180004104  call    cs:__imp_VariantChangeType
0x18000410a  mov     edi, eax
0x18000410c  test    eax, eax
0x18000410e  js      loc_180004234
0x180004114  mov     esi, [r14+8]
0x180004118  jmp     loc_180004223
0x18000411d  mov     esi, r12d
0x180004120  cmp     [r15+54h], r12d
0x180004124  jbe     loc_180004223
0x18000412a  mov     r12d, 9
0x180004130  mov     rcx, [rbp+ppvData]
0x180004134  mov     eax, esi
0x180004136  lea     rax, [rax+rax*2]
0x18000413a  cmp     r12w, [rcx+rax*8]
0x18000413f  jnz     short loc_180004150
0x180004141  mov     rax, [rcx+rax*8+8]
0x180004146  cmp     [r14+8], rax
0x18000414a  jz      loc_180004223
0x180004150  inc     esi
0x180004152  cmp     esi, [r15+54h]
0x180004156  jb      short loc_180004130
0x180004158  jmp     loc_180004223
0x18000415d  mov     esi, r12d
0x180004160  mov     r12d, 9
0x180004166  cmp     esi, [r15+54h]
0x18000416a  jnb     loc_18000421F
0x180004170  mov     eax, esi
0x180004172  lea     r13, [rax+rax*2]
0x180004176  mov     rax, [rbp+ppvData]
0x18000417a  cmp     r12w, [rax+r13*8]
0x18000417f  jnz     loc_180004218
0x180004185  mov     rcx, [rbp+arg_8]
0x180004189  test    rcx, rcx
0x18000418c  jz      short loc_1800041A2
0x18000418e  mov     rax, [rcx]
0x180004191  mov     rax, [rax+10h]
0x180004195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000419a  mov     [rbp+arg_8], 0
0x1800041a2  mov     rax, [rbp+ppvData]
0x1800041a6  lea     r8, [rbp+arg_8]
0x1800041aa  lea     rdx, _GUID_140bfe8b_54ec_11dc_b924_001438c29fab
0x1800041b1  mov     rcx, [rax+r13*8+8]
0x1800041b6  mov     rax, [rcx]
0x1800041b9  mov     rax, [rax]
0x1800041bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c1  mov     edi, eax
0x1800041c3  test    eax, eax
0x1800041c5  js      short loc_180004218
0x1800041c7  mov     rcx, [rbp+bstrString]; bstrString
0x1800041cb  test    rcx, rcx
0x1800041ce  jz      short loc_1800041DE
0x1800041d0  call    cs:__imp_SysFreeString
0x1800041d6  mov     [rbp+bstrString], 0
0x1800041de  mov     rcx, [rbp+arg_8]
0x1800041e2  lea     rdx, [rbp+bstrString]
0x1800041e6  xor     eax, eax
0x1800041e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ed  mov     edi, eax
0x1800041ef  test    eax, eax
0x1800041f1  js      short loc_180004218
0x1800041f3  mov     rcx, [rbp+bstrString]; pbstr
0x1800041f7  test    rcx, rcx
0x1800041fa  jz      short loc_180004218
0x1800041fc  call    cs:__imp_SysStringLen
0x180004202  test    eax, eax
0x180004204  jz      short loc_180004218
0x180004206  mov     rdx, [r14+8]; String2
0x18000420a  mov     rcx, [rbp+bstrString]; String1
0x18000420e  call    cs:__imp__wcsicmp
0x180004214  test    eax, eax
0x180004216  jz      short loc_18000421F
0x180004218  inc     esi
0x18000421a  jmp     loc_180004166
0x18000421f  mov     r13, [rbp+arg_18]
0x180004223  xor     r12d, r12d
0x180004226  cmp     esi, [r15+54h]
0x18000422a  jnb     loc_18000409F
0x180004230  mov     [r13+0], esi
0x180004234  test    edi, edi
0x180004236  jz      short loc_180004252
0x180004238  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000423f  jz      short loc_18000426E
0x180004241  mov     r9d, edi
0x180004244  lea     r8, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x18000424b  call    McTemplateU0sq_EventWriteTransfer
0x180004250  jmp     short loc_18000426E
0x180004252  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180004259  jz      short loc_18000426E
0x18000425b  lea     r8, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x180004262  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180004269  call    McTemplateU0s_EventWriteTransfer
0x18000426e  cmp     [rbp+ppvData], r12
0x180004272  jz      short loc_180004281
0x180004274  mov     rcx, [rbx]; psa
0x180004277  call    cs:__imp_SafeArrayUnaccessData
0x18000427d  mov     [rbp+ppvData], r12
0x180004281  mov     rcx, [rbp+bstrString]; bstrString
0x180004285  test    rcx, rcx
0x180004288  jz      short loc_180004294
0x18000428a  call    cs:__imp_SysFreeString
0x180004290  mov     [rbp+bstrString], r12
0x180004294  mov     rcx, [rbp+arg_8]
0x180004298  test    rcx, rcx
0x18000429b  jz      short loc_1800042A9
0x18000429d  mov     rax, [rcx]
0x1800042a0  mov     rax, [rax+10h]
0x1800042a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a9  mov     eax, edi
0x1800042ab  add     rsp, 28h
0x1800042af  pop     r15
0x1800042b1  pop     r14
0x1800042b3  pop     r13
0x1800042b5  pop     r12
0x1800042b7  pop     rdi
0x1800042b8  pop     rsi
0x1800042b9  pop     rbx
0x1800042ba  pop     rbp
0x1800042bb  retn
```
