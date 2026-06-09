# AspNetGetExtensionVersion

- ea: `0x1800148d0`
- end: `0x180014a38`
- name: `AspNetGetExtensionVersion`
- size: `360`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a3a0`
- `0x180012b30`
- `0x1800146d4`
- `0x1800148d0`
- `0x180016ce0`
- `0x18001b710`
- `0x180020664`
- `0x180059e4c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180014909`
- `KERNEL32!GetModuleHandleW` at `0x180014909`
- `KERNEL32!SetLastError` at `0x180014a23`
- `KERNEL32!SetLastError` at `0x180014a23`
- `ADVAPI32!RegCloseKey` at `0x180014a17`
- `ADVAPI32!RegCloseKey` at `0x180014a17`
- `ADVAPI32!RegOpenKeyExW` at `0x1800149ac`
- `ADVAPI32!RegOpenKeyExW` at `0x1800149ac`
- `ADVAPI32!RegQueryValueExW` at `0x1800149ef`
- `ADVAPI32!RegQueryValueExW` at `0x1800149ef`

## string_xrefs

- `0x180014949`: `aspnet_isapi.dll`

## pseudocode

```c
__int64 __fastcall AspNetGetExtensionVersion(_DWORD *a1)
{
  unsigned int v1; // ebx
  signed int inited; // edi
  HMODULE ModuleHandleW; // rax
  char *v5; // rcx
  __int64 v6; // rdx
  char v7; // al
  char *v8; // rax
  bool v9; // zf
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  v1 = 0;
  if ( g_IsAppPoolInIntegratedMode )
  {
    g_InitHR = -1073741637;
    XspLogEvent(0x4000052Cu);
    inited = 0;
LABEL_18:
    v9 = inited == 0;
    goto LABEL_19;
  }
  ModuleHandleW = GetModuleHandleW(L"w3wp.exe");
  inited = InitializeLibrary(ModuleHandleW != 0);
  if ( inited )
    goto LABEL_17;
  PerfCounterInitialize();
  inited = ISAPIInitProcessModel();
  if ( inited )
    goto LABEL_17;
  EtwTraceAspNetRegister();
  v5 = (char *)(a1 + 1);
  *a1 = 6;
  v6 = 256;
  do
  {
    if ( v6 == -2147483390 )
      break;
    v7 = v5["aspnet_isapi.dll" - (char *)(a1 + 1)];
    if ( !v7 )
      break;
    *v5++ = v7;
    --v6;
  }
  while ( v6 );
  hKey = 0;
  v8 = v5 - 1;
  if ( v6 )
    v8 = v5;
  inited = 0;
  *v8 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\InetStp", 0, 0x20019u, &hKey) )
    goto LABEL_18;
  Data = 0;
  cbData = 4;
  Type = 4;
  if ( !RegQueryValueExW(hKey, L"MajorVersion", 0, &Type, (LPBYTE)&Data, &cbData) && Data >= 7 )
  {
    inited = InitIIS7Config();
    if ( inited >= 0 )
      inited = MgdInitIsapiModeStatic();
  }
  RegCloseKey(hKey);
  v9 = inited == 0;
  if ( inited )
  {
LABEL_17:
    SetLastError(inited);
    goto LABEL_18;
  }
LABEL_19:
  LOBYTE(v1) = v9;
  return v1;
}

