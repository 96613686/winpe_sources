# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007dd4`
- end: `0x180007f0a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000834c`

## callees

- `0x180004c4c`
- `0x180004cc4`
- `0x180007838`
- `0x180007cbc`
- `0x180007cdc`
- `0x180007dd4`
- `0x180028f2e`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007e83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007e91`

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
0x180007dd4  push    rbx
0x180007dd6  push    rbp
0x180007dd7  push    rsi
0x180007dd8  push    rdi
0x180007dd9  push    r12
0x180007ddb  push    r13
0x180007ddd  push    r14
0x180007ddf  push    r15
0x180007de1  sub     rsp, 28h
0x180007de5  mov     [rcx+4], r8d
0x180007de9  lea     r14, [rcx+38h]
0x180007ded  mov     eax, [rdx+8]
0x180007df0  mov     rsi, rcx
0x180007df3  mov     [rcx+8], eax
0x180007df6  mov     r15, rdx
0x180007df9  mov     qword ptr [rcx+10h], 0
0x180007e01  movzx   eax, word ptr [rdx+40h]
0x180007e05  mov     [rcx+18h], ax
0x180007e09  mov     al, [rdx]
0x180007e0b  mov     [rcx+1Ah], al
0x180007e0e  mov     qword ptr [rcx+20h], 0
0x180007e16  mov     rax, [rdx+88h]
0x180007e1d  mov     [rcx+28h], rax
0x180007e21  mov     rax, [rdx+90h]
0x180007e28  mov     [rcx+30h], rax
0x180007e2c  mov     qword ptr [r14], 0
0x180007e33  mov     rcx, [rdx+18h]; this
0x180007e37  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180007e3c  mov     rcx, [r15+38h]; this
0x180007e40  mov     rbp, rax
0x180007e43  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007e48  mov     rcx, [r15+80h]; this
0x180007e4f  add     rbp, rax
0x180007e52  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007e57  add     rbp, rax
0x180007e5a  lea     rdi, [rsi+48h]
0x180007e5e  cmp     qword ptr [rsi+40h], 0
0x180007e63  jz      short loc_180007E6A
0x180007e65  cmp     [rdi], rbp
0x180007e68  jnb     short loc_180007EA2
0x180007e6a  mov     rdx, rbp; dwBytes
0x180007e6d  mov     ecx, 8; dwFlags
0x180007e72  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007e77  mov     r14, rax
0x180007e7a  test    rax, rax
0x180007e7d  jz      short loc_180007E9E
0x180007e7f  mov     rbx, [rsi+40h]
0x180007e83  call    cs:__imp_GetProcessHeap
0x180007e89  mov     r8, rbx; lpMem
0x180007e8c  xor     edx, edx; dwFlags
0x180007e8e  mov     rcx, rax; hHeap
0x180007e91  call    cs:__imp_HeapFree
0x180007e97  mov     [rsi+40h], r14
0x180007e9b  mov     [rdi], rbp
0x180007e9e  lea     r14, [rsi+38h]
0x180007ea2  mov     rcx, [rsi+40h]; Destination
0x180007ea6  test    rcx, rcx
0x180007ea9  jz      short loc_180007EF9
0x180007eab  mov     rbx, [rdi]
0x180007eae  lea     r9, [rsi+10h]
0x180007eb2  mov     r8, [r15+38h]
0x180007eb6  add     rbx, rcx
0x180007eb9  mov     rdx, rbx
0x180007ebc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007ec1  mov     r8, [r15+80h]
0x180007ec8  lea     r9, [rsi+20h]
0x180007ecc  mov     rdx, rbx
0x180007ecf  mov     rcx, rax; Destination
0x180007ed2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007ed7  mov     r8, [r15+18h]
0x180007edb  mov     r9, r14
0x180007ede  mov     rdx, rbx
0x180007ee1  mov     rcx, rax; Destination
0x180007ee4  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180007ee9  sub     rbx, rax
0x180007eec  xor     edx, edx; Val
0x180007eee  mov     r8, rbx; Size
0x180007ef1  mov     rcx, rax; void *
0x180007ef4  call    memset_0
0x180007ef9  add     rsp, 28h
0x180007efd  pop     r15
0x180007eff  pop     r14
0x180007f01  pop     r13
0x180007f03  pop     r12
0x180007f05  pop     rdi
0x180007f06  pop     rsi
0x180007f07  pop     rbp
0x180007f08  pop     rbx
0x180007f09  retn
```
