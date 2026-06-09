# swprintf_sfn(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18001230c`
- end: `0x180012364`
- name: `?swprintf_sfn@@YAXPEAG_KPEBGZZ`
- size: `88`
- prototype: `void(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b114`
- `0x18000b4b8`
- `0x18000c5c8`
- `0x18000ca6c`

## callees

- `0x18001230c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180012344`
- `msvcrt!_vsnwprintf` at `0x180012344`

## pseudocode

```c
void swprintf_sfn(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rbx
  int v5; // eax
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  *a1 = 0;
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v4 = a2 - 1;
    v5 = _vsnwprintf(a1, a2 - 1, a3, va);
    if ( v5 < 0 || v5 >= v4 )
      a1[v4] = 0;
  }
}

```

## disassembly

```asm
0x18001230c  mov     rax, rsp
0x18001230f  mov     [rax+18h], r8
0x180012313  mov     [rax+20h], r9
0x180012317  push    rbx
0x180012318  push    rdi
0x180012319  sub     rsp, 38h
0x18001231d  mov     qword ptr [rax-28h], 0
0x180012325  lea     r9, [rax+20h]; Args
0x180012329  xor     eax, eax
0x18001232b  mov     rdi, rcx
0x18001232e  mov     [rcx], ax
0x180012331  lea     rax, [rdx-1]
0x180012335  cmp     rax, 7FFFFFFEh
0x18001233b  ja      short loc_18001235D
0x18001233d  lea     rbx, [rdx-1]
0x180012341  mov     rdx, rbx; BufferCount
0x180012344  call    cs:__imp__vsnwprintf
0x18001234a  test    eax, eax
0x18001234c  js      short loc_180012357
0x18001234e  cdqe
0x180012350  cmp     rax, rbx
0x180012353  ja      short loc_180012357
0x180012355  jnz     short loc_18001235D
0x180012357  xor     eax, eax
0x180012359  mov     [rdi+rbx*2], ax
0x18001235d  add     rsp, 38h
0x180012361  pop     rdi
0x180012362  pop     rbx
0x180012363  retn
```
