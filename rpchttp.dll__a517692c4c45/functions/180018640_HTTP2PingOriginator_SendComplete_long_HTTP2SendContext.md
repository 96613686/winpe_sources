# HTTP2PingOriginator::SendComplete(long,HTTP2SendContext *)

- ea: `0x180018640`
- end: `0x18001867b`
- name: `?SendComplete@HTTP2PingOriginator@@UEAAJJPEAVHTTP2SendContext@@@Z`
- size: `59`
- prototype: `__int64 __fastcall(HTTP2PingOriginator *__hidden this, int, struct HTTP2SendContext *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180018640`
- `0x180018980`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall HTTP2PingOriginator::SendComplete(
        HTTP2PingOriginator *this,
        __int64 a2,
        struct HTTP2SendContext *a3)
{
  if ( *((_DWORD *)a3 + 22) != 1 || (*(_BYTE *)(*((_QWORD *)a3 + 6) + 16LL) & 1) == 0 )
    return HTTP2TransportChannel::SendComplete(this, a2, a3);
  (*((void (__fastcall **)(struct HTTP2SendContext *))pRuntimeImportTable + 1))(a3);
  return 3221360681LL;
}

```

## disassembly

```asm
0x180018640  sub     rsp, 28h
0x180018644  cmp     dword ptr [r8+58h], 1
0x180018649  jnz     short loc_180018672
0x18001864b  mov     rax, [r8+30h]
0x18001864f  test    byte ptr [rax+10h], 1
0x180018653  jz      short loc_180018672
0x180018655  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001865c  mov     rcx, r8
0x18001865f  mov     rax, [rax+8]
0x180018663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018668  mov     eax, 0C0021029h
0x18001866d  add     rsp, 28h
0x180018671  retn
0x180018672  add     rsp, 28h
0x180018676  jmp     ?SendComplete@HTTP2TransportChannel@@UEAAJJPEAVHTTP2SendContext@@@Z; HTTP2TransportChannel::SendComplete(long,HTTP2SendContext *)
```
