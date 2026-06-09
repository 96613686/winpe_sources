# SchdpGetGroupPolicySetting(ulong *)

- ea: `0x1800073ec`
- end: `0x18000754c`
- name: `?SchdpGetGroupPolicySetting@@YAJPEAK@Z`
- size: `352`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007810`

## callees

- `0x1800073ec`
- `0x18000b13c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180007473`
- `ADVAPI32!RegQueryValueExW` at `0x1800074d1`
- `ADVAPI32!RegQueryValueExW` at `0x180007473`
- `ADVAPI32!RegQueryValueExW` at `0x1800074d1`
- `ADVAPI32!RegCloseKey` at `0x180007535`
- `ADVAPI32!RegCloseKey` at `0x180007535`
- `ADVAPI32!RegOpenKeyExW` at `0x180007432`
- `ADVAPI32!RegOpenKeyExW` at `0x180007432`

## string_xrefs

- `0x180007404`: `Software\Policies\Microsoft\Windows\ScheduledDiagnostics`

## pseudocode

```c
__int64 __fastcall SchdpGetGroupPolicySetting(unsigned int *a1)
{
  unsigned int v2; // ebx
  unsigned int v3; // eax
  int v4; // r8d
  BYTE Data[8]; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  int v10; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  v10 = 0;
  Type = 0;
  cbData = 4;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows\\ScheduledDiagnostics",
         0,
         0x20019u,
         &hKey)
    || !hKey
    || (v2 = RegQueryValueExW(hKey, L"EnabledExecution", 0, &Type, Data, &cbData)) != 0 )
  {
    v2 = 0;
  }
  else
  {
    if ( Type == 4 && cbData == 4 )
    {
      if ( !*(_DWORD *)Data )
      {
        v3 = 3;
        v10 = 3;
LABEL_13:
        *a1 = v3;
        goto LABEL_18;
      }
      Type = 0;
      cbData = 4;
      v2 = RegQueryValueExW(hKey, L"EnabledExecutionLevel", 0, &Type, (LPBYTE)&v10, &cbData);
      if ( v2 )
      {
        v3 = 2;
        v10 = 2;
      }
      else
      {
        v3 = v10;
      }
      if ( Type == 4 && cbData == 4 )
        goto LABEL_13;
      v4 = 392;
    }
    else
    {
      v4 = 370;
    }
    v2 = -2147023267;
    SdpDebugTrace(1u, L"SchdpGetGroupPolicySetting", v4, -2147023267);
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800073ec  push    rbp
0x1800073ee  push    rbx
0x1800073ef  push    rdi
0x1800073f0  mov     rbp, rsp
0x1800073f3  sub     rsp, 40h
0x1800073f7  and     [rbp+hKey], 0
0x1800073fc  lea     rax, [rbp+hKey]
0x180007400  and     dword ptr [rbp+Data], 0
0x180007404  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18000740b  and     [rbp+arg_18], 0
0x18000740f  mov     rdi, rcx
0x180007412  and     [rbp+Type], 0
0x180007416  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000741d  mov     r9d, 20019h; samDesired
0x180007423  mov     [rsp+40h+phkResult], rax; phkResult
0x180007428  xor     r8d, r8d; ulOptions
0x18000742b  mov     [rbp+cbData], 4
0x180007432  call    cs:__imp_RegOpenKeyExW
0x180007439  nop     dword ptr [rax+rax+00h]
0x18000743e  test    eax, eax
0x180007440  jnz     loc_18000752A
0x180007446  mov     rcx, [rbp+hKey]; hKey
0x18000744a  test    rcx, rcx
0x18000744d  jz      loc_18000752A
0x180007453  lea     rax, [rbp+cbData]
0x180007457  xor     r8d, r8d; lpReserved
0x18000745a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000745f  lea     r9, [rbp+Type]; lpType
0x180007463  lea     rax, [rbp+Data]
0x180007467  lea     rdx, ValueName; "EnabledExecution"
0x18000746e  mov     [rsp+40h+phkResult], rax; lpData
0x180007473  call    cs:__imp_RegQueryValueExW
0x18000747a  nop     dword ptr [rax+rax+00h]
0x18000747f  mov     ebx, eax
0x180007481  test    eax, eax
0x180007483  jnz     loc_18000752A
0x180007489  cmp     [rbp+Type], 4
0x18000748d  jnz     short loc_180007508
0x18000748f  cmp     [rbp+cbData], 4
0x180007493  jnz     short loc_180007508
0x180007495  cmp     dword ptr [rbp+Data], eax
0x180007498  jnz     short loc_1800074A2
0x18000749a  lea     eax, [rbx+3]
0x18000749d  mov     [rbp+arg_18], eax
0x1800074a0  jmp     short loc_1800074FC
0x1800074a2  mov     rcx, [rbp+hKey]; hKey
0x1800074a6  lea     rax, [rbp+cbData]
0x1800074aa  and     [rbp+Type], 0
0x1800074ae  lea     r9, [rbp+Type]; lpType
0x1800074b2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800074b7  lea     rdx, aEnabledexecuti; "EnabledExecutionLevel"
0x1800074be  lea     rax, [rbp+arg_18]
0x1800074c2  mov     [rbp+cbData], 4
0x1800074c9  xor     r8d, r8d; lpReserved
0x1800074cc  mov     [rsp+40h+phkResult], rax; lpData
0x1800074d1  call    cs:__imp_RegQueryValueExW
0x1800074d8  nop     dword ptr [rax+rax+00h]
0x1800074dd  mov     ebx, eax
0x1800074df  test    eax, eax
0x1800074e1  jz      short loc_1800074ED
0x1800074e3  mov     eax, 2
0x1800074e8  mov     [rbp+arg_18], eax
0x1800074eb  jmp     short loc_1800074F0
0x1800074ed  mov     eax, [rbp+arg_18]
0x1800074f0  cmp     [rbp+Type], 4
0x1800074f4  jnz     short loc_180007500
0x1800074f6  cmp     [rbp+cbData], 4
0x1800074fa  jnz     short loc_180007500
0x1800074fc  mov     [rdi], eax
0x1800074fe  jmp     short loc_18000752C
0x180007500  mov     r8d, 188h
0x180007506  jmp     short loc_18000750E
0x180007508  mov     r8d, 172h; int
0x18000750e  mov     r9d, 8007065Dh; int
0x180007514  lea     rdx, aSchdpgetgroupp; "SchdpGetGroupPolicySetting"
0x18000751b  mov     ecx, 1; Level
0x180007520  mov     ebx, r9d
0x180007523  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180007528  jmp     short loc_18000752C
0x18000752a  xor     ebx, ebx
0x18000752c  mov     rcx, [rbp+hKey]; hKey
0x180007530  test    rcx, rcx
0x180007533  jz      short loc_180007541
0x180007535  call    cs:__imp_RegCloseKey
0x18000753c  nop     dword ptr [rax+rax+00h]
0x180007541  mov     eax, ebx
0x180007543  add     rsp, 40h
0x180007547  pop     rdi
0x180007548  pop     rbx
0x180007549  pop     rbp
0x18000754a  retn
```
