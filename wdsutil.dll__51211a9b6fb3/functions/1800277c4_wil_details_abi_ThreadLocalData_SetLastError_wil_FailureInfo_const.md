# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800277c4`
- end: `0x180027a5c`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `664`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800253b0`

## callees

- `0x1800222e0`
- `0x180026f3c`
- `0x1800277c4`
- `0x1800319ae`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180027a1f`
- `msvcrt!memcpy_s` at `0x180027a1f`
- `KERNEL32!HeapFree` at `0x18002798a`
- `KERNEL32!HeapFree` at `0x18002798a`
- `KERNEL32!GetProcessHeap` at `0x180027976`
- `KERNEL32!GetProcessHeap` at `0x180027976`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // esi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // edx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned __int64 v23; // rbp
  LPVOID v24; // r12
  void *v25; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v27; // rcx
  char *v28; // rbp
  __int64 v29; // rax
  char *v30; // rax
  char *v31; // rbx
  _WORD *v32; // r8
  rsize_t v33; // r14

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = *((_QWORD *)this + 3), v9 = v7 + 80LL * *((unsigned __int16 *)this + 16), v7 == v9) )
    {
LABEL_13:
      v10 = 1;
      v11 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v11;
      v12 = 80LL * (unsigned __int16)v11;
      *(_DWORD *)(v12 + v7 + 4) = _InterlockedIncrement(*((volatile signed __int32 **)this + 1));
      v13 = (_QWORD *)(v12 + v7 + 32);
      *(_DWORD *)(v12 + v7 + 8) = *((_DWORD *)a2 + 2);
      v14 = -1;
      *(_QWORD *)(v12 + v7 + 16) = 0;
      *(_WORD *)(v12 + v7 + 24) = *((_WORD *)a2 + 32);
      *(_BYTE *)(v12 + v7 + 26) = *(_BYTE *)a2;
      *v13 = 0;
      *(_QWORD *)(v12 + v7 + 40) = *((_QWORD *)a2 + 17);
      *(_QWORD *)(v12 + v7 + 48) = *((_QWORD *)a2 + 18);
      *(_QWORD *)(v12 + v7 + 56) = 0;
      v15 = *((_QWORD *)a2 + 7);
      if ( v15 )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_BYTE *)(v15 + v17) );
        v16 = v17 + 1;
      }
      else
      {
        v16 = 1;
      }
      v18 = *((_QWORD *)a2 + 16);
      if ( v18 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_BYTE *)(v18 + v19) );
        v10 = v19 + 1;
      }
      v20 = *((_QWORD *)a2 + 3);
      if ( v20 )
      {
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)(v20 + 2 * v22) );
        v21 = 2 * v22 + 2;
      }
      else
      {
        v21 = 2;
      }
      v23 = v16 + v10 + v21;
      if ( !*(_QWORD *)(v12 + v7 + 64) || *(_QWORD *)(v12 + v7 + 72) < v23 )
      {
        v24 = wil::details::ProcessHeapAlloc(8u, v16 + v10 + v21);
        if ( v24 )
        {
          v25 = *(void **)(v12 + v7 + 64);
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v25);
          *(_QWORD *)(v12 + v7 + 64) = v24;
          v13 = (_QWORD *)(v12 + v7 + 32);
          *(_QWORD *)(v12 + v7 + 72) = v23;
        }
      }
      v27 = *(_QWORD *)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = (char *)(v27 + *(_QWORD *)(v12 + v7 + 72));
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_QWORD *)a2 + 7), v12 + v7 + 16);
        v30 = (char *)wil::details::WriteResultString<char const *>(v29, v28, *((_QWORD *)a2 + 16), v13);
        v31 = v30;
        if ( v30 == v28 )
          goto LABEL_38;
        v32 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( !v32 || !*v32 )
          goto LABEL_38;
        do
          ++v14;
        while ( v32[v14] );
        v33 = 2 * v14 + 2;
        if ( v28 - v30 >= v33 )
        {
          memcpy_s(v30, v28 - v30, v32, v33);
          *(_QWORD *)(v12 + v7 + 56) = v31;
          v31 += v33;
        }
        else
        {
LABEL_38:
          *(_QWORD *)(v12 + v7 + 56) = 0;
        }
        memset_0(v31, 0, v28 - v31);
      }
    }
    else
    {
      while ( *(_DWORD *)(v8 + 4) <= *((_DWORD *)this + 4) || *(_DWORD *)(v8 + 8) != *((_DWORD *)a2 + 2) )
      {
        v8 += 80;
        if ( v8 == v9 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x1800277c4  push    rbx
0x1800277c6  push    rbp
0x1800277c7  push    rsi
0x1800277c8  push    rdi
0x1800277c9  push    r12
0x1800277cb  push    r13
0x1800277cd  push    r14
0x1800277cf  push    r15
0x1800277d1  sub     rsp, 28h
0x1800277d5  mov     esi, [rcx+10h]
0x1800277d8  xor     r12d, r12d
0x1800277db  mov     r15, rdx
0x1800277de  mov     rbx, rcx
0x1800277e1  mov     ebp, 50h ; 'P'
0x1800277e6  cmp     [rcx+18h], r12
0x1800277ea  jnz     short loc_180027821
0x1800277ec  test    esi, esi
0x1800277ee  jz      short loc_180027821
0x1800277f0  mov     edx, 190h; dwBytes
0x1800277f5  lea     ecx, [rbp-48h]; dwFlags
0x1800277f8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800277fd  mov     [rbx+18h], rax
0x180027801  test    rax, rax
0x180027804  jz      short loc_180027821
0x180027806  mov     dword ptr [rbx+20h], 5
0x18002780d  lea     rcx, [rax+190h]
0x180027814  jmp     short loc_18002781C
0x180027816  mov     [rax], bp
0x180027819  add     rax, rbp
0x18002781c  cmp     rax, rcx
0x18002781f  jnz     short loc_180027816
0x180027821  mov     rdi, [rbx+18h]
0x180027825  test    rdi, rdi
0x180027828  jz      loc_180027A4A
0x18002782e  test    esi, esi
0x180027830  jz      short loc_180027868
0x180027832  movzx   eax, word ptr [rbx+20h]
0x180027836  mov     rcx, rdi
0x180027839  lea     rdx, [rax+rax*4]
0x18002783d  shl     rdx, 4
0x180027841  add     rdx, rdi
0x180027844  cmp     rdi, rdx
0x180027847  jz      short loc_180027868
0x180027849  mov     r8d, [rbx+10h]
0x18002784d  cmp     [rcx+4], r8d
0x180027851  jbe     short loc_180027860
0x180027853  mov     eax, [r15+8]
0x180027857  cmp     [rcx+8], eax
0x18002785a  jz      loc_180027A4A
0x180027860  add     rcx, rbp
0x180027863  cmp     rcx, rdx
0x180027866  jnz     short loc_18002784D
0x180027868  movzx   eax, word ptr [rbx+22h]
0x18002786c  mov     r8d, 1
0x180027872  movzx   ecx, word ptr [rbx+20h]
0x180027876  add     eax, r8d
0x180027879  xor     edx, edx
0x18002787b  div     ecx
0x18002787d  mov     ecx, r8d
0x180027880  movzx   eax, dx
0x180027883  mov     [rbx+22h], dx
0x180027887  lea     rsi, [rax+rax*4]
0x18002788b  mov     rax, [rbx+8]
0x18002788f  shl     rsi, 4
0x180027893  lock xadd [rax], ecx
0x180027897  add     ecx, r8d
0x18002789a  lea     r13, [rsi+rdi]
0x18002789e  mov     [rsi+rdi+4], ecx
0x1800278a2  lea     rbx, [rdi+20h]
0x1800278a6  mov     eax, [r15+8]
0x1800278aa  add     rbx, rsi
0x1800278ad  mov     [rsi+rdi+8], eax
0x1800278b1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800278b5  mov     [r13+10h], r12
0x1800278b9  movzx   eax, word ptr [r15+40h]
0x1800278be  mov     [rsi+rdi+18h], ax
0x1800278c3  mov     al, [r15]
0x1800278c6  mov     [rsi+rdi+1Ah], al
0x1800278ca  mov     [rbx], r12
0x1800278cd  mov     rax, [r15+88h]
0x1800278d4  mov     [rsi+rdi+28h], rax
0x1800278d9  mov     rax, [r15+90h]
0x1800278e0  mov     [rsi+rdi+30h], rax
0x1800278e5  mov     [rsi+rdi+38h], r12
0x1800278ea  mov     rcx, [r15+38h]
0x1800278ee  test    rcx, rcx
0x1800278f1  jnz     short loc_1800278F8
0x1800278f3  mov     edx, r8d
0x1800278f6  jmp     short loc_180027908
0x1800278f8  mov     rax, r14
0x1800278fb  inc     rax
0x1800278fe  cmp     [rcx+rax], r12b
0x180027902  jnz     short loc_1800278FB
0x180027904  lea     rdx, [rax+1]
0x180027908  mov     rcx, [r15+80h]
0x18002790f  test    rcx, rcx
0x180027912  jz      short loc_180027924
0x180027914  mov     rax, r14
0x180027917  inc     rax
0x18002791a  cmp     [rcx+rax], r12b
0x18002791e  jnz     short loc_180027917
0x180027920  lea     r8, [rax+1]; unsigned __int64
0x180027924  mov     rcx, [r15+18h]
0x180027928  test    rcx, rcx
0x18002792b  jnz     short loc_180027932
0x18002792d  lea     eax, [rcx+2]
0x180027930  jmp     short loc_180027947
0x180027932  mov     rax, r14
0x180027935  inc     rax
0x180027938  cmp     [rcx+rax*2], r12w
0x18002793d  jnz     short loc_180027935
0x18002793f  lea     rax, ds:2[rax*2]
0x180027947  lea     rbp, [r8+rax]
0x18002794b  add     rbp, rdx
0x18002794e  cmp     [rsi+rdi+40h], r12
0x180027953  jz      short loc_18002795C
0x180027955  cmp     [rsi+rdi+48h], rbp
0x18002795a  jnb     short loc_1800279AA
0x18002795c  mov     rdx, rbp; dwBytes
0x18002795f  mov     ecx, 8; dwFlags
0x180027964  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180027969  mov     r12, rax
0x18002796c  test    rax, rax
0x18002796f  jz      short loc_1800279A7
0x180027971  mov     rbx, [rsi+rdi+40h]
0x180027976  call    cs:__imp_GetProcessHeap
0x18002797d  nop     dword ptr [rax+rax+00h]
0x180027982  mov     r8, rbx; lpMem
0x180027985  xor     edx, edx; dwFlags
0x180027987  mov     rcx, rax; hHeap
0x18002798a  call    cs:__imp_HeapFree
0x180027991  nop     dword ptr [rax+rax+00h]
0x180027996  lea     rbx, [rdi+20h]
0x18002799a  mov     [rsi+rdi+40h], r12
0x18002799f  add     rbx, rsi
0x1800279a2  mov     [rsi+rdi+48h], rbp
0x1800279a7  xor     r12d, r12d
0x1800279aa  mov     rcx, [rsi+rdi+40h]
0x1800279af  test    rcx, rcx
0x1800279b2  jz      loc_180027A4A
0x1800279b8  mov     rbp, [rsi+rdi+48h]
0x1800279bd  lea     r9, [r13+10h]
0x1800279c1  mov     r8, [r15+38h]
0x1800279c5  add     rbp, rcx
0x1800279c8  mov     rdx, rbp
0x1800279cb  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800279d0  mov     r8, [r15+80h]
0x1800279d7  mov     r9, rbx
0x1800279da  mov     rdx, rbp
0x1800279dd  mov     rcx, rax
0x1800279e0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800279e5  mov     rbx, rax
0x1800279e8  cmp     rax, rbp
0x1800279eb  jz      short loc_180027A35
0x1800279ed  mov     r8, [r15+18h]; Source
0x1800279f1  test    r8, r8
0x1800279f4  jz      short loc_180027A35
0x1800279f6  cmp     [r8], r12w
0x1800279fa  jz      short loc_180027A35
0x1800279fc  inc     r14
0x1800279ff  cmp     [r8+r14*2], r12w
0x180027a04  jnz     short loc_1800279FC
0x180027a06  mov     rdx, rbp
0x180027a09  lea     r14, ds:2[r14*2]
0x180027a11  sub     rdx, rbx; DestinationSize
0x180027a14  cmp     rdx, r14
0x180027a17  jb      short loc_180027A35
0x180027a19  mov     r9, r14; SourceSize
0x180027a1c  mov     rcx, rbx; Destination
0x180027a1f  call    cs:__imp_memcpy_s
0x180027a26  nop     dword ptr [rax+rax+00h]
0x180027a2b  mov     [rsi+rdi+38h], rbx
0x180027a30  add     rbx, r14
0x180027a33  jmp     short loc_180027A3A
0x180027a35  mov     [rsi+rdi+38h], r12
0x180027a3a  sub     rbp, rbx
0x180027a3d  xor     edx, edx; Val
0x180027a3f  mov     r8, rbp; Size
0x180027a42  mov     rcx, rbx; void *
0x180027a45  call    memset_0
0x180027a4a  add     rsp, 28h
0x180027a4e  pop     r15
0x180027a50  pop     r14
0x180027a52  pop     r13
0x180027a54  pop     r12
0x180027a56  pop     rdi
0x180027a57  pop     rsi
0x180027a58  pop     rbp
0x180027a59  pop     rbx
0x180027a5a  retn
```
