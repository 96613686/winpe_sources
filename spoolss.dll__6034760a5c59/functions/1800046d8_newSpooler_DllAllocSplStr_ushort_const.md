# newSpooler::DllAllocSplStr(ushort const *)

- ea: `0x1800046d8`
- end: `0x18000472c`
- name: `?DllAllocSplStr@newSpooler@@YAPEAGPEBG@Z`
- size: `84`
- prototype: `unsigned __int16 *__fastcall(newSpooler *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001dc0`
- `0x1800046b0`

## callees

- `0x1800045e0`
- `0x1800046d8`
- `0x18001503c`

## pseudocode

```c
unsigned __int16 *__fastcall newSpooler::DllAllocSplStr(newSpooler *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned int v5; // esi
  HLOCAL v6; // rax
  HLOCAL v7; // rdi

  if ( !this )
    return 0;
  v4 = -1;
  do
    ++v4;
  while ( *((_WORD *)this + v4) );
  v5 = 2 * v4 + 2;
  v6 = newSpooler::DllAllocSplMem(v5);
  v7 = v6;
  if ( v6 )
    memcpy_0(v6, this, v5);
  return (unsigned __int16 *)v7;
}

```

## disassembly

```asm
0x1800046d8  push    rbx
0x1800046da  push    rbp
0x1800046db  push    rsi
0x1800046dc  push    rdi
0x1800046dd  sub     rsp, 28h
0x1800046e1  xor     ebp, ebp
0x1800046e3  mov     rbx, rcx
0x1800046e6  test    rcx, rcx
0x1800046e9  jnz     short loc_1800046EF
0x1800046eb  xor     eax, eax
0x1800046ed  jmp     short loc_180004723
0x1800046ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800046f3  inc     rax
0x1800046f6  cmp     [rcx+rax*2], bp
0x1800046fa  jnz     short loc_1800046F3
0x1800046fc  lea     esi, ds:2[rax*2]
0x180004703  mov     ecx, esi; uBytes
0x180004705  call    ?DllAllocSplMem@newSpooler@@YAPEAXK@Z; newSpooler::DllAllocSplMem(ulong)
0x18000470a  mov     rdi, rax
0x18000470d  test    rax, rax
0x180004710  jz      short loc_180004720
0x180004712  mov     r8d, esi; Size
0x180004715  mov     rdx, rbx; Src
0x180004718  mov     rcx, rax; void *
0x18000471b  call    memcpy_0
0x180004720  mov     rax, rdi
0x180004723  add     rsp, 28h
0x180004727  pop     rdi
0x180004728  pop     rsi
0x180004729  pop     rbp
0x18000472a  pop     rbx
0x18000472b  retn
```
