# UpdatePrinterRegUser

- ea: `0x1400104d0`
- end: `0x140010787`
- name: `UpdatePrinterRegUser`
- size: `695`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140010790`
- `0x140061cfc`
- `0x140061ed8`

## callees

- `0x140003df0`
- `0x1400104d0`
- `0x140012adc`
- `0x1400140cc`
- `0x14001696c`
- `0x14002abc0`
- `0x14002b810`
- `0x14006b080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001070c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001070c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400106b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010706`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400106b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140010706`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010546`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010587`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400105b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400105e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001067b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010546`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140010587`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400105b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400105e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001067b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14001064b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140010659`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14001068d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400106e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14001064b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140010659`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14001068d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400106e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010698`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400106fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010732`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010742`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010760`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010698`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400106fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010732`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010742`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010752`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010760`

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
0x1400104d0  push    rbp
0x1400104d2  push    rbx
0x1400104d3  push    rsi
0x1400104d4  push    rdi
0x1400104d5  push    r14
0x1400104d7  push    r15
0x1400104d9  lea     rbp, [rsp-3A8h]
0x1400104e1  sub     rsp, 4A8h
0x1400104e8  mov     rax, cs:__security_cookie
0x1400104ef  xor     rax, rsp
0x1400104f2  mov     [rbp+3D0h+var_40], rax
0x1400104f9  mov     rdi, r8
0x1400104fc  mov     rsi, rdx
0x1400104ff  mov     rbx, rcx
0x140010502  xor     r14d, r14d
0x140010505  xor     edx, edx; Val
0x140010507  mov     [rsp+4D0h+hKey], r14
0x14001050c  mov     r8d, 438h; Size
0x140010512  mov     dword ptr [rsp+4D0h+var_498], r14d
0x140010517  lea     rcx, [rsp+4D0h+var_480]; void *
0x14001051c  mov     r15, r9
0x14001051f  call    memset_0
0x140010524  test    rsi, rsi
0x140010527  jz      short loc_140010560
0x140010529  lea     rax, [rsp+4D0h+hKey]
0x14001052e  mov     r9d, 2001Fh; samDesired
0x140010534  xor     r8d, r8d; ulOptions
0x140010537  mov     [rsp+4D0h+phkResult], rax; phkResult
0x14001053c  mov     rdx, rsi; lpSubKey
0x14001053f  mov     rcx, 0FFFFFFFF80000003h; hKey
0x140010546  call    cs:__imp_RegOpenKeyExW
0x14001054c  mov     ebx, eax
0x14001054e  test    eax, eax
0x140010550  jnz     loc_140010728
0x140010556  mov     rbx, [rsp+4D0h+hKey]
0x14001055b  mov     r14, rbx
0x14001055e  jmp     short loc_140010565
0x140010560  mov     [rsp+4D0h+hKey], rbx
0x140010565  lea     rax, [rsp+4D0h+var_470]
0x14001056a  mov     [rsp+4D0h+var_480], rbx
0x14001056f  mov     r9d, 2001Fh; samDesired
0x140010575  mov     [rsp+4D0h+phkResult], rax; phkResult
0x14001057a  xor     r8d, r8d; ulOptions
0x14001057d  lea     rdx, szRegDevicesPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x140010584  mov     rcx, rbx; hKey
0x140010587  call    cs:__imp_RegOpenKeyExW
0x14001058d  mov     ebx, eax
0x14001058f  test    eax, eax
0x140010591  jnz     loc_140010728
0x140010597  mov     rcx, [rsp+4D0h+hKey]; hKey
0x14001059c  lea     rax, [rsp+4D0h+var_478]
0x1400105a1  mov     r9d, 2001Fh; samDesired
0x1400105a7  mov     [rsp+4D0h+phkResult], rax; phkResult
0x1400105ac  xor     r8d, r8d; ulOptions
0x1400105af  lea     rdx, szRegWindowsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400105b6  call    cs:__imp_RegOpenKeyExW
0x1400105bc  mov     ebx, eax
0x1400105be  test    eax, eax
0x1400105c0  jnz     loc_140010728
0x1400105c6  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1400105cb  lea     rax, [rsp+4D0h+var_468]
0x1400105d0  mov     esi, 20006h
0x1400105d5  mov     [rsp+4D0h+phkResult], rax; phkResult
0x1400105da  mov     r9d, esi; samDesired
0x1400105dd  lea     rdx, szRegPrinterPortsPath; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400105e4  xor     r8d, r8d; ulOptions
0x1400105e7  call    cs:__imp_RegOpenKeyExW
0x1400105ed  mov     ebx, eax
0x1400105ef  test    eax, eax
0x1400105f1  jnz     loc_140010728
0x1400105f7  cmp     [rbp+3D0h+arg_20], eax
0x1400105fd  jnz     short loc_14001063A
0x1400105ff  mov     rcx, r15; unsigned __int16 *
0x140010602  call    ?CheckBadPortName@@YAPEAGPEAG@Z; CheckBadPortName(ushort *)
0x140010607  mov     rsi, rax
0x14001060a  test    rax, rax
0x14001060d  jnz     short loc_140010620
0x14001060f  mov     rcx, [rsp+4D0h+var_470]; hKey
0x140010614  mov     rdx, rdi; unsigned __int16 *
0x140010617  call    ?GetNetworkIdWorker@@YAKPEAUHKEY__@@PEAG@Z; GetNetworkIdWorker(HKEY__ *,ushort *)
0x14001061c  mov     dword ptr [rsp+4D0h+var_498], eax
0x140010620  lea     r9, [rsp+4D0h+var_498]; unsigned int *
0x140010625  mov     r8, rsi; unsigned __int16 *
0x140010628  mov     rdx, rdi; unsigned __int16 *
0x14001062b  lea     rcx, [rsp+4D0h+var_480]; struct INIT_REG_USER *
0x140010630  call    ?UpdatePrinterInfo@@YAHQEAUINIT_REG_USER@@PEBG1PEAK@Z; UpdatePrinterInfo(INIT_REG_USER * const,ushort const *,ushort const *,ulong *)
0x140010635  jmp     loc_140010728
0x14001063a  mov     rcx, [rsp+4D0h+var_470]; hKey
0x14001063f  mov     rdx, rdi; lpValueName
0x140010642  mov     [rsp+4D0h+var_498], 0
0x14001064b  call    cs:__imp_RegDeleteValueW
0x140010651  mov     rcx, [rsp+4D0h+var_468]; hKey
0x140010656  mov     rdx, rdi; lpValueName
0x140010659  call    cs:__imp_RegDeleteValueW
0x14001065f  mov     rcx, [rsp+4D0h+hKey]; hKey
0x140010664  lea     rax, [rsp+4D0h+var_498]
0x140010669  mov     r9d, esi; samDesired
0x14001066c  mov     [rsp+4D0h+phkResult], rax; phkResult
0x140010671  xor     r8d, r8d; ulOptions
0x140010674  lea     rdx, szDevModes2Path; "Printers\\DevModes2"
0x14001067b  call    cs:__imp_RegOpenKeyExW
0x140010681  test    eax, eax
0x140010683  jnz     short loc_14001069E
0x140010685  mov     rcx, [rsp+4D0h+var_498]; hKey
0x14001068a  mov     rdx, rdi; lpValueName
0x14001068d  call    cs:__imp_RegDeleteValueW
0x140010693  mov     rcx, [rsp+4D0h+var_498]; hKey
0x140010698  call    cs:__imp_RegCloseKey
0x14001069e  mov     [rsp+4D0h+var_490], 0
0x1400106a7  mov     [rsp+4D0h+lpValueName], 0
0x1400106b0  test    rdi, rdi
0x1400106b3  jnz     short loc_1400106C0
0x1400106b5  lea     ecx, [rdi+6]; dwErrCode
0x1400106b8  call    cs:__imp_SetLastError
0x1400106be  jmp     short loc_140010728
0x1400106c0  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1400106c5  lea     r9, [rsp+4D0h+lpValueName]; unsigned __int16 **
0x1400106ca  lea     r8, [rsp+4D0h+var_490]; phkResult
0x1400106cf  mov     rdx, rdi; unsigned __int16 *
0x1400106d2  call    ?bGetDevModeLocation@@YAHPEAUHKEY__@@PEBGPEAPEAU1@PEAPEBG@Z; bGetDevModeLocation(HKEY__ *,ushort const *,HKEY__ * *,ushort const * *)
0x1400106d7  test    eax, eax
0x1400106d9  jz      short loc_140010728
0x1400106db  mov     rdx, [rsp+4D0h+lpValueName]; lpValueName
0x1400106e0  mov     rcx, [rsp+4D0h+var_490]; hKey
0x1400106e5  call    cs:__imp_RegDeleteValueW
0x1400106eb  mov     rcx, [rsp+4D0h+var_490]; hKey
0x1400106f0  mov     edi, eax
0x1400106f2  xor     eax, eax
0x1400106f4  cmp     edi, 2
0x1400106f7  cmovz   edi, eax
0x1400106fa  call    cs:__imp_RegCloseKey
0x140010700  test    edi, edi
0x140010702  jz      short loc_140010728
0x140010704  mov     ecx, edi; dwErrCode
0x140010706  call    cs:__imp_SetLastError
0x14001070c  call    cs:__imp_GetLastError
0x140010712  mov     r8d, eax
0x140010715  lea     rdx, aFailedToSetDev; "Failed to set devmode.  Error %d."
0x14001071c  lea     rcx, aBsetdevmodeper; "bSetDevModePerUser"
0x140010723  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140010728  mov     rcx, [rsp+4D0h+var_470]; hKey
0x14001072d  test    rcx, rcx
0x140010730  jz      short loc_140010738
0x140010732  call    cs:__imp_RegCloseKey
0x140010738  mov     rcx, [rsp+4D0h+var_478]; hKey
0x14001073d  test    rcx, rcx
0x140010740  jz      short loc_140010748
0x140010742  call    cs:__imp_RegCloseKey
0x140010748  mov     rcx, [rsp+4D0h+var_468]; hKey
0x14001074d  test    rcx, rcx
0x140010750  jz      short loc_140010758
0x140010752  call    cs:__imp_RegCloseKey
0x140010758  test    r14, r14
0x14001075b  jz      short loc_140010766
0x14001075d  mov     rcx, r14; hKey
0x140010760  call    cs:__imp_RegCloseKey
0x140010766  mov     eax, ebx
0x140010768  mov     rcx, [rbp+3D0h+var_40]
0x14001076f  xor     rcx, rsp; StackCookie
0x140010772  call    __security_check_cookie
0x140010777  add     rsp, 4A8h
0x14001077e  pop     r15
0x140010780  pop     r14
0x140010782  pop     rdi
0x140010783  pop     rsi
0x140010784  pop     rbx
0x140010785  pop     rbp
0x140010786  retn
```
