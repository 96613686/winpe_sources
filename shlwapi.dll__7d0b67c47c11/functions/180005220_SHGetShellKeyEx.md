# SHGetShellKeyEx

- ea: `0x180005220`
- end: `0x180005590`
- name: `SHGetShellKeyEx`
- size: `880`
- prototype: `HKEY __fastcall(int, const WCHAR *, int, REGSAM)`
- caller_count: `10`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004760`
- `0x1800047f0`
- `0x180004a38`
- `0x180004d10`
- `0x180004ef0`
- `0x180005190`
- `0x180024b80`
- `0x180025970`
- `0x180029c20`
- `0x18002c060`

## callees

- `0x180005220`
- `0x180012550`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005472`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005483`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005472`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005483`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000533d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000533d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005328`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180005328`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005358`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005468`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005515`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005468`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005515`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800054c2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005559`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800054c2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005559`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000534e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000534e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800053ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000541b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005500`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800053ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000541b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005500`

## pseudocode

```c
HKEY __fastcall SHGetShellKeyEx(int a1, const WCHAR *a2, int a3, REGSAM a4)
{
  int v4; // r9d
  __int64 i; // rax
  __int64 v8; // rbx
  HKEY v9; // rsi
  HKEY v10; // rdi
  int v11; // r14d
  REGSAM v12; // r15d
  HANDLE CurrentThread; // rax
  HKEY v14; // r12
  const WCHAR *v15; // rdx
  LSTATUS v16; // eax
  HKEY v17; // r15
  void (__fastcall *v18)(HKEY); // rax
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  HKEY v23; // [rsp+60h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-1h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+7h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+Fh] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+17h] BYREF

  v4 = 0x1FFFF;
  if ( a1 != 33 )
    v4 = a1;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 7 )
      return 0;
    v8 = 5 * i;
    if ( LODWORD(qword_180059000[5 * i]) == v4 )
      break;
  }
  v9 = 0;
  v10 = (HKEY)qword_180059000[v8 + 1];
  v11 = 1;
  v12 = 131101;
  if ( !a3 )
    v12 = 131097;
  if ( v10 == HKEY_CURRENT_USER_LOCAL_SETTINGS )
  {
    if ( !g_tbCanAccessHKCULS )
    {
      v23 = 0;
      v20 = RegOpenKeyExW(HKEY_CURRENT_USER_LOCAL_SETTINGS, 0, 0, 0x20019u, &v23);
      if ( v20 )
      {
        if ( v20 == 6 )
        {
          g_tbCanAccessHKCULS = 2;
          goto LABEL_13;
        }
      }
      else
      {
        g_tbCanAccessHKCULS = 1;
        RegCloseKey(v23);
      }
    }
    if ( g_tbCanAccessHKCULS == 2 )
    {
LABEL_13:
      phkResult = HKEY_CURRENT_USER;
      TokenHandle = 0;
      goto LABEL_15;
    }
  }
  phkResult = v10;
  TokenHandle = 0;
  if ( v10 != HKEY_CURRENT_USER )
  {
LABEL_18:
    v11 = 0;
    goto LABEL_19;
  }
LABEL_15:
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    RegOpenCurrentUser(v12, &phkResult);
    CloseHandle(TokenHandle);
  }
  v10 = phkResult;
  if ( phkResult == HKEY_CURRENT_USER )
    goto LABEL_18;
LABEL_19:
  if ( v10 )
  {
    v14 = (HKEY)qword_180059000[v8 + 4];
    if ( !v14 || v11 )
    {
      hKey = 0;
      v15 = (const WCHAR *)qword_180059000[v8 + 2];
      if ( a3 && v15 )
      {
        dwDisposition = 0;
        v16 = RegCreateKeyExW(v10, v15, 0, 0, 0, a4, 0, &hKey, &dwDisposition);
      }
      else
      {
        v16 = RegOpenKeyExW(v10, v15, 0, a4, &hKey);
      }
      v17 = hKey;
      if ( !hKey )
      {
        SetLastError(v16);
        v17 = hKey;
        if ( !hKey )
          goto LABEL_38;
      }
      v14 = v17;
      v18 = (void (__fastcall *)(HKEY))qword_180059000[v8 + 3];
      if ( v18 )
        v18(v17);
      if ( !v11 && !_InterlockedCompareExchange64(&qword_180059000[v8 + 4], (signed __int64)v17, 0) )
        v17 = 0;
    }
    else
    {
      v17 = 0;
    }
    v23 = 0;
    if ( a3 && a2 )
    {
      dwDisposition = 0;
      v19 = RegCreateKeyExW(v14, a2, 0, 0, 0, a4, 0, &v23, &dwDisposition);
    }
    else
    {
      v19 = RegOpenKeyExW(v14, a2, 0, a4, &v23);
    }
    v9 = v23;
    if ( !v23 )
    {
      SetLastError(v19);
      v9 = v23;
    }
    if ( v17 )
      RegCloseKey(v17);
LABEL_38:
    if ( v11 )
      RegCloseKey(v10);
    return v9;
  }
  SetLastError(5u);
  return v9;
}

```

