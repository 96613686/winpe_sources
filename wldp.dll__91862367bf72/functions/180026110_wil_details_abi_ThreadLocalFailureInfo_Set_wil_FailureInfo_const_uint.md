# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180026110`
- end: `0x180026246`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800264a8`

## callees

- `0x180015c00`
- `0x180022a10`
- `0x180024b30`
- `0x180024ba8`
- `0x180026068`
- `0x180026088`
- `0x180026110`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800261cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800261bf`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int64 v5; // rbp
  const char *v6; // rdx
  unsigned __int64 v7; // rbp
  const char *v8; // rdx
  SIZE_T v9; // rbp
  SIZE_T *v10; // rdi
  LPVOID v11; // r14
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  char *v14; // rcx
  char *v15; // rbx
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v8) + v7;
  v10 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v10 < v9 )
  {
    v11 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v11 )
    {
      v12 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      *((_QWORD *)this + 8) = v11;
      *v10 = v9;
    }
  }
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = &v14[*v10];
    v16 = (void *)wil::details::WriteResultString<char const *>(v14);
    v17 = (void *)wil::details::WriteResultString<char const *>(v16);
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x180026110  push    rbx
0x180026112  push    rbp
0x180026113  push    rsi
0x180026114  push    rdi
0x180026115  push    r12
0x180026117  push    r13
0x180026119  push    r14
0x18002611b  push    r15
0x18002611d  sub     rsp, 28h
0x180026121  mov     [rcx+4], r8d
0x180026125  lea     r14, [rcx+38h]
0x180026129  mov     eax, [rdx+8]
0x18002612c  mov     rsi, rcx
0x18002612f  mov     [rcx+8], eax
0x180026132  mov     r15, rdx
0x180026135  mov     qword ptr [rcx+10h], 0
0x18002613d  movzx   eax, word ptr [rdx+40h]
0x180026141  mov     [rcx+18h], ax
0x180026145  mov     al, [rdx]
0x180026147  mov     [rcx+1Ah], al
0x18002614a  mov     qword ptr [rcx+20h], 0
0x180026152  mov     rax, [rdx+88h]
0x180026159  mov     [rcx+28h], rax
0x18002615d  mov     rax, [rdx+90h]
0x180026164  mov     [rcx+30h], rax
0x180026168  mov     qword ptr [r14], 0
0x18002616f  mov     rcx, [rdx+18h]; this
0x180026173  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180026178  mov     rcx, [r15+38h]; this
0x18002617c  mov     rbp, rax
0x18002617f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180026184  mov     rcx, [r15+80h]; this
0x18002618b  add     rbp, rax
0x18002618e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180026193  add     rbp, rax
0x180026196  lea     rdi, [rsi+48h]
0x18002619a  cmp     qword ptr [rsi+40h], 0
0x18002619f  jz      short loc_1800261A6
0x1800261a1  cmp     [rdi], rbp
0x1800261a4  jnb     short loc_1800261DE
0x1800261a6  mov     rdx, rbp; dwBytes
0x1800261a9  mov     ecx, 8; dwFlags
0x1800261ae  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800261b3  mov     r14, rax
0x1800261b6  test    rax, rax
0x1800261b9  jz      short loc_1800261DA
0x1800261bb  mov     rbx, [rsi+40h]
0x1800261bf  call    cs:__imp_GetProcessHeap
0x1800261c5  mov     r8, rbx; lpMem
0x1800261c8  xor     edx, edx; dwFlags
0x1800261ca  mov     rcx, rax; hHeap
0x1800261cd  call    cs:__imp_HeapFree
0x1800261d3  mov     [rsi+40h], r14
0x1800261d7  mov     [rdi], rbp
0x1800261da  lea     r14, [rsi+38h]
0x1800261de  mov     rcx, [rsi+40h]; Destination
0x1800261e2  test    rcx, rcx
0x1800261e5  jz      short loc_180026235
0x1800261e7  mov     rbx, [rdi]
0x1800261ea  lea     r9, [rsi+10h]
0x1800261ee  mov     r8, [r15+38h]
0x1800261f2  add     rbx, rcx
0x1800261f5  mov     rdx, rbx
0x1800261f8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800261fd  mov     r8, [r15+80h]
0x180026204  lea     r9, [rsi+20h]
0x180026208  mov     rdx, rbx
0x18002620b  mov     rcx, rax; Destination
0x18002620e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180026213  mov     r8, [r15+18h]
0x180026217  mov     r9, r14
0x18002621a  mov     rdx, rbx
0x18002621d  mov     rcx, rax; Destination
0x180026220  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180026225  sub     rbx, rax
0x180026228  xor     edx, edx; Val
0x18002622a  mov     r8, rbx; Size
0x18002622d  mov     rcx, rax; void *
0x180026230  call    memset_0
0x180026235  add     rsp, 28h
0x180026239  pop     r15
0x18002623b  pop     r14
0x18002623d  pop     r13
0x18002623f  pop     r12
0x180026241  pop     rdi
0x180026242  pop     rsi
0x180026243  pop     rbp
0x180026244  pop     rbx
0x180026245  retn
```
