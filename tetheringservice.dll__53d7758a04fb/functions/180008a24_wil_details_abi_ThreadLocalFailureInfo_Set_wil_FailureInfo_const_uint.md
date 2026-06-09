# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008a24`
- end: `0x180008c3d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006250`

## callees

- `0x180003088`
- `0x1800071b8`
- `0x180008a24`
- `0x18000a7a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b1a`

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
0x180008a24  push    rbx
0x180008a26  push    rbp
0x180008a27  push    rsi
0x180008a28  push    rdi
0x180008a29  push    r12
0x180008a2b  push    r13
0x180008a2d  push    r14
0x180008a2f  push    r15
0x180008a31  sub     rsp, 28h
0x180008a35  mov     [rcx+4], r8d
0x180008a39  xor     r13d, r13d
0x180008a3c  mov     eax, [rdx+8]
0x180008a3f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180008a43  mov     [rcx+8], eax
0x180008a46  mov     rdi, rcx
0x180008a49  mov     [rcx+10h], r13
0x180008a4d  mov     r12, rdx
0x180008a50  movzx   eax, word ptr [rdx+40h]
0x180008a54  mov     [rcx+18h], ax
0x180008a58  mov     al, [rdx]
0x180008a5a  mov     [rcx+1Ah], al
0x180008a5d  mov     [rcx+20h], r13
0x180008a61  mov     rax, [rdx+88h]
0x180008a68  mov     [rcx+28h], rax
0x180008a6c  mov     rax, [rdx+90h]
0x180008a73  mov     [rcx+30h], rax
0x180008a77  mov     [rcx+38h], r13
0x180008a7b  mov     rcx, [rdx+38h]
0x180008a7f  lea     edx, [rbp+2]
0x180008a82  test    rcx, rcx
0x180008a85  jnz     short loc_180008A8C
0x180008a87  mov     r8d, edx
0x180008a8a  jmp     short loc_180008A9C
0x180008a8c  mov     rax, rbp
0x180008a8f  inc     rax
0x180008a92  cmp     [rcx+rax], r13b
0x180008a96  jnz     short loc_180008A8F
0x180008a98  lea     r8, [rax+1]; unsigned __int64
0x180008a9c  mov     rcx, [r12+80h]
0x180008aa4  test    rcx, rcx
0x180008aa7  jz      short loc_180008AB9
0x180008aa9  mov     rax, rbp
0x180008aac  inc     rax
0x180008aaf  cmp     [rcx+rax], r13b
0x180008ab3  jnz     short loc_180008AAC
0x180008ab5  lea     rdx, [rax+1]
0x180008ab9  mov     rcx, [r12+18h]
0x180008abe  test    rcx, rcx
0x180008ac1  jnz     short loc_180008AC8
0x180008ac3  lea     eax, [rcx+2]
0x180008ac6  jmp     short loc_180008ADD
0x180008ac8  mov     rax, rbp
0x180008acb  inc     rax
0x180008ace  cmp     [rcx+rax*2], r13w
0x180008ad3  jnz     short loc_180008ACB
0x180008ad5  lea     rax, ds:2[rax*2]
0x180008add  lea     r14, [rdx+rax]
0x180008ae1  add     r14, r8
0x180008ae4  lea     rsi, [rdi+48h]
0x180008ae8  cmp     [rdi+40h], r13
0x180008aec  jz      short loc_180008AF3
0x180008aee  cmp     [rsi], r14
0x180008af1  jnb     short loc_180008B27
0x180008af3  mov     rdx, r14; dwBytes
0x180008af6  mov     ecx, 8; dwFlags
0x180008afb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008b00  mov     r15, rax
0x180008b03  test    rax, rax
0x180008b06  jz      short loc_180008B27
0x180008b08  mov     rbx, [rdi+40h]
0x180008b0c  call    cs:__imp_GetProcessHeap
0x180008b12  mov     r8, rbx; lpMem
0x180008b15  xor     edx, edx; dwFlags
0x180008b17  mov     rcx, rax; hHeap
0x180008b1a  call    cs:__imp_HeapFree
0x180008b20  mov     [rdi+40h], r15
0x180008b24  mov     [rsi], r14
0x180008b27  mov     rbx, [rdi+40h]
0x180008b2b  test    rbx, rbx
0x180008b2e  jz      loc_180008C2C
0x180008b34  mov     rdx, [rsi]; DestinationSize
0x180008b37  lea     rsi, [rdx+rbx]
0x180008b3b  cmp     rbx, rsi
0x180008b3e  jz      short loc_180008B7E
0x180008b40  mov     r8, [r12+38h]; Source
0x180008b45  test    r8, r8
0x180008b48  jz      short loc_180008B7E
0x180008b4a  cmp     [r8], r13b
0x180008b4d  jz      short loc_180008B7E
0x180008b4f  mov     rax, rbp
0x180008b52  inc     rax
0x180008b55  cmp     [r8+rax], r13b
0x180008b59  jnz     short loc_180008B52
0x180008b5b  lea     r14, [rax+1]
0x180008b5f  cmp     rdx, r14
0x180008b62  jnb     short loc_180008B6A
0x180008b64  mov     [rdi+10h], r13
0x180008b68  jmp     short loc_180008B87
0x180008b6a  mov     r9, r14; SourceSize
0x180008b6d  mov     rcx, rbx; Destination
0x180008b70  call    memcpy_s
0x180008b75  mov     [rdi+10h], rbx
0x180008b79  add     rbx, r14
0x180008b7c  jmp     short loc_180008B82
0x180008b7e  mov     [rdi+10h], r13
0x180008b82  cmp     rbx, rsi
0x180008b85  jz      short loc_180008BCE
0x180008b87  mov     r8, [r12+80h]; Source
0x180008b8f  test    r8, r8
0x180008b92  jz      short loc_180008BCE
0x180008b94  cmp     [r8], r13b
0x180008b97  jz      short loc_180008BCE
0x180008b99  mov     rax, rbp
0x180008b9c  inc     rax
0x180008b9f  cmp     [r8+rax], r13b
0x180008ba3  jnz     short loc_180008B9C
0x180008ba5  mov     rdx, rsi
0x180008ba8  lea     r14, [rax+1]
0x180008bac  sub     rdx, rbx; DestinationSize
0x180008baf  cmp     rdx, r14
0x180008bb2  jnb     short loc_180008BBA
0x180008bb4  mov     [rdi+20h], r13
0x180008bb8  jmp     short loc_180008BD7
0x180008bba  mov     r9, r14; SourceSize
0x180008bbd  mov     rcx, rbx; Destination
0x180008bc0  call    memcpy_s
0x180008bc5  mov     [rdi+20h], rbx
0x180008bc9  add     rbx, r14
0x180008bcc  jmp     short loc_180008BD2
0x180008bce  mov     [rdi+20h], r13
0x180008bd2  cmp     rbx, rsi
0x180008bd5  jz      short loc_180008C18
0x180008bd7  mov     r8, [r12+18h]; Source
0x180008bdc  test    r8, r8
0x180008bdf  jz      short loc_180008C18
0x180008be1  cmp     [r8], r13w
0x180008be5  jz      short loc_180008C18
0x180008be7  inc     rbp
0x180008bea  cmp     [r8+rbp*2], r13w
0x180008bef  jnz     short loc_180008BE7
0x180008bf1  mov     rdx, rsi
0x180008bf4  lea     r14, ds:2[rbp*2]
0x180008bfc  sub     rdx, rbx; DestinationSize
0x180008bff  cmp     rdx, r14
0x180008c02  jb      short loc_180008C18
0x180008c04  mov     r9, r14; SourceSize
0x180008c07  mov     rcx, rbx; Destination
0x180008c0a  call    memcpy_s
0x180008c0f  mov     [rdi+38h], rbx
0x180008c13  add     rbx, r14
0x180008c16  jmp     short loc_180008C1C
0x180008c18  mov     [rdi+38h], r13
0x180008c1c  sub     rsi, rbx
0x180008c1f  xor     edx, edx; Val
0x180008c21  mov     r8, rsi; Size
0x180008c24  mov     rcx, rbx; void *
0x180008c27  call    memset_0
0x180008c2c  add     rsp, 28h
0x180008c30  pop     r15
0x180008c32  pop     r14
0x180008c34  pop     r13
0x180008c36  pop     r12
0x180008c38  pop     rdi
0x180008c39  pop     rsi
0x180008c3a  pop     rbp
0x180008c3b  pop     rbx
0x180008c3c  retn
```
