# CUmRdpPrn::ReadPrinterDriverPolicy(void)

- ea: `0x180009108`
- end: `0x180009345`
- name: `?ReadPrinterDriverPolicy@CUmRdpPrn@@QEAAXXZ`
- size: `573`
- prototype: `void __fastcall(CUmRdpPrn *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011850`
- `0x1800165c8`

## callees

- `0x180009108`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800092f3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800092f9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800092f9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180009250`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180009250`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009166`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009296`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009166`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009296`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000919f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800091e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009227`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800092ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000919f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800091e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009227`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800092ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000923b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800092e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800092eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000923b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800092e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800092eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000926f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000926f`
- `WINSTA!WinStationFreePropertyValue` at `0x180009335`
- `WINSTA!WinStationFreePropertyValue` at `0x180009335`
- `WINSTA!WinStationGetConnectionProperty` at `0x18000930f`
- `WINSTA!WinStationGetConnectionProperty` at `0x18000930f`

## string_xrefs

- `0x18000914f`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18000928f`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180009203`: `DisablePOAccess`

## pseudocode

```c
void __fastcall CUmRdpPrn::ReadPrinterDriverPolicy(CUmRdpPrn *this)
{
  int v2; // edi
  char ConnectionProperty; // al
  __int64 v4; // rcx
  int v5; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  __int64 v7; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+28h] BYREF
  int Data; // [rsp+78h] [rbp+30h] BYREF
  HKEY v10; // [rsp+80h] [rbp+38h] BYREF
  int v11; // [rsp+88h] [rbp+40h] BYREF

  *(_QWORD *)((char *)this + 20) = 3;
  *(_QWORD *)((char *)this + 12) = 20;
  Data = 0;
  cbData = 4;
  hKey = 0;
  v7 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_26;
  }
  v2 = 0;
  if ( !RegQueryValueExW(hKey, L"RedirectOnlyDefaultClientPrinter", 0, 0, (LPBYTE)&Data, &cbData) )
  {
    v2 = 1;
    *((_DWORD *)this + 6) = Data != 0;
  }
  LODWORD(v10) = 0;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"MaxPrintersPerSession", 0, 0, (LPBYTE)&v10, &cbData) )
    *((_DWORD *)this + 3) = (_DWORD)v10;
  v11 = 0;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"DisablePOAccess", 0, 0, (LPBYTE)&v11, &cbData) )
    *((_DWORD *)this + 4) = v11;
  RegCloseKey(hKey);
  if ( !v2 )
  {
LABEL_26:
    if ( ImpersonateLoggedOnUser(*((HANDLE *)this + 23)) )
    {
      v10 = 0;
      if ( RegOpenCurrentUser(0x20019u, &v10) )
      {
        GetLastError();
      }
      else
      {
        if ( !RegOpenKeyExW(v10, L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services", 0, 0x20019u, &hKey) )
        {
          cbData = 4;
          if ( !RegQueryValueExW(hKey, L"RedirectOnlyDefaultClientPrinter", 0, 0, (LPBYTE)&Data, &cbData) )
            *((_DWORD *)this + 6) = Data != 0;
          RegCloseKey(hKey);
        }
        RegCloseKey(v10);
      }
      RevertToSelf();
    }
  }
  ConnectionProperty = WinStationGetConnectionProperty(**(unsigned int **)this, PROPERTY_TYPE_EASY_PRINT, &v7);
  v4 = v7;
  if ( ConnectionProperty && *(_WORD *)v7 == 1 )
    v5 = *(_DWORD *)(v7 + 8);
  else
    v5 = 2;
  *((_DWORD *)this + 5) = v5;
  if ( v4 )
    WinStationFreePropertyValue();
}

```

## disassembly

```asm
0x180009108  push    rbp
0x18000910a  push    rbx
0x18000910b  push    rdi
0x18000910c  push    r12
0x18000910e  mov     rbp, rsp
0x180009111  sub     rsp, 48h
0x180009115  mov     rbx, rcx
0x180009118  mov     qword ptr [rcx+14h], 3
0x180009120  mov     qword ptr [rcx+0Ch], 14h
0x180009128  lea     rax, [rbp+hKey]
0x18000912c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009133  mov     [rsp+48h+phkResult], rax; phkResult
0x180009138  mov     r9d, 20019h; samDesired
0x18000913e  mov     [rbp+Data], 0
0x180009145  xor     r8d, r8d; ulOptions
0x180009148  mov     [rbp+cbData], 4
0x18000914f  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180009156  mov     [rbp+hKey], 0
0x18000915e  mov     [rbp+var_10], 0
0x180009166  call    cs:__imp_RegOpenKeyExW
0x18000916c  mov     r12d, 1
0x180009172  test    eax, eax
0x180009174  jnz     loc_180009249
0x18000917a  mov     rcx, [rbp+hKey]; hKey
0x18000917e  lea     rax, [rbp+cbData]
0x180009182  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180009187  lea     rdx, aRedirectonlyde; "RedirectOnlyDefaultClientPrinter"
0x18000918e  lea     rax, [rbp+Data]
0x180009192  xor     r9d, r9d; lpType
0x180009195  xor     r8d, r8d; lpReserved
0x180009198  mov     [rsp+48h+phkResult], rax; lpData
0x18000919d  xor     edi, edi
0x18000919f  call    cs:__imp_RegQueryValueExW
0x1800091a5  test    eax, eax
0x1800091a7  jnz     short loc_1800091B5
0x1800091a9  cmp     [rbp+Data], eax
0x1800091ac  mov     edi, r12d
0x1800091af  setnz   al
0x1800091b2  mov     [rbx+18h], eax
0x1800091b5  mov     rcx, [rbp+hKey]; hKey
0x1800091b9  lea     rax, [rbp+cbData]
0x1800091bd  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800091c2  lea     rdx, aMaxprintersper; "MaxPrintersPerSession"
0x1800091c9  lea     rax, [rbp+arg_10]
0x1800091cd  mov     dword ptr [rbp+arg_10], 0
0x1800091d4  xor     r9d, r9d; lpType
0x1800091d7  mov     [rsp+48h+phkResult], rax; lpData
0x1800091dc  xor     r8d, r8d; lpReserved
0x1800091df  mov     [rbp+cbData], 4
0x1800091e6  call    cs:__imp_RegQueryValueExW
0x1800091ec  test    eax, eax
0x1800091ee  jnz     short loc_1800091F6
0x1800091f0  mov     eax, dword ptr [rbp+arg_10]
0x1800091f3  mov     [rbx+0Ch], eax
0x1800091f6  mov     rcx, [rbp+hKey]; hKey
0x1800091fa  lea     rax, [rbp+cbData]
0x1800091fe  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180009203  lea     rdx, aDisablepoacces; "DisablePOAccess"
0x18000920a  lea     rax, [rbp+arg_18]
0x18000920e  mov     [rbp+arg_18], 0
0x180009215  xor     r9d, r9d; lpType
0x180009218  mov     [rsp+48h+phkResult], rax; lpData
0x18000921d  xor     r8d, r8d; lpReserved
0x180009220  mov     [rbp+cbData], 4
0x180009227  call    cs:__imp_RegQueryValueExW
0x18000922d  test    eax, eax
0x18000922f  jnz     short loc_180009237
0x180009231  mov     eax, [rbp+arg_18]
0x180009234  mov     [rbx+10h], eax
0x180009237  mov     rcx, [rbp+hKey]; hKey
0x18000923b  call    cs:__imp_RegCloseKey
0x180009241  test    edi, edi
0x180009243  jnz     loc_1800092FF
0x180009249  mov     rcx, [rbx+0B8h]; hToken
0x180009250  call    cs:__imp_ImpersonateLoggedOnUser
0x180009256  test    eax, eax
0x180009258  jz      loc_1800092FF
0x18000925e  lea     rdx, [rbp+arg_10]; phkResult
0x180009262  mov     [rbp+arg_10], 0
0x18000926a  mov     ecx, 20019h; samDesired
0x18000926f  call    cs:__imp_RegOpenCurrentUser
0x180009275  test    eax, eax
0x180009277  jnz     short loc_1800092F3
0x180009279  mov     rcx, [rbp+arg_10]; hKey
0x18000927d  lea     rax, [rbp+hKey]
0x180009281  mov     r9d, 20019h; samDesired
0x180009287  mov     [rsp+48h+phkResult], rax; phkResult
0x18000928c  xor     r8d, r8d; ulOptions
0x18000928f  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180009296  call    cs:__imp_RegOpenKeyExW
0x18000929c  test    eax, eax
0x18000929e  jnz     short loc_1800092E7
0x1800092a0  mov     rcx, [rbp+hKey]; hKey
0x1800092a4  lea     rax, [rbp+cbData]
0x1800092a8  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800092ad  lea     rdx, aRedirectonlyde; "RedirectOnlyDefaultClientPrinter"
0x1800092b4  lea     rax, [rbp+Data]
0x1800092b8  mov     [rbp+cbData], 4
0x1800092bf  xor     r9d, r9d; lpType
0x1800092c2  mov     [rsp+48h+phkResult], rax; lpData
0x1800092c7  xor     r8d, r8d; lpReserved
0x1800092ca  call    cs:__imp_RegQueryValueExW
0x1800092d0  test    eax, eax
0x1800092d2  jnz     short loc_1800092DD
0x1800092d4  cmp     [rbp+Data], eax
0x1800092d7  setnz   al
0x1800092da  mov     [rbx+18h], eax
0x1800092dd  mov     rcx, [rbp+hKey]; hKey
0x1800092e1  call    cs:__imp_RegCloseKey
0x1800092e7  mov     rcx, [rbp+arg_10]; hKey
0x1800092eb  call    cs:__imp_RegCloseKey
0x1800092f1  jmp     short loc_1800092F9
0x1800092f3  call    cs:__imp_GetLastError
0x1800092f9  call    cs:__imp_RevertToSelf
0x1800092ff  mov     rcx, [rbx]
0x180009302  lea     r8, [rbp+var_10]
0x180009306  lea     rdx, PROPERTY_TYPE_EASY_PRINT
0x18000930d  mov     ecx, [rcx]
0x18000930f  call    cs:__imp_WinStationGetConnectionProperty
0x180009315  mov     rcx, [rbp+var_10]
0x180009319  test    al, al
0x18000931b  jz      short loc_180009328
0x18000931d  cmp     r12w, [rcx]
0x180009321  jnz     short loc_180009328
0x180009323  mov     eax, [rcx+8]
0x180009326  jmp     short loc_18000932D
0x180009328  mov     eax, 2
0x18000932d  mov     [rbx+14h], eax
0x180009330  test    rcx, rcx
0x180009333  jz      short loc_18000933B
0x180009335  call    cs:__imp_WinStationFreePropertyValue
0x18000933b  add     rsp, 48h
0x18000933f  pop     r12
0x180009341  pop     rdi
0x180009342  pop     rbx
0x180009343  pop     rbp
0x180009344  retn
```
