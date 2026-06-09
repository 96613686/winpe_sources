# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000c8b0`
- end: `0x18000cb14`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `612`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cc44`

## callees

- `0x18000b3f0`
- `0x18000c8b0`
- `0x18002f3ba`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ca0e`
- `msvcrt!memcpy_s` at `0x18000ca69`
- `msvcrt!memcpy_s` at `0x18000cac5`
- `msvcrt!memcpy_s` at `0x18000ca0e`
- `msvcrt!memcpy_s` at `0x18000ca69`
- `msvcrt!memcpy_s` at `0x18000cac5`
- `KERNEL32!GetProcessHeap` at `0x18000c9a2`
- `KERNEL32!GetProcessHeap` at `0x18000c9a2`
- `KERNEL32!HeapFree` at `0x18000c9b6`
- `KERNEL32!HeapFree` at `0x18000c9b6`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v4; // r12
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned __int64 v15; // rbp
  rsize_t *v16; // rdi
  LPVOID v17; // r14
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char **v22; // rdi
  _BYTE *v23; // r8
  char *v24; // r14
  __int64 v25; // rbp
  rsize_t v26; // rbp
  _BYTE *v27; // r8
  char **v28; // rdi
  __int64 v29; // rbp
  rsize_t v30; // rbp
  _WORD *v31; // r8
  char **v32; // rdi
  unsigned __int64 v33; // rsi

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  v4 = -1;
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(v6 + v8) );
    v7 = v8 + 1;
  }
  else
  {
    v7 = 1;
  }
  v9 = *((_QWORD *)a2 + 16);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v10 = v11 + 1;
  }
  else
  {
    v10 = 1;
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
  v15 = v7 + v13 + v10;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v7 + v13 + v10);
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
    v22 = (char **)((char *)this + 16);
    v23 = (_BYTE *)*((_QWORD *)a2 + 7);
    v24 = &v20[v21];
    if ( v20 == &v20[v21] )
      goto LABEL_30;
    if ( !v23 )
      goto LABEL_30;
    if ( !*v23 )
      goto LABEL_30;
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    v26 = v25 + 1;
    if ( v21 >= v26 )
    {
      memcpy_s(*((void *const *)this + 8), v21, v23, v26);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = v20;
      v20 += v26;
    }
    else
    {
LABEL_30:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = 0;
    }
    v27 = (_BYTE *)*((_QWORD *)a2 + 16);
    v28 = (char **)((char *)this + 32);
    if ( v20 == v24 )
      goto LABEL_41;
    if ( !v27 )
      goto LABEL_41;
    if ( !*v27 )
      goto LABEL_41;
    v29 = -1;
    do
      ++v29;
    while ( v27[v29] );
    v30 = v29 + 1;
    if ( v24 - v20 >= v30 )
    {
      memcpy_s(v20, v24 - v20, v27, v30);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = v20;
      v20 += v30;
    }
    else
    {
LABEL_41:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = 0;
    }
    v31 = (_WORD *)*((_QWORD *)a2 + 3);
    v32 = (char **)((char *)this + 56);
    if ( v20 == v24 || !v31 || !*v31 )
      goto LABEL_51;
    do
      ++v4;
    while ( v31[v4] );
    v33 = 2 * v4 + 2;
    if ( v24 - v20 >= v33 )
    {
      memcpy_s(v20, v24 - v20, v31, 2 * v4 + 2);
      if ( v32 )
        *v32 = v20;
      v20 += v33;
    }
    else
    {
LABEL_51:
      if ( v32 )
        *v32 = 0;
    }
    memset_0(v20, 0, v24 - v20);
  }
}

