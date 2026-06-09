# PnPServices::UnregisterForInterfaceEvents(_GUID const *,PnPServices::IPnPInterfaceEventCB *)

- ea: `0x180025980`
- end: `0x180025a12`
- name: `?UnregisterForInterfaceEvents@PnPServices@@YAJPEBU_GUID@@PEAVIPnPInterfaceEventCB@1@@Z`
- size: `146`
- prototype: `int(PnPServices *__hidden this, const struct _GUID *, struct PnPServices::IPnPInterfaceEventCB *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x180027230`

## callees

- `0x180003570`
- `0x18002471c`
- `0x1800249f0`
- `0x1800257fc`
- `0x180025980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800259a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800259a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800259fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800259fa`

## pseudocode

```c
__int64 __fastcall PnPServices::UnregisterForInterfaceEvents(
        PnPServices *this,
        struct _GUID *a2,
        struct PnPServices::IPnPInterfaceEventCB *a3)
{
  __int64 v5; // rcx
  int v6; // ebx
  CRefCounted *v7; // rcx
  int v9; // [rsp+40h] [rbp+18h] BYREF
  CRefCounted *v10; // [rsp+48h] [rbp+20h] BYREF

  v10 = 0;
  EnterCriticalSection(&stru_18003E470);
  v6 = CNamedElemList<PnPServices::CInterfaceNotif>::Get<_GUID const *>(v5, this, &v10);
  if ( v6 >= 0 )
  {
    v9 = 0;
    v6 = PnPServices::CInterfaceNotifBase::RemoveCallback(
           (HDPA *)v10,
           (struct PnPServices::IPnPInterfaceEventCB *)a2,
           &v9);
    if ( v9 )
      CNamedElemList<PnPServices::CInterfaceNotif>::Remove<_GUID const *>(v7, this);
    CRefCounted::Release(v10);
  }
  LeaveCriticalSection(&stru_18003E470);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180025980  mov     [rsp+arg_0], rbx
0x180025985  mov     [rsp+arg_8], rsi
0x18002598a  push    rdi
0x18002598b  sub     rsp, 20h
0x18002598f  mov     rdi, rcx
0x180025992  mov     [rsp+28h+arg_18], 0
0x18002599b  lea     rcx, stru_18003E470; lpCriticalSection
0x1800259a2  mov     rsi, rdx
0x1800259a5  call    cs:__imp_EnterCriticalSection
0x1800259ab  lea     r8, [rsp+28h+arg_18]
0x1800259b0  mov     rdx, rdi
0x1800259b3  call    ??$Get@PEBU_GUID@@@?$CNamedElemList@VCInterfaceNotif@PnPServices@@@@QEAAJQEBU_GUID@@PEAPEAVCInterfaceNotif@PnPServices@@@Z; CNamedElemList<PnPServices::CInterfaceNotif>::Get<_GUID const *>(_GUID const * const,PnPServices::CInterfaceNotif * *)
0x1800259b8  mov     ebx, eax
0x1800259ba  test    eax, eax
0x1800259bc  js      short loc_1800259F3
0x1800259be  mov     rcx, [rsp+28h+arg_18]; this
0x1800259c3  lea     r8, [rsp+28h+arg_10]; int *
0x1800259c8  mov     rdx, rsi; struct PnPServices::IPnPInterfaceEventCB *
0x1800259cb  mov     [rsp+28h+arg_10], 0
0x1800259d3  call    ?RemoveCallback@CInterfaceNotifBase@PnPServices@@QEAAJPEAVIPnPInterfaceEventCB@2@PEAH@Z; PnPServices::CInterfaceNotifBase::RemoveCallback(PnPServices::IPnPInterfaceEventCB *,int *)
0x1800259d8  cmp     [rsp+28h+arg_10], 0
0x1800259dd  mov     ebx, eax
0x1800259df  jz      short loc_1800259E9
0x1800259e1  mov     rdx, rdi
0x1800259e4  call    ??$Remove@PEBU_GUID@@@?$CNamedElemList@VCInterfaceNotif@PnPServices@@@@QEAAJQEBU_GUID@@@Z; CNamedElemList<PnPServices::CInterfaceNotif>::Remove<_GUID const *>(_GUID const * const)
0x1800259e9  mov     rcx, [rsp+28h+arg_18]; this
0x1800259ee  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800259f3  lea     rcx, stru_18003E470; lpCriticalSection
0x1800259fa  call    cs:__imp_LeaveCriticalSection
0x180025a00  mov     rsi, [rsp+28h+arg_8]
0x180025a05  mov     eax, ebx
0x180025a07  mov     rbx, [rsp+28h+arg_0]
0x180025a0c  add     rsp, 20h
0x180025a10  pop     rdi
0x180025a11  retn
```
