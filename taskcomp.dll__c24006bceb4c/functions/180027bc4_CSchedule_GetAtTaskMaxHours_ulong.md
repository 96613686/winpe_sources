# CSchedule::GetAtTaskMaxHours(ulong *)

- ea: `0x180027bc4`
- end: `0x180027d07`
- name: `?GetAtTaskMaxHours@CSchedule@@AEAAJPEAK@Z`
- size: `323`
- prototype: `LSTATUS __fastcall(CSchedule *this, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180027228`

## callees

- `0x180027bc4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027c69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027ced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027c69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027ced`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027c54`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027c54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027c03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027cc8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180027cc8`

## string_xrefs

- `0x180027bed`: `System\CurrentControlSet\Services\Schedule`
- `0x180027c2d`: `AtTaskMaxHours`
- `0x180027cb3`: `AtTaskMaxHours`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180027bc4  mov     [rsp-18h+arg_8], rbx
0x180027bc9  mov     [rsp-18h+Data], rcx
0x180027bce  push    rbp
0x180027bcf  push    rsi
0x180027bd0  push    rdi
0x180027bd1  mov     rbp, rsp
0x180027bd4  sub     rsp, 30h
0x180027bd8  mov     rsi, rdx
0x180027bdb  mov     [rbp+hKey], 0
0x180027be3  lea     rax, [rbp+hKey]
0x180027be7  mov     r9d, 2001Fh; samDesired
0x180027bed  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Sc"...
0x180027bf4  mov     [rsp+30h+phkResult], rax; phkResult
0x180027bf9  xor     r8d, r8d; ulOptions
0x180027bfc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027c03  call    cs:__imp_RegOpenKeyExW
0x180027c09  test    eax, eax
0x180027c0b  jz      short loc_180027C20
0x180027c0d  jle     loc_180027CFA
0x180027c13  movzx   eax, ax
0x180027c16  or      eax, 80070000h
0x180027c1b  jmp     loc_180027CFA
0x180027c20  mov     rcx, [rbp+hKey]; hKey
0x180027c24  lea     rax, [rbp+cbData]
0x180027c28  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180027c2d  lea     rdx, aAttaskmaxhours; "AtTaskMaxHours"
0x180027c34  lea     rax, [rbp+Data]
0x180027c38  mov     dword ptr [rbp+Data], 0
0x180027c3f  xor     r9d, r9d; lpType
0x180027c42  mov     [rsp+30h+phkResult], rax; lpData
0x180027c47  xor     r8d, r8d; lpReserved
0x180027c4a  mov     [rbp+cbData], 4
0x180027c51  xor     dil, dil
0x180027c54  call    cs:__imp_RegQueryValueExW
0x180027c5a  mov     ebx, eax
0x180027c5c  test    eax, eax
0x180027c5e  jz      short loc_180027C8D
0x180027c60  cmp     eax, 2
0x180027c63  jz      short loc_180027C80
0x180027c65  mov     rcx, [rbp+hKey]; hKey
0x180027c69  call    cs:__imp_RegCloseKey
0x180027c6f  test    ebx, ebx
0x180027c71  jle     short loc_180027C7C
0x180027c73  movzx   ebx, bx
0x180027c76  or      ebx, 80070000h
0x180027c7c  mov     eax, ebx
0x180027c7e  jmp     short loc_180027CFA
0x180027c80  mov     eax, 48h ; 'H'
0x180027c85  mov     dil, 1
0x180027c88  mov     dword ptr [rbp+Data], eax
0x180027c8b  jmp     short loc_180027C90
0x180027c8d  mov     eax, dword ptr [rbp+Data]
0x180027c90  mov     ecx, 3E7h
0x180027c95  cmp     eax, ecx
0x180027c97  jbe     short loc_180027C9E
0x180027c99  mov     dword ptr [rbp+Data], ecx
0x180027c9c  jmp     short loc_180027CA3
0x180027c9e  test    dil, dil
0x180027ca1  jz      short loc_180027CD7
0x180027ca3  mov     rcx, [rbp+hKey]; hKey
0x180027ca7  lea     rax, [rbp+Data]
0x180027cab  mov     dword ptr [rsp+30h+lpcbData], 4; cbData
0x180027cb3  lea     rdx, aAttaskmaxhours; "AtTaskMaxHours"
0x180027cba  mov     r9d, 4; dwType
0x180027cc0  mov     [rsp+30h+phkResult], rax; lpData
0x180027cc5  xor     r8d, r8d; Reserved
0x180027cc8  call    cs:__imp_RegSetValueExW
0x180027cce  mov     ebx, eax
0x180027cd0  test    eax, eax
0x180027cd2  jnz     short loc_180027C65
0x180027cd4  mov     eax, dword ptr [rbp+Data]
0x180027cd7  test    eax, eax
0x180027cd9  jnz     short loc_180027CE0
0x180027cdb  or      eax, 0FFFFFFFFh
0x180027cde  jmp     short loc_180027CE6
0x180027ce0  imul    eax, 36EE80h
0x180027ce6  mov     rcx, [rbp+hKey]; hKey
0x180027cea  mov     dword ptr [rbp+Data], eax
0x180027ced  call    cs:__imp_RegCloseKey
0x180027cf3  mov     eax, dword ptr [rbp+Data]
0x180027cf6  mov     [rsi], eax
0x180027cf8  xor     eax, eax
0x180027cfa  mov     rbx, [rsp+30h+arg_8]
0x180027cff  add     rsp, 30h
0x180027d03  pop     rdi
0x180027d04  pop     rsi
0x180027d05  pop     rbp
0x180027d06  retn
```
