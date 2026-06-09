# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *)

- ea: `0x18001052c`
- end: `0x180010566`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z`
- size: `58`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ffd4`
- `0x1800111f4`
- `0x1800142b8`
- `0x180014484`
- `0x180014900`
- `0x1800151e0`
- `0x180015500`

## callees

- `0x18001052c`
- `0x1800136c0`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  __int64 v3; // r8

  *(_QWORD *)(a1 + 24) = 7;
  v3 = -1;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  do
    ++v3;
  while ( *(_WORD *)(a2 + 2 * v3) );
  std::wstring::assign(a1);
  return a1;
}

```

## disassembly

```asm
0x18001052c  push    rbx
0x18001052e  sub     rsp, 20h
0x180010532  mov     rbx, rcx
0x180010535  mov     qword ptr [rcx+18h], 7
0x18001053d  xor     ecx, ecx
0x18001053f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010543  mov     [rbx+10h], rcx
0x180010547  mov     [rbx], cx
0x18001054a  inc     r8
0x18001054d  cmp     [rdx+r8*2], cx
0x180010552  jnz     short loc_18001054A
0x180010554  mov     rcx, rbx
0x180010557  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001055c  mov     rax, rbx
0x18001055f  add     rsp, 20h
0x180010563  pop     rbx
0x180010564  retn
```
