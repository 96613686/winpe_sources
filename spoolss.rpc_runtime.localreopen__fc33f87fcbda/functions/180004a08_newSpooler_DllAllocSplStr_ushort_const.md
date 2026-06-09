# newSpooler::DllAllocSplStr(ushort const *)

- ea: `0x180004a08`
- end: `0x180004a5d`
- name: `?DllAllocSplStr@newSpooler@@YAPEAGPEBG@Z`
- size: `85`
- prototype: `unsigned __int16 *__fastcall(newSpooler *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001e20`
- `0x1800049e0`

## callees

- `0x180004850`
- `0x180004a08`
- `0x180016a3c`

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
0x180004a08  push    rbx
0x180004a0a  push    rbp
0x180004a0b  push    rsi
0x180004a0c  push    rdi
0x180004a0d  sub     rsp, 28h
0x180004a11  xor     ebp, ebp
0x180004a13  mov     rbx, rcx
0x180004a16  test    rcx, rcx
0x180004a19  jnz     short loc_180004A1F
0x180004a1b  xor     eax, eax
0x180004a1d  jmp     short loc_180004A53
0x180004a1f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a23  inc     rax
0x180004a26  cmp     [rcx+rax*2], bp
0x180004a2a  jnz     short loc_180004A23
0x180004a2c  lea     esi, ds:2[rax*2]
0x180004a33  mov     ecx, esi; uBytes
0x180004a35  call    ?DllAllocSplMem@newSpooler@@YAPEAXK@Z; newSpooler::DllAllocSplMem(ulong)
0x180004a3a  mov     rdi, rax
0x180004a3d  test    rax, rax
0x180004a40  jz      short loc_180004A50
0x180004a42  mov     r8d, esi; Size
0x180004a45  mov     rdx, rbx; Src
0x180004a48  mov     rcx, rax; void *
0x180004a4b  call    memcpy_0
0x180004a50  mov     rax, rdi
0x180004a53  add     rsp, 28h
0x180004a57  pop     rdi
0x180004a58  pop     rsi
0x180004a59  pop     rbp
0x180004a5a  pop     rbx
0x180004a5b  retn
```
