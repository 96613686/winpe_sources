# EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)

- ea: `0x180011810`
- end: `0x180011829`
- name: `?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z`
- size: `25`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *, unsigned __int64)`
- caller_count: `256`
- callee_count: `1`
- tags: ``

## callers

- `0x180010810`
- `0x180010820`
- `0x180010830`
- `0x180010840`
- `0x180010850`
- `0x180010860`
- `0x180010870`
- `0x180010880`
- `0x180010890`
- `0x1800108a0`
- `0x1800108b0`
- `0x1800108c0`
- `0x1800108d0`
- `0x1800108e0`
- `0x1800108f0`
- `0x180010900`
- `0x180010910`
- `0x180010920`
- `0x180010930`
- `0x180010940`
- `0x180010950`
- `0x180010960`
- `0x180010970`
- `0x180010980`
- `0x180010990`
- `0x1800109a0`
- `0x1800109b0`
- `0x1800109c0`
- `0x1800109d0`
- `0x1800109e0`
- `0x1800109f0`
- `0x180010a00`
- `0x180010a10`
- `0x180010a20`
- `0x180010a30`
- `0x180010a40`
- `0x180010a50`
- `0x180010a60`
- `0x180010a70`
- `0x180010a80`
- `0x180010a90`
- `0x180010aa0`
- `0x180010ab0`
- `0x180010ac0`
- `0x180010ad0`
- `0x180010ae0`
- `0x180010af0`
- `0x180010b00`
- `0x180010b10`
- `0x180010b20`

## callees

- `0x180034010`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_Call(struct _EVENT_TRACE_LOGFILEW *a1, __int64 a2)
{
  return ((__int64 (__fastcall *)(struct _EVENT_TRACE_LOGFILEW *, _UNKNOWN *****************))(&off_18004B008)[3 * a2 + 1])(
           a1,
           (&off_18004B008)[3 * a2]);
}

```

## disassembly

```asm
0x180011810  lea     rax, [rdx+rdx*2]
0x180011814  lea     r8, off_18004B008
0x18001181b  mov     rdx, [r8+rax*8]
0x18001181f  mov     rax, [r8+rax*8+8]
0x180011824  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
