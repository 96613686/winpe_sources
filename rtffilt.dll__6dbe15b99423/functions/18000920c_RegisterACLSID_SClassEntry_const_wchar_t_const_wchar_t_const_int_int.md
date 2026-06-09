# RegisterACLSID(SClassEntry const &,wchar_t const *,wchar_t const *,int,int)

- ea: `0x18000920c`
- end: `0x180009488`
- name: `?RegisterACLSID@@YAJAEBUSClassEntry@@PEB_W1HH@Z`
- size: `636`
- prototype: `__int64 __fastcall(const struct SClassEntry *, const wchar_t *, const wchar_t *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009490`
- `0x18000cff4`

## callees

- `0x180001e40`
- `0x18000920c`
- `0x18000b288`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000938e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009442`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000938e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009442`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009454`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009454`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009341`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009414`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009341`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009414`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800092f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800092f3`

## string_xrefs

- `0x180009243`: `CLSID\`

## pseudocode

```c
__int64 __fastcall RegisterACLSID(const struct SClassEntry *a1, const wchar_t *a2, const wchar_t *a3, int a4)
{
  const wchar_t *v4; // r11
  __int64 v5; // rdx
  WCHAR *v6; // rax
  const wchar_t *v8; // rdi
  __int64 v10; // r10
  WCHAR *v11; // rcx
  __int64 v12; // rax
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  const BYTE *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = L"CLSID\\";
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v5 = 260;
  v6 = SubKey;
  v8 = a3;
  v10 = 2147483646;
  do
  {
    if ( !v10 )
      break;
    if ( !*v4 )
      break;
    *v6++ = *v4++;
    --v10;
    --v5;
  }
  while ( v5 );
  v11 = v6 - 1;
  if ( v5 )
    v11 = v6;
  v12 = -1;
  *v11 = 0;
  do
    ++v12;
  while ( SubKey[v12] );
  if ( !a3 )
    a3 = (const wchar_t *)*((_QWORD *)a1 + 3);
  StringCchCatW(SubKey, 260 - v12, a3);
  dwDisposition = 0;
  if ( a4 )
  {
    v13 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &hKey);
    if ( v13 )
    {
      v14 = 0;
      if ( v13 != 2 )
        v14 = v13;
      goto LABEL_29;
    }
    dwDisposition = 2;
  }
  else
  {
    v14 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    if ( v14 )
      goto LABEL_29;
    if ( dwDisposition == 1 && !v8 )
    {
      v15 = (const BYTE *)*((_QWORD *)a1 + 4);
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)&v15[2 * v16] );
      v14 = RegSetValueExW(hKey, 0, 0, 1u, v15, 2 * v16 + 2);
      if ( v14 )
        goto LABEL_29;
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  v17 = -1;
  do
    ++v17;
  while ( SubKey[v17] );
  StringCchCatW(SubKey, 260 - v17, L"\\PersistentHandler");
  v14 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( !v14 )
    v14 = RegSetValueExW(hKey, 0, 0, 1u, L"{2e2294a9-50d7-4fe7-a09f-e6492e185884}", 0x4Eu);
LABEL_29:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return v14;
}

