# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000d9a4`
- end: `0x18000dbc0`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b0a0`

## callees

- `0x18000c354`
- `0x18000d9a4`
- `0x18001218a`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000daf0`
- `msvcrt!memcpy_s` at `0x18000db41`
- `msvcrt!memcpy_s` at `0x18000db8c`
- `msvcrt!memcpy_s` at `0x18000daf0`
- `msvcrt!memcpy_s` at `0x18000db41`
- `msvcrt!memcpy_s` at `0x18000db8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000da9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000da8c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v3; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r14
  rsize_t *v16; // rsi
  LPVOID v17; // r15
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char *v22; // rsi
  _BYTE *v23; // r8
  __int64 v24; // rax
  __int64 v25; // r14
  _BYTE *v26; // r8
  __int64 v27; // rax
  __int64 v28; // r14
  _WORD *v29; // r8
  unsigned __int64 v30; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = -1;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v7 + v13;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v7 + v13);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = &v20[*v16];
    if ( v20 != v22 && (v23 = (_BYTE *)*((_QWORD *)a2 + 7)) != 0 && *v23 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v23[v24] );
      v25 = v24 + 1;
      if ( v21 < v24 + 1 )
      {
        *((_QWORD *)this + 2) = 0;
LABEL_30:
        v26 = (_BYTE *)*((_QWORD *)a2 + 16);
        if ( v26 && *v26 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v26[v27] );
          v28 = v27 + 1;
          if ( v22 - v20 < (unsigned __int64)(v27 + 1) )
          {
            *((_QWORD *)this + 4) = 0;
LABEL_39:
            v29 = (_WORD *)*((_QWORD *)a2 + 3);
            if ( v29 && *v29 )
            {
              do
                ++v3;
              while ( v29[v3] );
              v30 = 2 * v3 + 2;
              if ( v22 - v20 >= v30 )
              {
                memcpy_s(v20, v22 - v20, v29, 2 * v3 + 2);
                *((_QWORD *)this + 7) = v20;
                v20 += v30;
LABEL_45:
                memset_0(v20, 0, v22 - v20);
                return;
              }
            }
LABEL_44:
            *((_QWORD *)this + 7) = 0;
            goto LABEL_45;
          }
          memcpy_s(v20, v22 - v20, v26, v27 + 1);
          *((_QWORD *)this + 4) = v20;
          v20 += v28;
LABEL_38:
          if ( v20 == v22 )
            goto LABEL_44;
          goto LABEL_39;
        }
LABEL_37:
        *((_QWORD *)this + 4) = 0;
        goto LABEL_38;
      }
      memcpy_s(*((void *const *)this + 8), v21, v23, v24 + 1);
      *((_QWORD *)this + 2) = v20;
      v20 += v25;
    }
    else
    {
      *((_QWORD *)this + 2) = 0;
    }
    if ( v20 == v22 )
      goto LABEL_37;
    goto LABEL_30;
  }
}

```

## disassembly

