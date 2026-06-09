# mi::MiApplication::CreateInstance(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::shared_ptr<mi::MiSession const> const &)

- ea: `0x180025f80`
- end: `0x18002605d`
- name: `?CreateInstance@MiApplication@mi@@QEAA?AVMiInstance@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@5@@Z`
- size: `221`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180025f44`

## callees

- `0x18000296b`
- `0x1800065ec`
- `0x180008668`
- `0x180025844`
- `0x180025e64`
- `0x180025f80`
- `0x1800267a8`
- `0x18002d010`

## pseudocode

```c
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
0x180025f80  push    rbx
0x180025f82  push    rbp
0x180025f83  push    rsi
0x180025f84  push    rdi
0x180025f85  sub     rsp, 88h
0x180025f8c  mov     rbx, r9
0x180025f8f  mov     rsi, r8
0x180025f92  mov     rdi, rdx
0x180025f95  mov     rbp, rcx
0x180025f98  mov     [rsp+0A8h+var_70], rdx
0x180025f9d  mov     [rsp+0A8h+var_78], 0
0x180025fa5  lea     rdx, [rsp+0A8h+var_68]
0x180025faa  call    ?shared_from_this@?$enable_shared_from_this@VMiSession@mi@@@std@@QEAA?AV?$shared_ptr@VMiSession@mi@@@2@XZ; std::enable_shared_from_this<mi::MiSession>::shared_from_this(void)
0x180025faf  mov     r9b, 1
0x180025fb2  mov     r8, rbx
0x180025fb5  mov     rdx, rax
0x180025fb8  mov     rcx, rdi
0x180025fbb  call    ??0MiInstance@mi@@AEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$shared_ptr@$$CBVMiSession@mi@@@3@_N@Z; mi::MiInstance::MiInstance(std::shared_ptr<mi::MiApplication> const &,std::shared_ptr<mi::MiSession const> const &,bool)
0x180025fc0  mov     [rsp+0A8h+var_78], 1
0x180025fc8  mov     rcx, [rsp+0A8h+var_60]; this
0x180025fcd  test    rcx, rcx
0x180025fd0  jz      short loc_180025FD7
0x180025fd2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025fd7  mov     rcx, rdi
0x180025fda  call    ?Close@?$MiObjectPtr@U_MI_Instance@@@mi@@AEAAXXZ; mi::MiObjectPtr<_MI_Instance>::Close(void)
0x180025fdf  cmp     qword ptr [rsi+18h], 7
0x180025fe4  jbe     short loc_180025FE9
0x180025fe6  mov     rsi, [rsi]
0x180025fe9  lea     rcx, [rbp+10h]
0x180025fed  test    rcx, rcx
0x180025ff0  jz      short loc_180026020
0x180025ff2  mov     rax, [rcx+10h]
0x180025ff6  test    rax, rax
0x180025ff9  jz      short loc_180026020
0x180025ffb  mov     r9, rdi
0x180025ffe  xor     r8d, r8d
0x180026001  mov     rdx, rsi
0x180026004  mov     rax, [rax+18h]
0x180026008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002600d  test    eax, eax
0x18002600f  jnz     short loc_180026031
0x180026011  mov     rax, rdi
0x180026014  add     rsp, 88h
0x18002601b  pop     rdi
0x18002601c  pop     rsi
0x18002601d  pop     rbp
0x18002601e  pop     rbx
0x18002601f  retn
0x180026020  test    rdi, rdi
0x180026023  jz      short loc_18002602C
0x180026025  mov     qword ptr [rdi], 0
0x18002602c  mov     eax, 4
0x180026031  lea     r9, aMiApplicationN_0; "MI_Application_NewInstance failed."
0x180026038  lea     r8, ?mi_category_var@mi@@3Vmi_error_categoryImpl@1@A; struct std::error_category *
0x18002603f  mov     edx, eax; int
0x180026041  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x180026046  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18002604b  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180026052  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180026057  call    _CxxThrowException_0
```
