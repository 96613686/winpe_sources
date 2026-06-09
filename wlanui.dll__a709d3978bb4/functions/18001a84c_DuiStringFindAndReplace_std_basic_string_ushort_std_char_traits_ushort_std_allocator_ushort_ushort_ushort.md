# DuiStringFindAndReplace(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,ushort *,ushort *)

- ea: `0x18001a84c`
- end: `0x18001a8b8`
- name: `?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z`
- size: `108`
- prototype: `__int64 __fastcall(void *Src, __int64, _WORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180019da0`
- `0x180019ea4`
- `0x180019fa0`
- `0x18001a09c`
- `0x18001a660`
- `0x18001ab44`

## callees

- `0x18001a84c`
- `0x18001b324`
- `0x18001b820`

## pseudocode

```c
__int64 __fastcall DuiStringFindAndReplace(void *Src, __int64 a2, _WORD *a3)
{
  __int64 result; // rax
  __int64 v7; // r9
  __int64 v8; // r8

  result = std::wstring::find();
  v7 = -1;
  if ( result != -1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a2 + 2 * v8) );
    if ( *a3 )
    {
      do
        ++v7;
      while ( a3[v7] );
    }
    else
    {
      v7 = 0;
    }
    return std::wstring::replace(Src, v7);
  }
  return result;
}

```

## disassembly

```asm
0x18001a84c  mov     [rsp+arg_0], rbx
0x18001a851  mov     [rsp+arg_8], rsi
0x18001a856  push    rdi
0x18001a857  sub     rsp, 30h
0x18001a85b  mov     rbx, r8
0x18001a85e  mov     rdi, rdx
0x18001a861  mov     rsi, rcx
0x18001a864  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find(ushort const *,unsigned __int64)
0x18001a869  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001a86d  cmp     rax, r9
0x18001a870  jz      short loc_18001A8A8
0x18001a872  mov     r8, r9
0x18001a875  xor     ecx, ecx
0x18001a877  inc     r8
0x18001a87a  cmp     [rdi+r8*2], cx
0x18001a87f  jnz     short loc_18001A877
0x18001a881  cmp     [rbx], cx
0x18001a884  jnz     short loc_18001A88B
0x18001a886  mov     r9, rcx
0x18001a889  jmp     short loc_18001A895
0x18001a88b  inc     r9
0x18001a88e  cmp     [rbx+r9*2], cx
0x18001a893  jnz     short loc_18001A88B
0x18001a895  mov     [rsp+38h+var_18], r9; __int64
0x18001a89a  mov     rdx, rax
0x18001a89d  mov     r9, rbx
0x18001a8a0  mov     rcx, rsi; Src
0x18001a8a3  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0PEBG0@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x18001a8a8  mov     rbx, [rsp+38h+arg_0]
0x18001a8ad  mov     rsi, [rsp+38h+arg_8]
0x18001a8b2  add     rsp, 30h
0x18001a8b6  pop     rdi
0x18001a8b7  retn
```