```

## disassembly

```asm
0x18000920c  mov     [rsp-8+arg_8], rbx
0x180009211  mov     [rsp-8+arg_18], rdi
0x180009216  push    rbp
0x180009217  push    r12
0x180009219  push    r13
0x18000921b  push    r14
0x18000921d  push    r15
0x18000921f  lea     rbp, [rsp-180h]
0x180009227  sub     rsp, 280h
0x18000922e  mov     rax, cs:__security_cookie
0x180009235  xor     rax, rsp
0x180009238  mov     [rbp+1A0h+var_30], rax
0x18000923f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180009243  lea     r11, aClsid; "CLSID\\"
0x18000924a  mov     r15d, 104h
0x180009250  mov     [rsp+2A0h+hKey], r13
0x180009255  mov     edx, r15d
0x180009258  lea     rax, [rsp+2A0h+SubKey]
0x18000925d  xor     r12d, r12d
0x180009260  mov     ebx, r9d
0x180009263  mov     rdi, r8
0x180009266  mov     r14, rcx
0x180009269  mov     r10d, 7FFFFFFEh
0x18000926f  test    r10, r10
0x180009272  jz      short loc_180009291
0x180009274  movzx   ecx, word ptr [r11]
0x180009278  test    cx, cx
0x18000927b  jz      short loc_180009291
0x18000927d  mov     [rax], cx
0x180009280  add     r11, 2
0x180009284  add     rax, 2
0x180009288  dec     r10
0x18000928b  sub     rdx, 1
0x18000928f  jnz     short loc_18000926F
0x180009291  lea     rcx, [rax-2]
0x180009295  test    rdx, rdx
0x180009298  cmovnz  rcx, rax
0x18000929c  mov     rax, r13
0x18000929f  mov     [rcx], r12w
0x1800092a3  lea     rcx, [rsp+2A0h+SubKey]
0x1800092a8  inc     rax
0x1800092ab  cmp     [rcx+rax*2], r12w
0x1800092b0  jnz     short loc_1800092A8
0x1800092b2  mov     rdx, r15
0x1800092b5  sub     rdx, rax; unsigned __int64
0x1800092b8  test    rdi, rdi
0x1800092bb  jnz     short loc_1800092C1
0x1800092bd  mov     r8, [r14+18h]; wchar_t *
0x1800092c1  lea     rcx, [rsp+2A0h+SubKey]; wchar_t *
0x1800092c6  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800092cb  xor     r8d, r8d; Reserved
0x1800092ce  mov     [rsp+2A0h+dwDisposition], r12d
0x1800092d3  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800092d8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800092df  test    ebx, ebx
0x1800092e1  jz      short loc_180009318
0x1800092e3  lea     rax, [rsp+2A0h+hKey]
0x1800092e8  mov     r9d, 2001Fh; samDesired
0x1800092ee  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800092f3  call    cs:__imp_RegOpenKeyExW
0x1800092f9  test    eax, eax
0x1800092fb  jz      short loc_18000930B
0x1800092fd  cmp     eax, 2
0x180009300  mov     ebx, r12d
0x180009303  cmovnz  ebx, eax
0x180009306  jmp     loc_18000944A
0x18000930b  mov     [rsp+2A0h+dwDisposition], 2
0x180009313  jmp     loc_18000939E
0x180009318  lea     rax, [rsp+2A0h+dwDisposition]
0x18000931d  xor     r9d, r9d; lpClass
0x180009320  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x180009325  lea     rax, [rsp+2A0h+hKey]
0x18000932a  mov     [rsp+2A0h+var_268], rax; phkResult
0x18000932f  mov     [rsp+2A0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180009334  mov     [rsp+2A0h+samDesired], 2001Fh; samDesired
0x18000933c  mov     dword ptr [rsp+2A0h+phkResult], r12d; dwOptions
0x180009341  call    cs:__imp_RegCreateKeyExW
0x180009347  mov     ebx, eax
0x180009349  test    eax, eax
0x18000934b  jnz     loc_18000944A
0x180009351  cmp     [rsp+2A0h+dwDisposition], 1
0x180009356  jnz     short loc_18000939E
0x180009358  test    rdi, rdi
0x18000935b  jnz     short loc_18000939E
0x18000935d  mov     rcx, [r14+20h]
0x180009361  mov     rax, r13
0x180009364  inc     rax
0x180009367  cmp     [rcx+rax*2], r12w
0x18000936c  jnz     short loc_180009364
0x18000936e  lea     eax, ds:2[rax*2]
0x180009375  mov     r9d, 1; dwType
0x18000937b  mov     [rsp+2A0h+samDesired], eax; cbData
0x18000937f  xor     r8d, r8d; Reserved
0x180009382  mov     [rsp+2A0h+phkResult], rcx; lpData
0x180009387  xor     edx, edx; lpValueName
0x180009389  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000938e  call    cs:__imp_RegSetValueExW
0x180009394  mov     ebx, eax
0x180009396  test    eax, eax
0x180009398  jnz     loc_18000944A
0x18000939e  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800093a3  cmp     rcx, r13
0x1800093a6  jz      short loc_1800093B3
0x1800093a8  call    cs:__imp_RegCloseKey
0x1800093ae  mov     [rsp+2A0h+hKey], r13
0x1800093b3  lea     rcx, [rsp+2A0h+SubKey]
0x1800093b8  mov     rax, r13
0x1800093bb  inc     rax
0x1800093be  cmp     [rcx+rax*2], r12w
0x1800093c3  jnz     short loc_1800093BB
0x1800093c5  sub     r15, rax
0x1800093c8  lea     r8, aPersistenthand; "\\PersistentHandler"
0x1800093cf  mov     rdx, r15; unsigned __int64
0x1800093d2  lea     rcx, [rsp+2A0h+SubKey]; wchar_t *
0x1800093d7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800093dc  lea     rax, [rsp+2A0h+dwDisposition]
0x1800093e1  xor     r9d, r9d; lpClass
0x1800093e4  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1800093e9  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800093ee  lea     rax, [rsp+2A0h+hKey]
0x1800093f3  xor     r8d, r8d; Reserved
0x1800093f6  mov     [rsp+2A0h+var_268], rax; phkResult
0x1800093fb  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180009402  mov     [rsp+2A0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180009407  mov     [rsp+2A0h+samDesired], 2001Fh; samDesired
0x18000940f  mov     dword ptr [rsp+2A0h+phkResult], r12d; dwOptions
0x180009414  call    cs:__imp_RegCreateKeyExW
0x18000941a  mov     ebx, eax
0x18000941c  test    eax, eax
0x18000941e  jnz     short loc_18000944A
0x180009420  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180009425  lea     rax, Data; "{2e2294a9-50d7-4fe7-a09f-e6492e185884}"
0x18000942c  mov     [rsp+2A0h+samDesired], 4Eh ; 'N'; cbData
0x180009434  lea     r9d, [rbx+1]; dwType
0x180009438  xor     r8d, r8d; Reserved
0x18000943b  mov     [rsp+2A0h+phkResult], rax; lpData
0x180009440  xor     edx, edx; lpValueName
0x180009442  call    cs:__imp_RegSetValueExW
0x180009448  mov     ebx, eax
0x18000944a  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18000944f  cmp     rcx, r13
0x180009452  jz      short loc_18000945A
0x180009454  call    cs:__imp_RegCloseKey
0x18000945a  mov     eax, ebx
0x18000945c  mov     rcx, [rbp+1A0h+var_30]
0x180009463  xor     rcx, rsp; StackCookie
0x180009466  call    __security_check_cookie
0x18000946b  lea     r11, [rsp+2A0h+var_20]
0x180009473  mov     rbx, [r11+38h]
0x180009477  mov     rdi, [r11+48h]
0x18000947b  mov     rsp, r11
0x18000947e  pop     r15
0x180009480  pop     r14
0x180009482  pop     r13
0x180009484  pop     r12
0x180009486  pop     rbp
0x180009487  retn
```
