# RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x140005620`
- end: `0x140005a6e`
- name: `?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1102`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400050a0`
- `0x140006de0`
- `0x1400076b4`
- `0x1400158b4`
- `0x140015cac`
- `0x1400196d8`
- `0x14002cc9c`
- `0x14002e0cc`

## callees

- `0x140005620`
- `0x140031828`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140005709`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x140005709`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400059aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400059aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005878`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005956`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000599c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005878`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005956`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000599c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005837`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005964`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005837`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140005964`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400058c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400058c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000569f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000569f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005743`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400058e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400059f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005743`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400058e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400059f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005a51`

## pseudocode

```c
__int64 __fastcall RegReadStringValueNoThrow(HKEY hKey, const WCHAR *a2, const WCHAR *a3, __int64 a4)
{
  DWORD v6; // eax
  HKEY v7; // rbp
  __int64 v8; // r13
  unsigned int v9; // edi
  char *v10; // rdx
  LPBYTE v11; // rcx
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // rsi
  _WORD *v14; // rcx
  size_t v15; // rax
  char *v16; // rcx
  size_t v17; // rsi
  LPBYTE v18; // rax
  unsigned __int64 v19; // rdi
  _WORD *v20; // rcx
  _QWORD *v22; // r15
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  char *v25; // rdi
  _QWORD *v26; // r14
  unsigned __int64 v27; // rdx
  size_t v28; // rdx
  char *v29; // rdi
  size_t i; // rcx
  __int64 v31; // rax
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rax
  SIZE_T v34; // r12
  HANDLE ProcessHeap; // rax
  char *v36; // r12
  HANDLE v37; // rax
  unsigned int v38; // edi
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rax
  SIZE_T v41; // r15
  HANDLE v42; // rax
  char *v43; // rax
  char *v44; // rbp
  __int64 v45; // r12
  LPBYTE v46; // r13
  HANDLE v47; // rax
  _WORD *v48; // rcx
  LPBYTE lpMem; // [rsp+30h] [rbp-58h]
  __int64 v50; // [rsp+38h] [rbp-50h]
  __int64 v51; // [rsp+40h] [rbp-48h]
  DWORD cbData; // [rsp+90h] [rbp+8h] BYREF
  DWORD Type; // [rsp+98h] [rbp+10h] BYREF
  HKEY hKeya; // [rsp+A8h] [rbp+20h] BYREF

  v6 = 2 * ((__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1);
  Type = 0;
  cbData = v6;
  v7 = hKey;
  hKeya = 0;
  if ( a2 && *a2 )
  {
    v38 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &hKeya);
    if ( v38 )
    {
      if ( hKeya )
        RegCloseKey(hKeya);
      return v38;
    }
    v7 = hKeya;
  }
  v8 = 7;
  while ( 1 )
  {
    v9 = RegQueryValueExW(v7, a3, 0, &Type, *(LPBYTE *)a4, &cbData);
    if ( v9 != 234 )
      break;
    v10 = *(char **)(a4 + 8);
    v11 = *(LPBYTE *)a4;
    v12 = (__int64)&v10[-*(_QWORD *)a4] >> 1;
    v13 = (unsigned __int64)cbData >> 1;
    if ( v12 < v13 )
    {
      v22 = (_QWORD *)(a4 + 16);
      if ( v11 == (LPBYTE)(a4 + 16) )
        v23 = 7;
      else
        v23 = (__int64)(*v22 - (_QWORD)v11) >> 1;
      if ( v13 > v23 )
      {
        if ( v11 == (LPBYTE)v22 )
          v31 = 7;
        else
          v31 = (__int64)(*v22 - (_QWORD)v11) >> 1;
        v32 = 2 * v31 + 1;
        if ( v32 < v13 )
          v32 = (unsigned __int64)cbData >> 1;
        if ( v32 > 0x3FFFFFFFFFFFFFF7LL )
          v32 = 0x3FFFFFFFFFFFFFF7LL;
        if ( v13 > v32
          || (v33 = (v32 + 8) & 0xFFFFFFFFFFFFFFF8uLL, v33 > 0x7FFFFFFFFFFFFFFFLL)
          || (v34 = 2 * v33,
              v51 = 2 * v33,
              ProcessHeap = GetProcessHeap(),
              (v36 = (char *)HeapAlloc(ProcessHeap, 0, v34)) == 0) )
        {
          v48 = (_WORD *)(*(_QWORD *)a4 + 2 * v12);
          *(_QWORD *)(a4 + 8) = v48;
          *v48 = 0;
          if ( hKeya )
            RegCloseKey(hKeya);
          return 14;
        }
        v50 = 2 * ((__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1);
        memcpy_0(v36, *(const void **)a4, v50 + 2);
        lpMem = *(LPBYTE *)a4;
        if ( *(_QWORD **)a4 != v22 )
        {
          v37 = GetProcessHeap();
          HeapFree(v37, 0, lpMem);
        }
        *(_QWORD *)a4 = v36;
        v10 = &v36[v50];
        *v22 = &v36[v51 - 2];
      }
      v24 = v13 - v12;
      if ( v13 != v12 )
      {
        v25 = v10;
        while ( v24 )
        {
          *(_WORD *)v25 = 0;
          v25 += 2;
          --v24;
        }
      }
    }
    v14 = (_WORD *)(*(_QWORD *)a4 + 2 * v13);
    *(_QWORD *)(a4 + 8) = v14;
    *v14 = 0;
  }
  if ( v9 )
  {
    if ( hKeya )
      RegCloseKey(hKeya);
    return v9;
  }
  else
  {
    if ( Type - 1 <= 1 )
    {
      v15 = wcsnlen(*(const wchar_t **)a4, (unsigned __int64)cbData >> 1);
      v16 = *(char **)(a4 + 8);
      v17 = v15;
      v18 = *(LPBYTE *)a4;
      v19 = (__int64)&v16[-*(_QWORD *)a4] >> 1;
      if ( v19 >= v17 )
      {
LABEL_10:
        v20 = (_WORD *)(*(_QWORD *)a4 + 2 * v17);
        *(_QWORD *)(a4 + 8) = v20;
        *v20 = 0;
        if ( hKeya )
          RegCloseKey(hKeya);
        return 0;
      }
      v26 = (_QWORD *)(a4 + 16);
      if ( v18 == (LPBYTE)(a4 + 16) )
        v27 = 7;
      else
        v27 = (__int64)(*v26 - (_QWORD)v18) >> 1;
      if ( v17 > v27 )
      {
        if ( v18 != (LPBYTE)v26 )
          v8 = (__int64)(*v26 - (_QWORD)v18) >> 1;
        v39 = 2 * v8 + 1;
        if ( v39 < v17 )
          v39 = v17;
        if ( v39 > 0x3FFFFFFFFFFFFFF7LL )
          v39 = 0x3FFFFFFFFFFFFFF7LL;
        if ( v17 > v39
          || (v40 = (v39 + 8) & 0xFFFFFFFFFFFFFFF8uLL, v40 > 0x7FFFFFFFFFFFFFFFLL)
          || (v41 = 2 * v40, v42 = GetProcessHeap(), v43 = (char *)HeapAlloc(v42, 0, v41), (v44 = v43) == 0) )
        {
          v17 = v19;
          goto LABEL_10;
        }
        v45 = 2 * ((__int64)(*(_QWORD *)(a4 + 8) - *(_QWORD *)a4) >> 1);
        memcpy_0(v43, *(const void **)a4, v45 + 2);
        v46 = *(LPBYTE *)a4;
        if ( *(_QWORD **)a4 != v26 )
        {
          v47 = GetProcessHeap();
          HeapFree(v47, 0, v46);
        }
        *(_QWORD *)a4 = v44;
        v16 = &v44[v45];
        *v26 = &v44[v41 - 2];
      }
      v28 = v17 - v19;
      if ( v17 != v19 )
      {
        v29 = v16;
        for ( i = v28; i; --i )
        {
          *(_WORD *)v29 = 0;
          v29 += 2;
        }
      }
      goto LABEL_10;
    }
    if ( hKeya )
      RegCloseKey(hKeya);
    return 1630;
  }
}

```

