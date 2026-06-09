# CBsString::BoundUpdateLength(ulong)

- ea: `0x14000ff4c`
- end: `0x14000ff7f`
- name: `?BoundUpdateLength@CBsString@@QEAAXK@Z`
- size: `51`
- prototype: `void __fastcall(CBsString *this, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400101a4`

## callees

- `0x14000ff4c`

## pseudocode

```c
void __fastcall CBsString::BoundUpdateLength(CBsString *this, __int64 a2)
{
  __int64 v2; // rax

  if ( *(__int64 **)this != qword_140013960 )
  {
    if ( *((_DWORD *)this + 3) < (unsigned int)a2 )
      a2 = *((unsigned int *)this + 3);
    v2 = -1;
    *(_WORD *)(*(_QWORD *)this + 2 * a2) = 0;
    do
      ++v2;
    while ( *(_WORD *)(*(_QWORD *)this + 2 * v2) );
    *((_DWORD *)this + 2) = v2;
  }
}

```

## disassembly

```asm
0x14000ff4c  mov     r8, [rcx]
0x14000ff4f  lea     rax, qword_140013960
0x14000ff56  cmp     r8, rax
0x14000ff59  jz      short locret_14000FF7E
0x14000ff5b  cmp     [rcx+0Ch], edx
0x14000ff5e  cmovb   edx, [rcx+0Ch]
0x14000ff62  xor     r9d, r9d
0x14000ff65  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ff69  mov     [r8+rdx*2], r9w
0x14000ff6e  mov     rdx, [rcx]
0x14000ff71  inc     rax
0x14000ff74  cmp     [rdx+rax*2], r9w
0x14000ff79  jnz     short loc_14000FF71
0x14000ff7b  mov     [rcx+8], eax
0x14000ff7e  retn
```
