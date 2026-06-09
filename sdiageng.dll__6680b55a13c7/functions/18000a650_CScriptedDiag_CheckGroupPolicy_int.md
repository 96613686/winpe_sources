# CScriptedDiag::CheckGroupPolicy(int *)

- ea: `0x18000a650`
- end: `0x18000a72a`
- name: `?CheckGroupPolicy@CScriptedDiag@@AEAAJPEAH@Z`
- size: `218`
- prototype: `__int64 __fastcall(CScriptedDiag *__hidden this, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cf00`

## callees

- `0x18000a650`
- `0x180026fa0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000a6c6`
- `ADVAPI32!RegOpenKeyExW` at `0x18000a6c6`
- `ADVAPI32!RegCloseKey` at `0x18000a717`
- `ADVAPI32!RegCloseKey` at `0x18000a717`
- `ADVAPI32!RegQueryValueExW` at `0x18000a6fb`
- `ADVAPI32!RegQueryValueExW` at `0x18000a6fb`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::CheckGroupPolicy(CScriptedDiag *this, int *a2)
{
  unsigned int v3; // edi
  int Data; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+44h] [rbp+Ch]
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v6 = HIDWORD(this);
  hKey = 0;
  Data = 0;
  cbData = 4;
  if ( a2 )
  {
    *a2 = 1;
    v3 = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\ScriptedDiagnostics",
            0,
            0x20019u,
            &hKey) )
    {
      if ( !hKey )
        return v3;
      if ( !RegQueryValueExW(hKey, L"EnableDiagnostics", 0, 0, (LPBYTE)&Data, &cbData) && !Data )
        *a2 = 0;
    }
  }
  else
  {
    v3 = -2147024809;
    SdpDebugTrace(1u, L"CScriptedDiag::CheckGroupPolicy", 2945, -2147024809);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18000a650  mov     rax, rsp
0x18000a653  mov     [rax+20h], rbx
0x18000a657  mov     [rax+8], rcx
0x18000a65b  push    rdi
0x18000a65c  sub     rsp, 30h
0x18000a660  mov     qword ptr [rax+18h], 0
0x18000a668  mov     rbx, rdx
0x18000a66b  mov     dword ptr [rax+8], 0
0x18000a672  mov     dword ptr [rax+10h], 4
0x18000a679  test    rdx, rdx
0x18000a67c  jnz     short loc_18000A69D
0x18000a67e  mov     edi, 80070057h
0x18000a683  lea     rdx, aCscripteddiagC; "CScriptedDiag::CheckGroupPolicy"
0x18000a68a  mov     r9d, edi; int
0x18000a68d  lea     ecx, [rbx+1]; Level
0x18000a690  mov     r8d, 0B81h; int
0x18000a696  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000a69b  jmp     short loc_18000A70D
0x18000a69d  mov     dword ptr [rdx], 1
0x18000a6a3  lea     rax, [rsp+38h+hKey]
0x18000a6a8  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x18000a6af  mov     [rsp+38h+phkResult], rax; phkResult
0x18000a6b4  mov     r9d, 20019h; samDesired
0x18000a6ba  xor     r8d, r8d; ulOptions
0x18000a6bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a6c4  xor     edi, edi
0x18000a6c6  call    cs:__imp_RegOpenKeyExW
0x18000a6cc  test    eax, eax
0x18000a6ce  jnz     short loc_18000A70D
0x18000a6d0  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a6d5  test    rcx, rcx
0x18000a6d8  jz      short loc_18000A71D
0x18000a6da  lea     rax, [rsp+38h+cbData]
0x18000a6df  xor     r9d, r9d; lpType
0x18000a6e2  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000a6e7  lea     rdx, aEnablediagnost; "EnableDiagnostics"
0x18000a6ee  lea     rax, [rsp+38h+Data]
0x18000a6f3  xor     r8d, r8d; lpReserved
0x18000a6f6  mov     [rsp+38h+phkResult], rax; lpData
0x18000a6fb  call    cs:__imp_RegQueryValueExW
0x18000a701  test    eax, eax
0x18000a703  jnz     short loc_18000A70D
0x18000a705  cmp     [rsp+38h+Data], edi
0x18000a709  ja      short loc_18000A70D
0x18000a70b  mov     [rbx], edi
0x18000a70d  mov     rcx, [rsp+38h+hKey]; hKey
0x18000a712  test    rcx, rcx
0x18000a715  jz      short loc_18000A71D
0x18000a717  call    cs:__imp_RegCloseKey
0x18000a71d  mov     rbx, [rsp+38h+arg_18]
0x18000a722  mov     eax, edi
0x18000a724  add     rsp, 30h
0x18000a728  pop     rdi
0x18000a729  retn
```
