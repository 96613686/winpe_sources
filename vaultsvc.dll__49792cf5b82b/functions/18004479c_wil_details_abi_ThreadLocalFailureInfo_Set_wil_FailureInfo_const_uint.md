# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18004479c`
- end: `0x1800448d2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180044b34`

## callees

- `0x18003af10`
- `0x1800427d4`
- `0x18004284c`
- `0x1800442d8`
- `0x1800446d0`
- `0x1800446f0`
- `0x18004479c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004484b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004484b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044859`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180044859`

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
0x18004479c  push    rbx
0x18004479e  push    rbp
0x18004479f  push    rsi
0x1800447a0  push    rdi
0x1800447a1  push    r12
0x1800447a3  push    r13
0x1800447a5  push    r14
0x1800447a7  push    r15
0x1800447a9  sub     rsp, 28h
0x1800447ad  mov     [rcx+4], r8d
0x1800447b1  lea     r14, [rcx+38h]
0x1800447b5  mov     eax, [rdx+8]
0x1800447b8  mov     rsi, rcx
0x1800447bb  mov     [rcx+8], eax
0x1800447be  mov     r15, rdx
0x1800447c1  mov     qword ptr [rcx+10h], 0
0x1800447c9  movzx   eax, word ptr [rdx+40h]
0x1800447cd  mov     [rcx+18h], ax
0x1800447d1  mov     al, [rdx]
0x1800447d3  mov     [rcx+1Ah], al
0x1800447d6  mov     qword ptr [rcx+20h], 0
0x1800447de  mov     rax, [rdx+88h]
0x1800447e5  mov     [rcx+28h], rax
0x1800447e9  mov     rax, [rdx+90h]
0x1800447f0  mov     [rcx+30h], rax
0x1800447f4  mov     qword ptr [r14], 0
0x1800447fb  mov     rcx, [rdx+18h]; this
0x1800447ff  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180044804  mov     rcx, [r15+38h]; this
0x180044808  mov     rbp, rax
0x18004480b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180044810  mov     rcx, [r15+80h]; this
0x180044817  add     rbp, rax
0x18004481a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18004481f  add     rbp, rax
0x180044822  lea     rdi, [rsi+48h]
0x180044826  cmp     qword ptr [rsi+40h], 0
0x18004482b  jz      short loc_180044832
0x18004482d  cmp     [rdi], rbp
0x180044830  jnb     short loc_18004486A
0x180044832  mov     rdx, rbp; dwBytes
0x180044835  mov     ecx, 8; dwFlags
0x18004483a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18004483f  mov     r14, rax
0x180044842  test    rax, rax
0x180044845  jz      short loc_180044866
0x180044847  mov     rbx, [rsi+40h]
0x18004484b  call    cs:__imp_GetProcessHeap
0x180044851  mov     r8, rbx; lpMem
0x180044854  xor     edx, edx; dwFlags
0x180044856  mov     rcx, rax; hHeap
0x180044859  call    cs:__imp_HeapFree
0x18004485f  mov     [rsi+40h], r14
0x180044863  mov     [rdi], rbp
0x180044866  lea     r14, [rsi+38h]
0x18004486a  mov     rcx, [rsi+40h]; Destination
0x18004486e  test    rcx, rcx
0x180044871  jz      short loc_1800448C1
0x180044873  mov     rbx, [rdi]
0x180044876  lea     r9, [rsi+10h]
0x18004487a  mov     r8, [r15+38h]
0x18004487e  add     rbx, rcx
0x180044881  mov     rdx, rbx
0x180044884  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180044889  mov     r8, [r15+80h]
0x180044890  lea     r9, [rsi+20h]
0x180044894  mov     rdx, rbx
0x180044897  mov     rcx, rax; Destination
0x18004489a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18004489f  mov     r8, [r15+18h]
0x1800448a3  mov     r9, r14
0x1800448a6  mov     rdx, rbx
0x1800448a9  mov     rcx, rax; Destination
0x1800448ac  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800448b1  sub     rbx, rax
0x1800448b4  xor     edx, edx; Val
0x1800448b6  mov     r8, rbx; Size
0x1800448b9  mov     rcx, rax; void *
0x1800448bc  call    memset_0
0x1800448c1  add     rsp, 28h
0x1800448c5  pop     r15
0x1800448c7  pop     r14
0x1800448c9  pop     r13
0x1800448cb  pop     r12
0x1800448cd  pop     rdi
0x1800448ce  pop     rsi
0x1800448cf  pop     rbp
0x1800448d0  pop     rbx
0x1800448d1  retn
```
