# CodePageCharacterSource::CopyFrom(CodePageCharacterSource &)

- ea: `0x10041a980`
- end: `0x10041ab1d`
- name: `?CopyFrom@CodePageCharacterSource@@MEAAXAEAV1@@Z`
- size: `413`
- prototype: `void __fastcall(CodePageCharacterSource *__hidden this, struct CodePageCharacterSource *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x10041a980`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x10041a9dc`
- `KERNEL32!HeapFree` at `0x10041a9dc`

## pseudocode

```c
void __fastcall CodePageCharacterSource::CopyFrom(CodePageCharacterSource *this, struct CodePageCharacterSource *a2)
{
  void *v2; // r8
  struct IMalloc *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rbp
  __int64 v8; // r14
  __int64 v9; // rax
  int v10; // edx
  unsigned int v11; // ebx
  __int64 v12; // rax
  double v13; // xmm0_8
  int v14; // eax
  __int64 v15; // rax

  v2 = (void *)*((_QWORD *)this + 26);
  if ( v2 )
  {
    v5 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v5->lpVtbl->Free)(v5, v2);
    else
      HeapFree(g_hHeap, 0, v2);
  }
  v6 = *(_QWORD *)this;
  v7 = (*((_QWORD *)a2 + 6) - *((_QWORD *)a2 + 5)) >> 1;
  v8 = (*((_QWORD *)a2 + 7) - *((_QWORD *)a2 + 5)) >> 1;
  v9 = (*(__int64 (__fastcall **)(struct CodePageCharacterSource *))(*(_QWORD *)a2 + 40LL))(a2);
  (*(void (__fastcall **)(CodePageCharacterSource *, __int64))(v6 + 48))(this, v9);
  v10 = *((_DWORD *)a2 + 7);
  v11 = 0;
  v12 = *((_QWORD *)a2 + 5);
  *((_QWORD *)this + 5) = v12;
  *((_QWORD *)this + 10) = v12;
  *((_QWORD *)this + 14) = v12;
  *((_QWORD *)this + 12) = v12;
  *((_QWORD *)this + 7) = v12;
  *((_QWORD *)this + 6) = v12;
  *((_QWORD *)this + 8) = v12;
  *((_DWORD *)this + 7) = v10;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 16) = 0;
  v13 = (double)v10 * 0.9;
  *((_DWORD *)this + 8) = (int)v13;
  if ( (unsigned int)(v10 - (int)v13) < 0x10 )
    *((_DWORD *)this + 8) = v10 - 16;
  v14 = *((_DWORD *)a2 + 50);
  *((_QWORD *)a2 + 5) = 0;
  *((_DWORD *)this + 50) = v14;
  *((_DWORD *)this + 56) = *((_DWORD *)a2 + 54) + *((_DWORD *)a2 + 56) - *((_DWORD *)a2 + 52);
  v15 = *((_QWORD *)a2 + 26);
  *((_QWORD *)this + 26) = v15;
  *((_QWORD *)this + 27) = v15;
  *((_QWORD *)this + 29) = *((_QWORD *)a2 + 29);
  *((_QWORD *)this + 30) = *((_QWORD *)a2 + 30);
  *((_QWORD *)a2 + 26) = 0;
  if ( (_DWORD)v7 )
  {
    do
    {
      if ( v11 == (_DWORD)v8 )
      {
        *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
        *((_DWORD *)this + 22) = 1;
      }
      (*(void (__fastcall **)(CodePageCharacterSource *))(*(_QWORD *)this + 88LL))(this);
      ++v11;
    }
    while ( v11 < (unsigned int)v7 );
  }
}

