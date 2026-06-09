# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180025aec`
- end: `0x180025c22`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025e88`

## callees

- `0x180023a6c`
- `0x180023ae4`
- `0x18002551c`
- `0x180025a1c`
- `0x180025a3c`
- `0x180025aec`
- `0x18002a566`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180025ba9`
- `KERNEL32!HeapFree` at `0x180025ba9`
- `KERNEL32!GetProcessHeap` at `0x180025b9b`
- `KERNEL32!GetProcessHeap` at `0x180025b9b`

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
0x180025aec  push    rbx
0x180025aee  push    rbp
0x180025aef  push    rsi
0x180025af0  push    rdi
0x180025af1  push    r12
0x180025af3  push    r13
0x180025af5  push    r14
0x180025af7  push    r15
0x180025af9  sub     rsp, 28h
0x180025afd  mov     [rcx+4], r8d
0x180025b01  lea     r14, [rcx+38h]
0x180025b05  mov     eax, [rdx+8]
0x180025b08  mov     rsi, rcx
0x180025b0b  mov     [rcx+8], eax
0x180025b0e  mov     r15, rdx
0x180025b11  mov     qword ptr [rcx+10h], 0
0x180025b19  movzx   eax, word ptr [rdx+40h]
0x180025b1d  mov     [rcx+18h], ax
0x180025b21  mov     al, [rdx]
0x180025b23  mov     [rcx+1Ah], al
0x180025b26  mov     qword ptr [rcx+20h], 0
0x180025b2e  mov     rax, [rdx+88h]
0x180025b35  mov     [rcx+28h], rax
0x180025b39  mov     rax, [rdx+90h]
0x180025b40  mov     [rcx+30h], rax
0x180025b44  mov     qword ptr [r14], 0
0x180025b4b  mov     rcx, [rdx+18h]; this
0x180025b4f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180025b54  mov     rcx, [r15+38h]; this
0x180025b58  mov     rbp, rax
0x180025b5b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180025b60  mov     rcx, [r15+80h]; this
0x180025b67  add     rbp, rax
0x180025b6a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180025b6f  add     rbp, rax
0x180025b72  lea     rdi, [rsi+48h]
0x180025b76  cmp     qword ptr [rsi+40h], 0
0x180025b7b  jz      short loc_180025B82
0x180025b7d  cmp     [rdi], rbp
0x180025b80  jnb     short loc_180025BBA
0x180025b82  mov     rdx, rbp; dwBytes
0x180025b85  mov     ecx, 8; dwFlags
0x180025b8a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180025b8f  mov     r14, rax
0x180025b92  test    rax, rax
0x180025b95  jz      short loc_180025BB6
0x180025b97  mov     rbx, [rsi+40h]
0x180025b9b  call    cs:__imp_GetProcessHeap
0x180025ba1  mov     r8, rbx; lpMem
0x180025ba4  xor     edx, edx; dwFlags
0x180025ba6  mov     rcx, rax; hHeap
0x180025ba9  call    cs:__imp_HeapFree
0x180025baf  mov     [rsi+40h], r14
0x180025bb3  mov     [rdi], rbp
0x180025bb6  lea     r14, [rsi+38h]
0x180025bba  mov     rcx, [rsi+40h]; Destination
0x180025bbe  test    rcx, rcx
0x180025bc1  jz      short loc_180025C11
0x180025bc3  mov     rbx, [rdi]
0x180025bc6  lea     r9, [rsi+10h]
0x180025bca  mov     r8, [r15+38h]
0x180025bce  add     rbx, rcx
0x180025bd1  mov     rdx, rbx
0x180025bd4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180025bd9  mov     r8, [r15+80h]
0x180025be0  lea     r9, [rsi+20h]
0x180025be4  mov     rdx, rbx
0x180025be7  mov     rcx, rax; Destination
0x180025bea  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180025bef  mov     r8, [r15+18h]
0x180025bf3  mov     r9, r14
0x180025bf6  mov     rdx, rbx
0x180025bf9  mov     rcx, rax; Destination
0x180025bfc  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180025c01  sub     rbx, rax
0x180025c04  xor     edx, edx; Val
0x180025c06  mov     r8, rbx; Size
0x180025c09  mov     rcx, rax; void *
0x180025c0c  call    memset_0
0x180025c11  add     rsp, 28h
0x180025c15  pop     r15
0x180025c17  pop     r14
0x180025c19  pop     r13
0x180025c1b  pop     r12
0x180025c1d  pop     rdi
0x180025c1e  pop     rsi
0x180025c1f  pop     rbp
0x180025c20  pop     rbx
0x180025c21  retn
```
