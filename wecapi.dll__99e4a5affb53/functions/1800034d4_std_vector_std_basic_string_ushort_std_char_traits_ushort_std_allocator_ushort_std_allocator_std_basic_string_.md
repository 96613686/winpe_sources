# std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::~vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(void)

- ea: `0x1800034d4`
- end: `0x180003550`
- name: `??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800035c0`
- `0x18000bef4`

## callees

- `0x1800026c0`
- `0x1800034d4`

## pseudocode

```c
void __fastcall std::vector<std::wstring>::~vector<std::wstring>(__int64 a1)
{
  void **v1; // rbx
  void **v3; // rsi

  v1 = *(void ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(void ***)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( (unsigned __int64)v1[3] >= 8 )
        operator delete(*v1);
      v1[3] = (void *)7;
      v1[2] = 0;
      *(_WORD *)v1 = 0;
      v1 += 4;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1800034d4  mov     [rsp+arg_0], rbx
0x1800034d9  mov     [rsp+arg_8], rsi
0x1800034de  push    rdi
0x1800034df  sub     rsp, 20h
0x1800034e3  mov     rbx, [rcx]
0x1800034e6  mov     rdi, rcx
0x1800034e9  test    rbx, rbx
0x1800034ec  jz      short loc_180003540
0x1800034ee  mov     rsi, [rcx+8]
0x1800034f2  jmp     short loc_18000351C
0x1800034f4  cmp     qword ptr [rbx+18h], 8
0x1800034f9  jb      short loc_180003503
0x1800034fb  mov     rcx, [rbx]; void *
0x1800034fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003503  xor     eax, eax
0x180003505  mov     qword ptr [rbx+18h], 7
0x18000350d  mov     qword ptr [rbx+10h], 0
0x180003515  mov     [rbx], ax
0x180003518  add     rbx, 20h ; ' '
0x18000351c  cmp     rbx, rsi
0x18000351f  jnz     short loc_1800034F4
0x180003521  mov     rcx, [rdi]; void *
0x180003524  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003529  mov     qword ptr [rdi], 0
0x180003530  mov     qword ptr [rdi+8], 0
0x180003538  mov     qword ptr [rdi+10h], 0
0x180003540  mov     rbx, [rsp+28h+arg_0]
0x180003545  mov     rsi, [rsp+28h+arg_8]
0x18000354a  add     rsp, 20h
0x18000354e  pop     rdi
0x18000354f  retn
```