```

## disassembly

```asm
0x18000c8b0  mov     [rsp+arg_0], rbx
0x18000c8b5  mov     [rsp+arg_8], rbp
0x18000c8ba  mov     [rsp+arg_10], rsi
0x18000c8bf  push    rdi
0x18000c8c0  push    r12
0x18000c8c2  push    r13
0x18000c8c4  push    r14
0x18000c8c6  push    r15
0x18000c8c8  sub     rsp, 20h
0x18000c8cc  mov     [rcx+4], r8d
0x18000c8d0  xor     r13d, r13d
0x18000c8d3  mov     eax, [rdx+8]
0x18000c8d6  mov     rsi, rcx
0x18000c8d9  mov     [rcx+8], eax
0x18000c8dc  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000c8e0  mov     [rcx+10h], r13
0x18000c8e4  mov     r15, rdx
0x18000c8e7  movzx   eax, word ptr [rdx+40h]
0x18000c8eb  mov     [rcx+18h], ax
0x18000c8ef  mov     al, [rdx]
0x18000c8f1  mov     [rcx+1Ah], al
0x18000c8f4  mov     [rcx+20h], r13
0x18000c8f8  mov     rax, [rdx+88h]
0x18000c8ff  mov     [rcx+28h], rax
0x18000c903  mov     rax, [rdx+90h]
0x18000c90a  mov     [rcx+30h], rax
0x18000c90e  mov     [rcx+38h], r13
0x18000c912  mov     rcx, [rdx+38h]
0x18000c916  test    rcx, rcx
0x18000c919  jnz     short loc_18000C920
0x18000c91b  lea     eax, [rcx+1]
0x18000c91e  jmp     short loc_18000C92F
0x18000c920  mov     rax, r12
0x18000c923  inc     rax
0x18000c926  cmp     [rcx+rax], r13b
0x18000c92a  jnz     short loc_18000C923
0x18000c92c  inc     rax
0x18000c92f  mov     rdx, [rdx+80h]
0x18000c936  test    rdx, rdx
0x18000c939  jnz     short loc_18000C940
0x18000c93b  lea     ecx, [rdx+1]
0x18000c93e  jmp     short loc_18000C94F
0x18000c940  mov     rcx, r12
0x18000c943  inc     rcx
0x18000c946  cmp     [rdx+rcx], r13b
0x18000c94a  jnz     short loc_18000C943
0x18000c94c  inc     rcx
0x18000c94f  mov     r8, [r15+18h]; unsigned __int64
0x18000c953  test    r8, r8
0x18000c956  jnz     short loc_18000C95E
0x18000c958  lea     edx, [r8+2]
0x18000c95c  jmp     short loc_18000C973
0x18000c95e  mov     rdx, r12
0x18000c961  inc     rdx
0x18000c964  cmp     [r8+rdx*2], r13w
0x18000c969  jnz     short loc_18000C961
0x18000c96b  lea     rdx, ds:2[rdx*2]
0x18000c973  lea     rbp, [rdx+rcx]
0x18000c977  add     rbp, rax
0x18000c97a  lea     rdi, [rsi+48h]
0x18000c97e  cmp     [rsi+40h], r13
0x18000c982  jz      short loc_18000C989
0x18000c984  cmp     [rdi], rbp
0x18000c987  jnb     short loc_18000C9C9
0x18000c989  mov     rdx, rbp; dwBytes
0x18000c98c  mov     ecx, 8; dwFlags
0x18000c991  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c996  mov     r14, rax
0x18000c999  test    rax, rax
0x18000c99c  jz      short loc_18000C9C9
0x18000c99e  mov     rbx, [rsi+40h]
0x18000c9a2  call    cs:__imp_GetProcessHeap
0x18000c9a9  nop     dword ptr [rax+rax+00h]
0x18000c9ae  mov     r8, rbx; lpMem
0x18000c9b1  xor     edx, edx; dwFlags
0x18000c9b3  mov     rcx, rax; hHeap
0x18000c9b6  call    cs:__imp_HeapFree
0x18000c9bd  nop     dword ptr [rax+rax+00h]
0x18000c9c2  mov     [rsi+40h], r14
0x18000c9c6  mov     [rdi], rbp
0x18000c9c9  mov     rbx, [rsi+40h]
0x18000c9cd  test    rbx, rbx
0x18000c9d0  jz      loc_18000CAF6
0x18000c9d6  mov     rdx, [rdi]; DestinationSize
0x18000c9d9  lea     rdi, [rsi+10h]
0x18000c9dd  mov     r8, [r15+38h]; Source
0x18000c9e1  lea     r14, [rdx+rbx]
0x18000c9e5  cmp     rbx, r14
0x18000c9e8  jz      short loc_18000CA27
0x18000c9ea  test    r8, r8
0x18000c9ed  jz      short loc_18000CA27
0x18000c9ef  cmp     [r8], r13b
0x18000c9f2  jz      short loc_18000CA27
0x18000c9f4  mov     rbp, r12
0x18000c9f7  inc     rbp
0x18000c9fa  cmp     [r8+rbp], r13b
0x18000c9fe  jnz     short loc_18000C9F7
0x18000ca00  inc     rbp
0x18000ca03  cmp     rdx, rbp
0x18000ca06  jb      short loc_18000CA27
0x18000ca08  mov     r9, rbp; SourceSize
0x18000ca0b  mov     rcx, rbx; Destination
0x18000ca0e  call    cs:__imp_memcpy_s
0x18000ca15  nop     dword ptr [rax+rax+00h]
0x18000ca1a  test    rdi, rdi
0x18000ca1d  jz      short loc_18000CA22
0x18000ca1f  mov     [rdi], rbx
0x18000ca22  add     rbx, rbp
0x18000ca25  jmp     short loc_18000CA2F
0x18000ca27  test    rdi, rdi
0x18000ca2a  jz      short loc_18000CA2F
0x18000ca2c  mov     [rdi], r13
0x18000ca2f  mov     r8, [r15+80h]; Source
0x18000ca36  lea     rdi, [rsi+20h]
0x18000ca3a  cmp     rbx, r14
0x18000ca3d  jz      short loc_18000CA82
0x18000ca3f  test    r8, r8
0x18000ca42  jz      short loc_18000CA82
0x18000ca44  cmp     [r8], r13b
0x18000ca47  jz      short loc_18000CA82
0x18000ca49  mov     rbp, r12
0x18000ca4c  inc     rbp
0x18000ca4f  cmp     [r8+rbp], r13b
0x18000ca53  jnz     short loc_18000CA4C
0x18000ca55  mov     rdx, r14
0x18000ca58  inc     rbp
0x18000ca5b  sub     rdx, rbx; DestinationSize
0x18000ca5e  cmp     rdx, rbp
0x18000ca61  jb      short loc_18000CA82
0x18000ca63  mov     r9, rbp; SourceSize
0x18000ca66  mov     rcx, rbx; Destination
0x18000ca69  call    cs:__imp_memcpy_s
0x18000ca70  nop     dword ptr [rax+rax+00h]
0x18000ca75  test    rdi, rdi
0x18000ca78  jz      short loc_18000CA7D
0x18000ca7a  mov     [rdi], rbx
0x18000ca7d  add     rbx, rbp
0x18000ca80  jmp     short loc_18000CA8A
0x18000ca82  test    rdi, rdi
0x18000ca85  jz      short loc_18000CA8A
0x18000ca87  mov     [rdi], r13
0x18000ca8a  mov     r8, [r15+18h]; Source
0x18000ca8e  lea     rdi, [rsi+38h]
0x18000ca92  cmp     rbx, r14
0x18000ca95  jz      short loc_18000CADE
0x18000ca97  test    r8, r8
0x18000ca9a  jz      short loc_18000CADE
0x18000ca9c  cmp     [r8], r13w
0x18000caa0  jz      short loc_18000CADE
0x18000caa2  inc     r12
0x18000caa5  cmp     [r8+r12*2], r13w
0x18000caaa  jnz     short loc_18000CAA2
0x18000caac  mov     rdx, r14
0x18000caaf  lea     rsi, ds:2[r12*2]
0x18000cab7  sub     rdx, rbx; DestinationSize
0x18000caba  cmp     rdx, rsi
0x18000cabd  jb      short loc_18000CADE
0x18000cabf  mov     r9, rsi; SourceSize
0x18000cac2  mov     rcx, rbx; Destination
0x18000cac5  call    cs:__imp_memcpy_s
0x18000cacc  nop     dword ptr [rax+rax+00h]
0x18000cad1  test    rdi, rdi
0x18000cad4  jz      short loc_18000CAD9
0x18000cad6  mov     [rdi], rbx
0x18000cad9  add     rbx, rsi
0x18000cadc  jmp     short loc_18000CAE6
0x18000cade  test    rdi, rdi
0x18000cae1  jz      short loc_18000CAE6
0x18000cae3  mov     [rdi], r13
0x18000cae6  sub     r14, rbx
0x18000cae9  xor     edx, edx; Val
0x18000caeb  mov     r8, r14; Size
0x18000caee  mov     rcx, rbx; void *
0x18000caf1  call    memset_0
0x18000caf6  mov     rbx, [rsp+48h+arg_0]
0x18000cafb  mov     rbp, [rsp+48h+arg_8]
0x18000cb00  mov     rsi, [rsp+48h+arg_10]
0x18000cb05  add     rsp, 20h
0x18000cb09  pop     r15
0x18000cb0b  pop     r14
0x18000cb0d  pop     r13
0x18000cb0f  pop     r12
0x18000cb11  pop     rdi
0x18000cb12  retn
```
