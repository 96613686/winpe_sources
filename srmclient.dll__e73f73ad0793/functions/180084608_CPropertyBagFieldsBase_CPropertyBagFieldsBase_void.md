# CPropertyBagFieldsBase::~CPropertyBagFieldsBase(void)

- ea: `0x180084608`
- end: `0x18008476b`
- name: `??1CPropertyBagFieldsBase@@MEAA@XZ`
- size: `355`
- prototype: `void __fastcall(CPropertyBagFieldsBase *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18004d7b8`
- `0x180084780`
- `0x1800c0ef3`

## callees

- `0x180084608`
- `0x180084e28`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180084634`
- `ole32!CoTaskMemFree` at `0x180084642`
- `ole32!CoTaskMemFree` at `0x180084650`
- `ole32!CoTaskMemFree` at `0x18008465e`
- `ole32!CoTaskMemFree` at `0x18008466c`
- `ole32!CoTaskMemFree` at `0x18008467a`
- `ole32!CoTaskMemFree` at `0x180084684`
- `ole32!CoTaskMemFree` at `0x1800846ae`
- `ole32!CoTaskMemFree` at `0x1800846c2`
- `ole32!CoTaskMemFree` at `0x180084712`
- `ole32!CoTaskMemFree` at `0x18008471c`
- `ole32!CoTaskMemFree` at `0x180084733`
- `ole32!CoTaskMemFree` at `0x18008474a`
- `ole32!CoTaskMemFree` at `0x180084634`
- `ole32!CoTaskMemFree` at `0x180084642`
- `ole32!CoTaskMemFree` at `0x180084650`
- `ole32!CoTaskMemFree` at `0x18008465e`
- `ole32!CoTaskMemFree` at `0x18008466c`
- `ole32!CoTaskMemFree` at `0x18008467a`
- `ole32!CoTaskMemFree` at `0x180084684`
- `ole32!CoTaskMemFree` at `0x1800846ae`
- `ole32!CoTaskMemFree` at `0x1800846c2`
- `ole32!CoTaskMemFree` at `0x180084712`
- `ole32!CoTaskMemFree` at `0x18008471c`
- `ole32!CoTaskMemFree` at `0x180084733`
- `ole32!CoTaskMemFree` at `0x18008474a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800846e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800846ed`
- `OLEAUT32!__imp_SysFreeString` at `0x1800846e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800846ed`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800846fd`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800846fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
void __fastcall CPropertyBagFieldsBase::~CPropertyBagFieldsBase(CPropertyBagFieldsBase *this)
{
  LPVOID *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rcx
  unsigned int v6; // ebp
  __int64 v7; // rdi
  __int64 v8; // rbx
  SAFEARRAY *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  *(_QWORD *)this = &CPropertyBagFieldsBase::`vftable';
  if ( !*((_BYTE *)this + 56) )
  {
    v2 = (LPVOID *)*((_QWORD *)this + 1);
    if ( v2 )
    {
      CoTaskMemFree(*v2);
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 1) + 8LL));
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 1) + 16LL));
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 1) + 24LL));
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 1) + 32LL));
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 1) + 40LL));
      CoTaskMemFree(*((LPVOID *)this + 1));
      *((_QWORD *)this + 1) = 0;
    }
    v3 = *((_QWORD *)this + 2);
    if ( v3 )
    {
      if ( *(_DWORD *)v3 )
      {
        v4 = 0;
        do
        {
          CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(v3 + 8) + 8 * v4));
          v4 = (unsigned int)(v4 + 1);
          v3 = *((_QWORD *)this + 2);
        }
        while ( (unsigned int)v4 < *(_DWORD *)v3 );
      }
      CoTaskMemFree(*(LPVOID *)(v3 + 8));
      v5 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v5 + 16) )
      {
        v6 = 0;
        do
        {
          v7 = 32LL * v6;
          v8 = *(_QWORD *)(v5 + 24);
          SysFreeString(*(BSTR *)(v7 + v8));
          SysFreeString(*(BSTR *)(v7 + v8 + 8));
          v9 = *(SAFEARRAY **)(v7 + v8 + 16);
          if ( v9 )
            SafeArrayDestroy(v9);
          ++v6;
          v5 = *((_QWORD *)this + 2);
        }
        while ( v6 < *(_DWORD *)(v5 + 16) );
      }
      CoTaskMemFree(*(LPVOID *)(v5 + 24));
      CoTaskMemFree(*((LPVOID *)this + 2));
      *((_QWORD *)this + 2) = 0;
    }
    v10 = (void *)*((_QWORD *)this + 3);
    if ( v10 )
    {
      CoTaskMemFree(v10);
      *((_QWORD *)this + 3) = 0;
    }
    v11 = (void *)*((_QWORD *)this + 4);
    if ( v11 )
    {
      CoTaskMemFree(v11);
      *((_QWORD *)this + 4) = 0;
    }
    CPropertyBagFieldsBase::ClearInFileSecureProperties((struct _FSRM_IN_FILE_SECURE_PROPERTIES **)this + 5);
  }
}

```

## disassembly

```asm
0x180084608  push    rbx
0x18008460a  push    rbp
0x18008460b  push    rsi
0x18008460c  push    rdi
0x18008460d  sub     rsp, 28h
0x180084611  mov     rsi, rcx
0x180084614  lea     rax, ??_7CPropertyBagFieldsBase@@6B@; const CPropertyBagFieldsBase::`vftable'
0x18008461b  mov     [rcx], rax
0x18008461e  cmp     byte ptr [rcx+38h], 0
0x180084622  jnz     loc_180084762
0x180084628  mov     rcx, [rcx+8]
0x18008462c  test    rcx, rcx
0x18008462f  jz      short loc_180084692
0x180084631  mov     rcx, [rcx]; pv
0x180084634  call    cs:__imp_CoTaskMemFree
0x18008463a  mov     rcx, [rsi+8]
0x18008463e  mov     rcx, [rcx+8]; pv
0x180084642  call    cs:__imp_CoTaskMemFree
0x180084648  mov     rcx, [rsi+8]
0x18008464c  mov     rcx, [rcx+10h]; pv
0x180084650  call    cs:__imp_CoTaskMemFree
0x180084656  mov     rcx, [rsi+8]
0x18008465a  mov     rcx, [rcx+18h]; pv
0x18008465e  call    cs:__imp_CoTaskMemFree
0x180084664  mov     rcx, [rsi+8]
0x180084668  mov     rcx, [rcx+20h]; pv
0x18008466c  call    cs:__imp_CoTaskMemFree
0x180084672  mov     rcx, [rsi+8]
0x180084676  mov     rcx, [rcx+28h]; pv
0x18008467a  call    cs:__imp_CoTaskMemFree
0x180084680  mov     rcx, [rsi+8]; pv
0x180084684  call    cs:__imp_CoTaskMemFree
0x18008468a  mov     qword ptr [rsi+8], 0
0x180084692  mov     rcx, [rsi+10h]
0x180084696  test    rcx, rcx
0x180084699  jz      loc_18008472A
0x18008469f  cmp     dword ptr [rcx], 0
0x1800846a2  jbe     short loc_1800846BE
0x1800846a4  xor     ebx, ebx
0x1800846a6  mov     rcx, [rcx+8]
0x1800846aa  mov     rcx, [rcx+rbx*8]; pv
0x1800846ae  call    cs:__imp_CoTaskMemFree
0x1800846b4  inc     ebx
0x1800846b6  mov     rcx, [rsi+10h]
0x1800846ba  cmp     ebx, [rcx]
0x1800846bc  jb      short loc_1800846A6
0x1800846be  mov     rcx, [rcx+8]; pv
0x1800846c2  call    cs:__imp_CoTaskMemFree
0x1800846c8  mov     rcx, [rsi+10h]
0x1800846cc  cmp     dword ptr [rcx+10h], 0
0x1800846d0  jbe     short loc_18008470E
0x1800846d2  xor     ebp, ebp
0x1800846d4  mov     edi, ebp
0x1800846d6  shl     rdi, 5
0x1800846da  mov     rbx, [rcx+18h]
0x1800846de  mov     rcx, [rdi+rbx]; bstrString
0x1800846e2  call    cs:__imp_SysFreeString
0x1800846e8  mov     rcx, [rdi+rbx+8]; bstrString
0x1800846ed  call    cs:__imp_SysFreeString
0x1800846f3  mov     rcx, [rdi+rbx+10h]; psa
0x1800846f8  test    rcx, rcx
0x1800846fb  jz      short loc_180084703
0x1800846fd  call    cs:__imp_SafeArrayDestroy
0x180084703  inc     ebp
0x180084705  mov     rcx, [rsi+10h]
0x180084709  cmp     ebp, [rcx+10h]
0x18008470c  jb      short loc_1800846D4
0x18008470e  mov     rcx, [rcx+18h]; pv
0x180084712  call    cs:__imp_CoTaskMemFree
0x180084718  mov     rcx, [rsi+10h]; pv
0x18008471c  call    cs:__imp_CoTaskMemFree
0x180084722  mov     qword ptr [rsi+10h], 0
0x18008472a  mov     rcx, [rsi+18h]; pv
0x18008472e  test    rcx, rcx
0x180084731  jz      short loc_180084741
0x180084733  call    cs:__imp_CoTaskMemFree
0x180084739  mov     qword ptr [rsi+18h], 0
0x180084741  mov     rcx, [rsi+20h]; pv
0x180084745  test    rcx, rcx
0x180084748  jz      short loc_180084758
0x18008474a  call    cs:__imp_CoTaskMemFree
0x180084750  mov     qword ptr [rsi+20h], 0
0x180084758  lea     rcx, [rsi+28h]; struct _FSRM_IN_FILE_SECURE_PROPERTIES **
0x18008475c  call    ?ClearInFileSecureProperties@CPropertyBagFieldsBase@@KAXAEAPEAU_FSRM_IN_FILE_SECURE_PROPERTIES@@@Z; CPropertyBagFieldsBase::ClearInFileSecureProperties(_FSRM_IN_FILE_SECURE_PROPERTIES * &)
0x180084761  nop
0x180084762  add     rsp, 28h
0x180084766  pop     rdi
0x180084767  pop     rsi
0x180084768  pop     rbp
0x180084769  pop     rbx
0x18008476a  retn
```