```asm
0x18000d9a4  push    rbx
0x18000d9a6  push    rbp
0x18000d9a7  push    rsi
0x18000d9a8  push    rdi
0x18000d9a9  push    r12
0x18000d9ab  push    r13
0x18000d9ad  push    r14
0x18000d9af  push    r15
0x18000d9b1  sub     rsp, 28h
0x18000d9b5  mov     [rcx+4], r8d
0x18000d9b9  xor     r13d, r13d
0x18000d9bc  mov     eax, [rdx+8]
0x18000d9bf  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000d9c3  mov     [rcx+8], eax
0x18000d9c6  mov     rdi, rcx
0x18000d9c9  mov     [rcx+10h], r13
0x18000d9cd  mov     r12, rdx
0x18000d9d0  movzx   eax, word ptr [rdx+40h]
0x18000d9d4  mov     [rcx+18h], ax
0x18000d9d8  mov     al, [rdx]
0x18000d9da  mov     [rcx+1Ah], al
0x18000d9dd  mov     [rcx+20h], r13
0x18000d9e1  mov     rax, [rdx+88h]
0x18000d9e8  mov     [rcx+28h], rax
0x18000d9ec  mov     rax, [rdx+90h]
0x18000d9f3  mov     [rcx+30h], rax
0x18000d9f7  mov     [rcx+38h], r13
0x18000d9fb  mov     rcx, [rdx+38h]
0x18000d9ff  lea     edx, [rbp+2]
0x18000da02  test    rcx, rcx
0x18000da05  jnz     short loc_18000DA0C
0x18000da07  mov     r8d, edx
0x18000da0a  jmp     short loc_18000DA1C
0x18000da0c  mov     rax, rbp
0x18000da0f  inc     rax
0x18000da12  cmp     [rcx+rax], r13b
0x18000da16  jnz     short loc_18000DA0F
0x18000da18  lea     r8, [rax+1]; unsigned __int64
0x18000da1c  mov     rcx, [r12+80h]
0x18000da24  test    rcx, rcx
0x18000da27  jz      short loc_18000DA39
0x18000da29  mov     rax, rbp
0x18000da2c  inc     rax
0x18000da2f  cmp     [rcx+rax], r13b
0x18000da33  jnz     short loc_18000DA2C
0x18000da35  lea     rdx, [rax+1]
0x18000da39  mov     rcx, [r12+18h]
0x18000da3e  test    rcx, rcx
0x18000da41  jnz     short loc_18000DA48
0x18000da43  lea     eax, [rcx+2]
0x18000da46  jmp     short loc_18000DA5D
0x18000da48  mov     rax, rbp
0x18000da4b  inc     rax
0x18000da4e  cmp     [rcx+rax*2], r13w
0x18000da53  jnz     short loc_18000DA4B
0x18000da55  lea     rax, ds:2[rax*2]
0x18000da5d  lea     r14, [rdx+rax]
0x18000da61  add     r14, r8
0x18000da64  lea     rsi, [rdi+48h]
0x18000da68  cmp     [rdi+40h], r13
0x18000da6c  jz      short loc_18000DA73
0x18000da6e  cmp     [rsi], r14
0x18000da71  jnb     short loc_18000DAA7
0x18000da73  mov     rdx, r14; dwBytes
0x18000da76  mov     ecx, 8; dwFlags
0x18000da7b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000da80  mov     r15, rax
0x18000da83  test    rax, rax
0x18000da86  jz      short loc_18000DAA7
0x18000da88  mov     rbx, [rdi+40h]
0x18000da8c  call    cs:__imp_GetProcessHeap
0x18000da92  mov     r8, rbx; lpMem
0x18000da95  xor     edx, edx; dwFlags
0x18000da97  mov     rcx, rax; hHeap
0x18000da9a  call    cs:__imp_HeapFree
0x18000daa0  mov     [rdi+40h], r15
0x18000daa4  mov     [rsi], r14
0x18000daa7  mov     rbx, [rdi+40h]
0x18000daab  test    rbx, rbx
0x18000daae  jz      loc_18000DBAF
0x18000dab4  mov     rdx, [rsi]; DestinationSize
0x18000dab7  lea     rsi, [rdx+rbx]
0x18000dabb  cmp     rbx, rsi
0x18000dabe  jz      short loc_18000DAFF
0x18000dac0  mov     r8, [r12+38h]; Source
0x18000dac5  test    r8, r8
0x18000dac8  jz      short loc_18000DAFF
0x18000daca  cmp     [r8], r13b
0x18000dacd  jz      short loc_18000DAFF
0x18000dacf  mov     rax, rbp
0x18000dad2  inc     rax
0x18000dad5  cmp     [r8+rax], r13b
0x18000dad9  jnz     short loc_18000DAD2
0x18000dadb  lea     r14, [rax+1]
0x18000dadf  cmp     rdx, r14
0x18000dae2  jnb     short loc_18000DAEA
0x18000dae4  mov     [rdi+10h], r13
0x18000dae8  jmp     short loc_18000DB08
0x18000daea  mov     r9, r14; SourceSize
0x18000daed  mov     rcx, rbx; Destination
0x18000daf0  call    cs:__imp_memcpy_s
0x18000daf6  mov     [rdi+10h], rbx
0x18000dafa  add     rbx, r14
0x18000dafd  jmp     short loc_18000DB03
0x18000daff  mov     [rdi+10h], r13
0x18000db03  cmp     rbx, rsi
0x18000db06  jz      short loc_18000DB50
0x18000db08  mov     r8, [r12+80h]; Source
0x18000db10  test    r8, r8
0x18000db13  jz      short loc_18000DB50
0x18000db15  cmp     [r8], r13b
0x18000db18  jz      short loc_18000DB50
0x18000db1a  mov     rax, rbp
0x18000db1d  inc     rax
0x18000db20  cmp     [r8+rax], r13b
0x18000db24  jnz     short loc_18000DB1D
0x18000db26  mov     rdx, rsi
0x18000db29  lea     r14, [rax+1]
0x18000db2d  sub     rdx, rbx; DestinationSize
0x18000db30  cmp     rdx, r14
0x18000db33  jnb     short loc_18000DB3B
0x18000db35  mov     [rdi+20h], r13
0x18000db39  jmp     short loc_18000DB59
0x18000db3b  mov     r9, r14; SourceSize
0x18000db3e  mov     rcx, rbx; Destination
0x18000db41  call    cs:__imp_memcpy_s
0x18000db47  mov     [rdi+20h], rbx
0x18000db4b  add     rbx, r14
0x18000db4e  jmp     short loc_18000DB54
0x18000db50  mov     [rdi+20h], r13
0x18000db54  cmp     rbx, rsi
0x18000db57  jz      short loc_18000DB9B
0x18000db59  mov     r8, [r12+18h]; Source
0x18000db5e  test    r8, r8
0x18000db61  jz      short loc_18000DB9B
0x18000db63  cmp     [r8], r13w
0x18000db67  jz      short loc_18000DB9B
0x18000db69  inc     rbp
0x18000db6c  cmp     [r8+rbp*2], r13w
0x18000db71  jnz     short loc_18000DB69
0x18000db73  mov     rdx, rsi
0x18000db76  lea     r14, ds:2[rbp*2]
0x18000db7e  sub     rdx, rbx; DestinationSize
0x18000db81  cmp     rdx, r14
0x18000db84  jb      short loc_18000DB9B
0x18000db86  mov     r9, r14; SourceSize
0x18000db89  mov     rcx, rbx; Destination
0x18000db8c  call    cs:__imp_memcpy_s
0x18000db92  mov     [rdi+38h], rbx
0x18000db96  add     rbx, r14
0x18000db99  jmp     short loc_18000DB9F
0x18000db9b  mov     [rdi+38h], r13
0x18000db9f  sub     rsi, rbx
0x18000dba2  xor     edx, edx; Val
0x18000dba4  mov     r8, rsi; Size
0x18000dba7  mov     rcx, rbx; void *
0x18000dbaa  call    memset_0
0x18000dbaf  add     rsp, 28h
0x18000dbb3  pop     r15
0x18000dbb5  pop     r14
0x18000dbb7  pop     r13
0x18000dbb9  pop     r12
0x18000dbbb  pop     rdi
0x18000dbbc  pop     rsi
0x18000dbbd  pop     rbp
0x18000dbbe  pop     rbx
0x18000dbbf  retn
```
