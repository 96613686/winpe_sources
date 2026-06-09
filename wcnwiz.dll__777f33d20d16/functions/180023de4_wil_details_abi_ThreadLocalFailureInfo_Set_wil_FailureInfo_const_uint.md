# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180023de4`
- end: `0x180023f1a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002417c`

## callees

- `0x180002294`
- `0x180021eec`
- `0x180021f64`
- `0x180023b00`
- `0x180023c68`
- `0x180023c88`
- `0x180023de4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e93`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023ea1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023ea1`

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
0x180023de4  push    rbx
0x180023de6  push    rbp
0x180023de7  push    rsi
0x180023de8  push    rdi
0x180023de9  push    r12
0x180023deb  push    r13
0x180023ded  push    r14
0x180023def  push    r15
0x180023df1  sub     rsp, 28h
0x180023df5  mov     [rcx+4], r8d
0x180023df9  lea     r14, [rcx+38h]
0x180023dfd  mov     eax, [rdx+8]
0x180023e00  mov     rsi, rcx
0x180023e03  mov     [rcx+8], eax
0x180023e06  mov     r15, rdx
0x180023e09  mov     qword ptr [rcx+10h], 0
0x180023e11  movzx   eax, word ptr [rdx+40h]
0x180023e15  mov     [rcx+18h], ax
0x180023e19  mov     al, [rdx]
0x180023e1b  mov     [rcx+1Ah], al
0x180023e1e  mov     qword ptr [rcx+20h], 0
0x180023e26  mov     rax, [rdx+88h]
0x180023e2d  mov     [rcx+28h], rax
0x180023e31  mov     rax, [rdx+90h]
0x180023e38  mov     [rcx+30h], rax
0x180023e3c  mov     qword ptr [r14], 0
0x180023e43  mov     rcx, [rdx+18h]; this
0x180023e47  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180023e4c  mov     rcx, [r15+38h]; this
0x180023e50  mov     rbp, rax
0x180023e53  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180023e58  mov     rcx, [r15+80h]; this
0x180023e5f  add     rbp, rax
0x180023e62  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180023e67  add     rbp, rax
0x180023e6a  lea     rdi, [rsi+48h]
0x180023e6e  cmp     qword ptr [rsi+40h], 0
0x180023e73  jz      short loc_180023E7A
0x180023e75  cmp     [rdi], rbp
0x180023e78  jnb     short loc_180023EB2
0x180023e7a  mov     rdx, rbp; dwBytes
0x180023e7d  mov     ecx, 8; dwFlags
0x180023e82  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180023e87  mov     r14, rax
0x180023e8a  test    rax, rax
0x180023e8d  jz      short loc_180023EAE
0x180023e8f  mov     rbx, [rsi+40h]
0x180023e93  call    cs:__imp_GetProcessHeap
0x180023e99  mov     r8, rbx; lpMem
0x180023e9c  xor     edx, edx; dwFlags
0x180023e9e  mov     rcx, rax; hHeap
0x180023ea1  call    cs:__imp_HeapFree
0x180023ea7  mov     [rsi+40h], r14
0x180023eab  mov     [rdi], rbp
0x180023eae  lea     r14, [rsi+38h]
0x180023eb2  mov     rcx, [rsi+40h]; Destination
0x180023eb6  test    rcx, rcx
0x180023eb9  jz      short loc_180023F09
0x180023ebb  mov     rbx, [rdi]
0x180023ebe  lea     r9, [rsi+10h]
0x180023ec2  mov     r8, [r15+38h]
0x180023ec6  add     rbx, rcx
0x180023ec9  mov     rdx, rbx
0x180023ecc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180023ed1  mov     r8, [r15+80h]
0x180023ed8  lea     r9, [rsi+20h]
0x180023edc  mov     rdx, rbx
0x180023edf  mov     rcx, rax; Destination
0x180023ee2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180023ee7  mov     r8, [r15+18h]
0x180023eeb  mov     r9, r14
0x180023eee  mov     rdx, rbx
0x180023ef1  mov     rcx, rax; Destination
0x180023ef4  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180023ef9  sub     rbx, rax
0x180023efc  xor     edx, edx; Val
0x180023efe  mov     r8, rbx; Size
0x180023f01  mov     rcx, rax; void *
0x180023f04  call    memset_0
0x180023f09  add     rsp, 28h
0x180023f0d  pop     r15
0x180023f0f  pop     r14
0x180023f11  pop     r13
0x180023f13  pop     r12
0x180023f15  pop     rdi
0x180023f16  pop     rsi
0x180023f17  pop     rbp
0x180023f18  pop     rbx
0x180023f19  retn
```
