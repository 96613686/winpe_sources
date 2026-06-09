# _hardwareMonitorThreadRoutine

- ea: `0x180045d10`
- end: `0x180045eca`
- name: `_hardwareMonitorThreadRoutine`
- size: `442`
- prototype: `static int(struct thread_inside_functions *, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800133ec`
- `0x18001358c`
- `0x1800168cc`
- `0x180016b64`
- `0x18001aef8`
- `0x18001b920`
- `0x18001be18`
- `0x18002fa34`
- `0x1800305f4`
- `0x180039a8c`
- `0x180041c14`
- `0x180045d10`
- `0x1800624d4`
- `0x180069330`
- `0x180072628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045e9d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180045e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045d71`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180045d67`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180045d67`

## pseudocode

```c
__int64 __fastcall hardwareMonitorThreadRoutine(struct thread_inside_functions *a1, RTL_SRWLOCK *a2)
{
  PVOID Ptr; // rcx
  CPlugInManager *v5; // rax
  const unsigned __int16 *v6; // rdx
  struct _WINBIO_SENSOR_INTERFACE *v7; // r8
  CDatabaseManager *v8; // rax
  HANDLE *InternalHigh; // rcx
  _QWORD v11[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp+28h] BYREF
  int v13; // [rsp+78h] [rbp+30h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+80h] [rbp+38h] BYREF
  unsigned __int64 CompletionKey; // [rsp+88h] [rbp+40h] BYREF

  while ( _InterlockedCompareExchange((volatile signed __int32 *)a1 + 26, 2, 2) == 2 )
  {
    Ptr = a2[6].Ptr;
    Overlapped = 0;
    NumberOfBytesTransferred = 0;
    CompletionKey = 0;
    if ( GetQueuedCompletionStatus(Ptr, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
    {
      if ( !Overlapped )
        return 0;
      if ( (unsigned int)dword_18010F170 > 4 )
      {
        v11[0] = SLODWORD(Overlapped->Internal);
        v13 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (__int64)&dword_18010F170,
          (unsigned __int8 *)&word_1800EC68E,
          0,
          0,
          (__int64)&v13,
          (__int64)v11);
      }
      switch ( LODWORD(Overlapped->Internal) )
      {
        case 1:
          CHardwareManager::ScanHardware((CHardwareManager *)a2, 0, 0, 0);
          InternalHigh = (HANDLE *)Overlapped->InternalHigh;
          if ( InternalHigh )
            SetEvent(*InternalHigh);
          break;
        case 2:
          v5 = CPlugInManager::Instance();
          CPlugInManager::RegisterAll(v5, v6, v7);
          v8 = CDatabaseManager::Instance();
          CDatabaseManager::RegisterAll(v8);
          CHardwareManager::ScanHardware((CHardwareManager *)a2, 0, 0, 1);
          if ( CHardwareManager::CountLogonCapableSystemPoolUnits((CHardwareManager *)a2) )
            WbioSetServiceStartupPolicy();
          break;
        case 3:
          CHardwareManager::RemoveSensorByPath(
            (CHardwareManager *)a2,
            (unsigned __int16 *)&Overlapped->InternalHigh,
            (unsigned __int64)Overlapped[12].hEvent);
          break;
        case 4:
          CHardwareManager::RemoveSensorByPointer(
            (CHardwareManager *)Overlapped,
            (struct CBiometricUnit *)Overlapped->InternalHigh);
          break;
        case 5:
          CHardwareManager::RemoveSensorByHandle((CHardwareManager *)Overlapped, (void *)Overlapped->InternalHigh);
          break;
        case 6:
          CHardwareManager::OnPowerStatusChange((CHardwareManager *)a2);
          break;
      }
      operator delete(Overlapped, 0x1A0u);
      CHardwareManager::WriteAvailableBiometricUnitsToCache(a2);
    }
    else
    {
      GetLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180045d10  push    rbp
0x180045d12  push    rbx
0x180045d13  push    rdi
0x180045d14  push    r14
0x180045d16  mov     rbp, rsp
0x180045d19  sub     rsp, 48h
0x180045d1d  mov     rbx, rdx
0x180045d20  mov     rdi, rcx
0x180045d23  mov     r14d, 2
0x180045d29  mov     eax, r14d
0x180045d2c  lock cmpxchg [rdi+68h], r14d
0x180045d32  jnz     loc_180045EBE
0x180045d38  mov     rcx, [rbx+30h]; CompletionPort
0x180045d3c  lea     r9, [rbp+Overlapped]; lpOverlapped
0x180045d40  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x180045d44  mov     [rbp+Overlapped], 0
0x180045d4c  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180045d50  mov     [rbp+NumberOfBytesTransferred], 0
0x180045d57  mov     [rbp+CompletionKey], 0
0x180045d5f  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180045d67  call    cs:__imp_GetQueuedCompletionStatus
0x180045d6d  test    eax, eax
0x180045d6f  jnz     short loc_180045D79
0x180045d71  call    cs:__imp_GetLastError
0x180045d77  jmp     short loc_180045D29
0x180045d79  cmp     [rbp+Overlapped], 0
0x180045d7e  jz      loc_180045EBE
0x180045d84  mov     eax, cs:dword_18010F170
0x180045d8a  cmp     eax, 4
0x180045d8d  jbe     short loc_180045DCC
0x180045d8f  mov     rax, [rbp+Overlapped]
0x180045d93  lea     rdx, word_1800EC68E
0x180045d9a  xor     r9d, r9d
0x180045d9d  xor     r8d, r8d
0x180045da0  movsxd  rcx, dword ptr [rax]
0x180045da3  lea     rax, [rbp+var_18]
0x180045da7  mov     [rsp+48h+var_20], rax
0x180045dac  lea     rax, [rbp+arg_8]
0x180045db0  mov     [rbp+var_18], rcx
0x180045db4  lea     rcx, dword_18010F170
0x180045dbb  mov     qword ptr [rsp+48h+dwMilliseconds], rax
0x180045dc0  mov     [rbp+arg_8], 0
0x180045dc7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180045dcc  mov     rcx, [rbp+Overlapped]; this
0x180045dd0  mov     edx, [rcx]
0x180045dd2  sub     edx, 1
0x180045dd5  jz      loc_180045E7D
0x180045ddb  sub     edx, 1
0x180045dde  jz      short loc_180045E3F
0x180045de0  sub     edx, 1
0x180045de3  jz      short loc_180045E26
0x180045de5  sub     edx, 1
0x180045de8  jz      short loc_180045E17
0x180045dea  sub     edx, 1
0x180045ded  jz      short loc_180045E05
0x180045def  cmp     edx, 1
0x180045df2  jnz     loc_180045EA3
0x180045df8  mov     rcx, rbx; this
0x180045dfb  call    ?OnPowerStatusChange@CHardwareManager@@AEAAXXZ; CHardwareManager::OnPowerStatusChange(void)
0x180045e00  jmp     loc_180045EA3
0x180045e05  mov     rdx, [rbp+Overlapped]
0x180045e09  mov     rdx, [rdx+8]; void *
0x180045e0d  call    ?RemoveSensorByHandle@CHardwareManager@@AEAAXPEAX@Z; CHardwareManager::RemoveSensorByHandle(void *)
0x180045e12  jmp     loc_180045EA3
0x180045e17  mov     rdx, [rbp+Overlapped]
0x180045e1b  mov     rdx, [rdx+8]; struct CBiometricUnit *
0x180045e1f  call    ?RemoveSensorByPointer@CHardwareManager@@AEAAXPEAVCBiometricUnit@@@Z; CHardwareManager::RemoveSensorByPointer(CBiometricUnit *)
0x180045e24  jmp     short loc_180045EA3
0x180045e26  mov     rdx, [rbp+Overlapped]
0x180045e2a  mov     rcx, rbx; this
0x180045e2d  add     rdx, 8; unsigned __int16 *
0x180045e31  mov     r8, [rdx+190h]; unsigned __int64
0x180045e38  call    ?RemoveSensorByPath@CHardwareManager@@AEAAXPEAG_K@Z; CHardwareManager::RemoveSensorByPath(ushort *,unsigned __int64)
0x180045e3d  jmp     short loc_180045EA3
0x180045e3f  call    ?Instance@CPlugInManager@@SAAEAV1@XZ; CPlugInManager::Instance(void)
0x180045e44  mov     rcx, rax; this
0x180045e47  call    ?RegisterAll@CPlugInManager@@QEAAJXZ; CPlugInManager::RegisterAll(void)
0x180045e4c  call    ?Instance@CDatabaseManager@@SAAEAV1@XZ; CDatabaseManager::Instance(void)
0x180045e51  mov     rcx, rax; this
0x180045e54  call    ?RegisterAll@CDatabaseManager@@QEAAJXZ; CDatabaseManager::RegisterAll(void)
0x180045e59  mov     r9b, 1; bool
0x180045e5c  xor     r8d, r8d; unsigned __int64
0x180045e5f  xor     edx, edx; unsigned __int16 *
0x180045e61  mov     rcx, rbx; this
0x180045e64  call    ?ScanHardware@CHardwareManager@@AEAAJPEAG_K_N@Z; CHardwareManager::ScanHardware(ushort *,unsigned __int64,bool)
0x180045e69  mov     rcx, rbx; this
0x180045e6c  call    ?CountLogonCapableSystemPoolUnits@CHardwareManager@@QEAA_KXZ; CHardwareManager::CountLogonCapableSystemPoolUnits(void)
0x180045e71  test    rax, rax
0x180045e74  jz      short loc_180045EA3
0x180045e76  call    WbioSetServiceStartupPolicy
0x180045e7b  jmp     short loc_180045EA3
0x180045e7d  xor     r9d, r9d; bool
0x180045e80  xor     r8d, r8d; unsigned __int64
0x180045e83  xor     edx, edx; unsigned __int16 *
0x180045e85  mov     rcx, rbx; this
0x180045e88  call    ?ScanHardware@CHardwareManager@@AEAAJPEAG_K_N@Z; CHardwareManager::ScanHardware(ushort *,unsigned __int64,bool)
0x180045e8d  mov     rax, [rbp+Overlapped]
0x180045e91  mov     rcx, [rax+8]
0x180045e95  test    rcx, rcx
0x180045e98  jz      short loc_180045EA3
0x180045e9a  mov     rcx, [rcx]; hEvent
0x180045e9d  call    cs:__imp_SetEvent
0x180045ea3  mov     rcx, [rbp+Overlapped]; void *
0x180045ea7  mov     edx, 1A0h; unsigned __int64
0x180045eac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180045eb1  mov     rcx, rbx; this
0x180045eb4  call    ?WriteAvailableBiometricUnitsToCache@CHardwareManager@@QEBAJXZ; CHardwareManager::WriteAvailableBiometricUnitsToCache(void)
0x180045eb9  jmp     loc_180045D29
0x180045ebe  xor     eax, eax
0x180045ec0  add     rsp, 48h
0x180045ec4  pop     r14
0x180045ec6  pop     rdi
0x180045ec7  pop     rbx
0x180045ec8  pop     rbp
0x180045ec9  retn
```
