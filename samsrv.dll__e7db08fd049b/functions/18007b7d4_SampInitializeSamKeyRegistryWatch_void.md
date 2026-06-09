# SampInitializeSamKeyRegistryWatch(void)

- ea: `0x18007b7d4`
- end: `0x18007b909`
- name: `?SampInitializeSamKeyRegistryWatch@@YAJXZ`
- size: `309`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800888c0`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x18007b7d4`
- `0x18007c424`
- `0x180086ff0`
- `0x1800894a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007b842`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007b842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b867`
- `ntdll!RtlInitializeCriticalSection` at `0x18007b7e1`
- `ntdll!RtlInitializeCriticalSection` at `0x18007b7e1`
- `LSASRV!LsaIRegisterNotification` at `0x18007b8c6`
- `LSASRV!LsaIRegisterNotification` at `0x18007b8c6`

## string_xrefs

- `0x18007b7f2`: `SampOpenOrCreateCCSControlSAMKey`
- `0x18007b891`: `SampInitializeSamKeyRegistryWatch - CreateEvent`

## pseudocode

```c
__int64 SampInitializeSamKeyRegistryWatch(void)
{
  HKEY *v0; // rdx
  __int64 v1; // rcx
  int CCSControlSAMKey; // eax
  unsigned int v3; // ebx
  PUNICODE_STRING v4; // rcx
  HANDLE EventW; // rax
  DWORD LastError; // eax

  RtlInitializeCriticalSection(&gcsSamKeyReadLock);
  CCSControlSAMKey = SampOpenOrCreateCCSControlSAMKey(v1, v0);
  v3 = CCSControlSAMKey;
  if ( CCSControlSAMKey >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    ghSamKeyWatchEvent = EventW;
    if ( EventW )
    {
      LsaIRegisterNotification(SampProcessSamKeyUpdates, 0, 2, 0, 0, 0, EventW);
      SampProcessSamKeyUpdates(0);
      v3 = 0;
    }
    else
    {
      if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 223, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, LastError);
      }
      v3 = -1073741801;
      SampSetErrorInfo(3221225495LL, "SampInitializeSamKeyRegistryWatch - CreateEvent");
    }
    goto LABEL_11;
  }
  SampSetErrorInfo((unsigned int)CCSControlSAMKey, "SampOpenOrCreateCCSControlSAMKey");
  v4 = WPP_GLOBAL_Control;
  if ( *((char *)&WPP_GLOBAL_Control[4].MaximumLength + 2) < 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[3].Buffer, 222, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v3);
LABEL_11:
    v4 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(&v4[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(v4[3].Buffer, 224, WPP_6405431812663459a7a3c2922bf567cd_Traceguids, v3, v3);
  return v3;
}

```

## disassembly

```asm
0x18007b7d4  push    rbx
0x18007b7d6  sub     rsp, 40h
0x18007b7da  lea     rcx, ?gcsSamKeyReadLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007b7e1  call    cs:__imp_RtlInitializeCriticalSection
0x18007b7e7  call    ?SampOpenOrCreateCCSControlSAMKey@@YAJKPEAPEAUHKEY__@@@Z; SampOpenOrCreateCCSControlSAMKey(ulong,HKEY__ * *)
0x18007b7ec  mov     ebx, eax
0x18007b7ee  test    eax, eax
0x18007b7f0  jns     short loc_18007B838
0x18007b7f2  lea     rdx, aSampopenorcrea; "SampOpenOrCreateCCSControlSAMKey"
0x18007b7f9  mov     ecx, eax
0x18007b7fb  call    SampSetErrorInfo
0x18007b800  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b807  test    byte ptr [rcx+44h], 80h
0x18007b80b  jz      loc_18007B8DC
0x18007b811  cmp     byte ptr [rcx+41h], 2
0x18007b815  jb      loc_18007B8DC
0x18007b81b  mov     rcx, [rcx+38h]
0x18007b81f  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18007b826  mov     edx, 0DEh
0x18007b82b  mov     r9d, ebx
0x18007b82e  call    WPP_SF_d
0x18007b833  jmp     loc_18007B8D5
0x18007b838  xor     r9d, r9d; lpName
0x18007b83b  xor     r8d, r8d; bInitialState
0x18007b83e  xor     edx, edx; bManualReset
0x18007b840  xor     ecx, ecx; lpEventAttributes
0x18007b842  call    cs:__imp_CreateEventW
0x18007b848  mov     cs:?ghSamKeyWatchEvent@@3PEAXEA, rax; void * ghSamKeyWatchEvent
0x18007b84f  test    rax, rax
0x18007b852  jnz     short loc_18007B8A1
0x18007b854  mov     rax, cs:WPP_GLOBAL_Control
0x18007b85b  test    byte ptr [rax+44h], 80h
0x18007b85f  jz      short loc_18007B88C
0x18007b861  cmp     byte ptr [rax+41h], 2
0x18007b865  jb      short loc_18007B88C
0x18007b867  call    cs:__imp_GetLastError
0x18007b86d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b874  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18007b87b  mov     edx, 0DFh
0x18007b880  mov     r9d, eax
0x18007b883  mov     rcx, [rcx+38h]
0x18007b887  call    WPP_SF_d
0x18007b88c  mov     ebx, 0C0000017h
0x18007b891  lea     rdx, aSampinitialize_16; "SampInitializeSamKeyRegistryWatch - Cre"...
0x18007b898  mov     ecx, ebx
0x18007b89a  call    SampSetErrorInfo
0x18007b89f  jmp     short loc_18007B8D5
0x18007b8a1  mov     [rsp+48h+var_18], rax
0x18007b8a6  lea     rcx, ?SampProcessSamKeyUpdates@@YAJPEAX@Z; SampProcessSamKeyUpdates(void *)
0x18007b8ad  xor     r9d, r9d
0x18007b8b0  mov     [rsp+48h+var_20], 0
0x18007b8b8  xor     edx, edx
0x18007b8ba  mov     [rsp+48h+var_28], 0
0x18007b8c2  lea     r8d, [r9+2]
0x18007b8c6  call    cs:__imp_LsaIRegisterNotification
0x18007b8cc  xor     ecx, ecx; void *
0x18007b8ce  call    ?SampProcessSamKeyUpdates@@YAJPEAX@Z; SampProcessSamKeyUpdates(void *)
0x18007b8d3  xor     ebx, ebx
0x18007b8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b8dc  test    dword ptr [rcx+44h], 20000h
0x18007b8e3  jz      short loc_18007B901
0x18007b8e5  mov     rcx, [rcx+38h]
0x18007b8e9  lea     r8, WPP_6405431812663459a7a3c2922bf567cd_Traceguids
0x18007b8f0  mov     edx, 0E0h
0x18007b8f5  mov     [rsp+48h+var_28], ebx
0x18007b8f9  mov     r9d, ebx
0x18007b8fc  call    WPP_SF_Dd
0x18007b901  mov     eax, ebx
0x18007b903  add     rsp, 40h
0x18007b907  pop     rbx
0x18007b908  retn
```
