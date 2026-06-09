# TptMemoryBufferAllocate(ulong)

- ea: `0x180008f4c`
- end: `0x180008fe7`
- name: `?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z`
- size: `155`
- prototype: `struct CMemoryBuffer *__fastcall(unsigned int)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180008040`
- `0x18000a5a4`
- `0x18001bd40`
- `0x18001c71c`
- `0x18001d560`
- `0x18001d730`
- `0x18001d8a8`
- `0x18001dab0`
- `0x18001dd2c`
- `0x18001df44`
- `0x18001e16c`
- `0x18001e398`

## callees

- `0x180008f4c`
- `0x1800253a8`
- `0x1800266a0`
- `0x180026d70`

## pseudocode

```c
struct CMemoryBuffer *__fastcall TptMemoryBufferAllocate(unsigned int a1)
{
  CMemoryBuffer *v2; // rax
  CMemoryBuffer *v3; // rbx

  v2 = (CMemoryBuffer *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    *((_DWORD *)v2 + 2) = 1;
    *(_QWORD *)v2 = &CMemoryBuffer::`vftable';
    *((_QWORD *)v2 + 7) = 0;
    *((_QWORD *)v2 + 8) = 0;
    *((_QWORD *)v2 + 3) = 0;
    *((_QWORD *)v2 + 5) = 0;
    *((_DWORD *)v2 + 12) = 0;
    *((_DWORD *)v2 + 4) = 0;
    *((_QWORD *)v2 + 4) = 0;
  }
  else
  {
    v3 = 0;
  }
  if ( v3 )
  {
    if ( CMemoryBuffer::Initialize(v3, a1) )
    {
      (*(void (__fastcall **)(CMemoryBuffer *, __int64))(*(_QWORD *)v3 + 16LL))(v3, 1);
      v3 = 0;
    }
    if ( v3 )
      *((_DWORD *)v3 + 12) = a1;
  }
  return v3;
}

```

## disassembly

```asm
0x180008f4c  mov     [rsp+arg_0], rbx
0x180008f51  push    rdi
0x180008f52  sub     rsp, 20h
0x180008f56  mov     edi, ecx
0x180008f58  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008f5f  mov     ecx, 48h ; 'H'; unsigned __int64
0x180008f64  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008f69  mov     rbx, rax
0x180008f6c  test    rax, rax
0x180008f6f  jz      short loc_180008FA5
0x180008f71  mov     dword ptr [rax+8], 1
0x180008f78  lea     rax, ??_7CMemoryBuffer@@6B@; const CMemoryBuffer::`vftable'
0x180008f7f  mov     [rbx], rax
0x180008f82  and     qword ptr [rbx+38h], 0
0x180008f87  and     qword ptr [rbx+40h], 0
0x180008f8c  and     qword ptr [rbx+18h], 0
0x180008f91  and     qword ptr [rbx+28h], 0
0x180008f96  and     dword ptr [rbx+30h], 0
0x180008f9a  and     dword ptr [rbx+10h], 0
0x180008f9e  and     qword ptr [rbx+20h], 0
0x180008fa3  jmp     short loc_180008FA7
0x180008fa5  xor     ebx, ebx
0x180008fa7  test    rbx, rbx
0x180008faa  jz      short loc_180008FD9
0x180008fac  mov     edx, edi; unsigned int
0x180008fae  mov     rcx, rbx; this
0x180008fb1  call    ?Initialize@CMemoryBuffer@@QEAAKK@Z; CMemoryBuffer::Initialize(ulong)
0x180008fb6  test    eax, eax
0x180008fb8  jz      short loc_180008FD1
0x180008fba  mov     rax, [rbx]
0x180008fbd  mov     edx, 1
0x180008fc2  mov     rcx, rbx
0x180008fc5  mov     rax, [rax+10h]
0x180008fc9  call    cs:__guard_dispatch_icall_fptr
0x180008fcf  xor     ebx, ebx
0x180008fd1  test    rbx, rbx
0x180008fd4  jz      short loc_180008FD9
0x180008fd6  mov     [rbx+30h], edi
0x180008fd9  mov     rax, rbx
0x180008fdc  mov     rbx, [rsp+28h+arg_0]
0x180008fe1  add     rsp, 20h
0x180008fe5  pop     rdi
0x180008fe6  retn
```
