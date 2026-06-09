# UtilGetIFEOKeyForProcess(void *,ulong,ulong,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> *)

- ea: `0x18000f270`
- end: `0x18000f51f`
- name: `?UtilGetIFEOKeyForProcess@@YAJPEAXKKPEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000f528`
- `0x18002ab58`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x1800035e8`
- `0x180004a44`
- `0x18000f270`
- `0x180011648`
- `0x180011ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f31f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f31f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f432`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f40d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f453`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f40d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f453`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000f30b`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18000f30b`

## pseudocode

```c
__int64 __fastcall UtilGetIFEOKeyForProcess(HANDLE hProcess, __int64 a2, __int64 a3, HKEY *a4)
{
  __int64 v6; // rdi
  signed int LastError; // eax
  signed int v8; // ebx
  __int64 v9; // r8
  unsigned __int16 *v10; // r8
  unsigned __int16 *v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // r9
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  HKEY v16; // rcx
  LSTATUS v17; // edi
  HKEY v18; // rcx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v22[8]; // [rsp+48h] [rbp-B8h] BYREF
  void *v23[2]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD v24[8]; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  HKEY *v26; // [rsp+80h] [rbp-80h]
  WCHAR ExeName; // [rsp+90h] [rbp-70h] BYREF
  char v28[526]; // [rsp+92h] [rbp-6Eh] BYREF

  v23[0] = v24;
  v24[0] = 0;
  v23[1] = v24;
  v22[0] = 0;
  lpSubKey[0] = v22;
  ExeName = 0;
  lpSubKey[1] = v22;
  memset_0(v28, 0, 0x206u);
  dwSize = 260;
  if ( !hProcess )
  {
    v8 = -2147024809;
    goto LABEL_36;
  }
  v6 = -1;
  if ( QueryFullProcessImageNameW(hProcess, 0, &ExeName, &dwSize) )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&v28[2 * v9 - 2] );
    v8 = (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            v23,
                            &ExeName) == 0
       ? 0x8007000E
       : 0;
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
  }
  if ( v8 < 0 )
  {
LABEL_36:
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 161;
      goto LABEL_39;
    }
    goto LABEL_40;
  }
  if ( v23[0] )
  {
    do
      ++v6;
    while ( *((_WORD *)v23[0] + v6) );
    v11 = (unsigned __int16 *)((char *)v23[0] + 2 * v6);
    while ( 1 )
    {
      v10 = v11;
      if ( v11 <= v23[0] )
        break;
      v12 = *--v11;
      LOWORD(v12) = v12 - 47;
      if ( (unsigned __int16)v12 <= 0x2Du )
      {
        v13 = 0x200000000801LL;
        if ( _bittest64(&v13, v12) )
          break;
      }
    }
  }
  else
  {
    v10 = 0;
  }
  v8 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         lpSubKey,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\%ls",
         v10);
  if ( v8 >= 0 )
  {
    phkResult = 0;
    v26 = a4;
    v16 = *a4;
    *a4 = 0;
    if ( v16 )
      RegCloseKey(v16);
    v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 1u, &phkResult);
    if ( phkResult )
    {
      v18 = *v26;
      *v26 = phkResult;
      if ( v18 )
        RegCloseKey(v18);
    }
    if ( v17 )
    {
      v8 = v17 > 0 ? (unsigned __int16)v17 | 0x80070000 : v17;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 163;
        goto LABEL_39;
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 162;
LABEL_39:
      WPP_SF_d(v14[2], v15, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, (unsigned int)v8);
    }
  }
