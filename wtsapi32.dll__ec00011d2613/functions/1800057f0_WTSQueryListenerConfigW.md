# WTSQueryListenerConfigW

- ea: `0x1800057f0`
- end: `0x180005ac2`
- name: `WTSQueryListenerConfigW`
- size: `722`
- prototype: `BOOL __stdcall(HANDLE hServer, PVOID pReserved, DWORD Reserved, LPWSTR pListenerName, PWTSLISTENERCONFIGW pBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b230`

## callees

- `0x180004150`
- `0x1800057f0`
- `0x18001558e`
- `0x1800155c0`
- `0x180015650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800058dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005893`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005893`
- `REGAPI!RegWinstationQuerySecurityConfig_Machine` at `0x1800058f0`
- `REGAPI!RegWinstationQuerySecurityConfig_Machine` at `0x1800058f0`
- `REGAPI!RegWinStationQueryExNew` at `0x1800058d1`
- `REGAPI!RegWinStationQueryExNew` at `0x1800058d1`

## pseudocode

```c
BOOL __stdcall WTSQueryListenerConfigW(
        HANDLE hServer,
        PVOID pReserved,
        DWORD Reserved,
        LPWSTR pListenerName,
        PWTSLISTENERCONFIGW pBuffer)
{
  BOOL v9; // ebx
  unsigned __int8 *v10; // rdi
  DWORD v11; // ecx
  DWORD SecurityConfig_Machine; // eax
  _DWORD v14[4]; // [rsp+40h] [rbp-17E8h] BYREF
  _BYTE v15[288]; // [rsp+50h] [rbp-17D8h] BYREF
  _BYTE v16[5760]; // [rsp+170h] [rbp-16B8h] BYREF

  v9 = 0;
  memset_0(v16, 0, 0x1678u);
  v14[0] = 0;
  memset_0(v15, 0, sizeof(v15));
  if ( hServer || pReserved || Reserved || !pListenerName || !pBuffer )
  {
    v11 = 87;
    goto LABEL_14;
  }
  v10 = (unsigned __int8 *)LocalAlloc(0x40u, 0x28E8u);
  if ( !v10 )
  {
    v11 = 14;
LABEL_14:
    SetLastError(v11);
    return v9;
  }
  SecurityConfig_Machine = RegWinStationQueryExNew(0, v16, pListenerName, v10, 10472, v14, 0);
  if ( SecurityConfig_Machine
    || (SecurityConfig_Machine = RegWinstationQuerySecurityConfig_Machine(pListenerName, v15)) != 0 )
  {
    SetLastError(SecurityConfig_Machine);
  }
  else
  {
    v9 = 1;
    pBuffer->version = 1;
    pBuffer->fEnableListener = *(_DWORD *)v10 & 1;
    pBuffer->MaxConnectionCount = *((_DWORD *)v10 + 1);
    pBuffer->fPromptForPassword = (*((_DWORD *)v10 + 1983) >> 12) & 1;
    pBuffer->fInheritColorDepth = (*((_DWORD *)v10 + 1984) >> 8) & 1;
    pBuffer->ColorDepth = (*((_DWORD *)v10 + 1984) >> 5) & 7;
    pBuffer->fInheritBrokenTimeoutSettings = (*((_DWORD *)v10 + 1983) >> 1) & 1;
    pBuffer->fDisablePrinterRedirection = (*((_DWORD *)v10 + 1983) >> 29) & 1;
    pBuffer->fDisableDriveRedirection = (*((_DWORD *)v10 + 1983) >> 30) & 1;
    pBuffer->fDisableComPortRedirection = *((_DWORD *)v10 + 1983) >> 31;
    pBuffer->fDisableLPTPortRedirection = *((_DWORD *)v10 + 1984) & 1;
    pBuffer->fDisableClipboardRedirection = (*((_DWORD *)v10 + 1984) >> 1) & 1;
    pBuffer->fDisableAudioRedirection = (*((_DWORD *)v10 + 1984) >> 3) & 1;
    pBuffer->fDisablePNPRedirection = (*((_DWORD *)v10 + 1984) >> 11) & 1;
    pBuffer->fDisableDefaultMainClientPrinter = (*((_DWORD *)v10 + 1983) >> 19) & 1;
    pBuffer->LanAdapter = *((_DWORD *)v10 + 45);
    pBuffer->PortNumber = *((_DWORD *)v10 + 42);
    pBuffer->fInheritShadowSettings = (*((_DWORD *)v10 + 1983) >> 6) & 1;
    pBuffer->ShadowSettings = *((_DWORD *)v10 + 2296);
    pBuffer->TimeoutSettingsConnection = *((_DWORD *)v10 + 2297);
    pBuffer->TimeoutSettingsDisconnection = *((_DWORD *)v10 + 2298);
    pBuffer->TimeoutSettingsIdle = *((_DWORD *)v10 + 2299);
    pBuffer->MinEncryptionLevel = v10[9204];
    pBuffer->SecurityLayer = v15[0];
    pBuffer->UserAuthentication = v15[1];
    StringCchCopyW(pBuffer->Comment, 0x3Du, (STRSAFE_LPCWSTR)v10 + 3904);
    StringCchCopyW(pBuffer->LogonUserName, 0x15u, (STRSAFE_LPCWSTR)v10 + 3970);
    StringCchCopyW(pBuffer->LogonDomain, 0x12u, (STRSAFE_LPCWSTR)v10 + 3991);
    StringCchCopyW(pBuffer->WorkDirectory, 0x105u, (STRSAFE_LPCWSTR)v10 + 4024);
    StringCchCopyW(pBuffer->InitialProgram, 0x105u, (STRSAFE_LPCWSTR)v10 + 4281);
  }
  LocalFree(v10);
  return v9;
}

