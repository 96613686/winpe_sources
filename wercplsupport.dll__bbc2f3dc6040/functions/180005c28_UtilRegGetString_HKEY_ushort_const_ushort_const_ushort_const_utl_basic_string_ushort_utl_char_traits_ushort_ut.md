# UtilRegGetString(HKEY__ *,ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,bool,bool)

- ea: `0x180005c28`
- end: `0x180005dfe`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEBG11PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@_N3@Z`
- size: `470`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180004d28`

## callees

- `0x180001680`
- `0x180002a18`
- `0x180002ad0`
- `0x180005c28`
- `0x180006754`
- `0x180006b64`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180005d8e`
- `msvcrt!wcsnlen` at `0x180005d8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005cbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005cbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005de6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005de6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005cff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005d5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005cff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005d5f`

## string_xrefs

- `0x180005ccf`: `StorePath`
- `0x180005d41`: `StorePath`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, DWORD pcbData)
{
  __int64 v6; // rdi
  unsigned int v8; // ebx
  HKEY *phkResult; // rax
  HKEY v10; // rbx
  LSTATUS ValueW; // eax
  _WORD *v12; // rcx
  size_t v13; // rax
  PVOID Block; // [rsp+40h] [rbp-20h] BYREF
  char *v15; // [rsp+48h] [rbp-18h]
  _WORD v16[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+28h] BYREF

  v6 = a5;
  Block = v16;
  v15 = (char *)v16;
  pcbData = 0;
  hkey = 0;
  v16[0] = 0;
  if ( !a5 )
    return 2147942487LL;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &Block,
                           &qword_180016858,
                           0) )
    goto LABEL_4;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x101u, phkResult)
    || (v10 = hkey, pcbData = 0, RegGetValueW(hkey, 0, L"StorePath", 2u, 0, 0, &pcbData)) )
  {
LABEL_15:
    v8 = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      v6,
      &Block);
    goto LABEL_16;
  }
  v15 = (char *)Block;
  *(_WORD *)Block = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                          &Block,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v10, 0, L"StorePath", 2u, 0, Block, &pcbData);
    v8 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v8 = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_11;
    }
    v13 = wcsnlen((const wchar_t *)Block, (unsigned __int64)pcbData >> 1);
    if ( v13 > (v15 - (_BYTE *)Block) >> 1 )
      __int2c();
    v15 = (char *)Block + 2 * v13;
    *(_WORD *)v15 = 0;
    goto LABEL_15;
  }
LABEL_4:
  v8 = -2147024882;
LABEL_11:
  v12 = *(_WORD **)v6;
  *(_QWORD *)(v6 + 8) = *(_QWORD *)v6;
  *v12 = 0;
LABEL_16:
  if ( Block != v16 )
    operator delete(Block);
  if ( hkey )
    RegCloseKey(hkey);
  return v8;
}

```

## disassembly

