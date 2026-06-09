# CSpp::_ModifyBackupFlagForBackupType(ulong)

- ea: `0x18001cbfc`
- end: `0x18001cd84`
- name: `?_ModifyBackupFlagForBackupType@CSpp@@AEAAKK@Z`
- size: `392`
- prototype: `__int64 __fastcall(CSpp *this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006730`
- `0x180013c7c`

## callees

- `0x18001b70c`
- `0x18001cbfc`
- `0x180020710`
- `0x180020738`
- `0x1800268b4`
- `0x1800269ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cd63`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cd63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ccde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ccde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cca5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cca5`

## pseudocode

```c
__int64 __fastcall CSpp::_ModifyBackupFlagForBackupType(CSpp *this, unsigned int a2)
{
  CSpp *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r8
  PVOID *v6; // rcx
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v9[56]; // [rsp+38h] [rbp-38h] BYREF
  CSpp *cbData; // [rsp+90h] [rbp+20h] BYREF
  DWORD Type; // [rsp+A0h] [rbp+30h] BYREF
  int Data; // [rsp+A8h] [rbp+38h] BYREF

  cbData = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v9, "CSpp::_ModifyBackupFlagForBackupType", 3001, 1);
  Data = 0;
  LODWORD(cbData) = 0;
  Type = 0;
  hKey = 0;
  if ( (unsigned int)CSpp::_IsServerSku(v3) == 1
    && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP", 0, 0x20019u, &hKey) )
  {
    LODWORD(cbData) = 4;
    if ( !RegQueryValueExW(hKey, L"BackupType", 0, &Type, (LPBYTE)&Data, (LPDWORD)&cbData)
      && Type == 4
      && (_DWORD)cbData == 4 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( Data )
        a2 |= 8u;
      else
        a2 &= ~8u;
      if ( v6 != &WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x8000000) != 0 )
        WPP_SF_D(v6[2], 33, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids, a2);
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v9, v4, v5);
  return a2;
}

```

## disassembly

```asm
0x18001cbfc  mov     [rsp-18h+cbData], rcx
0x18001cc01  push    rbp
0x18001cc02  push    rbx
0x18001cc03  push    rsi
0x18001cc04  mov     rbp, rsp
0x18001cc07  sub     rsp, 70h
0x18001cc0b  mov     ebx, edx
0x18001cc0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc14  lea     rsi, WPP_GLOBAL_Control
0x18001cc1b  cmp     rcx, rsi
0x18001cc1e  jz      short loc_18001CC3E
0x18001cc20  test    dword ptr [rcx+1Ch], 20000000h
0x18001cc27  jz      short loc_18001CC3E
0x18001cc29  mov     rcx, [rcx+10h]
0x18001cc2d  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001cc34  mov     edx, 1Fh
0x18001cc39  call    WPP_SF_
0x18001cc3e  mov     r9d, 1; unsigned __int16
0x18001cc44  lea     rdx, aCsppModifyback; "CSpp::_ModifyBackupFlagForBackupType"
0x18001cc4b  mov     r8d, 0BB9h; unsigned __int16
0x18001cc51  lea     rcx, [rbp+var_38]; this
0x18001cc55  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001cc5a  mov     [rbp+Data], 0
0x18001cc61  mov     dword ptr [rbp+cbData], 0
0x18001cc68  mov     [rbp+Type], 0
0x18001cc6f  mov     [rbp+hKey], 0
0x18001cc77  call    ?_IsServerSku@CSpp@@AEAAJXZ; CSpp::_IsServerSku(void)
0x18001cc7c  cmp     eax, 1
0x18001cc7f  jnz     loc_18001CD71
0x18001cc85  lea     rax, [rbp+hKey]
0x18001cc89  mov     r9d, 20019h; samDesired
0x18001cc8f  xor     r8d, r8d; ulOptions
0x18001cc92  mov     [rsp+70h+phkResult], rax; phkResult
0x18001cc97  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001cc9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cca5  call    cs:__imp_RegOpenKeyExW
0x18001ccab  test    eax, eax
0x18001ccad  jnz     loc_18001CD71
0x18001ccb3  mov     rcx, [rbp+hKey]; hKey
0x18001ccb7  lea     rax, [rbp+cbData]
0x18001ccbb  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001ccc0  lea     r9, [rbp+Type]; lpType
0x18001ccc4  lea     rax, [rbp+Data]
0x18001ccc8  mov     dword ptr [rbp+cbData], 4
0x18001cccf  xor     r8d, r8d; lpReserved
0x18001ccd2  mov     [rsp+70h+phkResult], rax; lpData
0x18001ccd7  lea     rdx, aBackuptype; "BackupType"
0x18001ccde  call    cs:__imp_RegQueryValueExW
0x18001cce4  test    eax, eax
0x18001cce6  jnz     short loc_18001CD5A
0x18001cce8  cmp     [rbp+Type], 4
0x18001ccec  jnz     short loc_18001CD5A
0x18001ccee  cmp     dword ptr [rbp+cbData], 4
0x18001ccf2  jnz     short loc_18001CD5A
0x18001ccf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccfb  cmp     rcx, rsi
0x18001ccfe  jz      short loc_18001CD26
0x18001cd00  test    dword ptr [rcx+1Ch], 8000000h
0x18001cd07  jz      short loc_18001CD26
0x18001cd09  mov     rcx, [rcx+10h]
0x18001cd0d  lea     edx, [rax+20h]
0x18001cd10  mov     r9d, ebx
0x18001cd13  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001cd1a  call    WPP_SF_D
0x18001cd1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd26  cmp     [rbp+Data], 0
0x18001cd2a  jnz     short loc_18001CD31
0x18001cd2c  and     ebx, 0FFFFFFF7h
0x18001cd2f  jmp     short loc_18001CD34
0x18001cd31  or      ebx, 8
0x18001cd34  cmp     rcx, rsi
0x18001cd37  jz      short loc_18001CD5A
0x18001cd39  test    dword ptr [rcx+1Ch], 8000000h
0x18001cd40  jz      short loc_18001CD5A
0x18001cd42  mov     rcx, [rcx+10h]
0x18001cd46  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001cd4d  mov     edx, 21h ; '!'
0x18001cd52  mov     r9d, ebx
0x18001cd55  call    WPP_SF_D
0x18001cd5a  mov     rcx, [rbp+hKey]; hKey
0x18001cd5e  test    rcx, rcx
0x18001cd61  jz      short loc_18001CD71
0x18001cd63  call    cs:__imp_RegCloseKey
0x18001cd69  mov     [rbp+hKey], 0
0x18001cd71  lea     rcx, [rbp+var_38]; this
0x18001cd75  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001cd7a  mov     eax, ebx
0x18001cd7c  add     rsp, 70h
0x18001cd80  pop     rsi
0x18001cd81  pop     rbx
0x18001cd82  pop     rbp
0x18001cd83  retn
```
