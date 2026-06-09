# SclCreateKey

- ea: `0x1800014e8`
- end: `0x180001543`
- name: `SclCreateKey`
- size: `91`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int, __int64)`
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001a18`
- `0x180002cc8`
- `0x180003408`
- `0x18000505c`
- `0x180005144`
- `0x180007fb0`
- `0x180008e40`
- `0x180008ff0`
- `0x180009438`
- `0x18000952c`
- `0x18000ac28`
- `0x18000bc68`
- `0x18000dae0`
- `0x18000deec`

## callees

- `0x18000154c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000150c`
- `ntdll!RtlInitUnicodeString` at `0x18000150c`

## pseudocode

```c
__int64 __fastcall SclCreateKey(__int64 a1, const WCHAR *a2, unsigned int a3, __int64 a4)
{
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = 0;
  RtlInitUnicodeString(&v8, a2);
  return SclCreateKeyEx(a1, &v8, a3, 0, 0, a4);
}

```

## disassembly

```asm
0x1800014e8  mov     rax, rsp
0x1800014eb  mov     [rax+8], rbx
0x1800014ef  mov     [rax+10h], rsi
0x1800014f3  push    rdi
0x1800014f4  sub     rsp, 40h
0x1800014f8  mov     rsi, rcx
0x1800014fb  xorps   xmm0, xmm0
0x1800014fe  lea     rcx, [rax-18h]; DestinationString
0x180001502  mov     rbx, r9
0x180001505  movups  xmmword ptr [rax-18h], xmm0
0x180001509  mov     edi, r8d
0x18000150c  call    cs:__imp_RtlInitUnicodeString
0x180001512  xor     r9d, r9d
0x180001515  mov     [rsp+48h+var_20], rbx
0x18000151a  mov     r8d, edi
0x18000151d  mov     [rsp+48h+var_28], 0
0x180001526  lea     rdx, [rsp+48h+var_18]
0x18000152b  mov     rcx, rsi
0x18000152e  call    SclCreateKeyEx
0x180001533  mov     rbx, [rsp+48h+arg_0]
0x180001538  mov     rsi, [rsp+48h+arg_8]
0x18000153d  add     rsp, 40h
0x180001541  pop     rdi
0x180001542  retn
```
