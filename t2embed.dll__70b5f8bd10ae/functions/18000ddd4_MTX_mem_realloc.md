# MTX_mem_realloc

- ea: `0x18000ddd4`
- end: `0x18000de67`
- name: `MTX_mem_realloc`
- size: `147`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x180001e48`
- `0x180001f60`
- `0x1800034b4`
- `0x180003550`
- `0x1800059a0`
- `0x180006d30`
- `0x180007fb0`
- `0x180008230`
- `0x1800088a0`
- `0x180009a50`
- `0x18000bd00`
- `0x18000bde0`
- `0x18000d5a0`
- `0x18000dca8`
- `0x18000e640`
- `0x18000ea00`
- `0x18000eacc`

## callees

- `0x180006400`
- `0x180009c80`
- `0x18000ddd4`
- `0x18002b010`

## import_xrefs

- `msvcrt!longjmp` at `0x18000de50`
- `msvcrt!longjmp` at `0x18000de60`
- `msvcrt!longjmp` at `0x18000de50`
- `msvcrt!longjmp` at `0x18000de60`

## pseudocode

```c
__int64 __fastcall MTX_mem_realloc(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v5; // rbp
  int v6; // eax
  __int64 v7; // rdi
  __int64 result; // rax

  if ( !a2 )
    return MTX_mem_malloc((__int64 *)a1, a3);
  if ( a3 )
  {
    v5 = *(_QWORD *)a1;
    v6 = *(_DWORD *)(a1 + 12);
    do
    {
      if ( --v6 < 0 )
        longjmp((_JBTYPE *)(a1 + 48), 3356);
      v7 = 2LL * v6;
    }
    while ( *(_QWORD *)(v5 + 16LL * v6) != a2 );
    result = (*(__int64 (__fastcall **)(__int64, _QWORD))(a1 + 32))(a2, a3);
    if ( !result )
      longjmp((_JBTYPE *)(a1 + 48), 3357);
    *(_QWORD *)(v5 + 8 * v7) = result;
    *(_DWORD *)(v5 + 8 * v7 + 8) = a3;
  }
  else
  {
    DiscardPointer((__int64 *)a1, a2, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ddd4  push    rbx
0x18000ddd6  push    rbp
0x18000ddd7  push    rsi
0x18000ddd8  push    rdi
0x18000ddd9  sub     rsp, 28h
0x18000dddd  mov     esi, r8d
0x18000dde0  mov     r9, rdx
0x18000dde3  mov     rbx, rcx
0x18000dde6  test    rdx, rdx
0x18000dde9  jz      short loc_18000DE2F
0x18000ddeb  test    r8d, r8d
0x18000ddee  jz      short loc_18000DE38
0x18000ddf0  mov     rbp, [rcx]
0x18000ddf3  mov     eax, [rcx+0Ch]
0x18000ddf6  dec     eax
0x18000ddf8  test    eax, eax
0x18000ddfa  js      short loc_18000DE57
0x18000ddfc  movsxd  rdi, eax
0x18000ddff  add     rdi, rdi
0x18000de02  cmp     [rbp+rdi*8+0], r9
0x18000de07  jnz     short loc_18000DDF6
0x18000de09  mov     rax, [rbx+20h]
0x18000de0d  mov     rdx, rsi
0x18000de10  mov     rcx, r9
0x18000de13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de18  test    rax, rax
0x18000de1b  jz      short loc_18000DE47
0x18000de1d  mov     [rbp+rdi*8+0], rax
0x18000de22  mov     [rbp+rdi*8+8], esi
0x18000de26  add     rsp, 28h
0x18000de2a  pop     rdi
0x18000de2b  pop     rsi
0x18000de2c  pop     rbp
0x18000de2d  pop     rbx
0x18000de2e  retn
0x18000de2f  mov     edx, esi
0x18000de31  call    MTX_mem_malloc
0x18000de36  jmp     short loc_18000DE26
0x18000de38  mov     r8d, 1
0x18000de3e  call    DiscardPointer
0x18000de43  xor     eax, eax
0x18000de45  jmp     short loc_18000DE26
0x18000de47  lea     rcx, [rbx+30h]; Buf
0x18000de4b  mov     edx, 0D1Dh; Value
0x18000de50  call    cs:__imp_longjmp
0x18000de57  add     rcx, 30h ; '0'; Buf
0x18000de5b  mov     edx, 0D1Ch; Value
0x18000de60  call    cs:__imp_longjmp
```
