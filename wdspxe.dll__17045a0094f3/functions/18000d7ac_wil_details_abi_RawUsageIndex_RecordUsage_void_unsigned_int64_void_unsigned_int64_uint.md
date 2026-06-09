# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000d7ac`
- end: `0x18000d91b`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `367`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *Buf1, size_t Size, void *, size_t, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a160`
- `0x18000d69c`
- `0x18000d6d4`

## callees

- `0x18000d7ac`
- `0x18000d924`
- `0x18000f954`
- `0x180010b88`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000d864`
- `KERNEL32!GetProcessHeap` at `0x18000d894`
- `KERNEL32!GetProcessHeap` at `0x18000d864`
- `KERNEL32!GetProcessHeap` at `0x18000d894`
- `KERNEL32!HeapFree` at `0x18000d878`
- `KERNEL32!HeapFree` at `0x18000d8a8`
- `KERNEL32!HeapFree` at `0x18000d878`
- `KERNEL32!HeapFree` at `0x18000d8a8`

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
0x18000d7ac  mov     rax, rsp
0x18000d7af  mov     [rax+8], rbx
0x18000d7b3  mov     [rax+10h], rbp
0x18000d7b7  mov     [rax+18h], rsi
0x18000d7bb  push    rdi
0x18000d7bc  push    r12
0x18000d7be  push    r13
0x18000d7c0  push    r14
0x18000d7c2  push    r15
0x18000d7c4  sub     rsp, 50h
0x18000d7c8  mov     r13d, [rsp+78h+arg_28]
0x18000d7d0  mov     r15, r9
0x18000d7d3  mov     r14, [rsp+78h+arg_20]
0x18000d7db  mov     rbp, r8
0x18000d7de  mov     [rax-50h], r13d
0x18000d7e2  mov     r12, rdx
0x18000d7e5  mov     [rax-58h], r14
0x18000d7e9  mov     rbx, rcx
0x18000d7ec  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000d7f1  test    al, al
0x18000d7f3  jz      short loc_18000D7FC
0x18000d7f5  mov     al, 1
0x18000d7f7  jmp     loc_18000D8FC
0x18000d7fc  lea     r8, [r14+20h]
0x18000d800  add     r8, rbp
0x18000d803  lea     rcx, [rbx+18h]; this
0x18000d807  cmp     qword ptr [rcx], 0
0x18000d80b  jnz     loc_18000D8B6
0x18000d811  xorps   xmm0, xmm0
0x18000d814  lea     rdx, [r14+2Ah]
0x18000d818  xorps   xmm1, xmm1
0x18000d81b  lea     rcx, [rsp+78h+var_48]; this
0x18000d820  add     rdx, rbp; unsigned __int64
0x18000d823  movdqu  xmmword ptr [rsp+78h+var_48], xmm0
0x18000d829  movdqu  [rsp+78h+var_38], xmm1
0x18000d82f  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x18000d834  test    al, al
0x18000d836  jz      short loc_18000D88A
0x18000d838  mov     rdx, [rsp+78h+var_48]; void *
0x18000d83d  xor     r8d, r8d; unsigned __int64
0x18000d840  mov     r9, qword ptr [rsp+78h+var_38]
0x18000d845  mov     rcx, rbx; this
0x18000d848  sub     r9, rdx; unsigned __int64
0x18000d84b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000d850  mov     rsi, [rbx+30h]
0x18000d854  xor     edi, edi
0x18000d856  mov     rax, qword ptr [rsp+78h+var_38+8]
0x18000d85b  mov     [rbx+30h], rax
0x18000d85f  test    rsi, rsi
0x18000d862  jz      short loc_18000D884
0x18000d864  call    cs:__imp_GetProcessHeap
0x18000d86b  nop     dword ptr [rax+rax+00h]
0x18000d870  mov     r8, rsi; lpMem
0x18000d873  xor     edx, edx; dwFlags
0x18000d875  mov     rcx, rax; hHeap
0x18000d878  call    cs:__imp_HeapFree
0x18000d87f  nop     dword ptr [rax+rax+00h]
0x18000d884  mov     byte ptr [rbx+3Ah], 1
0x18000d888  jmp     short loc_18000D88F
0x18000d88a  mov     rdi, qword ptr [rsp+78h+var_38+8]
0x18000d88f  test    rdi, rdi
0x18000d892  jz      short loc_18000D8E1
0x18000d894  call    cs:__imp_GetProcessHeap
0x18000d89b  nop     dword ptr [rax+rax+00h]
0x18000d8a0  mov     r8, rdi; lpMem
0x18000d8a3  xor     edx, edx; dwFlags
0x18000d8a5  mov     rcx, rax; hHeap
0x18000d8a8  call    cs:__imp_HeapFree
0x18000d8af  nop     dword ptr [rax+rax+00h]
0x18000d8b4  jmp     short loc_18000D8E1
0x18000d8b6  cmp     byte ptr [rbx+3Ah], 0
0x18000d8ba  jz      short loc_18000D8E1
0x18000d8bc  mov     rax, [rcx+8]
0x18000d8c0  sub     rax, [rcx]
0x18000d8c3  mov     rdx, [rcx+10h]
0x18000d8c7  add     rax, r8
0x18000d8ca  sub     rdx, [rcx]
0x18000d8cd  cmp     rax, rdx
0x18000d8d0  jb      short loc_18000D8E1
0x18000d8d2  add     rdx, rdx
0x18000d8d5  cmp     r8, rdx
0x18000d8d8  cmovnb  rdx, r8; unsigned __int64
0x18000d8dc  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x18000d8e1  mov     [rsp+78h+var_50], r13d; unsigned int
0x18000d8e6  mov     r9, r15; void *
0x18000d8e9  mov     r8, rbp; Size
0x18000d8ec  mov     [rsp+78h+var_58], r14; size_t
0x18000d8f1  mov     rdx, r12; Buf1
0x18000d8f4  mov     rcx, rbx; this
0x18000d8f7  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000d8fc  lea     r11, [rsp+78h+var_28]
0x18000d901  mov     rbx, [r11+30h]
0x18000d905  mov     rbp, [r11+38h]
0x18000d909  mov     rsi, [r11+40h]
0x18000d90d  mov     rsp, r11
0x18000d910  pop     r15
0x18000d912  pop     r14
0x18000d914  pop     r13
0x18000d916  pop     r12
0x18000d918  pop     rdi
0x18000d919  retn
```
