# WrpRegQueryStringValue

- ea: `0x180007288`
- end: `0x18000741d`
- name: `WrpRegQueryStringValue`
- size: `405`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004fd0`
- `0x180005920`

## callees

- `0x180007288`
- `0x18001029c`
- `0x180011654`
- `0x18001b7b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800072f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800072f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800073fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800073fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007353`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000737b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800073ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007353`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000737b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800073ce`

## pseudocode

```c
__int64 __fastcall WrpRegQueryStringValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, __int64 *a4)
{
  unsigned __int64 v8; // rbx
  int v9; // edi
  int v10; // r14d
  LSTATUS v11; // eax
  bool v12; // sf
  unsigned __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-10h] BYREF
  DWORD Type; // [rsp+44h] [rbp-Ch] BYREF

  if ( !a4 )
    return 2147942487LL;
  v8 = 0;
  hKey = 0;
  v13 = 0;
  v9 = -2147467259;
  Type = 0;
  cbData = 0;
  if ( a2 )
  {
    if ( RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey) < 0 )
      goto LABEL_19;
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v10 = 0;
  if ( !*a4 )
  {
    v12 = RegQueryValueExW(a1, a3, 0, &Type, 0, &cbData) < 0;
    goto LABEL_12;
  }
  v9 = SczSize(*a4, &v13);
  if ( v9 < 0 )
    goto LABEL_18;
  v8 = v13;
  cbData = 2 * v13 - 4;
  v11 = RegQueryValueExW(hKey, a3, 0, &Type, (LPBYTE)*a4, &cbData);
  v12 = v11 < 0;
  if ( v11 )
  {
LABEL_12:
    if ( v12 )
      goto LABEL_18;
    goto LABEL_13;
  }
  v10 = 1;
LABEL_13:
  if ( Type - 1 <= 1 )
  {
    if ( v10
      || (v8 = ((unsigned __int64)cbData >> 1) + 2, v9 = SczAlloc(a4, v8), v9 >= 0)
      && RegQueryValueExW(hKey, a3, 0, &Type, (LPBYTE)*a4, &cbData) >= 0 )
    {
      v9 = 0;
      *(_WORD *)(*a4 + 2 * v8 - 4) = 0;
      *(_WORD *)(*a4 + 2 * v8 - 2) = 0;
    }
  }