```

## disassembly

```asm
0x1800148d0  push    rbx
0x1800148d2  push    rsi
0x1800148d3  push    rdi
0x1800148d4  sub     rsp, 40h
0x1800148d8  xor     ebx, ebx
0x1800148da  mov     rsi, rcx
0x1800148dd  cmp     cs:?g_IsAppPoolInIntegratedMode@@3HA, ebx; int g_IsAppPoolInIntegratedMode
0x1800148e3  jz      short loc_180014902
0x1800148e5  xor     edx, edx
0x1800148e7  mov     cs:?g_InitHR@@3JA, 0C00000BBh; long g_InitHR
0x1800148f1  mov     ecx, 4000052Ch; dwEventID
0x1800148f6  call    XspLogEvent
0x1800148fb  mov     edi, ebx
0x1800148fd  jmp     loc_180014A29
0x180014902  lea     rcx, ModuleName; "w3wp.exe"
0x180014909  call    cs:__imp_GetModuleHandleW
0x18001490f  test    rax, rax
0x180014912  mov     ecx, ebx
0x180014914  setnz   cl; int
0x180014917  call    ?InitializeLibrary@@YAJH@Z; InitializeLibrary(int)
0x18001491c  mov     edi, eax
0x18001491e  test    eax, eax
0x180014920  jnz     loc_180014A21
0x180014926  call    ?PerfCounterInitialize@@YAJXZ; PerfCounterInitialize(void)
0x18001492b  call    ?ISAPIInitProcessModel@@YAJXZ; ISAPIInitProcessModel(void)
0x180014930  mov     edi, eax
0x180014932  test    eax, eax
0x180014934  jnz     loc_180014A21
0x18001493a  call    ?EtwTraceAspNetRegister@@YAJXZ; EtwTraceAspNetRegister(void)
0x18001493f  lea     rcx, [rsi+4]
0x180014943  mov     dword ptr [rsi], 6
0x180014949  lea     r8, aAspnetIsapiDll; "aspnet_isapi.dll"
0x180014950  mov     edx, 100h
0x180014955  sub     r8, rcx
0x180014958  lea     rax, [rdx+7FFFFEFEh]
0x18001495f  test    rax, rax
0x180014962  jz      short loc_180014977
0x180014964  mov     al, [r8+rcx]
0x180014968  test    al, al
0x18001496a  jz      short loc_180014977
0x18001496c  mov     [rcx], al
0x18001496e  inc     rcx
0x180014971  sub     rdx, 1
0x180014975  jnz     short loc_180014958
0x180014977  test    rdx, rdx
0x18001497a  mov     [rsp+58h+hKey], rbx
0x18001497f  lea     rax, [rcx-1]
0x180014983  mov     r9d, 20019h; samDesired
0x180014989  cmovnz  rax, rcx
0x18001498d  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\InetStp"
0x180014994  xor     r8d, r8d; ulOptions
0x180014997  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001499e  mov     edi, ebx
0x1800149a0  mov     [rax], bl
0x1800149a2  lea     rax, [rsp+58h+hKey]
0x1800149a7  mov     [rsp+58h+phkResult], rax; phkResult
0x1800149ac  call    cs:__imp_RegOpenKeyExW
0x1800149b2  test    eax, eax
0x1800149b4  jnz     short loc_180014A29
0x1800149b6  mov     rcx, [rsp+58h+hKey]; hKey
0x1800149bb  lea     r9, [rsp+58h+Type]; lpType
0x1800149c0  mov     eax, 4
0x1800149c5  mov     [rsp+58h+Data], ebx
0x1800149c9  mov     [rsp+58h+cbData], eax
0x1800149cd  lea     rdx, aMajorversion; "MajorVersion"
0x1800149d4  mov     [rsp+58h+Type], eax
0x1800149d8  xor     r8d, r8d; lpReserved
0x1800149db  lea     rax, [rsp+58h+cbData]
0x1800149e0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800149e5  lea     rax, [rsp+58h+Data]
0x1800149ea  mov     [rsp+58h+phkResult], rax; lpData
0x1800149ef  call    cs:__imp_RegQueryValueExW
0x1800149f5  test    eax, eax
0x1800149f7  jnz     short loc_180014A12
0x1800149f9  cmp     [rsp+58h+Data], 7
0x1800149fe  jb      short loc_180014A12
0x180014a00  call    ?InitIIS7Config@@YAJXZ; InitIIS7Config(void)
0x180014a05  mov     edi, eax
0x180014a07  test    eax, eax
0x180014a09  js      short loc_180014A12
0x180014a0b  call    ?MgdInitIsapiModeStatic@@YAJXZ; MgdInitIsapiModeStatic(void)
0x180014a10  mov     edi, eax
0x180014a12  mov     rcx, [rsp+58h+hKey]; hKey
0x180014a17  call    cs:__imp_RegCloseKey
0x180014a1d  test    edi, edi
0x180014a1f  jz      short loc_180014A2B
0x180014a21  mov     ecx, edi; dwErrCode
0x180014a23  call    cs:__imp_SetLastError
0x180014a29  test    edi, edi
0x180014a2b  setz    bl
0x180014a2e  mov     eax, ebx
0x180014a30  add     rsp, 40h
0x180014a34  pop     rdi
0x180014a35  pop     rsi
0x180014a36  pop     rbx
0x180014a37  retn
```
