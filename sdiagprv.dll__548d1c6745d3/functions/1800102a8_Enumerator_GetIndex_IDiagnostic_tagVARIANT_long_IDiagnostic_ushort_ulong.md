# Enumerator::GetIndex<IDiagnostic>(tagVARIANT,long (IDiagnostic::*)(ushort * *),ulong *)

- ea: `0x1800102a8`
- end: `0x180010548`
- name: `??$GetIndex@UIDiagnostic@@@Enumerator@@IEAAJUtagVARIANT@@P8IDiagnostic@@EAAJPEAPEAG@ZPEAK@Z`
- size: `672`
- prototype: `__int64(char *, VARIANTARG *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010634`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800102a8`
- `0x180019010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001049a`
- `msvcrt!_wcsicmp` at `0x18001049a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001045c`
- `OLEAUT32!__imp_SysFreeString` at `0x180010516`
- `OLEAUT32!__imp_SysFreeString` at `0x18001045c`
- `OLEAUT32!__imp_SysFreeString` at `0x180010516`
- `OLEAUT32!__imp_SysStringLen` at `0x180010488`
- `OLEAUT32!__imp_SysStringLen` at `0x180010488`
- `OLEAUT32!__imp_VariantChangeType` at `0x180010390`
- `OLEAUT32!__imp_VariantChangeType` at `0x180010390`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001033d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001033d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180010503`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180010503`

## pseudocode

```c
__int64 Enumerator::GetIndex<IDiagnostic>(char *a1, VARIANTARG *a2, ...)
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
        v12 = (**v15)(v15, &GUID_140bfe8d_54ec_11dc_b924_001438c29fab, &v18);
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
0x1800102a8  mov     [rsp-40h+arg_18], r9
0x1800102ad  mov     [rsp-40h+bstrString], r8
0x1800102b2  push    rbp
0x1800102b3  push    rbx
0x1800102b4  push    rsi
0x1800102b5  push    rdi
0x1800102b6  push    r12
0x1800102b8  push    r13
0x1800102ba  push    r14
0x1800102bc  push    r15
0x1800102be  mov     rbp, rsp
0x1800102c1  sub     rsp, 28h
0x1800102c5  movzx   r8d, word ptr [rdx]
0x1800102c9  xor     r12d, r12d
0x1800102cc  mov     [rbp+bstrString], r12
0x1800102d0  mov     r13, r9
0x1800102d3  mov     [rbp+ppvData], r12
0x1800102d7  mov     r14, rdx
0x1800102da  mov     [rbp+arg_8], r12
0x1800102de  mov     r15, rcx
0x1800102e1  sub     r8d, 2
0x1800102e5  jz      short loc_18001031F
0x1800102e7  sub     r8d, 1
0x1800102eb  jz      short loc_18001031F
0x1800102ed  sub     r8d, 5
0x1800102f1  jz      short loc_180010311
0x1800102f3  sub     r8d, 1
0x1800102f7  jz      short loc_18001031F
0x1800102f9  sub     r8d, 7
0x1800102fd  jz      short loc_18001031F
0x1800102ff  sub     r8d, 1
0x180010303  jz      short loc_18001031F
0x180010305  sub     r8d, 1
0x180010309  jz      short loc_18001031F
0x18001030b  cmp     r8d, 1
0x18001030f  jz      short loc_18001031F
0x180010311  mov     edi, 80070057h
0x180010316  lea     rbx, [rcx+48h]
0x18001031a  jmp     loc_1800104C4
0x18001031f  lea     rbx, [rcx+48h]
0x180010323  mov     rcx, [rbx]; psa
0x180010326  test    rcx, rcx
0x180010329  jnz     short loc_180010335
0x18001032b  mov     edi, 80070490h
0x180010330  jmp     loc_1800104C4
0x180010335  mov     esi, [r15+54h]
0x180010339  lea     rdx, [rbp+ppvData]; ppvData
0x18001033d  call    cs:__imp_SafeArrayAccessData
0x180010343  mov     edi, eax
0x180010345  test    eax, eax
0x180010347  js      loc_1800104C0
0x18001034d  movzx   edx, word ptr [r14]
0x180010351  sub     edx, 2
0x180010354  jz      short loc_180010381
0x180010356  sub     edx, 1
0x180010359  jz      short loc_180010381
0x18001035b  sub     edx, 5
0x18001035e  jz      loc_1800103E9
0x180010364  sub     edx, 1
0x180010367  jz      short loc_1800103A9
0x180010369  sub     edx, 7
0x18001036c  jz      short loc_180010381
0x18001036e  sub     edx, 1
0x180010371  jz      short loc_180010381
0x180010373  sub     edx, 1
0x180010376  jz      short loc_180010381
0x180010378  cmp     edx, 1
0x18001037b  jnz     loc_1800104AF
0x180010381  mov     r9d, 13h; vt
0x180010387  xor     r8d, r8d; wFlags
0x18001038a  mov     rdx, r14; pvarSrc
0x18001038d  mov     rcx, r14; pvargDest
0x180010390  call    cs:__imp_VariantChangeType
0x180010396  mov     edi, eax
0x180010398  test    eax, eax
0x18001039a  js      loc_1800104C0
0x1800103a0  mov     esi, [r14+8]
0x1800103a4  jmp     loc_1800104AF
0x1800103a9  mov     esi, r12d
0x1800103ac  cmp     [r15+54h], r12d
0x1800103b0  jbe     loc_1800104AF
0x1800103b6  mov     r12d, 9
0x1800103bc  mov     rcx, [rbp+ppvData]
0x1800103c0  mov     eax, esi
0x1800103c2  lea     rax, [rax+rax*2]
0x1800103c6  cmp     r12w, [rcx+rax*8]
0x1800103cb  jnz     short loc_1800103DC
0x1800103cd  mov     rax, [rcx+rax*8+8]
0x1800103d2  cmp     [r14+8], rax
0x1800103d6  jz      loc_1800104AF
0x1800103dc  inc     esi
0x1800103de  cmp     esi, [r15+54h]
0x1800103e2  jb      short loc_1800103BC
0x1800103e4  jmp     loc_1800104AF
0x1800103e9  mov     esi, r12d
0x1800103ec  mov     r12d, 9
0x1800103f2  cmp     esi, [r15+54h]
0x1800103f6  jnb     loc_1800104AB
0x1800103fc  mov     eax, esi
0x1800103fe  lea     r13, [rax+rax*2]
0x180010402  mov     rax, [rbp+ppvData]
0x180010406  cmp     r12w, [rax+r13*8]
0x18001040b  jnz     loc_1800104A4
0x180010411  mov     rcx, [rbp+arg_8]
0x180010415  test    rcx, rcx
0x180010418  jz      short loc_18001042E
0x18001041a  mov     rax, [rcx]
0x18001041d  mov     rax, [rax+10h]
0x180010421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010426  mov     [rbp+arg_8], 0
0x18001042e  mov     rax, [rbp+ppvData]
0x180010432  lea     r8, [rbp+arg_8]
0x180010436  lea     rdx, _GUID_140bfe8d_54ec_11dc_b924_001438c29fab
0x18001043d  mov     rcx, [rax+r13*8+8]
0x180010442  mov     rax, [rcx]
0x180010445  mov     rax, [rax]
0x180010448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001044d  mov     edi, eax
0x18001044f  test    eax, eax
0x180010451  js      short loc_1800104A4
0x180010453  mov     rcx, [rbp+bstrString]; bstrString
0x180010457  test    rcx, rcx
0x18001045a  jz      short loc_18001046A
0x18001045c  call    cs:__imp_SysFreeString
0x180010462  mov     [rbp+bstrString], 0
0x18001046a  mov     rcx, [rbp+arg_8]
0x18001046e  lea     rdx, [rbp+bstrString]
0x180010472  xor     eax, eax
0x180010474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010479  mov     edi, eax
0x18001047b  test    eax, eax
0x18001047d  js      short loc_1800104A4
0x18001047f  mov     rcx, [rbp+bstrString]; pbstr
0x180010483  test    rcx, rcx
0x180010486  jz      short loc_1800104A4
0x180010488  call    cs:__imp_SysStringLen
0x18001048e  test    eax, eax
0x180010490  jz      short loc_1800104A4
0x180010492  mov     rdx, [r14+8]; String2
0x180010496  mov     rcx, [rbp+bstrString]; String1
0x18001049a  call    cs:__imp__wcsicmp
0x1800104a0  test    eax, eax
0x1800104a2  jz      short loc_1800104AB
0x1800104a4  inc     esi
0x1800104a6  jmp     loc_1800103F2
0x1800104ab  mov     r13, [rbp+arg_18]
0x1800104af  xor     r12d, r12d
0x1800104b2  cmp     esi, [r15+54h]
0x1800104b6  jnb     loc_18001032B
0x1800104bc  mov     [r13+0], esi
0x1800104c0  test    edi, edi
0x1800104c2  jz      short loc_1800104DE
0x1800104c4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800104cb  jz      short loc_1800104FA
0x1800104cd  mov     r9d, edi
0x1800104d0  lea     r8, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x1800104d7  call    McTemplateU0sq_EventWriteTransfer
0x1800104dc  jmp     short loc_1800104FA
0x1800104de  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800104e5  jz      short loc_1800104FA
0x1800104e7  lea     r8, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x1800104ee  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800104f5  call    McTemplateU0s_EventWriteTransfer
0x1800104fa  cmp     [rbp+ppvData], r12
0x1800104fe  jz      short loc_18001050D
0x180010500  mov     rcx, [rbx]; psa
0x180010503  call    cs:__imp_SafeArrayUnaccessData
0x180010509  mov     [rbp+ppvData], r12
0x18001050d  mov     rcx, [rbp+bstrString]; bstrString
0x180010511  test    rcx, rcx
0x180010514  jz      short loc_180010520
0x180010516  call    cs:__imp_SysFreeString
0x18001051c  mov     [rbp+bstrString], r12
0x180010520  mov     rcx, [rbp+arg_8]
0x180010524  test    rcx, rcx
0x180010527  jz      short loc_180010535
0x180010529  mov     rax, [rcx]
0x18001052c  mov     rax, [rax+10h]
0x180010530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010535  mov     eax, edi
0x180010537  add     rsp, 28h
0x18001053b  pop     r15
0x18001053d  pop     r14
0x18001053f  pop     r13
0x180010541  pop     r12
0x180010543  pop     rdi
0x180010544  pop     rsi
0x180010545  pop     rbx
0x180010546  pop     rbp
0x180010547  retn
```
