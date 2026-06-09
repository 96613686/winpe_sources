# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800498b8`
- end: `0x180049a3c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `388`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180049a44`

## callees

- `0x180033f7c`
- `0x180048060`
- `0x180049814`
- `0x180049838`
- `0x1800498b8`
- `0x180079436`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800499f9`
- `msvcrt!memcpy_s` at `0x1800499f9`
- `KERNEL32!GetProcessHeap` at `0x180049960`
- `KERNEL32!GetProcessHeap` at `0x180049960`
- `KERNEL32!HeapFree` at `0x180049974`
- `KERNEL32!HeapFree` at `0x180049974`

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
0x1800498b8  push    rbx
0x1800498ba  push    rbp
0x1800498bb  push    rsi
0x1800498bc  push    rdi
0x1800498bd  push    r12
0x1800498bf  push    r13
0x1800498c1  push    r14
0x1800498c3  push    r15
0x1800498c5  sub     rsp, 28h
0x1800498c9  mov     [rcx+4], r8d
0x1800498cd  lea     rbx, [rcx+20h]
0x1800498d1  mov     eax, [rdx+8]
0x1800498d4  lea     rsi, [rcx+38h]
0x1800498d8  mov     [rcx+8], eax
0x1800498db  xor     r12d, r12d
0x1800498de  mov     [rcx+10h], r12
0x1800498e2  mov     rbp, rcx
0x1800498e5  movzx   eax, word ptr [rdx+40h]
0x1800498e9  mov     r14, rdx
0x1800498ec  mov     [rcx+18h], ax
0x1800498f0  mov     al, [rdx]
0x1800498f2  mov     [rcx+1Ah], al
0x1800498f5  mov     [rbx], r12
0x1800498f8  mov     rax, [rdx+88h]
0x1800498ff  mov     [rcx+28h], rax
0x180049903  mov     rax, [rdx+90h]
0x18004990a  mov     [rcx+30h], rax
0x18004990e  mov     [rsi], r12
0x180049911  mov     rcx, [rdx+18h]; this
0x180049915  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18004991a  mov     rcx, [r14+38h]; this
0x18004991e  mov     r15, rax
0x180049921  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180049926  mov     rcx, [r14+80h]; this
0x18004992d  add     r15, rax
0x180049930  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180049935  add     r15, rax
0x180049938  lea     rdi, [rbp+48h]
0x18004993c  cmp     [rbp+40h], r12
0x180049940  jz      short loc_180049947
0x180049942  cmp     [rdi], r15
0x180049945  jnb     short loc_18004998E
0x180049947  mov     rdx, r15; dwBytes
0x18004994a  mov     ecx, 8; dwFlags
0x18004994f  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180049954  mov     r12, rax
0x180049957  test    rax, rax
0x18004995a  jz      short loc_18004998B
0x18004995c  mov     rbx, [rbp+40h]
0x180049960  call    cs:__imp_GetProcessHeap
0x180049967  nop     dword ptr [rax+rax+00h]
0x18004996c  mov     r8, rbx; lpMem
0x18004996f  xor     edx, edx; dwFlags
0x180049971  mov     rcx, rax; hHeap
0x180049974  call    cs:__imp_HeapFree
0x18004997b  nop     dword ptr [rax+rax+00h]
0x180049980  mov     [rbp+40h], r12
0x180049984  lea     rbx, [rbp+20h]
0x180049988  mov     [rdi], r15
0x18004998b  xor     r12d, r12d
0x18004998e  mov     rcx, [rbp+40h]; Destination
0x180049992  test    rcx, rcx
0x180049995  jz      loc_180049A2A
0x18004999b  mov     rdi, [rdi]
0x18004999e  lea     r9, [rbp+10h]
0x1800499a2  mov     r8, [r14+38h]
0x1800499a6  add     rdi, rcx
0x1800499a9  mov     rdx, rdi
0x1800499ac  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800499b1  mov     r8, [r14+80h]
0x1800499b8  mov     r9, rbx
0x1800499bb  mov     rdx, rdi
0x1800499be  mov     rcx, rax; Destination
0x1800499c1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800499c6  mov     rbx, rax
0x1800499c9  cmp     rax, rdi
0x1800499cc  jz      short loc_180049A12
0x1800499ce  mov     rcx, [r14+18h]; this
0x1800499d2  test    rcx, rcx
0x1800499d5  jz      short loc_180049A12
0x1800499d7  cmp     [rcx], r12w
0x1800499db  jz      short loc_180049A12
0x1800499dd  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800499e2  mov     rdx, rdi
0x1800499e5  mov     r14, rax
0x1800499e8  sub     rdx, rbx; DestinationSize
0x1800499eb  cmp     rdx, rax
0x1800499ee  jb      short loc_180049A12
0x1800499f0  mov     r8, rcx; Source
0x1800499f3  mov     r9, rax; SourceSize
0x1800499f6  mov     rcx, rbx; Destination
0x1800499f9  call    cs:__imp_memcpy_s
0x180049a00  nop     dword ptr [rax+rax+00h]
0x180049a05  test    rsi, rsi
0x180049a08  jz      short loc_180049A0D
0x180049a0a  mov     [rsi], rbx
0x180049a0d  add     rbx, r14
0x180049a10  jmp     short loc_180049A1A
0x180049a12  test    rsi, rsi
0x180049a15  jz      short loc_180049A1A
0x180049a17  mov     [rsi], r12
0x180049a1a  sub     rdi, rbx
0x180049a1d  xor     edx, edx; Val
0x180049a1f  mov     r8, rdi; Size
0x180049a22  mov     rcx, rbx; void *
0x180049a25  call    memset_0
0x180049a2a  add     rsp, 28h
0x180049a2e  pop     r15
0x180049a30  pop     r14
0x180049a32  pop     r13
0x180049a34  pop     r12
0x180049a36  pop     rdi
0x180049a37  pop     rsi
0x180049a38  pop     rbp
0x180049a39  pop     rbx
0x180049a3a  retn
```
