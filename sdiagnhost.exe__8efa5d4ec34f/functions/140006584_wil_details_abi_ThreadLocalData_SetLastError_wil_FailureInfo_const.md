# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140006584`
- end: `0x140006809`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004280`

## callees

- `0x140001c8f`
- `0x140003738`
- `0x140005254`
- `0x140006584`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140006736`
- `KERNEL32!GetProcessHeap` at `0x140006736`
- `KERNEL32!HeapFree` at `0x140006744`
- `KERNEL32!HeapFree` at `0x140006744`
- `msvcrt!memcpy_s` at `0x1400067d3`
- `msvcrt!memcpy_s` at `0x1400067d3`

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
0x140006584  push    rbx
0x140006586  push    rbp
0x140006587  push    rsi
0x140006588  push    rdi
0x140006589  push    r12
0x14000658b  push    r13
0x14000658d  push    r14
0x14000658f  push    r15
0x140006591  sub     rsp, 28h
0x140006595  mov     esi, [rcx+10h]
0x140006598  xor     r12d, r12d
0x14000659b  mov     r15, rdx
0x14000659e  mov     rbx, rcx
0x1400065a1  mov     ebp, 50h ; 'P'
0x1400065a6  cmp     [rcx+18h], r12
0x1400065aa  jnz     short loc_1400065E1
0x1400065ac  test    esi, esi
0x1400065ae  jz      short loc_1400065E1
0x1400065b0  mov     edx, 190h; dwBytes
0x1400065b5  lea     ecx, [rbp-48h]; dwFlags
0x1400065b8  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400065bd  mov     [rbx+18h], rax
0x1400065c1  test    rax, rax
0x1400065c4  jz      short loc_1400065E1
0x1400065c6  mov     dword ptr [rbx+20h], 5
0x1400065cd  lea     rcx, [rax+190h]
0x1400065d4  jmp     short loc_1400065DC
0x1400065d6  mov     [rax], bp
0x1400065d9  add     rax, rbp
0x1400065dc  cmp     rax, rcx
0x1400065df  jnz     short loc_1400065D6
0x1400065e1  mov     rdi, [rbx+18h]
0x1400065e5  test    rdi, rdi
0x1400065e8  jz      loc_1400067F8
0x1400065ee  test    esi, esi
0x1400065f0  jz      short loc_140006628
0x1400065f2  movzx   eax, word ptr [rbx+20h]
0x1400065f6  mov     rcx, rdi
0x1400065f9  lea     rdx, [rax+rax*4]
0x1400065fd  shl     rdx, 4
0x140006601  add     rdx, rdi
0x140006604  cmp     rdi, rdx
0x140006607  jz      short loc_140006628
0x140006609  mov     r8d, [rbx+10h]
0x14000660d  cmp     [rcx+4], r8d
0x140006611  jbe     short loc_140006620
0x140006613  mov     eax, [r15+8]
0x140006617  cmp     [rcx+8], eax
0x14000661a  jz      loc_1400067F8
0x140006620  add     rcx, rbp
0x140006623  cmp     rcx, rdx
0x140006626  jnz     short loc_14000660D
0x140006628  movzx   eax, word ptr [rbx+22h]
0x14000662c  mov     r8d, 1
0x140006632  movzx   ecx, word ptr [rbx+20h]
0x140006636  add     eax, r8d
0x140006639  xor     edx, edx
0x14000663b  div     ecx
0x14000663d  mov     ecx, r8d
0x140006640  movzx   eax, dx
0x140006643  mov     [rbx+22h], dx
0x140006647  lea     rsi, [rax+rax*4]
0x14000664b  mov     rax, [rbx+8]
0x14000664f  shl     rsi, 4
0x140006653  lock xadd [rax], ecx
0x140006657  add     ecx, r8d
0x14000665a  lea     r13, [rsi+rdi]
0x14000665e  mov     [rsi+rdi+4], ecx
0x140006662  lea     rbx, [rdi+20h]
0x140006666  mov     eax, [r15+8]
0x14000666a  add     rbx, rsi
0x14000666d  mov     [rsi+rdi+8], eax
0x140006671  or      r14, 0FFFFFFFFFFFFFFFFh
0x140006675  mov     [r13+10h], r12
0x140006679  movzx   eax, word ptr [r15+40h]
0x14000667e  mov     [rsi+rdi+18h], ax
0x140006683  mov     al, [r15]
0x140006686  mov     [rsi+rdi+1Ah], al
0x14000668a  mov     [rbx], r12
0x14000668d  mov     rax, [r15+88h]
0x140006694  mov     [rsi+rdi+28h], rax
0x140006699  mov     rax, [r15+90h]
0x1400066a0  mov     [rsi+rdi+30h], rax
0x1400066a5  mov     [rsi+rdi+38h], r12
0x1400066aa  mov     rcx, [r15+38h]
0x1400066ae  test    rcx, rcx
0x1400066b1  jnz     short loc_1400066B8
0x1400066b3  mov     edx, r8d
0x1400066b6  jmp     short loc_1400066C8
0x1400066b8  mov     rax, r14
0x1400066bb  inc     rax
0x1400066be  cmp     [rcx+rax], r12b
0x1400066c2  jnz     short loc_1400066BB
0x1400066c4  lea     rdx, [rax+1]
0x1400066c8  mov     rcx, [r15+80h]
0x1400066cf  test    rcx, rcx
0x1400066d2  jz      short loc_1400066E4
0x1400066d4  mov     rax, r14
0x1400066d7  inc     rax
0x1400066da  cmp     [rcx+rax], r12b
0x1400066de  jnz     short loc_1400066D7
0x1400066e0  lea     r8, [rax+1]; unsigned __int64
0x1400066e4  mov     rcx, [r15+18h]
0x1400066e8  test    rcx, rcx
0x1400066eb  jnz     short loc_1400066F2
0x1400066ed  lea     eax, [rcx+2]
0x1400066f0  jmp     short loc_140006707
0x1400066f2  mov     rax, r14
0x1400066f5  inc     rax
0x1400066f8  cmp     [rcx+rax*2], r12w
0x1400066fd  jnz     short loc_1400066F5
0x1400066ff  lea     rax, ds:2[rax*2]
0x140006707  lea     rbp, [r8+rax]
0x14000670b  add     rbp, rdx
0x14000670e  cmp     [rsi+rdi+40h], r12
0x140006713  jz      short loc_14000671C
0x140006715  cmp     [rsi+rdi+48h], rbp
0x14000671a  jnb     short loc_14000675E
0x14000671c  mov     rdx, rbp; dwBytes
0x14000671f  mov     ecx, 8; dwFlags
0x140006724  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006729  mov     r12, rax
0x14000672c  test    rax, rax
0x14000672f  jz      short loc_14000675B
0x140006731  mov     rbx, [rsi+rdi+40h]
0x140006736  call    cs:__imp_GetProcessHeap
0x14000673c  mov     r8, rbx; lpMem
0x14000673f  xor     edx, edx; dwFlags
0x140006741  mov     rcx, rax; hHeap
0x140006744  call    cs:__imp_HeapFree
0x14000674a  lea     rbx, [rdi+20h]
0x14000674e  mov     [rsi+rdi+40h], r12
0x140006753  add     rbx, rsi
0x140006756  mov     [rsi+rdi+48h], rbp
0x14000675b  xor     r12d, r12d
0x14000675e  mov     rcx, [rsi+rdi+40h]
0x140006763  test    rcx, rcx
0x140006766  jz      loc_1400067F8
0x14000676c  mov     rbp, [rsi+rdi+48h]
0x140006771  lea     r9, [r13+10h]
0x140006775  mov     r8, [r15+38h]
0x140006779  add     rbp, rcx
0x14000677c  mov     rdx, rbp
0x14000677f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006784  mov     r8, [r15+80h]
0x14000678b  mov     r9, rbx
0x14000678e  mov     rdx, rbp
0x140006791  mov     rcx, rax
0x140006794  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006799  mov     rbx, rax
0x14000679c  cmp     rax, rbp
0x14000679f  jz      short loc_1400067E3
0x1400067a1  mov     r8, [r15+18h]; Source
0x1400067a5  test    r8, r8
0x1400067a8  jz      short loc_1400067E3
0x1400067aa  cmp     [r8], r12w
0x1400067ae  jz      short loc_1400067E3
0x1400067b0  inc     r14
0x1400067b3  cmp     [r8+r14*2], r12w
0x1400067b8  jnz     short loc_1400067B0
0x1400067ba  mov     rdx, rbp
0x1400067bd  lea     r14, ds:2[r14*2]
0x1400067c5  sub     rdx, rbx; DestinationSize
0x1400067c8  cmp     rdx, r14
0x1400067cb  jb      short loc_1400067E3
0x1400067cd  mov     r9, r14; SourceSize
0x1400067d0  mov     rcx, rbx; Destination
0x1400067d3  call    cs:__imp_memcpy_s
0x1400067d9  mov     [rsi+rdi+38h], rbx
0x1400067de  add     rbx, r14
0x1400067e1  jmp     short loc_1400067E8
0x1400067e3  mov     [rsi+rdi+38h], r12
0x1400067e8  sub     rbp, rbx
0x1400067eb  xor     edx, edx; Val
0x1400067ed  mov     r8, rbp; Size
0x1400067f0  mov     rcx, rbx; void *
0x1400067f3  call    memset_0
0x1400067f8  add     rsp, 28h
0x1400067fc  pop     r15
0x1400067fe  pop     r14
0x140006800  pop     r13
0x140006802  pop     r12
0x140006804  pop     rdi
0x140006805  pop     rsi
0x140006806  pop     rbp
0x140006807  pop     rbx
0x140006808  retn
```
