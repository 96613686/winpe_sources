# MvmpEstablishGhcbPage

- ea: `0x14000e0a0`
- end: `0x14000e0e8`
- name: `MvmpEstablishGhcbPage`
- size: `72`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aae0`
- `0x14000ada0`
- `0x14000d300`
- `0x14000d410`
- `0x14000d620`
- `0x14000d704`
- `0x14000d910`
- `0x14000da50`
- `0x14000dbc0`
- `0x14000e408`

## callees

- `0x14000b350`
- `0x14000e0a0`

## pseudocode

```c
__int64 __fastcall MvmpEstablishGhcbPage(__int64 a1)
{
  unsigned __int64 v1; // rax

  if ( !*(_BYTE *)(a1 + 188) )
    return 0;
  do
  {
    do
      v1 = __readmsr(0xC0010130);
    while ( v1 < *(_QWORD *)(a1 + 176) );
  }
  while ( (v1 & 0xFFF) != 0 );
  return MvmMapPage(v1, *(_QWORD *)(a1 + 64), *(_QWORD *)(a1 + 72));
}

```

## disassembly

```asm
0x14000e0a0  sub     rsp, 28h
0x14000e0a4  cmp     byte ptr [rcx+0BCh], 0
0x14000e0ab  mov     r9, rcx
0x14000e0ae  jz      short loc_14000E0E0
0x14000e0b0  mov     ecx, 0C0010130h
0x14000e0b5  rdmsr
0x14000e0b7  shl     rdx, 20h
0x14000e0bb  or      rax, rdx
0x14000e0be  cmp     rax, [r9+0B0h]
0x14000e0c5  jb      short loc_14000E0B0
0x14000e0c7  test    eax, 0FFFh
0x14000e0cc  jnz     short loc_14000E0B0
0x14000e0ce  mov     r8, [r9+48h]
0x14000e0d2  mov     rcx, rax
0x14000e0d5  mov     rdx, [r9+40h]
0x14000e0d9  call    MvmMapPage
0x14000e0de  jmp     short loc_14000E0E2
0x14000e0e0  xor     eax, eax
0x14000e0e2  add     rsp, 28h
0x14000e0e6  retn
```