## disassembly

```asm
0x140005620  mov     r11, rsp
0x140005623  push    rbx
0x140005624  push    rbp
0x140005625  push    rdi
0x140005626  push    r12
0x140005628  push    r14
0x14000562a  sub     rsp, 60h
0x14000562e  mov     rax, [r9+8]
0x140005632  xor     r12d, r12d
0x140005635  sub     rax, [r9]
0x140005638  mov     rbx, r9
0x14000563b  sar     rax, 1
0x14000563e  mov     r14, r8
0x140005641  add     eax, eax
0x140005643  mov     [r11+10h], r12d
0x140005647  mov     [r11+8], eax
0x14000564b  mov     rbp, rcx
0x14000564e  mov     [r11+20h], r12
0x140005652  test    rdx, rdx
0x140005655  jz      short loc_140005661
0x140005657  cmp     [rdx], r12w
0x14000565b  jnz     loc_1400058B0
0x140005661  mov     [rsp+88h+var_30], r13
0x140005666  mov     r13d, 7
0x14000566c  mov     [rsp+88h+arg_10], rsi
0x140005674  mov     [rsp+88h+var_38], r15
0x140005679  lea     rax, [rsp+88h+cbData]
0x140005681  xor     r8d, r8d; lpReserved
0x140005684  mov     [rsp+88h+lpcbData], rax; lpcbData
0x140005689  lea     r9, [rsp+88h+Type]; lpType
0x140005691  mov     rax, [rbx]
0x140005694  mov     rdx, r14; lpValueName
0x140005697  mov     rcx, rbp; hKey
0x14000569a  mov     [rsp+88h+lpData], rax; lpData
0x14000569f  call    cs:__imp_RegQueryValueExW
0x1400056a5  mov     edi, eax
0x1400056a7  cmp     eax, 0EAh
0x1400056ac  jnz     short loc_1400056E2
0x1400056ae  mov     rdx, [rbx+8]
0x1400056b2  mov     rcx, [rbx]
0x1400056b5  mov     rdi, rdx
0x1400056b8  mov     esi, [rsp+88h+cbData]
0x1400056bf  sub     rdi, rcx
0x1400056c2  sar     rdi, 1
0x1400056c5  shr     rsi, 1
0x1400056c8  cmp     rdi, rsi
0x1400056cb  jb      loc_140005769
0x1400056d1  mov     rax, [rbx]
0x1400056d4  lea     rcx, [rax+rsi*2]
0x1400056d8  mov     [rbx+8], rcx
0x1400056dc  mov     [rcx], r12w
0x1400056e0  jmp     short loc_140005679
0x1400056e2  test    edi, edi
0x1400056e4  jnz     loc_140005A2A
0x1400056ea  mov     eax, [rsp+88h+Type]
0x1400056f1  dec     eax
0x1400056f3  cmp     eax, 1
0x1400056f6  ja      loc_140005A44
0x1400056fc  mov     edx, [rsp+88h+cbData]
0x140005703  mov     rcx, [rbx]; Source
0x140005706  shr     rdx, 1; MaxCount
0x140005709  call    cs:__imp_wcsnlen
0x14000570f  mov     rcx, [rbx+8]
0x140005713  mov     rsi, rax
0x140005716  mov     rax, [rbx]
0x140005719  mov     rdi, rcx
0x14000571c  sub     rdi, rax
0x14000571f  sar     rdi, 1
0x140005722  cmp     rdi, rsi
0x140005725  jb      short loc_140005799
0x140005727  mov     rax, [rbx]
0x14000572a  lea     rcx, [rax+rsi*2]
0x14000572e  mov     [rbx+8], rcx
0x140005732  mov     [rcx], r12w
0x140005736  mov     rcx, [rsp+88h+hKey]; hKey
0x14000573e  test    rcx, rcx
0x140005741  jz      short loc_140005749
0x140005743  call    cs:__imp_RegCloseKey
0x140005749  xor     eax, eax
0x14000574b  mov     rsi, [rsp+88h+arg_10]
0x140005753  mov     r15, [rsp+88h+var_38]
0x140005758  mov     r13, [rsp+88h+var_30]
0x14000575d  add     rsp, 60h
0x140005761  pop     r14
0x140005763  pop     r12
0x140005765  pop     rdi
0x140005766  pop     rbp
0x140005767  pop     rbx
0x140005768  retn
0x140005769  lea     r15, [rbx+10h]
0x14000576d  cmp     rcx, r15
0x140005770  jnz     loc_1400058F7
0x140005776  mov     rax, r13
0x140005779  cmp     rsi, rax
0x14000577c  ja      short loc_1400057D0
0x14000577e  mov     rcx, rsi
0x140005781  sub     rcx, rdi
0x140005784  jz      loc_1400056D1
0x14000578a  movzx   eax, r12w
0x14000578e  mov     rdi, rdx
0x140005791  rep stosw
0x140005794  jmp     loc_1400056D1
0x140005799  lea     r14, [rbx+10h]
0x14000579d  cmp     rax, r14
0x1400057a0  jnz     loc_1400059C9
0x1400057a6  mov     rdx, r13
0x1400057a9  cmp     rsi, rdx
0x1400057ac  ja      loc_140005905
0x1400057b2  mov     rdx, rsi
0x1400057b5  sub     rdx, rdi
0x1400057b8  jz      loc_140005727
0x1400057be  mov     rdi, rcx
0x1400057c1  movzx   eax, r12w
0x1400057c5  mov     rcx, rdx
0x1400057c8  rep stosw
0x1400057cb  jmp     loc_140005727
0x1400057d0  cmp     rcx, r15
0x1400057d3  jnz     loc_140005A06
0x1400057d9  mov     rax, r13
0x1400057dc  lea     rax, ds:1[rax*2]
0x1400057e4  mov     rcx, 3FFFFFFFFFFFFFF7h
0x1400057ee  cmp     rax, rsi
0x1400057f1  cmovb   rax, rsi
0x1400057f5  cmp     rax, rcx
0x1400057f8  cmova   rax, rcx
0x1400057fc  cmp     rsi, rax
0x1400057ff  ja      loc_1400059DA
0x140005805  add     rax, 8
0x140005809  mov     rcx, 7FFFFFFFFFFFFFFFh
0x140005813  and     rax, 0FFFFFFFFFFFFFFF8h
0x140005817  cmp     rax, rcx
0x14000581a  ja      loc_1400059DA
0x140005820  lea     r12, [rax+rax]
0x140005824  mov     [rsp+88h+var_48], r12
0x140005829  call    cs:__imp_GetProcessHeap
0x14000582f  mov     r8, r12; dwBytes
0x140005832  xor     edx, edx; dwFlags
0x140005834  mov     rcx, rax; hHeap
0x140005837  call    cs:__imp_HeapAlloc
0x14000583d  mov     r12, rax
0x140005840  test    rax, rax
0x140005843  jz      loc_1400059D7
0x140005849  mov     rdx, [rbx]; Src
0x14000584c  mov     rcx, [rbx+8]
0x140005850  sub     rcx, rdx
0x140005853  sar     rcx, 1
0x140005856  lea     rax, [rcx+rcx]
0x14000585a  mov     rcx, r12; void *
0x14000585d  lea     r8, [rax+2]; Size
0x140005861  mov     [rsp+88h+var_50], rax
0x140005866  call    memcpy_0
0x14000586b  mov     rax, [rbx]
0x14000586e  mov     [rsp+88h+lpMem], rax
0x140005873  cmp     rax, r15
0x140005876  jz      short loc_14000588E
0x140005878  call    cs:__imp_GetProcessHeap
0x14000587e  mov     r8, [rsp+88h+lpMem]; lpMem
0x140005883  xor     edx, edx; dwFlags
0x140005885  mov     rcx, rax; hHeap
0x140005888  call    cs:__imp_HeapFree
0x14000588e  mov     rax, [rsp+88h+var_48]
0x140005893  mov     rdx, [rsp+88h+var_50]
0x140005898  add     rax, 0FFFFFFFFFFFFFFFEh
0x14000589c  add     rax, r12
0x14000589f  mov     [rbx], r12
0x1400058a2  add     rdx, r12; lpSubKey
0x1400058a5  mov     [r15], rax
0x1400058a8  xor     r12d, r12d
0x1400058ab  jmp     loc_14000577E
0x1400058b0  lea     rax, [rsp+88h+hKey]
0x1400058b8  mov     r9d, 20019h; samDesired
0x1400058be  xor     r8d, r8d; ulOptions
0x1400058c1  mov     [rsp+88h+lpData], rax; phkResult
0x1400058c6  call    cs:__imp_RegOpenKeyExW
0x1400058cc  mov     edi, eax
0x1400058ce  test    eax, eax
0x1400058d0  jz      loc_140005A61
0x1400058d6  mov     rcx, [rsp+88h+hKey]; hKey
0x1400058de  test    rcx, rcx
0x1400058e1  jz      short loc_1400058E9
0x1400058e3  call    cs:__imp_RegCloseKey
0x1400058e9  mov     eax, edi
0x1400058eb  add     rsp, 60h
0x1400058ef  pop     r14
0x1400058f1  pop     r12
0x1400058f3  pop     rdi
0x1400058f4  pop     rbp
0x1400058f5  pop     rbx
0x1400058f6  retn
0x1400058f7  mov     rax, [r15]
0x1400058fa  sub     rax, rcx
0x1400058fd  sar     rax, 1
0x140005900  jmp     loc_140005779
0x140005905  cmp     rax, r14
0x140005908  jnz     loc_140005A1C
0x14000590e  lea     rax, ds:1[r13*2]
0x140005916  mov     rcx, 3FFFFFFFFFFFFFF7h
0x140005920  cmp     rax, rsi
0x140005923  cmovb   rax, rsi
0x140005927  cmp     rax, rcx
0x14000592a  cmova   rax, rcx
0x14000592e  cmp     rsi, rax
0x140005931  ja      loc_140005A14
0x140005937  add     rax, 8
0x14000593b  mov     rcx, 7FFFFFFFFFFFFFFFh
0x140005945  and     rax, 0FFFFFFFFFFFFFFF8h
0x140005949  cmp     rax, rcx
0x14000594c  ja      loc_140005A14
0x140005952  lea     r15, [rax+rax]
0x140005956  call    cs:__imp_GetProcessHeap
0x14000595c  mov     r8, r15; dwBytes
0x14000595f  xor     edx, edx; dwFlags
0x140005961  mov     rcx, rax; hHeap
0x140005964  call    cs:__imp_HeapAlloc
0x14000596a  mov     rbp, rax
0x14000596d  test    rax, rax
0x140005970  jz      loc_140005A14
0x140005976  mov     rdx, [rbx]; Src
0x140005979  mov     rcx, [rbx+8]
0x14000597d  sub     rcx, rdx
0x140005980  sar     rcx, 1
0x140005983  lea     r12, [rcx+rcx]
0x140005987  mov     rcx, rax; void *
0x14000598a  lea     r8, [r12+2]; Size
0x14000598f  call    memcpy_0
0x140005994  mov     r13, [rbx]
0x140005997  cmp     r13, r14
0x14000599a  jz      short loc_1400059B0
0x14000599c  call    cs:__imp_GetProcessHeap
0x1400059a2  mov     r8, r13; lpMem
0x1400059a5  xor     edx, edx; dwFlags
0x1400059a7  mov     rcx, rax; hHeap
0x1400059aa  call    cs:__imp_HeapFree
0x1400059b0  lea     rax, [rbp-2]
0x1400059b4  mov     [rbx], rbp
0x1400059b7  add     rax, r15
0x1400059ba  lea     rcx, [r12+rbp]
0x1400059be  mov     [r14], rax
0x1400059c1  xor     r12d, r12d
0x1400059c4  jmp     loc_1400057B2
0x1400059c9  mov     rdx, [r14]
0x1400059cc  sub     rdx, rax
0x1400059cf  sar     rdx, 1
0x1400059d2  jmp     loc_1400057A9
0x1400059d7  xor     r12d, r12d
0x1400059da  mov     rax, [rbx]
0x1400059dd  lea     rcx, [rax+rdi*2]
0x1400059e1  mov     [rbx+8], rcx
0x1400059e5  mov     [rcx], r12w
0x1400059e9  mov     rcx, [rsp+88h+hKey]; hKey
0x1400059f1  test    rcx, rcx
0x1400059f4  jz      short loc_1400059FC
0x1400059f6  call    cs:__imp_RegCloseKey
0x1400059fc  mov     eax, 0Eh
0x140005a01  jmp     loc_14000574B
0x140005a06  mov     rax, [r15]
0x140005a09  sub     rax, rcx
0x140005a0c  sar     rax, 1
0x140005a0f  jmp     loc_1400057DC
0x140005a14  mov     rsi, rdi
0x140005a17  jmp     loc_140005727
0x140005a1c  mov     r13, [r14]
0x140005a1f  sub     r13, rax
0x140005a22  sar     r13, 1
0x140005a25  jmp     loc_14000590E
0x140005a2a  mov     rcx, [rsp+88h+hKey]; hKey
0x140005a32  test    rcx, rcx
0x140005a35  jz      short loc_140005A3D
0x140005a37  call    cs:__imp_RegCloseKey
0x140005a3d  mov     eax, edi
0x140005a3f  jmp     loc_14000574B
0x140005a44  mov     rcx, [rsp+88h+hKey]; hKey
0x140005a4c  test    rcx, rcx
0x140005a4f  jz      short loc_140005A57
0x140005a51  call    cs:__imp_RegCloseKey
0x140005a57  mov     eax, 65Eh
0x140005a5c  jmp     loc_14000574B
0x140005a61  mov     rbp, [rsp+88h+hKey]
0x140005a69  jmp     loc_140005661
```
