# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000a6c0`
- end: `0x18000a7ab`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details **this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180007e90`
- `0x18000a5f0`
- `0x18000a624`

## callees

- `0x180007e50`
- `0x18000882c`
- `0x18000a6c0`
- `0x18000a7b4`
- `0x18000af90`
- `0x18000be6c`

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
0x18000a6c0  push    rbx
0x18000a6c2  push    rbp
0x18000a6c3  push    rsi
0x18000a6c4  push    rdi
0x18000a6c5  push    r12
0x18000a6c7  push    r14
0x18000a6c9  push    r15
0x18000a6cb  sub     rsp, 50h
0x18000a6cf  mov     r12d, [rsp+88h+arg_28]
0x18000a6d7  mov     r14, r9
0x18000a6da  mov     rbp, [rsp+88h+arg_20]
0x18000a6e2  mov     rsi, r8
0x18000a6e5  mov     [rsp+88h+var_60], r12d; unsigned int
0x18000a6ea  mov     r15, rdx
0x18000a6ed  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x18000a6f2  mov     rbx, rcx
0x18000a6f5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000a6fa  test    al, al
0x18000a6fc  jz      short loc_18000A705
0x18000a6fe  mov     al, 1
0x18000a700  jmp     loc_18000A79C
0x18000a705  lea     rdx, [rbp+20h]
0x18000a709  add     rdx, rsi; unsigned __int64
0x18000a70c  cmp     qword ptr [rbx+18h], 0
0x18000a711  jnz     short loc_18000A772
0x18000a713  xorps   xmm0, xmm0
0x18000a716  lea     rcx, [rsp+88h+var_58]; this
0x18000a71b  xorps   xmm1, xmm1
0x18000a71e  add     rdx, 0Ah; unsigned __int64
0x18000a722  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x18000a728  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x18000a72e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a733  test    al, al
0x18000a735  jz      short loc_18000A761
0x18000a737  mov     rdx, [rsp+88h+var_58]; void *
0x18000a73c  xor     r8d, r8d; unsigned __int64
0x18000a73f  mov     r9, [rsp+88h+var_48]
0x18000a744  mov     rcx, rbx; this
0x18000a747  sub     r9, rdx; unsigned __int64
0x18000a74a  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000a74f  lea     rcx, [rbx+30h]
0x18000a753  lea     rdx, [rsp+88h+var_48+8]
0x18000a758  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x18000a75d  mov     byte ptr [rbx+3Ah], 1
0x18000a761  mov     rcx, [rsp+88h+var_48+8]; this
0x18000a766  test    rcx, rcx
0x18000a769  jz      short loc_18000A781
0x18000a76b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18000a770  jmp     short loc_18000A781
0x18000a772  cmp     byte ptr [rbx+3Ah], 0
0x18000a776  jz      short loc_18000A781
0x18000a778  lea     rcx, [rbx+18h]; this
0x18000a77c  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a781  mov     [rsp+88h+var_60], r12d; unsigned int
0x18000a786  mov     r9, r14; void *
0x18000a789  mov     r8, rsi; unsigned __int64
0x18000a78c  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x18000a791  mov     rdx, r15; void *
0x18000a794  mov     rcx, rbx; this
0x18000a797  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000a79c  add     rsp, 50h
0x18000a7a0  pop     r15
0x18000a7a2  pop     r14
0x18000a7a4  pop     r12
0x18000a7a6  pop     rdi
0x18000a7a7  pop     rsi
0x18000a7a8  pop     rbp
0x18000a7a9  pop     rbx
0x18000a7aa  retn
```
