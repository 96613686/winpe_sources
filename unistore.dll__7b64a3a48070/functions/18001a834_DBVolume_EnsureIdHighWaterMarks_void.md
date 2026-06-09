# DBVolume::_EnsureIdHighWaterMarks(void)

- ea: `0x18001a834`
- end: `0x18001aa24`
- name: `?_EnsureIdHighWaterMarks@DBVolume@@IEAAJXZ`
- size: `496`
- prototype: `__int64 __fastcall(DBVolume *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800191e0`

## callees

- `0x1800068f0`
- `0x180019584`
- `0x18001a6c4`
- `0x18001a834`
- `0x18001bd48`
- `0x18001c080`
- `0x18001c2e0`
- `0x180078a40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a9e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a9e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a914`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a914`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18001a8c3`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18001a8c3`

## string_xrefs

- `0x18001a990`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001aa03`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`

## pseudocode

```c
__int64 __fastcall DBVolume::_EnsureIdHighWaterMarks(DBVolume *this)
{
  __int64 v2; // r8
  unsigned __int64 v3; // rcx
  LPCWSTR v4; // rdx
  LSTATUS v5; // eax
  unsigned int updated; // ebx
  HKEY *v7; // rax
  LSTATUS v8; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-20h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h]
  _BYTE v14[16]; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+18h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&lpSubKey);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &lpSubKey,
                           *((_QWORD *)this + 5),
                           (__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 1) )
  {
    updated = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      3855);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpSubKey);
    return updated;
  }
  v2 = v13;
  v3 = 0;
  v4 = lpSubKey;
  if ( (v13 - (__int64)lpSubKey) >> 1 )
  {
    do
    {
      if ( v4[v3] == 92 )
      {
        v4[v3] = 95;
        v2 = v13;
        v4 = lpSubKey;
      }
      ++v3;
    }
    while ( v3 < (v2 - (__int64)v4) >> 1 );
  }
  dwDisposition = 0;
  phkResult = 0;
  v5 = RegCreateKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store\\HighWaterMarks", &phkResult);
  updated = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      updated = (unsigned __int16)v5 | 0x80070000;
    v10 = 3872;
    goto LABEL_17;
  }
  v7 = tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>((HKEY *)this + 31);
  v8 = RegCreateKeyExW(phkResult, lpSubKey, 0, 0, 1u, 0x2001Fu, 0, v7, &dwDisposition);
  updated = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      updated = (unsigned __int16)v8 | 0x80070000;
    v10 = 3885;
LABEL_17:
    v11 = 0;
