# UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)

- ea: `0x14000c488`
- end: `0x14000c65e`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z`
- size: `470`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, DWORD pcbData)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000b70c`

## callees

- `0x140003224`
- `0x14000470c`
- `0x140004d70`
- `0x14000c488`
- `0x14000db44`
- `0x14000e258`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000c5ee`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14000c5ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c646`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c646`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c51d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c51d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000c55f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000c5bf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000c55f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000c5bf`

## string_xrefs

- `0x14000c52f`: `StorePath`
- `0x14000c5a1`: `StorePath`

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
  PVOID pvData; // [rsp+40h] [rbp-20h] BYREF
  char *v15; // [rsp+48h] [rbp-18h]
  _WORD v16[8]; // [rsp+50h] [rbp-10h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+28h] BYREF

  v6 = a5;
  pvData = v16;
  v15 = (char *)v16;
  pcbData = 0;
  hkey = 0;
  v16[0] = 0;
  if ( !a5 )
    return 2147942487LL;
  if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          (__int64)&pvData,
          &dword_1400241F4,
          0) )
    goto LABEL_4;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\Windows Error Reporting", 0, 0x101u, phkResult)
    || (v10 = hkey, pcbData = 0, RegGetValueW(hkey, 0, L"StorePath", 2u, 0, 0, &pcbData)) )
  {
LABEL_15:
    v8 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(v6, &pvData);
    goto LABEL_16;
  }
  v15 = (char *)pvData;
  *(_WORD *)pvData = 0;
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                          &pvData,
                          ((unsigned __int64)pcbData >> 1) + 1) )
  {
    ValueW = RegGetValueW(v10, 0, L"StorePath", 2u, 0, pvData, &pcbData);
    v8 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v8 = (unsigned __int16)ValueW | 0x80070000;
      goto LABEL_11;
    }
    v13 = wcsnlen((const wchar_t *)pvData, (unsigned __int64)pcbData >> 1);
    if ( v13 > (v15 - (_BYTE *)pvData) >> 1 )
      __int2c();
    v15 = (char *)pvData + 2 * v13;
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
  if ( pvData != v16 )
    operator delete(pvData, (const struct std::nothrow_t *)&std::nothrow);
  if ( hkey )
    RegCloseKey(hkey);
  return v8;
}

