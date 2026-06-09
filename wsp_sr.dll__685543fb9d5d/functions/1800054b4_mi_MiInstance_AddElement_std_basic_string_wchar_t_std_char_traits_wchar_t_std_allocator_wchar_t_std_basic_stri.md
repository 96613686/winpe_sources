# mi::MiInstance::AddElement<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uint)

- ea: `0x1800054b4`
- end: `0x180005535`
- name: `??$AddElement@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@MiInstance@mi@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0I@Z`
- size: `129`
- prototype: ``
- caller_count: `22`
- callee_count: `3`
- tags: ``

## callers

- `0x180006360`
- `0x180013f60`
- `0x180016e4c`
- `0x180019584`
- `0x18001a0fc`
- `0x18001db88`
- `0x18001dff4`
- `0x18001e200`
- `0x18001e390`
- `0x18001e5d4`
- `0x18001e88c`
- `0x18001ea08`
- `0x18001ebd0`
- `0x18001ed30`
- `0x18001eec0`
- `0x18001f18c`
- `0x18001f354`
- `0x18001f4e4`
- `0x18001f674`
- `0x18001f7d8`
- `0x18001fa48`
- `0x180020ac0`

## callees

- `0x1800014e0`
- `0x1800054b4`
- `0x180026ee8`

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
0x1800054b4  push    rbp
0x1800054b6  lea     rbp, [rsp-57h]
0x1800054bb  sub     rsp, 90h
0x1800054c2  mov     rax, cs:__security_cookie
0x1800054c9  xor     rax, rsp
0x1800054cc  mov     [rbp+57h+var_10], rax
0x1800054d0  xorps   xmm0, xmm0
0x1800054d3  xor     eax, eax
0x1800054d5  cmp     qword ptr [r8+18h], 7
0x1800054da  movups  [rbp+57h+var_4F], xmm0
0x1800054de  mov     qword ptr [rbp+57h+var_4F+0Fh], rax
0x1800054e2  movups  [rbp+57h+var_5F], xmm0
0x1800054e6  jbe     short loc_1800054EB
0x1800054e8  mov     r8, [r8]
0x1800054eb  movups  xmm0, [rbp+57h+var_5F+8]
0x1800054ef  mov     [rbp-9], r8
0x1800054f3  movups  xmm1, [rbp+57h+var_4F+7]
0x1800054f7  mov     rax, qword ptr [rbp+57h+var_5F]
0x1800054fb  mov     [rbp+57h+var_38], r8b
0x1800054ff  mov     r8d, 0Dh
0x180005505  mov     [rsp+90h+var_70], r9d
0x18000550a  lea     r9, [rbp+57h+var_38]
0x18000550e  movups  xmmword ptr [rbp+57h+var_2F], xmm0
0x180005512  mov     [rbp+57h+var_37], rax
0x180005516  movups  xmmword ptr [rbp+57h+var_2F+0Fh], xmm1
0x18000551a  call    ?AddElement@MiInstance@mi@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4_MI_Type@@PEAT_MI_Value@@I@Z; mi::MiInstance::AddElement(std::wstring const &,_MI_Type,_MI_Value *,uint)
0x18000551f  mov     rcx, [rbp+57h+var_10]
0x180005523  xor     rcx, rsp; StackCookie
0x180005526  call    __security_check_cookie
0x18000552b  add     rsp, 90h
0x180005532  pop     rbp
0x180005533  retn
```
