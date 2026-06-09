# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008ccc`
- end: `0x180008e3b`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `367`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, size_t, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003a50`
- `0x180008bbc`
- `0x180008bf4`

## callees

- `0x180008ccc`
- `0x180008e44`
- `0x18000a38c`
- `0x18000b958`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008d98`
- `KERNEL32!HeapFree` at `0x180008dc8`
- `KERNEL32!HeapFree` at `0x180008d98`
- `KERNEL32!HeapFree` at `0x180008dc8`
- `KERNEL32!GetProcessHeap` at `0x180008d84`
- `KERNEL32!GetProcessHeap` at `0x180008db4`
- `KERNEL32!GetProcessHeap` at `0x180008d84`
- `KERNEL32!GetProcessHeap` at `0x180008db4`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        size_t a5,
        unsigned int a6)
{
  unsigned __int64 v11; // r8
  void *v12; // rsi
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  void *v18[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v19; // [rsp+40h] [rbp-38h]

  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, Buf1, Size, a4, a5, a6) )
    return 1;
  v11 = Size + a5 + 32;
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
    {
      v16 = *((_QWORD *)this + 5) - *((_QWORD *)this + 3);
      if ( v11 + *((_QWORD *)this + 4) - *((_QWORD *)this + 3) >= v16 )
      {
        v17 = 2 * v16;
        if ( v11 >= v17 )
          v17 = Size + a5 + 32;
        wil::details_abi::heap_buffer::reserve((wil::details_abi::RawUsageIndex *)((char *)this + 24), v17);
      }
    }
  }
  else
  {
    *(_OWORD *)v18 = 0;
    v19 = 0;
    if ( wil::details_abi::heap_buffer::reserve((wil::details_abi::heap_buffer *)v18, Size + a5 + 42) )
    {
      wil::details_abi::RawUsageIndex::SetBuffer(this, v18[0], 0, v19 - (unsigned __int64)v18[0]);
      v12 = (void *)*((_QWORD *)this + 6);
      v13 = 0;
      *((_QWORD *)this + 6) = *((_QWORD *)&v19 + 1);
      if ( v12 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v12);
      }
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v13 = (void *)*((_QWORD *)&v19 + 1);
    }
    if ( v13 )
    {
      v15 = GetProcessHeap();
      HeapFree(v15, 0, v13);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, Buf1, Size, a4, a5, a6);
}

```

## disassembly

```asm
0x180008ccc  mov     rax, rsp
0x180008ccf  mov     [rax+8], rbx
0x180008cd3  mov     [rax+10h], rbp
0x180008cd7  mov     [rax+18h], rsi
0x180008cdb  push    rdi
0x180008cdc  push    r12
0x180008cde  push    r13
0x180008ce0  push    r14
0x180008ce2  push    r15
0x180008ce4  sub     rsp, 50h
0x180008ce8  mov     r13d, [rsp+78h+arg_28]
0x180008cf0  mov     r15, r9
0x180008cf3  mov     r14, [rsp+78h+arg_20]
0x180008cfb  mov     rbp, r8
0x180008cfe  mov     [rax-50h], r13d
0x180008d02  mov     r12, rdx
0x180008d05  mov     [rax-58h], r14
0x180008d09  mov     rbx, rcx
0x180008d0c  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180008d11  test    al, al
0x180008d13  jz      short loc_180008D1C
0x180008d15  mov     al, 1
0x180008d17  jmp     loc_180008E1C
0x180008d1c  lea     r8, [r14+20h]
0x180008d20  add     r8, rbp
0x180008d23  lea     rcx, [rbx+18h]; this
0x180008d27  cmp     qword ptr [rcx], 0
0x180008d2b  jnz     loc_180008DD6
0x180008d31  xorps   xmm0, xmm0
0x180008d34  lea     rdx, [r14+2Ah]
0x180008d38  xorps   xmm1, xmm1
0x180008d3b  lea     rcx, [rsp+78h+var_48]; this
0x180008d40  add     rdx, rbp; unsigned __int64
0x180008d43  movdqu  xmmword ptr [rsp+78h+var_48], xmm0
0x180008d49  movdqu  [rsp+78h+var_38], xmm1
0x180008d4f  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x180008d54  test    al, al
0x180008d56  jz      short loc_180008DAA
0x180008d58  mov     rdx, [rsp+78h+var_48]; void *
0x180008d5d  xor     r8d, r8d; unsigned __int64
0x180008d60  mov     r9, qword ptr [rsp+78h+var_38]
0x180008d65  mov     rcx, rbx; this
0x180008d68  sub     r9, rdx; unsigned __int64
0x180008d6b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180008d70  mov     rsi, [rbx+30h]
0x180008d74  xor     edi, edi
0x180008d76  mov     rax, qword ptr [rsp+78h+var_38+8]
0x180008d7b  mov     [rbx+30h], rax
0x180008d7f  test    rsi, rsi
0x180008d82  jz      short loc_180008DA4
0x180008d84  call    cs:__imp_GetProcessHeap
0x180008d8b  nop     dword ptr [rax+rax+00h]
0x180008d90  mov     r8, rsi; lpMem
0x180008d93  xor     edx, edx; dwFlags
0x180008d95  mov     rcx, rax; hHeap
0x180008d98  call    cs:__imp_HeapFree
0x180008d9f  nop     dword ptr [rax+rax+00h]
0x180008da4  mov     byte ptr [rbx+3Ah], 1
0x180008da8  jmp     short loc_180008DAF
0x180008daa  mov     rdi, qword ptr [rsp+78h+var_38+8]
0x180008daf  test    rdi, rdi
0x180008db2  jz      short loc_180008E01
0x180008db4  call    cs:__imp_GetProcessHeap
0x180008dbb  nop     dword ptr [rax+rax+00h]
0x180008dc0  mov     r8, rdi; lpMem
0x180008dc3  xor     edx, edx; dwFlags
0x180008dc5  mov     rcx, rax; hHeap
0x180008dc8  call    cs:__imp_HeapFree
0x180008dcf  nop     dword ptr [rax+rax+00h]
0x180008dd4  jmp     short loc_180008E01
0x180008dd6  cmp     byte ptr [rbx+3Ah], 0
0x180008dda  jz      short loc_180008E01
0x180008ddc  mov     rax, [rcx+8]
0x180008de0  sub     rax, [rcx]
0x180008de3  mov     rdx, [rcx+10h]
0x180008de7  add     rax, r8
0x180008dea  sub     rdx, [rcx]
0x180008ded  cmp     rax, rdx
0x180008df0  jb      short loc_180008E01
0x180008df2  add     rdx, rdx
0x180008df5  cmp     r8, rdx
0x180008df8  cmovnb  rdx, r8; unsigned __int64
0x180008dfc  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x180008e01  mov     [rsp+78h+var_50], r13d; unsigned int
0x180008e06  mov     r9, r15; void *
0x180008e09  mov     r8, rbp; Size
0x180008e0c  mov     [rsp+78h+var_58], r14; size_t
0x180008e11  mov     rdx, r12; Buf1
0x180008e14  mov     rcx, rbx; this
0x180008e17  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180008e1c  lea     r11, [rsp+78h+var_28]
0x180008e21  mov     rbx, [r11+30h]
0x180008e25  mov     rbp, [r11+38h]
0x180008e29  mov     rsi, [r11+40h]
0x180008e2d  mov     rsp, r11
0x180008e30  pop     r15
0x180008e32  pop     r14
0x180008e34  pop     r13
0x180008e36  pop     r12
0x180008e38  pop     rdi
0x180008e39  retn
```
