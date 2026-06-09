# TSDereferenceCredential(_TS_CREDENTIAL *)

- ea: `0x1800053d0`
- end: `0x1800053f3`
- name: `?TSDereferenceCredential@@YAXPEAU_TS_CREDENTIAL@@@Z`
- size: `35`
- prototype: `void __fastcall(struct _TS_CREDENTIAL *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029b0`
- `0x1800052f0`
- `0x180012af0`
- `0x180013120`
- `0x180013200`
- `0x180013ad0`
- `0x180013c64`
- `0x180013e00`
- `0x1800147b0`
- `0x18001528c`

## callees

- `0x1800053d0`
- `0x180014100`

## pseudocode

```c
void __fastcall TSDereferenceCredential(struct _TS_CREDENTIAL *a1)
{
  if ( a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) <= 1 )
      TSFreeCredential(a1);
  }
}

```

## disassembly

```asm
0x1800053d0  sub     rsp, 28h
0x1800053d4  test    rcx, rcx
0x1800053d7  jz      short loc_1800053E7
0x1800053d9  mov     eax, 0FFFFFFFFh
0x1800053de  lock xadd [rcx], eax
0x1800053e2  sub     eax, 1
0x1800053e5  jle     short loc_1800053EC
0x1800053e7  add     rsp, 28h
0x1800053eb  retn
0x1800053ec  call    ?TSFreeCredential@@YAXPEAU_TS_CREDENTIAL@@@Z; TSFreeCredential(_TS_CREDENTIAL *)
0x1800053f1  jmp     short loc_1800053E7
```
