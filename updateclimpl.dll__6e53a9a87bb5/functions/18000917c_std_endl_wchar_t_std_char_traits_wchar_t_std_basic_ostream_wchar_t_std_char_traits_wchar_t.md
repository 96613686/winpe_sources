# std::endl<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &)

- ea: `0x18000917c`
- end: `0x18000921e`
- name: `??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z`
- size: `162`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800084bc`
- `0x180008b90`
- `0x180008cdc`
- `0x180009314`
- `0x180015ac6`

## callees

- `0x18000917c`
- `0x18000960c`
- `0x1800096f4`
- `0x180009888`
- `0x1800148e0`

## pseudocode

```c
__int64 __fastcall std::endl<wchar_t,std::char_traits<wchar_t>>(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  unsigned __int16 v4; // di
  void (__fastcall ***v5)(_QWORD, __int64); // r8
  void (__fastcall ***v6)(_QWORD, __int64); // rax
  _BYTE v8[8]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+28h] [rbp-10h]

  v9 = *(_QWORD *)(*(_QWORD *)(*(int *)(*(_QWORD *)a1 + 4LL) + a1 + 64) + 8LL);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v2 = std::use_facet<std::ctype<wchar_t>>(v8);
  LOBYTE(v3) = 10;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 96LL))(v2, v3);
  if ( v9 )
  {
    v6 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v5 = v6;
    if ( v6 )
      (**v6)(v6, 1);
  }
  std::wostream::put(a1, v4, v5);
  std::wostream::flush(a1);
  return a1;
}

```

## disassembly

```asm
0x18000917c  mov     [rsp+arg_0], rbx
0x180009181  push    rdi
0x180009182  sub     rsp, 30h
0x180009186  mov     rbx, rcx
0x180009189  mov     rax, [rcx]
0x18000918c  movsxd  rdx, dword ptr [rax+4]
0x180009190  mov     rax, [rdx+rcx+40h]
0x180009195  mov     rcx, [rax+8]
0x180009199  mov     [rsp+38h+var_10], rcx
0x18000919e  mov     rax, [rcx]
0x1800091a1  mov     rax, [rax+8]
0x1800091a5  call    _guard_dispatch_icall
0x1800091aa  nop
0x1800091ab  lea     rcx, [rsp+38h+var_18]
0x1800091b0  call    ??$use_facet@V?$ctype@_W@std@@@std@@YAAEBV?$ctype@_W@0@AEBVlocale@0@@Z; std::use_facet<std::ctype<wchar_t>>(std::locale const &)
0x1800091b5  mov     r8, rax
0x1800091b8  mov     rcx, [rax]
0x1800091bb  mov     rax, [rcx+60h]
0x1800091bf  mov     dl, 0Ah
0x1800091c1  mov     rcx, r8
0x1800091c4  call    _guard_dispatch_icall
0x1800091c9  movzx   edi, ax
0x1800091cc  mov     rcx, [rsp+38h+var_10]
0x1800091d1  test    rcx, rcx
0x1800091d4  jz      short loc_1800091FD
0x1800091d6  mov     rdx, [rcx]
0x1800091d9  mov     rax, [rdx+10h]
0x1800091dd  call    _guard_dispatch_icall
0x1800091e2  mov     r8, rax
0x1800091e5  test    rax, rax
0x1800091e8  jz      short loc_1800091FD
0x1800091ea  mov     rcx, [rax]
0x1800091ed  mov     rax, [rcx]
0x1800091f0  mov     edx, 1
0x1800091f5  mov     rcx, r8
0x1800091f8  call    _guard_dispatch_icall
0x1800091fd  movzx   edx, di
0x180009200  mov     rcx, rbx
0x180009203  call    ?put@?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV12@_W@Z; std::wostream::put(wchar_t)
0x180009208  mov     rcx, rbx
0x18000920b  call    ?flush@?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV12@XZ; std::wostream::flush(void)
0x180009210  mov     rax, rbx
0x180009213  mov     rbx, [rsp+38h+arg_0]
0x180009218  add     rsp, 30h
0x18000921c  pop     rdi
0x18000921d  retn
```
