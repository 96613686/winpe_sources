# CharEncoder::wideCharToMultiByteMlangNoBestFit(ulong *,uint,wchar_t *,uint *,uchar *,uint *)

- ea: `0x100421180`
- end: `0x10042126d`
- name: `?wideCharToMultiByteMlangNoBestFit@CharEncoder@@SAJPEAKIPEA_WPEAIPEAE2@Z`
- size: `237`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x100421180`
- `0x100439df0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1004211ce`
- `ole32!CoCreateInstance` at `0x1004211ce`

## pseudocode

```c
HRESULT __fastcall CharEncoder::wideCharToMultiByteMlangNoBestFit(
        unsigned int *a1,
        unsigned int a2,
        wchar_t *a3,
        unsigned int *a4,
        unsigned __int8 *a5,
        unsigned int *a6)
{
  struct IMultiLanguage2 *v8; // rcx
  HRESULT result; // eax
  bool v12; // zf
  LPVOID ppv; // [rsp+50h] [rbp-18h] BYREF

  v8 = s_pMultiLanguage2;
  if ( s_pMultiLanguage2 )
    return ((__int64 (__fastcall *)(struct IMultiLanguage2 *, unsigned int *, _QWORD, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *, int, const wchar_t *))v8->lpVtbl->ConvertStringFromUnicodeEx)(
             v8,
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             24,
             L"?");
  ppv = 0;
  result = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, &ppv);
  v12 = result == 0;
  if ( result >= 0 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&s_pMultiLanguage2, (signed __int64)ppv, 0) )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    result = 0;
    v12 = 1;
  }
  if ( v12 )
  {
    v8 = s_pMultiLanguage2;
    return ((__int64 (__fastcall *)(struct IMultiLanguage2 *, unsigned int *, _QWORD, wchar_t *, unsigned int *, unsigned __int8 *, unsigned int *, int, const wchar_t *))v8->lpVtbl->ConvertStringFromUnicodeEx)(
             v8,
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             24,
             L"?");
  }
  return result;
}

```

## disassembly

```asm
0x100421180  mov     [rsp+arg_0], rbx
0x100421185  mov     [rsp+arg_8], rbp
0x10042118a  mov     [rsp+arg_10], rsi
0x10042118f  push    rdi
0x100421190  sub     rsp, 60h
0x100421194  mov     rbp, rcx
0x100421197  mov     rbx, r9
0x10042119a  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x1004211a1  mov     rdi, r8
0x1004211a4  mov     esi, edx
0x1004211a6  test    rcx, rcx
0x1004211a9  jnz     short loc_100421209
0x1004211ab  mov     [rsp+68h+var_18], rcx
0x1004211b0  lea     rax, [rsp+68h+var_18]
0x1004211b5  lea     r8d, [rcx+1]; dwClsContext
0x1004211b9  mov     [rsp+68h+ppv], rax; ppv
0x1004211be  lea     rcx, CLSID_CMultiLanguage; rclsid
0x1004211c5  xor     edx, edx; pUnkOuter
0x1004211c7  lea     r9, IID_IMultiLanguage2; riid
0x1004211ce  call    cs:__imp_CoCreateInstance
0x1004211d4  test    eax, eax
0x1004211d6  js      short loc_100421200
0x1004211d8  mov     rcx, [rsp+68h+var_18]
0x1004211dd  xor     eax, eax
0x1004211df  lock cmpxchg cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA, rcx; IMultiLanguage2 * s_pMultiLanguage2
0x1004211e8  jz      short loc_1004211FC
0x1004211ea  mov     rcx, [rsp+68h+var_18]
0x1004211ef  mov     rax, [rcx]
0x1004211f2  mov     rax, [rax+10h]
0x1004211f6  call    cs:__guard_dispatch_icall_fptr
0x1004211fc  xor     eax, eax
0x1004211fe  test    eax, eax
0x100421200  jnz     short loc_100421255
0x100421202  mov     rcx, cs:?s_pMultiLanguage2@@3PEAUIMultiLanguage2@@EA; IMultiLanguage2 * s_pMultiLanguage2
0x100421209  mov     rax, [rcx]
0x10042120c  lea     rdx, asc_100444F80; "?"
0x100421213  mov     [rsp+68h+var_28], rdx
0x100421218  mov     r9, rdi
0x10042121b  mov     rdx, [rsp+68h+arg_28]
0x100421223  mov     r8d, esi
0x100421226  mov     [rsp+68h+var_30], 18h
0x10042122e  mov     rax, [rax+0A0h]
0x100421235  mov     [rsp+68h+var_38], rdx
0x10042123a  mov     rdx, [rsp+68h+arg_20]
0x100421242  mov     [rsp+68h+var_40], rdx
0x100421247  mov     rdx, rbp
0x10042124a  mov     [rsp+68h+ppv], rbx
0x10042124f  call    cs:__guard_dispatch_icall_fptr
0x100421255  mov     rbx, [rsp+68h+arg_0]
0x10042125a  mov     rbp, [rsp+68h+arg_8]
0x10042125f  mov     rsi, [rsp+68h+arg_10]
0x100421267  add     rsp, 60h
0x10042126b  pop     rdi
0x10042126c  retn
```
