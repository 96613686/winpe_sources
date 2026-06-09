# GetTimeouts

- ea: `0x1800028f4`
- end: `0x180002ae4`
- name: `GetTimeouts`
- size: `496`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004160`
- `0x180008040`

## callees

- `0x180002724`
- `0x1800027f8`
- `0x1800028f4`
- `0x1800035c0`

## import_xrefs

- `ntdll!RtlOpenCurrentUser` at `0x180002916`
- `ntdll!RtlOpenCurrentUser` at `0x180002916`
- `ntdll!NtClose` at `0x180002a31`
- `ntdll!NtClose` at `0x180002a41`
- `ntdll!NtClose` at `0x180002a9c`
- `ntdll!NtClose` at `0x180002ad1`
- `ntdll!NtClose` at `0x180002a31`
- `ntdll!NtClose` at `0x180002a41`
- `ntdll!NtClose` at `0x180002a9c`
- `ntdll!NtClose` at `0x180002ad1`
- `USER32!SystemParametersInfoW` at `0x180002955`
- `USER32!SystemParametersInfoW` at `0x180002970`
- `USER32!SystemParametersInfoW` at `0x180002a72`
- `USER32!SystemParametersInfoW` at `0x180002955`
- `USER32!SystemParametersInfoW` at `0x180002970`
- `USER32!SystemParametersInfoW` at `0x180002a72`

## string_xrefs

- `0x180002a53`: `\Registry\Machine\System\CurrentControlSet\Control`
- `0x180002aae`: `\Registry\Machine\Software\Policies\Microsoft\Windows\System`

## pseudocode

```c
NTSTATUS GetTimeouts()
{
  UINT v0; // eax
  NTSTATUS result; // eax
  HANDLE Handle; // [rsp+30h] [rbp+10h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp+18h] BYREF

  KeyHandle = 0;
  Handle = 0;
  if ( RtlOpenCurrentUser(0x2000000u, &KeyHandle) >= 0 )
  {
    if ( (int)MyRegOpenKey(KeyHandle, L"Control Panel\\Desktop", &Handle) >= 0 )
    {
      SystemParametersInfoW(0x78u, 0, &gCmsHungAppTimeout, 0);
      SystemParametersInfoW(0x7Au, 0, &gCmsWaitToKillTimeout, 0);
      if ( gCmsHungAppTimeout )
        v0 = gCmsWaitToKillTimeout / gCmsHungAppTimeout;
      else
        v0 = 0;
      gdwHungToKillCount = v0;
      gfAutoEndTask = GetRegIntFromID(Handle);
      gCmsQuickAppShutdownTimeout = GetRegIntFromID(Handle);
      if ( !gCmsQuickAppShutdownTimeout )
        gCmsQuickAppShutdownTimeout = 500;
      gCmsQuickAppShutdownCleanupTimeout = GetRegIntFromID(Handle);
      if ( !gCmsQuickAppShutdownCleanupTimeout )
        gCmsQuickAppShutdownCleanupTimeout = 1000;
      gCmsQuickResolverTimeout = GetRegIntFromID(Handle);
      if ( !gCmsQuickResolverTimeout )
        gCmsQuickResolverTimeout = 5000;
      NtClose(Handle);
    }
    NtClose(KeyHandle);
  }
  if ( (int)MyRegOpenKey(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control", &Handle) >= 0 )
  {
    SystemParametersInfoW(0x7Cu, 0, &gdwServicesWaitToKillTimeout, 0);
    gdwProcessTerminateTimeout = GetRegIntFromID(Handle);
    NtClose(Handle);
  }
  result = MyRegOpenKey(0, L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\System", &Handle);
  if ( result >= 0 )
  {
    gfAllowBlockingApps = GetRegDwordIntFromID(Handle);
    return NtClose(Handle);
  }
  return result;
}

```

## disassembly

```asm
0x1800028f4  push    rbp
0x1800028f6  mov     rbp, rsp
0x1800028f9  sub     rsp, 20h
0x1800028fd  lea     rdx, [rbp+KeyHandle]; KeyHandle
0x180002901  mov     [rbp+KeyHandle], 0
0x180002909  mov     ecx, 2000000h; DesiredAccess
0x18000290e  mov     [rbp+Handle], 0
0x180002916  call    cs:__imp_RtlOpenCurrentUser
0x18000291d  nop     dword ptr [rax+rax+00h]
0x180002922  test    eax, eax
0x180002924  js      loc_180002A4D
0x18000292a  mov     rcx, [rbp+KeyHandle]
0x18000292e  lea     r8, [rbp+Handle]
0x180002932  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x180002939  call    MyRegOpenKey
0x18000293e  test    eax, eax
0x180002940  js      loc_180002A3D
0x180002946  xor     edx, edx; uiParam
0x180002948  lea     r8, gCmsHungAppTimeout; pvParam
0x18000294f  xor     r9d, r9d; fWinIni
0x180002952  lea     ecx, [rdx+78h]; uiAction
0x180002955  call    cs:__imp_SystemParametersInfoW
0x18000295c  nop     dword ptr [rax+rax+00h]
0x180002961  xor     edx, edx; uiParam
0x180002963  lea     r8, gCmsWaitToKillTimeout; pvParam
0x18000296a  xor     r9d, r9d; fWinIni
0x18000296d  lea     ecx, [rdx+7Ah]; uiAction
0x180002970  call    cs:__imp_SystemParametersInfoW
0x180002977  nop     dword ptr [rax+rax+00h]
0x18000297c  mov     ecx, cs:gCmsHungAppTimeout
0x180002982  test    ecx, ecx
0x180002984  jz      short loc_180002992
0x180002986  mov     eax, cs:gCmsWaitToKillTimeout
0x18000298c  xor     edx, edx
0x18000298e  div     ecx
0x180002990  jmp     short loc_180002994
0x180002992  xor     eax, eax
0x180002994  mov     r8d, cs:gfAutoEndTask
0x18000299b  mov     edx, 0Bh
0x1800029a0  mov     rcx, [rbp+Handle]; KeyHandle
0x1800029a4  mov     cs:gdwHungToKillCount, eax
0x1800029aa  call    GetRegIntFromID
0x1800029af  mov     rcx, [rbp+Handle]; KeyHandle
0x1800029b3  mov     edx, 19h
0x1800029b8  mov     r8d, 1F4h
0x1800029be  mov     cs:gfAutoEndTask, eax
0x1800029c4  call    GetRegIntFromID
0x1800029c9  mov     cs:gCmsQuickAppShutdownTimeout, eax
0x1800029cf  test    eax, eax
0x1800029d1  jnz     short loc_1800029DD
0x1800029d3  mov     cs:gCmsQuickAppShutdownTimeout, 1F4h
0x1800029dd  mov     rcx, [rbp+Handle]; KeyHandle
0x1800029e1  mov     edx, 1Ah
0x1800029e6  mov     r8d, 3E8h
0x1800029ec  call    GetRegIntFromID
0x1800029f1  mov     cs:gCmsQuickAppShutdownCleanupTimeout, eax
0x1800029f7  test    eax, eax
0x1800029f9  jnz     short loc_180002A05
0x1800029fb  mov     cs:gCmsQuickAppShutdownCleanupTimeout, 3E8h
0x180002a05  mov     rcx, [rbp+Handle]; KeyHandle
0x180002a09  mov     edx, 0Eh
0x180002a0e  mov     r8d, 1388h
0x180002a14  call    GetRegIntFromID
0x180002a19  mov     cs:gCmsQuickResolverTimeout, eax
0x180002a1f  test    eax, eax
0x180002a21  jnz     short loc_180002A2D
0x180002a23  mov     cs:gCmsQuickResolverTimeout, 1388h
0x180002a2d  mov     rcx, [rbp+Handle]; Handle
0x180002a31  call    cs:__imp_NtClose
0x180002a38  nop     dword ptr [rax+rax+00h]
0x180002a3d  mov     rcx, [rbp+KeyHandle]; Handle
0x180002a41  call    cs:__imp_NtClose
0x180002a48  nop     dword ptr [rax+rax+00h]
0x180002a4d  lea     r8, [rbp+Handle]
0x180002a51  xor     ecx, ecx
0x180002a53  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x180002a5a  call    MyRegOpenKey
0x180002a5f  test    eax, eax
0x180002a61  js      short loc_180002AA8
0x180002a63  xor     edx, edx; uiParam
0x180002a65  lea     r8, gdwServicesWaitToKillTimeout; pvParam
0x180002a6c  xor     r9d, r9d; fWinIni
0x180002a6f  lea     ecx, [rdx+7Ch]; uiAction
0x180002a72  call    cs:__imp_SystemParametersInfoW
0x180002a79  nop     dword ptr [rax+rax+00h]
0x180002a7e  mov     rcx, [rbp+Handle]; KeyHandle
0x180002a82  mov     edx, 16h
0x180002a87  mov     r8d, 1F4h
0x180002a8d  call    GetRegIntFromID
0x180002a92  mov     rcx, [rbp+Handle]; Handle
0x180002a96  mov     cs:gdwProcessTerminateTimeout, eax
0x180002a9c  call    cs:__imp_NtClose
0x180002aa3  nop     dword ptr [rax+rax+00h]
0x180002aa8  lea     r8, [rbp+Handle]
0x180002aac  xor     ecx, ecx
0x180002aae  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine\\Software\\Policies"...
0x180002ab5  call    MyRegOpenKey
0x180002aba  test    eax, eax
0x180002abc  js      short loc_180002ADD
0x180002abe  mov     rcx, [rbp+Handle]; KeyHandle
0x180002ac2  call    GetRegDwordIntFromID
0x180002ac7  mov     rcx, [rbp+Handle]; Handle
0x180002acb  mov     cs:gfAllowBlockingApps, eax
0x180002ad1  call    cs:__imp_NtClose
0x180002ad8  nop     dword ptr [rax+rax+00h]
0x180002add  add     rsp, 20h
0x180002ae1  pop     rbp
0x180002ae2  retn
```
