# GetTypeLibraryFromTypeLibKey

- ea: `0x180042fd0`
- end: `0x1800432b2`
- name: `GetTypeLibraryFromTypeLibKey`
- size: `738`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006450c`

## callees

- `0x180042fd0`
- `0x180045ca8`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `msvcrt!atoi` at `0x1800431a1`
- `msvcrt!atoi` at `0x1800431b6`
- `msvcrt!atoi` at `0x1800431a1`
- `msvcrt!atoi` at `0x1800431b6`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180043218`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180043218`
- `KERNEL32!MultiByteToWideChar` at `0x1800431dd`
- `KERNEL32!MultiByteToWideChar` at `0x1800431dd`
- `OLE32!CLSIDFromString` at `0x1800431f0`
- `OLE32!CLSIDFromString` at `0x1800431f0`
- `ADVAPI32!RegOpenKeyExA` at `0x18004305a`
- `ADVAPI32!RegOpenKeyExA` at `0x180043101`
- `ADVAPI32!RegOpenKeyExA` at `0x18004305a`
- `ADVAPI32!RegOpenKeyExA` at `0x180043101`
- `ADVAPI32!RegCloseKey` at `0x18004324e`
- `ADVAPI32!RegCloseKey` at `0x180043267`
- `ADVAPI32!RegCloseKey` at `0x18004324e`
- `ADVAPI32!RegCloseKey` at `0x180043267`
- `ADVAPI32!RegQueryValueExA` at `0x18004309b`
- `ADVAPI32!RegQueryValueExA` at `0x18004313d`
- `ADVAPI32!RegQueryValueExA` at `0x18004309b`
- `ADVAPI32!RegQueryValueExA` at `0x18004313d`

## pseudocode

```c
__int64 __fastcall GetTypeLibraryFromTypeLibKey(HKEY hKey, ITypeLib **a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  const char *v10; // rdi
  __int64 i; // rbx
  WORD v12; // si
  WORD v13; // di
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  ITypeLib *pptlib; // [rsp+50h] [rbp-B0h] BYREF
  CLSID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v22[16]; // [rsp+68h] [rbp-98h] BYREF
  CHAR Data[56]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR WideCharStr[48]; // [rsp+B0h] [rbp-50h] BYREF

  *a2 = 0;
  hKeya = 0;
  phkResult = 0;
  cbData = 48;
  lpcbData = 10;
  pclsid = 0;
  Type = 0;
  pptlib = 0;
  v4 = RegOpenKeyExA(hKey, "TypeLib", 0, 0x20019u, &hKeya);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = RegQueryValueExA(hKeya, 0, 0, &Type, (LPBYTE)Data, &cbData);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 >= 0 )
    {
      if ( Type != 1 )
        goto LABEL_32;
      if ( !cbData )
        goto LABEL_32;
      v7 = cbData - 1;
      if ( (unsigned int)v7 >= 0x2F )
        goto LABEL_32;
      Data[v7] = 0;
      v8 = RegOpenKeyExA(hKey, "Version", 0, 0x20019u, &phkResult);
      v5 = v8;
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v5 >= 0 )
      {
        v9 = RegQueryValueExA(phkResult, 0, 0, &Type, v22, &lpcbData);
        v5 = v9;
        if ( v9 > 0 )
          v5 = (unsigned __int16)v9 | 0x80070000;
        if ( v5 >= 0 )
        {
          if ( Type == 1 && lpcbData )
          {
            v10 = 0;
            for ( i = 0; (unsigned int)i < lpcbData; i = (unsigned int)(i + 1) )
            {
              if ( v22[i] == 46 )
              {
                if ( (unsigned int)i >= 0xAuLL )
                  _report_rangecheckfailure();
                v22[i] = 0;
                v10 = (const char *)&v22[(unsigned int)(i + 1)];
                break;
              }
            }
            v12 = atoi((const char *)v22);
            v13 = (_DWORD)i == lpcbData ? 0 : atoi(v10);
            if ( MultiByteToWideChar(0, 0, Data, -1, WideCharStr, 48) )
            {
              v5 = CLSIDFromString(WideCharStr, &pclsid);
              if ( v5 >= 0 )
              {
                v5 = LoadRegTypeLib(&pclsid, v12, v13, 0x400u, &pptlib);
                if ( v5 >= 0 )
                {
                  v5 = 0;
                  *a2 = pptlib;
                  pptlib = 0;
                }
              }
              goto LABEL_33;
            }
          }
LABEL_32:
          v5 = -2147467259;
        }
      }
    }
  }
LABEL_33:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( pptlib )
    ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180042fd0  mov     [rsp-8+arg_10], rbx
