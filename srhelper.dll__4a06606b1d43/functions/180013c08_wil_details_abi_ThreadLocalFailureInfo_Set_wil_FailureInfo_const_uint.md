# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180013c08`
- end: `0x180013e24`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011710`

## callees

- `0x180012878`
- `0x180013c08`
- `0x1800157be`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013d54`
- `msvcrt!memcpy_s` at `0x180013da5`
- `msvcrt!memcpy_s` at `0x180013df0`
- `msvcrt!memcpy_s` at `0x180013d54`
- `msvcrt!memcpy_s` at `0x180013da5`
- `msvcrt!memcpy_s` at `0x180013df0`
- `KERNEL32!HeapFree` at `0x180013cfe`
- `KERNEL32!HeapFree` at `0x180013cfe`
- `KERNEL32!GetProcessHeap` at `0x180013cf0`
- `KERNEL32!GetProcessHeap` at `0x180013cf0`

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
0x180013c08  push    rbx
0x180013c0a  push    rbp
0x180013c0b  push    rsi
0x180013c0c  push    rdi
0x180013c0d  push    r12
0x180013c0f  push    r13
0x180013c11  push    r14
0x180013c13  push    r15
0x180013c15  sub     rsp, 28h
0x180013c19  mov     [rcx+4], r8d
0x180013c1d  xor     r13d, r13d
0x180013c20  mov     eax, [rdx+8]
0x180013c23  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180013c27  mov     [rcx+8], eax
0x180013c2a  mov     rdi, rcx
0x180013c2d  mov     [rcx+10h], r13
0x180013c31  mov     r12, rdx
0x180013c34  movzx   eax, word ptr [rdx+40h]
0x180013c38  mov     [rcx+18h], ax
0x180013c3c  mov     al, [rdx]
0x180013c3e  mov     [rcx+1Ah], al
0x180013c41  mov     [rcx+20h], r13
0x180013c45  mov     rax, [rdx+88h]
0x180013c4c  mov     [rcx+28h], rax
0x180013c50  mov     rax, [rdx+90h]
0x180013c57  mov     [rcx+30h], rax
0x180013c5b  mov     [rcx+38h], r13
0x180013c5f  mov     rcx, [rdx+38h]
0x180013c63  lea     edx, [rbp+2]
0x180013c66  test    rcx, rcx
0x180013c69  jnz     short loc_180013C70
0x180013c6b  mov     r8d, edx
0x180013c6e  jmp     short loc_180013C80
0x180013c70  mov     rax, rbp
0x180013c73  inc     rax
0x180013c76  cmp     [rcx+rax], r13b
0x180013c7a  jnz     short loc_180013C73
0x180013c7c  lea     r8, [rax+1]; unsigned __int64
0x180013c80  mov     rcx, [r12+80h]
0x180013c88  test    rcx, rcx
0x180013c8b  jz      short loc_180013C9D
0x180013c8d  mov     rax, rbp
0x180013c90  inc     rax
0x180013c93  cmp     [rcx+rax], r13b
0x180013c97  jnz     short loc_180013C90
0x180013c99  lea     rdx, [rax+1]
0x180013c9d  mov     rcx, [r12+18h]
0x180013ca2  test    rcx, rcx
0x180013ca5  jnz     short loc_180013CAC
0x180013ca7  lea     eax, [rcx+2]
0x180013caa  jmp     short loc_180013CC1
0x180013cac  mov     rax, rbp
0x180013caf  inc     rax
0x180013cb2  cmp     [rcx+rax*2], r13w
0x180013cb7  jnz     short loc_180013CAF
0x180013cb9  lea     rax, ds:2[rax*2]
0x180013cc1  lea     r14, [rdx+rax]
0x180013cc5  add     r14, r8
0x180013cc8  lea     rsi, [rdi+48h]
0x180013ccc  cmp     [rdi+40h], r13
0x180013cd0  jz      short loc_180013CD7
0x180013cd2  cmp     [rsi], r14
0x180013cd5  jnb     short loc_180013D0B
0x180013cd7  mov     rdx, r14; dwBytes
0x180013cda  mov     ecx, 8; dwFlags
0x180013cdf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013ce4  mov     r15, rax
0x180013ce7  test    rax, rax
0x180013cea  jz      short loc_180013D0B
0x180013cec  mov     rbx, [rdi+40h]
0x180013cf0  call    cs:__imp_GetProcessHeap
0x180013cf6  mov     r8, rbx; lpMem
0x180013cf9  xor     edx, edx; dwFlags
0x180013cfb  mov     rcx, rax; hHeap
0x180013cfe  call    cs:__imp_HeapFree
0x180013d04  mov     [rdi+40h], r15
0x180013d08  mov     [rsi], r14
0x180013d0b  mov     rbx, [rdi+40h]
0x180013d0f  test    rbx, rbx
0x180013d12  jz      loc_180013E13
0x180013d18  mov     rdx, [rsi]; DestinationSize
0x180013d1b  lea     rsi, [rdx+rbx]
0x180013d1f  cmp     rbx, rsi
0x180013d22  jz      short loc_180013D63
0x180013d24  mov     r8, [r12+38h]; Source
0x180013d29  test    r8, r8
0x180013d2c  jz      short loc_180013D63
0x180013d2e  cmp     [r8], r13b
0x180013d31  jz      short loc_180013D63
0x180013d33  mov     rax, rbp
0x180013d36  inc     rax
0x180013d39  cmp     [r8+rax], r13b
0x180013d3d  jnz     short loc_180013D36
0x180013d3f  lea     r14, [rax+1]
0x180013d43  cmp     rdx, r14
0x180013d46  jnb     short loc_180013D4E
0x180013d48  mov     [rdi+10h], r13
0x180013d4c  jmp     short loc_180013D6C
0x180013d4e  mov     r9, r14; SourceSize
0x180013d51  mov     rcx, rbx; Destination
0x180013d54  call    cs:__imp_memcpy_s
0x180013d5a  mov     [rdi+10h], rbx
0x180013d5e  add     rbx, r14
0x180013d61  jmp     short loc_180013D67
0x180013d63  mov     [rdi+10h], r13
0x180013d67  cmp     rbx, rsi
0x180013d6a  jz      short loc_180013DB4
0x180013d6c  mov     r8, [r12+80h]; Source
0x180013d74  test    r8, r8
0x180013d77  jz      short loc_180013DB4
0x180013d79  cmp     [r8], r13b
0x180013d7c  jz      short loc_180013DB4
0x180013d7e  mov     rax, rbp
0x180013d81  inc     rax
0x180013d84  cmp     [r8+rax], r13b
0x180013d88  jnz     short loc_180013D81
0x180013d8a  mov     rdx, rsi
0x180013d8d  lea     r14, [rax+1]
0x180013d91  sub     rdx, rbx; DestinationSize
0x180013d94  cmp     rdx, r14
0x180013d97  jnb     short loc_180013D9F
0x180013d99  mov     [rdi+20h], r13
0x180013d9d  jmp     short loc_180013DBD
0x180013d9f  mov     r9, r14; SourceSize
0x180013da2  mov     rcx, rbx; Destination
0x180013da5  call    cs:__imp_memcpy_s
0x180013dab  mov     [rdi+20h], rbx
0x180013daf  add     rbx, r14
0x180013db2  jmp     short loc_180013DB8
0x180013db4  mov     [rdi+20h], r13
0x180013db8  cmp     rbx, rsi
0x180013dbb  jz      short loc_180013DFF
0x180013dbd  mov     r8, [r12+18h]; Source
0x180013dc2  test    r8, r8
0x180013dc5  jz      short loc_180013DFF
0x180013dc7  cmp     [r8], r13w
0x180013dcb  jz      short loc_180013DFF
0x180013dcd  inc     rbp
0x180013dd0  cmp     [r8+rbp*2], r13w
0x180013dd5  jnz     short loc_180013DCD
0x180013dd7  mov     rdx, rsi
0x180013dda  lea     r14, ds:2[rbp*2]
0x180013de2  sub     rdx, rbx; DestinationSize
0x180013de5  cmp     rdx, r14
0x180013de8  jb      short loc_180013DFF
0x180013dea  mov     r9, r14; SourceSize
0x180013ded  mov     rcx, rbx; Destination
0x180013df0  call    cs:__imp_memcpy_s
0x180013df6  mov     [rdi+38h], rbx
0x180013dfa  add     rbx, r14
0x180013dfd  jmp     short loc_180013E03
0x180013dff  mov     [rdi+38h], r13
0x180013e03  sub     rsi, rbx
0x180013e06  xor     edx, edx; Val
0x180013e08  mov     r8, rsi; Size
0x180013e0b  mov     rcx, rbx; void *
0x180013e0e  call    memset_0
0x180013e13  add     rsp, 28h
0x180013e17  pop     r15
0x180013e19  pop     r14
0x180013e1b  pop     r13
0x180013e1d  pop     r12
0x180013e1f  pop     rdi
0x180013e20  pop     rsi
0x180013e21  pop     rbp
0x180013e22  pop     rbx
0x180013e23  retn
```
