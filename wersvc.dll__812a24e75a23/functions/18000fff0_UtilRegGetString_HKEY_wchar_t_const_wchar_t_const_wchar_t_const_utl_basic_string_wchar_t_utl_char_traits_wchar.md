# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x18000fff0`
- end: `0x1800101d3`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `483`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, LPCWSTR lpValue@<r8>, __int64, DWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000ec60`
- `0x18002d084`
- `0x1800313b0`

## callees

- `0x1800029f4`
- `0x180007cc8`
- `0x180008dac`
- `0x18000fff0`
- `0x180011648`
- `0x180011bf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010092`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010092`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800101b2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800100d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001012a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800100d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001012a`
- `ntdll!wcsnlen` at `0x18001015a`
- `ntdll!wcsnlen` at `0x18001015a`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValue, _WORD *a4, __int64 a5, DWORD pcbData)
{
  __int64 v6; // rsi
  unsigned __int64 v12; // r8
  unsigned int v13; // ebx
  HKEY *phkResult; // rax
  LSTATUS ValueW; // eax
  HKEY v16; // r14
  _WORD *v17; // rcx
  size_t v18; // rax
  PVOID pvData; // [rsp+40h] [rbp-20h] BYREF
  char *v20; // [rsp+48h] [rbp-18h]
  _WORD v21[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+90h] [rbp+30h] BYREF

  v6 = a5;
  pvData = v21;
  pcbData = 0;
  v20 = (char *)v21;
  hkey = 0;
  v21[0] = 0;
  if ( !a5 )
    return 2147942487LL;
  if ( a4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
    if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
            (__int64)&pvData,
            a4,
            v12) )
      goto LABEL_7;
  }
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  ValueW = RegOpenKeyExW(hKey, lpSubKey, 0, 0x101u, phkResult);
  v13 = ValueW;
  if ( ValueW
    || (v16 = hkey, pcbData = 0, ValueW = RegGetValueW(hkey, 0, lpValue, 2u, 0, 0, &pcbData), (v13 = ValueW) != 0) )
  {
    if ( !a4 )
    {
LABEL_14:
      if ( ValueW > 0 )
        v13 = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_16;
    }
LABEL_20:
    v13 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v6, &pvData);
    goto LABEL_21;
  }
  v20 = (char *)pvData;
  *(_WORD *)pvData = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &pvData,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v16, 0, lpValue, 2u, 0, pvData, &pcbData);
    v13 = ValueW;
    if ( ValueW )
      goto LABEL_14;
    v18 = wcsnlen((const wchar_t *)pvData, (unsigned __int64)pcbData >> 1);
    if ( v18 > (v20 - (_BYTE *)pvData) >> 1 )
      __int2c();
    v20 = (char *)pvData + 2 * v18;
    *(_WORD *)v20 = 0;
    goto LABEL_20;
  }
LABEL_7:
  v13 = -2147024882;
LABEL_16:
  v17 = *(_WORD **)v6;
  *(_QWORD *)(v6 + 8) = *(_QWORD *)v6;
  *v17 = 0;
LABEL_21:
  if ( pvData != v21 )
    operator delete(pvData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hkey )
    RegCloseKey(hkey);
  return v13;
}

```

## disassembly

