# VssAllocString(CVssFunctionTracer &,unsigned __int64)

- ea: `0x1800171dc`
- end: `0x18001727b`
- name: `?VssAllocString@@YAPEAGAEAVCVssFunctionTracer@@_K@Z`
- size: `159`
- prototype: `unsigned __int16 *__fastcall(struct CVssFunctionTracer *, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016ff0`
- `0x18001c294`
- `0x1800275b4`

## callees

- `0x18000212c`
- `0x1800171dc`
- `0x18003649c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800171f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800171f9`

## pseudocode

```c
unsigned __int16 *__fastcall VssAllocString(struct CVssFunctionTracer *a1, __int64 a2)
{
  unsigned __int16 *result; // rax
  _QWORD v4[3]; // [rsp+20h] [rbp-59h] BYREF
  int v5; // [rsp+38h] [rbp-41h]
  int v6; // [rsp+3Ch] [rbp-3Dh]
  int v7; // [rsp+40h] [rbp-39h]
  _BYTE v8[120]; // [rsp+48h] [rbp-31h] BYREF
  int v9; // [rsp+C0h] [rbp+47h]

  result = (unsigned __int16 *)CoTaskMemAlloc(2 * a2 + 2);
  if ( !result )
  {
    v5 = 101;
    v4[0] = L"base\\stor\\vss\\inc\\vs_str.hxx";
    v6 = 11;
    v7 = 255;
    v4[1] = L"VssAllocString";
    v4[2] = L"INCSTRH";
    v9 = 0x1000000;
    memset_0(v8, 0, sizeof(v8));
    CVssFunctionTracer::Throw(a1, (const struct CVssDebugInfo *)v4, -2147024882, L"Memory allocation error");
  }
  return result;
}

```

## disassembly

```asm
0x1800171dc  mov     [rsp-8+arg_0], rbx
0x1800171e1  push    rbp
0x1800171e2  lea     rbp, [rsp-57h]
0x1800171e7  sub     rsp, 0D0h
0x1800171ee  mov     rbx, rcx
0x1800171f1  lea     rcx, ds:2[rdx*2]; cb
0x1800171f9  call    cs:__imp_CoTaskMemAlloc
0x1800171ff  test    rax, rax
0x180017202  jnz     short loc_18001726A
0x180017204  lea     rax, aBaseStorVssInc_1; "base\\stor\\vss\\inc\\vs_str.hxx"
0x18001720b  mov     [rbp+57h+var_98], 65h ; 'e'
0x180017212  mov     [rbp+57h+var_B0], rax
0x180017216  lea     rcx, [rbp+57h+var_88]; void *
0x18001721a  xor     edx, edx; Val
0x18001721c  mov     [rbp+57h+var_94], 0Bh
0x180017223  lea     rax, aVssallocstring; "VssAllocString"
0x18001722a  mov     [rbp+57h+var_90], 0FFh
0x180017231  mov     [rbp+57h+var_A8], rax
0x180017235  lea     rax, aIncstrh; "INCSTRH"
0x18001723c  mov     [rbp+57h+var_A0], rax
0x180017240  lea     r8d, [rdx+78h]; Size
0x180017244  mov     [rbp+57h+var_10], 1000000h
0x18001724b  call    memset_0
0x180017250  lea     r9, aMemoryAllocati; "Memory allocation error"
0x180017257  mov     r8d, 8007000Eh
0x18001725d  lea     rdx, [rbp+57h+var_B0]
0x180017261  mov     rcx, rbx
0x180017264  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x18001726a  mov     rbx, [rsp+0D0h+arg_0]
0x180017272  add     rsp, 0D0h
0x180017279  pop     rbp
0x18001727a  retn
```
