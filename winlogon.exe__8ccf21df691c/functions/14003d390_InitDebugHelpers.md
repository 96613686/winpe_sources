# InitDebugHelpers

- ea: `0x14003d390`
- end: `0x14003d511`
- name: `InitDebugHelpers`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400877f0`

## callees

- `0x1400057f4`
- `0x14003d390`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14003d3d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetUnhandledExceptionFilter` at `0x14003d3d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003d406`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003d406`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003d444`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14003d444`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003d460`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003d460`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x14003d502`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x14003d502`
- `ntdll!NtQuerySystemInformation` at `0x14003d3b2`
- `ntdll!NtQuerySystemInformation` at `0x14003d3b2`
- `ntdll!NtSystemDebugControl` at `0x14003d492`
- `ntdll!NtSystemDebugControl` at `0x14003d492`

## string_xrefs

- `0x14003d421`: `NoDebugThread`

## pseudocode

```c
__int64 __fastcall InitDebugHelpers(__int64 a1)
{
  BOOL v1; // ebx
  __int64 v2; // rbx
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  __int64 SystemInformation; // [rsp+70h] [rbp+18h] BYREF
  void *Type; // [rsp+78h] [rbp+20h] BYREF
  int Data; // [rsp+80h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+30h] BYREF

  SystemInformation = a1;
  LOWORD(SystemInformation) = 0;
  NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0);
  if ( (_BYTE)SystemInformation || NtCurrentPeb()->BeingDebugged )
  {
    SetUnhandledExceptionFilter(MyUnhandledExceptionFilter);
    hKey = 0;
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
           0,
           0x20019u,
           &hKey) )
    {
      goto LABEL_8;
    }
    v1 = 1;
    Data = 0;
    LODWORD(Type) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"NoDebugThread", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData) && (_DWORD)Type == 4 )
      v1 = Data == 0;
    RegCloseKey(hKey);
    if ( v1 )
    {
LABEL_8:
      Type = 0;
      v2 = NtSystemDebugControl(SysDbgRegisterForUmBreakInfo, 0, 0, 0, 0, 0);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_e10c96d05cf7373b02487e5d91a8da97_Traceguids,
          (unsigned int)v2);
      }
      CreateTimerQueueTimer(&Type, 0, WlpPeriodicBreak, (PVOID)(((v2 >> 63) & 1) - 1), 0xEA60u, 0xEA60u, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003d390  mov     [rsp-10h+SystemInformation], rcx
0x14003d395  push    rbp
0x14003d396  push    rbx
0x14003d397  mov     rbp, rsp
0x14003d39a  sub     rsp, 58h
0x14003d39e  xor     eax, eax
0x14003d3a0  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x14003d3a4  xor     r9d, r9d; ReturnLength
0x14003d3a7  mov     word ptr [rbp+SystemInformation], ax
0x14003d3ab  lea     r8d, [rax+2]; SystemInformationLength
0x14003d3af  lea     ecx, [rax+23h]; SystemInformationClass
0x14003d3b2  call    cs:__imp_NtQuerySystemInformation
0x14003d3b8  cmp     byte ptr [rbp+SystemInformation], 0
0x14003d3bc  jnz     short loc_14003D3D1
0x14003d3be  mov     rax, gs:60h
0x14003d3c7  cmp     byte ptr [rax+2], 0
0x14003d3cb  jz      loc_14003D508
0x14003d3d1  lea     rcx, ?MyUnhandledExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@@Z; lpTopLevelExceptionFilter
0x14003d3d8  call    cs:__imp_SetUnhandledExceptionFilter
0x14003d3de  lea     rax, [rbp+hKey]
0x14003d3e2  mov     [rbp+hKey], 0
0x14003d3ea  mov     r9d, 20019h; samDesired
0x14003d3f0  mov     [rsp+58h+phkResult], rax; phkResult
0x14003d3f5  xor     r8d, r8d; ulOptions
0x14003d3f8  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14003d3ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003d406  call    cs:__imp_RegOpenKeyExW
0x14003d40c  test    eax, eax
0x14003d40e  jnz     short loc_14003D46E
0x14003d410  mov     rcx, [rbp+hKey]; hKey
0x14003d414  lea     ebx, [rax+1]
0x14003d417  mov     [rbp+Data], eax
0x14003d41a  lea     r9, [rbp+Type]; lpType
0x14003d41e  mov     dword ptr [rbp+Type], eax
0x14003d421  lea     rdx, aNodebugthread; "NoDebugThread"
0x14003d428  lea     rax, [rbp+cbData]
0x14003d42c  mov     [rbp+cbData], 4
0x14003d433  mov     [rsp+58h+lpcbData], rax; lpcbData
0x14003d438  xor     r8d, r8d; lpReserved
0x14003d43b  lea     rax, [rbp+Data]
0x14003d43f  mov     [rsp+58h+phkResult], rax; lpData
0x14003d444  call    cs:__imp_RegQueryValueExW
0x14003d44a  test    eax, eax
0x14003d44c  jnz     short loc_14003D45C
0x14003d44e  cmp     dword ptr [rbp+Type], 4
0x14003d452  jnz     short loc_14003D45C
0x14003d454  xor     ebx, ebx
0x14003d456  cmp     [rbp+Data], ebx
0x14003d459  setz    bl
0x14003d45c  mov     rcx, [rbp+hKey]; hKey
0x14003d460  call    cs:__imp_RegCloseKey
0x14003d466  test    ebx, ebx
0x14003d468  jz      loc_14003D508
0x14003d46e  xor     edx, edx; InputBuffer
0x14003d470  mov     [rsp+58h+lpcbData], 0; ReturnLength
0x14003d479  xor     r9d, r9d; OutputBuffer
0x14003d47c  mov     [rbp+Type], 0
0x14003d484  xor     r8d, r8d; InputBufferLength
0x14003d487  mov     dword ptr [rsp+58h+phkResult], 0; OutputBufferLength
0x14003d48f  lea     ecx, [rdx+20h]; ControlCode
0x14003d492  call    cs:__imp_NtSystemDebugControl
0x14003d498  movsxd  rbx, eax
0x14003d49b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d4a2  lea     rax, WPP_GLOBAL_Control
0x14003d4a9  cmp     rcx, rax
0x14003d4ac  jz      short loc_14003D4D2
0x14003d4ae  test    byte ptr [rcx+1Ch], 8
0x14003d4b2  jz      short loc_14003D4D2
0x14003d4b4  cmp     byte ptr [rcx+19h], 5
0x14003d4b8  jb      short loc_14003D4D2
0x14003d4ba  mov     rcx, [rcx+10h]
0x14003d4be  lea     r8, WPP_e10c96d05cf7373b02487e5d91a8da97_Traceguids
0x14003d4c5  mov     edx, 15h
0x14003d4ca  mov     r9d, ebx
0x14003d4cd  call    WPP_SF_d
0x14003d4d2  mov     eax, 0EA60h
0x14003d4d7  mov     [rsp+58h+Flags], 0; Flags
0x14003d4df  mov     dword ptr [rsp+58h+lpcbData], eax; Period
0x14003d4e3  lea     r8, ?WlpPeriodicBreak@@YAXPEAXE@Z; Callback
0x14003d4ea  mov     r9, rbx
0x14003d4ed  mov     dword ptr [rsp+58h+phkResult], eax; DueTime
0x14003d4f1  sar     r9, 3Fh
0x14003d4f5  lea     rcx, [rbp+Type]; phNewTimer
0x14003d4f9  and     r9d, 1
0x14003d4fd  xor     edx, edx; TimerQueue
0x14003d4ff  dec     r9; Parameter
0x14003d502  call    cs:__imp_CreateTimerQueueTimer
0x14003d508  xor     eax, eax
0x14003d50a  add     rsp, 58h
0x14003d50e  pop     rbx
0x14003d50f  pop     rbp
0x14003d510  retn
```
