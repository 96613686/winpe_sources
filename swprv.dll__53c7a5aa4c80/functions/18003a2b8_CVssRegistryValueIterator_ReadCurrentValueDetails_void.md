# CVssRegistryValueIterator::ReadCurrentValueDetails(void)

- ea: `0x18003a2b8`
- end: `0x18003a52d`
- name: `?ReadCurrentValueDetails@CVssRegistryValueIterator@@AEAAXXZ`
- size: `629`
- prototype: `void __fastcall(CVssRegistryValueIterator *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800389c0`
- `0x180038d40`
- `0x180038dec`
- `0x180038f00`

## callees

- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x180037080`
- `0x18003a2b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003a3bc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003a3bc`

## string_xrefs

- `0x18003a2d9`: `base\stor\vss\modules\registry\registry.cxx`
- `0x18003a2e5`: `CVssRegistryValueIterator::ReadCurrentValueDetails`
- `0x18003a3fa`: `CVssRegistryValueIterator::ReadCurrentValueDetails`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssRegistryValueIterator::ReadCurrentValueDetails(CVssRegistryValueIterator *this)
{
  WCHAR *v2; // r8
  LSTATUS v3; // eax
  unsigned int v4; // edi
  int v5; // esi
  DWORD v6; // r14d
  __int64 v7; // r15
  __int64 v8; // rbx
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  LPDWORD lpType; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbData; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v12; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v14; // [rsp+50h] [rbp-B0h]
  int v15; // [rsp+58h] [rbp-A8h]
  int v16; // [rsp+5Ch] [rbp-A4h]
  int v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[120]; // [rsp+68h] [rbp-98h] BYREF
  int v19; // [rsp+E0h] [rbp-20h]
  LPVOID v20[14]; // [rsp+F0h] [rbp-10h] BYREF
  DWORD cchValueName; // [rsp+190h] [rbp+90h] BYREF

  v12 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v13 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
  v14 = L"REGREGSC";
  v15 = 1118;
  v16 = 11;
  v17 = 255;
  v19 = 0x1000000;
  memset_0(v18, 0, sizeof(v18));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v20, (__int64)&v12, 0);
  if ( !*((_BYTE *)this + 49) || (v2 = (WCHAR *)*((_QWORD *)this + 4)) == 0 )
  {
    v12 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v13 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
    v14 = L"REGREGSC";
    v15 = 1122;
    v16 = 11;
    v17 = 255;
    v19 = 0x1000000;
    memset_0(v18, 0, sizeof(v18));
    CVssFunctionTracer::TranslateGenericError(v20, &v12, 2147549183LL, L"Unexpected error: noninitialized iterator");
  }
  if ( !*((_BYTE *)this + 48) )
  {
    cchValueName = *((_DWORD *)this + 10);
    v3 = RegEnumValueW(
           *(HKEY *)this,
           *((_DWORD *)this + 3),
           v2,
           &cchValueName,
           0,
           (LPDWORD)this + 4,
           0,
           (LPDWORD)this + 11);
    v4 = v3;
    if ( v3 )
    {
      v5 = *((_DWORD *)this + 3);
      if ( v3 != 259 )
      {
        v6 = cchValueName;
        v7 = *((_QWORD *)this + 4);
        v8 = *(_QWORD *)this;
        if ( v3 > 0 )
          v4 = (unsigned __int16)v3 | 0x80070000;
        v12 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
        v13 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
        v14 = L"REGREGSC";
        v15 = 1146;
        v16 = 11;
        v17 = 255;
        v19 = 0x1000000;
        memset_0(v18, 0, sizeof(v18));
        LODWORD(lpcbData) = v6;
        LODWORD(lpType) = v5;
        CVssFunctionTracer::TranslateGenericError(
          v20,
          &v12,
          v4,
          L"RegEnumValue(%p,%lu,%p,%lu ...)",
          v8,
          lpType,
          v7,
          lpcbData);
      }
      v12 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
      v13 = L"CVssRegistryValueIterator::ReadCurrentValueDetails";
      v14 = L"REGREGSC";
      v15 = 1150;
      v16 = 11;
      v17 = 255;
      v19 = 0x1000000;
      memset_0(v18, 0, sizeof(v18));
      LODWORD(lpType) = *((_DWORD *)this + 2);
      LODWORD(lpReserved) = v5;
      CVssFunctionTracer::TranslateGenericError(
        v20,
        &v12,
        2147549183LL,
        L"Unexpected error: dwIndex out of scope %lu %lu",
        lpReserved,
        lpType);
    }
    *((_BYTE *)this + 48) = 1;
  }
  CVssFunctionTracer::~CVssFunctionTracer(v20);
}

```

