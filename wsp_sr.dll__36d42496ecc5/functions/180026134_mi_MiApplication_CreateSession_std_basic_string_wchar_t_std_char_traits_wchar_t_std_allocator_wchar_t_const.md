# mi::MiApplication::CreateSession(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180026134`
- end: `0x1800261df`
- name: `?CreateSession@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z`
- size: `171`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
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

- `0x1800014e0`
- `0x180005890`
- `0x1800066d8`
- `0x180025c68`
- `0x180027db0`

## pseudocode

```c
_QWORD *__fastcall mi::MiApplication::CreateSession(__int64 a1, _QWORD *a2, __int64 a3)
{
  _OWORD v7[2]; // [rsp+40h] [rbp-78h] BYREF
  __int64 v8; // [rsp+60h] [rbp-58h]
  __int64 v9; // [rsp+68h] [rbp-50h]
  _BYTE v10[32]; // [rsp+70h] [rbp-48h] BYREF

  std::wstring::wstring((__int64)v10, (__int64)byte_1800AA410);
  memset(v7, 0, sizeof(v7));
  v8 = 0;
  v9 = 0;
  mi::MiApplication::CreateSession<0>(a1, a2, a3, (__int64)v10, (__int64)v7);
  mi::MiDestinationOptions::~MiDestinationOptions((mi::MiDestinationOptions *)v7);
  std::wstring::_Tidy_deallocate((__int64)v10);
  return a2;
}

```

## disassembly

```asm
0x180026134  push    rbx
0x180026136  push    rsi
0x180026137  push    rdi
0x180026138  sub     rsp, 0A0h
0x18002613f  mov     rax, cs:__security_cookie
0x180026146  xor     rax, rsp
0x180026149  mov     [rsp+0B8h+var_28], rax
0x180026151  mov     rdi, r8
0x180026154  mov     rsi, rdx
0x180026157  mov     rbx, rcx
0x18002615a  mov     [rsp+0B8h+var_80], rdx
0x18002615f  lea     rdx, byte_1800AA410
0x180026166  lea     rcx, [rsp+0B8h+var_48]
0x18002616b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x180026170  nop
0x180026171  xorps   xmm0, xmm0
0x180026174  movdqu  [rsp+0B8h+var_78], xmm0
0x18002617a  xorps   xmm1, xmm1
0x18002617d  xor     eax, eax
0x18002617f  movups  [rsp+0B8h+var_68], xmm1
0x180026184  mov     [rsp+0B8h+var_58], rax
0x180026189  mov     [rsp+0B8h+var_50], rax
0x18002618e  lea     rax, [rsp+0B8h+var_78]
0x180026193  mov     [rsp+0B8h+var_98], rax
0x180026198  lea     r9, [rsp+0B8h+var_48]
0x18002619d  mov     r8, rdi
0x1800261a0  mov     rdx, rsi
0x1800261a3  mov     rcx, rbx
0x1800261a6  call    ??$CreateSession@$0A@@MiApplication@mi@@QEAA?AV?$shared_ptr@VMiSession@mi@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@0AEAVMiDestinationOptions@1@@Z; mi::MiApplication::CreateSession<0>(std::wstring const &,std::wstring const &,mi::MiDestinationOptions &)
0x1800261ab  nop
0x1800261ac  lea     rcx, [rsp+0B8h+var_78]; this
0x1800261b1  call    ??1MiDestinationOptions@mi@@QEAA@XZ; mi::MiDestinationOptions::~MiDestinationOptions(void)
0x1800261b6  nop
0x1800261b7  lea     rcx, [rsp+0B8h+var_48]
0x1800261bc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800261c1  mov     rax, rsi
0x1800261c4  mov     rcx, [rsp+0B8h+var_28]
0x1800261cc  xor     rcx, rsp; StackCookie
0x1800261cf  call    __security_check_cookie
0x1800261d4  add     rsp, 0A0h
0x1800261db  pop     rdi
0x1800261dc  pop     rsi
0x1800261dd  pop     rbx
0x1800261de  retn
```
