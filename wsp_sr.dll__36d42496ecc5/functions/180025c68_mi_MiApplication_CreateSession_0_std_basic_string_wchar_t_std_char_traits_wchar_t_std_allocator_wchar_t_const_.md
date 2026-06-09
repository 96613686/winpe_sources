# mi::MiApplication::CreateSession<0>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,mi::MiDestinationOptions &)

- ea: `0x180025c68`
- end: `0x180025d08`
- name: `??$CreateSession@$0A@@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@0AEAVMiDestinationOptions@1@@Z`
- size: `160`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180026134`

## callees

- `0x1800024cc`
- `0x1800065ec`
- `0x180023f90`
- `0x180024958`
- `0x180025844`
- `0x180025bc8`
- `0x180025c68`

## pseudocode

```c
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
0x180025c68  mov     [rsp+arg_8], rdx
0x180025c6d  push    rbx
0x180025c6e  push    rbp
0x180025c6f  push    rsi
0x180025c70  push    rdi
0x180025c71  sub     rsp, 48h
0x180025c75  mov     rbp, r9
0x180025c78  mov     rdi, r8
0x180025c7b  mov     rsi, rdx
0x180025c7e  mov     [rsp+68h+var_48], 0
0x180025c86  lea     rdx, [rsp+68h+var_38]
0x180025c8b  call    ?shared_from_this@?$enable_shared_from_this@VMiSession@mi@@@std@@QEAA?AV?$shared_ptr@VMiSession@mi@@@2@XZ; std::enable_shared_from_this<mi::MiSession>::shared_from_this(void)
0x180025c90  mov     rbx, rax
0x180025c93  mov     ecx, 138h; Size
0x180025c98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025c9d  mov     [rsp+68h+var_40], rax
0x180025ca2  mov     r8, rdi
0x180025ca5  mov     rdx, rbx
0x180025ca8  mov     rcx, rax
0x180025cab  call    ??$?0V?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@?$_Ref_count_obj2@VMiSession@mi@@@std@@QEAA@$$QEAV?$shared_ptr@VMiApplication@mi@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Ref_count_obj2<mi::MiSession>::_Ref_count_obj2<mi::MiSession>(std::shared_ptr<mi::MiApplication> &&,std::wstring const &)
0x180025cb0  nop
0x180025cb1  mov     qword ptr [rsi], 0
0x180025cb8  mov     qword ptr [rsi+8], 0
0x180025cc0  lea     rdx, [rax+10h]
0x180025cc4  mov     r8, rax
0x180025cc7  mov     rcx, rsi
0x180025cca  call    ??$_Set_ptr_rep_and_enable_shared@VMiSession@mi@@@?$shared_ptr@VMiSession@mi@@@std@@AEAAXQEAVMiSession@mi@@QEAV_Ref_count_base@1@@Z; std::shared_ptr<mi::MiSession>::_Set_ptr_rep_and_enable_shared<mi::MiSession>(mi::MiSession * const,std::_Ref_count_base * const)
0x180025ccf  mov     [rsp+68h+var_48], 3
0x180025cd7  mov     rcx, [rsp+68h+var_30]; this
0x180025cdc  test    rcx, rcx
0x180025cdf  jz      short loc_180025CE6
0x180025ce1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025ce6  mov     r9, [rsp+68h+arg_20]
0x180025cee  mov     r8, rbp
0x180025cf1  xor     edx, edx
0x180025cf3  mov     rcx, [rsi]
0x180025cf6  call    ?Initialize@MiSession@mi@@IEAAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVMiDestinationOptions@2@@Z; mi::MiSession::Initialize(wchar_t const *,std::wstring const &,mi::MiDestinationOptions &)
0x180025cfb  mov     rax, rsi
0x180025cfe  add     rsp, 48h
0x180025d02  pop     rdi
0x180025d03  pop     rsi
0x180025d04  pop     rbp
0x180025d05  pop     rbx
0x180025d06  retn
```
