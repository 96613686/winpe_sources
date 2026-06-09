# CRegSetting::Load(HKEY__ *,ulong)

- ea: `0x18000cb80`
- end: `0x18000ceee`
- name: `?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z`
- size: `878`
- prototype: `int(CRegSetting *__hidden this, HKEY, unsigned int)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000c504`
- `0x18000cb20`
- `0x18002ebd0`
- `0x180040598`
- `0x18006230c`
- `0x18007e000`
- `0x1800a96e4`

## callees

- `0x18000cb80`
- `0x18000cf50`
- `0x18002c680`
- `0x1800459c0`
- `0x1800471c4`
- `0x18004bc54`
- `0x180053d3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cbd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ccc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cbd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ccc5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cc86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ce20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cc86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ce20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ccda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cbed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ccda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cd18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cc4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000cc4f`

## pseudocode

```c
__int64 __fastcall CRegSetting::Load(CRegSetting *this, HKEY a2, int a3)
{
  const WCHAR *v7; // rdx
  int v8; // edi
  __int64 v9; // r8
  unsigned int i; // ecx
  __int64 v11; // rax
  int v12; // eax
  int v13; // ecx
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  __int64 v16; // r15
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  LPVOID lpMem[2]; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  if ( a2 )
  {
    if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 9) )
    {
      if ( lpMem[0] != v19 )
        HeapFree(g_hWerheap, 0, lpMem[0]);
      return 2149285891LL;
    }
    if ( !*((_BYTE *)this + 1) || *(_BYTE *)this )
      goto LABEL_24;
    v7 = (const WCHAR *)*((_QWORD *)this + 4);
    if ( v7 != *((const WCHAR **)this + 5) )
    {
      if ( RegOpenKeyExW(a2, v7, 0, a3 | 0x20019, &hKey) )
      {
        v8 = -2147467259;
LABEL_14:
        if ( lpMem[0] != v19 )
          HeapFree(g_hWerheap, 0, lpMem[0]);
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)v8;
      }
      a2 = hKey;
    }
    if ( RegQueryValueExW(a2, *((LPCWSTR *)this + 8), 0, &Type, 0, &cbData) )
    {
      v8 = -2147467259;
      goto LABEL_14;
    }
    v9 = cbData;
    if ( Type - 1 <= 1 )
    {
      v9 = cbData + 1;
    }
    else
    {
      if ( Type != 7 )
        goto LABEL_27;
      v9 = cbData + 2;
    }
    cbData = v9;
LABEL_27:
    for ( i = 0; i < 0xB; ++i )
    {
      v11 = 8LL * i;
      if ( *(_DWORD *)((char *)&CRegSetting::s_typeMapping + v11 + 4) == Type )
      {
        v12 = *(_DWORD *)((char *)&CRegSetting::s_typeMapping + v11);
        goto LABEL_31;
      }
    }
    v12 = 9;
LABEL_31:
    v13 = *((_DWORD *)this + 1);
    if ( v13 != v12 && v13 != 9 )
    {
      if ( v13 == 5 )
      {
        if ( v12 != 1 )
        {
LABEL_53:
          v8 = -2147467259;
          goto LABEL_14;
        }
      }
      else if ( v13 == 1 )
      {
        if ( v12 != 5 )
          goto LABEL_53;
      }
      else if ( v13 || v12 != 1 )
      {
        goto LABEL_53;
      }
    }
    *((_DWORD *)this + 1) = v12;
    v14 = *((_QWORD *)this + 1);
    v15 = *((_QWORD *)this + 2) - v14;
    v16 = (unsigned int)v9;
    if ( (unsigned int)v9 > v15 )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               (unsigned int)v9,
                               v9,
                               &CRegSetting::s_typeMapping) )
      {
        v8 = -2147024882;
        goto LABEL_14;
      }
      memset_0(*((void **)this + 2), 0, v16 - v15);
      v14 = *((_QWORD *)this + 1);
    }
    *((_QWORD *)this + 2) = v16 + v14;
    if ( RegQueryValueExW(a2, *((LPCWSTR *)this + 8), 0, &Type, *((LPBYTE *)this + 1), &cbData) )
    {
      v8 = -2147467259;
      *((_QWORD *)this + 2) = *((_QWORD *)this + 1);
      goto LABEL_14;
    }
    utl::vector<unsigned char,utl::allocator<unsigned char>>::_Resize<,0>((char *)this + 8, cbData);
    if ( *((_DWORD *)this + 1) == 5 )
    {
      v8 = UtilExpandEnvironmentStrings(*((LPCWSTR *)this + 1));
      if ( v8 < 0 )
        goto LABEL_14;
      cbData = 2 * (((char *)lpMem[1] - (char *)lpMem[0]) >> 1) + 2;
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::assign<unsigned char *,void>(
                               (char *)this + 8,
                               lpMem[0],
                               (char *)lpMem[0] + cbData) )
      {
        v8 = -2147024882;
        goto LABEL_14;
      }
    }
    *(_BYTE *)this = 1;
LABEL_24:
    v8 = 0;
    goto LABEL_14;
  }
  if ( lpMem[0] != v19 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000cb80  push    rbp
0x18000cb82  push    rbx
0x18000cb83  push    rsi
0x18000cb84  push    rdi
0x18000cb85  push    r12
0x18000cb87  mov     rbp, rsp
0x18000cb8a  sub     rsp, 60h
0x18000cb8e  xor     r12d, r12d
0x18000cb91  mov     rbx, rcx
0x18000cb94  lea     rcx, [rbp+lpMem]; void *
0x18000cb98  mov     [rbp+hKey], r12
0x18000cb9c  mov     [rbp+Type], r12d
0x18000cba0  mov     esi, r8d
0x18000cba3  mov     [rbp+cbData], r12d
0x18000cba7  mov     rdi, rdx
0x18000cbaa  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18000cbaf  test    rdi, rdi
0x18000cbb2  jz      loc_18000CCED
0x18000cbb8  mov     rax, [rbx+48h]
0x18000cbbc  cmp     [rbx+40h], rax
0x18000cbc0  jnz     short loc_18000CC0A
0x18000cbc2  mov     r8, [rbp+lpMem]; lpMem
0x18000cbc6  lea     rax, [rbp+var_18]
0x18000cbca  cmp     r8, rax
0x18000cbcd  jz      short loc_18000CBE4
0x18000cbcf  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000cbd6  xor     edx, edx; dwFlags
0x18000cbd8  call    cs:__imp_HeapFree
0x18000cbdf  nop     dword ptr [rax+rax+00h]
0x18000cbe4  mov     rcx, [rbp+hKey]; hKey
0x18000cbe8  test    rcx, rcx
0x18000cbeb  jz      short loc_18000CBF9
0x18000cbed  call    cs:__imp_RegCloseKey
0x18000cbf4  nop     dword ptr [rax+rax+00h]
0x18000cbf9  mov     eax, 801B8003h
0x18000cbfe  add     rsp, 60h
0x18000cc02  pop     r12
0x18000cc04  pop     rdi
0x18000cc05  pop     rsi
0x18000cc06  pop     rbx
0x18000cc07  pop     rbp
0x18000cc08  retn
0x18000cc0a  mov     [rsp+60h+arg_0], r14
0x18000cc12  mov     [rsp+60h+arg_10], r15
0x18000cc1a  cmp     [rbx+1], r12b
0x18000cc1e  jz      loc_18000CD67
0x18000cc24  cmp     [rbx], r12b
0x18000cc27  jnz     loc_18000CD67
0x18000cc2d  mov     rdx, [rbx+20h]; lpSubKey
0x18000cc31  cmp     rdx, [rbx+28h]
0x18000cc35  jz      short loc_18000CC6A
0x18000cc37  lea     rax, [rbp+hKey]
0x18000cc3b  or      esi, 20019h
0x18000cc41  mov     r9d, esi; samDesired
0x18000cc44  mov     [rsp+60h+phkResult], rax; phkResult
0x18000cc49  xor     r8d, r8d; ulOptions
0x18000cc4c  mov     rcx, rdi; hKey
0x18000cc4f  call    cs:__imp_RegOpenKeyExW
0x18000cc56  nop     dword ptr [rax+rax+00h]
0x18000cc5b  test    eax, eax
0x18000cc5d  jz      short loc_18000CC66
0x18000cc5f  mov     edi, 80004005h
0x18000cc64  jmp     short loc_18000CC9F
0x18000cc66  mov     rdi, [rbp+hKey]
0x18000cc6a  mov     rdx, [rbx+40h]; lpValueName
0x18000cc6e  lea     rax, [rbp+cbData]
0x18000cc72  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000cc77  lea     r9, [rbp+Type]; lpType
0x18000cc7b  xor     r8d, r8d; lpReserved
0x18000cc7e  mov     [rsp+60h+phkResult], r12; lpData
0x18000cc83  mov     rcx, rdi; hKey
0x18000cc86  call    cs:__imp_RegQueryValueExW
0x18000cc8d  nop     dword ptr [rax+rax+00h]
0x18000cc92  test    eax, eax
0x18000cc94  jz      loc_18000CD6F
0x18000cc9a  mov     edi, 80004005h
0x18000cc9f  mov     r8, [rbp+lpMem]; lpMem
0x18000cca3  lea     rax, [rbp+var_18]
0x18000cca7  mov     r15, [rsp+60h+arg_10]
0x18000ccaf  mov     r14, [rsp+60h+arg_0]
0x18000ccb7  cmp     r8, rax
0x18000ccba  jz      short loc_18000CCD1
0x18000ccbc  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000ccc3  xor     edx, edx; dwFlags
0x18000ccc5  call    cs:__imp_HeapFree
0x18000cccc  nop     dword ptr [rax+rax+00h]
0x18000ccd1  mov     rcx, [rbp+hKey]; hKey
0x18000ccd5  test    rcx, rcx
0x18000ccd8  jz      short loc_18000CCE6
0x18000ccda  call    cs:__imp_RegCloseKey
0x18000cce1  nop     dword ptr [rax+rax+00h]
0x18000cce6  mov     eax, edi
0x18000cce8  jmp     loc_18000CBFE
0x18000cced  mov     r8, [rbp+lpMem]; lpMem
0x18000ccf1  lea     rax, [rbp+var_18]
0x18000ccf5  cmp     r8, rax
0x18000ccf8  jz      short loc_18000CD0F
0x18000ccfa  mov     rcx, cs:?g_hWerheap@@3PEAXEA; hHeap
0x18000cd01  xor     edx, edx; dwFlags
0x18000cd03  call    cs:__imp_HeapFree
0x18000cd0a  nop     dword ptr [rax+rax+00h]
0x18000cd0f  mov     rcx, [rbp+hKey]; hKey
0x18000cd13  test    rcx, rcx
0x18000cd16  jz      short loc_18000CD24
0x18000cd18  call    cs:__imp_RegCloseKey
0x18000cd1f  nop     dword ptr [rax+rax+00h]
0x18000cd24  mov     eax, 80070057h
0x18000cd29  add     rsp, 60h
0x18000cd2d  pop     r12
0x18000cd2f  pop     rdi
0x18000cd30  pop     rsi
0x18000cd31  pop     rbx
0x18000cd32  pop     rbp
0x18000cd33  retn
0x18000cd35  mov     rdx, [rbp+lpMem]
0x18000cd39  lea     rcx, [rbx+8]
0x18000cd3d  mov     rax, [rbp+var_20]
0x18000cd41  sub     rax, rdx
0x18000cd44  sar     rax, 1
0x18000cd47  lea     eax, ds:2[rax*2]
0x18000cd4e  mov     r8d, eax
0x18000cd51  add     r8, rdx
0x18000cd54  mov     [rbp+cbData], eax
0x18000cd57  call    ??$assign@PEAEX@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_NPEAE0@Z; utl::vector<uchar,utl::allocator<uchar>>::assign<uchar *,void>(uchar *,uchar *)
0x18000cd5c  test    al, al
0x18000cd5e  jz      loc_18000CEE4
0x18000cd64  mov     byte ptr [rbx], 1
0x18000cd67  mov     edi, r12d
0x18000cd6a  jmp     loc_18000CC9F
0x18000cd6f  mov     edx, [rbp+Type]
0x18000cd72  mov     r8d, [rbp+cbData]
0x18000cd76  lea     eax, [rdx-1]
0x18000cd79  cmp     eax, 1
0x18000cd7c  jbe     loc_18000CE6C
0x18000cd82  cmp     edx, 7
0x18000cd85  jz      loc_18000CE66
0x18000cd8b  mov     ecx, r12d
0x18000cd8e  lea     r9, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x18000cd95  cmp     ecx, 0Bh
0x18000cd98  jnb     short loc_18000CDF2
0x18000cd9a  mov     eax, ecx
0x18000cd9c  lea     rax, ds:0[rax*8]
0x18000cda4  cmp     [rax+r9+4], edx
0x18000cda9  jnz     short loc_18000CDEE
0x18000cdab  mov     eax, [rax+r9]
0x18000cdaf  mov     ecx, [rbx+4]
0x18000cdb2  cmp     ecx, eax
0x18000cdb4  jnz     loc_18000CE78
0x18000cdba  mov     [rbx+4], eax
0x18000cdbd  mov     rax, [rbx+8]
0x18000cdc1  mov     rsi, [rbx+10h]
0x18000cdc5  sub     rsi, rax
0x18000cdc8  mov     r15d, r8d
0x18000cdcb  cmp     r15, rsi
0x18000cdce  jbe     short loc_18000CDF9
0x18000cdd0  mov     edx, r15d
0x18000cdd3  lea     rcx, [rbx+8]
0x18000cdd7  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x18000cddc  test    al, al
0x18000cdde  jnz     loc_18000CEB8
0x18000cde4  mov     edi, 8007000Eh
0x18000cde9  jmp     loc_18000CC9F
0x18000cdee  inc     ecx
0x18000cdf0  jmp     short loc_18000CD95
0x18000cdf2  mov     eax, 9
0x18000cdf7  jmp     short loc_18000CDAF
0x18000cdf9  add     rax, r15
0x18000cdfc  lea     r9, [rbp+Type]; lpType
0x18000ce00  mov     [rbx+10h], rax
0x18000ce04  xor     r8d, r8d; lpReserved
0x18000ce07  mov     rdx, [rbx+40h]; lpValueName
0x18000ce0b  lea     rax, [rbp+cbData]
0x18000ce0f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18000ce14  mov     rcx, rdi; hKey
0x18000ce17  mov     rax, [rbx+8]
0x18000ce1b  mov     [rsp+60h+phkResult], rax; lpData
0x18000ce20  call    cs:__imp_RegQueryValueExW
0x18000ce27  nop     dword ptr [rax+rax+00h]
0x18000ce2c  test    eax, eax
0x18000ce2e  jnz     loc_18000CED2
0x18000ce34  mov     edx, [rbp+cbData]
0x18000ce37  lea     rcx, [rbx+8]
0x18000ce3b  call    ??$_Resize@$$V$0A@@?$vector@EV?$allocator@E@utl@@@utl@@AEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::_Resize<,0>(unsigned __int64)
0x18000ce40  cmp     dword ptr [rbx+4], 5
0x18000ce44  jnz     loc_18000CD64
0x18000ce4a  mov     rcx, [rbx+8]; lpSrc
0x18000ce4e  lea     rdx, [rbp+lpMem]
0x18000ce52  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18000ce57  mov     edi, eax
0x18000ce59  test    eax, eax
0x18000ce5b  js      loc_18000CC9F
0x18000ce61  jmp     loc_18000CD35
0x18000ce66  add     r8d, 2
0x18000ce6a  jmp     short loc_18000CE6F
0x18000ce6c  inc     r8d
0x18000ce6f  mov     [rbp+cbData], r8d
0x18000ce73  jmp     loc_18000CD8B
0x18000ce78  cmp     ecx, 9
0x18000ce7b  jz      loc_18000CDBA
0x18000ce81  cmp     ecx, 5
0x18000ce84  jnz     short loc_18000CE91
0x18000ce86  cmp     eax, 1
0x18000ce89  jz      loc_18000CDBA
0x18000ce8f  jmp     short loc_18000CEAE
0x18000ce91  cmp     ecx, 1
0x18000ce94  jnz     short loc_18000CEA1
0x18000ce96  cmp     eax, 5
0x18000ce99  jz      loc_18000CDBA
0x18000ce9f  jmp     short loc_18000CEAE
0x18000cea1  test    ecx, ecx
0x18000cea3  jnz     short loc_18000CEAE
0x18000cea5  cmp     eax, 1
0x18000cea8  jz      loc_18000CDBA
0x18000ceae  mov     edi, 80004005h
0x18000ceb3  jmp     loc_18000CC9F
0x18000ceb8  mov     rcx, [rbx+10h]; void *
0x18000cebc  mov     r8, r15
0x18000cebf  sub     r8, rsi; Size
0x18000cec2  xor     edx, edx; Val
0x18000cec4  call    memset_0
0x18000cec9  mov     rax, [rbx+8]
0x18000cecd  jmp     loc_18000CDF9
0x18000ced2  mov     rax, [rbx+8]
0x18000ced6  mov     edi, 80004005h
0x18000cedb  mov     [rbx+10h], rax
0x18000cedf  jmp     loc_18000CC9F
0x18000cee4  mov     edi, 8007000Eh
0x18000cee9  jmp     loc_18000CC9F
```
