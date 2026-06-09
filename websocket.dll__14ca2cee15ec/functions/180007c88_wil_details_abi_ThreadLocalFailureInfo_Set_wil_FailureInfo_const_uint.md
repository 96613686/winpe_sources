# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007c88`
- end: `0x180007ea1`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005100`

## callees

- `0x180001f8c`
- `0x180001fa4`
- `0x180006678`
- `0x180007c88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d70`

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
0x180007c88  push    rbx
0x180007c8a  push    rbp
0x180007c8b  push    rsi
0x180007c8c  push    rdi
0x180007c8d  push    r12
0x180007c8f  push    r13
0x180007c91  push    r14
0x180007c93  push    r15
0x180007c95  sub     rsp, 28h
0x180007c99  mov     [rcx+4], r8d
0x180007c9d  xor     r13d, r13d
0x180007ca0  mov     eax, [rdx+8]
0x180007ca3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007ca7  mov     [rcx+8], eax
0x180007caa  mov     rdi, rcx
0x180007cad  mov     [rcx+10h], r13
0x180007cb1  mov     r12, rdx
0x180007cb4  movzx   eax, word ptr [rdx+40h]
0x180007cb8  mov     [rcx+18h], ax
0x180007cbc  mov     al, [rdx]
0x180007cbe  mov     [rcx+1Ah], al
0x180007cc1  mov     [rcx+20h], r13
0x180007cc5  mov     rax, [rdx+88h]
0x180007ccc  mov     [rcx+28h], rax
0x180007cd0  mov     rax, [rdx+90h]
0x180007cd7  mov     [rcx+30h], rax
0x180007cdb  mov     [rcx+38h], r13
0x180007cdf  mov     rcx, [rdx+38h]
0x180007ce3  lea     edx, [rbp+2]
0x180007ce6  test    rcx, rcx
0x180007ce9  jnz     short loc_180007CF0
0x180007ceb  mov     r8d, edx
0x180007cee  jmp     short loc_180007D00
0x180007cf0  mov     rax, rbp
0x180007cf3  inc     rax
0x180007cf6  cmp     [rcx+rax], r13b
0x180007cfa  jnz     short loc_180007CF3
0x180007cfc  lea     r8, [rax+1]; unsigned __int64
0x180007d00  mov     rcx, [r12+80h]
0x180007d08  test    rcx, rcx
0x180007d0b  jz      short loc_180007D1D
0x180007d0d  mov     rax, rbp
0x180007d10  inc     rax
0x180007d13  cmp     [rcx+rax], r13b
0x180007d17  jnz     short loc_180007D10
0x180007d19  lea     rdx, [rax+1]
0x180007d1d  mov     rcx, [r12+18h]
0x180007d22  test    rcx, rcx
0x180007d25  jnz     short loc_180007D2C
0x180007d27  lea     eax, [rcx+2]
0x180007d2a  jmp     short loc_180007D41
0x180007d2c  mov     rax, rbp
0x180007d2f  inc     rax
0x180007d32  cmp     [rcx+rax*2], r13w
0x180007d37  jnz     short loc_180007D2F
0x180007d39  lea     rax, ds:2[rax*2]
0x180007d41  lea     r14, [rdx+rax]
0x180007d45  add     r14, r8
0x180007d48  lea     rsi, [rdi+48h]
0x180007d4c  cmp     [rdi+40h], r13
0x180007d50  jz      short loc_180007D57
0x180007d52  cmp     [rsi], r14
0x180007d55  jnb     short loc_180007D8B
0x180007d57  mov     rdx, r14; dwBytes
0x180007d5a  mov     ecx, 8; dwFlags
0x180007d5f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007d64  mov     r15, rax
0x180007d67  test    rax, rax
0x180007d6a  jz      short loc_180007D8B
0x180007d6c  mov     rbx, [rdi+40h]
0x180007d70  call    cs:__imp_GetProcessHeap
0x180007d76  mov     r8, rbx; lpMem
0x180007d79  xor     edx, edx; dwFlags
0x180007d7b  mov     rcx, rax; hHeap
0x180007d7e  call    cs:__imp_HeapFree
0x180007d84  mov     [rdi+40h], r15
0x180007d88  mov     [rsi], r14
0x180007d8b  mov     rbx, [rdi+40h]
0x180007d8f  test    rbx, rbx
0x180007d92  jz      loc_180007E90
0x180007d98  mov     rdx, [rsi]; DestinationSize
0x180007d9b  lea     rsi, [rdx+rbx]
0x180007d9f  cmp     rbx, rsi
0x180007da2  jz      short loc_180007DE2
0x180007da4  mov     r8, [r12+38h]; Source
0x180007da9  test    r8, r8
0x180007dac  jz      short loc_180007DE2
0x180007dae  cmp     [r8], r13b
0x180007db1  jz      short loc_180007DE2
0x180007db3  mov     rax, rbp
0x180007db6  inc     rax
0x180007db9  cmp     [r8+rax], r13b
0x180007dbd  jnz     short loc_180007DB6
0x180007dbf  lea     r14, [rax+1]
0x180007dc3  cmp     rdx, r14
0x180007dc6  jnb     short loc_180007DCE
0x180007dc8  mov     [rdi+10h], r13
0x180007dcc  jmp     short loc_180007DEB
0x180007dce  mov     r9, r14; SourceSize
0x180007dd1  mov     rcx, rbx; Destination
0x180007dd4  call    memcpy_s
0x180007dd9  mov     [rdi+10h], rbx
0x180007ddd  add     rbx, r14
0x180007de0  jmp     short loc_180007DE6
0x180007de2  mov     [rdi+10h], r13
0x180007de6  cmp     rbx, rsi
0x180007de9  jz      short loc_180007E32
0x180007deb  mov     r8, [r12+80h]; Source
0x180007df3  test    r8, r8
0x180007df6  jz      short loc_180007E32
0x180007df8  cmp     [r8], r13b
0x180007dfb  jz      short loc_180007E32
0x180007dfd  mov     rax, rbp
0x180007e00  inc     rax
0x180007e03  cmp     [r8+rax], r13b
0x180007e07  jnz     short loc_180007E00
0x180007e09  mov     rdx, rsi
0x180007e0c  lea     r14, [rax+1]
0x180007e10  sub     rdx, rbx; DestinationSize
0x180007e13  cmp     rdx, r14
0x180007e16  jnb     short loc_180007E1E
0x180007e18  mov     [rdi+20h], r13
0x180007e1c  jmp     short loc_180007E3B
0x180007e1e  mov     r9, r14; SourceSize
0x180007e21  mov     rcx, rbx; Destination
0x180007e24  call    memcpy_s
0x180007e29  mov     [rdi+20h], rbx
0x180007e2d  add     rbx, r14
0x180007e30  jmp     short loc_180007E36
0x180007e32  mov     [rdi+20h], r13
0x180007e36  cmp     rbx, rsi
0x180007e39  jz      short loc_180007E7C
0x180007e3b  mov     r8, [r12+18h]; Source
0x180007e40  test    r8, r8
0x180007e43  jz      short loc_180007E7C
0x180007e45  cmp     [r8], r13w
0x180007e49  jz      short loc_180007E7C
0x180007e4b  inc     rbp
0x180007e4e  cmp     [r8+rbp*2], r13w
0x180007e53  jnz     short loc_180007E4B
0x180007e55  mov     rdx, rsi
0x180007e58  lea     r14, ds:2[rbp*2]
0x180007e60  sub     rdx, rbx; DestinationSize
0x180007e63  cmp     rdx, r14
0x180007e66  jb      short loc_180007E7C
0x180007e68  mov     r9, r14; SourceSize
0x180007e6b  mov     rcx, rbx; Destination
0x180007e6e  call    memcpy_s
0x180007e73  mov     [rdi+38h], rbx
0x180007e77  add     rbx, r14
0x180007e7a  jmp     short loc_180007E80
0x180007e7c  mov     [rdi+38h], r13
0x180007e80  sub     rsi, rbx
0x180007e83  xor     edx, edx; Val
0x180007e85  mov     r8, rsi; Size
0x180007e88  mov     rcx, rbx; void *
0x180007e8b  call    memset_0
0x180007e90  add     rsp, 28h
0x180007e94  pop     r15
0x180007e96  pop     r14
0x180007e98  pop     r13
0x180007e9a  pop     r12
0x180007e9c  pop     rdi
0x180007e9d  pop     rsi
0x180007e9e  pop     rbp
0x180007e9f  pop     rbx
0x180007ea0  retn
```