LABEL_18:
  if ( a2 )
  {
LABEL_19:
    if ( hKey )
      RegCloseKey(hKey);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007288  push    rbp
0x18000728a  push    rbx
0x18000728b  push    rsi
0x18000728c  push    rdi
0x18000728d  push    r12
0x18000728f  push    r14
0x180007291  push    r15
0x180007293  mov     rbp, rsp
0x180007296  sub     rsp, 50h
0x18000729a  mov     rax, cs:__security_cookie
0x1800072a1  xor     rax, rsp
0x1800072a4  mov     [rbp+var_8], rax
0x1800072a8  mov     rsi, r9
0x1800072ab  mov     r12, r8
0x1800072ae  mov     r15, rdx
0x1800072b1  test    r9, r9
0x1800072b4  jnz     short loc_1800072C0
0x1800072b6  mov     eax, 80070057h
0x1800072bb  jmp     loc_180007402
0x1800072c0  xor     ebx, ebx
0x1800072c2  mov     [rbp+hKey], 0
0x1800072ca  mov     [rbp+var_20], rbx
0x1800072ce  mov     edi, 80004005h
0x1800072d3  mov     [rbp+Type], ebx
0x1800072d6  mov     [rbp+cbData], ebx
0x1800072d9  test    r15, r15
0x1800072dc  jz      short loc_180007304
0x1800072de  lea     rax, [rbp+hKey]
0x1800072e2  mov     r9d, 20019h; samDesired
0x1800072e8  xor     r8d, r8d; ulOptions
0x1800072eb  mov     [rsp+50h+phkResult], rax; phkResult
0x1800072f0  call    cs:__imp_RegOpenKeyExW
0x1800072f6  test    eax, eax
0x1800072f8  js      loc_1800073F1
0x1800072fe  mov     rcx, [rbp+hKey]
0x180007302  jmp     short loc_180007308
0x180007304  mov     [rbp+hKey], rcx
0x180007308  xor     r14d, r14d
0x18000730b  cmp     [rsi], rbx
0x18000730e  jz      short loc_180007363
0x180007310  mov     rcx, [rsi]
0x180007313  lea     rdx, [rbp+var_20]
0x180007317  call    SczSize
0x18000731c  mov     edi, eax
0x18000731e  test    eax, eax
0x180007320  js      loc_1800073EC
0x180007326  mov     rbx, [rbp+var_20]
0x18000732a  lea     rax, [rbp+cbData]
0x18000732e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180007333  lea     r9, [rbp+Type]; lpType
0x180007337  xor     r8d, r8d; lpReserved
0x18000733a  mov     rdx, r12; lpValueName
0x18000733d  lea     ecx, ds:0FFFFFFFFFFFFFFFCh[rbx*2]
0x180007344  mov     [rbp+cbData], ecx
0x180007347  mov     rcx, [rsi]
0x18000734a  mov     [rsp+50h+phkResult], rcx; lpData
0x18000734f  mov     rcx, [rbp+hKey]; hKey
0x180007353  call    cs:__imp_RegQueryValueExW
0x180007359  test    eax, eax
0x18000735b  jnz     short loc_180007383
0x18000735d  lea     r14d, [rax+1]
0x180007361  jmp     short loc_180007385
0x180007363  lea     rax, [rbp+cbData]
0x180007367  xor     r8d, r8d; lpReserved
0x18000736a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18000736f  lea     r9, [rbp+Type]; lpType
0x180007373  mov     rdx, r12; lpValueName
0x180007376  mov     [rsp+50h+phkResult], rbx; lpData
0x18000737b  call    cs:__imp_RegQueryValueExW
0x180007381  test    eax, eax
0x180007383  js      short loc_1800073EC
0x180007385  mov     eax, [rbp+Type]
0x180007388  dec     eax
0x18000738a  cmp     eax, 1
0x18000738d  ja      short loc_1800073EC
0x18000738f  test    r14d, r14d
0x180007392  jnz     short loc_1800073D8
0x180007394  mov     ebx, [rbp+cbData]
0x180007397  mov     rcx, rsi
0x18000739a  shr     rbx, 1
0x18000739d  add     rbx, 2
0x1800073a1  mov     rdx, rbx
0x1800073a4  call    SczAlloc
0x1800073a9  mov     edi, eax
0x1800073ab  test    eax, eax
0x1800073ad  js      short loc_1800073EC
0x1800073af  mov     rcx, [rbp+hKey]; hKey
0x1800073b3  lea     rax, [rbp+cbData]
0x1800073b7  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800073bc  lea     r9, [rbp+Type]; lpType
0x1800073c0  mov     rax, [rsi]
0x1800073c3  xor     r8d, r8d; lpReserved
0x1800073c6  mov     rdx, r12; lpValueName
0x1800073c9  mov     [rsp+50h+phkResult], rax; lpData
0x1800073ce  call    cs:__imp_RegQueryValueExW
0x1800073d4  test    eax, eax
0x1800073d6  js      short loc_1800073EC
0x1800073d8  mov     rcx, [rsi]
0x1800073db  xor     eax, eax
0x1800073dd  xor     edi, edi
0x1800073df  mov     [rcx+rbx*2-4], ax
0x1800073e4  mov     rcx, [rsi]
0x1800073e7  mov     [rcx+rbx*2-2], ax
0x1800073ec  test    r15, r15
0x1800073ef  jz      short loc_180007400
0x1800073f1  mov     rcx, [rbp+hKey]; hKey
0x1800073f5  test    rcx, rcx
0x1800073f8  jz      short loc_180007400
0x1800073fa  call    cs:__imp_RegCloseKey
0x180007400  mov     eax, edi
0x180007402  mov     rcx, [rbp+var_8]
0x180007406  xor     rcx, rsp; StackCookie
0x180007409  call    __security_check_cookie
0x18000740e  add     rsp, 50h
0x180007412  pop     r15
0x180007414  pop     r14
0x180007416  pop     r12
0x180007418  pop     rdi
0x180007419  pop     rsi
0x18000741a  pop     rbx
0x18000741b  pop     rbp
0x18000741c  retn
```
