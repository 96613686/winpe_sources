# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005188`
- end: `0x1800053a4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003d80`

## callees

- `0x180004dd8`
- `0x180005188`
- `0x18001afe2`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800052d4`
- `msvcrt!memcpy_s` at `0x180005325`
- `msvcrt!memcpy_s` at `0x180005370`
- `msvcrt!memcpy_s` at `0x1800052d4`
- `msvcrt!memcpy_s` at `0x180005325`
- `msvcrt!memcpy_s` at `0x180005370`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000527e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000527e`

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
0x180005188  push    rbx
0x18000518a  push    rbp
0x18000518b  push    rsi
0x18000518c  push    rdi
0x18000518d  push    r12
0x18000518f  push    r13
0x180005191  push    r14
0x180005193  push    r15
0x180005195  sub     rsp, 28h
0x180005199  mov     [rcx+4], r8d
0x18000519d  xor     r13d, r13d
0x1800051a0  mov     eax, [rdx+8]
0x1800051a3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800051a7  mov     [rcx+8], eax
0x1800051aa  mov     rdi, rcx
0x1800051ad  mov     [rcx+10h], r13
0x1800051b1  mov     r12, rdx
0x1800051b4  movzx   eax, word ptr [rdx+40h]
0x1800051b8  mov     [rcx+18h], ax
0x1800051bc  mov     al, [rdx]
0x1800051be  mov     [rcx+1Ah], al
0x1800051c1  mov     [rcx+20h], r13
0x1800051c5  mov     rax, [rdx+88h]
0x1800051cc  mov     [rcx+28h], rax
0x1800051d0  mov     rax, [rdx+90h]
0x1800051d7  mov     [rcx+30h], rax
0x1800051db  mov     [rcx+38h], r13
0x1800051df  mov     rcx, [rdx+38h]
0x1800051e3  lea     edx, [rbp+2]
0x1800051e6  test    rcx, rcx
0x1800051e9  jnz     short loc_1800051F0
0x1800051eb  mov     r8d, edx
0x1800051ee  jmp     short loc_180005200
0x1800051f0  mov     rax, rbp
0x1800051f3  inc     rax
0x1800051f6  cmp     [rcx+rax], r13b
0x1800051fa  jnz     short loc_1800051F3
0x1800051fc  lea     r8, [rax+1]; unsigned __int64
0x180005200  mov     rcx, [r12+80h]
0x180005208  test    rcx, rcx
0x18000520b  jz      short loc_18000521D
0x18000520d  mov     rax, rbp
0x180005210  inc     rax
0x180005213  cmp     [rcx+rax], r13b
0x180005217  jnz     short loc_180005210
0x180005219  lea     rdx, [rax+1]
0x18000521d  mov     rcx, [r12+18h]
0x180005222  test    rcx, rcx
0x180005225  jnz     short loc_18000522C
0x180005227  lea     eax, [rcx+2]
0x18000522a  jmp     short loc_180005241
0x18000522c  mov     rax, rbp
0x18000522f  inc     rax
0x180005232  cmp     [rcx+rax*2], r13w
0x180005237  jnz     short loc_18000522F
0x180005239  lea     rax, ds:2[rax*2]
0x180005241  lea     r14, [rdx+rax]
0x180005245  add     r14, r8
0x180005248  lea     rsi, [rdi+48h]
0x18000524c  cmp     [rdi+40h], r13
0x180005250  jz      short loc_180005257
0x180005252  cmp     [rsi], r14
0x180005255  jnb     short loc_18000528B
0x180005257  mov     rdx, r14; dwBytes
0x18000525a  mov     ecx, 8; dwFlags
0x18000525f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005264  mov     r15, rax
0x180005267  test    rax, rax
0x18000526a  jz      short loc_18000528B
0x18000526c  mov     rbx, [rdi+40h]
0x180005270  call    cs:__imp_GetProcessHeap
0x180005276  mov     r8, rbx; lpMem
0x180005279  xor     edx, edx; dwFlags
0x18000527b  mov     rcx, rax; hHeap
0x18000527e  call    cs:__imp_HeapFree
0x180005284  mov     [rdi+40h], r15
0x180005288  mov     [rsi], r14
0x18000528b  mov     rbx, [rdi+40h]
0x18000528f  test    rbx, rbx
0x180005292  jz      loc_180005393
0x180005298  mov     rdx, [rsi]; DestinationSize
0x18000529b  lea     rsi, [rdx+rbx]
0x18000529f  cmp     rbx, rsi
0x1800052a2  jz      short loc_1800052E3
0x1800052a4  mov     r8, [r12+38h]; Source
0x1800052a9  test    r8, r8
0x1800052ac  jz      short loc_1800052E3
0x1800052ae  cmp     [r8], r13b
0x1800052b1  jz      short loc_1800052E3
0x1800052b3  mov     rax, rbp
0x1800052b6  inc     rax
0x1800052b9  cmp     [r8+rax], r13b
0x1800052bd  jnz     short loc_1800052B6
0x1800052bf  lea     r14, [rax+1]
0x1800052c3  cmp     rdx, r14
0x1800052c6  jnb     short loc_1800052CE
0x1800052c8  mov     [rdi+10h], r13
0x1800052cc  jmp     short loc_1800052EC
0x1800052ce  mov     r9, r14; SourceSize
0x1800052d1  mov     rcx, rbx; Destination
0x1800052d4  call    cs:__imp_memcpy_s
0x1800052da  mov     [rdi+10h], rbx
0x1800052de  add     rbx, r14
0x1800052e1  jmp     short loc_1800052E7
0x1800052e3  mov     [rdi+10h], r13
0x1800052e7  cmp     rbx, rsi
0x1800052ea  jz      short loc_180005334
0x1800052ec  mov     r8, [r12+80h]; Source
0x1800052f4  test    r8, r8
0x1800052f7  jz      short loc_180005334
0x1800052f9  cmp     [r8], r13b
0x1800052fc  jz      short loc_180005334
0x1800052fe  mov     rax, rbp
0x180005301  inc     rax
0x180005304  cmp     [r8+rax], r13b
0x180005308  jnz     short loc_180005301
0x18000530a  mov     rdx, rsi
0x18000530d  lea     r14, [rax+1]
0x180005311  sub     rdx, rbx; DestinationSize
0x180005314  cmp     rdx, r14
0x180005317  jnb     short loc_18000531F
0x180005319  mov     [rdi+20h], r13
0x18000531d  jmp     short loc_18000533D
0x18000531f  mov     r9, r14; SourceSize
0x180005322  mov     rcx, rbx; Destination
0x180005325  call    cs:__imp_memcpy_s
0x18000532b  mov     [rdi+20h], rbx
0x18000532f  add     rbx, r14
0x180005332  jmp     short loc_180005338
0x180005334  mov     [rdi+20h], r13
0x180005338  cmp     rbx, rsi
0x18000533b  jz      short loc_18000537F
0x18000533d  mov     r8, [r12+18h]; Source
0x180005342  test    r8, r8
0x180005345  jz      short loc_18000537F
0x180005347  cmp     [r8], r13w
0x18000534b  jz      short loc_18000537F
0x18000534d  inc     rbp
0x180005350  cmp     [r8+rbp*2], r13w
0x180005355  jnz     short loc_18000534D
0x180005357  mov     rdx, rsi
0x18000535a  lea     r14, ds:2[rbp*2]
0x180005362  sub     rdx, rbx; DestinationSize
0x180005365  cmp     rdx, r14
0x180005368  jb      short loc_18000537F
0x18000536a  mov     r9, r14; SourceSize
0x18000536d  mov     rcx, rbx; Destination
0x180005370  call    cs:__imp_memcpy_s
0x180005376  mov     [rdi+38h], rbx
0x18000537a  add     rbx, r14
0x18000537d  jmp     short loc_180005383
0x18000537f  mov     [rdi+38h], r13
0x180005383  sub     rsi, rbx
0x180005386  xor     edx, edx; Val
0x180005388  mov     r8, rsi; Size
0x18000538b  mov     rcx, rbx; void *
0x18000538e  call    memset_0
0x180005393  add     rsp, 28h
0x180005397  pop     r15
0x180005399  pop     r14
0x18000539b  pop     r13
0x18000539d  pop     r12
0x18000539f  pop     rdi
0x1800053a0  pop     rsi
0x1800053a1  pop     rbp
0x1800053a2  pop     rbx
0x1800053a3  retn
```
