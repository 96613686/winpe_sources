# UpdatePrinterRegUser

- ea: `0x140011770`
- end: `0x140011a97`
- name: `UpdatePrinterRegUser`
- size: `807`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140011aa0`
- `0x140067ca8`
- `0x140067e8c`

## callees

- `0x140003fb0`
- `0x140011770`
- `0x140013d28`
- `0x140015378`
- `0x140017e0c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140071c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400119fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400119fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001198e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400119f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001198e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400119f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400117e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001182d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011899`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001193f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400117e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001182d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011899`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001193f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140011903`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140011917`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140011957`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400119c4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140011903`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140011917`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140011957`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400119c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011968`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400119df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011a29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011a3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011a55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011a69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011968`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400119df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011a29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011a3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011a55`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011a69`

## pseudocode

```c
__int64 __fastcall UpdatePrinterRegUser(HKEY a1, const WCHAR *a2, WCHAR *a3, unsigned __int16 *a4, int a5)
{
  HKEY v8; // r14
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rsi
  LSTATUS v12; // edi
  DWORD LastError; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v16; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v17; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v19; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v20; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v22; // [rsp+68h] [rbp-98h] BYREF

  v8 = 0;
  hKey = 0;
  LODWORD(v16) = 0;
  memset_0(&v19, 0, 0x438u);
  if ( a2 )
  {
    v10 = RegOpenKeyExW(HKEY_USERS, a2, 0, 0x2001Fu, &hKey);
    if ( v10 )
      goto LABEL_21;
    a1 = hKey;
    v8 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v19 = a1;
  v10 = RegOpenKeyExW(a1, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Devices", 0, 0x2001Fu, &phkResult);
  if ( !v10 )
  {
    v10 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows", 0, 0x2001Fu, &v20);
    if ( !v10 )
    {
      v10 = RegOpenKeyExW(hKey, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PrinterPorts", 0, 0x20006u, &v22);
      if ( !v10 )
      {
        if ( a5 )
        {
          v16 = 0;
          RegDeleteValueW(phkResult, a3);
          RegDeleteValueW(v22, a3);
          if ( !RegOpenKeyExW(hKey, L"Printers\\DevModes2", 0, 0x20006u, &v16) )
          {
            RegDeleteValueW(v16, a3);
            RegCloseKey(v16);
          }
          v17 = 0;
          lpValueName = 0;
          if ( a3 )
          {
            if ( (unsigned int)bGetDevModeLocation(hKey, a3, &v17, &lpValueName) )
            {
              v12 = RegDeleteValueW(v17, lpValueName);
              if ( v12 == 2 )
                v12 = 0;
              RegCloseKey(v17);
              if ( v12 )
              {
                SetLastError(v12);
                LastError = GetLastError();
                PrvSpoolssTelemetry::WriteDbgTraceError(
                  "bSetDevModePerUser",
                  L"Failed to set devmode.  Error %d.",
                  LastError);
              }
            }
          }
          else
          {
            SetLastError(6u);
          }
        }
        else
        {
          v11 = CheckBadPortName(a4);
          if ( !v11 )
            LODWORD(v16) = GetNetworkIdWorker(phkResult, a3);
          UpdatePrinterInfo((struct INIT_REG_USER *const)&v19, a3, v11, (unsigned int *)&v16);
        }
      }
    }
  }
LABEL_21:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v20 )
    RegCloseKey(v20);
  if ( v22 )
    RegCloseKey(v22);
  if ( v8 )
    RegCloseKey(v8);
  return v10;
}

```

## disassembly

