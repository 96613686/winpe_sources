# fp_format_e

- ea: `0x100431de4`
- end: `0x100431ee0`
- name: `fp_format_e`
- size: `252`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, char, int, int, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x100431a44`
- `0x10043257c`

## callees

- `0x100431de4`
- `0x100431ee8`
- `0x100435374`
- `0x100435934`

## pseudocode

```c
__int64 __fastcall fp_format_e(
        _QWORD *a1,
        _BYTE *a2,
        __int64 a3,
        char *a4,
        rsize_t a5,
        int a6,
        char a7,
        int a8,
        int a9,
        __crt_cached_ptd_host *a10)
{
  int v12; // eax
  _BOOL8 v13; // r9
  _BOOL8 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 result; // rax
  __int64 v17; // r9
  int v18; // [rsp+30h] [rbp-28h]
  _DWORD v19[6]; // [rsp+40h] [rbp-18h] BYREF

  v12 = _acrt_fltout(*a1, a6 + 1, 1, (int)v19, a4, a5);
  v13 = v19[0] == 45;
  v14 = a6 > 0;
  v15 = a3 - v14 - v13;
  if ( a3 == -1 )
    v15 = -1;
  result = _acrt_fp_strflt_to_string(&a2[v13 + v14], v15, a6 + 1, (__int64)v19, v12, a9, a10);
  if ( (_DWORD)result )
  {
    *a2 = 0;
  }
  else
  {
    LOBYTE(v17) = a7;
    LOBYTE(v18) = 0;
    return fp_format_e_internal(a2, a3, (unsigned int)a6, v17, a8, v19, v18, a10);
  }
  return result;
}

```

## disassembly

```asm
0x100431de4  mov     r11, rsp
0x100431de7  mov     [r11+8], rbx
0x100431deb  mov     [r11+10h], rbp
0x100431def  mov     [r11+18h], rsi
0x100431df3  mov     [r11+20h], rdi
0x100431df7  push    r14
0x100431df9  sub     rsp, 50h
0x100431dfd  mov     rax, [rsp+58h+arg_20]
0x100431e05  mov     rsi, r8
0x100431e08  mov     ebp, [rsp+58h+arg_28]
0x100431e0f  mov     rdi, rdx
0x100431e12  mov     rcx, [rcx]; int
0x100431e15  mov     r8d, 1; int
0x100431e1b  mov     [r11-30h], rax
0x100431e1f  mov     [r11-38h], r9
0x100431e23  lea     r9, [r11-18h]; int
0x100431e27  lea     edx, [rbp+1]; int
0x100431e2a  call    __acrt_fltout
0x100431e2f  mov     r14, [rsp+58h+arg_48]
0x100431e37  lea     r8d, [rbp+1]
0x100431e3b  xor     r9d, r9d
0x100431e3e  mov     [rsp+58h+var_28], r14; __crt_cached_ptd_host *
0x100431e43  cmp     [rsp+58h+var_18], 2Dh ; '-'
0x100431e48  mov     r10d, eax
0x100431e4b  mov     eax, [rsp+58h+arg_40]
0x100431e52  mov     rdx, rsi
0x100431e55  setz    r9b
0x100431e59  mov     [rsp+58h+var_30], eax; int
0x100431e5d  xor     ecx, ecx
0x100431e5f  mov     [rsp+58h+var_38], r10d; int
0x100431e64  test    ebp, ebp
0x100431e66  setnle  cl
0x100431e69  sub     rdx, rcx
0x100431e6c  sub     rdx, r9
0x100431e6f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x100431e73  cmovz   rdx, rsi
0x100431e77  add     rcx, r9
0x100431e7a  add     rcx, rdi; void *
0x100431e7d  lea     r9, [rsp+58h+var_18]
0x100431e82  call    __acrt_fp_strflt_to_string
0x100431e87  test    eax, eax
0x100431e89  jz      short loc_100431E90
0x100431e8b  mov     byte ptr [rdi], 0
0x100431e8e  jmp     short loc_100431EC5
0x100431e90  mov     r9b, [rsp+58h+arg_30]
0x100431e98  lea     rax, [rsp+58h+var_18]
0x100431e9d  mov     [rsp+58h+var_20], r14
0x100431ea2  mov     r8d, ebp
0x100431ea5  mov     byte ptr [rsp+58h+var_28], 0
0x100431eaa  mov     rdx, rsi
0x100431ead  mov     qword ptr [rsp+58h+var_30], rax
0x100431eb2  mov     rcx, rdi
0x100431eb5  mov     eax, [rsp+58h+arg_38]
0x100431ebc  mov     [rsp+58h+var_38], eax
0x100431ec0  call    fp_format_e_internal
0x100431ec5  mov     rbx, [rsp+58h+arg_0]
0x100431eca  mov     rbp, [rsp+58h+arg_8]
0x100431ecf  mov     rsi, [rsp+58h+arg_10]
0x100431ed4  mov     rdi, [rsp+58h+arg_18]
0x100431ed9  add     rsp, 50h
0x100431edd  pop     r14
0x100431edf  retn
```
