# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007094`
- end: `0x18000717f`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details **this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a8b0`
- `0x18000bc04`
- `0x18000bc38`

## callees

- `0x180007094`
- `0x180007188`
- `0x18000740c`
- `0x180008afc`
- `0x18000bfc8`
- `0x18000c89c`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details **this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned __int64 v11; // rdx
  void *v12; // rdx
  void *v13[2]; // [rsp+30h] [rbp-58h] BYREF
  wil::details *v14[2]; // [rsp+40h] [rbp-48h] BYREF

  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal((wil::details_abi::RawUsageIndex *)this, a2, a3, a4, a5, a6) )
    return 1;
  v11 = a3 + a5 + 32;
  if ( this[3] )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(this + 3), v11);
  }
  else
  {
    *(_OWORD *)v13 = 0;
    *(_OWORD *)v14 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v13, v11 + 10) )
    {
      wil::details_abi::RawUsageIndex::SetBuffer(
        (wil::details_abi::RawUsageIndex *)this,
        v13[0],
        0,
        (char *)v14[0] - (char *)v13[0]);
      wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(this + 6, &v14[1]);
      *((_BYTE *)this + 58) = 1;
    }
    if ( v14[1] )
      wil::details::FreeProcessHeap(v14[1], v12);
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(
           (wil::details_abi::RawUsageIndex *)this,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180007094  push    rbx
0x180007096  push    rbp
0x180007097  push    rsi
0x180007098  push    rdi
0x180007099  push    r12
0x18000709b  push    r14
0x18000709d  push    r15
0x18000709f  sub     rsp, 50h
0x1800070a3  mov     r12d, [rsp+88h+arg_28]
0x1800070ab  mov     r14, r9
0x1800070ae  mov     rbp, [rsp+88h+arg_20]
0x1800070b6  mov     rsi, r8
0x1800070b9  mov     [rsp+88h+var_60], r12d; unsigned int
0x1800070be  mov     r15, rdx
0x1800070c1  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x1800070c6  mov     rbx, rcx
0x1800070c9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800070ce  test    al, al
0x1800070d0  jz      short loc_1800070D9
0x1800070d2  mov     al, 1
0x1800070d4  jmp     loc_180007170
0x1800070d9  lea     rdx, [rbp+20h]
0x1800070dd  add     rdx, rsi; unsigned __int64
0x1800070e0  cmp     qword ptr [rbx+18h], 0
0x1800070e5  jnz     short loc_180007146
0x1800070e7  xorps   xmm0, xmm0
0x1800070ea  lea     rcx, [rsp+88h+var_58]; this
0x1800070ef  xorps   xmm1, xmm1
0x1800070f2  add     rdx, 0Ah; unsigned __int64
0x1800070f6  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x1800070fc  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x180007102  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007107  test    al, al
0x180007109  jz      short loc_180007135
0x18000710b  mov     rdx, [rsp+88h+var_58]; void *
0x180007110  xor     r8d, r8d; unsigned __int64
0x180007113  mov     r9, [rsp+88h+var_48]
0x180007118  mov     rcx, rbx; this
0x18000711b  sub     r9, rdx; unsigned __int64
0x18000711e  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180007123  lea     rcx, [rbx+30h]
0x180007127  lea     rdx, [rsp+88h+var_48+8]
0x18000712c  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180007131  mov     byte ptr [rbx+3Ah], 1
0x180007135  mov     rcx, [rsp+88h+var_48+8]; this
0x18000713a  test    rcx, rcx
0x18000713d  jz      short loc_180007155
0x18000713f  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007144  jmp     short loc_180007155
0x180007146  cmp     byte ptr [rbx+3Ah], 0
0x18000714a  jz      short loc_180007155
0x18000714c  lea     rcx, [rbx+18h]; this
0x180007150  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007155  mov     [rsp+88h+var_60], r12d; unsigned int
0x18000715a  mov     r9, r14; void *
0x18000715d  mov     r8, rsi; unsigned __int64
0x180007160  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x180007165  mov     rdx, r15; void *
0x180007168  mov     rcx, rbx; this
0x18000716b  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007170  add     rsp, 50h
0x180007174  pop     r15
0x180007176  pop     r14
0x180007178  pop     r12
0x18000717a  pop     rdi
0x18000717b  pop     rsi
0x18000717c  pop     rbp
0x18000717d  pop     rbx
0x18000717e  retn
```
