# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140006cd4`
- end: `0x140006f59`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `645`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004190`

## callees

- `0x140002f08`
- `0x1400063dc`
- `0x140006cd4`
- `0x14002e3e2`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140006e86`
- `KERNEL32!GetProcessHeap` at `0x140006e86`
- `KERNEL32!HeapFree` at `0x140006e94`
- `KERNEL32!HeapFree` at `0x140006e94`
- `msvcrt!memcpy_s` at `0x140006f23`
- `msvcrt!memcpy_s` at `0x140006f23`

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
0x140006cd4  push    rbx
0x140006cd6  push    rbp
0x140006cd7  push    rsi
0x140006cd8  push    rdi
0x140006cd9  push    r12
0x140006cdb  push    r13
0x140006cdd  push    r14
0x140006cdf  push    r15
0x140006ce1  sub     rsp, 28h
0x140006ce5  mov     esi, [rcx+10h]
0x140006ce8  xor     r12d, r12d
0x140006ceb  mov     r15, rdx
0x140006cee  mov     rbx, rcx
0x140006cf1  mov     ebp, 50h ; 'P'
0x140006cf6  cmp     [rcx+18h], r12
0x140006cfa  jnz     short loc_140006D31
0x140006cfc  test    esi, esi
0x140006cfe  jz      short loc_140006D31
0x140006d00  mov     edx, 190h; dwBytes
0x140006d05  lea     ecx, [rbp-48h]; dwFlags
0x140006d08  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006d0d  mov     [rbx+18h], rax
0x140006d11  test    rax, rax
0x140006d14  jz      short loc_140006D31
0x140006d16  mov     dword ptr [rbx+20h], 5
0x140006d1d  lea     rcx, [rax+190h]
0x140006d24  jmp     short loc_140006D2C
0x140006d26  mov     [rax], bp
0x140006d29  add     rax, rbp
0x140006d2c  cmp     rax, rcx
0x140006d2f  jnz     short loc_140006D26
0x140006d31  mov     rdi, [rbx+18h]
0x140006d35  test    rdi, rdi
0x140006d38  jz      loc_140006F48
0x140006d3e  test    esi, esi
0x140006d40  jz      short loc_140006D78
0x140006d42  movzx   eax, word ptr [rbx+20h]
0x140006d46  mov     rcx, rdi
0x140006d49  lea     rdx, [rax+rax*4]
0x140006d4d  shl     rdx, 4
0x140006d51  add     rdx, rdi
0x140006d54  cmp     rdi, rdx
0x140006d57  jz      short loc_140006D78
0x140006d59  mov     r8d, [rbx+10h]
0x140006d5d  cmp     [rcx+4], r8d
0x140006d61  jbe     short loc_140006D70
0x140006d63  mov     eax, [r15+8]
0x140006d67  cmp     [rcx+8], eax
0x140006d6a  jz      loc_140006F48
0x140006d70  add     rcx, rbp
0x140006d73  cmp     rcx, rdx
0x140006d76  jnz     short loc_140006D5D
0x140006d78  movzx   eax, word ptr [rbx+22h]
0x140006d7c  mov     r8d, 1
0x140006d82  movzx   ecx, word ptr [rbx+20h]
0x140006d86  add     eax, r8d
0x140006d89  xor     edx, edx
0x140006d8b  div     ecx
0x140006d8d  mov     ecx, r8d
0x140006d90  movzx   eax, dx
0x140006d93  mov     [rbx+22h], dx
0x140006d97  lea     rsi, [rax+rax*4]
0x140006d9b  mov     rax, [rbx+8]
0x140006d9f  shl     rsi, 4
0x140006da3  lock xadd [rax], ecx
0x140006da7  add     ecx, r8d
0x140006daa  lea     r13, [rsi+rdi]
0x140006dae  mov     [rsi+rdi+4], ecx
0x140006db2  lea     rbx, [rdi+20h]
0x140006db6  mov     eax, [r15+8]
0x140006dba  add     rbx, rsi
0x140006dbd  mov     [rsi+rdi+8], eax
0x140006dc1  or      r14, 0FFFFFFFFFFFFFFFFh
0x140006dc5  mov     [r13+10h], r12
0x140006dc9  movzx   eax, word ptr [r15+40h]
0x140006dce  mov     [rsi+rdi+18h], ax
0x140006dd3  mov     al, [r15]
0x140006dd6  mov     [rsi+rdi+1Ah], al
0x140006dda  mov     [rbx], r12
0x140006ddd  mov     rax, [r15+88h]
0x140006de4  mov     [rsi+rdi+28h], rax
0x140006de9  mov     rax, [r15+90h]
0x140006df0  mov     [rsi+rdi+30h], rax
0x140006df5  mov     [rsi+rdi+38h], r12
0x140006dfa  mov     rcx, [r15+38h]
0x140006dfe  test    rcx, rcx
0x140006e01  jnz     short loc_140006E08
0x140006e03  mov     edx, r8d
0x140006e06  jmp     short loc_140006E18
0x140006e08  mov     rax, r14
0x140006e0b  inc     rax
0x140006e0e  cmp     [rcx+rax], r12b
0x140006e12  jnz     short loc_140006E0B
0x140006e14  lea     rdx, [rax+1]
0x140006e18  mov     rcx, [r15+80h]
0x140006e1f  test    rcx, rcx
0x140006e22  jz      short loc_140006E34
0x140006e24  mov     rax, r14
0x140006e27  inc     rax
0x140006e2a  cmp     [rcx+rax], r12b
0x140006e2e  jnz     short loc_140006E27
0x140006e30  lea     r8, [rax+1]; unsigned __int64
0x140006e34  mov     rcx, [r15+18h]
0x140006e38  test    rcx, rcx
0x140006e3b  jnz     short loc_140006E42
0x140006e3d  lea     eax, [rcx+2]
0x140006e40  jmp     short loc_140006E57
0x140006e42  mov     rax, r14
0x140006e45  inc     rax
0x140006e48  cmp     [rcx+rax*2], r12w
0x140006e4d  jnz     short loc_140006E45
0x140006e4f  lea     rax, ds:2[rax*2]
0x140006e57  lea     rbp, [r8+rax]
0x140006e5b  add     rbp, rdx
0x140006e5e  cmp     [rsi+rdi+40h], r12
0x140006e63  jz      short loc_140006E6C
0x140006e65  cmp     [rsi+rdi+48h], rbp
0x140006e6a  jnb     short loc_140006EAE
0x140006e6c  mov     rdx, rbp; dwBytes
0x140006e6f  mov     ecx, 8; dwFlags
0x140006e74  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006e79  mov     r12, rax
0x140006e7c  test    rax, rax
0x140006e7f  jz      short loc_140006EAB
0x140006e81  mov     rbx, [rsi+rdi+40h]
0x140006e86  call    cs:__imp_GetProcessHeap
0x140006e8c  mov     r8, rbx; lpMem
0x140006e8f  xor     edx, edx; dwFlags
0x140006e91  mov     rcx, rax; hHeap
0x140006e94  call    cs:__imp_HeapFree
0x140006e9a  lea     rbx, [rdi+20h]
0x140006e9e  mov     [rsi+rdi+40h], r12
0x140006ea3  add     rbx, rsi
0x140006ea6  mov     [rsi+rdi+48h], rbp
0x140006eab  xor     r12d, r12d
0x140006eae  mov     rcx, [rsi+rdi+40h]
0x140006eb3  test    rcx, rcx
0x140006eb6  jz      loc_140006F48
0x140006ebc  mov     rbp, [rsi+rdi+48h]
0x140006ec1  lea     r9, [r13+10h]
0x140006ec5  mov     r8, [r15+38h]
0x140006ec9  add     rbp, rcx
0x140006ecc  mov     rdx, rbp
0x140006ecf  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006ed4  mov     r8, [r15+80h]
0x140006edb  mov     r9, rbx
0x140006ede  mov     rdx, rbp
0x140006ee1  mov     rcx, rax
0x140006ee4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006ee9  mov     rbx, rax
0x140006eec  cmp     rax, rbp
0x140006eef  jz      short loc_140006F33
0x140006ef1  mov     r8, [r15+18h]; Source
0x140006ef5  test    r8, r8
0x140006ef8  jz      short loc_140006F33
0x140006efa  cmp     [r8], r12w
0x140006efe  jz      short loc_140006F33
0x140006f00  inc     r14
0x140006f03  cmp     [r8+r14*2], r12w
0x140006f08  jnz     short loc_140006F00
0x140006f0a  mov     rdx, rbp
0x140006f0d  lea     r14, ds:2[r14*2]
0x140006f15  sub     rdx, rbx; DestinationSize
0x140006f18  cmp     rdx, r14
0x140006f1b  jb      short loc_140006F33
0x140006f1d  mov     r9, r14; SourceSize
0x140006f20  mov     rcx, rbx; Destination
0x140006f23  call    cs:__imp_memcpy_s
0x140006f29  mov     [rsi+rdi+38h], rbx
0x140006f2e  add     rbx, r14
0x140006f31  jmp     short loc_140006F38
0x140006f33  mov     [rsi+rdi+38h], r12
0x140006f38  sub     rbp, rbx
0x140006f3b  xor     edx, edx; Val
0x140006f3d  mov     r8, rbp; Size
0x140006f40  mov     rcx, rbx; void *
0x140006f43  call    memset_0
0x140006f48  add     rsp, 28h
0x140006f4c  pop     r15
0x140006f4e  pop     r14
0x140006f50  pop     r13
0x140006f52  pop     r12
0x140006f54  pop     rdi
0x140006f55  pop     rsi
0x140006f56  pop     rbp
0x140006f57  pop     rbx
0x140006f58  retn
```
