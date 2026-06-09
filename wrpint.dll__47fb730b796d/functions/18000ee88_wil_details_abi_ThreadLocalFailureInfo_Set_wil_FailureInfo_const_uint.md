# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000ee88`
- end: `0x18000f0a1`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `537`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c8a0`

## callees

- `0x18000da6c`
- `0x18000ee88`
- `0x180011764`
- `0x18001b77a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ef7e`

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
0x18000ee88  push    rbx
0x18000ee8a  push    rbp
0x18000ee8b  push    rsi
0x18000ee8c  push    rdi
0x18000ee8d  push    r12
0x18000ee8f  push    r13
0x18000ee91  push    r14
0x18000ee93  push    r15
0x18000ee95  sub     rsp, 28h
0x18000ee99  mov     [rcx+4], r8d
0x18000ee9d  xor     r13d, r13d
0x18000eea0  mov     eax, [rdx+8]
0x18000eea3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000eea7  mov     [rcx+8], eax
0x18000eeaa  mov     rdi, rcx
0x18000eead  mov     [rcx+10h], r13
0x18000eeb1  mov     r12, rdx
0x18000eeb4  movzx   eax, word ptr [rdx+40h]
0x18000eeb8  mov     [rcx+18h], ax
0x18000eebc  mov     al, [rdx]
0x18000eebe  mov     [rcx+1Ah], al
0x18000eec1  mov     [rcx+20h], r13
0x18000eec5  mov     rax, [rdx+88h]
0x18000eecc  mov     [rcx+28h], rax
0x18000eed0  mov     rax, [rdx+90h]
0x18000eed7  mov     [rcx+30h], rax
0x18000eedb  mov     [rcx+38h], r13
0x18000eedf  mov     rcx, [rdx+38h]
0x18000eee3  lea     edx, [rbp+2]
0x18000eee6  test    rcx, rcx
0x18000eee9  jnz     short loc_18000EEF0
0x18000eeeb  mov     r8d, edx
0x18000eeee  jmp     short loc_18000EF00
0x18000eef0  mov     rax, rbp
0x18000eef3  inc     rax
0x18000eef6  cmp     [rcx+rax], r13b
0x18000eefa  jnz     short loc_18000EEF3
0x18000eefc  lea     r8, [rax+1]; unsigned __int64
0x18000ef00  mov     rcx, [r12+80h]
0x18000ef08  test    rcx, rcx
0x18000ef0b  jz      short loc_18000EF1D
0x18000ef0d  mov     rax, rbp
0x18000ef10  inc     rax
0x18000ef13  cmp     [rcx+rax], r13b
0x18000ef17  jnz     short loc_18000EF10
0x18000ef19  lea     rdx, [rax+1]
0x18000ef1d  mov     rcx, [r12+18h]
0x18000ef22  test    rcx, rcx
0x18000ef25  jnz     short loc_18000EF2C
0x18000ef27  lea     eax, [rcx+2]
0x18000ef2a  jmp     short loc_18000EF41
0x18000ef2c  mov     rax, rbp
0x18000ef2f  inc     rax
0x18000ef32  cmp     [rcx+rax*2], r13w
0x18000ef37  jnz     short loc_18000EF2F
0x18000ef39  lea     rax, ds:2[rax*2]
0x18000ef41  lea     r14, [rdx+rax]
0x18000ef45  add     r14, r8
0x18000ef48  lea     rsi, [rdi+48h]
0x18000ef4c  cmp     [rdi+40h], r13
0x18000ef50  jz      short loc_18000EF57
0x18000ef52  cmp     [rsi], r14
0x18000ef55  jnb     short loc_18000EF8B
0x18000ef57  mov     rdx, r14; dwBytes
0x18000ef5a  mov     ecx, 8; dwFlags
0x18000ef5f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ef64  mov     r15, rax
0x18000ef67  test    rax, rax
0x18000ef6a  jz      short loc_18000EF8B
0x18000ef6c  mov     rbx, [rdi+40h]
0x18000ef70  call    cs:__imp_GetProcessHeap
0x18000ef76  mov     r8, rbx; lpMem
0x18000ef79  xor     edx, edx; dwFlags
0x18000ef7b  mov     rcx, rax; hHeap
0x18000ef7e  call    cs:__imp_HeapFree
0x18000ef84  mov     [rdi+40h], r15
0x18000ef88  mov     [rsi], r14
0x18000ef8b  mov     rbx, [rdi+40h]
0x18000ef8f  test    rbx, rbx
0x18000ef92  jz      loc_18000F090
0x18000ef98  mov     rdx, [rsi]; DestinationSize
0x18000ef9b  lea     rsi, [rdx+rbx]
0x18000ef9f  cmp     rbx, rsi
0x18000efa2  jz      short loc_18000EFE2
0x18000efa4  mov     r8, [r12+38h]; Source
0x18000efa9  test    r8, r8
0x18000efac  jz      short loc_18000EFE2
0x18000efae  cmp     [r8], r13b
0x18000efb1  jz      short loc_18000EFE2
0x18000efb3  mov     rax, rbp
0x18000efb6  inc     rax
0x18000efb9  cmp     [r8+rax], r13b
0x18000efbd  jnz     short loc_18000EFB6
0x18000efbf  lea     r14, [rax+1]
0x18000efc3  cmp     rdx, r14
0x18000efc6  jnb     short loc_18000EFCE
0x18000efc8  mov     [rdi+10h], r13
0x18000efcc  jmp     short loc_18000EFEB
0x18000efce  mov     r9, r14; SourceSize
0x18000efd1  mov     rcx, rbx; Destination
0x18000efd4  call    memcpy_s_0
0x18000efd9  mov     [rdi+10h], rbx
0x18000efdd  add     rbx, r14
0x18000efe0  jmp     short loc_18000EFE6
0x18000efe2  mov     [rdi+10h], r13
0x18000efe6  cmp     rbx, rsi
0x18000efe9  jz      short loc_18000F032
0x18000efeb  mov     r8, [r12+80h]; Source
0x18000eff3  test    r8, r8
0x18000eff6  jz      short loc_18000F032
0x18000eff8  cmp     [r8], r13b
0x18000effb  jz      short loc_18000F032
0x18000effd  mov     rax, rbp
0x18000f000  inc     rax
0x18000f003  cmp     [r8+rax], r13b
0x18000f007  jnz     short loc_18000F000
0x18000f009  mov     rdx, rsi
0x18000f00c  lea     r14, [rax+1]
0x18000f010  sub     rdx, rbx; DestinationSize
0x18000f013  cmp     rdx, r14
0x18000f016  jnb     short loc_18000F01E
0x18000f018  mov     [rdi+20h], r13
0x18000f01c  jmp     short loc_18000F03B
0x18000f01e  mov     r9, r14; SourceSize
0x18000f021  mov     rcx, rbx; Destination
0x18000f024  call    memcpy_s_0
0x18000f029  mov     [rdi+20h], rbx
0x18000f02d  add     rbx, r14
0x18000f030  jmp     short loc_18000F036
0x18000f032  mov     [rdi+20h], r13
0x18000f036  cmp     rbx, rsi
0x18000f039  jz      short loc_18000F07C
0x18000f03b  mov     r8, [r12+18h]; Source
0x18000f040  test    r8, r8
0x18000f043  jz      short loc_18000F07C
0x18000f045  cmp     [r8], r13w
0x18000f049  jz      short loc_18000F07C
0x18000f04b  inc     rbp
0x18000f04e  cmp     [r8+rbp*2], r13w
0x18000f053  jnz     short loc_18000F04B
0x18000f055  mov     rdx, rsi
0x18000f058  lea     r14, ds:2[rbp*2]
0x18000f060  sub     rdx, rbx; DestinationSize
0x18000f063  cmp     rdx, r14
0x18000f066  jb      short loc_18000F07C
0x18000f068  mov     r9, r14; SourceSize
0x18000f06b  mov     rcx, rbx; Destination
0x18000f06e  call    memcpy_s_0
0x18000f073  mov     [rdi+38h], rbx
0x18000f077  add     rbx, r14
0x18000f07a  jmp     short loc_18000F080
0x18000f07c  mov     [rdi+38h], r13
0x18000f080  sub     rsi, rbx
0x18000f083  xor     edx, edx; Val
0x18000f085  mov     r8, rsi; Size
0x18000f088  mov     rcx, rbx; void *
0x18000f08b  call    memset_0
0x18000f090  add     rsp, 28h
0x18000f094  pop     r15
0x18000f096  pop     r14
0x18000f098  pop     r13
0x18000f09a  pop     r12
0x18000f09c  pop     rdi
0x18000f09d  pop     rsi
0x18000f09e  pop     rbp
0x18000f09f  pop     rbx
0x18000f0a0  retn
```
