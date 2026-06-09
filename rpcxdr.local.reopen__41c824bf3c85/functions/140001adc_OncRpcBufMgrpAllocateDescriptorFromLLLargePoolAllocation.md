# OncRpcBufMgrpAllocateDescriptorFromLLLargePoolAllocation

- ea: `0x140001adc`
- end: `0x140001be7`
- name: `OncRpcBufMgrpAllocateDescriptorFromLLLargePoolAllocation`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400015ec`

## callees

- `0x140001adc`
- `0x140002060`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001b95`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001b95`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001af4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001af4`
- `ntoskrnl!ExAllocatePool2` at `0x140001b6f`
- `ntoskrnl!ExAllocatePool2` at `0x140001b6f`

## pseudocode

```c
_QWORD *__fastcall OncRpcBufMgrpAllocateDescriptorFromLLLargePoolAllocation(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  _QWORD *result; // rax
  _QWORD *v8; // rbx
  unsigned int v9; // edi
  int v10; // esi
  __int64 Pool2; // rax
  unsigned int v12; // edi
  __int64 v13; // rcx

  result = ExAllocateFromNPagedLookasideList(&stru_14001A600);
  v8 = result;
  if ( result )
  {
    ++qword_14001A6A0;
    ++dword_14001A6F0;
    OncRpcBufpDescriptorInit(result, a1, a4);
    v9 = 4096;
    if ( (unsigned __int64)(unsigned int)(a2 + 16) + 56 >= 0x1000 )
    {
      v10 = 8 * (((unsigned __int64)(unsigned int)(a2 + 4096) + 4095) >> 12) + 64;
      v9 = v10 + a2;
    }
    else
    {
      v10 = 72;
    }
    Pool2 = ExAllocatePool2(64, v9, 1346528344);
    v8[7] = Pool2;
    if ( Pool2 )
    {
      ++qword_14001A6B0;
      v12 = v9 - v10;
      ++dword_14001A6F4;
      v13 = v8[7];
      *((_DWORD *)v8 + 18) = v12;
      v8[8] = v13;
      *((_DWORD *)v8 + 20) |= 0xAu;
      v8[11] = (v13 + v12 + 15LL) & 0xFFFFFFFFFFFFFFF0uLL;
    }
    else
    {
      ++qword_14001A6B8;
      ExFreeToNPagedLookasideList(&stru_14001A600, v8);
      --dword_14001A6F0;
      return 0;
    }
    return v8;
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
0x140001adc  push    rbx
0x140001ade  push    rbp
0x140001adf  push    rsi
0x140001ae0  push    rdi
0x140001ae1  sub     rsp, 28h
0x140001ae5  mov     rsi, rcx
0x140001ae8  mov     rdi, r9
0x140001aeb  lea     rcx, stru_14001A600; Lookaside
0x140001af2  mov     ebp, edx
0x140001af4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140001afb  nop     dword ptr [rax+rax+00h]
0x140001b00  mov     rbx, rax
0x140001b03  test    rax, rax
0x140001b06  jnz     short loc_140001B14
0x140001b08  inc     cs:qword_14001A6A8
0x140001b0f  jmp     loc_140001BDD
0x140001b14  inc     cs:qword_14001A6A0
0x140001b1b  mov     r8, rdi
0x140001b1e  inc     cs:dword_14001A6F0
0x140001b24  mov     rdx, rsi
0x140001b27  mov     rcx, rbx
0x140001b2a  call    OncRpcBufpDescriptorInit
0x140001b2f  lea     eax, [rbp+10h]
0x140001b32  mov     edi, 1000h
0x140001b37  add     rax, 38h ; '8'
0x140001b3b  cmp     rax, rdi
0x140001b3e  jnb     short loc_140001B47
0x140001b40  mov     esi, 48h ; 'H'
0x140001b45  jmp     short loc_140001B62
0x140001b47  lea     ecx, [rbp+1000h]
0x140001b4d  add     rcx, 0FFFh
0x140001b54  shr     rcx, 0Ch
0x140001b58  lea     esi, ds:40h[rcx*8]
0x140001b5f  lea     edi, [rsi+rbp]
0x140001b62  mov     edx, edi
0x140001b64  mov     ecx, 40h ; '@'
0x140001b69  mov     r8d, 50426458h
0x140001b6f  call    cs:__imp_ExAllocatePool2
0x140001b76  nop     dword ptr [rax+rax+00h]
0x140001b7b  mov     [rbx+38h], rax
0x140001b7f  test    rax, rax
0x140001b82  jnz     short loc_140001BAB
0x140001b84  inc     cs:qword_14001A6B8
0x140001b8b  lea     rcx, stru_14001A600; Lookaside
0x140001b92  mov     rdx, rbx; Entry
0x140001b95  call    cs:__imp_ExFreeToNPagedLookasideList
0x140001b9c  nop     dword ptr [rax+rax+00h]
0x140001ba1  dec     cs:dword_14001A6F0
0x140001ba7  xor     ebx, ebx
0x140001ba9  jmp     short loc_140001BDA
0x140001bab  inc     cs:qword_14001A6B0
0x140001bb2  sub     edi, esi
0x140001bb4  inc     cs:dword_14001A6F4
0x140001bba  mov     rcx, [rbx+38h]
0x140001bbe  mov     eax, edi
0x140001bc0  mov     [rbx+48h], eax
0x140001bc3  add     rax, 0Fh
0x140001bc7  add     rax, rcx
0x140001bca  mov     [rbx+40h], rcx
0x140001bce  and     rax, 0FFFFFFFFFFFFFFF0h
0x140001bd2  or      dword ptr [rbx+50h], 0Ah
0x140001bd6  mov     [rbx+58h], rax
0x140001bda  mov     rax, rbx
0x140001bdd  add     rsp, 28h
0x140001be1  pop     rdi
0x140001be2  pop     rsi
0x140001be3  pop     rbp
0x140001be4  pop     rbx
0x140001be5  retn
```
