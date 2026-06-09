# TSDereferenceContext(_TS_CONTEXT *)

- ea: `0x180003e00`
- end: `0x180003e23`
- name: `?TSDereferenceContext@@YAXPEAU_TS_CONTEXT@@@Z`
- size: `35`
- prototype: `void __fastcall(struct _TS_CONTEXT *)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d30`
- `0x180006650`
- `0x180007fd0`
- `0x1800177b0`
- `0x180017800`
- `0x180017e00`
- `0x180017e60`
- `0x180017fa0`
- `0x18001a3e0`
- `0x18001a820`
- `0x18001aa90`
- `0x18001b000`
- `0x18001b1f0`

## callees

- `0x180003e00`
- `0x180004170`

## pseudocode

```c
void __fastcall TSDereferenceContext(struct _TS_CONTEXT *a1)
{
  if ( a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) <= 1 )
      TSFreeContext(a1);
  }
}

```

## disassembly

```asm
0x180003e00  sub     rsp, 28h
0x180003e04  test    rcx, rcx
0x180003e07  jz      short loc_180003E17
0x180003e09  mov     eax, 0FFFFFFFFh
0x180003e0e  lock xadd [rcx], eax
0x180003e12  sub     eax, 1
0x180003e15  jle     short loc_180003E1C
0x180003e17  add     rsp, 28h
0x180003e1b  retn
0x180003e1c  call    ?TSFreeContext@@YAXPEAU_TS_CONTEXT@@@Z; TSFreeContext(_TS_CONTEXT *)
0x180003e21  jmp     short loc_180003E17
```
