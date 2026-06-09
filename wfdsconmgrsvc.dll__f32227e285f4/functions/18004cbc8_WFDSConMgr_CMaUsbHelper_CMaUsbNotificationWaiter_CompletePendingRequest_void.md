# WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::CompletePendingRequest(void)

- ea: `0x18004cbc8`
- end: `0x18004cc89`
- name: `?CompletePendingRequest@CMaUsbNotificationWaiter@CMaUsbHelper@WFDSConMgr@@AEAAXXZ`
- size: `193`
- prototype: `void __fastcall(WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004e2b0`

## callees

- `0x1800059c0`
- `0x18002f5f0`
- `0x18004cbc8`
- `0x18005c888`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cc73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cc73`

## string_xrefs

- `0x18004cc1b`: `MA-USB PostNotificationRequestCompleteAsync failed`
- `0x18004cc3b`: `WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::CompletePendingRequest`

## pseudocode

```c
void __fastcall WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::CompletePendingRequest(
        WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter *this)
{
  int v2; // edi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp+8h] BYREF

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**(_QWORD **)(*((_QWORD *)this + 28) + 48LL) + 88LL))(
         *(_QWORD *)(*((_QWORD *)this + 28) + 48LL),
         *((_QWORD *)this + 29),
         (char *)this + 168);
  std::shared_ptr<WFDSConMgr::CWFDClientHandle>::reset((char *)this + 232);
  if ( v2 )
    WFDSConMgr::CException::Throw(
      v2,
      "WFDSConMgr::CMaUsbHelper::CMaUsbNotificationWaiter::CompletePendingRequest",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\mausbhelper.cpp",
      93,
      L"MA-USB PostNotificationRequestCompleteAsync failed",
      this);
  WFDSConMgr::CriticalSection::Lock((char *)this + 112, &lpCriticalSection);
  if ( *((_DWORD *)this + 38) == 1 )
    *((_DWORD *)this + 38) = 2;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18004cbc8  mov     [rsp+arg_8], rbx
0x18004cbcd  mov     [rsp+arg_10], rsi
0x18004cbd2  push    rdi
0x18004cbd3  sub     rsp, 30h
0x18004cbd7  mov     rax, [rcx+0E0h]
0x18004cbde  mov     rsi, rcx
0x18004cbe1  mov     rcx, [rax+30h]
0x18004cbe5  lea     rbx, [rsi+0E8h]
0x18004cbec  mov     rdx, [rbx]
0x18004cbef  lea     r8, [rsi+0A8h]
0x18004cbf6  mov     rax, [rcx]
0x18004cbf9  mov     rax, [rax+58h]
0x18004cbfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc02  mov     rcx, rbx
0x18004cc05  mov     edi, eax
0x18004cc07  call    ?reset@?$shared_ptr@VCWFDClientHandle@WFDSConMgr@@@std@@QEAAXXZ; std::shared_ptr<WFDSConMgr::CWFDClientHandle>::reset(void)
0x18004cc0c  test    edi, edi
0x18004cc0e  jz      short loc_18004CC48
0x18004cc10  jle     short loc_18004CC1B
0x18004cc12  movzx   edi, di
0x18004cc15  or      edi, 80070000h
0x18004cc1b  lea     rax, aMaUsbPostnotif; "MA-USB PostNotificationRequestCompleteA"...
0x18004cc22  mov     [rsp+38h+var_10], rsi; void *
0x18004cc27  mov     r9d, 55Dh; char
0x18004cc2d  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18004cc32  lea     r8, aOnecoreuapNetW_16; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004cc39  mov     ecx, edi; char
0x18004cc3b  lea     rdx, aWfdsconmgrCmau_2; "WFDSConMgr::CMaUsbHelper::CMaUsbNotific"...
0x18004cc42  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004cc48  lea     rcx, [rsi+70h]
0x18004cc4c  lea     rdx, [rsp+38h+lpCriticalSection]
0x18004cc51  call    ?Lock@CriticalSection@WFDSConMgr@@QEAA?AVSyncLock@12@XZ; WFDSConMgr::CriticalSection::Lock(void)
0x18004cc56  cmp     dword ptr [rsi+98h], 1
0x18004cc5d  jnz     short loc_18004CC69
0x18004cc5f  mov     dword ptr [rsi+98h], 2
0x18004cc69  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x18004cc6e  test    rcx, rcx
0x18004cc71  jz      short loc_18004CC79
0x18004cc73  call    cs:__imp_LeaveCriticalSection
0x18004cc79  mov     rbx, [rsp+38h+arg_8]
0x18004cc7e  mov     rsi, [rsp+38h+arg_10]
0x18004cc83  add     rsp, 30h
0x18004cc87  pop     rdi
0x18004cc88  retn
```
