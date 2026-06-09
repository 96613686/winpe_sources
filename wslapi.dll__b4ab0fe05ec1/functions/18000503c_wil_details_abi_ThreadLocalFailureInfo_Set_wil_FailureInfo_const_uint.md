# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000503c`
- end: `0x180005172`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800053d4`

## callees

- `0x180002ab4`
- `0x180003110`
- `0x180003188`
- `0x180004ba4`
- `0x180004f58`
- `0x180004f78`
- `0x18000503c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800050f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800050eb`

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
0x18000503c  push    rbx
0x18000503e  push    rbp
0x18000503f  push    rsi
0x180005040  push    rdi
0x180005041  push    r12
0x180005043  push    r13
0x180005045  push    r14
0x180005047  push    r15
0x180005049  sub     rsp, 28h
0x18000504d  mov     [rcx+4], r8d
0x180005051  lea     r14, [rcx+38h]
0x180005055  mov     eax, [rdx+8]
0x180005058  mov     rsi, rcx
0x18000505b  mov     [rcx+8], eax
0x18000505e  mov     r15, rdx
0x180005061  mov     qword ptr [rcx+10h], 0
0x180005069  movzx   eax, word ptr [rdx+40h]
0x18000506d  mov     [rcx+18h], ax
0x180005071  mov     al, [rdx]
0x180005073  mov     [rcx+1Ah], al
0x180005076  mov     qword ptr [rcx+20h], 0
0x18000507e  mov     rax, [rdx+88h]
0x180005085  mov     [rcx+28h], rax
0x180005089  mov     rax, [rdx+90h]
0x180005090  mov     [rcx+30h], rax
0x180005094  mov     qword ptr [r14], 0
0x18000509b  mov     rcx, [rdx+18h]; this
0x18000509f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800050a4  mov     rcx, [r15+38h]; this
0x1800050a8  mov     rbp, rax
0x1800050ab  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800050b0  mov     rcx, [r15+80h]; this
0x1800050b7  add     rbp, rax
0x1800050ba  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800050bf  add     rbp, rax
0x1800050c2  lea     rdi, [rsi+48h]
0x1800050c6  cmp     qword ptr [rsi+40h], 0
0x1800050cb  jz      short loc_1800050D2
0x1800050cd  cmp     [rdi], rbp
0x1800050d0  jnb     short loc_18000510A
0x1800050d2  mov     rdx, rbp; dwBytes
0x1800050d5  mov     ecx, 8; dwFlags
0x1800050da  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800050df  mov     r14, rax
0x1800050e2  test    rax, rax
0x1800050e5  jz      short loc_180005106
0x1800050e7  mov     rbx, [rsi+40h]
0x1800050eb  call    cs:__imp_GetProcessHeap
0x1800050f1  mov     r8, rbx; lpMem
0x1800050f4  xor     edx, edx; dwFlags
0x1800050f6  mov     rcx, rax; hHeap
0x1800050f9  call    cs:__imp_HeapFree
0x1800050ff  mov     [rsi+40h], r14
0x180005103  mov     [rdi], rbp
0x180005106  lea     r14, [rsi+38h]
0x18000510a  mov     rcx, [rsi+40h]; Destination
0x18000510e  test    rcx, rcx
0x180005111  jz      short loc_180005161
0x180005113  mov     rbx, [rdi]
0x180005116  lea     r9, [rsi+10h]
0x18000511a  mov     r8, [r15+38h]
0x18000511e  add     rbx, rcx
0x180005121  mov     rdx, rbx
0x180005124  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005129  mov     r8, [r15+80h]
0x180005130  lea     r9, [rsi+20h]
0x180005134  mov     rdx, rbx
0x180005137  mov     rcx, rax; Destination
0x18000513a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000513f  mov     r8, [r15+18h]
0x180005143  mov     r9, r14
0x180005146  mov     rdx, rbx
0x180005149  mov     rcx, rax; Destination
0x18000514c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180005151  sub     rbx, rax
0x180005154  xor     edx, edx; Val
0x180005156  mov     r8, rbx; Size
0x180005159  mov     rcx, rax; void *
0x18000515c  call    memset_0
0x180005161  add     rsp, 28h
0x180005165  pop     r15
0x180005167  pop     r14
0x180005169  pop     r13
0x18000516b  pop     r12
0x18000516d  pop     rdi
0x18000516e  pop     rsi
0x18000516f  pop     rbp
0x180005170  pop     rbx
0x180005171  retn
```
