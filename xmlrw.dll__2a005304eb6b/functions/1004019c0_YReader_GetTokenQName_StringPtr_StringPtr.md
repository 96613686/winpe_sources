# YReader::GetTokenQName(StringPtr *,StringPtr *)

- ea: `0x1004019c0`
- end: `0x100401aa1`
- name: `?GetTokenQName@YReader@@AEAAXPEAUStringPtr@@0@Z`
- size: `225`
- prototype: `void __fastcall(YReader *__hidden this, struct StringPtr *, struct StringPtr *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x100404070`
- `0x100404310`
- `0x100407840`
- `0x1004079d0`

## callees

- `0x1004019c0`
- `0x100415560`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::GetTokenQName(YReader *this, struct StringPtr *a2, struct StringPtr *a3)
{
  unsigned int v6; // eax
  struct BlockAlloc::Header *v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rcx
  struct BlockAlloc::Header *v11; // rax

  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v7 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v8 = v6;
  v9 = *((_QWORD *)v7 + 2);
  if ( *((_DWORD *)v7 + 6) - (int)v9 < v6 )
  {
    v10 = *((_QWORD *)v7 + 1);
    if ( v10 )
    {
      while ( 1 )
      {
        v7 = (struct BlockAlloc::Header *)v10;
        if ( *(_DWORD *)(v10 + 24) - (int)v10 - 32 >= v6 )
          break;
        v10 = *(_QWORD *)(v10 + 8);
        if ( !v10 )
          goto LABEL_5;
      }
      *(_QWORD *)(v10 + 16) = v10 + 32;
    }
    else
    {
LABEL_5:
      _mm_lfence();
      v11 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v6, v7);
      *((_QWORD *)v7 + 1) = v11;
      v7 = v11;
    }
    *((_QWORD *)this + 55) = v7;
    v9 = *((_QWORD *)v7 + 2);
  }
  *((_QWORD *)v7 + 2) += v8;
  *(_QWORD *)a2 = v9;
  (*(void (__fastcall **)(_QWORD, struct StringPtr *))(**((_QWORD **)this + 13) + 104LL))(*((_QWORD *)this + 13), a2);
  *(_QWORD *)a3 = *(_QWORD *)a2;
  *((_DWORD *)a3 + 2) = *((_DWORD *)this + 80);
}

```

## disassembly

```asm
0x1004019c0  mov     [rsp+arg_0], rbx
0x1004019c5  mov     [rsp+arg_8], rsi
0x1004019ca  mov     [rsp+arg_10], rdi
0x1004019cf  mov     [rsp+arg_18], r14
0x1004019d4  push    r15
0x1004019d6  sub     rsp, 20h
0x1004019da  mov     rsi, rcx
0x1004019dd  mov     r15, r8
0x1004019e0  mov     rcx, [rcx+68h]
0x1004019e4  mov     r14, rdx
0x1004019e7  mov     rax, [rcx]
0x1004019ea  mov     rax, [rax+60h]
0x1004019ee  call    cs:__guard_dispatch_icall_fptr
0x1004019f4  mov     rbx, [rsi+1B8h]
0x1004019fb  mov     edi, eax
0x1004019fd  mov     rdx, [rbx+10h]
0x100401a01  mov     ecx, [rbx+18h]
0x100401a04  sub     ecx, edx
0x100401a06  cmp     ecx, eax
0x100401a08  jnb     short loc_100401A51
0x100401a0a  mov     rcx, [rbx+8]
0x100401a0e  test    rcx, rcx
0x100401a11  jz      short loc_100401A2B
0x100401a13  mov     eax, [rcx+18h]
0x100401a16  mov     rbx, rcx
0x100401a19  sub     eax, ecx
0x100401a1b  sub     eax, 20h ; ' '
0x100401a1e  cmp     eax, edi
0x100401a20  jnb     short loc_100401A97
0x100401a22  mov     rcx, [rcx+8]
0x100401a26  test    rcx, rcx
0x100401a29  jnz     short loc_100401A13
0x100401a2b  lfence
0x100401a2e  mov     r8, rbx; struct BlockAlloc::Header *
0x100401a31  lea     rcx, [rsi+1A0h]; this
0x100401a38  mov     edx, edi; unsigned int
0x100401a3a  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100401a3f  mov     [rbx+8], rax
0x100401a43  mov     rbx, rax
0x100401a46  mov     [rsi+1B8h], rbx
0x100401a4d  mov     rdx, [rbx+10h]
0x100401a51  add     [rbx+10h], rdi
0x100401a55  mov     [r14], rdx
0x100401a58  mov     rdx, r14
0x100401a5b  mov     rcx, [rsi+68h]
0x100401a5f  mov     rax, [rcx]
0x100401a62  mov     rax, [rax+68h]
0x100401a66  call    cs:__guard_dispatch_icall_fptr
0x100401a6c  mov     rax, [r14]
0x100401a6f  mov     rbx, [rsp+28h+arg_0]
0x100401a74  mov     rdi, [rsp+28h+arg_10]
0x100401a79  mov     r14, [rsp+28h+arg_18]
0x100401a7e  mov     [r15], rax
0x100401a81  mov     eax, [rsi+140h]
0x100401a87  mov     rsi, [rsp+28h+arg_8]
0x100401a8c  mov     [r15+8], eax
0x100401a90  add     rsp, 20h
0x100401a94  pop     r15
0x100401a96  retn
0x100401a97  lea     rax, [rcx+20h]
0x100401a9b  mov     [rcx+10h], rax
0x100401a9f  jmp     short loc_100401A46
```
