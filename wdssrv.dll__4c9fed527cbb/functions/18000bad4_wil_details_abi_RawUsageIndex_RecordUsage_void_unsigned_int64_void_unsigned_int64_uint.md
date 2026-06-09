# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000bad4`
- end: `0x18000bc43`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `367`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, size_t, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007820`
- `0x18000b9c4`
- `0x18000b9fc`

## callees

- `0x18000bad4`
- `0x18000bc4c`
- `0x18000d154`
- `0x18000ecd8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000bb8c`
- `KERNEL32!GetProcessHeap` at `0x18000bbbc`
- `KERNEL32!GetProcessHeap` at `0x18000bb8c`
- `KERNEL32!GetProcessHeap` at `0x18000bbbc`
- `KERNEL32!HeapFree` at `0x18000bba0`
- `KERNEL32!HeapFree` at `0x18000bbd0`
- `KERNEL32!HeapFree` at `0x18000bba0`
- `KERNEL32!HeapFree` at `0x18000bbd0`

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
0x18000bad4  mov     rax, rsp
0x18000bad7  mov     [rax+8], rbx
0x18000badb  mov     [rax+10h], rbp
0x18000badf  mov     [rax+18h], rsi
0x18000bae3  push    rdi
0x18000bae4  push    r12
0x18000bae6  push    r13
0x18000bae8  push    r14
0x18000baea  push    r15
0x18000baec  sub     rsp, 50h
0x18000baf0  mov     r13d, [rsp+78h+arg_28]
0x18000baf8  mov     r15, r9
0x18000bafb  mov     r14, [rsp+78h+arg_20]
0x18000bb03  mov     rbp, r8
0x18000bb06  mov     [rax-50h], r13d
0x18000bb0a  mov     r12, rdx
0x18000bb0d  mov     [rax-58h], r14
0x18000bb11  mov     rbx, rcx
0x18000bb14  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000bb19  test    al, al
0x18000bb1b  jz      short loc_18000BB24
0x18000bb1d  mov     al, 1
0x18000bb1f  jmp     loc_18000BC24
0x18000bb24  lea     r8, [r14+20h]
0x18000bb28  add     r8, rbp
0x18000bb2b  lea     rcx, [rbx+18h]; this
0x18000bb2f  cmp     qword ptr [rcx], 0
0x18000bb33  jnz     loc_18000BBDE
0x18000bb39  xorps   xmm0, xmm0
0x18000bb3c  lea     rdx, [r14+2Ah]
0x18000bb40  xorps   xmm1, xmm1
0x18000bb43  lea     rcx, [rsp+78h+var_48]; this
0x18000bb48  add     rdx, rbp; unsigned __int64
0x18000bb4b  movdqu  xmmword ptr [rsp+78h+var_48], xmm0
0x18000bb51  movdqu  [rsp+78h+var_38], xmm1
0x18000bb57  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x18000bb5c  test    al, al
0x18000bb5e  jz      short loc_18000BBB2
0x18000bb60  mov     rdx, [rsp+78h+var_48]; void *
0x18000bb65  xor     r8d, r8d; unsigned __int64
0x18000bb68  mov     r9, qword ptr [rsp+78h+var_38]
0x18000bb6d  mov     rcx, rbx; this
0x18000bb70  sub     r9, rdx; unsigned __int64
0x18000bb73  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000bb78  mov     rsi, [rbx+30h]
0x18000bb7c  xor     edi, edi
0x18000bb7e  mov     rax, qword ptr [rsp+78h+var_38+8]
0x18000bb83  mov     [rbx+30h], rax
0x18000bb87  test    rsi, rsi
0x18000bb8a  jz      short loc_18000BBAC
0x18000bb8c  call    cs:__imp_GetProcessHeap
0x18000bb93  nop     dword ptr [rax+rax+00h]
0x18000bb98  mov     r8, rsi; lpMem
0x18000bb9b  xor     edx, edx; dwFlags
0x18000bb9d  mov     rcx, rax; hHeap
0x18000bba0  call    cs:__imp_HeapFree
0x18000bba7  nop     dword ptr [rax+rax+00h]
0x18000bbac  mov     byte ptr [rbx+3Ah], 1
0x18000bbb0  jmp     short loc_18000BBB7
0x18000bbb2  mov     rdi, qword ptr [rsp+78h+var_38+8]
0x18000bbb7  test    rdi, rdi
0x18000bbba  jz      short loc_18000BC09
0x18000bbbc  call    cs:__imp_GetProcessHeap
0x18000bbc3  nop     dword ptr [rax+rax+00h]
0x18000bbc8  mov     r8, rdi; lpMem
0x18000bbcb  xor     edx, edx; dwFlags
0x18000bbcd  mov     rcx, rax; hHeap
0x18000bbd0  call    cs:__imp_HeapFree
0x18000bbd7  nop     dword ptr [rax+rax+00h]
0x18000bbdc  jmp     short loc_18000BC09
0x18000bbde  cmp     byte ptr [rbx+3Ah], 0
0x18000bbe2  jz      short loc_18000BC09
0x18000bbe4  mov     rax, [rcx+8]
0x18000bbe8  sub     rax, [rcx]
0x18000bbeb  mov     rdx, [rcx+10h]
0x18000bbef  add     rax, r8
0x18000bbf2  sub     rdx, [rcx]
0x18000bbf5  cmp     rax, rdx
0x18000bbf8  jb      short loc_18000BC09
0x18000bbfa  add     rdx, rdx
0x18000bbfd  cmp     r8, rdx
0x18000bc00  cmovnb  rdx, r8; unsigned __int64
0x18000bc04  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x18000bc09  mov     [rsp+78h+var_50], r13d; unsigned int
0x18000bc0e  mov     r9, r15; void *
0x18000bc11  mov     r8, rbp; Size
0x18000bc14  mov     [rsp+78h+var_58], r14; size_t
0x18000bc19  mov     rdx, r12; Buf1
0x18000bc1c  mov     rcx, rbx; this
0x18000bc1f  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000bc24  lea     r11, [rsp+78h+var_28]
0x18000bc29  mov     rbx, [r11+30h]
0x18000bc2d  mov     rbp, [r11+38h]
0x18000bc31  mov     rsi, [r11+40h]
0x18000bc35  mov     rsp, r11
0x18000bc38  pop     r15
0x18000bc3a  pop     r14
0x18000bc3c  pop     r13
0x18000bc3e  pop     r12
0x18000bc40  pop     rdi
0x18000bc41  retn
```
