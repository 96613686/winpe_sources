# CAntiVirusManager::OnWbemSetCustomProperties(CExternalBase *,IWbemClassObject *)

- ea: `0x180036460`
- end: `0x180036689`
- name: `?OnWbemSetCustomProperties@CAntiVirusManager@@MEAAJPEAVCExternalBase@@PEAUIWbemClassObject@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(CAntiVirusManager *__hidden this, struct CExternalBase *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180008cc0`
- `0x180036460`
- `0x180042010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800364a0`
- `OLEAUT32!__imp_VariantInit` at `0x1800364a0`
- `OLEAUT32!__imp_VariantClear` at `0x1800364ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800365a5`
- `OLEAUT32!__imp_VariantClear` at `0x180036613`
- `OLEAUT32!__imp_VariantClear` at `0x180036669`
- `OLEAUT32!__imp_VariantClear` at `0x1800364ff`
- `OLEAUT32!__imp_VariantClear` at `0x1800365a5`
- `OLEAUT32!__imp_VariantClear` at `0x180036613`
- `OLEAUT32!__imp_VariantClear` at `0x180036669`

## string_xrefs

- `0x180036625`: `onAccessScanningEnabled`

## pseudocode

```c
__int64 __fastcall CAntiVirusManager::OnWbemSetCustomProperties(
        CAntiVirusManager *this,
        struct CExternalBase *a2,
        struct IWbemClassObject *a3)
{
  int v5; // edi
  int v6; // eax
  int v7; // r14d
  int v8; // eax
  __int64 v9; // r8
  __int64 v10; // rdx
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF

  if ( a2 && a3 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
           a3,
           L"productUptoDate",
           0,
           &pvarg,
           0,
           0);
    if ( v5 >= 0 )
    {
      if ( pvarg.vt == 1 || (v6 = 0, pvarg.iVal != -1) )
        v6 = 16;
      *((_DWORD *)a2 + 20) &= 0xFFFFFF0F;
      *((_DWORD *)a2 + 20) |= v6;
    }
    VariantClear(&pvarg);
    if ( v5 >= 0 )
    {
      v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
             a3,
             L"productHasNotifiedUser",
             0,
             &pvarg,
             0,
             0);
      if ( v5 >= 0 )
      {
        if ( pvarg.vt == 1 || (v7 = 0x10000, pvarg.iVal != -1) )
          v7 = 0;
        v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
               a3,
               L"productWantsWscNotifications",
               0,
               &pvarg,
               0,
               0);
        if ( v5 >= 0 )
        {
          if ( pvarg.vt == 1 || (v8 = 0x20000, pvarg.iVal != -1) )
            v8 = 0;
          *((_DWORD *)a2 + 20) &= 0xFFF0FFFF;
          *((_DWORD *)a2 + 20) |= v7 | v8;
        }
      }
    }
    VariantClear(&pvarg);
    if ( v5 < 0 )
      return (unsigned int)v5;
    v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
           a3,
           L"productState",
           0,
           &pvarg,
           0,
           0);
    if ( v5 < 0 || pvarg.vt == 1 )
    {
      VariantClear(&pvarg);
      v5 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3->lpVtbl->Get)(
             a3,
             L"onAccessScanningEnabled",
             0,
             &pvarg,
             0,
             0);
      if ( v5 < 0 )
      {
LABEL_34:
        VariantClear(&pvarg);
        return (unsigned int)v5;
      }
      if ( pvarg.vt == 1 || !pvarg.iVal )
        v10 = 0;
      else
        v10 = 4096;
    }
    else
    {
      v10 = 0;
      if ( pvarg.bVal == 1 )
        v10 = 4096;
      if ( pvarg.bVal == 3 )
        v10 = 0x4000;
      if ( pvarg.bVal == 2 )
        v10 = 0x2000;
    }
    CExternalBase::SetProductState(a2, v10, v9);
    goto LABEL_34;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180036460  push    rbp
0x180036462  push    rbx
0x180036463  push    rsi
0x180036464  push    rdi
0x180036465  push    r12
0x180036467  push    r13
0x180036469  push    r14
0x18003646b  push    r15
0x18003646d  mov     rbp, rsp
0x180036470  sub     rsp, 68h
0x180036474  xor     r15d, r15d
0x180036477  mov     rsi, r8
0x18003647a  mov     rbx, rdx
0x18003647d  test    rdx, rdx
0x180036480  jz      loc_180036673
0x180036486  test    r8, r8
0x180036489  jz      loc_180036673
0x18003648f  xorps   xmm0, xmm0
0x180036492  lea     rcx, [rbp+pvarg]; pvarg
0x180036496  xor     eax, eax
0x180036498  movups  xmmword ptr [rbp+pvarg], xmm0
0x18003649c  mov     qword ptr [rbp+pvarg+10h], rax
0x1800364a0  call    cs:__imp_VariantInit
0x1800364a6  mov     rax, [rsi]
0x1800364a9  lea     r9, [rbp+pvarg]
0x1800364ad  mov     [rsp+68h+var_40], r15
0x1800364b2  lea     rdx, aProductuptodat; "productUptoDate"
0x1800364b9  xor     r8d, r8d
0x1800364bc  mov     [rsp+68h+var_48], r15
0x1800364c1  mov     rcx, rsi
0x1800364c4  mov     rax, [rax+20h]
0x1800364c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364cd  or      r13d, 0FFFFFFFFh
0x1800364d1  lea     r12d, [r15+1]
0x1800364d5  mov     edi, eax
0x1800364d7  test    eax, eax
0x1800364d9  js      short loc_1800364FB
0x1800364db  cmp     r12w, word ptr [rbp+pvarg]
0x1800364e0  jz      short loc_1800364EC
0x1800364e2  mov     eax, r15d
0x1800364e5  cmp     r13w, word ptr [rbp+pvarg+8]
0x1800364ea  jz      short loc_1800364F1
0x1800364ec  mov     eax, 10h
0x1800364f1  and     dword ptr [rbx+50h], 0FFFFFF0Fh
0x1800364f8  or      [rbx+50h], eax
0x1800364fb  lea     rcx, [rbp+pvarg]; pvarg
0x1800364ff  call    cs:__imp_VariantClear
0x180036505  test    edi, edi
0x180036507  js      loc_1800365A1
0x18003650d  mov     rax, [rsi]
0x180036510  lea     r9, [rbp+pvarg]
0x180036514  mov     [rsp+68h+var_40], r15
0x180036519  lea     rdx, aProducthasnoti; "productHasNotifiedUser"
0x180036520  xor     r8d, r8d
0x180036523  mov     [rsp+68h+var_48], r15
0x180036528  mov     rcx, rsi
0x18003652b  mov     rax, [rax+20h]
0x18003652f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036534  mov     edi, eax
0x180036536  test    eax, eax
0x180036538  js      short loc_1800365A1
0x18003653a  cmp     r12w, word ptr [rbp+pvarg]
0x18003653f  jz      short loc_18003654E
0x180036541  mov     r14d, 10000h
0x180036547  cmp     r13w, word ptr [rbp+pvarg+8]
0x18003654c  jz      short loc_180036551
0x18003654e  mov     r14d, r15d
0x180036551  mov     rax, [rsi]
0x180036554  lea     r9, [rbp+pvarg]
0x180036558  mov     [rsp+68h+var_40], r15
0x18003655d  lea     rdx, aProductwantsws; "productWantsWscNotifications"
0x180036564  xor     r8d, r8d
0x180036567  mov     [rsp+68h+var_48], r15
0x18003656c  mov     rcx, rsi
0x18003656f  mov     rax, [rax+20h]
0x180036573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036578  mov     edi, eax
0x18003657a  test    eax, eax
0x18003657c  js      short loc_1800365A1
0x18003657e  cmp     r12w, word ptr [rbp+pvarg]
0x180036583  jz      short loc_180036591
0x180036585  mov     eax, 20000h
0x18003658a  cmp     r13w, word ptr [rbp+pvarg+8]
0x18003658f  jz      short loc_180036594
0x180036591  mov     eax, r15d
0x180036594  and     dword ptr [rbx+50h], 0FFF0FFFFh
0x18003659b  or      eax, r14d
0x18003659e  or      [rbx+50h], eax
0x1800365a1  lea     rcx, [rbp+pvarg]; pvarg
0x1800365a5  call    cs:__imp_VariantClear
0x1800365ab  test    edi, edi
0x1800365ad  js      loc_18003666F
0x1800365b3  mov     rax, [rsi]
0x1800365b6  lea     r9, [rbp+pvarg]
0x1800365ba  mov     [rsp+68h+var_40], r15
0x1800365bf  lea     rdx, aProductstate; "productState"
0x1800365c6  xor     r8d, r8d
0x1800365c9  mov     [rsp+68h+var_48], r15
0x1800365ce  mov     rcx, rsi
0x1800365d1  mov     rax, [rax+20h]
0x1800365d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365da  mov     edi, eax
0x1800365dc  test    eax, eax
0x1800365de  js      short loc_18003660F
0x1800365e0  cmp     word ptr [rbp+pvarg], r12w
0x1800365e5  jz      short loc_18003660F
0x1800365e7  movzx   eax, word ptr [rbp+pvarg+8]
0x1800365eb  mov     ecx, 1000h
0x1800365f0  cmp     al, r12b
0x1800365f3  mov     edx, r15d
0x1800365f6  cmovz   edx, ecx
0x1800365f9  cmp     al, 3
0x1800365fb  mov     ecx, 4000h
0x180036600  cmovz   edx, ecx
0x180036603  cmp     al, 2
0x180036605  mov     ecx, 2000h
0x18003660a  cmovz   edx, ecx
0x18003660d  jmp     short loc_18003665D
0x18003660f  lea     rcx, [rbp+pvarg]; pvarg
0x180036613  call    cs:__imp_VariantClear
0x180036619  mov     rax, [rsi]
0x18003661c  lea     r9, [rbp+pvarg]
0x180036620  mov     [rsp+68h+var_40], r15
0x180036625  lea     rdx, aOnaccessscanni; "onAccessScanningEnabled"
0x18003662c  xor     r8d, r8d
0x18003662f  mov     [rsp+68h+var_48], r15
0x180036634  mov     rcx, rsi
0x180036637  mov     rax, [rax+20h]
0x18003663b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036640  mov     edi, eax
0x180036642  test    eax, eax
0x180036644  js      short loc_180036665
0x180036646  cmp     word ptr [rbp+pvarg], r12w
0x18003664b  jz      short loc_18003665B
0x18003664d  cmp     word ptr [rbp+pvarg+8], r15w
0x180036652  jz      short loc_18003665B
0x180036654  mov     edx, 1000h
0x180036659  jmp     short loc_18003665D
0x18003665b  xor     edx, edx
0x18003665d  mov     rcx, rbx
0x180036660  call    ?SetProductState@CExternalBase@@QEAAHW4ProductState@@@Z; CExternalBase::SetProductState(ProductState)
0x180036665  lea     rcx, [rbp+pvarg]; pvarg
0x180036669  call    cs:__imp_VariantClear
0x18003666f  mov     eax, edi
0x180036671  jmp     short loc_180036678
0x180036673  mov     eax, 80070057h
0x180036678  add     rsp, 68h
0x18003667c  pop     r15
0x18003667e  pop     r14
0x180036680  pop     r13
0x180036682  pop     r12
0x180036684  pop     rdi
0x180036685  pop     rsi
0x180036686  pop     rbx
0x180036687  pop     rbp
0x180036688  retn
```