## disassembly

```asm
0x180005220  push    rbp
0x180005222  push    r12
0x180005224  push    r13
0x180005226  lea     rbp, [rsp-47h]
0x18000522b  sub     rsp, 0B0h
0x180005232  mov     rax, cs:__security_cookie
0x180005239  xor     rax, rsp
0x18000523c  mov     [rbp+57h+var_38], rax
0x180005240  xor     r10d, r10d
0x180005243  mov     [rbp+57h+samDesired], r9d
0x180005247  cmp     ecx, 21h ; '!'
0x18000524a  mov     [rbp+57h+lpSubKey], rdx
0x18000524e  mov     r9d, 1FFFFh
0x180005254  mov     [rsp+0C0h+arg_0], rbx
0x18000525c  cmovnz  r9d, ecx
0x180005260  lea     r12, qword_180059000
0x180005267  xor     eax, eax
0x180005269  mov     r13d, r8d
0x18000526c  cmp     eax, 7
0x18000526f  jb      short loc_180005295
0x180005271  mov     rax, r10
0x180005274  mov     rbx, [rsp+0C0h+arg_0]
0x18000527c  mov     rcx, [rbp+57h+var_38]
0x180005280  xor     rcx, rsp; StackCookie
0x180005283  call    __security_check_cookie
0x180005288  add     rsp, 0B0h
0x18000528f  pop     r13
0x180005291  pop     r12
0x180005293  pop     rbp
0x180005294  retn
0x180005295  lea     rdx, [rax+rax*4]
0x180005299  lea     rbx, ds:0[rdx*8]
0x1800052a1  cmp     [rbx+r12], r9d
0x1800052a5  jz      short loc_1800052AB
0x1800052a7  inc     eax
0x1800052a9  jmp     short loc_18000526C
0x1800052ab  mov     [rsp+0C0h+var_18], rsi
0x1800052b3  mov     r9d, 20019h; samDesired
0x1800052b9  mov     [rsp+0C0h+var_20], rdi
0x1800052c1  xor     esi, esi
0x1800052c3  mov     rdi, [rbx+r12+8]
0x1800052c8  test    r13d, r13d
0x1800052cb  mov     [rsp+0C0h+var_28], r14
0x1800052d3  mov     r14d, 1
0x1800052d9  mov     [rsp+0C0h+var_30], r15
0x1800052e1  mov     r15d, 2001Dh
0x1800052e7  cmovz   r15d, r9d
0x1800052eb  cmp     rdi, 0FFFFFFFF80000007h
0x1800052f2  jnz     short loc_180005317
0x1800052f4  cmp     cs:?g_tbCanAccessHKCULS@@3W4TRIBIT@@A, esi; TRIBIT g_tbCanAccessHKCULS
0x1800052fa  jz      loc_1800054E7
0x180005300  cmp     cs:?g_tbCanAccessHKCULS@@3W4TRIBIT@@A, 2; TRIBIT g_tbCanAccessHKCULS
0x180005307  jnz     short loc_180005317
0x180005309  mov     [rbp+57h+phkResult], 0FFFFFFFF80000001h
0x180005311  mov     [rbp+57h+TokenHandle], rsi
0x180005315  jmp     short loc_180005328
0x180005317  mov     [rbp+57h+phkResult], rdi
0x18000531b  mov     [rbp+57h+TokenHandle], rsi
0x18000531f  cmp     rdi, 0FFFFFFFF80000001h
0x180005326  jnz     short loc_18000536B
0x180005328  call    cs:__imp_GetCurrentThread
0x18000532e  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180005332  mov     r8d, r14d; OpenAsSelf
0x180005335  mov     rcx, rax; ThreadHandle
0x180005338  mov     edx, 0Ch; DesiredAccess
0x18000533d  call    cs:__imp_OpenThreadToken
0x180005343  test    eax, eax
0x180005345  jz      short loc_18000535E
0x180005347  lea     rdx, [rbp+57h+phkResult]; phkResult
0x18000534b  mov     ecx, r15d; samDesired
0x18000534e  call    cs:__imp_RegOpenCurrentUser
0x180005354  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180005358  call    cs:__imp_CloseHandle
0x18000535e  mov     rdi, [rbp+57h+phkResult]
0x180005362  cmp     rdi, 0FFFFFFFF80000001h
0x180005369  jnz     short loc_18000536E
0x18000536b  xor     r14d, r14d
0x18000536e  test    rdi, rdi
0x180005371  jz      loc_18000547E
0x180005377  mov     r12, [rbx+r12+20h]
0x18000537c  test    r12, r12
0x18000537f  jnz     short loc_1800053EF
0x180005381  mov     [rbp+57h+hKey], rsi
0x180005385  lea     rdx, qword_180059000
0x18000538c  mov     rdx, [rbx+rdx+10h]; lpSubKey
0x180005391  test    r13d, r13d
0x180005394  jnz     loc_180005520
0x18000539a  mov     r9d, [rbp+57h+samDesired]; samDesired
0x18000539e  lea     rax, [rbp+57h+hKey]
0x1800053a2  xor     r8d, r8d; ulOptions
0x1800053a5  mov     [rsp+0C0h+var_A0], rax; phkResult
0x1800053aa  mov     rcx, rdi; hKey
0x1800053ad  call    cs:__imp_RegOpenKeyExW
0x1800053b3  mov     r15, [rbp+57h+hKey]
0x1800053b7  test    r15, r15
0x1800053ba  jz      loc_1800054CD
0x1800053c0  lea     rcx, qword_180059000
0x1800053c7  mov     r12, r15
0x1800053ca  mov     rax, [rbx+rcx+18h]
0x1800053cf  test    rax, rax
0x1800053d2  jnz     loc_18000557C
0x1800053d8  test    r14d, r14d
0x1800053db  jnz     short loc_1800053F7
0x1800053dd  xor     eax, eax
0x1800053df  lock cmpxchg [rbx+rcx+20h], r15
0x1800053e6  mov     rax, rsi
0x1800053e9  cmovz   r15, rax
0x1800053ed  jmp     short loc_1800053F7
0x1800053ef  test    r14d, r14d
0x1800053f2  jnz     short loc_180005381
0x1800053f4  xor     r15d, r15d
0x1800053f7  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800053fb  mov     [rbp+57h+var_60], rsi
0x1800053ff  test    r13d, r13d
0x180005402  jnz     loc_18000548B
0x180005408  mov     r9d, [rbp+57h+samDesired]; samDesired
0x18000540c  lea     rax, [rbp+57h+var_60]
0x180005410  xor     r8d, r8d; ulOptions
0x180005413  mov     [rsp+0C0h+var_A0], rax; phkResult
0x180005418  mov     rcx, r12; hKey
0x18000541b  call    cs:__imp_RegOpenKeyExW
0x180005421  mov     rsi, [rbp+57h+var_60]
0x180005425  test    rsi, rsi
0x180005428  jz      short loc_180005470
0x18000542a  test    r15, r15
0x18000542d  jz      short loc_180005438
0x18000542f  mov     rcx, r15; hKey
0x180005432  call    cs:__imp_RegCloseKey
0x180005438  test    r14d, r14d
0x18000543b  jnz     short loc_180005465
0x18000543d  mov     r15, [rsp+0C0h+var_30]
0x180005445  mov     rax, rsi
0x180005448  mov     rsi, [rsp+0C0h+var_18]
0x180005450  mov     r14, [rsp+0C0h+var_28]
0x180005458  mov     rdi, [rsp+0C0h+var_20]
0x180005460  jmp     loc_180005274
0x180005465  mov     rcx, rdi; hKey
0x180005468  call    cs:__imp_RegCloseKey
0x18000546e  jmp     short loc_18000543D
0x180005470  mov     ecx, eax; dwErrCode
0x180005472  call    cs:__imp_SetLastError
0x180005478  mov     rsi, [rbp+57h+var_60]
0x18000547c  jmp     short loc_18000542A
0x18000547e  mov     ecx, 5; dwErrCode
0x180005483  call    cs:__imp_SetLastError
0x180005489  jmp     short loc_18000543D
0x18000548b  test    rdx, rdx
0x18000548e  jz      loc_180005408
0x180005494  lea     rax, [rbp+57h+dwDisposition]
0x180005498  mov     [rbp+57h+dwDisposition], esi
0x18000549b  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x1800054a0  xor     r9d, r9d; lpClass
0x1800054a3  lea     rax, [rbp+57h+var_60]
0x1800054a7  xor     r8d, r8d; Reserved
0x1800054aa  mov     [rsp+0C0h+var_88], rax; phkResult
0x1800054af  mov     rcx, r12; hKey
0x1800054b2  mov     eax, [rbp+57h+samDesired]
0x1800054b5  mov     [rsp+0C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800054ba  mov     [rsp+0C0h+var_98], eax; samDesired
0x1800054be  mov     dword ptr [rsp+0C0h+var_A0], esi; dwOptions
0x1800054c2  call    cs:__imp_RegCreateKeyExW
0x1800054c8  jmp     loc_180005421
0x1800054cd  mov     ecx, eax; dwErrCode
0x1800054cf  call    cs:__imp_SetLastError
0x1800054d5  mov     r15, [rbp+57h+hKey]
0x1800054d9  test    r15, r15
0x1800054dc  jnz     loc_1800053C0
0x1800054e2  jmp     loc_180005438
0x1800054e7  lea     rax, [rbp+57h+var_60]
0x1800054eb  mov     [rbp+57h+var_60], rsi
0x1800054ef  xor     r8d, r8d; ulOptions
0x1800054f2  mov     [rsp+0C0h+var_A0], rax; phkResult
0x1800054f7  xor     edx, edx; lpSubKey
0x1800054f9  mov     rcx, 0FFFFFFFF80000007h; hKey
0x180005500  call    cs:__imp_RegOpenKeyExW
0x180005506  test    eax, eax
0x180005508  jnz     short loc_180005564
0x18000550a  mov     rcx, [rbp+57h+var_60]; hKey
0x18000550e  mov     cs:?g_tbCanAccessHKCULS@@3W4TRIBIT@@A, r14d; TRIBIT g_tbCanAccessHKCULS
0x180005515  call    cs:__imp_RegCloseKey
0x18000551b  jmp     loc_180005300
0x180005520  test    rdx, rdx
0x180005523  jz      loc_18000539A
0x180005529  mov     r9d, [rbp+57h+samDesired]
0x18000552d  lea     rax, [rbp+57h+dwDisposition]
0x180005531  mov     [rsp+0C0h+lpdwDisposition], rax; lpdwDisposition
0x180005536  xor     r8d, r8d; Reserved
0x180005539  lea     rax, [rbp+57h+hKey]
0x18000553d  mov     [rbp+57h+dwDisposition], esi
0x180005540  mov     [rsp+0C0h+var_88], rax; phkResult
0x180005545  mov     rcx, rdi; hKey
0x180005548  mov     [rsp+0C0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000554d  mov     [rsp+0C0h+var_98], r9d; samDesired
0x180005552  xor     r9d, r9d; lpClass
0x180005555  mov     dword ptr [rsp+0C0h+var_A0], esi; dwOptions
0x180005559  call    cs:__imp_RegCreateKeyExW
0x18000555f  jmp     loc_1800053B3
0x180005564  cmp     eax, 6
0x180005567  jnz     loc_180005300
0x18000556d  mov     cs:?g_tbCanAccessHKCULS@@3W4TRIBIT@@A, 2; TRIBIT g_tbCanAccessHKCULS
0x180005577  jmp     loc_180005309
0x18000557c  mov     rcx, r15
0x18000557f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005584  lea     rcx, qword_180059000
0x18000558b  jmp     loc_1800053D8
```
