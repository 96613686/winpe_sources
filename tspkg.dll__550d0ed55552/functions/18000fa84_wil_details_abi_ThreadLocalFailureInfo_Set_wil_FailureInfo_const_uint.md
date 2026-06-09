# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000fa84`
- end: `0x18000fbf4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000fce8`

## callees

- `0x18000c1a4`
- `0x18000d198`
- `0x18000f008`
- `0x18000f930`
- `0x18000f950`
- `0x18000fa84`
- `0x180010e4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb2c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fb2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fb3a`

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
0x18000fa84  push    rbx
0x18000fa86  push    rbp
0x18000fa87  push    rsi
0x18000fa88  push    rdi
0x18000fa89  push    r12
0x18000fa8b  push    r13
0x18000fa8d  push    r14
0x18000fa8f  push    r15
0x18000fa91  sub     rsp, 28h
0x18000fa95  mov     [rcx+4], r8d
0x18000fa99  lea     rbx, [rcx+20h]
0x18000fa9d  mov     eax, [rdx+8]
0x18000faa0  lea     rsi, [rcx+38h]
0x18000faa4  mov     [rcx+8], eax
0x18000faa7  xor     r12d, r12d
0x18000faaa  mov     [rcx+10h], r12
0x18000faae  mov     rbp, rcx
0x18000fab1  movzx   eax, word ptr [rdx+40h]
0x18000fab5  mov     r14, rdx
0x18000fab8  mov     [rcx+18h], ax
0x18000fabc  mov     al, [rdx]
0x18000fabe  mov     [rcx+1Ah], al
0x18000fac1  mov     [rbx], r12
0x18000fac4  mov     rax, [rdx+88h]
0x18000facb  mov     [rcx+28h], rax
0x18000facf  mov     rax, [rdx+90h]
0x18000fad6  mov     [rcx+30h], rax
0x18000fada  mov     [rsi], r12
0x18000fadd  mov     rcx, [rdx+18h]; this
0x18000fae1  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000fae6  mov     rcx, [r14+38h]; this
0x18000faea  mov     r15, rax
0x18000faed  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000faf2  mov     rcx, [r14+80h]; this
0x18000faf9  add     r15, rax
0x18000fafc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000fb01  add     r15, rax
0x18000fb04  lea     rdi, [rbp+48h]
0x18000fb08  cmp     [rbp+40h], r12
0x18000fb0c  jz      short loc_18000FB13
0x18000fb0e  cmp     [rdi], r15
0x18000fb11  jnb     short loc_18000FB4E
0x18000fb13  mov     rdx, r15; dwBytes
0x18000fb16  mov     ecx, 8; dwFlags
0x18000fb1b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000fb20  mov     r12, rax
0x18000fb23  test    rax, rax
0x18000fb26  jz      short loc_18000FB4B
0x18000fb28  mov     rbx, [rbp+40h]
0x18000fb2c  call    cs:__imp_GetProcessHeap
0x18000fb32  mov     r8, rbx; lpMem
0x18000fb35  xor     edx, edx; dwFlags
0x18000fb37  mov     rcx, rax; hHeap
0x18000fb3a  call    cs:__imp_HeapFree
0x18000fb40  mov     [rbp+40h], r12
0x18000fb44  lea     rbx, [rbp+20h]
0x18000fb48  mov     [rdi], r15
0x18000fb4b  xor     r12d, r12d
0x18000fb4e  mov     rcx, [rbp+40h]; Destination
0x18000fb52  test    rcx, rcx
0x18000fb55  jz      loc_18000FBE3
0x18000fb5b  mov     rdi, [rdi]
0x18000fb5e  lea     r9, [rbp+10h]
0x18000fb62  mov     r8, [r14+38h]
0x18000fb66  add     rdi, rcx
0x18000fb69  mov     rdx, rdi
0x18000fb6c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000fb71  mov     r8, [r14+80h]
0x18000fb78  mov     r9, rbx
0x18000fb7b  mov     rdx, rdi
0x18000fb7e  mov     rcx, rax; Destination
0x18000fb81  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000fb86  mov     rbx, rax
0x18000fb89  cmp     rax, rdi
0x18000fb8c  jz      short loc_18000FBCB
0x18000fb8e  mov     rcx, [r14+18h]; this
0x18000fb92  test    rcx, rcx
0x18000fb95  jz      short loc_18000FBCB
0x18000fb97  cmp     [rcx], r12w
0x18000fb9b  jz      short loc_18000FBCB
0x18000fb9d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000fba2  mov     rdx, rdi
0x18000fba5  mov     r14, rax
0x18000fba8  sub     rdx, rbx; DestinationSize
0x18000fbab  cmp     rdx, rax
0x18000fbae  jb      short loc_18000FBCB
0x18000fbb0  mov     r8, rcx; Source
0x18000fbb3  mov     r9, rax; SourceSize
0x18000fbb6  mov     rcx, rbx; Destination
0x18000fbb9  call    memcpy_s
0x18000fbbe  test    rsi, rsi
0x18000fbc1  jz      short loc_18000FBC6
0x18000fbc3  mov     [rsi], rbx
0x18000fbc6  add     rbx, r14
0x18000fbc9  jmp     short loc_18000FBD3
0x18000fbcb  test    rsi, rsi
0x18000fbce  jz      short loc_18000FBD3
0x18000fbd0  mov     [rsi], r12
0x18000fbd3  sub     rdi, rbx
0x18000fbd6  xor     edx, edx; Val
0x18000fbd8  mov     r8, rdi; Size
0x18000fbdb  mov     rcx, rbx; void *
0x18000fbde  call    memset_0
0x18000fbe3  add     rsp, 28h
0x18000fbe7  pop     r15
0x18000fbe9  pop     r14
0x18000fbeb  pop     r13
0x18000fbed  pop     r12
0x18000fbef  pop     rdi
0x18000fbf0  pop     rsi
0x18000fbf1  pop     rbp
0x18000fbf2  pop     rbx
0x18000fbf3  retn
```