```asm
0x18000fff0  mov     [rsp-28h+arg_8], rbx
0x18000fff5  mov     [rsp-28h+arg_10], rsi
0x18000fffa  push    rbp
0x18000fffb  push    rdi
0x18000fffc  push    r12
0x18000fffe  push    r14
0x180010000  push    r15
0x180010002  mov     rbp, rsp
0x180010005  sub     rsp, 60h
0x180010009  mov     rsi, [rbp+arg_20]
0x18001000d  lea     rax, [rbp+var_10]
0x180010011  xor     r12d, r12d
0x180010014  mov     [rbp+var_20], rax
0x180010018  mov     [rbp+arg_28], r12d
0x18001001c  lea     rax, [rbp+var_10]
0x180010020  mov     [rbp+var_18], rax
0x180010024  mov     rdi, r9
0x180010027  mov     [rbp+hkey], r12
0x18001002b  mov     r15, r8
0x18001002e  mov     [rbp+var_10], r12w
0x180010033  mov     rbx, rdx
0x180010036  mov     r14, rcx
0x180010039  test    rsi, rsi
0x18001003c  jnz     short loc_180010048
0x18001003e  mov     eax, 80070057h
0x180010043  jmp     loc_1800101BA
0x180010048  test    rdi, rdi
0x18001004b  jz      short loc_180010075
0x18001004d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010051  inc     r8
0x180010054  cmp     [r9+r8*2], r12w
0x180010059  jnz     short loc_180010051
0x18001005b  mov     rdx, rdi
0x18001005e  lea     rcx, [rbp+var_20]
0x180010062  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180010067  test    al, al
0x180010069  jnz     short loc_180010075
0x18001006b  mov     ebx, 8007000Eh
0x180010070  jmp     loc_180010143
0x180010075  lea     rcx, [rbp+hkey]
0x180010079  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001007e  mov     r9d, 101h; samDesired
0x180010084  mov     [rsp+60h+phkResult], rax; phkResult
0x180010089  xor     r8d, r8d; ulOptions
0x18001008c  mov     rdx, rbx; lpSubKey
0x18001008f  mov     rcx, r14; hKey
0x180010092  call    cs:__imp_RegOpenKeyExW
0x180010098  mov     ebx, eax
0x18001009a  test    eax, eax
0x18001009c  jz      short loc_1800100AC
0x18001009e  test    rdi, rdi
0x1800100a1  jnz     loc_180010181
0x1800100a7  jmp     loc_180010136
0x1800100ac  mov     r14, [rbp+hkey]
0x1800100b0  lea     rax, [rbp+arg_28]
0x1800100b4  mov     [rsp+60h+pcbData], rax; pcbData
0x1800100b9  mov     r9d, 2; dwFlags
0x1800100bf  mov     [rsp+60h+pvData], r12; pvData
0x1800100c4  mov     r8, r15; lpValue
0x1800100c7  xor     edx, edx; lpSubKey
0x1800100c9  mov     [rsp+60h+phkResult], r12; pdwType
0x1800100ce  mov     rcx, r14; hkey
0x1800100d1  mov     [rbp+arg_28], r12d
0x1800100d5  call    cs:__imp_RegGetValueW
0x1800100db  mov     ebx, eax
0x1800100dd  test    eax, eax
0x1800100df  jnz     short loc_18001009E
0x1800100e1  mov     rcx, [rbp+var_20]
0x1800100e5  mov     [rbp+var_18], rcx
0x1800100e9  mov     [rcx], r12w
0x1800100ed  lea     rcx, [rbp+var_20]
0x1800100f1  mov     edx, [rbp+arg_28]
0x1800100f4  shr     rdx, 1
0x1800100f7  inc     rdx
0x1800100fa  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x1800100ff  test    al, al
0x180010101  jz      loc_18001006B
0x180010107  lea     rax, [rbp+arg_28]
0x18001010b  mov     r8, r15; lpValue
0x18001010e  mov     [rsp+60h+pcbData], rax; pcbData
0x180010113  lea     r9d, [rbx+2]; dwFlags
0x180010117  mov     rax, [rbp+var_20]
0x18001011b  xor     edx, edx; lpSubKey
0x18001011d  mov     [rsp+60h+pvData], rax; pvData
0x180010122  mov     rcx, r14; hkey
0x180010125  mov     [rsp+60h+phkResult], r12; pdwType
0x18001012a  call    cs:__imp_RegGetValueW
0x180010130  mov     ebx, eax
0x180010132  test    eax, eax
0x180010134  jz      short loc_180010150
0x180010136  test    eax, eax
0x180010138  jle     short loc_180010143
0x18001013a  movzx   ebx, ax
0x18001013d  or      ebx, 80070000h
0x180010143  mov     rcx, [rsi]
0x180010146  mov     [rsi+8], rcx
0x18001014a  mov     [rcx], r12w
0x18001014e  jmp     short loc_180010190
0x180010150  mov     edx, [rbp+arg_28]
0x180010153  mov     rcx, [rbp+var_20]; Source
0x180010157  shr     rdx, 1; MaxCount
0x18001015a  call    cs:__imp_wcsnlen
0x180010160  mov     rcx, [rbp+var_18]
0x180010164  mov     rdx, [rbp+var_20]
0x180010168  sub     rcx, rdx
0x18001016b  sar     rcx, 1
0x18001016e  cmp     rax, rcx
0x180010171  jbe     short loc_180010175
0x180010173  int     2Ch; Windows NT - assertion failure
0x180010175  lea     rdx, [rdx+rax*2]
0x180010179  mov     [rbp+var_18], rdx
0x18001017d  mov     [rdx], r12w
0x180010181  lea     rdx, [rbp+var_20]
0x180010185  mov     rcx, rsi
0x180010188  mov     ebx, r12d
0x18001018b  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180010190  mov     rcx, [rbp+var_20]; void *
0x180010194  lea     rax, [rbp+var_10]
0x180010198  cmp     rcx, rax
0x18001019b  jz      short loc_1800101A9
0x18001019d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800101a4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800101a9  mov     rcx, [rbp+hkey]; hKey
0x1800101ad  test    rcx, rcx
0x1800101b0  jz      short loc_1800101B8
0x1800101b2  call    cs:__imp_RegCloseKey
0x1800101b8  mov     eax, ebx
0x1800101ba  lea     r11, [rsp+60h+var_s0]
0x1800101bf  mov     rbx, [r11+38h]
0x1800101c3  mov     rsi, [r11+40h]
0x1800101c7  mov     rsp, r11
0x1800101ca  pop     r15
0x1800101cc  pop     r14
0x1800101ce  pop     r12
0x1800101d0  pop     rdi
0x1800101d1  pop     rbp
0x1800101d2  retn
```
