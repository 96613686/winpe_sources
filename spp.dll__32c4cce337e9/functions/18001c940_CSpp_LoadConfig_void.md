# CSpp::_LoadConfig(void)

- ea: `0x18001c940`
- end: `0x18001caba`
- name: `?_LoadConfig@CSpp@@AEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(CSpp *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008b10`

## callees

- `0x18001c940`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ca90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ca24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ca6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ca24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ca6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c9da`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c9da`

## string_xrefs

- `0x18001c987`: `CSpp::_LoadConfig`
- `0x18001ca1d`: `CreateTimeout`

## pseudocode

```c
__int64 __fastcall CSpp::_LoadConfig(CSpp *this)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  int v7; // [rsp+38h] [rbp-38h] BYREF
  __int16 v8; // [rsp+3Ch] [rbp-34h]
  DWORD cbData; // [rsp+88h] [rbp+18h] BYREF
  DWORD Type; // [rsp+90h] [rbp+20h] BYREF
  int Data; // [rsp+98h] [rbp+28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "CSpp::_LoadConfig", 2943, 1);
  Data = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\SPP", 0, 0x20019u, &hKey) )
  {
    v7 = 1;
    v8 = 2954;
  }
  else
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"CreateTimeout", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
      *((_DWORD *)this + 11) = Data;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"DisableOptimizedRPCreation", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && cbData == 4 )
    {
      *((_DWORD *)this + 12) = Data;
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v4 = v7;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7, v2, v3);
  return v4;
}

```

## disassembly

```asm
0x18001c940  mov     [rsp-8+arg_0], rbx
0x18001c945  push    rbp
0x18001c946  mov     rbp, rsp
0x18001c949  sub     rsp, 70h
0x18001c94d  mov     rbx, rcx
0x18001c950  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c957  lea     rax, WPP_GLOBAL_Control
0x18001c95e  cmp     rcx, rax
0x18001c961  jz      short loc_18001C981
0x18001c963  test    dword ptr [rcx+1Ch], 20000000h
0x18001c96a  jz      short loc_18001C981
0x18001c96c  mov     rcx, [rcx+10h]
0x18001c970  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001c977  mov     edx, 1Eh
0x18001c97c  call    WPP_SF_
0x18001c981  mov     r9d, 1; unsigned __int16
0x18001c987  lea     rdx, aCsppLoadconfig; "CSpp::_LoadConfig"
0x18001c98e  mov     r8d, 0B7Fh; unsigned __int16
0x18001c994  lea     rcx, [rbp+var_38]; this
0x18001c998  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001c99d  lea     rax, [rbp+hKey]
0x18001c9a1  mov     [rbp+Data], 0
0x18001c9a8  mov     r9d, 20019h; samDesired
0x18001c9ae  mov     [rsp+70h+phkResult], rax; phkResult
0x18001c9b3  xor     r8d, r8d; ulOptions
0x18001c9b6  mov     [rbp+cbData], 0
0x18001c9bd  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001c9c4  mov     [rbp+Type], 0
0x18001c9cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c9d2  mov     [rbp+hKey], 0
0x18001c9da  call    cs:__imp_RegOpenKeyExW
0x18001c9e0  test    eax, eax
0x18001c9e2  jz      short loc_18001C9F9
0x18001c9e4  mov     eax, 0B8Ah
0x18001c9e9  mov     [rbp+var_38], 1
0x18001c9f0  mov     [rbp+var_34], ax
0x18001c9f4  jmp     loc_18001CA87
0x18001c9f9  mov     rcx, [rbp+hKey]; hKey
0x18001c9fd  lea     rax, [rbp+cbData]
0x18001ca01  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001ca06  lea     r9, [rbp+Type]; lpType
0x18001ca0a  lea     rax, [rbp+Data]
0x18001ca0e  mov     [rbp+cbData], 4
0x18001ca15  xor     r8d, r8d; lpReserved
0x18001ca18  mov     [rsp+70h+phkResult], rax; lpData
0x18001ca1d  lea     rdx, aCreatetimeout; "CreateTimeout"
0x18001ca24  call    cs:__imp_RegQueryValueExW
0x18001ca2a  test    eax, eax
0x18001ca2c  jnz     short loc_18001CA40
0x18001ca2e  cmp     [rbp+Type], 4
0x18001ca32  jnz     short loc_18001CA40
0x18001ca34  cmp     [rbp+cbData], 4
0x18001ca38  jnz     short loc_18001CA40
0x18001ca3a  mov     eax, [rbp+Data]
0x18001ca3d  mov     [rbx+2Ch], eax
0x18001ca40  mov     rcx, [rbp+hKey]; hKey
0x18001ca44  lea     rax, [rbp+cbData]
0x18001ca48  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18001ca4d  lea     r9, [rbp+Type]; lpType
0x18001ca51  lea     rax, [rbp+Data]
0x18001ca55  mov     [rbp+cbData], 4
0x18001ca5c  xor     r8d, r8d; lpReserved
0x18001ca5f  mov     [rsp+70h+phkResult], rax; lpData
0x18001ca64  lea     rdx, aDisableoptimiz; "DisableOptimizedRPCreation"
0x18001ca6b  call    cs:__imp_RegQueryValueExW
0x18001ca71  test    eax, eax
0x18001ca73  jnz     short loc_18001CA87
0x18001ca75  cmp     [rbp+Type], 4
0x18001ca79  jnz     short loc_18001CA87
0x18001ca7b  cmp     [rbp+cbData], 4
0x18001ca7f  jnz     short loc_18001CA87
0x18001ca81  mov     eax, [rbp+Data]
0x18001ca84  mov     [rbx+30h], eax
0x18001ca87  mov     rcx, [rbp+hKey]; hKey
0x18001ca8b  test    rcx, rcx
0x18001ca8e  jz      short loc_18001CA9E
0x18001ca90  call    cs:__imp_RegCloseKey
0x18001ca96  mov     [rbp+hKey], 0
0x18001ca9e  mov     ebx, [rbp+var_38]
0x18001caa1  lea     rcx, [rbp+var_38]; this
0x18001caa5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001caaa  mov     eax, ebx
0x18001caac  mov     rbx, [rsp+70h+arg_0]
0x18001cab4  add     rsp, 70h
0x18001cab8  pop     rbp
0x18001cab9  retn
```
