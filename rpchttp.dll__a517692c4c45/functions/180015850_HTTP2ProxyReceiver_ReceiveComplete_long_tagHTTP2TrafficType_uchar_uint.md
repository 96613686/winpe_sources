# HTTP2ProxyReceiver::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)

- ea: `0x180015850`
- end: `0x1800158d7`
- name: `?ReceiveComplete@HTTP2ProxyReceiver@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800056b8`
- `0x180015850`
- `0x1800167d0`
- `0x180025010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180015896`
- `ntdll!RtlLeaveCriticalSection` at `0x180015896`
- `ntdll!RtlEnterCriticalSection` at `0x18001587f`
- `ntdll!RtlEnterCriticalSection` at `0x18001587f`

## pseudocode

```c
__int64 __fastcall HTTP2ProxyReceiver::ReceiveComplete(__int64 a1, int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  int v7; // esi

  if ( !a2 && *(_BYTE *)(a4 + 2) != 20 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 112));
    v7 = HTTP2GenericReceiver::BytesReceivedNotification((HTTP2GenericReceiver *)a1, a5);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 112));
    if ( v7 )
      (*((void (__fastcall **)(__int64))pRuntimeImportTable + 1))(a4);
  }
  return HTTP2TransportChannel::ReceiveComplete(a1);
}

```

## disassembly

```asm
0x180015850  push    rbx
0x180015852  push    rbp
0x180015853  push    rsi
0x180015854  push    rdi
0x180015855  push    r14
0x180015857  push    r15
0x180015859  sub     rsp, 38h
0x18001585d  mov     r14d, [rsp+68h+arg_20]
0x180015865  mov     rdi, r9
0x180015868  mov     r15d, r8d
0x18001586b  mov     esi, edx
0x18001586d  mov     rbp, rcx
0x180015870  test    edx, edx
0x180015872  jnz     short loc_1800158B3
0x180015874  cmp     byte ptr [r9+2], 14h
0x180015879  jz      short loc_1800158B3
0x18001587b  add     rcx, 70h ; 'p'; CriticalSection
0x18001587f  call    cs:__imp_RtlEnterCriticalSection
0x180015885  mov     edx, r14d; unsigned int
0x180015888  mov     rcx, rbp; this
0x18001588b  call    ?BytesReceivedNotification@HTTP2GenericReceiver@@QEAAJK@Z; HTTP2GenericReceiver::BytesReceivedNotification(ulong)
0x180015890  lea     rcx, [rbp+70h]; CriticalSection
0x180015894  mov     esi, eax
0x180015896  call    cs:__imp_RtlLeaveCriticalSection
0x18001589c  test    esi, esi
0x18001589e  jz      short loc_1800158B3
0x1800158a0  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800158a7  mov     rcx, rdi
0x1800158aa  mov     rax, [rax+8]
0x1800158ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158b3  mov     r9, rdi
0x1800158b6  mov     [rsp+68h+arg_20], r14d
0x1800158be  mov     r8d, r15d
0x1800158c1  mov     edx, esi
0x1800158c3  mov     rcx, rbp
0x1800158c6  add     rsp, 38h
0x1800158ca  pop     r15
0x1800158cc  pop     r14
0x1800158ce  pop     rdi
0x1800158cf  pop     rsi
0x1800158d0  pop     rbp
0x1800158d1  pop     rbx
0x1800158d2  jmp     ?ReceiveComplete@HTTP2TransportChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z; HTTP2TransportChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)
```
