# UtilIsFeatureUpdatePendingReboot(ulong *)

- ea: `0x18003dc48`
- end: `0x18003ddbb`
- name: `?UtilIsFeatureUpdatePendingReboot@@YAJPEAK@Z`
- size: `371`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180017a18`

## callees

- `0x18003dc48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003dcd3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003dd6f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003dcd3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003dd6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dcfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dd97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dcfb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003dd97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dc96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dd37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dc96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003dd37`

## pseudocode

```c
__int64 __fastcall UtilIsFeatureUpdatePendingReboot(unsigned int *a1)
{
  LSTATUS v2; // eax
  bool v3; // sf
  bool v4; // cc
  LSTATUS ValueW; // eax
  int v6; // edi
  LSTATUS v7; // eax
  bool v8; // sf
  bool v9; // cc
  LSTATUS v10; // eax
  int v11; // ebx
  int pvData; // [rsp+60h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp+28h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+30h] BYREF

  *a1 = 0;
  pvData = 0;
  pcbData = 4;
  hkey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\MoSetup\\Volatile", 0, 0x101u, &hkey);
  v3 = v2 < 0;
  v4 = v2 <= 0;
  if ( !v2 )
  {
    ValueW = RegGetValueW(hkey, 0, L"SetupPhase", 0x10u, 0, &pvData, &pcbData);
    v3 = ValueW < 0;
    v4 = ValueW <= 0;
    if ( !ValueW )
      goto LABEL_7;
  }
  if ( !v4 )
    v3 = 1;
  if ( v3 )
  {
    v6 = 0;
    pvData = 0;
  }
  else
  {
LABEL_7:
    v6 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  pvData = 0;
  pcbData = 4;
  hkey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\MoSetup\\Volatile", 0, 0x101u, &hkey);
  v8 = v7 < 0;
  v9 = v7 <= 0;
  if ( !v7 )
  {
    v10 = RegGetValueW(hkey, 0, L"SetupHostResult", 0x10u, 0, &pvData, &pcbData);
    v8 = v10 < 0;
    v9 = v10 <= 0;
    if ( !v10 )
      goto LABEL_16;
  }
  if ( !v9 )
    v8 = 1;
  if ( v8 )
  {
    v11 = 0;
    pvData = 0;
  }
  else
  {
LABEL_16:
    v11 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  if ( !v11 && v6 == 6 )
    *a1 = 1;
  return 0;
}

```

## disassembly

```asm
0x18003dc48  mov     [rsp-18h+arg_18], rbx
0x18003dc4d  push    rbp
0x18003dc4e  push    rsi
0x18003dc4f  push    rdi
0x18003dc50  mov     rbp, rsp
0x18003dc53  sub     rsp, 40h
0x18003dc57  mov     rsi, rcx
0x18003dc5a  mov     dword ptr [rcx], 0
0x18003dc60  lea     rax, [rbp+hkey]
0x18003dc64  mov     [rbp+arg_0], 0
0x18003dc6b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003dc72  mov     [rsp+40h+phkResult], rax; phkResult
0x18003dc77  mov     r9d, 101h; samDesired
0x18003dc7d  mov     [rbp+arg_8], 4
0x18003dc84  xor     r8d, r8d; ulOptions
0x18003dc87  mov     [rbp+hkey], 0
0x18003dc8f  lea     rdx, aSystemSetupMos; "SYSTEM\\Setup\\MoSetup\\Volatile"
0x18003dc96  call    cs:__imp_RegOpenKeyExW
0x18003dc9c  mov     ebx, 80070000h
0x18003dca1  test    eax, eax
0x18003dca3  jnz     short loc_18003DCDD
0x18003dca5  mov     rcx, [rbp+hkey]; hkey
0x18003dca9  lea     rax, [rbp+arg_8]
0x18003dcad  mov     [rsp+40h+pcbData], rax; pcbData
0x18003dcb2  lea     r8, aSetupphase; "SetupPhase"
0x18003dcb9  lea     rax, [rbp+arg_0]
0x18003dcbd  mov     r9d, 10h; dwFlags
0x18003dcc3  mov     [rsp+40h+pvData], rax; pvData
0x18003dcc8  xor     edx, edx; lpSubKey
0x18003dcca  mov     [rsp+40h+phkResult], 0; pdwType
0x18003dcd3  call    cs:__imp_RegGetValueW
0x18003dcd9  test    eax, eax
0x18003dcdb  jz      short loc_18003DCEF
0x18003dcdd  jle     short loc_18003DCE6
0x18003dcdf  movzx   eax, ax
0x18003dce2  or      eax, ebx
0x18003dce4  test    eax, eax
0x18003dce6  jns     short loc_18003DCEF
0x18003dce8  xor     edi, edi
0x18003dcea  mov     [rbp+arg_0], edi
0x18003dced  jmp     short loc_18003DCF2
0x18003dcef  mov     edi, [rbp+arg_0]
0x18003dcf2  mov     rcx, [rbp+hkey]; hKey
0x18003dcf6  test    rcx, rcx
0x18003dcf9  jz      short loc_18003DD01
0x18003dcfb  call    cs:__imp_RegCloseKey
0x18003dd01  lea     rax, [rbp+hkey]
0x18003dd05  mov     [rbp+arg_0], 0
0x18003dd0c  mov     r9d, 101h; samDesired
0x18003dd12  mov     [rsp+40h+phkResult], rax; phkResult
0x18003dd17  xor     r8d, r8d; ulOptions
0x18003dd1a  mov     [rbp+arg_8], 4
0x18003dd21  lea     rdx, aSystemSetupMos; "SYSTEM\\Setup\\MoSetup\\Volatile"
0x18003dd28  mov     [rbp+hkey], 0
0x18003dd30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003dd37  call    cs:__imp_RegOpenKeyExW
0x18003dd3d  test    eax, eax
0x18003dd3f  jnz     short loc_18003DD79
0x18003dd41  mov     rcx, [rbp+hkey]; hkey
0x18003dd45  lea     rax, [rbp+arg_8]
0x18003dd49  mov     [rsp+40h+pcbData], rax; pcbData
0x18003dd4e  lea     r8, aSetuphostresul; "SetupHostResult"
0x18003dd55  lea     rax, [rbp+arg_0]
0x18003dd59  mov     r9d, 10h; dwFlags
0x18003dd5f  mov     [rsp+40h+pvData], rax; pvData
0x18003dd64  xor     edx, edx; lpSubKey
0x18003dd66  mov     [rsp+40h+phkResult], 0; pdwType
0x18003dd6f  call    cs:__imp_RegGetValueW
0x18003dd75  test    eax, eax
0x18003dd77  jz      short loc_18003DD8B
0x18003dd79  jle     short loc_18003DD82
0x18003dd7b  movzx   eax, ax
0x18003dd7e  or      eax, ebx
0x18003dd80  test    eax, eax
0x18003dd82  jns     short loc_18003DD8B
0x18003dd84  xor     ebx, ebx
0x18003dd86  mov     [rbp+arg_0], ebx
0x18003dd89  jmp     short loc_18003DD8E
0x18003dd8b  mov     ebx, [rbp+arg_0]
0x18003dd8e  mov     rcx, [rbp+hkey]; hKey
0x18003dd92  test    rcx, rcx
0x18003dd95  jz      short loc_18003DD9D
0x18003dd97  call    cs:__imp_RegCloseKey
0x18003dd9d  test    ebx, ebx
0x18003dd9f  jnz     short loc_18003DDAC
0x18003dda1  cmp     edi, 6
0x18003dda4  jnz     short loc_18003DDAC
0x18003dda6  mov     dword ptr [rsi], 1
0x18003ddac  mov     rbx, [rsp+40h+arg_18]
0x18003ddb1  xor     eax, eax
0x18003ddb3  add     rsp, 40h
0x18003ddb7  pop     rdi
0x18003ddb8  pop     rsi
0x18003ddb9  pop     rbp
0x18003ddba  retn
```
