# mi::MiApplication::Create(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800261d4`
- end: `0x180026274`
- name: `?Create@MiApplication@mi@@SA?AV?$shared_ptr@VMiApplication@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `160`
- prototype: ``
- caller_count: `33`
- callee_count: `5`
- tags: ``

## callers

- `0x180005df8`
- `0x180009f4c`
- `0x18000a0f4`
- `0x18000a2c4`
- `0x18000a4b0`
- `0x18000a664`
- `0x18000a804`
- `0x18000aa00`
- `0x18000ab90`
- `0x18000ad2c`
- `0x18000aecc`
- `0x18000b030`
- `0x18000b2dc`
- `0x18000b494`
- `0x18000cec8`
- `0x18000ed64`
- `0x18000ef94`
- `0x18000f264`
- `0x180011d40`
- `0x180012594`
- `0x180013964`
- `0x180014450`
- `0x180015358`
- `0x180016170`
- `0x180016424`
- `0x180016684`
- `0x180019388`
- `0x180019cf0`
- `0x180022788`
- `0x180022958`
- `0x180022b1c`
- `0x180022ce0`
- `0x180022ea4`

## callees

- `0x18000299b`
- `0x1800087cc`
- `0x1800244c4`
- `0x180026038`
- `0x1800261d4`

## import_xrefs

- `mi!MI_Application_InitializeV1` at `0x180026224`
- `mi!MI_Application_InitializeV1` at `0x180026224`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800261d4  mov     rax, rsp
0x1800261d7  mov     [rax+10h], rbx
0x1800261db  mov     [rax+18h], rsi
0x1800261df  mov     [rax+8], rcx
0x1800261e3  push    rdi
0x1800261e4  sub     rsp, 50h
0x1800261e8  mov     rbx, rdx
0x1800261eb  mov     rdi, rcx
0x1800261ee  mov     dword ptr [rax-38h], 0
0x1800261f5  call    ??$make_shared@VMiApplication@mi@@Uprivate_make_shared_tag@12@@std@@YA?AV?$shared_ptr@VMiApplication@mi@@@0@$$QEAUprivate_make_shared_tag@MiApplication@mi@@@Z; std::make_shared<mi::MiApplication,mi::MiApplication::private_make_shared_tag>(mi::MiApplication::private_make_shared_tag &&)
0x1800261fa  mov     [rsp+58h+var_38], 1
0x180026202  mov     rsi, [rdi]
0x180026205  lea     rcx, [rsi+10h]
0x180026209  call    ?Close@?$MiObject@U_MI_Application@@@mi@@AEAAXXZ; mi::MiObject<_MI_Application>::Close(void)
0x18002620e  cmp     qword ptr [rbx+18h], 7
0x180026213  jbe     short loc_180026218
0x180026215  mov     rbx, [rbx]
0x180026218  lea     r9, [rsi+10h]; application
0x18002621c  xor     r8d, r8d; extendedError
0x18002621f  mov     rdx, rbx; applicationID
0x180026222  xor     ecx, ecx; flags
0x180026224  call    cs:__imp_MI_Application_InitializeV1
0x18002622b  nop     dword ptr [rax+rax+00h]
0x180026230  test    eax, eax
0x180026232  jz      short loc_180026260
0x180026234  lea     r9, aMiApplicationI_0; "MI_Application_Initialize failed"
0x18002623b  lea     r8, ?mi_category_var@mi@@3Vmi_error_categoryImpl@1@A; struct std::error_category *
0x180026242  mov     edx, eax; int
0x180026244  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180026249  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18002624e  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x180026255  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18002625a  call    _CxxThrowException_0
0x180026260  mov     rax, rdi
0x180026263  mov     rbx, [rsp+58h+arg_8]
0x180026268  mov     rsi, [rsp+58h+arg_10]
0x18002626d  add     rsp, 50h
0x180026271  pop     rdi
0x180026272  retn
```
