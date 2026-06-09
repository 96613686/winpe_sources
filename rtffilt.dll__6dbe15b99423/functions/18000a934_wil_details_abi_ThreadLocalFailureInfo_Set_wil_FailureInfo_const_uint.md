# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a934`
- end: `0x18000ab4d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006760`

## callees

- `0x1800028b4`
- `0x180007d28`
- `0x18000a934`
- `0x18000d1bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aa1c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aa2a`

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
0x18000a934  push    rbx
0x18000a936  push    rbp
0x18000a937  push    rsi
0x18000a938  push    rdi
0x18000a939  push    r12
0x18000a93b  push    r13
0x18000a93d  push    r14
0x18000a93f  push    r15
0x18000a941  sub     rsp, 28h
0x18000a945  mov     [rcx+4], r8d
0x18000a949  xor     r13d, r13d
0x18000a94c  mov     eax, [rdx+8]
0x18000a94f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000a953  mov     [rcx+8], eax
0x18000a956  mov     rdi, rcx
0x18000a959  mov     [rcx+10h], r13
0x18000a95d  mov     r12, rdx
0x18000a960  movzx   eax, word ptr [rdx+40h]
0x18000a964  mov     [rcx+18h], ax
0x18000a968  mov     al, [rdx]
0x18000a96a  mov     [rcx+1Ah], al
0x18000a96d  mov     [rcx+20h], r13
0x18000a971  mov     rax, [rdx+88h]
0x18000a978  mov     [rcx+28h], rax
0x18000a97c  mov     rax, [rdx+90h]
0x18000a983  mov     [rcx+30h], rax
0x18000a987  mov     [rcx+38h], r13
0x18000a98b  mov     rcx, [rdx+38h]
0x18000a98f  lea     edx, [rbp+2]
0x18000a992  test    rcx, rcx
0x18000a995  jnz     short loc_18000A99C
0x18000a997  mov     r8d, edx
0x18000a99a  jmp     short loc_18000A9AC
0x18000a99c  mov     rax, rbp
0x18000a99f  inc     rax
0x18000a9a2  cmp     [rcx+rax], r13b
0x18000a9a6  jnz     short loc_18000A99F
0x18000a9a8  lea     r8, [rax+1]; unsigned __int64
0x18000a9ac  mov     rcx, [r12+80h]
0x18000a9b4  test    rcx, rcx
0x18000a9b7  jz      short loc_18000A9C9
0x18000a9b9  mov     rax, rbp
0x18000a9bc  inc     rax
0x18000a9bf  cmp     [rcx+rax], r13b
0x18000a9c3  jnz     short loc_18000A9BC
0x18000a9c5  lea     rdx, [rax+1]
0x18000a9c9  mov     rcx, [r12+18h]
0x18000a9ce  test    rcx, rcx
0x18000a9d1  jnz     short loc_18000A9D8
0x18000a9d3  lea     eax, [rcx+2]
0x18000a9d6  jmp     short loc_18000A9ED
0x18000a9d8  mov     rax, rbp
0x18000a9db  inc     rax
0x18000a9de  cmp     [rcx+rax*2], r13w
0x18000a9e3  jnz     short loc_18000A9DB
0x18000a9e5  lea     rax, ds:2[rax*2]
0x18000a9ed  lea     r14, [rdx+rax]
0x18000a9f1  add     r14, r8
0x18000a9f4  lea     rsi, [rdi+48h]
0x18000a9f8  cmp     [rdi+40h], r13
0x18000a9fc  jz      short loc_18000AA03
0x18000a9fe  cmp     [rsi], r14
0x18000aa01  jnb     short loc_18000AA37
0x18000aa03  mov     rdx, r14; dwBytes
0x18000aa06  mov     ecx, 8; dwFlags
0x18000aa0b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000aa10  mov     r15, rax
0x18000aa13  test    rax, rax
0x18000aa16  jz      short loc_18000AA37
0x18000aa18  mov     rbx, [rdi+40h]
0x18000aa1c  call    cs:__imp_GetProcessHeap
0x18000aa22  mov     r8, rbx; lpMem
0x18000aa25  xor     edx, edx; dwFlags
0x18000aa27  mov     rcx, rax; hHeap
0x18000aa2a  call    cs:__imp_HeapFree
0x18000aa30  mov     [rdi+40h], r15
0x18000aa34  mov     [rsi], r14
0x18000aa37  mov     rbx, [rdi+40h]
0x18000aa3b  test    rbx, rbx
0x18000aa3e  jz      loc_18000AB3C
0x18000aa44  mov     rdx, [rsi]; DestinationSize
0x18000aa47  lea     rsi, [rdx+rbx]
0x18000aa4b  cmp     rbx, rsi
0x18000aa4e  jz      short loc_18000AA8E
0x18000aa50  mov     r8, [r12+38h]; Source
0x18000aa55  test    r8, r8
0x18000aa58  jz      short loc_18000AA8E
0x18000aa5a  cmp     [r8], r13b
0x18000aa5d  jz      short loc_18000AA8E
0x18000aa5f  mov     rax, rbp
0x18000aa62  inc     rax
0x18000aa65  cmp     [r8+rax], r13b
0x18000aa69  jnz     short loc_18000AA62
0x18000aa6b  lea     r14, [rax+1]
0x18000aa6f  cmp     rdx, r14
0x18000aa72  jnb     short loc_18000AA7A
0x18000aa74  mov     [rdi+10h], r13
0x18000aa78  jmp     short loc_18000AA97
0x18000aa7a  mov     r9, r14; SourceSize
0x18000aa7d  mov     rcx, rbx; Destination
0x18000aa80  call    memcpy_s
0x18000aa85  mov     [rdi+10h], rbx
0x18000aa89  add     rbx, r14
0x18000aa8c  jmp     short loc_18000AA92
0x18000aa8e  mov     [rdi+10h], r13
0x18000aa92  cmp     rbx, rsi
0x18000aa95  jz      short loc_18000AADE
0x18000aa97  mov     r8, [r12+80h]; Source
0x18000aa9f  test    r8, r8
0x18000aaa2  jz      short loc_18000AADE
0x18000aaa4  cmp     [r8], r13b
0x18000aaa7  jz      short loc_18000AADE
0x18000aaa9  mov     rax, rbp
0x18000aaac  inc     rax
0x18000aaaf  cmp     [r8+rax], r13b
0x18000aab3  jnz     short loc_18000AAAC
0x18000aab5  mov     rdx, rsi
0x18000aab8  lea     r14, [rax+1]
0x18000aabc  sub     rdx, rbx; DestinationSize
0x18000aabf  cmp     rdx, r14
0x18000aac2  jnb     short loc_18000AACA
0x18000aac4  mov     [rdi+20h], r13
0x18000aac8  jmp     short loc_18000AAE7
0x18000aaca  mov     r9, r14; SourceSize
0x18000aacd  mov     rcx, rbx; Destination
0x18000aad0  call    memcpy_s
0x18000aad5  mov     [rdi+20h], rbx
0x18000aad9  add     rbx, r14
0x18000aadc  jmp     short loc_18000AAE2
0x18000aade  mov     [rdi+20h], r13
0x18000aae2  cmp     rbx, rsi
0x18000aae5  jz      short loc_18000AB28
0x18000aae7  mov     r8, [r12+18h]; Source
0x18000aaec  test    r8, r8
0x18000aaef  jz      short loc_18000AB28
0x18000aaf1  cmp     [r8], r13w
0x18000aaf5  jz      short loc_18000AB28
0x18000aaf7  inc     rbp
0x18000aafa  cmp     [r8+rbp*2], r13w
0x18000aaff  jnz     short loc_18000AAF7
0x18000ab01  mov     rdx, rsi
0x18000ab04  lea     r14, ds:2[rbp*2]
0x18000ab0c  sub     rdx, rbx; DestinationSize
0x18000ab0f  cmp     rdx, r14
0x18000ab12  jb      short loc_18000AB28
0x18000ab14  mov     r9, r14; SourceSize
0x18000ab17  mov     rcx, rbx; Destination
0x18000ab1a  call    memcpy_s
0x18000ab1f  mov     [rdi+38h], rbx
0x18000ab23  add     rbx, r14
0x18000ab26  jmp     short loc_18000AB2C
0x18000ab28  mov     [rdi+38h], r13
0x18000ab2c  sub     rsi, rbx
0x18000ab2f  xor     edx, edx; Val
0x18000ab31  mov     r8, rsi; Size
0x18000ab34  mov     rcx, rbx; void *
0x18000ab37  call    memset_0
0x18000ab3c  add     rsp, 28h
0x18000ab40  pop     r15
0x18000ab42  pop     r14
0x18000ab44  pop     r13
0x18000ab46  pop     r12
0x18000ab48  pop     rdi
0x18000ab49  pop     rsi
0x18000ab4a  pop     rbp
0x18000ab4b  pop     rbx
0x18000ab4c  retn
```
