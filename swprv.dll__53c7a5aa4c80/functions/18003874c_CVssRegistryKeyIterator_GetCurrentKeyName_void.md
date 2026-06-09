# CVssRegistryKeyIterator::GetCurrentKeyName(void)

- ea: `0x18003874c`
- end: `0x1800389b9`
- name: `?GetCurrentKeyName@CVssRegistryKeyIterator@@QEAAPEAGXZ`
- size: `621`
- prototype: `unsigned __int16 *__fastcall(CVssRegistryKeyIterator *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002e7ec`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x180037080`
- `0x18003874c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003882e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003882e`

## string_xrefs

- `0x180038766`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180038772`: `CVssRegistryKeyIterator::GetCurrentKeyName`
- `0x18003886c`: `CVssRegistryKeyIterator::GetCurrentKeyName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall CVssRegistryKeyIterator::GetCurrentKeyName(CVssRegistryKeyIterator *this)
{
  WCHAR *v2; // r8
  LSTATUS v3; // eax
  unsigned int v4; // edi
  DWORD v5; // esi
  __int64 v6; // r14
  int v7; // r15d
  __int64 v8; // rbx
  __int64 v9; // rbx
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  PFILETIME lpftLastWriteTime; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v14; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v15; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v16; // [rsp+50h] [rbp-B0h]
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  int v19; // [rsp+60h] [rbp-A0h]
  _BYTE v20[120]; // [rsp+68h] [rbp-98h] BYREF
  int v21; // [rsp+E0h] [rbp-20h]
  LPVOID v22[20]; // [rsp+F0h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+1A0h] [rbp+A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+1A8h] [rbp+A8h] BYREF

  v14 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v15 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
  v16 = L"REGREGSC";
  v17 = 719;
  v18 = 11;
  v19 = 255;
  v21 = 0x1000000;
  memset_0(v20, 0, sizeof(v20));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v22, (__int64)&v14, 0);
  if ( !*((_BYTE *)this + 40) || (v2 = (WCHAR *)*((_QWORD *)this + 4)) == 0 )
  {
    v14 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v15 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
    v16 = L"REGREGSC";
    v17 = 723;
    v18 = 11;
    v19 = 255;
    v21 = 0x1000000;
    memset_0(v20, 0, sizeof(v20));
    CVssFunctionTracer::Throw(v22, &v14, 2147549183LL, L"Unexpected error: noninitialized iterator");
  }
  ftLastWriteTime = 0;
  cchName = *((_DWORD *)this + 4);
  v3 = RegEnumKeyExW(*(HKEY *)this, *((_DWORD *)this + 3), v2, &cchName, 0, 0, 0, &ftLastWriteTime);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 != 259 )
    {
      v5 = cchName;
      v6 = *((_QWORD *)this + 4);
      v7 = *((_DWORD *)this + 3);
      v8 = *(_QWORD *)this;
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
      v14 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v15 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
      v16 = L"REGREGSC";
      v17 = 744;
      v18 = 11;
      v19 = 255;
      v21 = 0x1000000;
      memset_0(v20, 0, sizeof(v20));
      LODWORD(lpftLastWriteTime) = v5;
      LODWORD(lpClass) = v7;
      CVssFunctionTracer::TranslateGenericError(
        v22,
        &v14,
        v4,
        L"RegEnumKeyExW(%p,%lu,%p,%lu ...)",
        v8,
        lpClass,
        v6,
        lpftLastWriteTime);
    }
    v14 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v15 = L"CVssRegistryKeyIterator::GetCurrentKeyName";
    v16 = L"REGREGSC";
    v17 = 748;
    v18 = 11;
    v19 = 255;
    v21 = 0x1000000;
    memset_0(v20, 0, sizeof(v20));
    LODWORD(lpClass) = *((_DWORD *)this + 2);
    LODWORD(lpReserved) = *((_DWORD *)this + 3);
    CVssFunctionTracer::TranslateGenericError(
      v22,
      &v14,
      2147549183LL,
      L"Unexpected error: dwIndex out of scope %lu %lu",
      lpReserved,
      lpClass);
  }
  v9 = *((_QWORD *)this + 4);
  CVssFunctionTracer::~CVssFunctionTracer(v22);
  return (unsigned __int16 *)v9;
}

```

