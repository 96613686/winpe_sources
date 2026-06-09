# HTTP2WinHttpTransportChannel::MoveEEInfoFromThreadToObject(void)

- ea: `0x18000f630`
- end: `0x18000f66e`
- name: `?MoveEEInfoFromThreadToObject@HTTP2WinHttpTransportChannel@@AEAAXXZ`
- size: `62`
- prototype: `void __fastcall(HTTP2WinHttpTransportChannel *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004418`
- `0x1800081e8`
- `0x18001ae4c`
- `0x18001b2b0`

## callees

- `0x180025010`

## pseudocode

```c
void __fastcall HTTP2WinHttpTransportChannel::MoveEEInfoFromThreadToObject(HTTP2WinHttpTransportChannel *this)
{
  __int64 v2; // rax

  v2 = (*((__int64 (**)(void))pRuntimeImportTable + 60))();
  (*((void (__fastcall **)(char *, __int64))pRuntimeImportTable + 61))((char *)this + 88, v2);
}

```

## disassembly

```asm
0x18000f630  push    rbx
0x18000f632  sub     rsp, 20h
0x18000f636  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000f63d  mov     rbx, rcx
0x18000f640  mov     rax, [rax+1E0h]
0x18000f647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f64c  mov     rdx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000f653  lea     rcx, [rbx+58h]
0x18000f657  mov     r8, rax
0x18000f65a  mov     rax, [rdx+1E8h]
0x18000f661  mov     rdx, r8
0x18000f664  add     rsp, 20h
0x18000f668  pop     rbx
0x18000f669  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
