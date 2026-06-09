# mi::MiApplication::CreateSession<0>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiDestinationOptions &)

- ea: `0x180025f90`
- end: `0x180026030`
- name: `??$CreateSession@$0A@@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@0AEAVMiDestinationOptions@1@@Z`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180026470`

## callees

- `0x1800024fc`
- `0x180006630`
- `0x180024264`
- `0x180024c48`
- `0x180025b64`
- `0x180025ef0`
- `0x180025f90`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall mi::MiApplication::CreateSession<0>(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  void *v11; // [rsp+28h] [rbp-40h]
  _BYTE v12[8]; // [rsp+30h] [rbp-38h] BYREF
  std::_Ref_count_base *v13; // [rsp+38h] [rbp-30h]

  v8 = std::enable_shared_from_this<mi::MiSession>::shared_from_this(a1, v12);
  v11 = operator new(0x138u);
  v9 = std::_Ref_count_obj2<mi::MiSession>::_Ref_count_obj2<mi::MiSession>(v11, v8, a3);
  *a2 = 0;
  a2[1] = 0;
  std::shared_ptr<mi::MiSession>::_Set_ptr_rep_and_enable_shared<mi::MiSession>(a2, v9 + 16, v9);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  mi::MiSession::Initialize(*a2, 0, a4, a5, 3);
  return a2;
}

```

## disassembly

```asm
0x180025f90  mov     [rsp+arg_8], rdx
0x180025f95  push    rbx
0x180025f96  push    rbp
0x180025f97  push    rsi
0x180025f98  push    rdi
0x180025f99  sub     rsp, 48h
0x180025f9d  mov     rbp, r9
0x180025fa0  mov     rdi, r8
0x180025fa3  mov     rsi, rdx
0x180025fa6  mov     [rsp+68h+var_48], 0
0x180025fae  lea     rdx, [rsp+68h+var_38]
0x180025fb3  call    ?shared_from_this@?$enable_shared_from_this@VMiSession@mi@@@std@@QEAA?AV?$shared_ptr@VMiSession@mi@@@2@XZ; std::enable_shared_from_this<mi::MiSession>::shared_from_this(void)
0x180025fb8  mov     rbx, rax
0x180025fbb  mov     ecx, 138h; Size
0x180025fc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025fc5  mov     [rsp+68h+var_40], rax
0x180025fca  mov     r8, rdi
0x180025fcd  mov     rdx, rbx
0x180025fd0  mov     rcx, rax
0x180025fd3  call    ??$?0V?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@?$_Ref_count_obj2@VMiSession@mi@@@std@@QEAA@$$QEAV?$shared_ptr@VMiApplication@mi@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Ref_count_obj2<mi::MiSession>::_Ref_count_obj2<mi::MiSession>(std::shared_ptr<mi::MiApplication> &&,std::wstring const &)
0x180025fd8  nop
0x180025fd9  mov     qword ptr [rsi], 0
0x180025fe0  mov     qword ptr [rsi+8], 0
0x180025fe8  lea     rdx, [rax+10h]
0x180025fec  mov     r8, rax
0x180025fef  mov     rcx, rsi
0x180025ff2  call    ??$_Set_ptr_rep_and_enable_shared@VMiSession@mi@@@?$shared_ptr@VMiSession@mi@@@std@@AEAAXQEAVMiSession@mi@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<mi::MiSession>::_Set_ptr_rep_and_enable_shared<mi::MiSession>(mi::MiSession * const,std::_Ref_count_base * const)
0x180025ff7  mov     [rsp+68h+var_48], 3
0x180025fff  mov     rcx, [rsp+68h+var_30]; this
0x180026004  test    rcx, rcx
0x180026007  jz      short loc_18002600E
0x180026009  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002600e  mov     r9, [rsp+68h+arg_20]
0x180026016  mov     r8, rbp
0x180026019  xor     edx, edx
0x18002601b  mov     rcx, [rsi]
0x18002601e  call    ?Initialize@MiSession@mi@@IEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVMiDestinationOptions@2@@Z; mi::MiSession::Initialize(wchar_t const *,std::wstring const &,mi::MiDestinationOptions &)
0x180026023  mov     rax, rsi
0x180026026  add     rsp, 48h
0x18002602a  pop     rdi
0x18002602b  pop     rsi
0x18002602c  pop     rbp
0x18002602d  pop     rbx
0x18002602e  retn
```
