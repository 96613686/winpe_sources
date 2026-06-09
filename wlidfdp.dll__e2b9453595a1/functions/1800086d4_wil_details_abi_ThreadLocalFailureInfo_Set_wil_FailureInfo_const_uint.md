# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800086d4`
- end: `0x18000880a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008a6c`

## callees

- `0x1800033b4`
- `0x180004f74`
- `0x180004fec`
- `0x180007a58`
- `0x180008590`
- `0x1800085b0`
- `0x1800086d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008783`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008783`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008791`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008791`

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
0x1800086d4  push    rbx
0x1800086d6  push    rbp
0x1800086d7  push    rsi
0x1800086d8  push    rdi
0x1800086d9  push    r12
0x1800086db  push    r13
0x1800086dd  push    r14
0x1800086df  push    r15
0x1800086e1  sub     rsp, 28h
0x1800086e5  mov     [rcx+4], r8d
0x1800086e9  lea     r14, [rcx+38h]
0x1800086ed  mov     eax, [rdx+8]
0x1800086f0  mov     rsi, rcx
0x1800086f3  mov     [rcx+8], eax
0x1800086f6  mov     r15, rdx
0x1800086f9  mov     qword ptr [rcx+10h], 0
0x180008701  movzx   eax, word ptr [rdx+40h]
0x180008705  mov     [rcx+18h], ax
0x180008709  mov     al, [rdx]
0x18000870b  mov     [rcx+1Ah], al
0x18000870e  mov     qword ptr [rcx+20h], 0
0x180008716  mov     rax, [rdx+88h]
0x18000871d  mov     [rcx+28h], rax
0x180008721  mov     rax, [rdx+90h]
0x180008728  mov     [rcx+30h], rax
0x18000872c  mov     qword ptr [r14], 0
0x180008733  mov     rcx, [rdx+18h]; this
0x180008737  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000873c  mov     rcx, [r15+38h]; this
0x180008740  mov     rbp, rax
0x180008743  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008748  mov     rcx, [r15+80h]; this
0x18000874f  add     rbp, rax
0x180008752  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008757  add     rbp, rax
0x18000875a  lea     rdi, [rsi+48h]
0x18000875e  cmp     qword ptr [rsi+40h], 0
0x180008763  jz      short loc_18000876A
0x180008765  cmp     [rdi], rbp
0x180008768  jnb     short loc_1800087A2
0x18000876a  mov     rdx, rbp; dwBytes
0x18000876d  mov     ecx, 8; dwFlags
0x180008772  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008777  mov     r14, rax
0x18000877a  test    rax, rax
0x18000877d  jz      short loc_18000879E
0x18000877f  mov     rbx, [rsi+40h]
0x180008783  call    cs:__imp_GetProcessHeap
0x180008789  mov     r8, rbx; lpMem
0x18000878c  xor     edx, edx; dwFlags
0x18000878e  mov     rcx, rax; hHeap
0x180008791  call    cs:__imp_HeapFree
0x180008797  mov     [rsi+40h], r14
0x18000879b  mov     [rdi], rbp
0x18000879e  lea     r14, [rsi+38h]
0x1800087a2  mov     rcx, [rsi+40h]; Destination
0x1800087a6  test    rcx, rcx
0x1800087a9  jz      short loc_1800087F9
0x1800087ab  mov     rbx, [rdi]
0x1800087ae  lea     r9, [rsi+10h]
0x1800087b2  mov     r8, [r15+38h]
0x1800087b6  add     rbx, rcx
0x1800087b9  mov     rdx, rbx
0x1800087bc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800087c1  mov     r8, [r15+80h]
0x1800087c8  lea     r9, [rsi+20h]
0x1800087cc  mov     rdx, rbx
0x1800087cf  mov     rcx, rax; Destination
0x1800087d2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800087d7  mov     r8, [r15+18h]
0x1800087db  mov     r9, r14
0x1800087de  mov     rdx, rbx
0x1800087e1  mov     rcx, rax; Destination
0x1800087e4  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800087e9  sub     rbx, rax
0x1800087ec  xor     edx, edx; Val
0x1800087ee  mov     r8, rbx; Size
0x1800087f1  mov     rcx, rax; void *
0x1800087f4  call    memset_0
0x1800087f9  add     rsp, 28h
0x1800087fd  pop     r15
0x1800087ff  pop     r14
0x180008801  pop     r13
0x180008803  pop     r12
0x180008805  pop     rdi
0x180008806  pop     rsi
0x180008807  pop     rbp
0x180008808  pop     rbx
0x180008809  retn
```
