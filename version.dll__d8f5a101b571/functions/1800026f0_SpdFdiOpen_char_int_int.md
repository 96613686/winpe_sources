# SpdFdiOpen(char *,int,int)

- ea: `0x1800026f0`
- end: `0x180002733`
- name: `?SpdFdiOpen@@YA_JPEADHH@Z`
- size: `67`
- prototype: `__int64 __fastcall(char *, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002198`
- `0x1800025b8`

## callees

- `0x1800026f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000271a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000271a`
- `KERNEL32!_lopen` at `0x180002709`
- `KERNEL32!_lopen` at `0x180002709`

## pseudocode

```c
__int64 __fastcall SpdFdiOpen(char *a1, char a2)
{
  int v2; // edx
  __int64 result; // rax

  if ( (a2 & 1) != 0 )
    v2 = 33;
  else
    v2 = a2 & 2 | 0x20;
  LODWORD(result) = _lopen(a1, v2);
  if ( (_DWORD)result != -1 )
    return (int)result;
  *(_DWORD *)TlsGetValue(itlsDiamondContext) = -1;
  return -1;
}

```

## disassembly

```asm
0x1800026f0  sub     rsp, 28h
0x1800026f4  test    dl, 1
0x1800026f7  jz      short loc_180002700
0x1800026f9  mov     edx, 21h ; '!'
0x1800026fe  jmp     short loc_180002709
0x180002700  movzx   edx, dl
0x180002703  and     edx, 2
0x180002706  or      edx, 20h; iReadWrite
0x180002709  call    cs:__imp__lopen
0x18000270f  cmp     eax, 0FFFFFFFFh
0x180002712  jnz     short loc_18000272C
0x180002714  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x18000271a  call    cs:__imp_TlsGetValue
0x180002720  mov     dword ptr [rax], 0FFFFFFFFh
0x180002726  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000272a  jmp     short loc_18000272E
0x18000272c  cdqe
0x18000272e  add     rsp, 28h
0x180002732  retn
```
