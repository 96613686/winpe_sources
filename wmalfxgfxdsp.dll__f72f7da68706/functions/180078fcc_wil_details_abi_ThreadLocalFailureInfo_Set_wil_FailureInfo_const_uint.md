# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180078fcc`
- end: `0x18007913c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18007926c`

## callees

- `0x180015e48`
- `0x180015ea8`
- `0x180076790`
- `0x18007892c`
- `0x180078f20`
- `0x180078f40`
- `0x180078fcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079074`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180079074`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079082`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180079082`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v6; // r15
  const char *v7; // rdx
  unsigned __int64 v8; // r15
  const char *v9; // rdx
  SIZE_T v10; // r15
  SIZE_T *v11; // rdi
  LPVOID v12; // r12
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  char *v16; // rdi
  void *v17; // rax
  const unsigned __int16 *v18; // rdx
  char *v19; // rbx
  wil::details *v20; // rcx
  rsize_t v21; // rax
  const void *v22; // rcx
  rsize_t v23; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v8 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v7) + v6;
  v10 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v9) + v8;
  v11 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v11 < v10 )
  {
    v12 = wil::details::ProcessHeapAlloc(8u, v10);
    if ( v12 )
    {
      v13 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)this + 8) = v12;
      *v11 = v10;
    }
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = (void *)wil::details::WriteResultString<char const *>(v15);
    v19 = (char *)wil::details::WriteResultString<char const *>(v17);
    if ( v19 != v16
      && (v20 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v20
      && (v21 = wil::details::ResultStringSize(v20, v18), v23 = v21, v16 - v19 >= v21) )
    {
      memcpy_s(v19, v16 - v19, v22, v21);
      if ( v3 )
        *v3 = v19;
      v19 += v23;
    }
    else if ( v3 )
    {
      *v3 = 0;
    }
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x180078fcc  push    rbx
0x180078fce  push    rbp
0x180078fcf  push    rsi
0x180078fd0  push    rdi
0x180078fd1  push    r12
0x180078fd3  push    r13
0x180078fd5  push    r14
0x180078fd7  push    r15
0x180078fd9  sub     rsp, 28h
0x180078fdd  mov     [rcx+4], r8d
0x180078fe1  lea     rbx, [rcx+20h]
0x180078fe5  mov     eax, [rdx+8]
0x180078fe8  lea     rsi, [rcx+38h]
0x180078fec  mov     [rcx+8], eax
0x180078fef  xor     r12d, r12d
0x180078ff2  mov     [rcx+10h], r12
0x180078ff6  mov     rbp, rcx
0x180078ff9  movzx   eax, word ptr [rdx+40h]
0x180078ffd  mov     r14, rdx
0x180079000  mov     [rcx+18h], ax
0x180079004  mov     al, [rdx]
0x180079006  mov     [rcx+1Ah], al
0x180079009  mov     [rbx], r12
0x18007900c  mov     rax, [rdx+88h]
0x180079013  mov     [rcx+28h], rax
0x180079017  mov     rax, [rdx+90h]
0x18007901e  mov     [rcx+30h], rax
0x180079022  mov     [rsi], r12
0x180079025  mov     rcx, [rdx+18h]; this
0x180079029  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18007902e  mov     rcx, [r14+38h]; this
0x180079032  mov     r15, rax
0x180079035  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18007903a  mov     rcx, [r14+80h]; this
0x180079041  add     r15, rax
0x180079044  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180079049  add     r15, rax
0x18007904c  lea     rdi, [rbp+48h]
0x180079050  cmp     [rbp+40h], r12
0x180079054  jz      short loc_18007905B
0x180079056  cmp     [rdi], r15
0x180079059  jnb     short loc_180079096
0x18007905b  mov     rdx, r15; dwBytes
0x18007905e  mov     ecx, 8; dwFlags
0x180079063  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180079068  mov     r12, rax
0x18007906b  test    rax, rax
0x18007906e  jz      short loc_180079093
0x180079070  mov     rbx, [rbp+40h]
0x180079074  call    cs:__imp_GetProcessHeap
0x18007907a  mov     r8, rbx; lpMem
0x18007907d  xor     edx, edx; dwFlags
0x18007907f  mov     rcx, rax; hHeap
0x180079082  call    cs:__imp_HeapFree
0x180079088  mov     [rbp+40h], r12
0x18007908c  lea     rbx, [rbp+20h]
0x180079090  mov     [rdi], r15
0x180079093  xor     r12d, r12d
0x180079096  mov     rcx, [rbp+40h]; Destination
0x18007909a  test    rcx, rcx
0x18007909d  jz      loc_18007912B
0x1800790a3  mov     rdi, [rdi]
0x1800790a6  lea     r9, [rbp+10h]
0x1800790aa  mov     r8, [r14+38h]
0x1800790ae  add     rdi, rcx
0x1800790b1  mov     rdx, rdi
0x1800790b4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800790b9  mov     r8, [r14+80h]
0x1800790c0  mov     r9, rbx
0x1800790c3  mov     rdx, rdi
0x1800790c6  mov     rcx, rax; Destination
0x1800790c9  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800790ce  mov     rbx, rax
0x1800790d1  cmp     rax, rdi
0x1800790d4  jz      short loc_180079113
0x1800790d6  mov     rcx, [r14+18h]; this
0x1800790da  test    rcx, rcx
0x1800790dd  jz      short loc_180079113
0x1800790df  cmp     [rcx], r12w
0x1800790e3  jz      short loc_180079113
0x1800790e5  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800790ea  mov     rdx, rdi
0x1800790ed  mov     r14, rax
0x1800790f0  sub     rdx, rbx; DestinationSize
0x1800790f3  cmp     rdx, rax
0x1800790f6  jb      short loc_180079113
0x1800790f8  mov     r8, rcx; Source
0x1800790fb  mov     r9, rax; SourceSize
0x1800790fe  mov     rcx, rbx; Destination
0x180079101  call    memcpy_s
0x180079106  test    rsi, rsi
0x180079109  jz      short loc_18007910E
0x18007910b  mov     [rsi], rbx
0x18007910e  add     rbx, r14
0x180079111  jmp     short loc_18007911B
0x180079113  test    rsi, rsi
0x180079116  jz      short loc_18007911B
0x180079118  mov     [rsi], r12
0x18007911b  sub     rdi, rbx
0x18007911e  xor     edx, edx; Val
0x180079120  mov     r8, rdi; Size
0x180079123  mov     rcx, rbx; void *
0x180079126  call    memset_0
0x18007912b  add     rsp, 28h
0x18007912f  pop     r15
0x180079131  pop     r14
0x180079133  pop     r13
0x180079135  pop     r12
0x180079137  pop     rdi
0x180079138  pop     rsi
0x180079139  pop     rbp
0x18007913a  pop     rbx
0x18007913b  retn
```
