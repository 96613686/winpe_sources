# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000cb34`
- end: `0x18000cd4d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a4f0`

## callees

- `0x1800035e8`
- `0x180006ba4`
- `0x18000ae30`
- `0x18000cb34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc2a`

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
0x18000cb34  push    rbx
0x18000cb36  push    rbp
0x18000cb37  push    rsi
0x18000cb38  push    rdi
0x18000cb39  push    r12
0x18000cb3b  push    r13
0x18000cb3d  push    r14
0x18000cb3f  push    r15
0x18000cb41  sub     rsp, 28h
0x18000cb45  mov     [rcx+4], r8d
0x18000cb49  xor     r13d, r13d
0x18000cb4c  mov     eax, [rdx+8]
0x18000cb4f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000cb53  mov     [rcx+8], eax
0x18000cb56  mov     rdi, rcx
0x18000cb59  mov     [rcx+10h], r13
0x18000cb5d  mov     r12, rdx
0x18000cb60  movzx   eax, word ptr [rdx+40h]
0x18000cb64  mov     [rcx+18h], ax
0x18000cb68  mov     al, [rdx]
0x18000cb6a  mov     [rcx+1Ah], al
0x18000cb6d  mov     [rcx+20h], r13
0x18000cb71  mov     rax, [rdx+88h]
0x18000cb78  mov     [rcx+28h], rax
0x18000cb7c  mov     rax, [rdx+90h]
0x18000cb83  mov     [rcx+30h], rax
0x18000cb87  mov     [rcx+38h], r13
0x18000cb8b  mov     rcx, [rdx+38h]
0x18000cb8f  lea     edx, [rbp+2]
0x18000cb92  test    rcx, rcx
0x18000cb95  jnz     short loc_18000CB9C
0x18000cb97  mov     r8d, edx
0x18000cb9a  jmp     short loc_18000CBAC
0x18000cb9c  mov     rax, rbp
0x18000cb9f  inc     rax
0x18000cba2  cmp     [rcx+rax], r13b
0x18000cba6  jnz     short loc_18000CB9F
0x18000cba8  lea     r8, [rax+1]; unsigned __int64
0x18000cbac  mov     rcx, [r12+80h]
0x18000cbb4  test    rcx, rcx
0x18000cbb7  jz      short loc_18000CBC9
0x18000cbb9  mov     rax, rbp
0x18000cbbc  inc     rax
0x18000cbbf  cmp     [rcx+rax], r13b
0x18000cbc3  jnz     short loc_18000CBBC
0x18000cbc5  lea     rdx, [rax+1]
0x18000cbc9  mov     rcx, [r12+18h]
0x18000cbce  test    rcx, rcx
0x18000cbd1  jnz     short loc_18000CBD8
0x18000cbd3  lea     eax, [rcx+2]
0x18000cbd6  jmp     short loc_18000CBED
0x18000cbd8  mov     rax, rbp
0x18000cbdb  inc     rax
0x18000cbde  cmp     [rcx+rax*2], r13w
0x18000cbe3  jnz     short loc_18000CBDB
0x18000cbe5  lea     rax, ds:2[rax*2]
0x18000cbed  lea     r14, [rdx+rax]
0x18000cbf1  add     r14, r8
0x18000cbf4  lea     rsi, [rdi+48h]
0x18000cbf8  cmp     [rdi+40h], r13
0x18000cbfc  jz      short loc_18000CC03
0x18000cbfe  cmp     [rsi], r14
0x18000cc01  jnb     short loc_18000CC37
0x18000cc03  mov     rdx, r14; dwBytes
0x18000cc06  mov     ecx, 8; dwFlags
0x18000cc0b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000cc10  mov     r15, rax
0x18000cc13  test    rax, rax
0x18000cc16  jz      short loc_18000CC37
0x18000cc18  mov     rbx, [rdi+40h]
0x18000cc1c  call    cs:__imp_GetProcessHeap
0x18000cc22  mov     r8, rbx; lpMem
0x18000cc25  xor     edx, edx; dwFlags
0x18000cc27  mov     rcx, rax; hHeap
0x18000cc2a  call    cs:__imp_HeapFree
0x18000cc30  mov     [rdi+40h], r15
0x18000cc34  mov     [rsi], r14
0x18000cc37  mov     rbx, [rdi+40h]
0x18000cc3b  test    rbx, rbx
0x18000cc3e  jz      loc_18000CD3C
0x18000cc44  mov     rdx, [rsi]; DestinationSize
0x18000cc47  lea     rsi, [rdx+rbx]
0x18000cc4b  cmp     rbx, rsi
0x18000cc4e  jz      short loc_18000CC8E
0x18000cc50  mov     r8, [r12+38h]; Source
0x18000cc55  test    r8, r8
0x18000cc58  jz      short loc_18000CC8E
0x18000cc5a  cmp     [r8], r13b
0x18000cc5d  jz      short loc_18000CC8E
0x18000cc5f  mov     rax, rbp
0x18000cc62  inc     rax
0x18000cc65  cmp     [r8+rax], r13b
0x18000cc69  jnz     short loc_18000CC62
0x18000cc6b  lea     r14, [rax+1]
0x18000cc6f  cmp     rdx, r14
0x18000cc72  jnb     short loc_18000CC7A
0x18000cc74  mov     [rdi+10h], r13
0x18000cc78  jmp     short loc_18000CC97
0x18000cc7a  mov     r9, r14; SourceSize
0x18000cc7d  mov     rcx, rbx; Destination
0x18000cc80  call    memcpy_s
0x18000cc85  mov     [rdi+10h], rbx
0x18000cc89  add     rbx, r14
0x18000cc8c  jmp     short loc_18000CC92
0x18000cc8e  mov     [rdi+10h], r13
0x18000cc92  cmp     rbx, rsi
0x18000cc95  jz      short loc_18000CCDE
0x18000cc97  mov     r8, [r12+80h]; Source
0x18000cc9f  test    r8, r8
0x18000cca2  jz      short loc_18000CCDE
0x18000cca4  cmp     [r8], r13b
0x18000cca7  jz      short loc_18000CCDE
0x18000cca9  mov     rax, rbp
0x18000ccac  inc     rax
0x18000ccaf  cmp     [r8+rax], r13b
0x18000ccb3  jnz     short loc_18000CCAC
0x18000ccb5  mov     rdx, rsi
0x18000ccb8  lea     r14, [rax+1]
0x18000ccbc  sub     rdx, rbx; DestinationSize
0x18000ccbf  cmp     rdx, r14
0x18000ccc2  jnb     short loc_18000CCCA
0x18000ccc4  mov     [rdi+20h], r13
0x18000ccc8  jmp     short loc_18000CCE7
0x18000ccca  mov     r9, r14; SourceSize
0x18000cccd  mov     rcx, rbx; Destination
0x18000ccd0  call    memcpy_s
0x18000ccd5  mov     [rdi+20h], rbx
0x18000ccd9  add     rbx, r14
0x18000ccdc  jmp     short loc_18000CCE2
0x18000ccde  mov     [rdi+20h], r13
0x18000cce2  cmp     rbx, rsi
0x18000cce5  jz      short loc_18000CD28
0x18000cce7  mov     r8, [r12+18h]; Source
0x18000ccec  test    r8, r8
0x18000ccef  jz      short loc_18000CD28
0x18000ccf1  cmp     [r8], r13w
0x18000ccf5  jz      short loc_18000CD28
0x18000ccf7  inc     rbp
0x18000ccfa  cmp     [r8+rbp*2], r13w
0x18000ccff  jnz     short loc_18000CCF7
0x18000cd01  mov     rdx, rsi
0x18000cd04  lea     r14, ds:2[rbp*2]
0x18000cd0c  sub     rdx, rbx; DestinationSize
0x18000cd0f  cmp     rdx, r14
0x18000cd12  jb      short loc_18000CD28
0x18000cd14  mov     r9, r14; SourceSize
0x18000cd17  mov     rcx, rbx; Destination
0x18000cd1a  call    memcpy_s
0x18000cd1f  mov     [rdi+38h], rbx
0x18000cd23  add     rbx, r14
0x18000cd26  jmp     short loc_18000CD2C
0x18000cd28  mov     [rdi+38h], r13
0x18000cd2c  sub     rsi, rbx
0x18000cd2f  xor     edx, edx; Val
0x18000cd31  mov     r8, rsi; Size
0x18000cd34  mov     rcx, rbx; void *
0x18000cd37  call    memset_0
0x18000cd3c  add     rsp, 28h
0x18000cd40  pop     r15
0x18000cd42  pop     r14
0x18000cd44  pop     r13
0x18000cd46  pop     r12
0x18000cd48  pop     rdi
0x18000cd49  pop     rsi
0x18000cd4a  pop     rbp
0x18000cd4b  pop     rbx
0x18000cd4c  retn
```
