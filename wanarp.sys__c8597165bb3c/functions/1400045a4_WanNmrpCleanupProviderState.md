# WanNmrpCleanupProviderState

- ea: `0x1400045a4`
- end: `0x1400045e5`
- name: `WanNmrpCleanupProviderState`
- size: `65`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140017550`
- `0x14001a078`
- `0x14001aa04`

## callees

- `0x1400045a4`

## import_xrefs

- `NETIO!NetioFreeStackBlock` at `0x1400045c7`
- `NETIO!NetioFreeStackBlock` at `0x1400045c7`

## pseudocode

```c
__int64 __fastcall WanNmrpCleanupProviderState(__int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  if ( a1 && *(_BYTE *)a1 )
  {
    v2 = *(_QWORD *)(a1 + 584);
    if ( v2 )
    {
      result = NetioFreeStackBlock(v2, 1112765015);
      *(_QWORD *)(a1 + 584) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400045a4  test    rcx, rcx
0x1400045a7  jz      short locret_1400045E3
0x1400045a9  push    rbx
0x1400045aa  sub     rsp, 20h
0x1400045ae  cmp     byte ptr [rcx], 0
0x1400045b1  mov     rbx, rcx
0x1400045b4  jz      short loc_1400045DE
0x1400045b6  mov     rcx, [rcx+248h]
0x1400045bd  test    rcx, rcx
0x1400045c0  jz      short loc_1400045DE
0x1400045c2  mov     edx, 42537257h
0x1400045c7  call    cs:__imp_NetioFreeStackBlock
0x1400045ce  nop     dword ptr [rax+rax+00h]
0x1400045d3  mov     qword ptr [rbx+248h], 0
0x1400045de  add     rsp, 20h
0x1400045e2  pop     rbx
0x1400045e3  retn
```
