# mi::MiInstance::AddElement<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uint)

- ea: `0x180005488`
- end: `0x180005508`
- name: `??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z`
- size: `128`
- prototype: `__int64 __fastcall(int, int, _QWORD *, int)`
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x180006320`
- `0x180014050`
- `0x180016f84`
- `0x180019550`
- `0x18001a0c4`
- `0x18001da60`
- `0x18001decc`
- `0x18001e0d4`
- `0x18001e264`
- `0x18001e4a8`
- `0x18001e75c`
- `0x18001e8d8`
- `0x18001eaa0`
- `0x18001ec00`
- `0x18001ed90`
- `0x18001f058`
- `0x18001f220`
- `0x18001f3b0`
- `0x18001f540`
- `0x18001f6a0`
- `0x18001f910`
- `0x18002095c`

## callees

- `0x1800014e0`
- `0x180005488`
- `0x180026b90`

## pseudocode

```c
__int64 __fastcall mi::MiInstance::AddElement<std::wstring>(int a1, int a2, _QWORD *a3, int a4)
{
  _BYTE v5[40]; // [rsp+30h] [rbp-9h] BYREF
  char v6; // [rsp+58h] [rbp+1Fh] BYREF
  __int64 v7; // [rsp+59h] [rbp+20h]
  _BYTE v8[31]; // [rsp+61h] [rbp+28h]

  memset(&v5[1], 0, 39);
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  *(_QWORD *)v5 = a3;
  v6 = (char)a3;
  *(_OWORD *)v8 = *(_OWORD *)&v5[9];
  v7 = *(_QWORD *)&v5[1];
  *(_OWORD *)&v8[15] = *(_OWORD *)&v5[24];
  return mi::MiInstance::AddElement(a1, a2, 13, (unsigned int)&v6, a4);
}

```

## disassembly

```asm
0x180005488  push    rbp
0x18000548a  lea     rbp, [rsp-57h]
0x18000548f  sub     rsp, 90h
0x180005496  mov     rax, cs:__security_cookie
0x18000549d  xor     rax, rsp
0x1800054a0  mov     [rbp+57h+var_10], rax
0x1800054a4  xorps   xmm0, xmm0
0x1800054a7  xor     eax, eax
0x1800054a9  cmp     qword ptr [r8+18h], 7
0x1800054ae  movups  [rbp+57h+var_4F], xmm0
0x1800054b2  mov     qword ptr [rbp+57h+var_4F+0Fh], rax
0x1800054b6  movups  [rbp+57h+var_5F], xmm0
0x1800054ba  jbe     short loc_1800054BF
0x1800054bc  mov     r8, [r8]
0x1800054bf  movups  xmm0, [rbp+57h+var_5F+8]
0x1800054c3  mov     [rbp-9], r8
0x1800054c7  movups  xmm1, [rbp+57h+var_4F+7]
0x1800054cb  mov     rax, qword ptr [rbp+57h+var_5F]
0x1800054cf  mov     [rbp+57h+var_38], r8b
0x1800054d3  mov     r8d, 0Dh
0x1800054d9  mov     [rsp+90h+var_70], r9d
0x1800054de  lea     r9, [rbp+57h+var_38]
0x1800054e2  movups  xmmword ptr [rbp+57h+var_2F], xmm0
0x1800054e6  mov     [rbp+57h+var_37], rax
0x1800054ea  movups  xmmword ptr [rbp+57h+var_2F+0Fh], xmm1
0x1800054ee  call    ?AddElement@MiInstance@mi@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4_MI_Type@@PEAT_MI_Value@@I@Z; mi::MiInstance::AddElement(std::wstring const &,_MI_Type,_MI_Value *,uint)
0x1800054f3  mov     rcx, [rbp+57h+var_10]
0x1800054f7  xor     rcx, rsp; StackCookie
0x1800054fa  call    __security_check_cookie
0x1800054ff  add     rsp, 90h
0x180005506  pop     rbp
0x180005507  retn
```
