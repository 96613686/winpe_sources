# LoadOfflineRegistryKey

- ea: `0x180006f84`
- end: `0x1800070e8`
- name: `LoadOfflineRegistryKey`
- size: `356`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800056a0`

## callees

- `0x180001de0`
- `0x180006f84`
- `0x180007178`
- `0x180009e30`
- `0x180010448`
- `0x180010de4`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180007087`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180007087`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180007044`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180007044`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007077`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007077`

## pseudocode

```c
__int64 __fastcall LoadOfflineRegistryKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  const WCHAR *v4; // rdi
  HKEY v5; // r15
  int v7; // eax
  const WCHAR *v8; // r14
  int KeyW; // ebx
  int LoadedHiveKeyNameInternal; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r8
  HKEY v17; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpSubKey; // [rsp+28h] [rbp-D8h] BYREF
  LPCWSTR lpFile[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t v20[256]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = 0;
  lpFile[0] = 0;
  v5 = 0;
  lpSubKey = 0;
  v17 = 0;
  v7 = SczAllocConcat2Sz(lpFile, a2, a3);
  v8 = lpFile[0];
  KeyW = v7;
  if ( v7 < 0 )
    goto LABEL_14;
  LoadedHiveKeyNameInternal = GetLoadedHiveKeyNameInternal(lpFile[0], v20);
  KeyW = 0;
  if ( LoadedHiveKeyNameInternal < 0 )
    KeyW = LoadedHiveKeyNameInternal | 0x10000000;
  if ( KeyW < 0 )
    goto LABEL_10;
  v11 = SczAllocFromSz(&lpSubKey, v20);
  v4 = lpSubKey;
  KeyW = v11;
  if ( v11 >= 0 )
  {
    if ( (int)WrpRegOpenKeyWithBackupRestore(v12, lpSubKey, v13, &v17) >= 0
      || (KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, v4, v8), KeyW >= 0)
      && (*(_DWORD *)(a4 + 8) = 1, KeyW = WrpRegOpenKeyWithBackupRestore(v14, v4, v15, &v17), KeyW >= 0) )
    {
      KeyW = 0;
      *(_QWORD *)(a4 + 16) = v17;
      *(_QWORD *)a4 = v4;
      goto LABEL_14;
    }
    v5 = v17;
LABEL_10:
    if ( v5 )
    {
      RegCloseKey(v5);
      RegUnLoadKeyW(HKEY_LOCAL_MACHINE, v4);
      *(_DWORD *)(a4 + 8) = 0;
    }
  }
  if ( v4 )
    operator delete((void *)(v4 - 4));
LABEL_14:
  if ( v8 )
    operator delete((void *)(v8 - 4));
  return (unsigned int)KeyW;
}

```

## disassembly

```asm
0x180006f84  mov     [rsp-8+arg_0], rbx
0x180006f89  push    rbp
0x180006f8a  push    rsi
0x180006f8b  push    rdi
0x180006f8c  push    r14
0x180006f8e  push    r15
0x180006f90  lea     rbp, [rsp-150h]
0x180006f98  sub     rsp, 250h
0x180006f9f  mov     rax, cs:__security_cookie
0x180006fa6  xor     rax, rsp
0x180006fa9  mov     [rbp+170h+var_30], rax
0x180006fb0  xor     edi, edi
0x180006fb2  mov     [rsp+270h+lpFile], 0
0x180006fbb  xor     r15d, r15d
0x180006fbe  mov     [rsp+270h+lpSubKey], rdi
0x180006fc3  lea     rcx, [rsp+270h+lpFile]
0x180006fc8  mov     [rsp+270h+var_250], r15
0x180006fcd  mov     rsi, r9
0x180006fd0  call    SczAllocConcat2Sz
0x180006fd5  mov     r14, [rsp+270h+lpFile]
0x180006fda  mov     ebx, eax
0x180006fdc  test    eax, eax
0x180006fde  js      loc_1800070A2
0x180006fe4  mov     r8d, 100h; unsigned __int64
0x180006fea  lea     rdx, [rsp+270h+var_230]; wchar_t *
0x180006fef  mov     rcx, r14; wchar_t *
0x180006ff2  call    ?GetLoadedHiveKeyNameInternal@@YAJPEB_WPEA_W_K@Z; GetLoadedHiveKeyNameInternal(wchar_t const *,wchar_t *,unsigned __int64)
0x180006ff7  xor     ebx, ebx
0x180006ff9  mov     ecx, eax
0x180006ffb  bts     ecx, 1Ch
0x180006fff  test    eax, eax
0x180007001  cmovs   ebx, ecx
0x180007004  test    ebx, ebx
0x180007006  js      short loc_18000706F
0x180007008  lea     rdx, [rsp+270h+var_230]
0x18000700d  lea     rcx, [rsp+270h+lpSubKey]
0x180007012  call    SczAllocFromSz
0x180007017  mov     rdi, [rsp+270h+lpSubKey]
0x18000701c  mov     ebx, eax
0x18000701e  test    eax, eax
0x180007020  js      short loc_180007094
0x180007022  lea     r9, [rsp+270h+var_250]
0x180007027  mov     rdx, rdi
0x18000702a  call    WrpRegOpenKeyWithBackupRestore
0x18000702f  test    eax, eax
0x180007031  jns     loc_1800070D8
0x180007037  mov     r8, r14; lpFile
0x18000703a  mov     rdx, rdi; lpSubKey
0x18000703d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007044  call    cs:__imp_RegLoadKeyW
0x18000704a  mov     ebx, eax
0x18000704c  test    eax, eax
0x18000704e  js      short loc_18000706A
0x180007050  lea     r9, [rsp+270h+var_250]
0x180007055  mov     dword ptr [rsi+8], 1
0x18000705c  mov     rdx, rdi
0x18000705f  call    WrpRegOpenKeyWithBackupRestore
0x180007064  mov     ebx, eax
0x180007066  test    eax, eax
0x180007068  jns     short loc_1800070D8
0x18000706a  mov     r15, [rsp+270h+var_250]
0x18000706f  test    r15, r15
0x180007072  jz      short loc_180007094
0x180007074  mov     rcx, r15; hKey
0x180007077  call    cs:__imp_RegCloseKey
0x18000707d  mov     rdx, rdi; lpSubKey
0x180007080  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007087  call    cs:__imp_RegUnLoadKeyW
0x18000708d  mov     dword ptr [rsi+8], 0
0x180007094  test    rdi, rdi
0x180007097  jz      short loc_1800070A2
0x180007099  lea     rcx, [rdi-8]; Block
0x18000709d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800070a2  test    r14, r14
0x1800070a5  jz      short loc_1800070B0
0x1800070a7  lea     rcx, [r14-8]; Block
0x1800070ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800070b0  mov     eax, ebx
0x1800070b2  mov     rcx, [rbp+170h+var_30]
0x1800070b9  xor     rcx, rsp; StackCookie
0x1800070bc  call    __security_check_cookie
0x1800070c1  mov     rbx, [rsp+270h+arg_0]
0x1800070c9  add     rsp, 250h
0x1800070d0  pop     r15
0x1800070d2  pop     r14
0x1800070d4  pop     rdi
0x1800070d5  pop     rsi
0x1800070d6  pop     rbp
0x1800070d7  retn
0x1800070d8  mov     rax, [rsp+270h+var_250]
0x1800070dd  xor     ebx, ebx
0x1800070df  mov     [rsi+10h], rax
0x1800070e3  mov     [rsi], rdi
0x1800070e6  jmp     short loc_1800070A2
```
