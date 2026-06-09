# HTTP2PingReceiver::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)

- ea: `0x180015790`
- end: `0x180015846`
- name: `?ReceiveComplete@HTTP2PingReceiver@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z`
- size: `182`
- prototype: `int __high(int, enum tagHTTP2TrafficType, unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800054b8`
- `0x180009d58`
- `0x180011c70`
- `0x180015790`
- `0x1800167d0`
- `0x180016df8`
- `0x18001ca44`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2PingReceiver::ReceiveComplete(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  unsigned __int8 *v5; // rbx
  unsigned int v7; // edi

  v5 = a4;
  v7 = a2;
  if ( a2 || a4[2] != 20 || !(unsigned int)UntrustedIsPingPacket(a4, a5) )
    return HTTP2TransportChannel::ReceiveComplete(a1, v7, a3, v5, a5);
  v7 = HTTP2Channel::BeginSubmitAsync(*(HTTP2Channel **)(a1 + 24));
  if ( v7 )
  {
LABEL_7:
    (*((void (__fastcall **)(unsigned __int8 *))pRuntimeImportTable + 1))(v5);
    v5 = 0;
    return HTTP2TransportChannel::ReceiveComplete(a1, v7, a3, v5, a5);
  }
  v7 = HTTP2TransportChannel::Receive(a1, 4);
  HTTP2Channel::FinishSubmitAsync(*(HTTP2Channel **)(a1 + 24));
  if ( v7 )
  {
    HTTP2Channel::RemoveReference(*(HTTP2Channel **)(a1 + 24));
    goto LABEL_7;
  }
  (*((void (__fastcall **)(unsigned __int8 *))pRuntimeImportTable + 1))(v5);
  return 3221360681LL;
}

```

## disassembly

```asm
0x180015790  push    rbx
0x180015792  push    rbp
0x180015793  push    rsi
0x180015794  push    rdi
0x180015795  push    r14
0x180015797  sub     rsp, 30h
0x18001579b  mov     ebp, [rsp+58h+arg_20]
0x1800157a2  mov     rbx, r9
0x1800157a5  mov     r14d, r8d
0x1800157a8  mov     edi, edx
0x1800157aa  mov     rsi, rcx
0x1800157ad  test    edx, edx
0x1800157af  jnz     short loc_18001580D
0x1800157b1  cmp     byte ptr [r9+2], 14h
0x1800157b6  jnz     short loc_18001580D
0x1800157b8  mov     edx, ebp; unsigned int
0x1800157ba  mov     rcx, rbx; unsigned __int8 *
0x1800157bd  call    ?UntrustedIsPingPacket@@YAHPEAEK@Z; UntrustedIsPingPacket(uchar *,ulong)
0x1800157c2  test    eax, eax
0x1800157c4  jz      short loc_18001580D
0x1800157c6  mov     rcx, [rsi+18h]; this
0x1800157ca  call    ?BeginSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSubmitAsync(void)
0x1800157cf  mov     edi, eax
0x1800157d1  test    eax, eax
0x1800157d3  jnz     short loc_1800157F8
0x1800157d5  lea     edx, [rax+4]
0x1800157d8  mov     rcx, rsi
0x1800157db  call    ?Receive@HTTP2TransportChannel@@UEAAJW4tagHTTP2TrafficType@@@Z; HTTP2TransportChannel::Receive(tagHTTP2TrafficType)
0x1800157e0  mov     rcx, [rsi+18h]; this
0x1800157e4  mov     edi, eax
0x1800157e6  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x1800157eb  test    edi, edi
0x1800157ed  jz      short loc_18001582C
0x1800157ef  mov     rcx, [rsi+18h]; this
0x1800157f3  call    ?RemoveReference@HTTP2Channel@@QEAAXXZ; HTTP2Channel::RemoveReference(void)
0x1800157f8  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800157ff  mov     rcx, rbx
0x180015802  mov     rax, [rax+8]
0x180015806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001580b  xor     ebx, ebx
0x18001580d  mov     r9, rbx
0x180015810  mov     [rsp+58h+var_38], ebp
0x180015814  mov     r8d, r14d
0x180015817  mov     edx, edi
0x180015819  mov     rcx, rsi
0x18001581c  call    ?ReceiveComplete@HTTP2TransportChannel@@UEAAJJW4tagHTTP2TrafficType@@PEAEI@Z; HTTP2TransportChannel::ReceiveComplete(long,tagHTTP2TrafficType,uchar *,uint)
0x180015821  add     rsp, 30h
0x180015825  pop     r14
0x180015827  pop     rdi
0x180015828  pop     rsi
0x180015829  pop     rbp
0x18001582a  pop     rbx
0x18001582b  retn
0x18001582c  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180015833  mov     rcx, rbx
0x180015836  mov     rax, [rax+8]
0x18001583a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001583f  mov     eax, 0C0021029h
0x180015844  jmp     short loc_180015821
```
