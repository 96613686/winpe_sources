# YReader::GetTokenData(StringPtr *)

- ea: `0x1004018f0`
- end: `0x1004019b9`
- name: `?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z`
- size: `201`
- prototype: `void __fastcall(YReader *__hidden this, struct StringPtr *)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x100404670`
- `0x100404a40`
- `0x100404c10`
- `0x100404de0`
- `0x1004055d0`
- `0x1004058d0`
- `0x100405a00`
- `0x1004064a0`
- `0x1004069e0`
- `0x100407100`
- `0x100408580`
- `0x100408ba0`

## callees

- `0x1004018f0`
- `0x100415560`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::GetTokenData(YReader *this, struct StringPtr *a2)
{
  unsigned int v4; // eax
  struct BlockAlloc::Header *v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  struct BlockAlloc::Header *v9; // rax

  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 96LL))(*((_QWORD *)this + 13));
  v5 = (struct BlockAlloc::Header *)*((_QWORD *)this + 55);
  v6 = v4;
  v7 = *((_QWORD *)v5 + 2);
  if ( *((_DWORD *)v5 + 6) - (int)v7 < v4 )
  {
    v8 = *((_QWORD *)v5 + 1);
    if ( v8 )
    {
      while ( 1 )
      {
        v5 = (struct BlockAlloc::Header *)v8;
        if ( *(_DWORD *)(v8 + 24) - (int)v8 - 32 >= v4 )
          break;
        v8 = *(_QWORD *)(v8 + 8);
        if ( !v8 )
          goto LABEL_5;
      }
      *(_QWORD *)(v8 + 16) = v8 + 32;
    }
    else
    {
LABEL_5:
      _mm_lfence();
      v9 = BlockAlloc::EnqueueBlock((YReader *)((char *)this + 416), v4, v5);
      *((_QWORD *)v5 + 1) = v9;
      v5 = v9;
    }
    *((_QWORD *)this + 55) = v5;
    v7 = *((_QWORD *)v5 + 2);
  }
  *((_QWORD *)v5 + 2) += v6;
  *(_QWORD *)a2 = v7;
  (*(void (__fastcall **)(_QWORD, struct StringPtr *))(**((_QWORD **)this + 13) + 104LL))(*((_QWORD *)this + 13), a2);
}

```

## disassembly

```asm
0x1004018f0  mov     [rsp+arg_0], rbx
0x1004018f5  mov     [rsp+arg_8], rsi
0x1004018fa  mov     [rsp+arg_10], rdi
0x1004018ff  push    r14
0x100401901  sub     rsp, 20h
0x100401905  mov     rsi, rcx
0x100401908  mov     r14, rdx
0x10040190b  mov     rcx, [rcx+68h]
0x10040190f  mov     rax, [rcx]
0x100401912  mov     rax, [rax+60h]
0x100401916  call    cs:__guard_dispatch_icall_fptr
0x10040191c  mov     rbx, [rsi+1B8h]
0x100401923  mov     edi, eax
0x100401925  mov     rdx, [rbx+10h]
0x100401929  mov     ecx, [rbx+18h]
0x10040192c  sub     ecx, edx
0x10040192e  cmp     ecx, eax
0x100401930  jnb     short loc_10040197E
0x100401932  mov     rcx, [rbx+8]
0x100401936  test    rcx, rcx
0x100401939  jz      short loc_100401958
0x10040193b  nop     dword ptr [rax+rax+00h]
0x100401940  mov     eax, [rcx+18h]
0x100401943  mov     rbx, rcx
0x100401946  sub     eax, ecx
0x100401948  sub     eax, 20h ; ' '
0x10040194b  cmp     eax, edi
0x10040194d  jnb     short loc_1004019AF
0x10040194f  mov     rcx, [rcx+8]
0x100401953  test    rcx, rcx
0x100401956  jnz     short loc_100401940
0x100401958  lfence
0x10040195b  mov     r8, rbx; struct BlockAlloc::Header *
0x10040195e  lea     rcx, [rsi+1A0h]; this
0x100401965  mov     edx, edi; unsigned int
0x100401967  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040196c  mov     [rbx+8], rax
0x100401970  mov     rbx, rax
0x100401973  mov     [rsi+1B8h], rbx
0x10040197a  mov     rdx, [rbx+10h]
0x10040197e  add     [rbx+10h], rdi
0x100401982  mov     [r14], rdx
0x100401985  mov     rdx, r14
0x100401988  mov     rcx, [rsi+68h]
0x10040198c  mov     rax, [rcx]
0x10040198f  mov     rax, [rax+68h]
0x100401993  mov     rbx, [rsp+28h+arg_0]
0x100401998  mov     rsi, [rsp+28h+arg_8]
0x10040199d  mov     rdi, [rsp+28h+arg_10]
0x1004019a2  add     rsp, 20h
0x1004019a6  pop     r14
0x1004019a8  jmp     cs:__guard_dispatch_icall_fptr
0x1004019af  lea     rax, [rcx+20h]
0x1004019b3  mov     [rcx+10h], rax
0x1004019b7  jmp     short loc_100401973
```