LABEL_18:
    Log_UnistoreHREvent_0(
      updated,
      v11,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v10);
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( lpSubKey != (LPCWSTR)v14 )
      operator delete((void *)lpSubKey);
    return updated;
  }
  if ( dwDisposition == 2 )
  {
    updated = DBVolume::_UpdatePrimaryIdTableFromKey((HKEY *)this);
    if ( (updated & 0x80000000) != 0 )
    {
      v10 = 3889;
      v11 = 1;
      goto LABEL_18;
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( lpSubKey != (LPCWSTR)v14 )
    operator delete((void *)lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x18001a834  mov     [rsp-8+arg_10], rbx
0x18001a839  mov     [rsp-8+arg_18], rdi
0x18001a83e  push    rbp
0x18001a83f  mov     rbp, rsp
0x18001a842  sub     rsp, 70h
0x18001a846  mov     rdi, rcx
0x18001a849  lea     rcx, [rbp+lpSubKey]
0x18001a84d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001a852  mov     rdx, [rdi+28h]
0x18001a856  lea     rcx, [rbp+lpSubKey]
0x18001a85a  mov     r8, [rdi+30h]
0x18001a85e  sub     r8, rdx
0x18001a861  sar     r8, 1
0x18001a864  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001a869  test    al, al
0x18001a86b  jz      loc_18001A9FE
0x18001a871  mov     r8, [rbp+var_18]
0x18001a875  xor     ecx, ecx
0x18001a877  mov     rdx, [rbp+lpSubKey]
0x18001a87b  mov     rax, r8
0x18001a87e  sub     rax, rdx
0x18001a881  sar     rax, 1
0x18001a884  jz      short loc_18001A8A2
0x18001a886  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x18001a88b  jz      loc_18001A96A
0x18001a891  mov     rax, r8
0x18001a894  inc     rcx
0x18001a897  sub     rax, rdx
0x18001a89a  sar     rax, 1
0x18001a89d  cmp     rcx, rax
0x18001a8a0  jb      short loc_18001A886
0x18001a8a2  lea     r8, [rbp+phkResult]; phkResult
0x18001a8a6  mov     [rbp+dwDisposition], 0
0x18001a8ad  lea     rdx, ?c_wszUnistoreHighWaterMarkKey@@3QBGB; "Software\\Microsoft\\Unified Store\\Hig"...
0x18001a8b4  mov     [rbp+phkResult], 0
0x18001a8bc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a8c3  call    cs:__imp_RegCreateKeyW
0x18001a8c9  mov     ebx, eax
0x18001a8cb  test    eax, eax
0x18001a8cd  jnz     loc_18001A97D
0x18001a8d3  lea     rcx, [rdi+0F8h]
0x18001a8da  call    ??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z; tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001a8df  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18001a8e3  lea     rcx, [rbp+dwDisposition]
0x18001a8e7  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x18001a8ec  xor     r9d, r9d; lpClass
0x18001a8ef  mov     rcx, [rbp+phkResult]; hKey
0x18001a8f3  xor     r8d, r8d; Reserved
0x18001a8f6  mov     [rsp+70h+var_38], rax; phkResult
0x18001a8fb  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001a904  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x18001a90c  mov     [rsp+70h+dwOptions], 1; dwOptions
0x18001a914  call    cs:__imp_RegCreateKeyExW
0x18001a91a  mov     ebx, eax
0x18001a91c  test    eax, eax
0x18001a91e  jnz     loc_18001A9EB
0x18001a924  cmp     [rbp+dwDisposition], 2
0x18001a928  jz      loc_18001A9C4
0x18001a92e  mov     rcx, [rbp+phkResult]; hKey
0x18001a932  test    rcx, rcx
0x18001a935  jz      short loc_18001A93D
0x18001a937  call    cs:__imp_RegCloseKey
0x18001a93d  mov     rcx, [rbp+lpSubKey]; Block
0x18001a941  lea     rax, [rbp+var_10]
0x18001a945  cmp     rcx, rax
0x18001a948  jz      short loc_18001A956
0x18001a94a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001a951  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a956  xor     eax, eax
0x18001a958  lea     r11, [rsp+70h+var_s0]
0x18001a95d  mov     rbx, [r11+20h]
0x18001a961  mov     rdi, [r11+28h]
0x18001a965  mov     rsp, r11
0x18001a968  pop     rbp
0x18001a969  retn
0x18001a96a  mov     word ptr [rdx+rcx*2], 5Fh ; '_'
0x18001a970  mov     r8, [rbp+var_18]
0x18001a974  mov     rdx, [rbp+lpSubKey]
0x18001a978  jmp     loc_18001A891
0x18001a97d  jle     short loc_18001A988
0x18001a97f  movzx   ebx, ax
0x18001a982  or      ebx, 80070000h
0x18001a988  mov     r9d, 0F20h
0x18001a98e  xor     edx, edx
0x18001a990  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001a997  mov     ecx, ebx
0x18001a999  call    Log_UnistoreHREvent_0
0x18001a99e  mov     rcx, [rbp+phkResult]; hKey
0x18001a9a2  test    rcx, rcx
0x18001a9a5  jnz     short loc_18001A9E3
0x18001a9a7  mov     rcx, [rbp+lpSubKey]; Block
0x18001a9ab  lea     rax, [rbp+var_10]
0x18001a9af  cmp     rcx, rax
0x18001a9b2  jz      short loc_18001A9C0
0x18001a9b4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18001a9bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a9c0  mov     eax, ebx
0x18001a9c2  jmp     short loc_18001A958
0x18001a9c4  mov     rcx, rdi; this
0x18001a9c7  call    ?_UpdatePrimaryIdTableFromKey@DBVolume@@IEAAJXZ; DBVolume::_UpdatePrimaryIdTableFromKey(void)
0x18001a9cc  mov     ebx, eax
0x18001a9ce  test    eax, eax
0x18001a9d0  jns     loc_18001A92E
0x18001a9d6  mov     r9d, 0F31h
0x18001a9dc  mov     edx, 1
0x18001a9e1  jmp     short loc_18001A990
0x18001a9e3  call    cs:__imp_RegCloseKey
0x18001a9e9  jmp     short loc_18001A9A7
0x18001a9eb  jle     short loc_18001A9F6
0x18001a9ed  movzx   ebx, ax
0x18001a9f0  or      ebx, 80070000h
0x18001a9f6  mov     r9d, 0F2Dh
0x18001a9fc  jmp     short loc_18001A98E
0x18001a9fe  mov     ebx, 8007000Eh
0x18001aa03  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001aa0a  mov     ecx, ebx
0x18001aa0c  mov     r9d, 0F0Fh
0x18001aa12  xor     edx, edx
0x18001aa14  call    Log_UnistoreHREvent_0
0x18001aa19  lea     rcx, [rbp+lpSubKey]
0x18001aa1d  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18001aa22  jmp     short loc_18001A9C0
```
