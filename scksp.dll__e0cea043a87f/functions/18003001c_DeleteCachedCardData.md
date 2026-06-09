# DeleteCachedCardData

- ea: `0x18003001c`
- end: `0x18003009d`
- name: `DeleteCachedCardData`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18002d504`
- `0x18002d61c`
- `0x18002e3bc`

## callees

- `0x180009e82`
- `0x180013c94`
- `0x1800308f4`
- `0x18003c240`

## pseudocode

```c
__int64 __fastcall DeleteCachedCardData(__int64 a1, size_t *a2)
{
  __int64 v5; // [rsp+20h] [rbp-258h] BYREF
  int v6; // [rsp+28h] [rbp-250h]
  _BYTE v7[8]; // [rsp+2Ch] [rbp-24Ch] BYREF
  unsigned __int16 v8[278]; // [rsp+34h] [rbp-244h] BYREF

  memset_0(v7, 0, 0x22Cu);
  v6 = 2;
  v5 = a1;
  StringCbCopyW(v8, 0x208u, a2);
  return MyCacheDeleteItem(&v5);
}

```

## disassembly

```asm
0x18003001c  mov     [rsp+arg_10], rbx
0x180030021  push    rdi
0x180030022  sub     rsp, 270h
0x180030029  mov     rax, cs:__security_cookie
0x180030030  xor     rax, rsp
0x180030033  mov     [rsp+278h+var_18], rax
0x18003003b  mov     rdi, rdx
0x18003003e  mov     rbx, rcx
0x180030041  xor     edx, edx; Val
0x180030043  lea     rcx, [rsp+278h+var_24C]; void *
0x180030048  mov     r8d, 22Ch; Size
0x18003004e  call    memset_0
0x180030053  mov     r8, rdi; unsigned __int16 *
0x180030056  mov     [rsp+278h+var_250], 2
0x18003005e  mov     edx, 208h; unsigned __int64
0x180030063  mov     [rsp+278h+var_258], rbx
0x180030068  lea     rcx, [rsp+278h+var_244]; unsigned __int16 *
0x18003006d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180030072  lea     rcx, [rsp+278h+var_258]
0x180030077  call    MyCacheDeleteItem
0x18003007c  mov     rcx, [rsp+278h+var_18]
0x180030084  xor     rcx, rsp; StackCookie
0x180030087  call    __security_check_cookie
0x18003008c  mov     rbx, [rsp+278h+arg_10]
0x180030094  add     rsp, 270h
0x18003009b  pop     rdi
0x18003009c  retn
```
