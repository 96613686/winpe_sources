# DecodeAllFields(ushort const *,STRU *,ushort const * *,STRU *,ushort const * *,STRU *,ushort const * *)

- ea: `0x18000283c`
- end: `0x180002901`
- name: `?DecodeAllFields@@YAJPEBGPEAVSTRU@@PEAPEBG1212@Z`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct STRU *, const unsigned __int16 **, struct STRU *, unsigned __int16 **, struct STRU *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001cdc`
- `0x180002974`

## callees

- `0x18000283c`
- `0x180002908`

## import_xrefs

- `msvcrt!wcschr` at `0x180002878`
- `msvcrt!wcschr` at `0x18000288d`
- `msvcrt!wcschr` at `0x180002878`
- `msvcrt!wcschr` at `0x18000288d`

## pseudocode

```c
__int64 __fastcall DecodeAllFields(
        const unsigned __int16 *a1,
        struct STRU *a2,
        const unsigned __int16 **a3,
        struct STRU *a4,
        unsigned __int16 **a5,
        struct STRU *a6,
        unsigned __int16 **a7)
{
  wchar_t *v10; // rax
  wchar_t *v11; // rdi
  wchar_t *v12; // rax
  wchar_t *v13; // rbx
  __int64 result; // rax

  *a3 = 0;
  *a5 = 0;
  *a7 = 0;
  v10 = wcschr(a1, 0x21u);
  v11 = v10;
  if ( !v10 )
    return 2147942487LL;
  v12 = wcschr(v10 + 1, 0x21u);
  v13 = v12;
  if ( !v12 )
    return 2147942487LL;
  *v11 = 0;
  *v12 = 0;
  result = DecodeOneField(a1, a2, a3);
  if ( (int)result >= 0 )
  {
    result = DecodeOneField(v11 + 1, a4, (const unsigned __int16 **)a5);
    if ( (int)result >= 0 )
      result = DecodeOneField(v13 + 1, a6, (const unsigned __int16 **)a7);
  }
  *v11 = 33;
  *v13 = 33;
  return result;
}

```

## disassembly

```asm
0x18000283c  mov     [rsp+arg_8], rdx
0x180002841  push    rbx
0x180002842  push    rbp
0x180002843  push    rsi
0x180002844  push    rdi
0x180002845  push    r12
0x180002847  push    r13
0x180002849  push    r14
0x18000284b  push    r15
0x18000284d  sub     rsp, 28h
0x180002851  mov     r15, [rsp+68h+arg_20]
0x180002859  xor     ebx, ebx
0x18000285b  mov     r14, [rsp+68h+arg_30]
0x180002863  mov     r13, r9
0x180002866  mov     rbp, r8
0x180002869  mov     [r8], rbx
0x18000286c  mov     r12, rcx
0x18000286f  lea     edx, [rbx+21h]; Ch
0x180002872  mov     [r15], rbx
0x180002875  mov     [r14], rbx
0x180002878  call    cs:__imp_wcschr
0x18000287e  mov     rdi, rax
0x180002881  test    rax, rax
0x180002884  jz      short loc_1800028EB
0x180002886  lea     edx, [rbx+21h]; Ch
0x180002889  lea     rcx, [rax+2]; Str
0x18000288d  call    cs:__imp_wcschr
0x180002893  mov     rbx, rax
0x180002896  test    rax, rax
0x180002899  jz      short loc_1800028EB
0x18000289b  xor     edx, edx
0x18000289d  mov     r8, rbp; unsigned __int16 **
0x1800028a0  mov     [rdi], dx
0x1800028a3  mov     rcx, r12; unsigned __int16 *
0x1800028a6  mov     [rax], dx
0x1800028a9  mov     rdx, [rsp+68h+arg_8]; struct STRU *
0x1800028ae  call    ?DecodeOneField@@YAJPEBGPEAVSTRU@@PEAPEBG@Z; DecodeOneField(ushort const *,STRU *,ushort const * *)
0x1800028b3  test    eax, eax
0x1800028b5  js      short loc_1800028DE
0x1800028b7  mov     r8, r15; unsigned __int16 **
0x1800028ba  lea     rcx, [rdi+2]; unsigned __int16 *
0x1800028be  mov     rdx, r13; struct STRU *
0x1800028c1  call    ?DecodeOneField@@YAJPEBGPEAVSTRU@@PEAPEBG@Z; DecodeOneField(ushort const *,STRU *,ushort const * *)
0x1800028c6  test    eax, eax
0x1800028c8  js      short loc_1800028DE
0x1800028ca  mov     rdx, [rsp+68h+arg_28]; struct STRU *
0x1800028d2  lea     rcx, [rbx+2]; unsigned __int16 *
0x1800028d6  mov     r8, r14; unsigned __int16 **
0x1800028d9  call    ?DecodeOneField@@YAJPEBGPEAVSTRU@@PEAPEBG@Z; DecodeOneField(ushort const *,STRU *,ushort const * *)
0x1800028de  mov     ecx, 21h ; '!'
0x1800028e3  mov     [rdi], cx
0x1800028e6  mov     [rbx], cx
0x1800028e9  jmp     short loc_1800028F0
0x1800028eb  mov     eax, 80070057h
0x1800028f0  add     rsp, 28h
0x1800028f4  pop     r15
0x1800028f6  pop     r14
0x1800028f8  pop     r13
0x1800028fa  pop     r12
0x1800028fc  pop     rdi
0x1800028fd  pop     rsi
0x1800028fe  pop     rbp
0x1800028ff  pop     rbx
0x180002900  retn
```
