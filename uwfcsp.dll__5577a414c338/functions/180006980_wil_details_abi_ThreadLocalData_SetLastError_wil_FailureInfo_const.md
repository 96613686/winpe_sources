# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180006980`
- end: `0x180006c05`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005600`

## callees

- `0x180004d50`
- `0x180006638`
- `0x180006980`
- `0x18001a1d6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006bcf`
- `msvcrt!memcpy_s` at `0x180006bcf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b40`

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
0x180006980  push    rbx
0x180006982  push    rbp
0x180006983  push    rsi
0x180006984  push    rdi
0x180006985  push    r12
0x180006987  push    r13
0x180006989  push    r14
0x18000698b  push    r15
0x18000698d  sub     rsp, 28h
0x180006991  mov     esi, [rcx+10h]
0x180006994  xor     r12d, r12d
0x180006997  mov     r15, rdx
0x18000699a  mov     rbx, rcx
0x18000699d  mov     ebp, 50h ; 'P'
0x1800069a2  cmp     [rcx+18h], r12
0x1800069a6  jnz     short loc_1800069DD
0x1800069a8  test    esi, esi
0x1800069aa  jz      short loc_1800069DD
0x1800069ac  mov     edx, 190h; dwBytes
0x1800069b1  lea     ecx, [rbp-48h]; dwFlags
0x1800069b4  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800069b9  mov     [rbx+18h], rax
0x1800069bd  test    rax, rax
0x1800069c0  jz      short loc_1800069DD
0x1800069c2  mov     dword ptr [rbx+20h], 5
0x1800069c9  lea     rcx, [rax+190h]
0x1800069d0  jmp     short loc_1800069D8
0x1800069d2  mov     [rax], bp
0x1800069d5  add     rax, rbp
0x1800069d8  cmp     rax, rcx
0x1800069db  jnz     short loc_1800069D2
0x1800069dd  mov     rdi, [rbx+18h]
0x1800069e1  test    rdi, rdi
0x1800069e4  jz      loc_180006BF4
0x1800069ea  test    esi, esi
0x1800069ec  jz      short loc_180006A24
0x1800069ee  movzx   eax, word ptr [rbx+20h]
0x1800069f2  mov     rcx, rdi
0x1800069f5  lea     rdx, [rax+rax*4]
0x1800069f9  shl     rdx, 4
0x1800069fd  add     rdx, rdi
0x180006a00  cmp     rdi, rdx
0x180006a03  jz      short loc_180006A24
0x180006a05  mov     r8d, [rbx+10h]
0x180006a09  cmp     [rcx+4], r8d
0x180006a0d  jbe     short loc_180006A1C
0x180006a0f  mov     eax, [r15+8]
0x180006a13  cmp     [rcx+8], eax
0x180006a16  jz      loc_180006BF4
0x180006a1c  add     rcx, rbp
0x180006a1f  cmp     rcx, rdx
0x180006a22  jnz     short loc_180006A09
0x180006a24  movzx   eax, word ptr [rbx+22h]
0x180006a28  mov     r8d, 1
0x180006a2e  movzx   ecx, word ptr [rbx+20h]
0x180006a32  add     eax, r8d
0x180006a35  xor     edx, edx
0x180006a37  div     ecx
0x180006a39  mov     ecx, r8d
0x180006a3c  movzx   eax, dx
0x180006a3f  mov     [rbx+22h], dx
0x180006a43  lea     rsi, [rax+rax*4]
0x180006a47  mov     rax, [rbx+8]
0x180006a4b  shl     rsi, 4
0x180006a4f  lock xadd [rax], ecx
0x180006a53  add     ecx, r8d
0x180006a56  lea     r13, [rsi+rdi]
0x180006a5a  mov     [rsi+rdi+4], ecx
0x180006a5e  lea     rbx, [rdi+20h]
0x180006a62  mov     eax, [r15+8]
0x180006a66  add     rbx, rsi
0x180006a69  mov     [rsi+rdi+8], eax
0x180006a6d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180006a71  mov     [r13+10h], r12
0x180006a75  movzx   eax, word ptr [r15+40h]
0x180006a7a  mov     [rsi+rdi+18h], ax
0x180006a7f  mov     al, [r15]
0x180006a82  mov     [rsi+rdi+1Ah], al
0x180006a86  mov     [rbx], r12
0x180006a89  mov     rax, [r15+88h]
0x180006a90  mov     [rsi+rdi+28h], rax
0x180006a95  mov     rax, [r15+90h]
0x180006a9c  mov     [rsi+rdi+30h], rax
0x180006aa1  mov     [rsi+rdi+38h], r12
0x180006aa6  mov     rcx, [r15+38h]
0x180006aaa  test    rcx, rcx
0x180006aad  jnz     short loc_180006AB4
0x180006aaf  mov     edx, r8d
0x180006ab2  jmp     short loc_180006AC4
0x180006ab4  mov     rax, r14
0x180006ab7  inc     rax
0x180006aba  cmp     [rcx+rax], r12b
0x180006abe  jnz     short loc_180006AB7
0x180006ac0  lea     rdx, [rax+1]
0x180006ac4  mov     rcx, [r15+80h]
0x180006acb  test    rcx, rcx
0x180006ace  jz      short loc_180006AE0
0x180006ad0  mov     rax, r14
0x180006ad3  inc     rax
0x180006ad6  cmp     [rcx+rax], r12b
0x180006ada  jnz     short loc_180006AD3
0x180006adc  lea     r8, [rax+1]; unsigned __int64
0x180006ae0  mov     rcx, [r15+18h]
0x180006ae4  test    rcx, rcx
0x180006ae7  jnz     short loc_180006AEE
0x180006ae9  lea     eax, [rcx+2]
0x180006aec  jmp     short loc_180006B03
0x180006aee  mov     rax, r14
0x180006af1  inc     rax
0x180006af4  cmp     [rcx+rax*2], r12w
0x180006af9  jnz     short loc_180006AF1
0x180006afb  lea     rax, ds:2[rax*2]
0x180006b03  lea     rbp, [r8+rax]
0x180006b07  add     rbp, rdx
0x180006b0a  cmp     [rsi+rdi+40h], r12
0x180006b0f  jz      short loc_180006B18
0x180006b11  cmp     [rsi+rdi+48h], rbp
0x180006b16  jnb     short loc_180006B5A
0x180006b18  mov     rdx, rbp; dwBytes
0x180006b1b  mov     ecx, 8; dwFlags
0x180006b20  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006b25  mov     r12, rax
0x180006b28  test    rax, rax
0x180006b2b  jz      short loc_180006B57
0x180006b2d  mov     rbx, [rsi+rdi+40h]
0x180006b32  call    cs:__imp_GetProcessHeap
0x180006b38  mov     r8, rbx; lpMem
0x180006b3b  xor     edx, edx; dwFlags
0x180006b3d  mov     rcx, rax; hHeap
0x180006b40  call    cs:__imp_HeapFree
0x180006b46  lea     rbx, [rdi+20h]
0x180006b4a  mov     [rsi+rdi+40h], r12
0x180006b4f  add     rbx, rsi
0x180006b52  mov     [rsi+rdi+48h], rbp
0x180006b57  xor     r12d, r12d
0x180006b5a  mov     rcx, [rsi+rdi+40h]
0x180006b5f  test    rcx, rcx
0x180006b62  jz      loc_180006BF4
0x180006b68  mov     rbp, [rsi+rdi+48h]
0x180006b6d  lea     r9, [r13+10h]
0x180006b71  mov     r8, [r15+38h]
0x180006b75  add     rbp, rcx
0x180006b78  mov     rdx, rbp
0x180006b7b  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006b80  mov     r8, [r15+80h]
0x180006b87  mov     r9, rbx
0x180006b8a  mov     rdx, rbp
0x180006b8d  mov     rcx, rax
0x180006b90  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006b95  mov     rbx, rax
0x180006b98  cmp     rax, rbp
0x180006b9b  jz      short loc_180006BDF
0x180006b9d  mov     r8, [r15+18h]; Source
0x180006ba1  test    r8, r8
0x180006ba4  jz      short loc_180006BDF
0x180006ba6  cmp     [r8], r12w
0x180006baa  jz      short loc_180006BDF
0x180006bac  inc     r14
0x180006baf  cmp     [r8+r14*2], r12w
0x180006bb4  jnz     short loc_180006BAC
0x180006bb6  mov     rdx, rbp
0x180006bb9  lea     r14, ds:2[r14*2]
0x180006bc1  sub     rdx, rbx; DestinationSize
0x180006bc4  cmp     rdx, r14
0x180006bc7  jb      short loc_180006BDF
0x180006bc9  mov     r9, r14; SourceSize
0x180006bcc  mov     rcx, rbx; Destination
0x180006bcf  call    cs:__imp_memcpy_s
0x180006bd5  mov     [rsi+rdi+38h], rbx
0x180006bda  add     rbx, r14
0x180006bdd  jmp     short loc_180006BE4
0x180006bdf  mov     [rsi+rdi+38h], r12
0x180006be4  sub     rbp, rbx
0x180006be7  xor     edx, edx; Val
0x180006be9  mov     r8, rbp; Size
0x180006bec  mov     rcx, rbx; void *
0x180006bef  call    memset_0
0x180006bf4  add     rsp, 28h
0x180006bf8  pop     r15
0x180006bfa  pop     r14
0x180006bfc  pop     r13
0x180006bfe  pop     r12
0x180006c00  pop     rdi
0x180006c01  pop     rsi
0x180006c02  pop     rbp
0x180006c03  pop     rbx
0x180006c04  retn
```
