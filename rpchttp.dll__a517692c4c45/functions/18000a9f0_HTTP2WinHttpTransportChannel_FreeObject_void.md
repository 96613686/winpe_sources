# HTTP2WinHttpTransportChannel::FreeObject(void)

- ea: `0x18000a9f0`
- end: `0x18000aa90`
- name: `?FreeObject@HTTP2WinHttpTransportChannel@@UEAAXXZ`
- size: `160`
- prototype: `void __fastcall(HTTP2WinHttpTransportChannel *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a9f0`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000aa89`
- `RPCRT4!I_RpcFree` at `0x18000aa72`
- `RPCRT4!I_RpcFree` at `0x18000aa72`
- `RPCRT4!I_RpcLogEvent` at `0x18000aa1e`
- `RPCRT4!I_RpcLogEvent` at `0x18000aa1e`

## pseudocode

```c
void __fastcall HTTP2WinHttpTransportChannel::FreeObject(HTTP2WinHttpTransportChannel *this, __int64 a2)
{
  HTTP2WinHttpTransportChannel *v2; // rbx
  HTTP2WinHttpTransportChannel *v3; // r8
  void *v4; // rcx

  v2 = this;
  v3 = this;
  LOBYTE(this) = 50;
  LOBYTE(a2) = 111;
  I_RpcLogEvent(this, a2, v3, 17170453, 0, 0, 0);
  if ( *((_QWORD *)v2 + 4) )
  {
    (*((void (**)(void))pRuntimeImportTable + 1))();
    *((_QWORD *)v2 + 4) = 0;
  }
  if ( *((_QWORD *)v2 + 11) )
  {
    (*((void (**)(void))pRuntimeImportTable + 62))();
    *((_QWORD *)v2 + 11) = 0;
  }
  v4 = (void *)*((_QWORD *)v2 + 12);
  if ( v4 )
  {
    I_RpcFree(v4);
    *((_QWORD *)v2 + 12) = 0;
  }
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)v2 + 104));
}

```

## disassembly

```asm
0x18000a9f0  push    rbx
0x18000a9f2  sub     rsp, 40h
0x18000a9f6  mov     rbx, rcx
0x18000a9f9  mov     [rsp+48h+var_18], 0
0x18000aa01  mov     r8, rcx
0x18000aa04  mov     [rsp+48h+var_20], 0
0x18000aa0c  mov     cl, 32h ; '2'
0x18000aa0e  mov     [rsp+48h+var_28], 0
0x18000aa16  mov     r9d, 1060015h
0x18000aa1c  mov     dl, 6Fh ; 'o'
0x18000aa1e  call    cs:__imp_I_RpcLogEvent
0x18000aa24  mov     rcx, [rbx+20h]
0x18000aa28  test    rcx, rcx
0x18000aa2b  jz      short loc_18000AA45
0x18000aa2d  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000aa34  mov     rax, [rax+8]
0x18000aa38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa3d  mov     qword ptr [rbx+20h], 0
0x18000aa45  mov     rcx, [rbx+58h]
0x18000aa49  test    rcx, rcx
0x18000aa4c  jz      short loc_18000AA69
0x18000aa4e  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000aa55  mov     rax, [rax+1F0h]
0x18000aa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa61  mov     qword ptr [rbx+58h], 0
0x18000aa69  mov     rcx, [rbx+60h]; Object
0x18000aa6d  test    rcx, rcx
0x18000aa70  jz      short loc_18000AA80
0x18000aa72  call    cs:__imp_I_RpcFree
0x18000aa78  mov     qword ptr [rbx+60h], 0
0x18000aa80  lea     rcx, [rbx+68h]
0x18000aa84  add     rsp, 40h
0x18000aa88  pop     rbx
0x18000aa89  jmp     cs:__imp_RtlDeleteCriticalSection
```
