# OncRpcBufMgrpAllocateDescriptorFromLLInlineBuffer

- ea: `0x140001a2c`
- end: `0x140001ad5`
- name: `OncRpcBufMgrpAllocateDescriptorFromLLInlineBuffer`
- size: `169`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400015ec`

## callees

- `0x140001a2c`
- `0x140002060`
- `0x140015b40`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001a45`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001a45`

## pseudocode

```c
_QWORD *__fastcall OncRpcBufMgrpAllocateDescriptorFromLLInlineBuffer(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 v5; // rdi
  _QWORD *result; // rax
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rdx

  v5 = a3;
  result = ExAllocateFromNPagedLookasideList(&stru_14001A580);
  v8 = result;
  if ( result )
  {
    memset(result, 0, 0x8B0u);
    ++qword_14001A6A0;
    ++dword_14001A6F0;
    OncRpcBufpDescriptorInit(v8, a1, a4);
    v9 = -(int)v5 & ((unsigned __int64)v8 + v5 + 103);
    v8[7] = v9;
    v8[8] = v9;
    *((_DWORD *)v8 + 18) = (_DWORD)v8 + 104 - v9 + 2048;
    result = v8;
    *((_DWORD *)v8 + 20) |= 5u;
    v8[11] = (v9 + (unsigned int)((_DWORD)v8 + 104 - v9 + 2048) + 15LL) & 0xFFFFFFFFFFFFFFF0uLL;
  }
  else
  {
    ++qword_14001A6A8;
  }
  return result;
}

```

## disassembly

```asm
0x140001a2c  push    rbx
0x140001a2e  push    rbp
0x140001a2f  push    rsi
0x140001a30  push    rdi
0x140001a31  sub     rsp, 28h
0x140001a35  mov     rbp, rcx
0x140001a38  mov     edi, r8d
0x140001a3b  lea     rcx, stru_14001A580; Lookaside
0x140001a42  mov     rsi, r9
0x140001a45  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140001a4c  nop     dword ptr [rax+rax+00h]
0x140001a51  mov     rbx, rax
0x140001a54  test    rax, rax
0x140001a57  jnz     short loc_140001A62
0x140001a59  inc     cs:qword_14001A6A8
0x140001a60  jmp     short loc_140001ACB
0x140001a62  xor     edx, edx; Val
0x140001a64  mov     r8d, 8B0h; Size
0x140001a6a  mov     rcx, rbx; void *
0x140001a6d  call    memset
0x140001a72  inc     cs:qword_14001A6A0
0x140001a79  mov     r8, rsi
0x140001a7c  inc     cs:dword_14001A6F0
0x140001a82  mov     rdx, rbp
0x140001a85  mov     rcx, rbx
0x140001a88  call    OncRpcBufpDescriptorInit
0x140001a8d  lea     rcx, [rbx+68h]
0x140001a91  lea     rdx, [rdi-1]
0x140001a95  neg     edi
0x140001a97  add     rdx, rcx
0x140001a9a  movsxd  rax, edi
0x140001a9d  and     rdx, rax
0x140001aa0  sub     ecx, edx
0x140001aa2  mov     [rbx+38h], rdx
0x140001aa6  mov     [rbx+40h], rdx
0x140001aaa  lea     eax, [rcx+800h]
0x140001ab0  mov     ecx, eax
0x140001ab2  add     rcx, 0Fh
0x140001ab6  mov     [rbx+48h], eax
0x140001ab9  add     rcx, rdx
0x140001abc  mov     rax, rbx
0x140001abf  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140001ac3  or      dword ptr [rbx+50h], 5
0x140001ac7  mov     [rbx+58h], rcx
0x140001acb  add     rsp, 28h
0x140001acf  pop     rdi
0x140001ad0  pop     rsi
0x140001ad1  pop     rbp
0x140001ad2  pop     rbx
0x140001ad3  retn
```