LABEL_40:
  if ( lpSubKey[0] != v22 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v23[0] != v24 )
    operator delete(v23[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f270  push    rbp
0x18000f272  push    rbx
0x18000f273  push    rsi
0x18000f274  push    rdi
0x18000f275  push    r12
0x18000f277  push    r14
0x18000f279  lea     rbp, [rsp-1B8h]
0x18000f281  sub     rsp, 2B8h
0x18000f288  mov     rax, cs:__security_cookie
0x18000f28f  xor     rax, rsp
0x18000f292  mov     [rbp+1E0h+var_40], rax
0x18000f299  xor     r14d, r14d
0x18000f29c  lea     rax, [rsp+2E0h+var_278]
0x18000f2a1  mov     [rsp+2E0h+var_288], rax
0x18000f2a6  mov     rbx, rcx
0x18000f2a9  lea     rax, [rsp+2E0h+var_278]
0x18000f2ae  mov     [rsp+2E0h+var_278], r14w
0x18000f2b4  mov     [rsp+2E0h+var_280], rax
0x18000f2b9  lea     rcx, [rbp+1E0h+var_24E]; void *
0x18000f2bd  lea     rax, [rsp+2E0h+var_298]
0x18000f2c2  mov     [rsp+2E0h+var_298], r14w
0x18000f2c8  mov     [rsp+2E0h+lpSubKey], rax
0x18000f2cd  xor     edx, edx; Val
0x18000f2cf  lea     rax, [rsp+2E0h+var_298]
0x18000f2d4  mov     [rbp+1E0h+ExeName], r14w
0x18000f2d9  mov     r8d, 206h; Size
0x18000f2df  mov     [rsp+2E0h+var_2A0], rax
0x18000f2e4  mov     rsi, r9
0x18000f2e7  call    memset_0
0x18000f2ec  mov     [rsp+2E0h+dwSize], 104h
0x18000f2f4  test    rbx, rbx
0x18000f2f7  jz      loc_18000F492
0x18000f2fd  lea     r9, [rsp+2E0h+dwSize]; lpdwSize
0x18000f302  xor     edx, edx; dwFlags
0x18000f304  lea     r8, [rbp+1E0h+ExeName]; lpExeName
0x18000f308  mov     rcx, rbx; hProcess
0x18000f30b  call    cs:__imp_QueryFullProcessImageNameW
0x18000f311  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f315  mov     r12d, 80004005h
0x18000f31b  test    eax, eax
0x18000f31d  jnz     short loc_18000F33C
0x18000f31f  call    cs:__imp_GetLastError
0x18000f325  mov     ebx, eax
0x18000f327  test    eax, eax
0x18000f329  jle     short loc_18000F334
0x18000f32b  movzx   ebx, ax
0x18000f32e  or      ebx, 80070000h
0x18000f334  test    ebx, ebx
0x18000f336  cmovns  ebx, r12d
0x18000f33a  jmp     short loc_18000F367
0x18000f33c  lea     rax, [rbp+1E0h+ExeName]
0x18000f340  mov     r8, rdi
0x18000f343  inc     r8
0x18000f346  cmp     [rax+r8*2], r14w
0x18000f34b  jnz     short loc_18000F343
0x18000f34d  lea     rdx, [rbp+1E0h+ExeName]
0x18000f351  lea     rcx, [rsp+2E0h+var_288]
0x18000f356  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18000f35b  neg     al
0x18000f35d  sbb     ebx, ebx
0x18000f35f  not     ebx
0x18000f361  and     ebx, 8007000Eh
0x18000f367  test    ebx, ebx
0x18000f369  js      loc_18000F497
0x18000f36f  mov     rdx, [rsp+2E0h+var_288]
0x18000f374  test    rdx, rdx
0x18000f377  jnz     short loc_18000F37E
0x18000f379  mov     r8, r14
0x18000f37c  jmp     short loc_18000F3B7
0x18000f37e  inc     rdi
0x18000f381  cmp     [rdx+rdi*2], r14w
0x18000f386  jnz     short loc_18000F37E
0x18000f388  lea     rcx, [rdx+rdi*2]
0x18000f38c  jmp     short loc_18000F3AF
0x18000f38e  sub     rcx, 2
0x18000f392  movzx   eax, word ptr [rcx]
0x18000f395  sub     ax, 2Fh ; '/'
0x18000f399  cmp     ax, 2Dh ; '-'
0x18000f39d  ja      short loc_18000F3AF
0x18000f39f  mov     r9, 200000000801h
0x18000f3a9  bt      r9, rax
0x18000f3ad  jb      short loc_18000F3B7
0x18000f3af  mov     r8, rcx
0x18000f3b2  cmp     rcx, rdx
0x18000f3b5  ja      short loc_18000F38E
0x18000f3b7  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000f3be  lea     rcx, [rsp+2E0h+lpSubKey]
0x18000f3c3  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18000f3c8  mov     ebx, eax
0x18000f3ca  test    eax, eax
0x18000f3cc  jns     short loc_18000F3F9
0x18000f3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3d5  lea     rax, WPP_GLOBAL_Control
0x18000f3dc  cmp     rcx, rax
0x18000f3df  jz      loc_18000F4C8
0x18000f3e5  test    byte ptr [rcx+1Ch], 1
0x18000f3e9  jz      loc_18000F4C8
0x18000f3ef  mov     edx, 0A2h
0x18000f3f4  jmp     loc_18000F4B5
0x18000f3f9  mov     [rsp+2E0h+var_268], r14
0x18000f3fe  mov     [rbp+1E0h+var_260], rsi
0x18000f402  mov     rcx, [rsi]; hKey
0x18000f405  mov     [rsi], r14
0x18000f408  test    rcx, rcx
0x18000f40b  jz      short loc_18000F413
0x18000f40d  call    cs:__imp_RegCloseKey
0x18000f413  mov     rdx, [rsp+2E0h+lpSubKey]; lpSubKey
0x18000f418  lea     rax, [rsp+2E0h+var_268]
0x18000f41d  mov     r9d, 1; samDesired
0x18000f423  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000f428  xor     r8d, r8d; ulOptions
0x18000f42b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f432  call    cs:__imp_RegOpenKeyExW
0x18000f438  mov     edi, eax
0x18000f43a  mov     rax, [rsp+2E0h+var_268]
0x18000f43f  test    rax, rax
0x18000f442  jz      short loc_18000F459
0x18000f444  mov     rdx, [rbp+1E0h+var_260]
0x18000f448  mov     rcx, [rdx]; hKey
0x18000f44b  mov     [rdx], rax
0x18000f44e  test    rcx, rcx
0x18000f451  jz      short loc_18000F459
0x18000f453  call    cs:__imp_RegCloseKey
0x18000f459  test    edi, edi
0x18000f45b  jz      short loc_18000F4C8
0x18000f45d  jg      short loc_18000F463
0x18000f45f  mov     ebx, edi
0x18000f461  jmp     short loc_18000F46C
0x18000f463  movzx   ebx, di
0x18000f466  or      ebx, 80070000h
0x18000f46c  test    ebx, ebx
0x18000f46e  cmovns  ebx, r12d
0x18000f472  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f479  lea     rax, WPP_GLOBAL_Control
0x18000f480  cmp     rcx, rax
0x18000f483  jz      short loc_18000F4C8
0x18000f485  test    byte ptr [rcx+1Ch], 1
0x18000f489  jz      short loc_18000F4C8
0x18000f48b  mov     edx, 0A3h
0x18000f490  jmp     short loc_18000F4B5
0x18000f492  mov     ebx, 80070057h
0x18000f497  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f49e  lea     rax, WPP_GLOBAL_Control
0x18000f4a5  cmp     rcx, rax
0x18000f4a8  jz      short loc_18000F4C8
0x18000f4aa  test    byte ptr [rcx+1Ch], 1
0x18000f4ae  jz      short loc_18000F4C8
0x18000f4b0  mov     edx, 0A1h
0x18000f4b5  mov     rcx, [rcx+10h]
0x18000f4b9  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18000f4c0  mov     r9d, ebx
0x18000f4c3  call    WPP_SF_d
0x18000f4c8  mov     rcx, [rsp+2E0h+lpSubKey]; void *
0x18000f4cd  lea     rax, [rsp+2E0h+var_298]
0x18000f4d2  cmp     rcx, rax
0x18000f4d5  jz      short loc_18000F4E3
0x18000f4d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f4de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f4e3  mov     rcx, [rsp+2E0h+var_288]; void *
0x18000f4e8  lea     rax, [rsp+2E0h+var_278]
0x18000f4ed  cmp     rcx, rax
0x18000f4f0  jz      short loc_18000F4FE
0x18000f4f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f4f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f4fe  mov     eax, ebx
0x18000f500  mov     rcx, [rbp+1E0h+var_40]
0x18000f507  xor     rcx, rsp; StackCookie
0x18000f50a  call    __security_check_cookie
0x18000f50f  add     rsp, 2B8h
0x18000f516  pop     r14
0x18000f518  pop     r12
0x18000f51a  pop     rdi
0x18000f51b  pop     rsi
0x18000f51c  pop     rbx
0x18000f51d  pop     rbp
0x18000f51e  retn
```
