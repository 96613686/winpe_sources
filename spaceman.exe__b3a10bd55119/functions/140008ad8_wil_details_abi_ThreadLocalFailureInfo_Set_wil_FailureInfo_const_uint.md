# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140008ad8`
- end: `0x140008cf4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `540`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400065e0`

## callees

- `0x140007748`
- `0x140008ad8`
- `0x14000d1be`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008c24`
- `msvcrt!memcpy_s` at `0x140008c75`
- `msvcrt!memcpy_s` at `0x140008cc0`
- `msvcrt!memcpy_s` at `0x140008c24`
- `msvcrt!memcpy_s` at `0x140008c75`
- `msvcrt!memcpy_s` at `0x140008cc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008bce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008bce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008bc0`

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
0x140008ad8  push    rbx
0x140008ada  push    rbp
0x140008adb  push    rsi
0x140008adc  push    rdi
0x140008add  push    r12
0x140008adf  push    r13
0x140008ae1  push    r14
0x140008ae3  push    r15
0x140008ae5  sub     rsp, 28h
0x140008ae9  mov     [rcx+4], r8d
0x140008aed  xor     r13d, r13d
0x140008af0  mov     eax, [rdx+8]
0x140008af3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140008af7  mov     [rcx+8], eax
0x140008afa  mov     rdi, rcx
0x140008afd  mov     [rcx+10h], r13
0x140008b01  mov     r12, rdx
0x140008b04  movzx   eax, word ptr [rdx+40h]
0x140008b08  mov     [rcx+18h], ax
0x140008b0c  mov     al, [rdx]
0x140008b0e  mov     [rcx+1Ah], al
0x140008b11  mov     [rcx+20h], r13
0x140008b15  mov     rax, [rdx+88h]
0x140008b1c  mov     [rcx+28h], rax
0x140008b20  mov     rax, [rdx+90h]
0x140008b27  mov     [rcx+30h], rax
0x140008b2b  mov     [rcx+38h], r13
0x140008b2f  mov     rcx, [rdx+38h]
0x140008b33  lea     edx, [rbp+2]
0x140008b36  test    rcx, rcx
0x140008b39  jnz     short loc_140008B40
0x140008b3b  mov     r8d, edx
0x140008b3e  jmp     short loc_140008B50
0x140008b40  mov     rax, rbp
0x140008b43  inc     rax
0x140008b46  cmp     [rcx+rax], r13b
0x140008b4a  jnz     short loc_140008B43
0x140008b4c  lea     r8, [rax+1]; unsigned __int64
0x140008b50  mov     rcx, [r12+80h]
0x140008b58  test    rcx, rcx
0x140008b5b  jz      short loc_140008B6D
0x140008b5d  mov     rax, rbp
0x140008b60  inc     rax
0x140008b63  cmp     [rcx+rax], r13b
0x140008b67  jnz     short loc_140008B60
0x140008b69  lea     rdx, [rax+1]
0x140008b6d  mov     rcx, [r12+18h]
0x140008b72  test    rcx, rcx
0x140008b75  jnz     short loc_140008B7C
0x140008b77  lea     eax, [rcx+2]
0x140008b7a  jmp     short loc_140008B91
0x140008b7c  mov     rax, rbp
0x140008b7f  inc     rax
0x140008b82  cmp     [rcx+rax*2], r13w
0x140008b87  jnz     short loc_140008B7F
0x140008b89  lea     rax, ds:2[rax*2]
0x140008b91  lea     r14, [rdx+rax]
0x140008b95  add     r14, r8
0x140008b98  lea     rsi, [rdi+48h]
0x140008b9c  cmp     [rdi+40h], r13
0x140008ba0  jz      short loc_140008BA7
0x140008ba2  cmp     [rsi], r14
0x140008ba5  jnb     short loc_140008BDB
0x140008ba7  mov     rdx, r14; dwBytes
0x140008baa  mov     ecx, 8; dwFlags
0x140008baf  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008bb4  mov     r15, rax
0x140008bb7  test    rax, rax
0x140008bba  jz      short loc_140008BDB
0x140008bbc  mov     rbx, [rdi+40h]
0x140008bc0  call    cs:__imp_GetProcessHeap
0x140008bc6  mov     r8, rbx; lpMem
0x140008bc9  xor     edx, edx; dwFlags
0x140008bcb  mov     rcx, rax; hHeap
0x140008bce  call    cs:__imp_HeapFree
0x140008bd4  mov     [rdi+40h], r15
0x140008bd8  mov     [rsi], r14
0x140008bdb  mov     rbx, [rdi+40h]
0x140008bdf  test    rbx, rbx
0x140008be2  jz      loc_140008CE3
0x140008be8  mov     rdx, [rsi]; DestinationSize
0x140008beb  lea     rsi, [rdx+rbx]
0x140008bef  cmp     rbx, rsi
0x140008bf2  jz      short loc_140008C33
0x140008bf4  mov     r8, [r12+38h]; Source
0x140008bf9  test    r8, r8
0x140008bfc  jz      short loc_140008C33
0x140008bfe  cmp     [r8], r13b
0x140008c01  jz      short loc_140008C33
0x140008c03  mov     rax, rbp
0x140008c06  inc     rax
0x140008c09  cmp     [r8+rax], r13b
0x140008c0d  jnz     short loc_140008C06
0x140008c0f  lea     r14, [rax+1]
0x140008c13  cmp     rdx, r14
0x140008c16  jnb     short loc_140008C1E
0x140008c18  mov     [rdi+10h], r13
0x140008c1c  jmp     short loc_140008C3C
0x140008c1e  mov     r9, r14; SourceSize
0x140008c21  mov     rcx, rbx; Destination
0x140008c24  call    cs:__imp_memcpy_s
0x140008c2a  mov     [rdi+10h], rbx
0x140008c2e  add     rbx, r14
0x140008c31  jmp     short loc_140008C37
0x140008c33  mov     [rdi+10h], r13
0x140008c37  cmp     rbx, rsi
0x140008c3a  jz      short loc_140008C84
0x140008c3c  mov     r8, [r12+80h]; Source
0x140008c44  test    r8, r8
0x140008c47  jz      short loc_140008C84
0x140008c49  cmp     [r8], r13b
0x140008c4c  jz      short loc_140008C84
0x140008c4e  mov     rax, rbp
0x140008c51  inc     rax
0x140008c54  cmp     [r8+rax], r13b
0x140008c58  jnz     short loc_140008C51
0x140008c5a  mov     rdx, rsi
0x140008c5d  lea     r14, [rax+1]
0x140008c61  sub     rdx, rbx; DestinationSize
0x140008c64  cmp     rdx, r14
0x140008c67  jnb     short loc_140008C6F
0x140008c69  mov     [rdi+20h], r13
0x140008c6d  jmp     short loc_140008C8D
0x140008c6f  mov     r9, r14; SourceSize
0x140008c72  mov     rcx, rbx; Destination
0x140008c75  call    cs:__imp_memcpy_s
0x140008c7b  mov     [rdi+20h], rbx
0x140008c7f  add     rbx, r14
0x140008c82  jmp     short loc_140008C88
0x140008c84  mov     [rdi+20h], r13
0x140008c88  cmp     rbx, rsi
0x140008c8b  jz      short loc_140008CCF
0x140008c8d  mov     r8, [r12+18h]; Source
0x140008c92  test    r8, r8
0x140008c95  jz      short loc_140008CCF
0x140008c97  cmp     [r8], r13w
0x140008c9b  jz      short loc_140008CCF
0x140008c9d  inc     rbp
0x140008ca0  cmp     [r8+rbp*2], r13w
0x140008ca5  jnz     short loc_140008C9D
0x140008ca7  mov     rdx, rsi
0x140008caa  lea     r14, ds:2[rbp*2]
0x140008cb2  sub     rdx, rbx; DestinationSize
0x140008cb5  cmp     rdx, r14
0x140008cb8  jb      short loc_140008CCF
0x140008cba  mov     r9, r14; SourceSize
0x140008cbd  mov     rcx, rbx; Destination
0x140008cc0  call    cs:__imp_memcpy_s
0x140008cc6  mov     [rdi+38h], rbx
0x140008cca  add     rbx, r14
0x140008ccd  jmp     short loc_140008CD3
0x140008ccf  mov     [rdi+38h], r13
0x140008cd3  sub     rsi, rbx
0x140008cd6  xor     edx, edx; Val
0x140008cd8  mov     r8, rsi; Size
0x140008cdb  mov     rcx, rbx; void *
0x140008cde  call    memset_0
0x140008ce3  add     rsp, 28h
0x140008ce7  pop     r15
0x140008ce9  pop     r14
0x140008ceb  pop     r13
0x140008ced  pop     r12
0x140008cef  pop     rdi
0x140008cf0  pop     rsi
0x140008cf1  pop     rbp
0x140008cf2  pop     rbx
0x140008cf3  retn
```
