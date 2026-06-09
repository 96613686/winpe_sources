# mi::MiApplication::CreateParameterSet(void)

- ea: `0x180026064`
- end: `0x18002612e`
- name: `?CreateParameterSet@MiApplication@mi@@QEAA?AVMiInstance@2@XZ`
- size: `202`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `16`
- callee_count: `8`
- tags: ``

## callers

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

## callees

- `0x18000296b`
- `0x1800065ec`
- `0x180008668`
- `0x180025844`
- `0x180025e64`
- `0x180026064`
- `0x180026850`
- `0x18002d010`

## pseudocode

```c
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
0x180026064  mov     rax, rsp
0x180026067  mov     [rax+8], rbx
0x18002606b  mov     [rax+10h], rdx
0x18002606f  push    rdi
0x180026070  sub     rsp, 70h
0x180026074  mov     rbx, rdx
0x180026077  mov     rdi, rcx
0x18002607a  mov     dword ptr [rax-48h], 0
0x180026081  lea     rdx, [rax-40h]
0x180026085  call    ?shared_from_this@?$enable_shared_from_this@VMiSession@mi@@@std@@QEAA?AV?$shared_ptr@VMiSession@mi@@@2@XZ; std::enable_shared_from_this<mi::MiSession>::shared_from_this(void)
0x18002608a  mov     rdx, rax
0x18002608d  mov     rcx, rbx
0x180026090  call    ??0MiInstance@mi@@QEAA@AEBV?$shared_ptr@VMiApplication@mi@@@std@@@Z; mi::MiInstance::MiInstance(std::shared_ptr<mi::MiApplication> const &)
0x180026095  mov     [rsp+78h+var_48], 1
0x18002609d  mov     rcx, [rsp+78h+var_38]; this
0x1800260a2  test    rcx, rcx
0x1800260a5  jz      short loc_1800260AC
0x1800260a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800260ac  mov     rcx, rbx
0x1800260af  call    ?Close@?$MiObjectPtr@U_MI_Instance@@@mi@@AEAAXXZ; mi::MiObjectPtr<_MI_Instance>::Close(void)
0x1800260b4  lea     rcx, [rdi+10h]
0x1800260b8  test    rcx, rcx
0x1800260bb  jz      short loc_1800260F1
0x1800260bd  mov     rax, [rcx+10h]
0x1800260c1  test    rax, rax
0x1800260c4  jz      short loc_1800260F1
0x1800260c6  mov     r9, rbx
0x1800260c9  xor     r8d, r8d
0x1800260cc  lea     rdx, aParameters; "Parameters"
0x1800260d3  mov     rax, [rax+18h]
0x1800260d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260dc  test    eax, eax
0x1800260de  jnz     short loc_180026102
0x1800260e0  mov     rax, rbx
0x1800260e3  mov     rbx, [rsp+78h+arg_0]
0x1800260eb  add     rsp, 70h
0x1800260ef  pop     rdi
0x1800260f0  retn
0x1800260f1  test    rbx, rbx
0x1800260f4  jz      short loc_1800260FD
0x1800260f6  mov     qword ptr [rbx], 0
0x1800260fd  mov     eax, 4
0x180026102  lea     r9, aMiApplicationN_1; "MI_Application_NewParameterSet failed."
0x180026109  lea     r8, ?mi_category_var@mi@@3Vmi_error_categoryImpl@1@A; struct std::error_category *
0x180026110  mov     edx, eax; int
0x180026112  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180026117  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18002611c  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180026123  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180026128  call    _CxxThrowException_0
```
