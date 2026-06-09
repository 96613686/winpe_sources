# SampInitializeDeviceAccessRegistryWatch(void)

- ea: `0x180076528`
- end: `0x1800766ad`
- name: `?SampInitializeDeviceAccessRegistryWatch@@YAJXZ`
- size: `389`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180076438`

## callees

- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x180076350`
- `0x180076528`
- `0x180076880`
- `0x1800894a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800765a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800765a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800765c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800765c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076555`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180076555`
- `LSASRV!LsaIRegisterNotification` at `0x180076665`
- `LSASRV!LsaIRegisterNotification` at `0x180076665`

## string_xrefs

- `0x180076547`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x180076631`: `SampInitializeDeviceAccessKeyRegistryWatch - RegOpenKeyEx`
- `0x1800765f3`: `SampInitializeDeviceAccessKeyRegistryWatch - CreateEvent`

## pseudocode

```c
__int64 SampInitializeDeviceAccessRegistryWatch(void)
{
  unsigned int v0; // eax
  unsigned int v1; // edi
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned int v4; // ebx
  const char *v5; // rdx
  __int64 v6; // rcx

  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
         0,
         0x20019u,
         &ghDeviceAccessKey);
  v1 = v0;
  if ( v0 == 2 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control[3].Buffer, 49, WPP_e40c88ada9b13963995c64c8352bb48c_Traceguids);
    SampConfigurePoliciesForCTAMode(2);
  }
  else if ( v0 )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 50, WPP_e40c88ada9b13963995c64c8352bb48c_Traceguids, v0);
    v4 = -1073741801;
    v5 = "SampInitializeDeviceAccessKeyRegistryWatch - RegOpenKeyEx";
    v6 = v1;
    goto LABEL_16;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  ghDeviceAccessKeyWatchEvent = EventW;
  if ( !EventW )
  {
    if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 1) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 51, WPP_e40c88ada9b13963995c64c8352bb48c_Traceguids, LastError);
    }
    v4 = -1073741801;
    v5 = "SampInitializeDeviceAccessKeyRegistryWatch - CreateEvent";
    v6 = 3221225495LL;
LABEL_16:
    SampSetErrorInfo(v6, v5);
    goto LABEL_18;
  }
  LsaIRegisterNotification(SampProcessDeviceAccessUpdate, 0, 2, 0, 0, 0, EventW);
  SampProcessDeviceAccessUpdate(0);
  v4 = 0;
LABEL_18:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 52, WPP_e40c88ada9b13963995c64c8352bb48c_Traceguids, v4, v4);
  return v4;
}

```

## disassembly

