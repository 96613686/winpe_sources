# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000b1c4`
- end: `0x18000b307`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b578`

## callees

- `0x18000601c`
- `0x18000713c`
- `0x1800071b4`
- `0x180009e24`
- `0x18000ab38`
- `0x18000ab5c`
- `0x18000b1c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b287`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b287`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b273`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b273`

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
0x18000b1c4  push    rbx
0x18000b1c6  push    rbp
0x18000b1c7  push    rsi
0x18000b1c8  push    rdi
0x18000b1c9  push    r12
0x18000b1cb  push    r13
0x18000b1cd  push    r14
0x18000b1cf  push    r15
0x18000b1d1  sub     rsp, 28h
0x18000b1d5  mov     [rcx+4], r8d
0x18000b1d9  lea     r14, [rcx+38h]
0x18000b1dd  mov     eax, [rdx+8]
0x18000b1e0  mov     rsi, rcx
0x18000b1e3  mov     [rcx+8], eax
0x18000b1e6  mov     r15, rdx
0x18000b1e9  mov     qword ptr [rcx+10h], 0
0x18000b1f1  movzx   eax, word ptr [rdx+40h]
0x18000b1f5  mov     [rcx+18h], ax
0x18000b1f9  mov     al, [rdx]
0x18000b1fb  mov     [rcx+1Ah], al
0x18000b1fe  mov     qword ptr [rcx+20h], 0
0x18000b206  mov     rax, [rdx+88h]
0x18000b20d  mov     [rcx+28h], rax
0x18000b211  mov     rax, [rdx+90h]
0x18000b218  mov     [rcx+30h], rax
0x18000b21c  mov     qword ptr [r14], 0
0x18000b223  mov     rcx, [rdx+18h]; this
0x18000b227  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000b22c  mov     rcx, [r15+38h]; this
0x18000b230  mov     rbp, rax
0x18000b233  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b238  mov     rcx, [r15+80h]; this
0x18000b23f  add     rbp, rax
0x18000b242  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b247  add     rbp, rax
0x18000b24a  lea     rdi, [rsi+48h]
0x18000b24e  cmp     qword ptr [rsi+40h], 0
0x18000b253  jz      short loc_18000B25A
0x18000b255  cmp     [rdi], rbp
0x18000b258  jnb     short loc_18000B29E
0x18000b25a  mov     rdx, rbp; dwBytes
0x18000b25d  mov     ecx, 8; dwFlags
0x18000b262  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b267  mov     r14, rax
0x18000b26a  test    rax, rax
0x18000b26d  jz      short loc_18000B29A
0x18000b26f  mov     rbx, [rsi+40h]
0x18000b273  call    cs:__imp_GetProcessHeap
0x18000b27a  nop     dword ptr [rax+rax+00h]
0x18000b27f  mov     r8, rbx; lpMem
0x18000b282  xor     edx, edx; dwFlags
0x18000b284  mov     rcx, rax; hHeap
0x18000b287  call    cs:__imp_HeapFree
0x18000b28e  nop     dword ptr [rax+rax+00h]
0x18000b293  mov     [rsi+40h], r14
0x18000b297  mov     [rdi], rbp
0x18000b29a  lea     r14, [rsi+38h]
0x18000b29e  mov     rcx, [rsi+40h]; Destination
0x18000b2a2  test    rcx, rcx
0x18000b2a5  jz      short loc_18000B2F5
0x18000b2a7  mov     rbx, [rdi]
0x18000b2aa  lea     r9, [rsi+10h]
0x18000b2ae  mov     r8, [r15+38h]
0x18000b2b2  add     rbx, rcx
0x18000b2b5  mov     rdx, rbx
0x18000b2b8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b2bd  mov     r8, [r15+80h]
0x18000b2c4  lea     r9, [rsi+20h]
0x18000b2c8  mov     rdx, rbx
0x18000b2cb  mov     rcx, rax; Destination
0x18000b2ce  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b2d3  mov     r8, [r15+18h]
0x18000b2d7  mov     r9, r14
0x18000b2da  mov     rdx, rbx
0x18000b2dd  mov     rcx, rax; Destination
0x18000b2e0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000b2e5  sub     rbx, rax
0x18000b2e8  xor     edx, edx; Val
0x18000b2ea  mov     r8, rbx; Size
0x18000b2ed  mov     rcx, rax; void *
0x18000b2f0  call    memset_0
0x18000b2f5  add     rsp, 28h
0x18000b2f9  pop     r15
0x18000b2fb  pop     r14
0x18000b2fd  pop     r13
0x18000b2ff  pop     r12
0x18000b301  pop     rdi
0x18000b302  pop     rsi
0x18000b303  pop     rbp
0x18000b304  pop     rbx
0x18000b305  retn
```
