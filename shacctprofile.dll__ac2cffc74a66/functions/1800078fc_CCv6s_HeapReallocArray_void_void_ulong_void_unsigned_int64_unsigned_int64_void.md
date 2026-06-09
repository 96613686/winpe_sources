# CCv6s_HeapReallocArray<void *>(void *,ulong,void *,unsigned __int64,unsigned __int64,void * * *)

- ea: `0x1800078fc`
- end: `0x180007979`
- name: `??$CCv6s_HeapReallocArray@PEAX@@YAJPEAXK0_K1PEAPEAPEAX@Z`
- size: `125`
- prototype: `__int64 __fastcall(void *, __int64, void *, __int64, unsigned __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800079f0`
- `0x180007bb4`

## callees

- `0x180002230`
- `0x1800078fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007948`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007948`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000793d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000793d`

## pseudocode

```c
__int64 __fastcall CCv6s_HeapReallocArray<void *>(
        void *a1,
        __int64 a2,
        void *a3,
        __int64 a4,
        unsigned __int64 a5,
        _QWORD *a6)
{
  SIZE_T v6; // rax
  LPVOID v7; // rax

  v6 = 8 * a5;
  if ( !is_mul_ok(8u, a5) )
    return 2147942934LL;
  if ( a3 )
    v7 = HeapReAlloc(a1, 8u, a3, v6);
  else
    v7 = HeapAlloc(a1, 8u, v6);
  if ( !v7 )
    return 2147942414LL;
  *a6 = v7;
  return 0;
}

```

## disassembly

```asm
0x1800078fc  push    rbx
0x1800078fe  sub     rsp, 30h
0x180007902  mov     rax, cs:__security_cookie
0x180007909  xor     rax, rsp
0x18000790c  mov     [rsp+38h+var_10], rax
0x180007911  mov     rax, [rsp+38h+arg_20]
0x180007916  mov     r10d, 8
0x18000791c  mov     rbx, [rsp+38h+arg_28]
0x180007921  mul     r10
0x180007924  mov     [rsp+38h+var_18], 0
0x18000792d  test    rdx, rdx
0x180007930  jnz     short loc_180007961
0x180007932  mov     edx, r10d; dwFlags
0x180007935  test    r8, r8
0x180007938  jz      short loc_180007945
0x18000793a  mov     r9, rax; dwBytes
0x18000793d  call    cs:__imp_HeapReAlloc
0x180007943  jmp     short loc_18000794E
0x180007945  mov     r8, rax; dwBytes
0x180007948  call    cs:__imp_HeapAlloc
0x18000794e  test    rax, rax
0x180007951  jz      short loc_18000795A
0x180007953  mov     [rbx], rax
0x180007956  xor     eax, eax
0x180007958  jmp     short loc_180007966
0x18000795a  mov     eax, 8007000Eh
0x18000795f  jmp     short loc_180007966
0x180007961  mov     eax, 80070216h
0x180007966  mov     rcx, [rsp+38h+var_10]
0x18000796b  xor     rcx, rsp; StackCookie
0x18000796e  call    __security_check_cookie
0x180007973  add     rsp, 30h
0x180007977  pop     rbx
0x180007978  retn
```
