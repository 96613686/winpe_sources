# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140013534`
- end: `0x14001374d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400117e0`

## callees

- `0x140002fbc`
- `0x140008ea8`
- `0x140013534`
- `0x140014d88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001361c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001361c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001362a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001362a`

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
0x140013534  push    rbx
0x140013536  push    rbp
0x140013537  push    rsi
0x140013538  push    rdi
0x140013539  push    r12
0x14001353b  push    r13
0x14001353d  push    r14
0x14001353f  push    r15
0x140013541  sub     rsp, 28h
0x140013545  mov     [rcx+4], r8d
0x140013549  xor     r13d, r13d
0x14001354c  mov     eax, [rdx+8]
0x14001354f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140013553  mov     [rcx+8], eax
0x140013556  mov     rdi, rcx
0x140013559  mov     [rcx+10h], r13
0x14001355d  mov     r12, rdx
0x140013560  movzx   eax, word ptr [rdx+40h]
0x140013564  mov     [rcx+18h], ax
0x140013568  mov     al, [rdx]
0x14001356a  mov     [rcx+1Ah], al
0x14001356d  mov     [rcx+20h], r13
0x140013571  mov     rax, [rdx+88h]
0x140013578  mov     [rcx+28h], rax
0x14001357c  mov     rax, [rdx+90h]
0x140013583  mov     [rcx+30h], rax
0x140013587  mov     [rcx+38h], r13
0x14001358b  mov     rcx, [rdx+38h]
0x14001358f  lea     edx, [rbp+2]
0x140013592  test    rcx, rcx
0x140013595  jnz     short loc_14001359C
0x140013597  mov     r8d, edx
0x14001359a  jmp     short loc_1400135AC
0x14001359c  mov     rax, rbp
0x14001359f  inc     rax
0x1400135a2  cmp     [rcx+rax], r13b
0x1400135a6  jnz     short loc_14001359F
0x1400135a8  lea     r8, [rax+1]; unsigned __int64
0x1400135ac  mov     rcx, [r12+80h]
0x1400135b4  test    rcx, rcx
0x1400135b7  jz      short loc_1400135C9
0x1400135b9  mov     rax, rbp
0x1400135bc  inc     rax
0x1400135bf  cmp     [rcx+rax], r13b
0x1400135c3  jnz     short loc_1400135BC
0x1400135c5  lea     rdx, [rax+1]
0x1400135c9  mov     rcx, [r12+18h]
0x1400135ce  test    rcx, rcx
0x1400135d1  jnz     short loc_1400135D8
0x1400135d3  lea     eax, [rcx+2]
0x1400135d6  jmp     short loc_1400135ED
0x1400135d8  mov     rax, rbp
0x1400135db  inc     rax
0x1400135de  cmp     [rcx+rax*2], r13w
0x1400135e3  jnz     short loc_1400135DB
0x1400135e5  lea     rax, ds:2[rax*2]
0x1400135ed  lea     r14, [rdx+rax]
0x1400135f1  add     r14, r8
0x1400135f4  lea     rsi, [rdi+48h]
0x1400135f8  cmp     [rdi+40h], r13
0x1400135fc  jz      short loc_140013603
0x1400135fe  cmp     [rsi], r14
0x140013601  jnb     short loc_140013637
0x140013603  mov     rdx, r14; dwBytes
0x140013606  mov     ecx, 8; dwFlags
0x14001360b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140013610  mov     r15, rax
0x140013613  test    rax, rax
0x140013616  jz      short loc_140013637
0x140013618  mov     rbx, [rdi+40h]
0x14001361c  call    cs:__imp_GetProcessHeap
0x140013622  mov     r8, rbx; lpMem
0x140013625  xor     edx, edx; dwFlags
0x140013627  mov     rcx, rax; hHeap
0x14001362a  call    cs:__imp_HeapFree
0x140013630  mov     [rdi+40h], r15
0x140013634  mov     [rsi], r14
0x140013637  mov     rbx, [rdi+40h]
0x14001363b  test    rbx, rbx
0x14001363e  jz      loc_14001373C
0x140013644  mov     rdx, [rsi]; DestinationSize
0x140013647  lea     rsi, [rdx+rbx]
0x14001364b  cmp     rbx, rsi
0x14001364e  jz      short loc_14001368E
0x140013650  mov     r8, [r12+38h]; Source
0x140013655  test    r8, r8
0x140013658  jz      short loc_14001368E
0x14001365a  cmp     [r8], r13b
0x14001365d  jz      short loc_14001368E
0x14001365f  mov     rax, rbp
0x140013662  inc     rax
0x140013665  cmp     [r8+rax], r13b
0x140013669  jnz     short loc_140013662
0x14001366b  lea     r14, [rax+1]
0x14001366f  cmp     rdx, r14
0x140013672  jnb     short loc_14001367A
0x140013674  mov     [rdi+10h], r13
0x140013678  jmp     short loc_140013697
0x14001367a  mov     r9, r14; SourceSize
0x14001367d  mov     rcx, rbx; Destination
0x140013680  call    memcpy_s
0x140013685  mov     [rdi+10h], rbx
0x140013689  add     rbx, r14
0x14001368c  jmp     short loc_140013692
0x14001368e  mov     [rdi+10h], r13
0x140013692  cmp     rbx, rsi
0x140013695  jz      short loc_1400136DE
0x140013697  mov     r8, [r12+80h]; Source
0x14001369f  test    r8, r8
0x1400136a2  jz      short loc_1400136DE
0x1400136a4  cmp     [r8], r13b
0x1400136a7  jz      short loc_1400136DE
0x1400136a9  mov     rax, rbp
0x1400136ac  inc     rax
0x1400136af  cmp     [r8+rax], r13b
0x1400136b3  jnz     short loc_1400136AC
0x1400136b5  mov     rdx, rsi
0x1400136b8  lea     r14, [rax+1]
0x1400136bc  sub     rdx, rbx; DestinationSize
0x1400136bf  cmp     rdx, r14
0x1400136c2  jnb     short loc_1400136CA
0x1400136c4  mov     [rdi+20h], r13
0x1400136c8  jmp     short loc_1400136E7
0x1400136ca  mov     r9, r14; SourceSize
0x1400136cd  mov     rcx, rbx; Destination
0x1400136d0  call    memcpy_s
0x1400136d5  mov     [rdi+20h], rbx
0x1400136d9  add     rbx, r14
0x1400136dc  jmp     short loc_1400136E2
0x1400136de  mov     [rdi+20h], r13
0x1400136e2  cmp     rbx, rsi
0x1400136e5  jz      short loc_140013728
0x1400136e7  mov     r8, [r12+18h]; Source
0x1400136ec  test    r8, r8
0x1400136ef  jz      short loc_140013728
0x1400136f1  cmp     [r8], r13w
0x1400136f5  jz      short loc_140013728
0x1400136f7  inc     rbp
0x1400136fa  cmp     [r8+rbp*2], r13w
0x1400136ff  jnz     short loc_1400136F7
0x140013701  mov     rdx, rsi
0x140013704  lea     r14, ds:2[rbp*2]
0x14001370c  sub     rdx, rbx; DestinationSize
0x14001370f  cmp     rdx, r14
0x140013712  jb      short loc_140013728
0x140013714  mov     r9, r14; SourceSize
0x140013717  mov     rcx, rbx; Destination
0x14001371a  call    memcpy_s
0x14001371f  mov     [rdi+38h], rbx
0x140013723  add     rbx, r14
0x140013726  jmp     short loc_14001372C
0x140013728  mov     [rdi+38h], r13
0x14001372c  sub     rsi, rbx
0x14001372f  xor     edx, edx; Val
0x140013731  mov     r8, rsi; Size
0x140013734  mov     rcx, rbx; void *
0x140013737  call    memset_0
0x14001373c  add     rsp, 28h
0x140013740  pop     r15
0x140013742  pop     r14
0x140013744  pop     r13
0x140013746  pop     r12
0x140013748  pop     rdi
0x140013749  pop     rsi
0x14001374a  pop     rbp
0x14001374b  pop     rbx
0x14001374c  retn
```
