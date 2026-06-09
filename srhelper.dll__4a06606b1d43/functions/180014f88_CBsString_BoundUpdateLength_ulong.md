# CBsString::BoundUpdateLength(ulong)

- ea: `0x180014f88`
- end: `0x180014fbb`
- name: `?BoundUpdateLength@CBsString@@QEAAXK@Z`
- size: `51`
- prototype: `void __fastcall(CBsString *this, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001518c`

## callees

- `0x180014f88`

## pseudocode

```c
void __fastcall CBsString::BoundUpdateLength(CBsString *this, __int64 a2)
{
  __int64 v2; // rax

  if ( *(__int64 **)this != qword_18001A620 )
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
0x180014f88  mov     r8, [rcx]
0x180014f8b  lea     rax, qword_18001A620
0x180014f92  cmp     r8, rax
0x180014f95  jz      short locret_180014FBA
0x180014f97  cmp     [rcx+0Ch], edx
0x180014f9a  cmovb   edx, [rcx+0Ch]
0x180014f9e  xor     r9d, r9d
0x180014fa1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014fa5  mov     [r8+rdx*2], r9w
0x180014faa  mov     rdx, [rcx]
0x180014fad  inc     rax
0x180014fb0  cmp     [rdx+rax*2], r9w
0x180014fb5  jnz     short loc_180014FAD
0x180014fb7  mov     [rcx+8], eax
0x180014fba  retn
```