## disassembly

```asm
0x18003a2b8  mov     [rsp-8+arg_10], rbx
0x18003a2bd  mov     [rsp-8+arg_18], rsi
0x18003a2c2  push    rbp
0x18003a2c3  push    rdi
0x18003a2c4  push    r13
0x18003a2c6  push    r14
0x18003a2c8  push    r15
0x18003a2ca  lea     rbp, [rsp-60h]
0x18003a2cf  sub     rsp, 160h
0x18003a2d6  mov     rbx, rcx
0x18003a2d9  lea     r13, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x18003a2e0  mov     [rsp+180h+var_140], r13
0x18003a2e5  lea     r14, aCvssregistryva; "CVssRegistryValueIterator::ReadCurrentV"...
0x18003a2ec  mov     [rsp+180h+var_138], r14
0x18003a2f1  lea     r15, aRegregsc; "REGREGSC"
0x18003a2f8  mov     [rsp+180h+var_130], r15
0x18003a2fd  mov     [rsp+180h+var_128], 45Eh
0x18003a305  mov     edi, 0Bh
0x18003a30a  mov     [rsp+180h+var_124], edi
0x18003a30e  mov     esi, 0FFh
0x18003a313  mov     [rsp+180h+var_120], esi
0x18003a317  mov     [rbp+80h+var_A0], 1000000h
0x18003a31e  xor     edx, edx; Val
0x18003a320  lea     r8d, [rdi+6Dh]; Size
0x18003a324  lea     rcx, [rsp+180h+var_118]; void *
0x18003a329  call    memset_0
0x18003a32e  xor     r8d, r8d
0x18003a331  lea     rdx, [rsp+180h+var_140]
0x18003a336  lea     rcx, [rbp+80h+var_90]
0x18003a33a  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003a33f  nop
0x18003a340  cmp     byte ptr [rbx+31h], 0
0x18003a344  jz      loc_18003A4DB
0x18003a34a  mov     r8, [rbx+20h]; lpValueName
0x18003a34e  test    r8, r8
0x18003a351  jz      loc_18003A4DB
0x18003a357  cmp     byte ptr [rbx+30h], 0
0x18003a35b  jz      short loc_18003A382
0x18003a35d  lea     rcx, [rbp+80h+var_90]; this
0x18003a361  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003a366  lea     r11, [rsp+180h+var_20]
0x18003a36e  mov     rbx, [r11+40h]
0x18003a372  mov     rsi, [r11+48h]
0x18003a376  mov     rsp, r11
0x18003a379  pop     r15
0x18003a37b  pop     r14
0x18003a37d  pop     r13
0x18003a37f  pop     rdi
0x18003a380  pop     rbp
0x18003a381  retn
0x18003a382  mov     eax, [rbx+28h]
0x18003a385  mov     [rbp+80h+cchValueName], eax
0x18003a38b  lea     rax, [rbx+2Ch]
0x18003a38f  lea     rcx, [rbx+10h]
0x18003a393  mov     [rsp+180h+lpcbData], rax; lpcbData
0x18003a398  mov     [rsp+180h+lpData], 0; lpData
0x18003a3a1  mov     [rsp+180h+lpType], rcx; lpType
0x18003a3a6  mov     [rsp+180h+lpReserved], 0; lpReserved
0x18003a3af  lea     r9, [rbp+80h+cchValueName]; lpcchValueName
0x18003a3b6  mov     edx, [rbx+0Ch]; dwIndex
0x18003a3b9  mov     rcx, [rbx]; hKey
0x18003a3bc  call    cs:__imp_RegEnumValueW
0x18003a3c2  mov     edi, eax
0x18003a3c4  test    eax, eax
0x18003a3c6  jz      loc_18003A4D2
0x18003a3cc  mov     esi, [rbx+0Ch]
0x18003a3cf  cmp     eax, 103h
0x18003a3d4  jz      loc_18003A46D
0x18003a3da  mov     r14d, [rbp+80h+cchValueName]
0x18003a3e1  mov     r15, [rbx+20h]
0x18003a3e5  mov     rbx, [rbx]
0x18003a3e8  test    eax, eax
0x18003a3ea  jle     short loc_18003A3F5
0x18003a3ec  movzx   edi, ax
0x18003a3ef  or      edi, 80070000h
0x18003a3f5  mov     [rsp+180h+var_140], r13
0x18003a3fa  lea     rax, aCvssregistryva; "CVssRegistryValueIterator::ReadCurrentV"...
0x18003a401  mov     [rsp+180h+var_138], rax
0x18003a406  lea     rax, aRegregsc; "REGREGSC"
0x18003a40d  mov     [rsp+180h+var_130], rax
0x18003a412  mov     [rsp+180h+var_128], 47Ah
0x18003a41a  mov     [rsp+180h+var_124], 0Bh
0x18003a422  mov     [rsp+180h+var_120], 0FFh
0x18003a42a  mov     [rbp+80h+var_A0], 1000000h
0x18003a431  xor     edx, edx; Val
0x18003a433  lea     r8d, [rdx+78h]; Size
0x18003a437  lea     rcx, [rsp+180h+var_118]; void *
0x18003a43c  call    memset_0
0x18003a441  mov     dword ptr [rsp+180h+lpcbData], r14d
0x18003a446  mov     [rsp+180h+lpData], r15
0x18003a44b  mov     dword ptr [rsp+180h+lpType], esi
0x18003a44f  mov     [rsp+180h+lpReserved], rbx
0x18003a454  lea     r9, aRegenumvaluePL; "RegEnumValue(%p,%lu,%p,%lu ...)"
0x18003a45b  mov     r8d, edi
0x18003a45e  lea     rdx, [rsp+180h+var_140]
0x18003a463  lea     rcx, [rbp+80h+var_90]
0x18003a467  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003a46d  mov     [rsp+180h+var_140], r13
0x18003a472  mov     [rsp+180h+var_138], r14
0x18003a477  mov     [rsp+180h+var_130], r15
0x18003a47c  mov     [rsp+180h+var_128], 47Eh
0x18003a484  mov     [rsp+180h+var_124], 0Bh
0x18003a48c  mov     [rsp+180h+var_120], 0FFh
0x18003a494  mov     [rbp+80h+var_A0], 1000000h
0x18003a49b  xor     edx, edx; Val
0x18003a49d  lea     r8d, [rdx+78h]; Size
0x18003a4a1  lea     rcx, [rsp+180h+var_118]; void *
0x18003a4a6  call    memset_0
0x18003a4ab  mov     eax, [rbx+8]
0x18003a4ae  mov     dword ptr [rsp+180h+lpType], eax
0x18003a4b2  mov     dword ptr [rsp+180h+lpReserved], esi
0x18003a4b6  lea     r9, aUnexpectedErro_8; "Unexpected error: dwIndex out of scope "...
0x18003a4bd  mov     r8d, 8000FFFFh
0x18003a4c3  lea     rdx, [rsp+180h+var_140]
0x18003a4c8  lea     rcx, [rbp+80h+var_90]
0x18003a4cc  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x18003a4d2  mov     byte ptr [rbx+30h], 1
0x18003a4d6  jmp     loc_18003A35D
0x18003a4db  mov     [rsp+180h+var_140], r13
0x18003a4e0  mov     [rsp+180h+var_138], r14
0x18003a4e5  mov     [rsp+180h+var_130], r15
0x18003a4ea  mov     [rsp+180h+var_128], 462h
0x18003a4f2  mov     [rsp+180h+var_124], edi
0x18003a4f6  mov     [rsp+180h+var_120], esi
0x18003a4fa  mov     [rbp+80h+var_A0], 1000000h
0x18003a501  xor     edx, edx; Val
0x18003a503  lea     r8d, [rdx+78h]; Size
0x18003a507  lea     rcx, [rsp+180h+var_118]; void *
0x18003a50c  call    memset_0
0x18003a511  lea     r9, aUnexpectedErro_7; "Unexpected error: noninitialized iterat"...
0x18003a518  mov     r8d, 8000FFFFh
0x18003a51e  lea     rdx, [rsp+180h+var_140]
0x18003a523  lea     rcx, [rbp+80h+var_90]
0x18003a527  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
