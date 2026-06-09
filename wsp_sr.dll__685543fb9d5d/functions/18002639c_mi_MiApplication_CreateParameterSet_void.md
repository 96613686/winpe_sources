# mi::MiApplication::CreateParameterSet(void)

- ea: `0x18002639c`
- end: `0x180026467`
- name: `?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ`
- size: `203`
- prototype: ``
- caller_count: `16`
- callee_count: `8`
- tags: ``

## callers

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

## callees

- `0x18000299b`
- `0x180006630`
- `0x1800087cc`
- `0x180025b64`
- `0x180026194`
- `0x18002639c`
- `0x180026b98`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall mi::MiApplication::CreateParameterSet(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  int v6; // eax
  __int64 v8; // [rsp+38h] [rbp-40h] BYREF
  std::_Ref_count_base *v9; // [rsp+40h] [rbp-38h]
  _BYTE pExceptionObject[48]; // [rsp+48h] [rbp-30h] BYREF

  v4 = std::enable_shared_from_this<mi::MiSession>::shared_from_this(a1, &v8);
  mi::MiInstance::MiInstance(a2, v4);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  mi::MiObjectPtr<_MI_Instance>::Close(a2);
  if ( a1 == -16 || (v5 = *(_QWORD *)(a1 + 32)) == 0 )
  {
    if ( a2 )
      *a2 = 0;
    v6 = 4;
LABEL_10:
    std::system_error::system_error(
      (std::system_error *)pExceptionObject,
      v6,
      (const struct std::error_category *)&mi::mi_category_var,
      "MI_Application_NewParameterSet failed.");
    throw (std::system_error *)pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD *))(v5 + 24))(a1 + 16, L"Parameters", 0, a2);
  if ( v6 )
    goto LABEL_10;
  return a2;
}

```

## disassembly

```asm
0x18002639c  mov     rax, rsp
0x18002639f  mov     [rax+8], rbx
0x1800263a3  mov     [rax+10h], rdx
0x1800263a7  push    rdi
0x1800263a8  sub     rsp, 70h
0x1800263ac  mov     rbx, rdx
0x1800263af  mov     rdi, rcx
0x1800263b2  mov     dword ptr [rax-48h], 0
0x1800263b9  lea     rdx, [rax-40h]
0x1800263bd  call    ?shared_from_this@?$enable_shared_from_this@VMiSession@mi@@@std@@QEAA?AV?$shared_ptr@VMiSession@mi@@@2@XZ; std::enable_shared_from_this<mi::MiSession>::shared_from_this(void)
0x1800263c2  mov     rdx, rax
0x1800263c5  mov     rcx, rbx
0x1800263c8  call    ??0MiInstance@mi@@QEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@@Z; mi::MiInstance::MiInstance(std::shared_ptr<mi::MiApplication> const &)
0x1800263cd  mov     [rsp+78h+var_48], 1
0x1800263d5  mov     rcx, [rsp+78h+var_38]; this
0x1800263da  test    rcx, rcx
0x1800263dd  jz      short loc_1800263E4
0x1800263df  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800263e4  mov     rcx, rbx
0x1800263e7  call    ?Close@?$MiObjectPtr@U_MI_Instance@@@mi@@AEAAXXZ; mi::MiObjectPtr<_MI_Instance>::Close(void)
0x1800263ec  lea     rcx, [rdi+10h]
0x1800263f0  test    rcx, rcx
0x1800263f3  jz      short loc_18002642A
0x1800263f5  mov     rax, [rcx+10h]
0x1800263f9  test    rax, rax
0x1800263fc  jz      short loc_18002642A
0x1800263fe  mov     r9, rbx
0x180026401  xor     r8d, r8d
0x180026404  lea     rdx, aParameters; "Parameters"
0x18002640b  mov     rax, [rax+18h]
0x18002640f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026414  test    eax, eax
0x180026416  jnz     short loc_18002643B
0x180026418  mov     rax, rbx
0x18002641b  mov     rbx, [rsp+78h+arg_0]
0x180026423  add     rsp, 70h
0x180026427  pop     rdi
0x180026428  retn
0x18002642a  test    rbx, rbx
0x18002642d  jz      short loc_180026436
0x18002642f  mov     qword ptr [rbx], 0
0x180026436  mov     eax, 4
0x18002643b  lea     r9, aMiApplicationN_1; "MI_Application_NewParameterSet failed."
0x180026442  lea     r8, ?mi_category_var@mi@@3Vmi_error_categoryImpl@1@A; struct std::error_category *
0x180026449  mov     edx, eax; int
0x18002644b  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180026450  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x180026455  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18002645c  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180026461  call    _CxxThrowException_0
```
