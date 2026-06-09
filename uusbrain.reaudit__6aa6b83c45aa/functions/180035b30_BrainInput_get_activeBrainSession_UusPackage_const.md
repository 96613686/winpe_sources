# BrainInput::get_activeBrainSession(UusPackage const &)

- ea: `0x180035b30`
- end: `0x180035be9`
- name: `?get_activeBrainSession@BrainInput@@QEBAPEAXAEBVUusPackage@@@Z`
- size: `185`
- prototype: `void *__fastcall(BrainInput *__hidden this, const struct UusPackage *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180037064`

## callees

- `0x180028728`
- `0x180029344`
- `0x180029644`
- `0x180035b30`
- `0x180044848`
- `0x180047a30`

## string_xrefs

- `0x180035bc6`: `Requesting specific brain when we already did on the previous call.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrainInput::get_activeBrainSession(BrainInput *this, const struct UusPackage *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, _BYTE *, __int64, __int64 *); // rdi
  __int64 (__fastcall *v3)(_QWORD, _BYTE *, __int64, __int64 *); // rsi
  __int64 v4; // rbx
  __int64 v5; // rbx
  __int64 v7; // [rsp+30h] [rbp-58h] BYREF
  int v8; // [rsp+38h] [rbp-50h]
  int v9; // [rsp+3Ch] [rbp-4Ch]
  __int64 v10; // [rsp+40h] [rbp-48h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v12[32]; // [rsp+60h] [rbp-28h] BYREF

  v2 = (__int64 (__fastcall ***)(_QWORD, _BYTE *, __int64, __int64 *))*((_QWORD *)this + 2);
  v3 = **v2;
  if ( *((int *)this + 14) < 0 )
  {
    std::runtime_error::runtime_error(
      (std::runtime_error *)pExceptionObject,
      "Requesting specific brain when we already did on the previous call.");
    throw (std::runtime_error *)pExceptionObject;
  }
  v10 = 2307;
  v7 = 24;
  v8 = -1;
  v9 = 1;
  v4 = *((_QWORD *)this + 3);
  std::wstring::wstring(v12, (char *)a2 + 8);
  v5 = v3(v2, v12, v4, &v7);
  std::wstring::_Tidy_deallocate(v12);
  return v5;
}

```

## disassembly

```asm
0x180035b30  mov     r11, rsp
0x180035b33  mov     [r11+10h], rbx
0x180035b37  mov     [r11+18h], rsi
0x180035b3b  push    rdi
0x180035b3c  sub     rsp, 80h
0x180035b43  mov     rdi, [rcx+10h]
0x180035b47  mov     rax, [rdi]
0x180035b4a  mov     rsi, [rax]
0x180035b4d  mov     eax, [rcx+38h]
0x180035b50  shr     eax, 1Fh
0x180035b53  test    al, al
0x180035b55  jnz     short loc_180035BC6
0x180035b57  mov     qword ptr [r11-48h], 903h
0x180035b5f  mov     qword ptr [r11-58h], 18h
0x180035b67  mov     [rsp+88h+var_50], 0FFFFFFFFh
0x180035b6f  mov     [rsp+88h+var_4C], 1
0x180035b77  mov     rbx, [rcx+18h]
0x180035b7b  add     rdx, 8
0x180035b7f  lea     rcx, [r11-28h]
0x180035b83  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180035b88  nop
0x180035b89  lea     r9, [rsp+88h+var_58]
0x180035b8e  mov     r8, rbx
0x180035b91  lea     rdx, [rsp+88h+var_28]
0x180035b96  mov     rcx, rdi
0x180035b99  mov     rax, rsi
0x180035b9c  call    _guard_dispatch_icall
0x180035ba1  mov     rbx, rax
0x180035ba4  lea     rcx, [rsp+88h+var_28]
0x180035ba9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035bae  mov     rax, rbx
0x180035bb1  lea     r11, [rsp+88h+var_8]
0x180035bb9  mov     rbx, [r11+18h]
0x180035bbd  mov     rsi, [r11+20h]
0x180035bc1  mov     rsp, r11
0x180035bc4  pop     rdi
0x180035bc5  retn
0x180035bc6  lea     rdx, aRequestingSpec; "Requesting specific brain when we alrea"...
0x180035bcd  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180035bd2  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180035bd7  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180035bde  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180035be3  call    _CxxThrowException
```
