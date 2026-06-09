# CCv6s_HeapReallocArray<void *>(void *,ulong,void *,unsigned __int64,unsigned __int64,void * * *)

- ea: `0x180003298`
- end: `0x180003315`
- name: `??$CCv6s_HeapReallocArray@PEAX@@YAJPEAXK0_K1PEAPEAPEAX@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003484`

## callees

- `0x180003298`
- `0x1800036c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800032e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800032e4`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800032d9`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800032d9`

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
0x180003298  push    rbx
0x18000329a  sub     rsp, 30h
0x18000329e  mov     rax, cs:__security_cookie
0x1800032a5  xor     rax, rsp
0x1800032a8  mov     [rsp+38h+var_10], rax
0x1800032ad  mov     rax, [rsp+38h+arg_20]
0x1800032b2  mov     r10d, 8
0x1800032b8  mov     rbx, [rsp+38h+arg_28]
0x1800032bd  mul     r10
0x1800032c0  mov     [rsp+38h+var_18], 0
0x1800032c9  test    rdx, rdx
0x1800032cc  jnz     short loc_1800032FD
0x1800032ce  mov     edx, r10d; dwFlags
0x1800032d1  test    r8, r8
0x1800032d4  jz      short loc_1800032E1
0x1800032d6  mov     r9, rax; dwBytes
0x1800032d9  call    cs:__imp_HeapReAlloc
0x1800032df  jmp     short loc_1800032EA
0x1800032e1  mov     r8, rax; dwBytes
0x1800032e4  call    cs:__imp_HeapAlloc
0x1800032ea  test    rax, rax
0x1800032ed  jz      short loc_1800032F6
0x1800032ef  mov     [rbx], rax
0x1800032f2  xor     eax, eax
0x1800032f4  jmp     short loc_180003302
0x1800032f6  mov     eax, 8007000Eh
0x1800032fb  jmp     short loc_180003302
0x1800032fd  mov     eax, 80070216h
0x180003302  mov     rcx, [rsp+38h+var_10]
0x180003307  xor     rcx, rsp; StackCookie
0x18000330a  call    __security_check_cookie
0x18000330f  add     rsp, 30h
0x180003313  pop     rbx
0x180003314  retn
```
