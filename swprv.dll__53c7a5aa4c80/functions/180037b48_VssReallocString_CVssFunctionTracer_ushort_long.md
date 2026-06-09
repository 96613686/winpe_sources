# VssReallocString(CVssFunctionTracer &,ushort *,long)

- ea: `0x180037b48`
- end: `0x180037bef`
- name: `?VssReallocString@@YAPEAGAEAVCVssFunctionTracer@@PEAGJ@Z`
- size: `167`
- prototype: `unsigned __int16 *(struct CVssFunctionTracer *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036160`

## callees

- `0x18000212c`
- `0x18003649c`
- `0x180037b48`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180037b6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180037b6d`

## pseudocode

```c
unsigned __int16 *__fastcall VssReallocString(struct CVssFunctionTracer *a1, unsigned __int16 *a2, int a3)
{
  unsigned __int16 *result; // rax
  _QWORD v5[3]; // [rsp+20h] [rbp-59h] BYREF
  int v6; // [rsp+38h] [rbp-41h]
  int v7; // [rsp+3Ch] [rbp-3Dh]
  int v8; // [rsp+40h] [rbp-39h]
  _BYTE v9[120]; // [rsp+48h] [rbp-31h] BYREF
  int v10; // [rsp+C0h] [rbp+47h]

  result = (unsigned __int16 *)CoTaskMemRealloc(a2, 2LL * (a3 + 1));
  if ( !result )
  {
    v6 = 133;
    v5[0] = L"base\\stor\\vss\\inc\\vs_str.hxx";
    v7 = 11;
    v8 = 255;
    v5[1] = L"VssReallocString";
    v5[2] = L"INCSTRH";
    v10 = 0x1000000;
    memset_0(v9, 0, sizeof(v9));
    CVssFunctionTracer::Throw(a1, (const struct CVssDebugInfo *)v5, -2147024882, L"Memory allocation error");
  }
  return result;
}

```

## disassembly

```asm
0x180037b48  mov     [rsp-8+arg_0], rbx
0x180037b4d  push    rbp
0x180037b4e  lea     rbp, [rsp-57h]
0x180037b53  sub     rsp, 0D0h
0x180037b5a  mov     r9, rdx
0x180037b5d  lea     eax, [r8+1]
0x180037b61  movsxd  rdx, eax
0x180037b64  mov     rbx, rcx
0x180037b67  add     rdx, rdx; cb
0x180037b6a  mov     rcx, r9; pv
0x180037b6d  call    cs:__imp_CoTaskMemRealloc
0x180037b73  test    rax, rax
0x180037b76  jnz     short loc_180037BDE
0x180037b78  lea     rax, aBaseStorVssInc_1; "base\\stor\\vss\\inc\\vs_str.hxx"
0x180037b7f  mov     [rbp+57h+var_98], 85h
0x180037b86  mov     [rbp+57h+var_B0], rax
0x180037b8a  lea     rcx, [rbp+57h+var_88]; void *
0x180037b8e  xor     edx, edx; Val
0x180037b90  mov     [rbp+57h+var_94], 0Bh
0x180037b97  lea     rax, aVssreallocstri; "VssReallocString"
0x180037b9e  mov     [rbp+57h+var_90], 0FFh
0x180037ba5  mov     [rbp+57h+var_A8], rax
0x180037ba9  lea     rax, aIncstrh; "INCSTRH"
0x180037bb0  mov     [rbp+57h+var_A0], rax
0x180037bb4  lea     r8d, [rdx+78h]; Size
0x180037bb8  mov     [rbp+57h+var_10], 1000000h
0x180037bbf  call    memset_0
0x180037bc4  lea     r9, aMemoryAllocati; "Memory allocation error"
0x180037bcb  mov     r8d, 8007000Eh
0x180037bd1  lea     rdx, [rbp+57h+var_B0]
0x180037bd5  mov     rcx, rbx
0x180037bd8  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x180037bde  mov     rbx, [rsp+0D0h+arg_0]
0x180037be6  add     rsp, 0D0h
0x180037bed  pop     rbp
0x180037bee  retn
```
