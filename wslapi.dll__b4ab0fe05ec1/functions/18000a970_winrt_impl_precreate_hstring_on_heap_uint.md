# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x18000a970`
- end: `0x18000aa78`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `264`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ab1c`

## callees

- `0x180001dc0`
- `0x1800029c6`
- `0x180002ac0`
- `0x180002b38`
- `0x180002b44`
- `0x18000a970`

## pseudocode

```c
struct winrt::impl::shared_hstring_header *__fastcall winrt::impl::precreate_hstring_on_heap(winrt::impl *this)
{
  __int64 v1; // rbx
  SIZE_T v2; // rsi
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *result; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int128 v6; // [rsp+28h] [rbp-30h]
  const char *v7; // [rsp+38h] [rbp-20h] BYREF
  char v8; // [rsp+40h] [rbp-18h]
  int v9; // [rsp+41h] [rbp-17h]
  __int16 v10; // [rsp+45h] [rbp-13h]
  char v11; // [rsp+47h] [rbp-11h]

  v1 = (unsigned int)this;
  v2 = 2LL * (unsigned int)this + 32;
  if ( v2 > 0xFFFFFFFF )
  {
    v7 = "length";
    v8 = 1;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v6 = 0;
    o___std_exception_copy_0(&v7);
    pExceptionObject = &std::logic_error::`vftable';
    throw (std::invalid_argument *)&pExceptionObject;
  }
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v2);
  if ( !result )
  {
    *((_QWORD *)&v6 + 1) = 0;
    *(_QWORD *)&v6 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  *(_DWORD *)result = 0;
  *((_DWORD *)result + 1) = v1;
  *((_QWORD *)result + 2) = (char *)result + 28;
  _InterlockedExchange((volatile __int32 *)result + 6, 1);
  *((_WORD *)result + v1 + 14) = 0;
  return result;
}

```

## disassembly

```asm
0x18000a970  push    rbp
0x18000a972  push    rbx
0x18000a973  push    rsi
0x18000a974  push    rdi
0x18000a975  mov     rbp, rsp
0x18000a978  sub     rsp, 58h
0x18000a97c  mov     rax, cs:__security_cookie
0x18000a983  xor     rax, rsp
0x18000a986  mov     [rbp+var_10], rax
0x18000a98a  mov     ebx, ecx
0x18000a98c  mov     eax, 0FFFFFFFFh
0x18000a991  lea     rsi, ds:20h[rbx*2]
0x18000a999  cmp     rsi, rax
0x18000a99c  jbe     short loc_18000A9F8
0x18000a99e  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000a9a5  xorps   xmm0, xmm0
0x18000a9a8  mov     [rbp+pExceptionObject], rax
0x18000a9ac  lea     rdx, [rbp+var_30]
0x18000a9b0  lea     rax, aLength; "length"
0x18000a9b7  mov     [rbp+var_20], rax
0x18000a9bb  lea     rcx, [rbp+var_20]
0x18000a9bf  mov     eax, 1
0x18000a9c4  mov     [rbp+var_18], al
0x18000a9c7  xor     eax, eax
0x18000a9c9  mov     [rbp+var_17], eax
0x18000a9cc  mov     [rbp+var_13], ax
0x18000a9d0  mov     [rbp+var_11], al
0x18000a9d3  movups  [rbp+var_30], xmm0
0x18000a9d7  call    _o___std_exception_copy_0
0x18000a9dc  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x18000a9e3  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18000a9ea  mov     [rbp+pExceptionObject], rax
0x18000a9ee  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000a9f2  call    _CxxThrowException_0
0x18000a9f8  call    WINRT_IMPL_GetProcessHeap
0x18000a9fd  mov     rcx, rax; hHeap
0x18000aa00  mov     r8, rsi; dwBytes
0x18000aa03  xor     edx, edx; dwFlags
0x18000aa05  call    WINRT_IMPL_HeapAlloc
0x18000aa0a  mov     rcx, rax
0x18000aa0d  test    rax, rax
0x18000aa10  jnz     short loc_18000AA40
0x18000aa12  xorps   xmm0, xmm0
0x18000aa15  lea     rax, aBadAllocation; "bad allocation"
0x18000aa1c  movups  [rbp+var_30], xmm0
0x18000aa20  mov     qword ptr [rbp+var_30], rax
0x18000aa24  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000aa2b  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000aa32  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000aa36  mov     [rbp+pExceptionObject], rax
0x18000aa3a  call    _CxxThrowException_0
0x18000aa40  mov     dword ptr [rax], 0
0x18000aa46  mov     [rax+4], ebx
0x18000aa49  add     rax, 1Ch
0x18000aa4d  mov     [rcx+10h], rax
0x18000aa51  mov     eax, 1
0x18000aa56  xchg    eax, [rcx+18h]
0x18000aa59  xor     eax, eax
0x18000aa5b  mov     [rcx+rbx*2+1Ch], ax
0x18000aa60  mov     rax, rcx
0x18000aa63  mov     rcx, [rbp+var_10]
0x18000aa67  xor     rcx, rsp; StackCookie
0x18000aa6a  call    __security_check_cookie
0x18000aa6f  add     rsp, 58h
0x18000aa73  pop     rdi
0x18000aa74  pop     rsi
0x18000aa75  pop     rbx
0x18000aa76  pop     rbp
0x18000aa77  retn
```
