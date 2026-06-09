# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180010b78`
- end: `0x180010dfd`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b7f0`

## callees

- `0x180008d7c`
- `0x18000e5e4`
- `0x180010b78`
- `0x180029882`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180010dc7`
- `msvcrt!memcpy_s` at `0x180010dc7`
- `KERNEL32!GetProcessHeap` at `0x180010d2a`
- `KERNEL32!GetProcessHeap` at `0x180010d2a`
- `KERNEL32!HeapFree` at `0x180010d38`
- `KERNEL32!HeapFree` at `0x180010d38`

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
  char *v27; // rcx
  char *v28; // rbp
  char *v29; // rax
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
      v27 = *(char **)(v12 + v7 + 64);
      if ( v27 )
      {
        v28 = &v27[*(_QWORD *)(v12 + v7 + 72)];
        v29 = wil::details::WriteResultString<char const *>(v27, v28, *((_BYTE **)a2 + 7), (_QWORD *)(v12 + v7 + 16));
        v30 = wil::details::WriteResultString<char const *>(v29, v28, *((_BYTE **)a2 + 16), v13);
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
0x180010b78  push    rbx
0x180010b7a  push    rbp
0x180010b7b  push    rsi
0x180010b7c  push    rdi
0x180010b7d  push    r12
0x180010b7f  push    r13
0x180010b81  push    r14
0x180010b83  push    r15
0x180010b85  sub     rsp, 28h
0x180010b89  mov     esi, [rcx+10h]
0x180010b8c  xor     r12d, r12d
0x180010b8f  mov     r15, rdx
0x180010b92  mov     rbx, rcx
0x180010b95  mov     ebp, 50h ; 'P'
0x180010b9a  cmp     [rcx+18h], r12
0x180010b9e  jnz     short loc_180010BD5
0x180010ba0  test    esi, esi
0x180010ba2  jz      short loc_180010BD5
0x180010ba4  mov     edx, 190h; dwBytes
0x180010ba9  lea     ecx, [rbp-48h]; dwFlags
0x180010bac  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010bb1  mov     [rbx+18h], rax
0x180010bb5  test    rax, rax
0x180010bb8  jz      short loc_180010BD5
0x180010bba  mov     dword ptr [rbx+20h], 5
0x180010bc1  lea     rcx, [rax+190h]
0x180010bc8  jmp     short loc_180010BD0
0x180010bca  mov     [rax], bp
0x180010bcd  add     rax, rbp
0x180010bd0  cmp     rax, rcx
0x180010bd3  jnz     short loc_180010BCA
0x180010bd5  mov     rdi, [rbx+18h]
0x180010bd9  test    rdi, rdi
0x180010bdc  jz      loc_180010DEC
0x180010be2  test    esi, esi
0x180010be4  jz      short loc_180010C1C
0x180010be6  movzx   eax, word ptr [rbx+20h]
0x180010bea  mov     rcx, rdi
0x180010bed  lea     rdx, [rax+rax*4]
0x180010bf1  shl     rdx, 4
0x180010bf5  add     rdx, rdi
0x180010bf8  cmp     rdi, rdx
0x180010bfb  jz      short loc_180010C1C
0x180010bfd  mov     r8d, [rbx+10h]
0x180010c01  cmp     [rcx+4], r8d
0x180010c05  jbe     short loc_180010C14
0x180010c07  mov     eax, [r15+8]
0x180010c0b  cmp     [rcx+8], eax
0x180010c0e  jz      loc_180010DEC
0x180010c14  add     rcx, rbp
0x180010c17  cmp     rcx, rdx
0x180010c1a  jnz     short loc_180010C01
0x180010c1c  movzx   eax, word ptr [rbx+22h]
0x180010c20  mov     r8d, 1
0x180010c26  movzx   ecx, word ptr [rbx+20h]
0x180010c2a  add     eax, r8d
0x180010c2d  xor     edx, edx
0x180010c2f  div     ecx
0x180010c31  mov     ecx, r8d
0x180010c34  movzx   eax, dx
0x180010c37  mov     [rbx+22h], dx
0x180010c3b  lea     rsi, [rax+rax*4]
0x180010c3f  mov     rax, [rbx+8]
0x180010c43  shl     rsi, 4
0x180010c47  lock xadd [rax], ecx
0x180010c4b  add     ecx, r8d
0x180010c4e  lea     r13, [rsi+rdi]
0x180010c52  mov     [rsi+rdi+4], ecx
0x180010c56  lea     rbx, [rdi+20h]
0x180010c5a  mov     eax, [r15+8]
0x180010c5e  add     rbx, rsi
0x180010c61  mov     [rsi+rdi+8], eax
0x180010c65  or      r14, 0FFFFFFFFFFFFFFFFh
0x180010c69  mov     [r13+10h], r12
0x180010c6d  movzx   eax, word ptr [r15+40h]
0x180010c72  mov     [rsi+rdi+18h], ax
0x180010c77  mov     al, [r15]
0x180010c7a  mov     [rsi+rdi+1Ah], al
0x180010c7e  mov     [rbx], r12
0x180010c81  mov     rax, [r15+88h]
0x180010c88  mov     [rsi+rdi+28h], rax
0x180010c8d  mov     rax, [r15+90h]
0x180010c94  mov     [rsi+rdi+30h], rax
0x180010c99  mov     [rsi+rdi+38h], r12
0x180010c9e  mov     rcx, [r15+38h]
0x180010ca2  test    rcx, rcx
0x180010ca5  jnz     short loc_180010CAC
0x180010ca7  mov     edx, r8d
0x180010caa  jmp     short loc_180010CBC
0x180010cac  mov     rax, r14
0x180010caf  inc     rax
0x180010cb2  cmp     [rcx+rax], r12b
0x180010cb6  jnz     short loc_180010CAF
0x180010cb8  lea     rdx, [rax+1]
0x180010cbc  mov     rcx, [r15+80h]
0x180010cc3  test    rcx, rcx
0x180010cc6  jz      short loc_180010CD8
0x180010cc8  mov     rax, r14
0x180010ccb  inc     rax
0x180010cce  cmp     [rcx+rax], r12b
0x180010cd2  jnz     short loc_180010CCB
0x180010cd4  lea     r8, [rax+1]; unsigned __int64
0x180010cd8  mov     rcx, [r15+18h]
0x180010cdc  test    rcx, rcx
0x180010cdf  jnz     short loc_180010CE6
0x180010ce1  lea     eax, [rcx+2]
0x180010ce4  jmp     short loc_180010CFB
0x180010ce6  mov     rax, r14
0x180010ce9  inc     rax
0x180010cec  cmp     [rcx+rax*2], r12w
0x180010cf1  jnz     short loc_180010CE9
0x180010cf3  lea     rax, ds:2[rax*2]
0x180010cfb  lea     rbp, [r8+rax]
0x180010cff  add     rbp, rdx
0x180010d02  cmp     [rsi+rdi+40h], r12
0x180010d07  jz      short loc_180010D10
0x180010d09  cmp     [rsi+rdi+48h], rbp
0x180010d0e  jnb     short loc_180010D52
0x180010d10  mov     rdx, rbp; dwBytes
0x180010d13  mov     ecx, 8; dwFlags
0x180010d18  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010d1d  mov     r12, rax
0x180010d20  test    rax, rax
0x180010d23  jz      short loc_180010D4F
0x180010d25  mov     rbx, [rsi+rdi+40h]
0x180010d2a  call    cs:__imp_GetProcessHeap
0x180010d30  mov     r8, rbx; lpMem
0x180010d33  xor     edx, edx; dwFlags
0x180010d35  mov     rcx, rax; hHeap
0x180010d38  call    cs:__imp_HeapFree
0x180010d3e  lea     rbx, [rdi+20h]
0x180010d42  mov     [rsi+rdi+40h], r12
0x180010d47  add     rbx, rsi
0x180010d4a  mov     [rsi+rdi+48h], rbp
0x180010d4f  xor     r12d, r12d
0x180010d52  mov     rcx, [rsi+rdi+40h]
0x180010d57  test    rcx, rcx
0x180010d5a  jz      loc_180010DEC
0x180010d60  mov     rbp, [rsi+rdi+48h]
0x180010d65  lea     r9, [r13+10h]
0x180010d69  mov     r8, [r15+38h]
0x180010d6d  add     rbp, rcx
0x180010d70  mov     rdx, rbp
0x180010d73  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010d78  mov     r8, [r15+80h]
0x180010d7f  mov     r9, rbx
0x180010d82  mov     rdx, rbp
0x180010d85  mov     rcx, rax
0x180010d88  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010d8d  mov     rbx, rax
0x180010d90  cmp     rax, rbp
0x180010d93  jz      short loc_180010DD7
0x180010d95  mov     r8, [r15+18h]; Source
0x180010d99  test    r8, r8
0x180010d9c  jz      short loc_180010DD7
0x180010d9e  cmp     [r8], r12w
0x180010da2  jz      short loc_180010DD7
0x180010da4  inc     r14
0x180010da7  cmp     [r8+r14*2], r12w
0x180010dac  jnz     short loc_180010DA4
0x180010dae  mov     rdx, rbp
0x180010db1  lea     r14, ds:2[r14*2]
0x180010db9  sub     rdx, rbx; DestinationSize
0x180010dbc  cmp     rdx, r14
0x180010dbf  jb      short loc_180010DD7
0x180010dc1  mov     r9, r14; SourceSize
0x180010dc4  mov     rcx, rbx; Destination
0x180010dc7  call    cs:__imp_memcpy_s
0x180010dcd  mov     [rsi+rdi+38h], rbx
0x180010dd2  add     rbx, r14
0x180010dd5  jmp     short loc_180010DDC
0x180010dd7  mov     [rsi+rdi+38h], r12
0x180010ddc  sub     rbp, rbx
0x180010ddf  xor     edx, edx; Val
0x180010de1  mov     r8, rbp; Size
0x180010de4  mov     rcx, rbx; void *
0x180010de7  call    memset_0
0x180010dec  add     rsp, 28h
0x180010df0  pop     r15
0x180010df2  pop     r14
0x180010df4  pop     r13
0x180010df6  pop     r12
0x180010df8  pop     rdi
0x180010df9  pop     rsi
0x180010dfa  pop     rbp
0x180010dfb  pop     rbx
0x180010dfc  retn
```
