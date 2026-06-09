# HTTP2IISSenderTransportChannel::ReceiveCompleteInternal(long,tagHTTP2TrafficType,int,uchar * *,uint *)

- ea: `0x180016800`
- end: `0x180016892`
- name: `?ReceiveCompleteInternal@HTTP2IISSenderTransportChannel@@MEAAJJW4tagHTTP2TrafficType@@HPEAPEAEPEAI@Z`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180013630`
- `0x180016800`
- `0x1800190d0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18001683b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001683b`
- `ntdll!RtlEnterCriticalSection` at `0x180016823`
- `ntdll!RtlEnterCriticalSection` at `0x180016823`

## pseudocode

```c
__int64 __fastcall HTTP2IISSenderTransportChannel::ReceiveCompleteInternal(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        _QWORD *a5,
        unsigned int *a6)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  unsigned int v11; // ebp
  __int64 result; // rax
  signed __int32 v13[8]; // [rsp+0h] [rbp-68h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 128);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 128));
  if ( a4 )
    --*(_DWORD *)(a1 + 88);
  _InterlockedOr(v13, 0);
  v11 = *(_DWORD *)(a1 + 120);
  RtlLeaveCriticalSection(v6);
  result = HTTP2FragmentReceiver::ReceiveComplete((__int64 *)a1, a2, a3, a5, a6);
  if ( (_DWORD)result == -1073606615 || !(_DWORD)result && *a5 )
    return HTTP2IISSenderTransportChannel::SendQueuedContextIfNecessary(
             (HTTP2IISSenderTransportChannel *)a1,
             v11,
             result);
  return result;
}

```

## disassembly

```asm
0x180016800  push    rbx
0x180016802  push    rbp
0x180016803  push    rsi
0x180016804  push    rdi
0x180016805  push    r14
0x180016807  push    r15
0x180016809  sub     rsp, 38h
0x18001680d  lea     rsi, [rcx+80h]
0x180016814  mov     rdi, rcx
0x180016817  mov     rcx, rsi; CriticalSection
0x18001681a  mov     ebx, r9d
0x18001681d  mov     r14d, r8d
0x180016820  mov     r15d, edx
0x180016823  call    cs:__imp_RtlEnterCriticalSection
0x180016829  test    ebx, ebx
0x18001682b  jz      short loc_180016830
0x18001682d  dec     dword ptr [rdi+58h]
0x180016830  lock or [rsp+68h+var_68], 0
0x180016835  mov     ebp, [rdi+78h]
0x180016838  mov     rcx, rsi; CriticalSection
0x18001683b  call    cs:__imp_RtlLeaveCriticalSection
0x180016841  mov     rax, [rsp+68h+arg_28]
0x180016849  mov     r8d, r14d
0x18001684c  mov     rbx, [rsp+68h+arg_20]
0x180016854  mov     edx, r15d
0x180016857  mov     r9, rbx
0x18001685a  mov     [rsp+68h+var_48], rax
0x18001685f  mov     rcx, rdi
0x180016862  call    ?ReceiveComplete@HTTP2FragmentReceiver@@UEAAJJW4tagHTTP2TrafficType@@PEAPEAEPEAI@Z; HTTP2FragmentReceiver::ReceiveComplete(long,tagHTTP2TrafficType,uchar * *,uint *)
0x180016867  cmp     eax, 0C0021029h
0x18001686c  jz      short loc_180016878
0x18001686e  test    eax, eax
0x180016870  jnz     short loc_180016885
0x180016872  cmp     qword ptr [rbx], 0
0x180016876  jz      short loc_180016885
0x180016878  mov     r8d, eax; int
0x18001687b  mov     edx, ebp; unsigned int
0x18001687d  mov     rcx, rdi; this
0x180016880  call    ?SendQueuedContextIfNecessary@HTTP2IISSenderTransportChannel@@AEAAJKJ@Z; HTTP2IISSenderTransportChannel::SendQueuedContextIfNecessary(ulong,long)
0x180016885  add     rsp, 38h
0x180016889  pop     r15
0x18001688b  pop     r14
0x18001688d  pop     rdi
0x18001688e  pop     rsi
0x18001688f  pop     rbp
0x180016890  pop     rbx
0x180016891  retn
```
