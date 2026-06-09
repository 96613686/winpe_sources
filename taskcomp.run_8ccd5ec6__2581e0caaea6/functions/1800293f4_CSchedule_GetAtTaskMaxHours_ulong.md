# CSchedule::GetAtTaskMaxHours(ulong *)

- ea: `0x1800293f4`
- end: `0x180029559`
- name: `?GetAtTaskMaxHours@CSchedule@@AEAAJPEAK@Z`
- size: `357`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180028a3c`

## callees

- `0x1800293f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800294a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029538`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800294a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029538`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002948a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002948a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029433`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029433`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002950d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002950d`

## string_xrefs

- `0x18002941d`: `System\CurrentControlSet\Services\Schedule`
- `0x180029463`: `AtTaskMaxHours`
- `0x1800294f8`: `AtTaskMaxHours`

## pseudocode

```c
LSTATUS __fastcall CSchedule::GetAtTaskMaxHours(CSchedule *this, unsigned int *a2)
{
  LSTATUS result; // eax
  char v4; // di
  LSTATUS v5; // eax
  LSTATUS v6; // ebx
  unsigned int v7; // eax
  int v8; // eax
  CSchedule *Data; // [rsp+50h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Data = this;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Schedule", 0, 0x2001Fu, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  LODWORD(Data) = 0;
  cbData = 4;
  v4 = 0;
  v5 = RegQueryValueExW(hKey, L"AtTaskMaxHours", 0, 0, (LPBYTE)&Data, &cbData);
  v6 = v5;
  if ( !v5 )
  {
    v7 = (unsigned int)Data;
LABEL_11:
    if ( v7 <= 0x3E7 )
    {
      if ( !v4 )
        goto LABEL_16;
    }
    else
    {
      LODWORD(Data) = 999;
    }
    v6 = RegSetValueExW(hKey, L"AtTaskMaxHours", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v6 )
      goto LABEL_6;
    v7 = (unsigned int)Data;
LABEL_16:
    if ( v7 )
      v8 = 3600000 * v7;
    else
      v8 = -1;
    LODWORD(Data) = v8;
    RegCloseKey(hKey);
    *a2 = (unsigned int)Data;
    return 0;
  }
  if ( v5 == 2 )
  {
    v7 = 72;
    v4 = 1;
    LODWORD(Data) = 72;
    goto LABEL_11;
  }
LABEL_6:
  RegCloseKey(hKey);
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x1800293f4  mov     [rsp-18h+arg_8], rbx
0x1800293f9  mov     [rsp-18h+Data], rcx
0x1800293fe  push    rbp
0x1800293ff  push    rsi
0x180029400  push    rdi
0x180029401  mov     rbp, rsp
0x180029404  sub     rsp, 30h
0x180029408  mov     rsi, rdx
0x18002940b  mov     [rbp+hKey], 0
0x180029413  lea     rax, [rbp+hKey]
0x180029417  mov     r9d, 2001Fh; samDesired
0x18002941d  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x180029424  mov     [rsp+30h+phkResult], rax; phkResult
0x180029429  xor     r8d, r8d; ulOptions
0x18002942c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029433  call    cs:__imp_RegOpenKeyExW
0x18002943a  nop     dword ptr [rax+rax+00h]
0x18002943f  test    eax, eax
0x180029441  jz      short loc_180029456
0x180029443  jle     loc_18002954B
0x180029449  movzx   eax, ax
0x18002944c  or      eax, 80070000h
0x180029451  jmp     loc_18002954B
0x180029456  mov     rcx, [rbp+hKey]; hKey
0x18002945a  lea     rax, [rbp+cbData]
0x18002945e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180029463  lea     rdx, aAttaskmaxhours; "AtTaskMaxHours"
0x18002946a  lea     rax, [rbp+Data]
0x18002946e  mov     dword ptr [rbp+Data], 0
0x180029475  xor     r9d, r9d; lpType
0x180029478  mov     [rsp+30h+phkResult], rax; lpData
0x18002947d  xor     r8d, r8d; lpReserved
0x180029480  mov     [rbp+cbData], 4
0x180029487  xor     dil, dil
0x18002948a  call    cs:__imp_RegQueryValueExW
0x180029491  nop     dword ptr [rax+rax+00h]
0x180029496  mov     ebx, eax
0x180029498  test    eax, eax
0x18002949a  jz      short loc_1800294D2
0x18002949c  cmp     eax, 2
0x18002949f  jz      short loc_1800294C5
0x1800294a1  mov     rcx, [rbp+hKey]; hKey
0x1800294a5  call    cs:__imp_RegCloseKey
0x1800294ac  nop     dword ptr [rax+rax+00h]
0x1800294b1  test    ebx, ebx
0x1800294b3  jle     short loc_1800294BE
0x1800294b5  movzx   ebx, bx
0x1800294b8  or      ebx, 80070000h
0x1800294be  mov     eax, ebx
0x1800294c0  jmp     loc_18002954B
0x1800294c5  mov     eax, 48h ; 'H'
0x1800294ca  mov     dil, 1
0x1800294cd  mov     dword ptr [rbp+Data], eax
0x1800294d0  jmp     short loc_1800294D5
0x1800294d2  mov     eax, dword ptr [rbp+Data]
0x1800294d5  mov     ecx, 3E7h
0x1800294da  cmp     eax, ecx
0x1800294dc  jbe     short loc_1800294E3
0x1800294de  mov     dword ptr [rbp+Data], ecx
0x1800294e1  jmp     short loc_1800294E8
0x1800294e3  test    dil, dil
0x1800294e6  jz      short loc_180029522
0x1800294e8  mov     rcx, [rbp+hKey]; hKey
0x1800294ec  lea     rax, [rbp+Data]
0x1800294f0  mov     dword ptr [rsp+30h+lpcbData], 4; cbData
0x1800294f8  lea     rdx, aAttaskmaxhours; "AtTaskMaxHours"
0x1800294ff  mov     r9d, 4; dwType
0x180029505  mov     [rsp+30h+phkResult], rax; lpData
0x18002950a  xor     r8d, r8d; Reserved
0x18002950d  call    cs:__imp_RegSetValueExW
0x180029514  nop     dword ptr [rax+rax+00h]
0x180029519  mov     ebx, eax
0x18002951b  test    eax, eax
0x18002951d  jnz     short loc_1800294A1
0x18002951f  mov     eax, dword ptr [rbp+Data]
0x180029522  test    eax, eax
0x180029524  jnz     short loc_18002952B
0x180029526  or      eax, 0FFFFFFFFh
0x180029529  jmp     short loc_180029531
0x18002952b  imul    eax, 36EE80h
0x180029531  mov     rcx, [rbp+hKey]; hKey
0x180029535  mov     dword ptr [rbp+Data], eax
0x180029538  call    cs:__imp_RegCloseKey
0x18002953f  nop     dword ptr [rax+rax+00h]
0x180029544  mov     eax, dword ptr [rbp+Data]
0x180029547  mov     [rsi], eax
0x180029549  xor     eax, eax
0x18002954b  mov     rbx, [rsp+30h+arg_8]
0x180029550  add     rsp, 30h
0x180029554  pop     rdi
0x180029555  pop     rsi
0x180029556  pop     rbp
0x180029557  retn
```
