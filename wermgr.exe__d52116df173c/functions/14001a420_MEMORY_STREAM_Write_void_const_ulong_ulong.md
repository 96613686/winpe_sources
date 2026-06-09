# MEMORY_STREAM::Write(void const *,ulong,ulong *)

- ea: `0x14001a420`
- end: `0x14001a4fc`
- name: `?Write@MEMORY_STREAM@@UEAAJPEBXKPEAK@Z`
- size: `220`
- prototype: `__int64 __fastcall(MEMORY_STREAM *this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x140003224`
- `0x140003254`
- `0x14001a420`
- `0x14001c9a8`

## pseudocode

```c
__int64 __fastcall MEMORY_STREAM::Write(MEMORY_STREAM *this, const void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v9; // edx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  void *v13; // rax
  void *v14; // r14
  const struct std::nothrow_t *v15; // rdx

  if ( a4 )
    *a4 = 0;
  if ( !*((_BYTE *)this + 24) )
    return 2147680261LL;
  v9 = *((_DWORD *)this + 4);
  v10 = *((unsigned int *)this + 5);
  v11 = (unsigned int)v10 < v9 ? v9 - v10 : 0;
  if ( *((_BYTE *)this + 25) && a3 > v11 )
  {
    v12 = v9 - v11 + a3;
    if ( v12 < v9 )
      return 2147942934LL;
    v13 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v13;
    if ( !v13 )
      return 2147680368LL;
    memcpy_0(v13, *((const void **)this + 1), *((unsigned int *)this + 4));
    operator delete(*((void **)this + 1), v15);
    v10 = *((unsigned int *)this + 5);
    *((_DWORD *)this + 4) = v12;
    v11 = v12 - v10;
    *((_QWORD *)this + 1) = v14;
  }
  if ( !*((_QWORD *)this + 1) || !v11 )
    return 2147680368LL;
  if ( a3 < v11 )
    v11 = a3;
  memcpy_0((void *)(*((_QWORD *)this + 1) + v10), a2, v11);
  *((_DWORD *)this + 5) += v11;
  if ( a4 )
    *a4 = v11;
  return 0;
}

```

## disassembly

```asm
0x14001a420  push    rbx
0x14001a422  push    rbp
0x14001a423  push    rsi
0x14001a424  push    rdi
0x14001a425  push    r14
0x14001a427  push    r15
0x14001a429  sub     rsp, 28h
0x14001a42d  mov     rsi, r9
0x14001a430  mov     ebp, r8d
0x14001a433  mov     r15, rdx
0x14001a436  mov     rdi, rcx
0x14001a439  test    r9, r9
0x14001a43c  jz      short loc_14001A445
0x14001a43e  mov     dword ptr [r9], 0
0x14001a445  cmp     byte ptr [rcx+18h], 0
0x14001a449  jnz     short loc_14001A455
0x14001a44b  mov     eax, 80030005h
0x14001a450  jmp     loc_14001A4EF
0x14001a455  mov     edx, [rcx+10h]
0x14001a458  mov     eax, edx
0x14001a45a  mov     ecx, [rcx+14h]
0x14001a45d  sub     eax, ecx
0x14001a45f  cmp     ecx, edx
0x14001a461  sbb     ebx, ebx
0x14001a463  and     ebx, eax
0x14001a465  cmp     byte ptr [rdi+19h], 0
0x14001a469  jz      short loc_14001A4BD
0x14001a46b  cmp     ebp, ebx
0x14001a46d  jbe     short loc_14001A4BD
0x14001a46f  mov     eax, edx
0x14001a471  sub     eax, ebx
0x14001a473  lea     ebx, [rax+r8]
0x14001a477  cmp     ebx, edx
0x14001a479  jnb     short loc_14001A482
0x14001a47b  mov     eax, 80070216h
0x14001a480  jmp     short loc_14001A4EF
0x14001a482  mov     ecx, ebx; unsigned __int64
0x14001a484  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001a48b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14001a490  mov     r14, rax
0x14001a493  test    rax, rax
0x14001a496  jz      short loc_14001A4EA
0x14001a498  mov     r8d, [rdi+10h]; Size
0x14001a49c  mov     rcx, rax; void *
0x14001a49f  mov     rdx, [rdi+8]; Src
0x14001a4a3  call    memcpy_0
0x14001a4a8  mov     rcx, [rdi+8]; void *
0x14001a4ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a4b1  mov     ecx, [rdi+14h]
0x14001a4b4  mov     [rdi+10h], ebx
0x14001a4b7  sub     ebx, ecx
0x14001a4b9  mov     [rdi+8], r14
0x14001a4bd  cmp     qword ptr [rdi+8], 0
0x14001a4c2  jz      short loc_14001A4EA
0x14001a4c4  test    ebx, ebx
0x14001a4c6  jz      short loc_14001A4EA
0x14001a4c8  cmp     ebp, ebx
0x14001a4ca  mov     rdx, r15; Src
0x14001a4cd  cmovb   ebx, ebp
0x14001a4d0  add     rcx, [rdi+8]; void *
0x14001a4d4  mov     r8d, ebx; Size
0x14001a4d7  call    memcpy_0
0x14001a4dc  add     [rdi+14h], ebx
0x14001a4df  test    rsi, rsi
0x14001a4e2  jz      short loc_14001A4E6
0x14001a4e4  mov     [rsi], ebx
0x14001a4e6  xor     eax, eax
0x14001a4e8  jmp     short loc_14001A4EF
0x14001a4ea  mov     eax, 80030070h
0x14001a4ef  add     rsp, 28h
0x14001a4f3  pop     r15
0x14001a4f5  pop     r14
0x14001a4f7  pop     rdi
0x14001a4f8  pop     rsi
0x14001a4f9  pop     rbp
0x14001a4fa  pop     rbx
0x14001a4fb  retn
```
