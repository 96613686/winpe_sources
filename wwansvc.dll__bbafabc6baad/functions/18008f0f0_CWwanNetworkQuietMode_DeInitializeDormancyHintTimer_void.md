# CWwanNetworkQuietMode::DeInitializeDormancyHintTimer(void)

- ea: `0x18008f0f0`
- end: `0x18008f19b`
- name: `?DeInitializeDormancyHintTimer@CWwanNetworkQuietMode@@AEAAXXZ`
- size: `171`
- prototype: `void __fastcall(CWwanNetworkQuietMode *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18008f0b4`

## callees

- `0x180014f1c`
- `0x18008f0f0`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x18008f130`
- `MobileNetworking!StopTimer` at `0x18008f130`
- `MobileNetworking!DeleteReadWriteLock` at `0x18008f174`
- `MobileNetworking!DeleteReadWriteLock` at `0x18008f174`
- `MobileNetworking!AcquireWriteLock` at `0x18008f123`
- `MobileNetworking!AcquireWriteLock` at `0x18008f123`
- `MobileNetworking!ReleaseWriteLock` at `0x18008f146`
- `MobileNetworking!ReleaseWriteLock` at `0x18008f146`
- `MobileNetworking!DeleteTimer` at `0x18008f16b`
- `MobileNetworking!DeleteTimer` at `0x18008f16b`

## string_xrefs

- `0x18008f14c`: `Timer Stop Completed`
- `0x18008f17a`: `Timer Deinitialization Completed`

## pseudocode

```c
void __fastcall CWwanNetworkQuietMode::DeInitializeDormancyHintTimer(CWwanNetworkQuietMode *this)
{
  char *v1; // rdi
  __int64 v3; // rcx

  v1 = (char *)this + 16;
  if ( *((_DWORD *)this + 32) )
  {
    AcquireWriteLock(*((_QWORD *)this + 15), v1, "CWwanNetworkQuietMode::DeInitializeDormancyHintTimer", 116);
    StopTimer(*((_QWORD *)this + 15), "CWwanNetworkQuietMode::DeInitializeDormancyHintTimer");
    ReleaseWriteLock(*((_QWORD *)this + 15), v1, "CWwanNetworkQuietMode::DeInitializeDormancyHintTimer", 118);
    WwanLog::Info("CWwanNetworkQuietMode::DeInitializeDormancyHintTimer", 0, L"Timer Stop Completed");
    v3 = *((_QWORD *)this + 15);
    *((_DWORD *)this + 32) = 0;
    DeleteTimer(v3);
    DeleteReadWriteLock(v1);
    WwanLog::Info("CWwanNetworkQuietMode::DeInitializeDormancyHintTimer", 0, L"Timer Deinitialization Completed");
  }
}

```

## disassembly

```asm
0x18008f0f0  mov     [rsp+arg_0], rbx
0x18008f0f5  mov     [rsp+arg_8], rsi
0x18008f0fa  push    rdi
0x18008f0fb  sub     rsp, 20h
0x18008f0ff  lea     rdi, [rcx+10h]
0x18008f103  mov     rbx, rcx
0x18008f106  cmp     dword ptr [rdi+70h], 0
0x18008f10a  jz      short loc_18008F18B
0x18008f10c  mov     rcx, [rcx+78h]
0x18008f110  lea     rsi, aCwwannetworkqu_1; "CWwanNetworkQuietMode::DeInitializeDorm"...
0x18008f117  mov     r8, rsi
0x18008f11a  mov     r9d, 74h ; 't'
0x18008f120  mov     rdx, rdi
0x18008f123  call    cs:__imp_AcquireWriteLock
0x18008f129  mov     rcx, [rbx+78h]
0x18008f12d  mov     rdx, rsi
0x18008f130  call    cs:__imp_StopTimer
0x18008f136  mov     rcx, [rbx+78h]
0x18008f13a  mov     r9d, 76h ; 'v'
0x18008f140  mov     r8, rsi
0x18008f143  mov     rdx, rdi
0x18008f146  call    cs:__imp_ReleaseWriteLock
0x18008f14c  lea     r8, aTimerStopCompl; "Timer Stop Completed"
0x18008f153  xor     edx, edx; struct _GUID *
0x18008f155  mov     rcx, rsi; char *
0x18008f158  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008f15d  mov     rcx, [rbx+78h]
0x18008f161  mov     dword ptr [rbx+80h], 0
0x18008f16b  call    cs:__imp_DeleteTimer
0x18008f171  mov     rcx, rdi
0x18008f174  call    cs:__imp_DeleteReadWriteLock
0x18008f17a  lea     r8, aTimerDeinitial_0; "Timer Deinitialization Completed"
0x18008f181  xor     edx, edx; struct _GUID *
0x18008f183  mov     rcx, rsi; char *
0x18008f186  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008f18b  mov     rbx, [rsp+28h+arg_0]
0x18008f190  mov     rsi, [rsp+28h+arg_8]
0x18008f195  add     rsp, 20h
0x18008f199  pop     rdi
0x18008f19a  retn
```
