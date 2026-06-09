# ResourceManagerImpl::UnsubscribeFromIdleStateChangeWnfEvent(void)

- ea: `0x1800a2630`
- end: `0x1800a2691`
- name: `?UnsubscribeFromIdleStateChangeWnfEvent@ResourceManagerImpl@@UEAAJXZ`
- size: `97`
- prototype: `__int64 __fastcall(ResourceManagerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007d74c`

## callees

- `0x1800a2630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a2647`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a2647`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a267e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a267e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800a2656`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800a266d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800a2656`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800a266d`

## pseudocode

```c
__int64 __fastcall ResourceManagerImpl::UnsubscribeFromIdleStateChangeWnfEvent(ResourceManagerImpl *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(v3);
    *((_QWORD *)this + 14) = 0;
  }
  v4 = *((_QWORD *)this + 15);
  if ( v4 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion(v4);
    *((_QWORD *)this + 15) = 0;
  }
  LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x1800a2630  mov     [rsp+arg_0], rbx
0x1800a2635  push    rdi
0x1800a2636  sub     rsp, 20h
0x1800a263a  lea     rdi, [rcx+80h]
0x1800a2641  mov     rbx, rcx
0x1800a2644  mov     rcx, rdi; lpCriticalSection
0x1800a2647  call    cs:__imp_EnterCriticalSection
0x1800a264d  mov     rcx, [rbx+70h]
0x1800a2651  test    rcx, rcx
0x1800a2654  jz      short loc_1800A2664
0x1800a2656  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800a265c  mov     qword ptr [rbx+70h], 0
0x1800a2664  mov     rcx, [rbx+78h]
0x1800a2668  test    rcx, rcx
0x1800a266b  jz      short loc_1800A267B
0x1800a266d  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800a2673  mov     qword ptr [rbx+78h], 0
0x1800a267b  mov     rcx, rdi; lpCriticalSection
0x1800a267e  call    cs:__imp_LeaveCriticalSection
0x1800a2684  mov     rbx, [rsp+28h+arg_0]
0x1800a2689  xor     eax, eax
0x1800a268b  add     rsp, 20h
0x1800a268f  pop     rdi
0x1800a2690  retn
```
