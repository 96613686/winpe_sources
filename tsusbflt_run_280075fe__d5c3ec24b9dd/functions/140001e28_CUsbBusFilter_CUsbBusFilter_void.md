# CUsbBusFilter::~CUsbBusFilter(void)

- ea: `0x140001e28`
- end: `0x140001e78`
- name: `??1CUsbBusFilter@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(CUsbBusFilter *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400029e4`
- `0x140012440`

## callees

- `0x140001e28`
- `0x14000aa30`

## pseudocode

```c
void __fastcall CUsbBusFilter::~CUsbBusFilter(CUsbBusFilter *this)
{
  __int64 v1; // rdx

  v1 = *((_QWORD *)this + 6);
  if ( v1 )
  {
    ((void (__fastcall *)(struct _LIST_ENTRY *, __int64, _QWORD, __int64, const char *))WPP_MAIN_CB.Queue.ListEntry.Flink[103].Flink)(
      WPP_MAIN_CB.Queue.ListEntry.Blink,
      v1,
      0,
      308,
      "clientcore\\termsrv\\devices\\urbdr\\busfilter\\cusbbusfilter.cpp");
    *((_QWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x140001e28  push    rbx
0x140001e2a  sub     rsp, 30h
0x140001e2e  mov     rdx, [rcx+30h]
0x140001e32  mov     rbx, rcx
0x140001e35  test    rdx, rdx
0x140001e38  jz      short loc_140001E71
0x140001e3a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001e41  lea     rcx, aClientcoreTerm_1; "clientcore\\termsrv\\devices\\urbdr\\bu"...
0x140001e48  mov     [rsp+38h+var_18], rcx
0x140001e4d  mov     r9d, 134h
0x140001e53  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001e5a  xor     r8d, r8d
0x140001e5d  mov     rax, [rax+670h]
0x140001e64  call    _guard_dispatch_icall
0x140001e69  mov     qword ptr [rbx+30h], 0
0x140001e71  add     rsp, 30h
0x140001e75  pop     rbx
0x140001e76  retn
```