```

## disassembly

```asm
0x1800057f0  mov     [rsp+arg_8], rbx
0x1800057f5  push    rbp
0x1800057f6  push    rsi
0x1800057f7  push    rdi
0x1800057f8  push    r14
0x1800057fa  push    r15
0x1800057fc  mov     eax, 1800h
0x180005801  call    _alloca_probe
0x180005806  sub     rsp, rax
0x180005809  mov     rax, cs:__security_cookie
0x180005810  xor     rax, rsp
0x180005813  mov     [rsp+1828h+var_38], rax
0x18000581b  mov     rsi, [rsp+1828h+pBuffer]
0x180005823  mov     r14d, r8d
0x180005826  mov     r15, rdx
0x180005829  mov     rdi, rcx
0x18000582c  xor     edx, edx; Val
0x18000582e  lea     rcx, [rsp+1828h+var_16B8]; void *
0x180005836  mov     r8d, 1678h; Size
0x18000583c  mov     rbp, r9
0x18000583f  xor     ebx, ebx
0x180005841  call    memset_0
0x180005846  xor     edx, edx; Val
0x180005848  mov     [rsp+1828h+var_17E8], ebx
0x18000584c  mov     r8d, 120h; Size
0x180005852  lea     rcx, [rsp+1828h+var_17D8]; void *
0x180005857  call    memset_0
0x18000585c  test    rdi, rdi
0x18000585f  jnz     loc_180005A8E
0x180005865  test    r15, r15
0x180005868  jnz     loc_180005A8E
0x18000586e  test    r14d, r14d
0x180005871  jnz     loc_180005A8E
0x180005877  test    rbp, rbp
0x18000587a  jz      loc_180005A8E
0x180005880  test    rsi, rsi
0x180005883  jz      loc_180005A8E
0x180005889  mov     edx, 28E8h; uBytes
0x18000588e  mov     ecx, 40h ; '@'; uFlags
0x180005893  call    cs:__imp_LocalAlloc
0x180005899  mov     rdi, rax
0x18000589c  test    rax, rax
0x18000589f  jnz     short loc_1800058AB
0x1800058a1  mov     ecx, 0Eh
0x1800058a6  jmp     loc_180005A93
0x1800058ab  lea     rax, [rsp+1828h+var_17E8]
0x1800058b0  mov     [rsp+1828h+var_17F8], bl
0x1800058b4  mov     [rsp+1828h+var_1800], rax
0x1800058b9  lea     rdx, [rsp+1828h+var_16B8]
0x1800058c1  mov     r9, rdi
0x1800058c4  mov     [rsp+1828h+var_1808], 28E8h
0x1800058cc  mov     r8, rbp
0x1800058cf  xor     ecx, ecx
0x1800058d1  call    cs:__imp_RegWinStationQueryExNew
0x1800058d7  test    eax, eax
0x1800058d9  jz      short loc_1800058E8
0x1800058db  mov     ecx, eax; dwErrCode
0x1800058dd  call    cs:__imp_SetLastError
0x1800058e3  jmp     loc_180005A83
0x1800058e8  lea     rdx, [rsp+1828h+var_17D8]
0x1800058ed  mov     rcx, rbp
0x1800058f0  call    cs:__imp_RegWinstationQuerySecurityConfig_Machine
0x1800058f6  test    eax, eax
0x1800058f8  jnz     short loc_1800058DB
0x1800058fa  mov     ebx, 1
0x1800058ff  lea     r8, [rdi+1E80h]; pszSrc
0x180005906  mov     [rsi], ebx
0x180005908  lea     rcx, [rsi+68h]; pszDest
0x18000590c  mov     eax, [rdi]
0x18000590e  mov     edx, 3Dh ; '='; cchDest
0x180005913  and     eax, ebx
0x180005915  mov     [rsi+4], eax
0x180005918  mov     eax, [rdi+4]
0x18000591b  mov     [rsi+8], eax
0x18000591e  mov     eax, [rdi+1EFCh]
0x180005924  shr     eax, 0Ch
0x180005927  and     eax, ebx
0x180005929  mov     [rsi+0Ch], eax
0x18000592c  mov     eax, [rdi+1F00h]
0x180005932  shr     eax, 8
0x180005935  and     eax, ebx
0x180005937  mov     [rsi+10h], eax
0x18000593a  mov     eax, [rdi+1F00h]
0x180005940  shr     eax, 5
0x180005943  and     eax, 7
0x180005946  mov     [rsi+14h], eax
0x180005949  mov     eax, [rdi+1EFCh]
0x18000594f  shr     eax, 1
0x180005951  and     eax, ebx
0x180005953  mov     [rsi+18h], eax
0x180005956  mov     eax, [rdi+1EFCh]
0x18000595c  shr     eax, 1Dh
0x18000595f  and     eax, ebx
0x180005961  mov     [rsi+20h], eax
0x180005964  mov     eax, [rdi+1EFCh]
0x18000596a  shr     eax, 1Eh
0x18000596d  and     eax, ebx
0x18000596f  mov     [rsi+24h], eax
0x180005972  mov     eax, [rdi+1EFCh]
0x180005978  shr     eax, 1Fh
0x18000597b  mov     [rsi+28h], eax
0x18000597e  mov     eax, [rdi+1F00h]
0x180005984  and     eax, ebx
0x180005986  mov     [rsi+2Ch], eax
0x180005989  mov     eax, [rdi+1F00h]
0x18000598f  shr     eax, 1
0x180005991  and     eax, ebx
0x180005993  mov     [rsi+30h], eax
0x180005996  mov     eax, [rdi+1F00h]
0x18000599c  shr     eax, 3
0x18000599f  and     eax, ebx
0x1800059a1  mov     [rsi+34h], eax
0x1800059a4  mov     eax, [rdi+1F00h]
0x1800059aa  shr     eax, 0Bh
0x1800059ad  and     eax, ebx
0x1800059af  mov     [rsi+38h], eax
0x1800059b2  mov     eax, [rdi+1EFCh]
0x1800059b8  shr     eax, 13h
0x1800059bb  and     eax, ebx
0x1800059bd  mov     [rsi+3Ch], eax
0x1800059c0  mov     eax, [rdi+0B4h]
0x1800059c6  mov     [rsi+40h], eax
0x1800059c9  mov     eax, [rdi+0A8h]
0x1800059cf  mov     [rsi+44h], eax
0x1800059d2  mov     eax, [rdi+1EFCh]
0x1800059d8  shr     eax, 6
0x1800059db  and     eax, ebx
0x1800059dd  mov     [rsi+48h], eax
0x1800059e0  mov     eax, [rdi+23E0h]
0x1800059e6  mov     [rsi+4Ch], eax
0x1800059e9  mov     eax, [rdi+23E4h]
0x1800059ef  mov     [rsi+50h], eax
0x1800059f2  mov     eax, [rdi+23E8h]
0x1800059f8  mov     [rsi+54h], eax
0x1800059fb  mov     eax, [rdi+23ECh]
0x180005a01  mov     [rsi+58h], eax
0x180005a04  movzx   eax, byte ptr [rdi+23F4h]
0x180005a0b  mov     [rsi+60h], eax
0x180005a0e  movzx   eax, [rsp+1828h+var_17D8]
0x180005a13  mov     [rsi+5Ch], eax
0x180005a16  movzx   eax, [rsp+1828h+var_17D7]
0x180005a1b  mov     [rsi+64h], eax
0x180005a1e  call    StringCchCopyW
0x180005a23  lea     r8, [rdi+1F04h]; pszSrc
0x180005a2a  lea     rcx, [rsi+0E2h]; pszDest
0x180005a31  mov     edx, 15h; cchDest
0x180005a36  call    StringCchCopyW
0x180005a3b  lea     r8, [rdi+1F2Eh]; pszSrc
0x180005a42  mov     edx, 12h; cchDest
0x180005a47  lea     rcx, [rsi+10Ch]; pszDest
0x180005a4e  call    StringCchCopyW
0x180005a53  lea     r8, [rdi+1F70h]; pszSrc
0x180005a5a  mov     edx, 105h; cchDest
0x180005a5f  lea     rcx, [rsi+130h]; pszDest
0x180005a66  call    StringCchCopyW
0x180005a6b  lea     r8, [rdi+2172h]; pszSrc
0x180005a72  mov     edx, 105h; cchDest
0x180005a77  lea     rcx, [rsi+33Ah]; pszDest
0x180005a7e  call    StringCchCopyW
0x180005a83  mov     rcx, rdi; hMem
0x180005a86  call    cs:__imp_LocalFree
0x180005a8c  jmp     short loc_180005A99
0x180005a8e  mov     ecx, 57h ; 'W'; dwErrCode
0x180005a93  call    cs:__imp_SetLastError
0x180005a99  mov     eax, ebx
0x180005a9b  mov     rcx, [rsp+1828h+var_38]
0x180005aa3  xor     rcx, rsp; StackCookie
0x180005aa6  call    __security_check_cookie
0x180005aab  mov     rbx, [rsp+1828h+arg_8]
0x180005ab3  add     rsp, 1800h
0x180005aba  pop     r15
0x180005abc  pop     r14
0x180005abe  pop     rdi
0x180005abf  pop     rsi
0x180005ac0  pop     rbp
0x180005ac1  retn
```
