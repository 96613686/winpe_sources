# IsMSFTInternal(int,int *)

- ea: `0x180015de8`
- end: `0x180015fa0`
- name: `?IsMSFTInternal@@YAJHPEAH@Z`
- size: `440`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015ae8`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180015de8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015ed7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015ed7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015e99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015f2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015e99`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015f2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015e52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015efe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015e52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015efe`

## pseudocode

```c
__int64 __fastcall IsMSFTInternal(__int64 a1, int *a2)
{
  signed int v3; // ebx
  int v5; // ebx
  LSTATUS v6; // eax
  bool v7; // sf
  HKEY v8; // rcx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  cbData = 4;
  Data = 0;
  Type = 0;
  hKey[0] = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    goto LABEL_3;
  }
  *a2 = 0;
  v5 = (_DWORD)a1 != 0 ? 0x100 : 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\SQMClient", 0, v5 + 131097, hKey);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  v8 = hKey[0];
  if ( v7 )
  {
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\SQMClient", 0, v5 + 131097, hKey);
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 < 0 )
      goto LABEL_21;
    v8 = hKey[0];
  }
  v9 = RegQueryValueExW(v8, L"MSFTInternal", 0, &Type, (LPBYTE)&Data, &cbData);
  v3 = v9;
  if ( v9 > 0 )
    v3 = (unsigned __int16)v9 | 0x80070000;
  if ( v3 >= 0 )
  {
    *a2 = Data != 0;
    goto LABEL_22;
  }
LABEL_21:
  if ( v3 == -2147024809 )
  {
LABEL_3:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        a1,
        (_DWORD)a2,
        (unsigned int)"IsMSFTInternal",
        -2147024809,
        (__int64)"IsInternal");
    goto LABEL_5;
  }
LABEL_22:
  if ( v3 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(a1, a2, "IsMSFTInternal", (unsigned int)v3);
    v3 = 0;
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
  {
    McTemplateU0s_EventWriteTransfer(a1, SDIAGPRV_EVENT_DEBUG_SUCCESS, "IsMSFTInternal");
  }
LABEL_5:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180015de8  mov     [rsp-18h+arg_0], rbx
0x180015ded  push    rbp
0x180015dee  push    rdi
0x180015def  push    r14
0x180015df1  mov     rbp, rsp
0x180015df4  sub     rsp, 40h
0x180015df8  mov     [rbp+cbData], 4
0x180015dff  mov     rdi, rdx
0x180015e02  mov     [rbp+Data], 0
0x180015e09  mov     [rbp+Type], 0
0x180015e10  mov     [rbp+hKey], 0
0x180015e18  test    rdx, rdx
0x180015e1b  jnz     short loc_180015E68
0x180015e1d  mov     ebx, 80070057h
0x180015e22  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015e29  jz      short loc_180015E49
0x180015e2b  lea     rax, aIsinternal; "IsInternal"
0x180015e32  mov     r9d, 80070057h
0x180015e38  lea     r8, aIsmsftinternal; "IsMSFTInternal"
0x180015e3f  mov     [rsp+40h+phkResult], rax
0x180015e44  call    McTemplateU0sqs_EventWriteTransfer
0x180015e49  mov     rcx, [rbp+hKey]; hKey
0x180015e4d  test    rcx, rcx
0x180015e50  jz      short loc_180015E58
0x180015e52  call    cs:__imp_RegCloseKey
0x180015e58  mov     eax, ebx
0x180015e5a  mov     rbx, [rsp+40h+arg_0]
0x180015e5f  add     rsp, 40h
0x180015e63  pop     r14
0x180015e65  pop     rdi
0x180015e66  pop     rbp
0x180015e67  retn
0x180015e68  neg     ecx
0x180015e6a  mov     dword ptr [rdx], 0
0x180015e70  lea     rax, [rbp+hKey]
0x180015e74  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015e7b  sbb     ebx, ebx
0x180015e7d  mov     [rsp+40h+phkResult], rax; phkResult
0x180015e82  and     ebx, 100h
0x180015e88  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\SQMClien"...
0x180015e8f  xor     r8d, r8d; ulOptions
0x180015e92  lea     r9d, [rbx+20019h]; samDesired
0x180015e99  call    cs:__imp_RegOpenKeyExW
0x180015e9f  mov     r14d, 80070000h
0x180015ea5  test    eax, eax
0x180015ea7  jle     short loc_180015EB1
0x180015ea9  movzx   eax, ax
0x180015eac  or      eax, r14d
0x180015eaf  test    eax, eax
0x180015eb1  mov     rcx, [rbp+hKey]; hKey
0x180015eb5  js      short loc_180015EF9
0x180015eb7  lea     rax, [rbp+cbData]
0x180015ebb  xor     r8d, r8d; lpReserved
0x180015ebe  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180015ec3  lea     r9, [rbp+Type]; lpType
0x180015ec7  lea     rax, [rbp+Data]
0x180015ecb  lea     rdx, aMsftinternal; "MSFTInternal"
0x180015ed2  mov     [rsp+40h+phkResult], rax; lpData
0x180015ed7  call    cs:__imp_RegQueryValueExW
0x180015edd  mov     ebx, eax
0x180015edf  test    eax, eax
0x180015ee1  jle     short loc_180015EE9
0x180015ee3  movzx   ebx, ax
0x180015ee6  or      ebx, r14d
0x180015ee9  test    ebx, ebx
0x180015eeb  js      short loc_180015F4C
0x180015eed  xor     eax, eax
0x180015eef  cmp     [rbp+Data], eax
0x180015ef2  setnz   al
0x180015ef5  mov     [rdi], eax
0x180015ef7  jmp     short loc_180015F58
0x180015ef9  test    rcx, rcx
0x180015efc  jz      short loc_180015F0C
0x180015efe  call    cs:__imp_RegCloseKey
0x180015f04  mov     [rbp+hKey], 0
0x180015f0c  lea     rax, [rbp+hKey]
0x180015f10  xor     r8d, r8d; ulOptions
0x180015f13  lea     r9d, [rbx+20019h]; samDesired
0x180015f1a  mov     [rsp+40h+phkResult], rax; phkResult
0x180015f1f  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\SQMClient"
0x180015f26  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015f2d  call    cs:__imp_RegOpenKeyExW
0x180015f33  mov     ebx, eax
0x180015f35  test    eax, eax
0x180015f37  jle     short loc_180015F3F
0x180015f39  movzx   ebx, ax
0x180015f3c  or      ebx, r14d
0x180015f3f  test    ebx, ebx
0x180015f41  js      short loc_180015F4C
0x180015f43  mov     rcx, [rbp+hKey]
0x180015f47  jmp     loc_180015EB7
0x180015f4c  cmp     ebx, 80070057h
0x180015f52  jz      loc_180015E22
0x180015f58  test    ebx, ebx
0x180015f5a  jz      short loc_180015F7B
0x180015f5c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180015f63  jz      short loc_180015F74
0x180015f65  mov     r9d, ebx
0x180015f68  lea     r8, aIsmsftinternal; "IsMSFTInternal"
0x180015f6f  call    McTemplateU0sq_EventWriteTransfer
0x180015f74  xor     ebx, ebx
0x180015f76  jmp     loc_180015E49
0x180015f7b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180015f82  jz      loc_180015E49
0x180015f88  lea     r8, aIsmsftinternal; "IsMSFTInternal"
0x180015f8f  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180015f96  call    McTemplateU0s_EventWriteTransfer
0x180015f9b  jmp     loc_180015E49
```
