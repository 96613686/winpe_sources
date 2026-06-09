# mi::MiApplication::CreateSession(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180026470`
- end: `0x18002651c`
- name: `?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `172`
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

- `0x1800014e0`
- `0x1800058c8`
- `0x180006724`
- `0x180025f90`
- `0x180028160`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall mi::MiApplication::CreateSession(int a1, __int64 a2, int a3)
{
  _OWORD v7[2]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v8; // [rsp+60h] [rbp-58h]
  __int64 v9; // [rsp+68h] [rbp-50h]
  _BYTE v10[32]; // [rsp+70h] [rbp-48h] BYREF

  std::wstring::wstring(v10, byte_1800AA3F0);
  memset(v7, 0, sizeof(v7));
  v8 = 0;
  v9 = 0;
  mi::MiApplication::CreateSession<0>(a1, a2, a3, (unsigned int)v10, (__int64)v7);
  mi::MiDestinationOptions::~MiDestinationOptions((mi::MiDestinationOptions *)v7);
  std::wstring::_Tidy_deallocate(v10);
  return a2;
}

```

## disassembly

```asm
0x180026470  push    rbx
0x180026472  push    rsi
0x180026473  push    rdi
0x180026474  sub     rsp, 0A0h
0x18002647b  mov     rax, cs:__security_cookie
0x180026482  xor     rax, rsp
0x180026485  mov     [rsp+0B8h+var_28], rax
0x18002648d  mov     rdi, r8
0x180026490  mov     rsi, rdx
0x180026493  mov     rbx, rcx
0x180026496  mov     [rsp+0B8h+var_80], rdx
0x18002649b  lea     rdx, byte_1800AA3F0
0x1800264a2  lea     rcx, [rsp+0B8h+var_48]
0x1800264a7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800264ac  nop
0x1800264ad  xorps   xmm0, xmm0
0x1800264b0  movdqu  [rsp+0B8h+var_78], xmm0
0x1800264b6  xorps   xmm1, xmm1
0x1800264b9  xor     eax, eax
0x1800264bb  movups  [rsp+0B8h+var_68], xmm1
0x1800264c0  mov     [rsp+0B8h+var_58], rax
0x1800264c5  mov     [rsp+0B8h+var_50], rax
0x1800264ca  lea     rax, [rsp+0B8h+var_78]
0x1800264cf  mov     [rsp+0B8h+var_98], rax
0x1800264d4  lea     r9, [rsp+0B8h+var_48]
0x1800264d9  mov     r8, rdi
0x1800264dc  mov     rdx, rsi
0x1800264df  mov     rcx, rbx
0x1800264e2  call    ??$CreateSession@$0A@@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@0AEAVMiDestinationOptions@1@@Z; mi::MiApplication::CreateSession<0>(std::wstring const &,std::wstring const &,mi::MiDestinationOptions &)
0x1800264e7  nop
0x1800264e8  lea     rcx, [rsp+0B8h+var_78]; this
0x1800264ed  call    ??1MiDestinationOptions@mi@@QEAA@XZ; mi::MiDestinationOptions::~MiDestinationOptions(void)
0x1800264f2  nop
0x1800264f3  lea     rcx, [rsp+0B8h+var_48]
0x1800264f8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800264fd  mov     rax, rsi
0x180026500  mov     rcx, [rsp+0B8h+var_28]
0x180026508  xor     rcx, rsp; StackCookie
0x18002650b  call    __security_check_cookie
0x180026510  add     rsp, 0A0h
0x180026517  pop     rdi
0x180026518  pop     rsi
0x180026519  pop     rbx
0x18002651a  retn
```
