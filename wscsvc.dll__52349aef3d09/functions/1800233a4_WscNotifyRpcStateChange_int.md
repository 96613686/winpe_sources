# WscNotifyRpcStateChange(int)

- ea: `0x1800233a4`
- end: `0x1800235f9`
- name: `?WscNotifyRpcStateChange@@YAXH@Z`
- size: `597`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cb1c`
- `0x18001d9e0`

## callees

- `0x180008e48`
- `0x1800233a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002352e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002352e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800233f9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800233f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800235ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800235ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023439`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023439`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023490`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800234e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023586`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023490`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800234e8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023586`

## string_xrefs

- `0x1800233c2`: `SOFTWARE\Microsoft\Security Center`

## pseudocode

```c
void __fastcall WscNotifyRpcStateChange(int a1)
{
  unsigned int v2; // eax
  CThirdPartyManager *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  BOOL Data; // [rsp+88h] [rbp+28h] BYREF
  DWORD Type; // [rsp+90h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF

  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Security Center", 0, 0, 1u, 0x20007u, 0, &hKey, 0);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_29;
    }
    v4 = 20;
    goto LABEL_28;
  }
  Data = 0;
  Type = 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"cval", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
  {
    Data = a1 != 0;
    v2 = RegSetValueExW(hKey, L"cval", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v2 )
      goto LABEL_29;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_29;
    }
    v4 = 19;
    goto LABEL_28;
  }
  if ( a1 )
  {
    if ( !Data )
    {
      Data = 1;
      goto LABEL_9;
    }
  }
  else if ( Data )
  {
    Data = 0;
LABEL_9:
    v2 = RegSetValueExW(hKey, L"cval", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v2 )
      goto LABEL_29;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_29;
    }
    v4 = 18;
    goto LABEL_28;
  }
  v5 = RegSetValueExW(hKey, L"cval2", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v5
    && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v5);
  }
  v2 = RegDeleteValueW(hKey, L"cval2");
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 17;
LABEL_28:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, v2);
    }
  }
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800233a4  push    rbp
0x1800233a6  push    rbx
0x1800233a7  push    r14
0x1800233a9  mov     rbp, rsp
0x1800233ac  sub     rsp, 60h
0x1800233b0  mov     [rsp+60h+lpdwDisposition], 0; lpdwDisposition
0x1800233b9  lea     rax, [rbp+hKey]
0x1800233bd  mov     [rsp+60h+phkResult], rax; phkResult
0x1800233c2  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\Security Center"
0x1800233c9  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800233d2  mov     ebx, ecx
0x1800233d4  mov     [rsp+60h+samDesired], 20007h; samDesired
0x1800233dc  xor     r9d, r9d; lpClass
0x1800233df  xor     r8d, r8d; Reserved
0x1800233e2  mov     [rsp+60h+dwOptions], 1; dwOptions
0x1800233ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800233f1  mov     [rbp+hKey], 0
0x1800233f9  call    cs:__imp_RegCreateKeyExW
0x1800233ff  test    eax, eax
0x180023401  jnz     loc_1800235B0
0x180023407  mov     rcx, [rbp+hKey]; hKey
0x18002340b  lea     r14d, [rax+4]
0x18002340f  mov     [rbp+Data], eax
0x180023412  lea     r9, [rbp+Type]; lpType
0x180023416  mov     [rbp+Type], eax
0x180023419  lea     rdx, aCval; "cval"
0x180023420  lea     rax, [rbp+cbData]
0x180023424  mov     [rbp+cbData], r14d
0x180023428  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x18002342d  xor     r8d, r8d; lpReserved
0x180023430  lea     rax, [rbp+Data]
0x180023434  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180023439  call    cs:__imp_RegQueryValueExW
0x18002343f  test    eax, eax
0x180023441  jnz     loc_18002355D
0x180023447  cmp     [rbp+Type], r14d
0x18002344b  jnz     loc_18002355D
0x180023451  test    ebx, ebx
0x180023453  jz      short loc_180023464
0x180023455  cmp     [rbp+Data], 1
0x180023459  jz      short loc_1800234C9
0x18002345b  mov     [rbp+Data], 1
0x180023462  jmp     short loc_180023471
0x180023464  cmp     [rbp+Data], 0
0x180023468  jz      short loc_1800234C9
0x18002346a  mov     [rbp+Data], 0
0x180023471  mov     rcx, [rbp+hKey]; hKey
0x180023475  lea     rax, [rbp+Data]
0x180023479  mov     [rsp+60h+samDesired], r14d; cbData
0x18002347e  lea     rdx, aCval; "cval"
0x180023485  mov     r9d, r14d; dwType
0x180023488  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18002348d  xor     r8d, r8d; Reserved
0x180023490  call    cs:__imp_RegSetValueExW
0x180023496  test    eax, eax
0x180023498  jz      loc_1800235E1
0x18002349e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234a5  lea     rbx, WPP_GLOBAL_Control
0x1800234ac  cmp     rcx, rbx
0x1800234af  jz      loc_1800235E1
0x1800234b5  test    byte ptr [rcx+1Ch], 1
0x1800234b9  jz      loc_1800235E1
0x1800234bf  mov     edx, 12h
0x1800234c4  jmp     loc_1800235CE
0x1800234c9  mov     rcx, [rbp+hKey]; hKey
0x1800234cd  lea     rax, [rbp+Data]
0x1800234d1  mov     [rsp+60h+samDesired], r14d; cbData
0x1800234d6  lea     rdx, aCval2; "cval2"
0x1800234dd  mov     r9d, r14d; dwType
0x1800234e0  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800234e5  xor     r8d, r8d; Reserved
0x1800234e8  call    cs:__imp_RegSetValueExW
0x1800234ee  lea     rbx, WPP_GLOBAL_Control
0x1800234f5  test    eax, eax
0x1800234f7  jz      short loc_180023523
0x1800234f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180023500  cmp     rcx, rbx
0x180023503  jz      short loc_180023523
0x180023505  test    byte ptr [rcx+1Ch], 1
0x180023509  jz      short loc_180023523
0x18002350b  mov     rcx, [rcx+10h]
0x18002350f  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180023516  mov     edx, 10h
0x18002351b  mov     r9d, eax
0x18002351e  call    WPP_SF_d
0x180023523  mov     rcx, [rbp+hKey]; hKey
0x180023527  lea     rdx, aCval2; "cval2"
0x18002352e  call    cs:__imp_RegDeleteValueW
0x180023534  test    eax, eax
0x180023536  jz      loc_1800235E1
0x18002353c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023543  cmp     rcx, rbx
0x180023546  jz      loc_1800235E1
0x18002354c  test    byte ptr [rcx+1Ch], 1
0x180023550  jz      loc_1800235E1
0x180023556  mov     edx, 11h
0x18002355b  jmp     short loc_1800235CE
0x18002355d  mov     rcx, [rbp+hKey]; hKey
0x180023561  lea     rdx, aCval; "cval"
0x180023568  xor     eax, eax
0x18002356a  mov     [rsp+60h+samDesired], r14d; cbData
0x18002356f  test    ebx, ebx
0x180023571  mov     r9d, r14d; dwType
0x180023574  setnz   al
0x180023577  xor     r8d, r8d; Reserved
0x18002357a  mov     [rbp+Data], eax
0x18002357d  lea     rax, [rbp+Data]
0x180023581  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180023586  call    cs:__imp_RegSetValueExW
0x18002358c  test    eax, eax
0x18002358e  jz      short loc_1800235E1
0x180023590  mov     rcx, cs:WPP_GLOBAL_Control
0x180023597  lea     rbx, WPP_GLOBAL_Control
0x18002359e  cmp     rcx, rbx
0x1800235a1  jz      short loc_1800235E1
0x1800235a3  test    byte ptr [rcx+1Ch], 1
0x1800235a7  jz      short loc_1800235E1
0x1800235a9  mov     edx, 13h
0x1800235ae  jmp     short loc_1800235CE
0x1800235b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235b7  lea     rbx, WPP_GLOBAL_Control
0x1800235be  cmp     rcx, rbx
0x1800235c1  jz      short loc_1800235E1
0x1800235c3  test    byte ptr [rcx+1Ch], 1
0x1800235c7  jz      short loc_1800235E1
0x1800235c9  mov     edx, 14h
0x1800235ce  mov     rcx, [rcx+10h]
0x1800235d2  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x1800235d9  mov     r9d, eax
0x1800235dc  call    WPP_SF_d
0x1800235e1  mov     rcx, [rbp+hKey]; hKey
0x1800235e5  test    rcx, rcx
0x1800235e8  jz      short loc_1800235F0
0x1800235ea  call    cs:__imp_RegCloseKey
0x1800235f0  add     rsp, 60h
0x1800235f4  pop     r14
0x1800235f6  pop     rbx
0x1800235f7  pop     rbp
0x1800235f8  retn
```
