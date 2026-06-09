# mi::MiApplication::CreateInstance(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::shared_ptr<mi::MiSession const> const &)

- ea: `0x1800262b8`
- end: `0x180026396`
- name: `?CreateInstance@MiApplication@mi@@QEAA?AVMiInstance@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@5@@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18002627c`

## callees

- `0x18000299b`
- `0x180006630`
- `0x1800087cc`
- `0x180025b64`
- `0x180026194`
- `0x1800262b8`
- `0x180026aec`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall mi::MiApplication::CreateInstance(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4)
{
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // rax
  int v11; // eax
  _BYTE v13[8]; // [rsp+40h] [rbp-68h] BYREF
  std::_Ref_count_base *v14; // [rsp+48h] [rbp-60h]
  _BYTE pExceptionObject[88]; // [rsp+50h] [rbp-58h] BYREF

  v8 = std::enable_shared_from_this<mi::MiSession>::shared_from_this(a1, v13);
  LOBYTE(v9) = 1;
  mi::MiInstance::MiInstance(a2, v8, a4, v9);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  mi::MiObjectPtr<_MI_Instance>::Close(a2);
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  if ( a1 == -16 || (v10 = *(_QWORD *)(a1 + 32)) == 0 )
  {
    if ( a2 )
      *a2 = 0;
    v11 = 4;
LABEL_12:
    std::system_error::system_error(
      (std::system_error *)pExceptionObject,
      v11,
      (const struct std::error_category *)&mi::mi_category_var,
      "MI_Application_NewInstance failed.");
    throw (std::system_error *)pExceptionObject;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _QWORD *))(v10 + 24))(a1 + 16, a3, 0, a2);
  if ( v11 )
    goto LABEL_12;
  return a2;
}

```

## disassembly

```asm
0x1800262b8  push    rbx
0x1800262ba  push    rbp
0x1800262bb  push    rsi
0x1800262bc  push    rdi
0x1800262bd  sub     rsp, 88h
0x1800262c4  mov     rbx, r9
0x1800262c7  mov     rsi, r8
0x1800262ca  mov     rdi, rdx
0x1800262cd  mov     rbp, rcx
0x1800262d0  mov     [rsp+0A8h+var_70], rdx
0x1800262d5  mov     [rsp+0A8h+var_78], 0
0x1800262dd  lea     rdx, [rsp+0A8h+var_68]
0x1800262e2  call    ?shared_from_this@?$enable_shared_from_this@VMiSession@mi@@@std@@QEAA?AV?$shared_ptr@VMiSession@mi@@@2@XZ; std::enable_shared_from_this<mi::MiSession>::shared_from_this(void)
0x1800262e7  mov     r9b, 1
0x1800262ea  mov     r8, rbx
0x1800262ed  mov     rdx, rax
0x1800262f0  mov     rcx, rdi
0x1800262f3  call    ??0MiInstance@mi@@AEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@3@_N@Z; mi::MiInstance::MiInstance(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,bool)
0x1800262f8  mov     [rsp+0A8h+var_78], 1
0x180026300  mov     rcx, [rsp+0A8h+var_60]; this
0x180026305  test    rcx, rcx
0x180026308  jz      short loc_18002630F
0x18002630a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002630f  mov     rcx, rdi
0x180026312  call    ?Close@?$MiObjectPtr@U_MI_Instance@@@mi@@AEAAXXZ; mi::MiObjectPtr<_MI_Instance>::Close(void)
0x180026317  cmp     qword ptr [rsi+18h], 7
0x18002631c  jbe     short loc_180026321
0x18002631e  mov     rsi, [rsi]
0x180026321  lea     rcx, [rbp+10h]
0x180026325  test    rcx, rcx
0x180026328  jz      short loc_180026359
0x18002632a  mov     rax, [rcx+10h]
0x18002632e  test    rax, rax
0x180026331  jz      short loc_180026359
0x180026333  mov     r9, rdi
0x180026336  xor     r8d, r8d
0x180026339  mov     rdx, rsi
0x18002633c  mov     rax, [rax+18h]
0x180026340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026345  test    eax, eax
0x180026347  jnz     short loc_18002636A
0x180026349  mov     rax, rdi
0x18002634c  add     rsp, 88h
0x180026353  pop     rdi
0x180026354  pop     rsi
0x180026355  pop     rbp
0x180026356  pop     rbx
0x180026357  retn
0x180026359  test    rdi, rdi
0x18002635c  jz      short loc_180026365
0x18002635e  mov     qword ptr [rdi], 0
0x180026365  mov     eax, 4
0x18002636a  lea     r9, aMiApplicationN_0; "MI_Application_NewInstance failed."
0x180026371  lea     r8, ?mi_category_var@mi@@3Vmi_error_categoryImpl@1@A; struct std::error_category *
0x180026378  mov     edx, eax; int
0x18002637a  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x18002637f  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x180026384  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18002638b  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180026390  call    _CxxThrowException_0
```