## disassembly

```asm
0x18003874c  push    rbp
0x18003874e  push    rbx
0x18003874f  push    rsi
0x180038750  push    rdi
0x180038751  push    r13
0x180038753  push    r14
0x180038755  push    r15
0x180038757  lea     rbp, [rsp-60h]
0x18003875c  sub     rsp, 160h
0x180038763  mov     rbx, rcx
0x180038766  lea     r13, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x18003876d  mov     [rsp+190h+var_150], r13
0x180038772  lea     rsi, aCvssregistryke_2; "CVssRegistryKeyIterator::GetCurrentKeyN"...
0x180038779  mov     [rsp+190h+var_148], rsi
0x18003877e  lea     r14, aRegregsc; "REGREGSC"
0x180038785  mov     [rsp+190h+var_140], r14
0x18003878a  mov     [rsp+190h+var_138], 2CFh
0x180038792  mov     r15d, 0Bh
0x180038798  mov     [rsp+190h+var_134], r15d
0x18003879d  mov     edi, 0FFh
0x1800387a2  mov     [rsp+190h+var_130], edi
0x1800387a6  mov     [rbp+90h+var_B0], 1000000h
0x1800387ad  xor     edx, edx; Val
0x1800387af  lea     r8d, [r15+6Dh]; Size
0x1800387b3  lea     rcx, [rsp+190h+var_128]; void *
0x1800387b8  call    memset_0
0x1800387bd  xor     r8d, r8d
0x1800387c0  lea     rdx, [rsp+190h+var_150]
0x1800387c5  lea     rcx, [rbp+90h+var_A0]
0x1800387c9  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x1800387ce  nop
0x1800387cf  cmp     byte ptr [rbx+28h], 0
0x1800387d3  jz      loc_180038966
0x1800387d9  mov     r8, [rbx+20h]; lpName
0x1800387dd  test    r8, r8
0x1800387e0  jz      loc_180038966
0x1800387e6  mov     qword ptr [rbp+90h+ftLastWriteTime.dwLowDateTime], 0
0x1800387f1  mov     eax, [rbx+10h]
0x1800387f4  mov     [rbp+90h+cchName], eax
0x1800387fa  lea     rax, [rbp+90h+ftLastWriteTime]
0x180038801  mov     [rsp+190h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180038806  mov     [rsp+190h+lpcchClass], 0; lpcchClass
0x18003880f  mov     [rsp+190h+lpClass], 0; lpClass
0x180038818  mov     [rsp+190h+lpReserved], 0; lpReserved
0x180038821  lea     r9, [rbp+90h+cchName]; lpcchName
0x180038828  mov     edx, [rbx+0Ch]; dwIndex
0x18003882b  mov     rcx, [rbx]; hKey
0x18003882e  call    cs:__imp_RegEnumKeyExW
0x180038834  mov     edi, eax
0x180038836  test    eax, eax
0x180038838  jz      loc_180038944
0x18003883e  cmp     eax, 103h
0x180038843  jz      loc_1800388DF
0x180038849  mov     esi, [rbp+90h+cchName]
0x18003884f  mov     r14, [rbx+20h]
0x180038853  mov     r15d, [rbx+0Ch]
0x180038857  mov     rbx, [rbx]
0x18003885a  test    eax, eax
0x18003885c  jle     short loc_180038867
0x18003885e  movzx   edi, ax
0x180038861  or      edi, 80070000h
0x180038867  mov     [rsp+190h+var_150], r13
0x18003886c  lea     rax, aCvssregistryke_2; "CVssRegistryKeyIterator::GetCurrentKeyN"...
0x180038873  mov     [rsp+190h+var_148], rax
0x180038878  lea     rax, aRegregsc; "REGREGSC"
0x18003887f  mov     [rsp+190h+var_140], rax
0x180038884  mov     [rsp+190h+var_138], 2E8h
0x18003888c  mov     [rsp+190h+var_134], 0Bh
0x180038894  mov     [rsp+190h+var_130], 0FFh
0x18003889c  mov     [rbp+90h+var_B0], 1000000h
0x1800388a3  xor     edx, edx; Val
0x1800388a5  lea     r8d, [rdx+78h]; Size
0x1800388a9  lea     rcx, [rsp+190h+var_128]; void *
0x1800388ae  call    memset_0
0x1800388b3  mov     dword ptr [rsp+190h+lpftLastWriteTime], esi
0x1800388b7  mov     [rsp+190h+lpcchClass], r14
0x1800388bc  mov     dword ptr [rsp+190h+lpClass], r15d
0x1800388c1  mov     [rsp+190h+lpReserved], rbx
0x1800388c6  lea     r9, aRegenumkeyexwP; "RegEnumKeyExW(%p,%lu,%p,%lu ...)"
0x1800388cd  mov     r8d, edi
0x1800388d0  lea     rdx, [rsp+190h+var_150]
0x1800388d5  lea     rcx, [rbp+90h+var_A0]
0x1800388d9  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x1800388df  mov     [rsp+190h+var_150], r13
0x1800388e4  mov     [rsp+190h+var_148], rsi
0x1800388e9  mov     [rsp+190h+var_140], r14
0x1800388ee  mov     [rsp+190h+var_138], 2ECh
0x1800388f6  mov     [rsp+190h+var_134], r15d
0x1800388fb  mov     [rsp+190h+var_130], 0FFh
0x180038903  mov     [rbp+90h+var_B0], 1000000h
0x18003890a  xor     edx, edx; Val
0x18003890c  lea     r8d, [rdx+78h]; Size
0x180038910  lea     rcx, [rsp+190h+var_128]; void *
0x180038915  call    memset_0
0x18003891a  mov     eax, [rbx+8]
0x18003891d  mov     dword ptr [rsp+190h+lpClass], eax
0x180038921  mov     eax, [rbx+0Ch]
0x180038924  mov     dword ptr [rsp+190h+lpReserved], eax
0x180038928  lea     r9, aUnexpectedErro_8; "Unexpected error: dwIndex out of scope "...
0x18003892f  mov     r8d, 8000FFFFh
0x180038935  lea     rdx, [rsp+190h+var_150]
0x18003893a  lea     rcx, [rbp+90h+var_A0]
0x18003893e  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038944  mov     rbx, [rbx+20h]
0x180038948  lea     rcx, [rbp+90h+var_A0]; this
0x18003894c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180038951  mov     rax, rbx
0x180038954  add     rsp, 160h
0x18003895b  pop     r15
0x18003895d  pop     r14
0x18003895f  pop     r13
0x180038961  pop     rdi
0x180038962  pop     rsi
0x180038963  pop     rbx
0x180038964  pop     rbp
0x180038965  retn
0x180038966  mov     [rsp+190h+var_150], r13
0x18003896b  mov     [rsp+190h+var_148], rsi
0x180038970  mov     [rsp+190h+var_140], r14
0x180038975  mov     [rsp+190h+var_138], 2D3h
0x18003897d  mov     [rsp+190h+var_134], r15d
0x180038982  mov     [rsp+190h+var_130], edi
0x180038986  mov     [rbp+90h+var_B0], 1000000h
0x18003898d  xor     edx, edx; Val
0x18003898f  lea     r8d, [rdx+78h]; Size
0x180038993  lea     rcx, [rsp+190h+var_128]; void *
0x180038998  call    memset_0
0x18003899d  lea     r9, aUnexpectedErro_7; "Unexpected error: noninitialized iterat"...
0x1800389a4  mov     r8d, 8000FFFFh
0x1800389aa  lea     rdx, [rsp+190h+var_150]
0x1800389af  lea     rcx, [rbp+90h+var_A0]
0x1800389b3  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
