# std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::construct<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x180005da0`
- end: `0x180005e23`
- name: `??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z`
- size: `131`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003178`
- `0x180005d3c`

## callees

- `0x180001ad2`
- `0x180005da0`

## pseudocode

```c
__int64 __fastcall std::_Wrap_alloc<std::allocator<std::wstring>>::construct<std::wstring,std::wstring>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // r8
  __int64 result; // rax

  a2[3] = 7;
  a2[2] = 0;
  *(_WORD *)a2 = 0;
  if ( a3[3] >= 8u )
  {
    *a2 = *a3;
    *a3 = 0;
  }
  else
  {
    v5 = a3[2] + 1LL;
    if ( v5 )
      memmove_0(a2, a3, 2 * v5);
  }
  a2[2] = a3[2];
  a2[3] = a3[3];
  result = 0;
  a3[3] = 7;
  a3[2] = 0;
  *(_WORD *)a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180005da0  mov     [rsp+arg_0], rbx
0x180005da5  push    rdi
0x180005da6  sub     rsp, 20h
0x180005daa  xor     eax, eax
0x180005dac  mov     qword ptr [rdx+18h], 7
0x180005db4  mov     qword ptr [rdx+10h], 0
0x180005dbc  mov     rbx, r8
0x180005dbf  mov     [rdx], ax
0x180005dc2  mov     rdi, rdx
0x180005dc5  cmp     qword ptr [r8+18h], 8
0x180005dca  jnb     short loc_180005DE6
0x180005dcc  mov     r8, [r8+10h]
0x180005dd0  add     r8, 1
0x180005dd4  jz      short loc_180005DF3
0x180005dd6  add     r8, r8; Size
0x180005dd9  mov     rdx, rbx; Src
0x180005ddc  mov     rcx, rdi; void *
0x180005ddf  call    memmove_0
0x180005de4  jmp     short loc_180005DF3
0x180005de6  mov     rax, [r8]
0x180005de9  mov     [rdx], rax
0x180005dec  mov     qword ptr [r8], 0
0x180005df3  mov     rax, [rbx+10h]
0x180005df7  mov     [rdi+10h], rax
0x180005dfb  mov     rax, [rbx+18h]
0x180005dff  mov     [rdi+18h], rax
0x180005e03  xor     eax, eax
0x180005e05  mov     qword ptr [rbx+18h], 7
0x180005e0d  mov     qword ptr [rbx+10h], 0
0x180005e15  mov     [rbx], ax
0x180005e18  mov     rbx, [rsp+28h+arg_0]
0x180005e1d  add     rsp, 20h
0x180005e21  pop     rdi
0x180005e22  retn
```
