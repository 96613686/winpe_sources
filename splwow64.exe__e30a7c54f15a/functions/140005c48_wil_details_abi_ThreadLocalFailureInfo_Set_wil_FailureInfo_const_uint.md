# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140005c48`
- end: `0x140005e61`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140004120`

## callees

- `0x1400028b8`
- `0x14000542c`
- `0x140005c48`
- `0x140006388`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005d3e`
- `KERNEL32!HeapFree` at `0x140005d3e`
- `KERNEL32!GetProcessHeap` at `0x140005d30`
- `KERNEL32!GetProcessHeap` at `0x140005d30`

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
0x140005c48  push    rbx
0x140005c4a  push    rbp
0x140005c4b  push    rsi
0x140005c4c  push    rdi
0x140005c4d  push    r12
0x140005c4f  push    r13
0x140005c51  push    r14
0x140005c53  push    r15
0x140005c55  sub     rsp, 28h
0x140005c59  mov     [rcx+4], r8d
0x140005c5d  xor     r13d, r13d
0x140005c60  mov     eax, [rdx+8]
0x140005c63  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140005c67  mov     [rcx+8], eax
0x140005c6a  mov     rdi, rcx
0x140005c6d  mov     [rcx+10h], r13
0x140005c71  mov     r12, rdx
0x140005c74  movzx   eax, word ptr [rdx+40h]
0x140005c78  mov     [rcx+18h], ax
0x140005c7c  mov     al, [rdx]
0x140005c7e  mov     [rcx+1Ah], al
0x140005c81  mov     [rcx+20h], r13
0x140005c85  mov     rax, [rdx+88h]
0x140005c8c  mov     [rcx+28h], rax
0x140005c90  mov     rax, [rdx+90h]
0x140005c97  mov     [rcx+30h], rax
0x140005c9b  mov     [rcx+38h], r13
0x140005c9f  mov     rcx, [rdx+38h]
0x140005ca3  lea     edx, [rbp+2]
0x140005ca6  test    rcx, rcx
0x140005ca9  jnz     short loc_140005CB0
0x140005cab  mov     r8d, edx
0x140005cae  jmp     short loc_140005CC0
0x140005cb0  mov     rax, rbp
0x140005cb3  inc     rax
0x140005cb6  cmp     [rcx+rax], r13b
0x140005cba  jnz     short loc_140005CB3
0x140005cbc  lea     r8, [rax+1]; unsigned __int64
0x140005cc0  mov     rcx, [r12+80h]
0x140005cc8  test    rcx, rcx
0x140005ccb  jz      short loc_140005CDD
0x140005ccd  mov     rax, rbp
0x140005cd0  inc     rax
0x140005cd3  cmp     [rcx+rax], r13b
0x140005cd7  jnz     short loc_140005CD0
0x140005cd9  lea     rdx, [rax+1]
0x140005cdd  mov     rcx, [r12+18h]
0x140005ce2  test    rcx, rcx
0x140005ce5  jnz     short loc_140005CEC
0x140005ce7  lea     eax, [rcx+2]
0x140005cea  jmp     short loc_140005D01
0x140005cec  mov     rax, rbp
0x140005cef  inc     rax
0x140005cf2  cmp     [rcx+rax*2], r13w
0x140005cf7  jnz     short loc_140005CEF
0x140005cf9  lea     rax, ds:2[rax*2]
0x140005d01  lea     r14, [rdx+rax]
0x140005d05  add     r14, r8
0x140005d08  lea     rsi, [rdi+48h]
0x140005d0c  cmp     [rdi+40h], r13
0x140005d10  jz      short loc_140005D17
0x140005d12  cmp     [rsi], r14
0x140005d15  jnb     short loc_140005D4B
0x140005d17  mov     rdx, r14; dwBytes
0x140005d1a  mov     ecx, 8; dwFlags
0x140005d1f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005d24  mov     r15, rax
0x140005d27  test    rax, rax
0x140005d2a  jz      short loc_140005D4B
0x140005d2c  mov     rbx, [rdi+40h]
0x140005d30  call    cs:__imp_GetProcessHeap
0x140005d36  mov     r8, rbx; lpMem
0x140005d39  xor     edx, edx; dwFlags
0x140005d3b  mov     rcx, rax; hHeap
0x140005d3e  call    cs:__imp_HeapFree
0x140005d44  mov     [rdi+40h], r15
0x140005d48  mov     [rsi], r14
0x140005d4b  mov     rbx, [rdi+40h]
0x140005d4f  test    rbx, rbx
0x140005d52  jz      loc_140005E50
0x140005d58  mov     rdx, [rsi]; DestinationSize
0x140005d5b  lea     rsi, [rdx+rbx]
0x140005d5f  cmp     rbx, rsi
0x140005d62  jz      short loc_140005DA2
0x140005d64  mov     r8, [r12+38h]; Source
0x140005d69  test    r8, r8
0x140005d6c  jz      short loc_140005DA2
0x140005d6e  cmp     [r8], r13b
0x140005d71  jz      short loc_140005DA2
0x140005d73  mov     rax, rbp
0x140005d76  inc     rax
0x140005d79  cmp     [r8+rax], r13b
0x140005d7d  jnz     short loc_140005D76
0x140005d7f  lea     r14, [rax+1]
0x140005d83  cmp     rdx, r14
0x140005d86  jnb     short loc_140005D8E
0x140005d88  mov     [rdi+10h], r13
0x140005d8c  jmp     short loc_140005DAB
0x140005d8e  mov     r9, r14; SourceSize
0x140005d91  mov     rcx, rbx; Destination
0x140005d94  call    memcpy_s
0x140005d99  mov     [rdi+10h], rbx
0x140005d9d  add     rbx, r14
0x140005da0  jmp     short loc_140005DA6
0x140005da2  mov     [rdi+10h], r13
0x140005da6  cmp     rbx, rsi
0x140005da9  jz      short loc_140005DF2
0x140005dab  mov     r8, [r12+80h]; Source
0x140005db3  test    r8, r8
0x140005db6  jz      short loc_140005DF2
0x140005db8  cmp     [r8], r13b
0x140005dbb  jz      short loc_140005DF2
0x140005dbd  mov     rax, rbp
0x140005dc0  inc     rax
0x140005dc3  cmp     [r8+rax], r13b
0x140005dc7  jnz     short loc_140005DC0
0x140005dc9  mov     rdx, rsi
0x140005dcc  lea     r14, [rax+1]
0x140005dd0  sub     rdx, rbx; DestinationSize
0x140005dd3  cmp     rdx, r14
0x140005dd6  jnb     short loc_140005DDE
0x140005dd8  mov     [rdi+20h], r13
0x140005ddc  jmp     short loc_140005DFB
0x140005dde  mov     r9, r14; SourceSize
0x140005de1  mov     rcx, rbx; Destination
0x140005de4  call    memcpy_s
0x140005de9  mov     [rdi+20h], rbx
0x140005ded  add     rbx, r14
0x140005df0  jmp     short loc_140005DF6
0x140005df2  mov     [rdi+20h], r13
0x140005df6  cmp     rbx, rsi
0x140005df9  jz      short loc_140005E3C
0x140005dfb  mov     r8, [r12+18h]; Source
0x140005e00  test    r8, r8
0x140005e03  jz      short loc_140005E3C
0x140005e05  cmp     [r8], r13w
0x140005e09  jz      short loc_140005E3C
0x140005e0b  inc     rbp
0x140005e0e  cmp     [r8+rbp*2], r13w
0x140005e13  jnz     short loc_140005E0B
0x140005e15  mov     rdx, rsi
0x140005e18  lea     r14, ds:2[rbp*2]
0x140005e20  sub     rdx, rbx; DestinationSize
0x140005e23  cmp     rdx, r14
0x140005e26  jb      short loc_140005E3C
0x140005e28  mov     r9, r14; SourceSize
0x140005e2b  mov     rcx, rbx; Destination
0x140005e2e  call    memcpy_s
0x140005e33  mov     [rdi+38h], rbx
0x140005e37  add     rbx, r14
0x140005e3a  jmp     short loc_140005E40
0x140005e3c  mov     [rdi+38h], r13
0x140005e40  sub     rsi, rbx
0x140005e43  xor     edx, edx; Val
0x140005e45  mov     r8, rsi; Size
0x140005e48  mov     rcx, rbx; void *
0x140005e4b  call    memset_0
0x140005e50  add     rsp, 28h
0x140005e54  pop     r15
0x140005e56  pop     r14
0x140005e58  pop     r13
0x140005e5a  pop     r12
0x140005e5c  pop     rdi
0x140005e5d  pop     rsi
0x140005e5e  pop     rbp
0x140005e5f  pop     rbx
0x140005e60  retn
```
