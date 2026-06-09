# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000fde8`
- end: `0x18000ff2b`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180010030`

## callees

- `0x18000953c`
- `0x18000974c`
- `0x1800097c4`
- `0x18000a2b8`
- `0x18000a2dc`
- `0x18000eb64`
- `0x18000fde8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000feab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000feab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe97`

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
0x18000fde8  push    rbx
0x18000fdea  push    rbp
0x18000fdeb  push    rsi
0x18000fdec  push    rdi
0x18000fded  push    r12
0x18000fdef  push    r13
0x18000fdf1  push    r14
0x18000fdf3  push    r15
0x18000fdf5  sub     rsp, 28h
0x18000fdf9  mov     [rcx+4], r8d
0x18000fdfd  lea     r14, [rcx+38h]
0x18000fe01  mov     eax, [rdx+8]
0x18000fe04  mov     rsi, rcx
0x18000fe07  mov     [rcx+8], eax
0x18000fe0a  mov     r15, rdx
0x18000fe0d  mov     qword ptr [rcx+10h], 0
0x18000fe15  movzx   eax, word ptr [rdx+40h]
0x18000fe19  mov     [rcx+18h], ax
0x18000fe1d  mov     al, [rdx]
0x18000fe1f  mov     [rcx+1Ah], al
0x18000fe22  mov     qword ptr [rcx+20h], 0
0x18000fe2a  mov     rax, [rdx+88h]
0x18000fe31  mov     [rcx+28h], rax
0x18000fe35  mov     rax, [rdx+90h]
0x18000fe3c  mov     [rcx+30h], rax
0x18000fe40  mov     qword ptr [r14], 0
0x18000fe47  mov     rcx, [rdx+18h]; this
0x18000fe4b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000fe50  mov     rcx, [r15+38h]; this
0x18000fe54  mov     rbp, rax
0x18000fe57  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000fe5c  mov     rcx, [r15+80h]; this
0x18000fe63  add     rbp, rax
0x18000fe66  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000fe6b  add     rbp, rax
0x18000fe6e  lea     rdi, [rsi+48h]
0x18000fe72  cmp     qword ptr [rsi+40h], 0
0x18000fe77  jz      short loc_18000FE7E
0x18000fe79  cmp     [rdi], rbp
0x18000fe7c  jnb     short loc_18000FEC2
0x18000fe7e  mov     rdx, rbp; dwBytes
0x18000fe81  mov     ecx, 8; dwFlags
0x18000fe86  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000fe8b  mov     r14, rax
0x18000fe8e  test    rax, rax
0x18000fe91  jz      short loc_18000FEBE
0x18000fe93  mov     rbx, [rsi+40h]
0x18000fe97  call    cs:__imp_GetProcessHeap
0x18000fe9e  nop     dword ptr [rax+rax+00h]
0x18000fea3  mov     r8, rbx; lpMem
0x18000fea6  xor     edx, edx; dwFlags
0x18000fea8  mov     rcx, rax; hHeap
0x18000feab  call    cs:__imp_HeapFree
0x18000feb2  nop     dword ptr [rax+rax+00h]
0x18000feb7  mov     [rsi+40h], r14
0x18000febb  mov     [rdi], rbp
0x18000febe  lea     r14, [rsi+38h]
0x18000fec2  mov     rcx, [rsi+40h]; Destination
0x18000fec6  test    rcx, rcx
0x18000fec9  jz      short loc_18000FF19
0x18000fecb  mov     rbx, [rdi]
0x18000fece  lea     r9, [rsi+10h]
0x18000fed2  mov     r8, [r15+38h]
0x18000fed6  add     rbx, rcx
0x18000fed9  mov     rdx, rbx
0x18000fedc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000fee1  mov     r8, [r15+80h]
0x18000fee8  lea     r9, [rsi+20h]
0x18000feec  mov     rdx, rbx
0x18000feef  mov     rcx, rax; Destination
0x18000fef2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000fef7  mov     r8, [r15+18h]
0x18000fefb  mov     r9, r14
0x18000fefe  mov     rdx, rbx
0x18000ff01  mov     rcx, rax; Destination
0x18000ff04  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000ff09  sub     rbx, rax
0x18000ff0c  xor     edx, edx; Val
0x18000ff0e  mov     r8, rbx; Size
0x18000ff11  mov     rcx, rax; void *
0x18000ff14  call    memset_0
0x18000ff19  add     rsp, 28h
0x18000ff1d  pop     r15
0x18000ff1f  pop     r14
0x18000ff21  pop     r13
0x18000ff23  pop     r12
0x18000ff25  pop     rdi
0x18000ff26  pop     rsi
0x18000ff27  pop     rbp
0x18000ff28  pop     rbx
0x18000ff29  retn
```
