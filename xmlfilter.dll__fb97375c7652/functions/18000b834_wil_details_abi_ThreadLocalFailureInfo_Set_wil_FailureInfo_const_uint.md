# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000b834`
- end: `0x18000ba4d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007470`

## callees

- `0x180002b38`
- `0x180009870`
- `0x18000b834`
- `0x18000e158`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b92a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b92a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b91c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b91c`

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
0x18000b834  push    rbx
0x18000b836  push    rbp
0x18000b837  push    rsi
0x18000b838  push    rdi
0x18000b839  push    r12
0x18000b83b  push    r13
0x18000b83d  push    r14
0x18000b83f  push    r15
0x18000b841  sub     rsp, 28h
0x18000b845  mov     [rcx+4], r8d
0x18000b849  xor     r13d, r13d
0x18000b84c  mov     eax, [rdx+8]
0x18000b84f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000b853  mov     [rcx+8], eax
0x18000b856  mov     rdi, rcx
0x18000b859  mov     [rcx+10h], r13
0x18000b85d  mov     r12, rdx
0x18000b860  movzx   eax, word ptr [rdx+40h]
0x18000b864  mov     [rcx+18h], ax
0x18000b868  mov     al, [rdx]
0x18000b86a  mov     [rcx+1Ah], al
0x18000b86d  mov     [rcx+20h], r13
0x18000b871  mov     rax, [rdx+88h]
0x18000b878  mov     [rcx+28h], rax
0x18000b87c  mov     rax, [rdx+90h]
0x18000b883  mov     [rcx+30h], rax
0x18000b887  mov     [rcx+38h], r13
0x18000b88b  mov     rcx, [rdx+38h]
0x18000b88f  lea     edx, [rbp+2]
0x18000b892  test    rcx, rcx
0x18000b895  jnz     short loc_18000B89C
0x18000b897  mov     r8d, edx
0x18000b89a  jmp     short loc_18000B8AC
0x18000b89c  mov     rax, rbp
0x18000b89f  inc     rax
0x18000b8a2  cmp     [rcx+rax], r13b
0x18000b8a6  jnz     short loc_18000B89F
0x18000b8a8  lea     r8, [rax+1]; unsigned __int64
0x18000b8ac  mov     rcx, [r12+80h]
0x18000b8b4  test    rcx, rcx
0x18000b8b7  jz      short loc_18000B8C9
0x18000b8b9  mov     rax, rbp
0x18000b8bc  inc     rax
0x18000b8bf  cmp     [rcx+rax], r13b
0x18000b8c3  jnz     short loc_18000B8BC
0x18000b8c5  lea     rdx, [rax+1]
0x18000b8c9  mov     rcx, [r12+18h]
0x18000b8ce  test    rcx, rcx
0x18000b8d1  jnz     short loc_18000B8D8
0x18000b8d3  lea     eax, [rcx+2]
0x18000b8d6  jmp     short loc_18000B8ED
0x18000b8d8  mov     rax, rbp
0x18000b8db  inc     rax
0x18000b8de  cmp     [rcx+rax*2], r13w
0x18000b8e3  jnz     short loc_18000B8DB
0x18000b8e5  lea     rax, ds:2[rax*2]
0x18000b8ed  lea     r14, [rdx+rax]
0x18000b8f1  add     r14, r8
0x18000b8f4  lea     rsi, [rdi+48h]
0x18000b8f8  cmp     [rdi+40h], r13
0x18000b8fc  jz      short loc_18000B903
0x18000b8fe  cmp     [rsi], r14
0x18000b901  jnb     short loc_18000B937
0x18000b903  mov     rdx, r14; dwBytes
0x18000b906  mov     ecx, 8; dwFlags
0x18000b90b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b910  mov     r15, rax
0x18000b913  test    rax, rax
0x18000b916  jz      short loc_18000B937
0x18000b918  mov     rbx, [rdi+40h]
0x18000b91c  call    cs:__imp_GetProcessHeap
0x18000b922  mov     r8, rbx; lpMem
0x18000b925  xor     edx, edx; dwFlags
0x18000b927  mov     rcx, rax; hHeap
0x18000b92a  call    cs:__imp_HeapFree
0x18000b930  mov     [rdi+40h], r15
0x18000b934  mov     [rsi], r14
0x18000b937  mov     rbx, [rdi+40h]
0x18000b93b  test    rbx, rbx
0x18000b93e  jz      loc_18000BA3C
0x18000b944  mov     rdx, [rsi]; DestinationSize
0x18000b947  lea     rsi, [rdx+rbx]
0x18000b94b  cmp     rbx, rsi
0x18000b94e  jz      short loc_18000B98E
0x18000b950  mov     r8, [r12+38h]; Source
0x18000b955  test    r8, r8
0x18000b958  jz      short loc_18000B98E
0x18000b95a  cmp     [r8], r13b
0x18000b95d  jz      short loc_18000B98E
0x18000b95f  mov     rax, rbp
0x18000b962  inc     rax
0x18000b965  cmp     [r8+rax], r13b
0x18000b969  jnz     short loc_18000B962
0x18000b96b  lea     r14, [rax+1]
0x18000b96f  cmp     rdx, r14
0x18000b972  jnb     short loc_18000B97A
0x18000b974  mov     [rdi+10h], r13
0x18000b978  jmp     short loc_18000B997
0x18000b97a  mov     r9, r14; SourceSize
0x18000b97d  mov     rcx, rbx; Destination
0x18000b980  call    memcpy_s
0x18000b985  mov     [rdi+10h], rbx
0x18000b989  add     rbx, r14
0x18000b98c  jmp     short loc_18000B992
0x18000b98e  mov     [rdi+10h], r13
0x18000b992  cmp     rbx, rsi
0x18000b995  jz      short loc_18000B9DE
0x18000b997  mov     r8, [r12+80h]; Source
0x18000b99f  test    r8, r8
0x18000b9a2  jz      short loc_18000B9DE
0x18000b9a4  cmp     [r8], r13b
0x18000b9a7  jz      short loc_18000B9DE
0x18000b9a9  mov     rax, rbp
0x18000b9ac  inc     rax
0x18000b9af  cmp     [r8+rax], r13b
0x18000b9b3  jnz     short loc_18000B9AC
0x18000b9b5  mov     rdx, rsi
0x18000b9b8  lea     r14, [rax+1]
0x18000b9bc  sub     rdx, rbx; DestinationSize
0x18000b9bf  cmp     rdx, r14
0x18000b9c2  jnb     short loc_18000B9CA
0x18000b9c4  mov     [rdi+20h], r13
0x18000b9c8  jmp     short loc_18000B9E7
0x18000b9ca  mov     r9, r14; SourceSize
0x18000b9cd  mov     rcx, rbx; Destination
0x18000b9d0  call    memcpy_s
0x18000b9d5  mov     [rdi+20h], rbx
0x18000b9d9  add     rbx, r14
0x18000b9dc  jmp     short loc_18000B9E2
0x18000b9de  mov     [rdi+20h], r13
0x18000b9e2  cmp     rbx, rsi
0x18000b9e5  jz      short loc_18000BA28
0x18000b9e7  mov     r8, [r12+18h]; Source
0x18000b9ec  test    r8, r8
0x18000b9ef  jz      short loc_18000BA28
0x18000b9f1  cmp     [r8], r13w
0x18000b9f5  jz      short loc_18000BA28
0x18000b9f7  inc     rbp
0x18000b9fa  cmp     [r8+rbp*2], r13w
0x18000b9ff  jnz     short loc_18000B9F7
0x18000ba01  mov     rdx, rsi
0x18000ba04  lea     r14, ds:2[rbp*2]
0x18000ba0c  sub     rdx, rbx; DestinationSize
0x18000ba0f  cmp     rdx, r14
0x18000ba12  jb      short loc_18000BA28
0x18000ba14  mov     r9, r14; SourceSize
0x18000ba17  mov     rcx, rbx; Destination
0x18000ba1a  call    memcpy_s
0x18000ba1f  mov     [rdi+38h], rbx
0x18000ba23  add     rbx, r14
0x18000ba26  jmp     short loc_18000BA2C
0x18000ba28  mov     [rdi+38h], r13
0x18000ba2c  sub     rsi, rbx
0x18000ba2f  xor     edx, edx; Val
0x18000ba31  mov     r8, rsi; Size
0x18000ba34  mov     rcx, rbx; void *
0x18000ba37  call    memset_0
0x18000ba3c  add     rsp, 28h
0x18000ba40  pop     r15
0x18000ba42  pop     r14
0x18000ba44  pop     r13
0x18000ba46  pop     r12
0x18000ba48  pop     rdi
0x18000ba49  pop     rsi
0x18000ba4a  pop     rbp
0x18000ba4b  pop     rbx
0x18000ba4c  retn
```