```asm
0x140011770  push    rbp
0x140011772  push    rbx
0x140011773  push    rsi
0x140011774  push    rdi
0x140011775  push    r14
0x140011777  push    r15
0x140011779  lea     rbp, [rsp-3A8h]
0x140011781  sub     rsp, 4A8h
0x140011788  mov     rax, cs:__security_cookie
0x14001178f  xor     rax, rsp
0x140011792  mov     [rbp+3D0h+var_40], rax
0x140011799  mov     rdi, r8
0x14001179c  mov     rsi, rdx
0x14001179f  mov     rbx, rcx
0x1400117a2  xor     r14d, r14d
0x1400117a5  xor     edx, edx; Val
0x1400117a7  mov     [rsp+4D0h+hKey], r14
0x1400117ac  mov     r8d, 438h; Size
0x1400117b2  mov     dword ptr [rsp+4D0h+var_498], r14d
0x1400117b7  lea     rcx, [rsp+4D0h+var_480]; void *
0x1400117bc  mov     r15, r9
0x1400117bf  call    memset_0
0x1400117c4  test    rsi, rsi
0x1400117c7  jz      short loc_140011806
0x1400117c9  lea     rax, [rsp+4D0h+hKey]
0x1400117ce  mov     r9d, 2001Fh; samDesired
0x1400117d4  xor     r8d, r8d; ulOptions
0x1400117d7  mov     [rsp+4D0h+phkResult], rax; phkResult
0x1400117dc  mov     rdx, rsi; lpSubKey
0x1400117df  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1400117e6  call    cs:__imp_RegOpenKeyExW
0x1400117ed  nop     dword ptr [rax+rax+00h]
0x1400117f2  mov     ebx, eax
0x1400117f4  test    eax, eax
0x1400117f6  jnz     loc_140011A1F
0x1400117fc  mov     rbx, [rsp+4D0h+hKey]
0x140011801  mov     r14, rbx
0x140011804  jmp     short loc_14001180B
0x140011806  mov     [rsp+4D0h+hKey], rbx
0x14001180b  lea     rax, [rsp+4D0h+var_470]
0x140011810  mov     [rsp+4D0h+var_480], rbx
0x140011815  mov     r9d, 2001Fh; samDesired
0x14001181b  mov     [rsp+4D0h+phkResult], rax; phkResult
0x140011820  xor     r8d, r8d; ulOptions
0x140011823  lea     rdx, szRegDevicesPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001182a  mov     rcx, rbx; hKey
0x14001182d  call    cs:__imp_RegOpenKeyExW
0x140011834  nop     dword ptr [rax+rax+00h]
0x140011839  mov     ebx, eax
0x14001183b  test    eax, eax
0x14001183d  jnz     loc_140011A1F
0x140011843  mov     rcx, [rsp+4D0h+hKey]; hKey
0x140011848  lea     rax, [rsp+4D0h+var_478]
0x14001184d  mov     r9d, 2001Fh; samDesired
0x140011853  mov     [rsp+4D0h+phkResult], rax; phkResult
0x140011858  xor     r8d, r8d; ulOptions
0x14001185b  lea     rdx, szRegWindowsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140011862  call    cs:__imp_RegOpenKeyExW
0x140011869  nop     dword ptr [rax+rax+00h]
0x14001186e  mov     ebx, eax
0x140011870  test    eax, eax
0x140011872  jnz     loc_140011A1F
0x140011878  mov     rcx, [rsp+4D0h+hKey]; hKey
0x14001187d  lea     rax, [rsp+4D0h+var_468]
0x140011882  mov     esi, 20006h
0x140011887  mov     [rsp+4D0h+phkResult], rax; phkResult
0x14001188c  mov     r9d, esi; samDesired
0x14001188f  lea     rdx, szRegPrinterPortsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140011896  xor     r8d, r8d; ulOptions
0x140011899  call    cs:__imp_RegOpenKeyExW
0x1400118a0  nop     dword ptr [rax+rax+00h]
0x1400118a5  mov     ebx, eax
0x1400118a7  test    eax, eax
0x1400118a9  jnz     loc_140011A1F
0x1400118af  cmp     [rbp+3D0h+arg_20], eax
0x1400118b5  jnz     short loc_1400118F2
0x1400118b7  mov     rcx, r15; unsigned __int16 *
0x1400118ba  call    ?CheckBadPortName@@YAPEAGPEAG@Z; CheckBadPortName(ushort *)
0x1400118bf  mov     rsi, rax
0x1400118c2  test    rax, rax
0x1400118c5  jnz     short loc_1400118D8
0x1400118c7  mov     rcx, [rsp+4D0h+var_470]; hKey
0x1400118cc  mov     rdx, rdi; unsigned __int16 *
0x1400118cf  call    ?GetNetworkIdWorker@@YAKPEAUHKEY__@@PEAG@Z; GetNetworkIdWorker(HKEY__ *,ushort *)
0x1400118d4  mov     dword ptr [rsp+4D0h+var_498], eax
0x1400118d8  lea     r9, [rsp+4D0h+var_498]; unsigned int *
0x1400118dd  mov     r8, rsi; unsigned __int16 *
0x1400118e0  mov     rdx, rdi; unsigned __int16 *
0x1400118e3  lea     rcx, [rsp+4D0h+var_480]; struct INIT_REG_USER *
0x1400118e8  call    ?UpdatePrinterInfo@@YAHQEAUINIT_REG_USER@@PEBG1PEAK@Z; UpdatePrinterInfo(INIT_REG_USER * const,ushort const *,ushort const *,ulong *)
0x1400118ed  jmp     loc_140011A1F
0x1400118f2  mov     rcx, [rsp+4D0h+var_470]; hKey
0x1400118f7  mov     rdx, rdi; lpValueName
0x1400118fa  mov     [rsp+4D0h+var_498], 0
0x140011903  call    cs:__imp_RegDeleteValueW
0x14001190a  nop     dword ptr [rax+rax+00h]
0x14001190f  mov     rcx, [rsp+4D0h+var_468]; hKey
0x140011914  mov     rdx, rdi; lpValueName
0x140011917  call    cs:__imp_RegDeleteValueW
0x14001191e  nop     dword ptr [rax+rax+00h]
0x140011923  mov     rcx, [rsp+4D0h+hKey]; hKey
0x140011928  lea     rax, [rsp+4D0h+var_498]
0x14001192d  mov     r9d, esi; samDesired
0x140011930  mov     [rsp+4D0h+phkResult], rax; phkResult
0x140011935  xor     r8d, r8d; ulOptions
0x140011938  lea     rdx, szDevModes2Path; "Printers\\DevModes2"
0x14001193f  call    cs:__imp_RegOpenKeyExW
0x140011946  nop     dword ptr [rax+rax+00h]
0x14001194b  test    eax, eax
0x14001194d  jnz     short loc_140011974
0x14001194f  mov     rcx, [rsp+4D0h+var_498]; hKey
0x140011954  mov     rdx, rdi; lpValueName
0x140011957  call    cs:__imp_RegDeleteValueW
0x14001195e  nop     dword ptr [rax+rax+00h]
0x140011963  mov     rcx, [rsp+4D0h+var_498]; hKey
0x140011968  call    cs:__imp_RegCloseKey
0x14001196f  nop     dword ptr [rax+rax+00h]
0x140011974  mov     [rsp+4D0h+var_490], 0
0x14001197d  mov     [rsp+4D0h+lpValueName], 0
0x140011986  test    rdi, rdi
0x140011989  jnz     short loc_14001199F
0x14001198b  lea     ecx, [rdi+6]; dwErrCode
0x14001198e  call    cs:__imp_SetLastError
0x140011995  nop     dword ptr [rax+rax+00h]
0x14001199a  jmp     loc_140011A1F
0x14001199f  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1400119a4  lea     r9, [rsp+4D0h+lpValueName]; unsigned __int16 **
0x1400119a9  lea     r8, [rsp+4D0h+var_490]; phkResult
0x1400119ae  mov     rdx, rdi; unsigned __int16 *
0x1400119b1  call    ?bGetDevModeLocation@@YAHPEAUHKEY__@@PEBGPEAPEAU1@PEAPEBG@Z; bGetDevModeLocation(HKEY__ *,ushort const *,HKEY__ * *,ushort const * *)
0x1400119b6  test    eax, eax
0x1400119b8  jz      short loc_140011A1F
0x1400119ba  mov     rdx, [rsp+4D0h+lpValueName]; lpValueName
0x1400119bf  mov     rcx, [rsp+4D0h+var_490]; hKey
0x1400119c4  call    cs:__imp_RegDeleteValueW
0x1400119cb  nop     dword ptr [rax+rax+00h]
0x1400119d0  mov     rcx, [rsp+4D0h+var_490]; hKey
0x1400119d5  mov     edi, eax
0x1400119d7  xor     eax, eax
0x1400119d9  cmp     edi, 2
0x1400119dc  cmovz   edi, eax
0x1400119df  call    cs:__imp_RegCloseKey
0x1400119e6  nop     dword ptr [rax+rax+00h]
0x1400119eb  test    edi, edi
0x1400119ed  jz      short loc_140011A1F
0x1400119ef  mov     ecx, edi; dwErrCode
0x1400119f1  call    cs:__imp_SetLastError
0x1400119f8  nop     dword ptr [rax+rax+00h]
0x1400119fd  call    cs:__imp_GetLastError
0x140011a04  nop     dword ptr [rax+rax+00h]
0x140011a09  mov     r8d, eax
0x140011a0c  lea     rdx, aFailedToSetDev; "Failed to set devmode.  Error %d."
0x140011a13  lea     rcx, aBsetdevmodeper; "bSetDevModePerUser"
0x140011a1a  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140011a1f  mov     rcx, [rsp+4D0h+var_470]; hKey
0x140011a24  test    rcx, rcx
0x140011a27  jz      short loc_140011A35
0x140011a29  call    cs:__imp_RegCloseKey
0x140011a30  nop     dword ptr [rax+rax+00h]
0x140011a35  mov     rcx, [rsp+4D0h+var_478]; hKey
0x140011a3a  test    rcx, rcx
0x140011a3d  jz      short loc_140011A4B
0x140011a3f  call    cs:__imp_RegCloseKey
0x140011a46  nop     dword ptr [rax+rax+00h]
0x140011a4b  mov     rcx, [rsp+4D0h+var_468]; hKey
0x140011a50  test    rcx, rcx
0x140011a53  jz      short loc_140011A61
0x140011a55  call    cs:__imp_RegCloseKey
0x140011a5c  nop     dword ptr [rax+rax+00h]
0x140011a61  test    r14, r14
0x140011a64  jz      short loc_140011A75
0x140011a66  mov     rcx, r14; hKey
0x140011a69  call    cs:__imp_RegCloseKey
0x140011a70  nop     dword ptr [rax+rax+00h]
0x140011a75  mov     eax, ebx
0x140011a77  mov     rcx, [rbp+3D0h+var_40]
0x140011a7e  xor     rcx, rsp; StackCookie
0x140011a81  call    __security_check_cookie
0x140011a86  add     rsp, 4A8h
0x140011a8d  pop     r15
0x140011a8f  pop     r14
0x140011a91  pop     rdi
0x140011a92  pop     rsi
0x140011a93  pop     rbx
0x140011a94  pop     rbp
0x140011a95  retn
```