```asm
0x180076528  mov     [rsp+arg_0], rbx
0x18007652d  push    rdi
0x18007652e  sub     rsp, 40h
0x180076532  lea     rax, ?ghDeviceAccessKey@@3PEAUHKEY__@@EA; HKEY__ * ghDeviceAccessKey
0x180076539  mov     r9d, 20019h; samDesired
0x18007653f  xor     r8d, r8d; ulOptions
0x180076542  mov     [rsp+48h+phkResult], rax; phkResult
0x180076547  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18007654e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180076555  call    cs:__imp_RegOpenKeyExW
0x18007655b  mov     ebx, 2
0x180076560  mov     edi, eax
0x180076562  cmp     eax, ebx
0x180076564  jnz     loc_1800765FE
0x18007656a  mov     rcx, cs:WPP_GLOBAL_Control
0x180076571  test    byte ptr [rcx+44h], 1
0x180076575  jz      short loc_180076590
0x180076577  cmp     byte ptr [rcx+41h], 4
0x18007657b  jb      short loc_180076590
0x18007657d  mov     rcx, [rcx+38h]
0x180076581  lea     edx, [rbx+2Fh]
0x180076584  lea     r8, WPP_e40c88ada9b13963995c64c8352bb48c_Traceguids
0x18007658b  call    WPP_SF_
0x180076590  mov     ecx, ebx
0x180076592  call    ?SampConfigurePoliciesForCTAMode@@YAXW4SAM_CTA_MODE@@@Z; SampConfigurePoliciesForCTAMode(SAM_CTA_MODE)
0x180076597  xor     r9d, r9d; lpName
0x18007659a  xor     r8d, r8d; bInitialState
0x18007659d  xor     edx, edx; bManualReset
0x18007659f  xor     ecx, ecx; lpEventAttributes
0x1800765a1  call    cs:__imp_CreateEventW
0x1800765a7  mov     cs:?ghDeviceAccessKeyWatchEvent@@3PEAXEA, rax; void * ghDeviceAccessKeyWatchEvent
0x1800765ae  test    rax, rax
0x1800765b1  jnz     loc_180076641
0x1800765b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800765be  test    byte ptr [rax+44h], 1
0x1800765c2  jz      short loc_1800765EE
0x1800765c4  cmp     [rax+41h], bl
0x1800765c7  jb      short loc_1800765EE
0x1800765c9  call    cs:__imp_GetLastError
0x1800765cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800765d6  lea     r8, WPP_e40c88ada9b13963995c64c8352bb48c_Traceguids
0x1800765dd  mov     edx, 33h ; '3'
0x1800765e2  mov     r9d, eax
0x1800765e5  mov     rcx, [rcx+38h]
0x1800765e9  call    WPP_SF_d
0x1800765ee  mov     ebx, 0C0000017h
0x1800765f3  lea     rdx, aSampinitialize_7; "SampInitializeDeviceAccessKeyRegistryWa"...
0x1800765fa  mov     ecx, ebx
0x1800765fc  jmp     short loc_18007663A
0x1800765fe  test    edi, edi
0x180076600  jz      short loc_180076597
0x180076602  mov     rcx, cs:WPP_GLOBAL_Control
0x180076609  test    byte ptr [rcx+44h], 1
0x18007660d  jz      short loc_18007662C
0x18007660f  cmp     [rcx+41h], bl
0x180076612  jb      short loc_18007662C
0x180076614  mov     rcx, [rcx+38h]
0x180076618  lea     r8, WPP_e40c88ada9b13963995c64c8352bb48c_Traceguids
0x18007661f  mov     edx, 32h ; '2'
0x180076624  mov     r9d, edi
0x180076627  call    WPP_SF_d
0x18007662c  mov     ebx, 0C0000017h
0x180076631  lea     rdx, aSampinitialize_18; "SampInitializeDeviceAccessKeyRegistryWa"...
0x180076638  mov     ecx, edi
0x18007663a  call    SampSetErrorInfo
0x18007663f  jmp     short loc_180076674
0x180076641  mov     [rsp+48h+var_18], rax
0x180076646  lea     rcx, ?SampProcessDeviceAccessUpdate@@YAJPEAX@Z; SampProcessDeviceAccessUpdate(void *)
0x18007664d  mov     [rsp+48h+var_20], 0
0x180076655  xor     r9d, r9d
0x180076658  mov     r8d, ebx
0x18007665b  mov     dword ptr [rsp+48h+phkResult], 0
0x180076663  xor     edx, edx
0x180076665  call    cs:__imp_LsaIRegisterNotification
0x18007666b  xor     ecx, ecx; void *
0x18007666d  call    ?SampProcessDeviceAccessUpdate@@YAJPEAX@Z; SampProcessDeviceAccessUpdate(void *)
0x180076672  xor     ebx, ebx
0x180076674  mov     rcx, cs:WPP_GLOBAL_Control
0x18007667b  test    dword ptr [rcx+44h], 20000h
0x180076682  jz      short loc_1800766A0
0x180076684  mov     rcx, [rcx+38h]
0x180076688  lea     r8, WPP_e40c88ada9b13963995c64c8352bb48c_Traceguids
0x18007668f  mov     edx, 34h ; '4'
0x180076694  mov     dword ptr [rsp+48h+phkResult], ebx
0x180076698  mov     r9d, ebx
0x18007669b  call    WPP_SF_Dd
0x1800766a0  mov     eax, ebx
0x1800766a2  mov     rbx, [rsp+48h+arg_0]
0x1800766a7  add     rsp, 40h
0x1800766ab  pop     rdi
0x1800766ac  retn
```
