# XsStopXactsrv

- ea: `0x18003003c`
- end: `0x180030190`
- name: `XsStopXactsrv`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002dfb0`

## callees

- `0x180020de8`
- `0x18003003c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030156`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030156`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003010d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003010d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003016e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003016e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003017b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003017b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180030052`
- `ntdll!RtlAcquireResourceExclusive` at `0x180030052`
- `ntdll!RtlReleaseResource` at `0x1800300f3`
- `ntdll!RtlReleaseResource` at `0x1800300f3`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800300ab`
- `RPCRT4!RpcServerUnregisterIf` at `0x1800300ab`
- `RPCRT4!RpcBindingVectorFree` at `0x180030098`
- `RPCRT4!RpcBindingVectorFree` at `0x180030098`
- `RPCRT4!RpcEpUnregister` at `0x18003008d`
- `RPCRT4!RpcEpUnregister` at `0x18003008d`
- `RPCRT4!RpcServerInqBindings` at `0x180030074`
- `RPCRT4!RpcServerInqBindings` at `0x180030074`

## pseudocode

```c
void XsStopXactsrv()
{
  unsigned int v0; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+30h] [rbp+8h] BYREF

  BindingVector = 0;
  RtlAcquireResourceExclusive(&stru_18005E3D8, 1u);
  if ( dword_18005E43C )
  {
    dword_18005E43C = 0;
    if ( !RpcServerInqBindings(&BindingVector) )
    {
      RpcEpUnregister(qword_18004D420, BindingVector, 0);
      RpcBindingVectorFree(&BindingVector);
    }
    v0 = RpcServerUnregisterIf(qword_18004D420, 0, 1u);
    if ( v0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids, v0);
    }
  }
  RtlReleaseResource(&stru_18005E3D8);
  if ( dword_18005E4AC == 1 )
  {
    EnterCriticalSection(&SpoolerMutex);
    pSpoolerOpenPrinterFunction = 0;
    pSpoolerResetPrinterFunction = 0;
    pSpoolerAddJobFunction = 0;
    pSpoolerScheduleJobFunction = 0;
    pSpoolerClosePrinterFunction = 0;
    if ( hSpoolerLibrary )
    {
      FreeLibrary(hSpoolerLibrary);
      hSpoolerLibrary = 0;
    }
    LeaveCriticalSection(&SpoolerMutex);
    DeleteCriticalSection(&SpoolerMutex);
    dword_18005E4AC = 0;
  }
}

```

## disassembly

```asm
0x18003003c  sub     rsp, 28h
0x180030040  mov     dl, 1; Wait
0x180030042  mov     [rsp+28h+BindingVector], 0
0x18003004b  lea     rcx, stru_18005E3D8; Resource
0x180030052  call    cs:__imp_RtlAcquireResourceExclusive
0x180030058  cmp     cs:dword_18005E43C, 0
0x18003005f  jz      loc_1800300EC
0x180030065  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x18003006a  mov     cs:dword_18005E43C, 0
0x180030074  call    cs:__imp_RpcServerInqBindings
0x18003007a  test    eax, eax
0x18003007c  jnz     short loc_18003009E
0x18003007e  mov     rdx, [rsp+28h+BindingVector]; BindingVector
0x180030083  lea     rcx, qword_18004D420; IfSpec
0x18003008a  xor     r8d, r8d; UuidVector
0x18003008d  call    cs:__imp_RpcEpUnregister
0x180030093  lea     rcx, [rsp+28h+BindingVector]; BindingVector
0x180030098  call    cs:__imp_RpcBindingVectorFree
0x18003009e  xor     edx, edx; MgrTypeUuid
0x1800300a0  lea     rcx, qword_18004D420; IfSpec
0x1800300a7  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x1800300ab  call    cs:__imp_RpcServerUnregisterIf
0x1800300b1  test    eax, eax
0x1800300b3  jz      short loc_1800300EC
0x1800300b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800300bc  lea     rdx, WPP_GLOBAL_Control
0x1800300c3  cmp     rcx, rdx
0x1800300c6  jz      short loc_1800300EC
0x1800300c8  test    byte ptr [rcx+1Ch], 10h
0x1800300cc  jz      short loc_1800300EC
0x1800300ce  cmp     byte ptr [rcx+19h], 1
0x1800300d2  jb      short loc_1800300EC
0x1800300d4  mov     rcx, [rcx+10h]
0x1800300d8  lea     r8, WPP_e398f63900a3398cb4ea66f5424edfa1_Traceguids
0x1800300df  mov     edx, 1Dh
0x1800300e4  mov     r9d, eax
0x1800300e7  call    WPP_SF_d
0x1800300ec  lea     rcx, stru_18005E3D8; Resource
0x1800300f3  call    cs:__imp_RtlReleaseResource
0x1800300f9  cmp     cs:dword_18005E4AC, 1
0x180030100  jnz     loc_18003018B
0x180030106  lea     rcx, SpoolerMutex; lpCriticalSection
0x18003010d  call    cs:__imp_EnterCriticalSection
0x180030113  mov     rcx, cs:hSpoolerLibrary; hLibModule
0x18003011a  mov     cs:pSpoolerOpenPrinterFunction, 0
0x180030125  mov     cs:pSpoolerResetPrinterFunction, 0
0x180030130  mov     cs:pSpoolerAddJobFunction, 0
0x18003013b  mov     cs:pSpoolerScheduleJobFunction, 0
0x180030146  mov     cs:pSpoolerClosePrinterFunction, 0
0x180030151  test    rcx, rcx
0x180030154  jz      short loc_180030167
0x180030156  call    cs:__imp_FreeLibrary
0x18003015c  mov     cs:hSpoolerLibrary, 0
0x180030167  lea     rcx, SpoolerMutex; lpCriticalSection
0x18003016e  call    cs:__imp_LeaveCriticalSection
0x180030174  lea     rcx, SpoolerMutex; lpCriticalSection
0x18003017b  call    cs:__imp_DeleteCriticalSection
0x180030181  mov     cs:dword_18005E4AC, 0
0x18003018b  add     rsp, 28h
0x18003018f  retn
```