```

## disassembly

```asm
0x10041a980  mov     [rsp+arg_0], rbx
0x10041a985  mov     [rsp+arg_8], rbp
0x10041a98a  mov     [rsp+arg_10], rsi
0x10041a98f  mov     [rsp+arg_18], rdi
0x10041a994  push    r14
0x10041a996  sub     rsp, 20h
0x10041a99a  mov     r8, [rcx+0D0h]; lpMem
0x10041a9a1  mov     rsi, rdx
0x10041a9a4  mov     rdi, rcx
0x10041a9a7  test    r8, r8
0x10041a9aa  jz      short loc_10041A9E2
0x10041a9ac  mov     rcx, [rcx+8]
0x10041a9b0  test    rcx, rcx
0x10041a9b3  jnz     short loc_10041A9C1
0x10041a9b5  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041a9bc  test    rcx, rcx
0x10041a9bf  jz      short loc_10041A9D3
0x10041a9c1  mov     rax, [rcx]
0x10041a9c4  mov     rdx, r8
0x10041a9c7  mov     rax, [rax+28h]
0x10041a9cb  call    cs:__guard_dispatch_icall_fptr
0x10041a9d1  jmp     short loc_10041A9E2
0x10041a9d3  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041a9da  xor     edx, edx; dwFlags
0x10041a9dc  call    cs:__imp_HeapFree
0x10041a9e2  mov     rax, [rsi]
0x10041a9e5  mov     rcx, rsi
0x10041a9e8  mov     rbp, [rsi+30h]
0x10041a9ec  mov     r14, [rsi+38h]
0x10041a9f0  sub     rbp, [rsi+28h]
0x10041a9f4  sub     r14, [rsi+28h]
0x10041a9f8  mov     rax, [rax+28h]
0x10041a9fc  mov     rbx, [rdi]
0x10041a9ff  shr     rbp, 1
0x10041aa02  shr     r14, 1
0x10041aa05  call    cs:__guard_dispatch_icall_fptr
0x10041aa0b  mov     rdx, rax
0x10041aa0e  mov     rcx, rdi
0x10041aa11  mov     rax, [rbx+30h]
0x10041aa15  call    cs:__guard_dispatch_icall_fptr
0x10041aa1b  mov     edx, [rsi+1Ch]
0x10041aa1e  xor     ebx, ebx
0x10041aa20  mov     rax, [rsi+28h]
0x10041aa24  xorps   xmm0, xmm0
0x10041aa27  mov     [rdi+28h], rax
0x10041aa2b  mov     [rdi+50h], rax
0x10041aa2f  mov     [rdi+70h], rax
0x10041aa33  mov     [rdi+60h], rax
0x10041aa37  mov     [rdi+38h], rax
0x10041aa3b  mov     [rdi+30h], rax
0x10041aa3f  mov     [rdi+40h], rax
0x10041aa43  mov     eax, edx
0x10041aa45  cvtsi2sd xmm0, rdx
0x10041aa4a  mov     [rdi+1Ch], edx
0x10041aa4d  mov     [rdi+78h], ebx
0x10041aa50  mov     [rdi+80h], rbx
0x10041aa57  mulsd   xmm0, cs:__real@3feccccccccccccd
0x10041aa5f  cvttsd2si rcx, xmm0
0x10041aa64  sub     eax, ecx
0x10041aa66  mov     [rdi+20h], ecx
0x10041aa69  cmp     eax, 10h
0x10041aa6c  jnb     short loc_10041AA74
0x10041aa6e  lea     eax, [rdx-10h]
0x10041aa71  mov     [rdi+20h], eax
0x10041aa74  mov     eax, [rsi+0C8h]
0x10041aa7a  mov     [rsi+28h], rbx
0x10041aa7e  mov     [rdi+0C8h], eax
0x10041aa84  mov     eax, [rsi+0E0h]
0x10041aa8a  add     eax, [rsi+0D8h]
0x10041aa90  sub     eax, [rsi+0D0h]
0x10041aa96  mov     [rdi+0E0h], eax
0x10041aa9c  mov     rax, [rsi+0D0h]
0x10041aaa3  mov     [rdi+0D0h], rax
0x10041aaaa  mov     [rdi+0D8h], rax
0x10041aab1  mov     rax, [rsi+0E8h]
0x10041aab8  mov     [rdi+0E8h], rax
0x10041aabf  mov     rax, [rsi+0F0h]
0x10041aac6  mov     [rdi+0F0h], rax
0x10041aacd  mov     [rsi+0D0h], rbx
0x10041aad4  test    ebp, ebp
0x10041aad6  jz      short loc_10041AB02
0x10041aad8  cmp     ebx, r14d
0x10041aadb  jnz     short loc_10041AAEC
0x10041aadd  mov     rax, [rdi+30h]
0x10041aae1  mov     [rdi+38h], rax
0x10041aae5  mov     dword ptr [rdi+58h], 1
0x10041aaec  mov     rax, [rdi]
0x10041aaef  mov     rcx, rdi
0x10041aaf2  mov     rax, [rax+58h]
0x10041aaf6  call    cs:__guard_dispatch_icall_fptr
0x10041aafc  inc     ebx
0x10041aafe  cmp     ebx, ebp
0x10041ab00  jb      short loc_10041AAD8
0x10041ab02  mov     rbx, [rsp+28h+arg_0]
0x10041ab07  mov     rbp, [rsp+28h+arg_8]
0x10041ab0c  mov     rsi, [rsp+28h+arg_10]
0x10041ab11  mov     rdi, [rsp+28h+arg_18]
0x10041ab16  add     rsp, 20h
0x10041ab1a  pop     r14
0x10041ab1c  retn
```