0x180042fd5  mov     [rsp-8+arg_18], rsi
0x180042fda  push    rbp
0x180042fdb  push    rdi
0x180042fdc  push    r14
0x180042fde  lea     rbp, [rsp-20h]
0x180042fe3  sub     rsp, 120h
0x180042fea  mov     rax, cs:__security_cookie
0x180042ff1  xor     rax, rsp
0x180042ff4  mov     [rbp+30h+var_20], rax
0x180042ff8  mov     r14, rdx
0x180042ffb  mov     qword ptr [rdx], 0
0x180043002  xorps   xmm0, xmm0
0x180043005  mov     [rsp+130h+hKey], 0
0x18004300e  lea     rax, [rsp+130h+hKey]
0x180043013  mov     [rsp+130h+var_E8], 0
0x18004301c  lea     rdx, aTypelib; "TypeLib"
0x180043023  mov     [rsp+130h+phkResult], rax; phkResult
0x180043028  mov     r9d, 20019h; samDesired
0x18004302e  mov     [rsp+130h+cbData], 30h ; '0'
0x180043036  xor     r8d, r8d; ulOptions
0x180043039  mov     [rsp+130h+var_FC], 0Ah
0x180043041  movups  xmmword ptr [rsp+130h+pclsid.Data1], xmm0
0x180043046  mov     rdi, rcx
0x180043049  mov     [rsp+130h+Type], 0
0x180043051  mov     [rsp+130h+pptlib], 0
0x18004305a  call    cs:__imp_RegOpenKeyExA
0x180043060  mov     ebx, eax
0x180043062  mov     esi, 80070000h
0x180043067  test    eax, eax
0x180043069  jle     short loc_180043070
0x18004306b  movzx   ebx, ax
0x18004306e  or      ebx, esi
0x180043070  test    ebx, ebx
0x180043072  js      loc_180043244
0x180043078  mov     rcx, [rsp+130h+hKey]; hKey
0x18004307d  lea     rax, [rsp+130h+cbData]
0x180043082  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180043087  lea     r9, [rsp+130h+Type]; lpType
0x18004308c  lea     rax, [rsp+130h+Data]
0x180043091  xor     r8d, r8d; lpReserved
0x180043094  xor     edx, edx; lpValueName
0x180043096  mov     [rsp+130h+phkResult], rax; lpData
0x18004309b  call    cs:__imp_RegQueryValueExA
0x1800430a1  mov     ebx, eax
0x1800430a3  test    eax, eax
0x1800430a5  jle     short loc_1800430AC
0x1800430a7  movzx   ebx, ax
0x1800430aa  or      ebx, esi
0x1800430ac  test    ebx, ebx
0x1800430ae  js      loc_180043244
0x1800430b4  cmp     [rsp+130h+Type], 1
0x1800430b9  jnz     loc_18004323F
0x1800430bf  mov     eax, [rsp+130h+cbData]
0x1800430c3  test    eax, eax
0x1800430c5  jz      loc_18004323F
0x1800430cb  dec     eax
0x1800430cd  cmp     eax, 2Fh ; '/'
0x1800430d0  jnb     loc_18004323F
0x1800430d6  cmp     eax, 30h ; '0'
0x1800430d9  jnb     loc_180043239
0x1800430df  mov     [rsp+rax+130h+Data], 0
0x1800430e4  lea     rdx, aVersion; "Version"
0x1800430eb  lea     rax, [rsp+130h+var_E8]
0x1800430f0  mov     r9d, 20019h; samDesired
0x1800430f6  xor     r8d, r8d; ulOptions
0x1800430f9  mov     [rsp+130h+phkResult], rax; phkResult
0x1800430fe  mov     rcx, rdi; hKey
0x180043101  call    cs:__imp_RegOpenKeyExA
0x180043107  mov     ebx, eax
0x180043109  test    eax, eax
0x18004310b  jle     short loc_180043112
0x18004310d  movzx   ebx, ax
0x180043110  or      ebx, esi
0x180043112  test    ebx, ebx
0x180043114  js      loc_180043244
0x18004311a  mov     rcx, [rsp+130h+var_E8]; hKey
0x18004311f  lea     rax, [rsp+130h+var_FC]
0x180043124  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180043129  lea     r9, [rsp+130h+Type]; lpType
0x18004312e  lea     rax, [rsp+130h+var_C8]
0x180043133  xor     r8d, r8d; lpReserved
0x180043136  xor     edx, edx; lpValueName
0x180043138  mov     [rsp+130h+phkResult], rax; lpData
0x18004313d  call    cs:__imp_RegQueryValueExA
0x180043143  mov     ebx, eax
0x180043145  test    eax, eax
0x180043147  jle     short loc_18004314E
0x180043149  movzx   ebx, ax
0x18004314c  or      ebx, esi
0x18004314e  test    ebx, ebx
0x180043150  js      loc_180043244
0x180043156  cmp     [rsp+130h+Type], 1
0x18004315b  jnz     loc_18004323F
0x180043161  mov     ecx, [rsp+130h+var_FC]
0x180043165  test    ecx, ecx
0x180043167  jz      loc_18004323F
0x18004316d  xor     edi, edi
0x18004316f  xor     ebx, ebx
0x180043171  cmp     ebx, ecx
0x180043173  jnb     short loc_18004319C
0x180043175  cmp     [rsp+rbx+130h+var_C8], 2Eh ; '.'
0x18004317a  mov     eax, ebx
0x18004317c  jz      short loc_180043182
0x18004317e  inc     ebx
0x180043180  jmp     short loc_180043171
0x180043182  cmp     rax, 0Ah
0x180043186  jnb     loc_180043239
0x18004318c  mov     [rsp+rbx+130h+var_C8], dil
0x180043191  lea     ecx, [rbx+1]
0x180043194  lea     rdi, [rsp+130h+var_C8]
0x180043199  add     rdi, rcx
0x18004319c  lea     rcx, [rsp+130h+var_C8]; String
0x1800431a1  call    cs:__imp_atoi
0x1800431a7  mov     esi, eax
0x1800431a9  cmp     ebx, [rsp+130h+var_FC]
0x1800431ad  jnz     short loc_1800431B3
0x1800431af  xor     edi, edi
0x1800431b1  jmp     short loc_1800431BF
0x1800431b3  mov     rcx, rdi; String
0x1800431b6  call    cs:__imp_atoi
0x1800431bc  movzx   edi, ax
0x1800431bf  lea     rax, [rbp+30h+WideCharStr]
0x1800431c3  mov     dword ptr [rsp+130h+lpcbData], 30h ; '0'; cchWideChar
0x1800431cb  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800431cf  mov     [rsp+130h+phkResult], rax; lpWideCharStr
0x1800431d4  lea     r8, [rsp+130h+Data]; lpMultiByteStr
0x1800431d9  xor     edx, edx; dwFlags
0x1800431db  xor     ecx, ecx; CodePage
0x1800431dd  call    cs:__imp_MultiByteToWideChar
0x1800431e3  test    eax, eax
0x1800431e5  jz      short loc_18004323F
0x1800431e7  lea     rdx, [rsp+130h+pclsid]; pclsid
0x1800431ec  lea     rcx, [rbp+30h+WideCharStr]; lpsz
0x1800431f0  call    cs:__imp_CLSIDFromString
0x1800431f6  mov     ebx, eax
0x1800431f8  test    eax, eax
0x1800431fa  js      short loc_180043244
0x1800431fc  lea     rax, [rsp+130h+pptlib]
0x180043201  movzx   edx, si; wVerMajor
0x180043204  mov     r9d, 400h; lcid
0x18004320a  mov     [rsp+130h+phkResult], rax; pptlib
0x18004320f  movzx   r8d, di; wVerMinor
0x180043213  lea     rcx, [rsp+130h+pclsid]; rguid
0x180043218  call    cs:__imp_LoadRegTypeLib
0x18004321e  mov     ebx, eax
0x180043220  test    eax, eax
0x180043222  js      short loc_180043244
0x180043224  mov     rax, [rsp+130h+pptlib]
0x180043229  xor     ebx, ebx
0x18004322b  mov     [r14], rax
0x18004322e  mov     [rsp+130h+pptlib], 0
0x180043237  jmp     short loc_180043244
0x180043239  call    __report_rangecheckfailure
0x18004323f  mov     ebx, 80004005h
0x180043244  mov     rcx, [rsp+130h+hKey]; hKey
0x180043249  test    rcx, rcx
0x18004324c  jz      short loc_18004325D
0x18004324e  call    cs:__imp_RegCloseKey
0x180043254  mov     [rsp+130h+hKey], 0
0x18004325d  mov     rcx, [rsp+130h+var_E8]; hKey
0x180043262  test    rcx, rcx
0x180043265  jz      short loc_180043276
0x180043267  call    cs:__imp_RegCloseKey
0x18004326d  mov     [rsp+130h+var_E8], 0
0x180043276  mov     rcx, [rsp+130h+pptlib]
0x18004327b  test    rcx, rcx
0x18004327e  jz      short loc_18004328C
0x180043280  mov     rax, [rcx]
0x180043283  mov     rax, [rax+10h]
0x180043287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004328c  mov     eax, ebx
0x18004328e  mov     rcx, [rbp+30h+var_20]
0x180043292  xor     rcx, rsp; StackCookie
0x180043295  call    __security_check_cookie
0x18004329a  lea     r11, [rsp+130h+var_10]
0x1800432a2  mov     rbx, [r11+30h]
0x1800432a6  mov     rsi, [r11+38h]
0x1800432aa  mov     rsp, r11
0x1800432ad  pop     r14
0x1800432af  pop     rdi
0x1800432b0  pop     rbp
0x1800432b1  retn
```
