# CLogFileHeader::SetDirty(int)

- ea: `0x18000cff8`
- end: `0x18000d017`
- name: `?SetDirty@CLogFileHeader@@QEAAXH@Z`
- size: `31`
- prototype: `void __fastcall(CLogFileHeader *__hidden this, int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800033b0`
- `0x180007f90`
- `0x18000cd40`
- `0x18000e7c0`
- `0x18000edb0`

## callees

- `0x18000c3d4`
- `0x18000cff8`

## pseudocode

```c
void __fastcall CLogFileHeader::SetDirty(CLogFileHeader *this, int a2)
{
  unsigned int v2; // eax

  v2 = a2 ^ (*(_DWORD *)this ^ a2) & 0xFFFFFFFE;
  *(_DWORD *)this = v2;
  if ( (v2 & 1) != 0 )
    CLogFileHeader::SetShutdown(this, 0);
}

```

## disassembly

```asm
0x18000cff8  sub     rsp, 28h
0x18000cffc  mov     eax, edx
0x18000cffe  xor     eax, [rcx]
0x18000d000  and     eax, 0FFFFFFFEh
0x18000d003  xor     eax, edx
0x18000d005  mov     [rcx], eax
0x18000d007  test    al, 1
0x18000d009  jz      short loc_18000D012
0x18000d00b  xor     edx, edx; int
0x18000d00d  call    ?SetShutdown@CLogFileHeader@@QEAAXH@Z; CLogFileHeader::SetShutdown(int)
0x18000d012  add     rsp, 28h
0x18000d016  retn
```
