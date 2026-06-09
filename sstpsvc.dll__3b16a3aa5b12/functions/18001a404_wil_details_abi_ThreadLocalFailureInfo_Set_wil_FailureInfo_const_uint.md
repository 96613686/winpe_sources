# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001a404`
- end: `0x18001a53a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001a630`

## callees

- `0x180016fc8`
- `0x180017040`
- `0x1800195a8`
- `0x18001a284`
- `0x18001a2a4`
- `0x18001a404`
- `0x18001bcba`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a4c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a4c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a4b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a4b3`

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
0x18001a404  push    rbx
0x18001a406  push    rbp
0x18001a407  push    rsi
0x18001a408  push    rdi
0x18001a409  push    r12
0x18001a40b  push    r13
0x18001a40d  push    r14
0x18001a40f  push    r15
0x18001a411  sub     rsp, 28h
0x18001a415  mov     [rcx+4], r8d
0x18001a419  lea     r14, [rcx+38h]
0x18001a41d  mov     eax, [rdx+8]
0x18001a420  mov     rsi, rcx
0x18001a423  mov     [rcx+8], eax
0x18001a426  mov     r15, rdx
0x18001a429  mov     qword ptr [rcx+10h], 0
0x18001a431  movzx   eax, word ptr [rdx+40h]
0x18001a435  mov     [rcx+18h], ax
0x18001a439  mov     al, [rdx]
0x18001a43b  mov     [rcx+1Ah], al
0x18001a43e  mov     qword ptr [rcx+20h], 0
0x18001a446  mov     rax, [rdx+88h]
0x18001a44d  mov     [rcx+28h], rax
0x18001a451  mov     rax, [rdx+90h]
0x18001a458  mov     [rcx+30h], rax
0x18001a45c  mov     qword ptr [r14], 0
0x18001a463  mov     rcx, [rdx+18h]; this
0x18001a467  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001a46c  mov     rcx, [r15+38h]; this
0x18001a470  mov     rbp, rax
0x18001a473  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001a478  mov     rcx, [r15+80h]; this
0x18001a47f  add     rbp, rax
0x18001a482  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001a487  add     rbp, rax
0x18001a48a  lea     rdi, [rsi+48h]
0x18001a48e  cmp     qword ptr [rsi+40h], 0
0x18001a493  jz      short loc_18001A49A
0x18001a495  cmp     [rdi], rbp
0x18001a498  jnb     short loc_18001A4D2
0x18001a49a  mov     rdx, rbp; dwBytes
0x18001a49d  mov     ecx, 8; dwFlags
0x18001a4a2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001a4a7  mov     r14, rax
0x18001a4aa  test    rax, rax
0x18001a4ad  jz      short loc_18001A4CE
0x18001a4af  mov     rbx, [rsi+40h]
0x18001a4b3  call    cs:__imp_GetProcessHeap
0x18001a4b9  mov     r8, rbx; lpMem
0x18001a4bc  xor     edx, edx; dwFlags
0x18001a4be  mov     rcx, rax; hHeap
0x18001a4c1  call    cs:__imp_HeapFree
0x18001a4c7  mov     [rsi+40h], r14
0x18001a4cb  mov     [rdi], rbp
0x18001a4ce  lea     r14, [rsi+38h]
0x18001a4d2  mov     rcx, [rsi+40h]; Destination
0x18001a4d6  test    rcx, rcx
0x18001a4d9  jz      short loc_18001A529
0x18001a4db  mov     rbx, [rdi]
0x18001a4de  lea     r9, [rsi+10h]
0x18001a4e2  mov     r8, [r15+38h]
0x18001a4e6  add     rbx, rcx
0x18001a4e9  mov     rdx, rbx
0x18001a4ec  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001a4f1  mov     r8, [r15+80h]
0x18001a4f8  lea     r9, [rsi+20h]
0x18001a4fc  mov     rdx, rbx
0x18001a4ff  mov     rcx, rax; Destination
0x18001a502  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001a507  mov     r8, [r15+18h]
0x18001a50b  mov     r9, r14
0x18001a50e  mov     rdx, rbx
0x18001a511  mov     rcx, rax; Destination
0x18001a514  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18001a519  sub     rbx, rax
0x18001a51c  xor     edx, edx; Val
0x18001a51e  mov     r8, rbx; Size
0x18001a521  mov     rcx, rax; void *
0x18001a524  call    memset_0
0x18001a529  add     rsp, 28h
0x18001a52d  pop     r15
0x18001a52f  pop     r14
0x18001a531  pop     r13
0x18001a533  pop     r12
0x18001a535  pop     rdi
0x18001a536  pop     rsi
0x18001a537  pop     rbp
0x18001a538  pop     rbx
0x18001a539  retn
```
