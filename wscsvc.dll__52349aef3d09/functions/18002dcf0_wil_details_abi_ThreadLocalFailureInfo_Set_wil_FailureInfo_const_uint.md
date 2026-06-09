# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002dcf0`
- end: `0x18002de26`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002e088`

## callees

- `0x18002bf28`
- `0x18002bfa0`
- `0x18002d704`
- `0x18002dc48`
- `0x18002dc68`
- `0x18002dcf0`
- `0x18003fbf2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dd9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dd9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ddad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ddad`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  unsigned __int64 v6; // rbp
  const char *v7; // rdx
  unsigned __int64 v8; // rbp
  const char *v9; // rdx
  SIZE_T v10; // rbp
  SIZE_T *v11; // rdi
  LPVOID v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  const char *v16; // rbx
  char *v17; // rax
  unsigned __int16 *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (unsigned __int16 **)((char *)this + 56);
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
    v3 = (unsigned __int16 **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((wil::details **)a2 + 16),
                                (char **)this + 4);
    v19 = wil::details::WriteResultString<unsigned short const *>(
            v18,
            (const unsigned __int16 *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x18002dcf0  push    rbx
0x18002dcf2  push    rbp
0x18002dcf3  push    rsi
0x18002dcf4  push    rdi
0x18002dcf5  push    r12
0x18002dcf7  push    r13
0x18002dcf9  push    r14
0x18002dcfb  push    r15
0x18002dcfd  sub     rsp, 28h
0x18002dd01  mov     [rcx+4], r8d
0x18002dd05  lea     r14, [rcx+38h]
0x18002dd09  mov     eax, [rdx+8]
0x18002dd0c  mov     rsi, rcx
0x18002dd0f  mov     [rcx+8], eax
0x18002dd12  mov     r15, rdx
0x18002dd15  mov     qword ptr [rcx+10h], 0
0x18002dd1d  movzx   eax, word ptr [rdx+40h]
0x18002dd21  mov     [rcx+18h], ax
0x18002dd25  mov     al, [rdx]
0x18002dd27  mov     [rcx+1Ah], al
0x18002dd2a  mov     qword ptr [rcx+20h], 0
0x18002dd32  mov     rax, [rdx+88h]
0x18002dd39  mov     [rcx+28h], rax
0x18002dd3d  mov     rax, [rdx+90h]
0x18002dd44  mov     [rcx+30h], rax
0x18002dd48  mov     qword ptr [r14], 0
0x18002dd4f  mov     rcx, [rdx+18h]; this
0x18002dd53  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002dd58  mov     rcx, [r15+38h]; this
0x18002dd5c  mov     rbp, rax
0x18002dd5f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002dd64  mov     rcx, [r15+80h]; this
0x18002dd6b  add     rbp, rax
0x18002dd6e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002dd73  add     rbp, rax
0x18002dd76  lea     rdi, [rsi+48h]
0x18002dd7a  cmp     qword ptr [rsi+40h], 0
0x18002dd7f  jz      short loc_18002DD86
0x18002dd81  cmp     [rdi], rbp
0x18002dd84  jnb     short loc_18002DDBE
0x18002dd86  mov     rdx, rbp; dwBytes
0x18002dd89  mov     ecx, 8; dwFlags
0x18002dd8e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002dd93  mov     r14, rax
0x18002dd96  test    rax, rax
0x18002dd99  jz      short loc_18002DDBA
0x18002dd9b  mov     rbx, [rsi+40h]
0x18002dd9f  call    cs:__imp_GetProcessHeap
0x18002dda5  mov     r8, rbx; lpMem
0x18002dda8  xor     edx, edx; dwFlags
0x18002ddaa  mov     rcx, rax; hHeap
0x18002ddad  call    cs:__imp_HeapFree
0x18002ddb3  mov     [rsi+40h], r14
0x18002ddb7  mov     [rdi], rbp
0x18002ddba  lea     r14, [rsi+38h]
0x18002ddbe  mov     rcx, [rsi+40h]; Destination
0x18002ddc2  test    rcx, rcx
0x18002ddc5  jz      short loc_18002DE15
0x18002ddc7  mov     rbx, [rdi]
0x18002ddca  lea     r9, [rsi+10h]
0x18002ddce  mov     r8, [r15+38h]
0x18002ddd2  add     rbx, rcx
0x18002ddd5  mov     rdx, rbx
0x18002ddd8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002dddd  mov     r8, [r15+80h]
0x18002dde4  lea     r9, [rsi+20h]
0x18002dde8  mov     rdx, rbx
0x18002ddeb  mov     rcx, rax; Destination
0x18002ddee  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002ddf3  mov     r8, [r15+18h]
0x18002ddf7  mov     r9, r14
0x18002ddfa  mov     rdx, rbx
0x18002ddfd  mov     rcx, rax; Destination
0x18002de00  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18002de05  sub     rbx, rax
0x18002de08  xor     edx, edx; Val
0x18002de0a  mov     r8, rbx; Size
0x18002de0d  mov     rcx, rax; void *
0x18002de10  call    memset_0
0x18002de15  add     rsp, 28h
0x18002de19  pop     r15
0x18002de1b  pop     r14
0x18002de1d  pop     r13
0x18002de1f  pop     r12
0x18002de21  pop     rdi
0x18002de22  pop     rsi
0x18002de23  pop     rbp
0x18002de24  pop     rbx
0x18002de25  retn
```
