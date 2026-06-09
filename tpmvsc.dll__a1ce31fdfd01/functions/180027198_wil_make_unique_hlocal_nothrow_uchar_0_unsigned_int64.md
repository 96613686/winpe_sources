# wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)

- ea: `0x180027198`
- end: `0x1800271d8`
- name: `??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `64`
- prototype: `_QWORD *__fastcall(_QWORD *, SIZE_T)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180027154`

## callees

- `0x180027198`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800271aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800271aa`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal_nothrow<unsigned char [0]>(_QWORD *a1, SIZE_T a2)
{
  _BYTE *v4; // rax
  _BYTE *v5; // rdx

  v4 = LocalAlloc(0, a2);
  *a1 = v4;
  if ( v4 )
  {
    v5 = &v4[a2];
    while ( v4 != v5 )
      *v4++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180027198  mov     [rsp+arg_0], rbx
0x18002719d  push    rdi
0x18002719e  sub     rsp, 20h
0x1800271a2  mov     rbx, rcx
0x1800271a5  mov     rdi, rdx
0x1800271a8  xor     ecx, ecx; uFlags
0x1800271aa  call    cs:__imp_LocalAlloc
0x1800271b0  mov     [rbx], rax
0x1800271b3  test    rax, rax
0x1800271b6  jz      short loc_1800271CA
0x1800271b8  lea     rdx, [rax+rdi]
0x1800271bc  jmp     short loc_1800271C5
0x1800271be  xor     ecx, ecx
0x1800271c0  mov     [rax], cl
0x1800271c2  inc     rax
0x1800271c5  cmp     rax, rdx
0x1800271c8  jnz     short loc_1800271BE
0x1800271ca  mov     rax, rbx
0x1800271cd  mov     rbx, [rsp+28h+arg_0]
0x1800271d2  add     rsp, 20h
0x1800271d6  pop     rdi
0x1800271d7  retn
```
