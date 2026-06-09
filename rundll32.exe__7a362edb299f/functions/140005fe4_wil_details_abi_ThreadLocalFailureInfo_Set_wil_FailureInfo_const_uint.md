# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140005fe4`
- end: `0x1400061fd`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400046f0`

## callees

- `0x140002254`
- `0x1400058a8`
- `0x140005fe4`
- `0x140007708`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400060da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400060da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400060cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400060cc`

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
                memcpy_s_0(v20, v22 - v20, v29, 2 * v3 + 2);
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
          memcpy_s_0(v20, v22 - v20, v26, v27 + 1);
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
      memcpy_s_0(*((void *const *)this + 8), v21, v23, v24 + 1);
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
0x140005fe4  push    rbx
0x140005fe6  push    rbp
0x140005fe7  push    rsi
0x140005fe8  push    rdi
0x140005fe9  push    r12
0x140005feb  push    r13
0x140005fed  push    r14
0x140005fef  push    r15
0x140005ff1  sub     rsp, 28h
0x140005ff5  mov     [rcx+4], r8d
0x140005ff9  xor     r13d, r13d
0x140005ffc  mov     eax, [rdx+8]
0x140005fff  or      rbp, 0FFFFFFFFFFFFFFFFh
0x140006003  mov     [rcx+8], eax
0x140006006  mov     rdi, rcx
0x140006009  mov     [rcx+10h], r13
0x14000600d  mov     r12, rdx
0x140006010  movzx   eax, word ptr [rdx+40h]
0x140006014  mov     [rcx+18h], ax
0x140006018  mov     al, [rdx]
0x14000601a  mov     [rcx+1Ah], al
0x14000601d  mov     [rcx+20h], r13
0x140006021  mov     rax, [rdx+88h]
0x140006028  mov     [rcx+28h], rax
0x14000602c  mov     rax, [rdx+90h]
0x140006033  mov     [rcx+30h], rax
0x140006037  mov     [rcx+38h], r13
0x14000603b  mov     rcx, [rdx+38h]
0x14000603f  lea     edx, [rbp+2]
0x140006042  test    rcx, rcx
0x140006045  jnz     short loc_14000604C
0x140006047  mov     r8d, edx
0x14000604a  jmp     short loc_14000605C
0x14000604c  mov     rax, rbp
0x14000604f  inc     rax
0x140006052  cmp     [rcx+rax], r13b
0x140006056  jnz     short loc_14000604F
0x140006058  lea     r8, [rax+1]; unsigned __int64
0x14000605c  mov     rcx, [r12+80h]
0x140006064  test    rcx, rcx
0x140006067  jz      short loc_140006079
0x140006069  mov     rax, rbp
0x14000606c  inc     rax
0x14000606f  cmp     [rcx+rax], r13b
0x140006073  jnz     short loc_14000606C
0x140006075  lea     rdx, [rax+1]
0x140006079  mov     rcx, [r12+18h]
0x14000607e  test    rcx, rcx
0x140006081  jnz     short loc_140006088
0x140006083  lea     eax, [rcx+2]
0x140006086  jmp     short loc_14000609D
0x140006088  mov     rax, rbp
0x14000608b  inc     rax
0x14000608e  cmp     [rcx+rax*2], r13w
0x140006093  jnz     short loc_14000608B
0x140006095  lea     rax, ds:2[rax*2]
0x14000609d  lea     r14, [rdx+rax]
0x1400060a1  add     r14, r8
0x1400060a4  lea     rsi, [rdi+48h]
0x1400060a8  cmp     [rdi+40h], r13
0x1400060ac  jz      short loc_1400060B3
0x1400060ae  cmp     [rsi], r14
0x1400060b1  jnb     short loc_1400060E7
0x1400060b3  mov     rdx, r14; dwBytes
0x1400060b6  mov     ecx, 8; dwFlags
0x1400060bb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400060c0  mov     r15, rax
0x1400060c3  test    rax, rax
0x1400060c6  jz      short loc_1400060E7
0x1400060c8  mov     rbx, [rdi+40h]
0x1400060cc  call    cs:__imp_GetProcessHeap
0x1400060d2  mov     r8, rbx; lpMem
0x1400060d5  xor     edx, edx; dwFlags
0x1400060d7  mov     rcx, rax; hHeap
0x1400060da  call    cs:__imp_HeapFree
0x1400060e0  mov     [rdi+40h], r15
0x1400060e4  mov     [rsi], r14
0x1400060e7  mov     rbx, [rdi+40h]
0x1400060eb  test    rbx, rbx
0x1400060ee  jz      loc_1400061EC
0x1400060f4  mov     rdx, [rsi]; DestinationSize
0x1400060f7  lea     rsi, [rdx+rbx]
0x1400060fb  cmp     rbx, rsi
0x1400060fe  jz      short loc_14000613E
0x140006100  mov     r8, [r12+38h]; Source
0x140006105  test    r8, r8
0x140006108  jz      short loc_14000613E
0x14000610a  cmp     [r8], r13b
0x14000610d  jz      short loc_14000613E
0x14000610f  mov     rax, rbp
0x140006112  inc     rax
0x140006115  cmp     [r8+rax], r13b
0x140006119  jnz     short loc_140006112
0x14000611b  lea     r14, [rax+1]
0x14000611f  cmp     rdx, r14
0x140006122  jnb     short loc_14000612A
0x140006124  mov     [rdi+10h], r13
0x140006128  jmp     short loc_140006147
0x14000612a  mov     r9, r14; SourceSize
0x14000612d  mov     rcx, rbx; Destination
0x140006130  call    memcpy_s_0
0x140006135  mov     [rdi+10h], rbx
0x140006139  add     rbx, r14
0x14000613c  jmp     short loc_140006142
0x14000613e  mov     [rdi+10h], r13
0x140006142  cmp     rbx, rsi
0x140006145  jz      short loc_14000618E
0x140006147  mov     r8, [r12+80h]; Source
0x14000614f  test    r8, r8
0x140006152  jz      short loc_14000618E
0x140006154  cmp     [r8], r13b
0x140006157  jz      short loc_14000618E
0x140006159  mov     rax, rbp
0x14000615c  inc     rax
0x14000615f  cmp     [r8+rax], r13b
0x140006163  jnz     short loc_14000615C
0x140006165  mov     rdx, rsi
0x140006168  lea     r14, [rax+1]
0x14000616c  sub     rdx, rbx; DestinationSize
0x14000616f  cmp     rdx, r14
0x140006172  jnb     short loc_14000617A
0x140006174  mov     [rdi+20h], r13
0x140006178  jmp     short loc_140006197
0x14000617a  mov     r9, r14; SourceSize
0x14000617d  mov     rcx, rbx; Destination
0x140006180  call    memcpy_s_0
0x140006185  mov     [rdi+20h], rbx
0x140006189  add     rbx, r14
0x14000618c  jmp     short loc_140006192
0x14000618e  mov     [rdi+20h], r13
0x140006192  cmp     rbx, rsi
0x140006195  jz      short loc_1400061D8
0x140006197  mov     r8, [r12+18h]; Source
0x14000619c  test    r8, r8
0x14000619f  jz      short loc_1400061D8
0x1400061a1  cmp     [r8], r13w
0x1400061a5  jz      short loc_1400061D8
0x1400061a7  inc     rbp
0x1400061aa  cmp     [r8+rbp*2], r13w
0x1400061af  jnz     short loc_1400061A7
0x1400061b1  mov     rdx, rsi
0x1400061b4  lea     r14, ds:2[rbp*2]
0x1400061bc  sub     rdx, rbx; DestinationSize
0x1400061bf  cmp     rdx, r14
0x1400061c2  jb      short loc_1400061D8
0x1400061c4  mov     r9, r14; SourceSize
0x1400061c7  mov     rcx, rbx; Destination
0x1400061ca  call    memcpy_s_0
0x1400061cf  mov     [rdi+38h], rbx
0x1400061d3  add     rbx, r14
0x1400061d6  jmp     short loc_1400061DC
0x1400061d8  mov     [rdi+38h], r13
0x1400061dc  sub     rsi, rbx
0x1400061df  xor     edx, edx; Val
0x1400061e1  mov     r8, rsi; Size
0x1400061e4  mov     rcx, rbx; void *
0x1400061e7  call    memset_0
0x1400061ec  add     rsp, 28h
0x1400061f0  pop     r15
0x1400061f2  pop     r14
0x1400061f4  pop     r13
0x1400061f6  pop     r12
0x1400061f8  pop     rdi
0x1400061f9  pop     rsi
0x1400061fa  pop     rbp
0x1400061fb  pop     rbx
0x1400061fc  retn
```
