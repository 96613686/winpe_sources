# WdipCopyGuid

- ea: `0x180007000`
- end: `0x180007011`
- name: `WdipCopyGuid`
- size: `17`
- prototype: `void __fastcall(_OWORD *, _OWORD *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c84`
- `0x1800097a0`
- `0x180009b60`
- `0x180009c30`
- `0x18000a160`
- `0x18000a280`
- `0x18000a420`
- `0x18000a744`
- `0x18000a9b0`
- `0x18000ab6c`
- `0x18000ae18`
- `0x18000b5c0`
- `0x18000b8b0`
- `0x18000c1e0`
- `0x18000cb40`
- `0x18000cc8c`
- `0x18000dc50`

## callees

- `0x180007000`

## pseudocode

```c
void __fastcall WdipCopyGuid(_OWORD *a1, _OWORD *a2)
{
  if ( a1 )
  {
    if ( a2 )
      *a1 = *a2;
  }
}

```

## disassembly

```asm
0x180007000  test    rcx, rcx
0x180007003  jz      short locret_180007010
0x180007005  test    rdx, rdx
0x180007008  jz      short locret_180007010
0x18000700a  movups  xmm0, xmmword ptr [rdx]
0x18000700d  movups  xmmword ptr [rcx], xmm0
0x180007010  retn
```
