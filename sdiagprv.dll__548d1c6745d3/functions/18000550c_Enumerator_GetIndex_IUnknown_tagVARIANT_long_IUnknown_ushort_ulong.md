# Enumerator::GetIndex<IUnknown>(tagVARIANT,long (IUnknown::*)(ushort * *),ulong *)

- ea: `0x18000550c`
- end: `0x1800057ac`
- name: `??$GetIndex@UIUnknown@@@Enumerator@@IEAAJUtagVARIANT@@P8IUnknown@@EAAJPEAPEAG@ZPEAK@Z`
- size: `672`
- prototype: `__int64(char *, VARIANTARG *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800057b4`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x18000550c`
- `0x180019010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800056fe`
- `msvcrt!_wcsicmp` at `0x1800056fe`
- `OLEAUT32!__imp_SysFreeString` at `0x1800056c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000577a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800056c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000577a`
- `OLEAUT32!__imp_SysStringLen` at `0x1800056ec`
- `OLEAUT32!__imp_SysStringLen` at `0x1800056ec`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800055f4`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800055f4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800055a1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800055a1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005767`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005767`

## pseudocode

```c
__int64 Enumerator::GetIndex<IUnknown>(char *a1, VARIANTARG *a2, ...)
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
        v12 = (**v15)(v15, &GUID_00000000_0000_0000_c000_000000000046, &v18);
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
0x18000550c  mov     [rsp-40h+arg_18], r9
0x180005511  mov     [rsp-40h+bstrString], r8
0x180005516  push    rbp
0x180005517  push    rbx
0x180005518  push    rsi
0x180005519  push    rdi
0x18000551a  push    r12
0x18000551c  push    r13
0x18000551e  push    r14
0x180005520  push    r15
0x180005522  mov     rbp, rsp
0x180005525  sub     rsp, 28h
0x180005529  movzx   r8d, word ptr [rdx]
0x18000552d  xor     r12d, r12d
0x180005530  mov     [rbp+bstrString], r12
0x180005534  mov     r13, r9
0x180005537  mov     [rbp+ppvData], r12
0x18000553b  mov     r14, rdx
0x18000553e  mov     [rbp+arg_8], r12
0x180005542  mov     r15, rcx
0x180005545  sub     r8d, 2
0x180005549  jz      short loc_180005583
0x18000554b  sub     r8d, 1
0x18000554f  jz      short loc_180005583
0x180005551  sub     r8d, 5
0x180005555  jz      short loc_180005575
0x180005557  sub     r8d, 1
0x18000555b  jz      short loc_180005583
0x18000555d  sub     r8d, 7
0x180005561  jz      short loc_180005583
0x180005563  sub     r8d, 1
0x180005567  jz      short loc_180005583
0x180005569  sub     r8d, 1
0x18000556d  jz      short loc_180005583
0x18000556f  cmp     r8d, 1
0x180005573  jz      short loc_180005583
0x180005575  mov     edi, 80070057h
0x18000557a  lea     rbx, [rcx+48h]
0x18000557e  jmp     loc_180005728
0x180005583  lea     rbx, [rcx+48h]
0x180005587  mov     rcx, [rbx]; psa
0x18000558a  test    rcx, rcx
0x18000558d  jnz     short loc_180005599
0x18000558f  mov     edi, 80070490h
0x180005594  jmp     loc_180005728
0x180005599  mov     esi, [r15+54h]
0x18000559d  lea     rdx, [rbp+ppvData]; ppvData
0x1800055a1  call    cs:__imp_SafeArrayAccessData
0x1800055a7  mov     edi, eax
0x1800055a9  test    eax, eax
0x1800055ab  js      loc_180005724
0x1800055b1  movzx   edx, word ptr [r14]
0x1800055b5  sub     edx, 2
0x1800055b8  jz      short loc_1800055E5
0x1800055ba  sub     edx, 1
0x1800055bd  jz      short loc_1800055E5
0x1800055bf  sub     edx, 5
0x1800055c2  jz      loc_18000564D
0x1800055c8  sub     edx, 1
0x1800055cb  jz      short loc_18000560D
0x1800055cd  sub     edx, 7
0x1800055d0  jz      short loc_1800055E5
0x1800055d2  sub     edx, 1
0x1800055d5  jz      short loc_1800055E5
0x1800055d7  sub     edx, 1
0x1800055da  jz      short loc_1800055E5
0x1800055dc  cmp     edx, 1
0x1800055df  jnz     loc_180005713
0x1800055e5  mov     r9d, 13h; vt
0x1800055eb  xor     r8d, r8d; wFlags
0x1800055ee  mov     rdx, r14; pvarSrc
0x1800055f1  mov     rcx, r14; pvargDest
0x1800055f4  call    cs:__imp_VariantChangeType
0x1800055fa  mov     edi, eax
0x1800055fc  test    eax, eax
0x1800055fe  js      loc_180005724
0x180005604  mov     esi, [r14+8]
0x180005608  jmp     loc_180005713
0x18000560d  mov     esi, r12d
0x180005610  cmp     [r15+54h], r12d
0x180005614  jbe     loc_180005713
0x18000561a  mov     r12d, 9
0x180005620  mov     rcx, [rbp+ppvData]
0x180005624  mov     eax, esi
0x180005626  lea     rax, [rax+rax*2]
0x18000562a  cmp     r12w, [rcx+rax*8]
0x18000562f  jnz     short loc_180005640
0x180005631  mov     rax, [rcx+rax*8+8]
0x180005636  cmp     [r14+8], rax
0x18000563a  jz      loc_180005713
0x180005640  inc     esi
0x180005642  cmp     esi, [r15+54h]
0x180005646  jb      short loc_180005620
0x180005648  jmp     loc_180005713
0x18000564d  mov     esi, r12d
0x180005650  mov     r12d, 9
0x180005656  cmp     esi, [r15+54h]
0x18000565a  jnb     loc_18000570F
0x180005660  mov     eax, esi
0x180005662  lea     r13, [rax+rax*2]
0x180005666  mov     rax, [rbp+ppvData]
0x18000566a  cmp     r12w, [rax+r13*8]
0x18000566f  jnz     loc_180005708
0x180005675  mov     rcx, [rbp+arg_8]
0x180005679  test    rcx, rcx
0x18000567c  jz      short loc_180005692
0x18000567e  mov     rax, [rcx]
0x180005681  mov     rax, [rax+10h]
0x180005685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568a  mov     [rbp+arg_8], 0
0x180005692  mov     rax, [rbp+ppvData]
0x180005696  lea     r8, [rbp+arg_8]
0x18000569a  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800056a1  mov     rcx, [rax+r13*8+8]
0x1800056a6  mov     rax, [rcx]
0x1800056a9  mov     rax, [rax]
0x1800056ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b1  mov     edi, eax
0x1800056b3  test    eax, eax
0x1800056b5  js      short loc_180005708
0x1800056b7  mov     rcx, [rbp+bstrString]; bstrString
0x1800056bb  test    rcx, rcx
0x1800056be  jz      short loc_1800056CE
0x1800056c0  call    cs:__imp_SysFreeString
0x1800056c6  mov     [rbp+bstrString], 0
0x1800056ce  mov     rcx, [rbp+arg_8]
0x1800056d2  lea     rdx, [rbp+bstrString]
0x1800056d6  xor     eax, eax
0x1800056d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056dd  mov     edi, eax
0x1800056df  test    eax, eax
0x1800056e1  js      short loc_180005708
0x1800056e3  mov     rcx, [rbp+bstrString]; pbstr
0x1800056e7  test    rcx, rcx
0x1800056ea  jz      short loc_180005708
0x1800056ec  call    cs:__imp_SysStringLen
0x1800056f2  test    eax, eax
0x1800056f4  jz      short loc_180005708
0x1800056f6  mov     rdx, [r14+8]; String2
0x1800056fa  mov     rcx, [rbp+bstrString]; String1
0x1800056fe  call    cs:__imp__wcsicmp
0x180005704  test    eax, eax
0x180005706  jz      short loc_18000570F
0x180005708  inc     esi
0x18000570a  jmp     loc_180005656
0x18000570f  mov     r13, [rbp+arg_18]
0x180005713  xor     r12d, r12d
0x180005716  cmp     esi, [r15+54h]
0x18000571a  jnb     loc_18000558F
0x180005720  mov     [r13+0], esi
0x180005724  test    edi, edi
0x180005726  jz      short loc_180005742
0x180005728  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000572f  jz      short loc_18000575E
0x180005731  mov     r9d, edi
0x180005734  lea     r8, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x18000573b  call    McTemplateU0sq_EventWriteTransfer
0x180005740  jmp     short loc_18000575E
0x180005742  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180005749  jz      short loc_18000575E
0x18000574b  lea     r8, aEnumeratorGeti_0; "Enumerator::GetIndex"
0x180005752  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180005759  call    McTemplateU0s_EventWriteTransfer
0x18000575e  cmp     [rbp+ppvData], r12
0x180005762  jz      short loc_180005771
0x180005764  mov     rcx, [rbx]; psa
0x180005767  call    cs:__imp_SafeArrayUnaccessData
0x18000576d  mov     [rbp+ppvData], r12
0x180005771  mov     rcx, [rbp+bstrString]; bstrString
0x180005775  test    rcx, rcx
0x180005778  jz      short loc_180005784
0x18000577a  call    cs:__imp_SysFreeString
0x180005780  mov     [rbp+bstrString], r12
0x180005784  mov     rcx, [rbp+arg_8]
0x180005788  test    rcx, rcx
0x18000578b  jz      short loc_180005799
0x18000578d  mov     rax, [rcx]
0x180005790  mov     rax, [rax+10h]
0x180005794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005799  mov     eax, edi
0x18000579b  add     rsp, 28h
0x18000579f  pop     r15
0x1800057a1  pop     r14
0x1800057a3  pop     r13
0x1800057a5  pop     r12
0x1800057a7  pop     rdi
0x1800057a8  pop     rsi
0x1800057a9  pop     rbx
0x1800057aa  pop     rbp
0x1800057ab  retn
```