```asm
0x180005c28  mov     [rsp-8+arg_0], rbx
0x180005c2d  mov     [rsp-8+arg_8], rdi
0x180005c32  mov     [rsp-8+hkey], r9
0x180005c37  push    rbp
0x180005c38  mov     rbp, rsp
0x180005c3b  sub     rsp, 60h
0x180005c3f  mov     rdi, [rbp+arg_20]
0x180005c43  lea     rax, [rbp+var_10]
0x180005c47  mov     [rbp+Block], rax
0x180005c4b  lea     rax, [rbp+var_10]
0x180005c4f  mov     [rbp+var_18], rax
0x180005c53  xor     eax, eax
0x180005c55  mov     [rbp+arg_28], 0
0x180005c5c  mov     [rbp+hkey], 0
0x180005c64  mov     [rbp+var_10], ax
0x180005c68  test    rdi, rdi
0x180005c6b  jnz     short loc_180005C77
0x180005c6d  mov     eax, 80070057h
0x180005c72  jmp     loc_180005DEE
0x180005c77  xor     r8d, r8d
0x180005c7a  lea     rdx, qword_180016858
0x180005c81  lea     rcx, [rbp+Block]
0x180005c85  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180005c8a  test    al, al
0x180005c8c  jnz     short loc_180005C98
0x180005c8e  mov     ebx, 8007000Eh
0x180005c93  jmp     loc_180005D76
0x180005c98  lea     rcx, [rbp+hkey]
0x180005c9c  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180005ca1  mov     r9d, 101h; samDesired
0x180005ca7  mov     [rsp+60h+phkResult], rax; phkResult
0x180005cac  xor     r8d, r8d; ulOptions
0x180005caf  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\Windows E"...
0x180005cb6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005cbd  call    cs:__imp_RegOpenKeyExW
0x180005cc3  test    eax, eax
0x180005cc5  jnz     loc_180005DB6
0x180005ccb  mov     rbx, [rbp+hkey]
0x180005ccf  lea     r8, Value; "StorePath"
0x180005cd6  mov     [rbp+arg_28], eax
0x180005cd9  mov     r9d, 2; dwFlags
0x180005cdf  lea     rax, [rbp+arg_28]
0x180005ce3  xor     edx, edx; lpSubKey
0x180005ce5  mov     [rsp+60h+pcbData], rax; pcbData
0x180005cea  mov     rcx, rbx; hkey
0x180005ced  mov     [rsp+60h+pvData], 0; pvData
0x180005cf6  mov     [rsp+60h+phkResult], 0; pdwType
0x180005cff  call    cs:__imp_RegGetValueW
0x180005d05  test    eax, eax
0x180005d07  jnz     loc_180005DB6
0x180005d0d  mov     rcx, [rbp+Block]
0x180005d11  mov     [rbp+var_18], rcx
0x180005d15  mov     [rcx], ax
0x180005d18  lea     rcx, [rbp+Block]
0x180005d1c  mov     edx, [rbp+arg_28]
0x180005d1f  shr     rdx, 1
0x180005d22  inc     rdx
0x180005d25  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x180005d2a  test    al, al
0x180005d2c  jz      loc_180005C8E
0x180005d32  lea     rax, [rbp+arg_28]
0x180005d36  mov     r9d, 2; dwFlags
0x180005d3c  mov     [rsp+60h+pcbData], rax; pcbData
0x180005d41  lea     r8, Value; "StorePath"
0x180005d48  mov     rax, [rbp+Block]
0x180005d4c  xor     edx, edx; lpSubKey
0x180005d4e  mov     [rsp+60h+pvData], rax; pvData
0x180005d53  mov     rcx, rbx; hkey
0x180005d56  mov     [rsp+60h+phkResult], 0; pdwType
0x180005d5f  call    cs:__imp_RegGetValueW
0x180005d65  mov     ebx, eax
0x180005d67  test    eax, eax
0x180005d69  jz      short loc_180005D84
0x180005d6b  jle     short loc_180005D76
0x180005d6d  movzx   ebx, ax
0x180005d70  or      ebx, 80070000h
0x180005d76  mov     rcx, [rdi]
0x180005d79  xor     eax, eax
0x180005d7b  mov     [rdi+8], rcx
0x180005d7f  mov     [rcx], ax
0x180005d82  jmp     short loc_180005DC4
0x180005d84  mov     edx, [rbp+arg_28]
0x180005d87  mov     rcx, [rbp+Block]; Source
0x180005d8b  shr     rdx, 1; MaxCount
0x180005d8e  call    cs:__imp_wcsnlen
0x180005d94  mov     rcx, [rbp+var_18]
0x180005d98  mov     rdx, [rbp+Block]
0x180005d9c  sub     rcx, rdx
0x180005d9f  sar     rcx, 1
0x180005da2  cmp     rax, rcx
0x180005da5  jbe     short loc_180005DA9
0x180005da7  int     2Ch; Windows NT - assertion failure
0x180005da9  lea     rdx, [rdx+rax*2]
0x180005dad  xor     eax, eax
0x180005daf  mov     [rbp+var_18], rdx
0x180005db3  mov     [rdx], ax
0x180005db6  xor     ebx, ebx
0x180005db8  lea     rdx, [rbp+Block]
0x180005dbc  mov     rcx, rdi
0x180005dbf  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180005dc4  mov     rcx, [rbp+Block]; Block
0x180005dc8  lea     rax, [rbp+var_10]
0x180005dcc  cmp     rcx, rax
0x180005dcf  jz      short loc_180005DDD
0x180005dd1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180005dd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005ddd  mov     rcx, [rbp+hkey]; hKey
0x180005de1  test    rcx, rcx
0x180005de4  jz      short loc_180005DEC
0x180005de6  call    cs:__imp_RegCloseKey
0x180005dec  mov     eax, ebx
0x180005dee  mov     rbx, [rsp+60h+arg_0]
0x180005df3  mov     rdi, [rsp+60h+arg_8]
0x180005df8  add     rsp, 60h
0x180005dfc  pop     rbp
0x180005dfd  retn
```
