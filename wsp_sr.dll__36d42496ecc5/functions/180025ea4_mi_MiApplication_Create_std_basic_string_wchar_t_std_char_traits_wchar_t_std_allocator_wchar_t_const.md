# mi::MiApplication::Create(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180025ea4`
- end: `0x180025f3e`
- name: `?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `154`
- prototype: `__int64 *__fastcall(__int64 *, const MI_Char *)`
- caller_count: `33`
- callee_count: `5`
- tags: ``

## callers

- `0x180005db8`
- `0x180009df4`
- `0x180009f9c`
- `0x18000a16c`
- `0x18000a354`
- `0x18000a508`
- `0x18000a6a8`
- `0x18000a89c`
- `0x18000aa28`
- `0x18000abc4`
- `0x18000ad64`
- `0x18000aec8`
- `0x18000b174`
- `0x18000b328`
- `0x18000cfa4`
- `0x18000ed90`
- `0x18000efc0`
- `0x18000f290`
- `0x180011e78`
- `0x1800126cc`
- `0x180013a5c`
- `0x180014540`
- `0x1800154a4`
- `0x1800162b8`
- `0x180016568`
- `0x1800167c8`
- `0x18001935c`
- `0x180019cb8`
- `0x1800225cc`
- `0x180022798`
- `0x18002295c`
- `0x180022b20`
- `0x180022ce4`

## callees

- `0x18000296b`
- `0x180008668`
- `0x1800241e4`
- `0x180025d10`
- `0x180025ea4`

## import_xrefs

- `mi!MI_Application_InitializeV1` at `0x180025ef4`
- `mi!MI_Application_InitializeV1` at `0x180025ef4`

## pseudocode

```c
__int64 *__fastcall mi::MiApplication::Create(__int64 *a1, const MI_Char *a2)
{
  __int64 v4; // rsi
  MI_Result v5; // eax
  _BYTE pExceptionObject[48]; // [rsp+28h] [rbp-30h] BYREF

  std::make_shared<mi::MiApplication,mi::MiApplication::private_make_shared_tag>(a1);
  v4 = *a1;
  mi::MiObject<_MI_Application>::Close(*a1 + 16);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const MI_Char **)a2;
  v5 = MI_Application_InitializeV1(0, a2, 0, (MI_Application *)(v4 + 16));
  if ( v5 )
  {
    std::system_error::system_error(
      (std::system_error *)pExceptionObject,
      v5,
      (const struct std::error_category *)&mi::mi_category_var,
      "MI_Application_Initialize failed");
    throw (std::system_error *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x180025ea4  mov     rax, rsp
0x180025ea7  mov     [rax+10h], rbx
0x180025eab  mov     [rax+18h], rsi
0x180025eaf  mov     [rax+8], rcx
0x180025eb3  push    rdi
0x180025eb4  sub     rsp, 50h
0x180025eb8  mov     rbx, rdx
0x180025ebb  mov     rdi, rcx
0x180025ebe  mov     dword ptr [rax-38h], 0
0x180025ec5  call    ??$make_shared@VMiApplication@mi@@Uprivate_make_shared_tag@12@@std@@YA?AV?$shared_ptr@VMiApplication@mi@@@0@$$QEAUprivate_make_shared_tag@MiApplication@mi@@@Z; std::make_shared<mi::MiApplication,mi::MiApplication::private_make_shared_tag>(mi::MiApplication::private_make_shared_tag &&)
0x180025eca  mov     [rsp+58h+var_38], 1
0x180025ed2  mov     rsi, [rdi]
0x180025ed5  lea     rcx, [rsi+10h]
0x180025ed9  call    ?Close@?$MiObject@U_MI_Application@@@mi@@AEAAXXZ; mi::MiObject<_MI_Application>::Close(void)
0x180025ede  cmp     qword ptr [rbx+18h], 7
0x180025ee3  jbe     short loc_180025EE8
0x180025ee5  mov     rbx, [rbx]
0x180025ee8  lea     r9, [rsi+10h]; application
0x180025eec  xor     r8d, r8d; extendedError
0x180025eef  mov     rdx, rbx; applicationID
0x180025ef2  xor     ecx, ecx; flags
0x180025ef4  call    cs:__imp_MI_Application_InitializeV1
0x180025efa  test    eax, eax
0x180025efc  jz      short loc_180025F2A
0x180025efe  lea     r9, aMiApplicationI_0; "MI_Application_Initialize failed"
0x180025f05  lea     r8, ?mi_category_var@mi@@3Vmi_error_categoryImpl@1@A; struct std::error_category *
0x180025f0c  mov     edx, eax; int
0x180025f0e  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180025f13  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x180025f18  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180025f1f  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180025f24  call    _CxxThrowException_0
0x180025f2a  mov     rax, rdi
0x180025f2d  mov     rbx, [rsp+58h+arg_8]
0x180025f32  mov     rsi, [rsp+58h+arg_10]
0x180025f37  add     rsp, 50h
0x180025f3b  pop     rdi
0x180025f3c  retn
```
