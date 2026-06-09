# common_flush_all

- ea: `0x10041ede4`
- end: `0x10041ee41`
- name: `common_flush_all`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10041eedc`
- `0x10041efb4`

## callees

- `0x10041ecfc`

## pseudocode

```c
__int64 __fastcall common_flush_all(char a1)
{
  __int64 result; // rax
  int v2; // [rsp+20h] [rbp-20h] BYREF
  int v3; // [rsp+24h] [rbp-1Ch] BYREF
  _QWORD v4[3]; // [rsp+28h] [rbp-18h] BYREF
  char v5; // [rsp+50h] [rbp+10h] BYREF
  char v6; // [rsp+58h] [rbp+18h] BYREF
  unsigned int v7; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v8; // [rsp+68h] [rbp+28h] BYREF

  v5 = a1;
  v8 = 0;
  v7 = 0;
  v4[0] = &v8;
  v4[1] = &v5;
  v4[2] = &v7;
  v2 = 8;
  v3 = 8;
  ((void (__fastcall *)(char *, int *, _QWORD *, int *))_crt_seh_guarded_call_void_::operator()__lambda_886d6c58226a84441f68b9f2b8217b83___lambda_ab61a845afdef5b7c387490eaf3616ee_____lambda_f7f22ab5edc0698d5f6905b0d3f44752___)(
    &v6,
    &v3,
    v4,
    &v2);
  result = v7;
  if ( v5 )
    return v8;
  return result;
}

```

## disassembly

```asm
0x10041ede4  mov     [rsp-8+arg_0], cl
0x10041ede8  push    rbp
0x10041ede9  mov     rbp, rsp
0x10041edec  sub     rsp, 40h
0x10041edf0  and     [rbp+arg_18], 0
0x10041edf4  lea     rax, [rbp+arg_18]
0x10041edf8  and     [rbp+arg_10], 0
0x10041edfc  lea     r9, [rbp+var_20]
0x10041ee00  mov     [rbp+var_18], rax
0x10041ee04  lea     r8, [rbp+var_18]
0x10041ee08  lea     rax, [rbp+arg_0]
0x10041ee0c  mov     [rbp+var_10], rax
0x10041ee10  lea     rdx, [rbp+var_1C]
0x10041ee14  lea     rax, [rbp+arg_10]
0x10041ee18  mov     [rbp+var_8], rax
0x10041ee1c  lea     rcx, [rbp+arg_8]
0x10041ee20  mov     eax, 8
0x10041ee25  mov     [rbp+var_20], eax
0x10041ee28  mov     [rbp+var_1C], eax
0x10041ee2b  call    __crt_seh_guarded_call_void___operator____lambda_886d6c58226a84441f68b9f2b8217b83___lambda_ab61a845afdef5b7c387490eaf3616ee_____lambda_f7f22ab5edc0698d5f6905b0d3f44752___
0x10041ee30  cmp     [rbp+arg_0], 0
0x10041ee34  mov     eax, [rbp+arg_10]
0x10041ee37  cmovnz  eax, [rbp+arg_18]
0x10041ee3b  add     rsp, 40h
0x10041ee3f  pop     rbp
0x10041ee40  retn
```