```

## disassembly

```asm
0x14000c488  mov     [rsp-8+arg_0], rbx
0x14000c48d  mov     [rsp-8+arg_8], rdi
0x14000c492  mov     [rsp-8+hkey], r9
0x14000c497  push    rbp
0x14000c498  mov     rbp, rsp
0x14000c49b  sub     rsp, 60h
0x14000c49f  mov     rdi, [rbp+arg_20]
0x14000c4a3  lea     rax, [rbp+var_10]
0x14000c4a7  mov     [rbp+var_20], rax
0x14000c4ab  lea     rax, [rbp+var_10]
0x14000c4af  mov     [rbp+var_18], rax
0x14000c4b3  xor     eax, eax
0x14000c4b5  mov     [rbp+arg_28], 0
0x14000c4bc  mov     [rbp+hkey], 0
0x14000c4c4  mov     [rbp+var_10], ax
0x14000c4c8  test    rdi, rdi
0x14000c4cb  jnz     short loc_14000C4D7
0x14000c4cd  mov     eax, 80070057h
0x14000c4d2  jmp     loc_14000C64E
0x14000c4d7  xor     r8d, r8d
0x14000c4da  lea     rdx, dword_1400241F4
0x14000c4e1  lea     rcx, [rbp+var_20]
0x14000c4e5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14000c4ea  test    al, al
0x14000c4ec  jnz     short loc_14000C4F8
0x14000c4ee  mov     ebx, 8007000Eh
0x14000c4f3  jmp     loc_14000C5D6
0x14000c4f8  lea     rcx, [rbp+hkey]
0x14000c4fc  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14000c501  mov     r9d, 101h; samDesired
0x14000c507  mov     [rsp+60h+phkResult], rax; phkResult
0x14000c50c  xor     r8d, r8d; ulOptions
0x14000c50f  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x14000c516  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000c51d  call    cs:__imp_RegOpenKeyExW
0x14000c523  test    eax, eax
0x14000c525  jnz     loc_14000C616
0x14000c52b  mov     rbx, [rbp+hkey]
0x14000c52f  lea     r8, aStorepath; "StorePath"
0x14000c536  mov     [rbp+arg_28], eax
0x14000c539  mov     r9d, 2; dwFlags
0x14000c53f  lea     rax, [rbp+arg_28]
0x14000c543  xor     edx, edx; lpSubKey
0x14000c545  mov     [rsp+60h+pcbData], rax; pcbData
0x14000c54a  mov     rcx, rbx; hkey
0x14000c54d  mov     [rsp+60h+pvData], 0; pvData
0x14000c556  mov     [rsp+60h+phkResult], 0; pdwType
0x14000c55f  call    cs:__imp_RegGetValueW
0x14000c565  test    eax, eax
0x14000c567  jnz     loc_14000C616
0x14000c56d  mov     rcx, [rbp+var_20]
0x14000c571  mov     [rbp+var_18], rcx
0x14000c575  mov     [rcx], ax
0x14000c578  lea     rcx, [rbp+var_20]
0x14000c57c  mov     edx, [rbp+arg_28]
0x14000c57f  shr     rdx, 1
0x14000c582  inc     rdx
0x14000c585  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x14000c58a  test    al, al
0x14000c58c  jz      loc_14000C4EE
0x14000c592  lea     rax, [rbp+arg_28]
0x14000c596  mov     r9d, 2; dwFlags
0x14000c59c  mov     [rsp+60h+pcbData], rax; pcbData
0x14000c5a1  lea     r8, aStorepath; "StorePath"
0x14000c5a8  mov     rax, [rbp+var_20]
0x14000c5ac  xor     edx, edx; lpSubKey
0x14000c5ae  mov     [rsp+60h+pvData], rax; pvData
0x14000c5b3  mov     rcx, rbx; hkey
0x14000c5b6  mov     [rsp+60h+phkResult], 0; pdwType
0x14000c5bf  call    cs:__imp_RegGetValueW
0x14000c5c5  mov     ebx, eax
0x14000c5c7  test    eax, eax
0x14000c5c9  jz      short loc_14000C5E4
0x14000c5cb  jle     short loc_14000C5D6
0x14000c5cd  movzx   ebx, ax
0x14000c5d0  or      ebx, 80070000h
0x14000c5d6  mov     rcx, [rdi]
0x14000c5d9  xor     eax, eax
0x14000c5db  mov     [rdi+8], rcx
0x14000c5df  mov     [rcx], ax
0x14000c5e2  jmp     short loc_14000C624
0x14000c5e4  mov     edx, [rbp+arg_28]
0x14000c5e7  mov     rcx, [rbp+var_20]; Source
0x14000c5eb  shr     rdx, 1; MaxCount
0x14000c5ee  call    cs:__imp_wcsnlen
0x14000c5f4  mov     rcx, [rbp+var_18]
0x14000c5f8  mov     rdx, [rbp+var_20]
0x14000c5fc  sub     rcx, rdx
0x14000c5ff  sar     rcx, 1
0x14000c602  cmp     rax, rcx
0x14000c605  jbe     short loc_14000C609
0x14000c607  int     2Ch; Windows NT - assertion failure
0x14000c609  lea     rdx, [rdx+rax*2]
0x14000c60d  xor     eax, eax
0x14000c60f  mov     [rbp+var_18], rdx
0x14000c613  mov     [rdx], ax
0x14000c616  xor     ebx, ebx
0x14000c618  lea     rdx, [rbp+var_20]
0x14000c61c  mov     rcx, rdi
0x14000c61f  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x14000c624  mov     rcx, [rbp+var_20]; void *
0x14000c628  lea     rax, [rbp+var_10]
0x14000c62c  cmp     rcx, rax
0x14000c62f  jz      short loc_14000C63D
0x14000c631  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c638  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c63d  mov     rcx, [rbp+hkey]; hKey
0x14000c641  test    rcx, rcx
0x14000c644  jz      short loc_14000C64C
0x14000c646  call    cs:__imp_RegCloseKey
0x14000c64c  mov     eax, ebx
0x14000c64e  mov     rbx, [rsp+60h+arg_0]
0x14000c653  mov     rdi, [rsp+60h+arg_8]
0x14000c658  add     rsp, 60h
0x14000c65c  pop     rbp
0x14000c65d  retn
```
