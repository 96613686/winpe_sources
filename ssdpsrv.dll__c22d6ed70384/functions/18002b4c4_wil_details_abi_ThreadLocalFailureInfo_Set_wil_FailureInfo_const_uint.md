# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002b4c4`
- end: `0x18002b634`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002b728`

## callees

- `0x180027344`
- `0x18002735c`
- `0x180028768`
- `0x18002a834`
- `0x18002b340`
- `0x18002b360`
- `0x18002b4c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b57a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002b57a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b56c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b56c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x18002b4c4  push    rbx
0x18002b4c6  push    rbp
0x18002b4c7  push    rsi
0x18002b4c8  push    rdi
0x18002b4c9  push    r12
0x18002b4cb  push    r13
0x18002b4cd  push    r14
0x18002b4cf  push    r15
0x18002b4d1  sub     rsp, 28h
0x18002b4d5  mov     [rcx+4], r8d
0x18002b4d9  lea     rbx, [rcx+20h]
0x18002b4dd  mov     eax, [rdx+8]
0x18002b4e0  lea     rsi, [rcx+38h]
0x18002b4e4  mov     [rcx+8], eax
0x18002b4e7  xor     r12d, r12d
0x18002b4ea  mov     [rcx+10h], r12
0x18002b4ee  mov     rbp, rcx
0x18002b4f1  movzx   eax, word ptr [rdx+40h]
0x18002b4f5  mov     r14, rdx
0x18002b4f8  mov     [rcx+18h], ax
0x18002b4fc  mov     al, [rdx]
0x18002b4fe  mov     [rcx+1Ah], al
0x18002b501  mov     [rbx], r12
0x18002b504  mov     rax, [rdx+88h]
0x18002b50b  mov     [rcx+28h], rax
0x18002b50f  mov     rax, [rdx+90h]
0x18002b516  mov     [rcx+30h], rax
0x18002b51a  mov     [rsi], r12
0x18002b51d  mov     rcx, [rdx+18h]; this
0x18002b521  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002b526  mov     rcx, [r14+38h]; this
0x18002b52a  mov     r15, rax
0x18002b52d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002b532  mov     rcx, [r14+80h]; this
0x18002b539  add     r15, rax
0x18002b53c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002b541  add     r15, rax
0x18002b544  lea     rdi, [rbp+48h]
0x18002b548  cmp     [rbp+40h], r12
0x18002b54c  jz      short loc_18002B553
0x18002b54e  cmp     [rdi], r15
0x18002b551  jnb     short loc_18002B58E
0x18002b553  mov     rdx, r15; dwBytes
0x18002b556  mov     ecx, 8; dwFlags
0x18002b55b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002b560  mov     r12, rax
0x18002b563  test    rax, rax
0x18002b566  jz      short loc_18002B58B
0x18002b568  mov     rbx, [rbp+40h]
0x18002b56c  call    cs:__imp_GetProcessHeap
0x18002b572  mov     r8, rbx; lpMem
0x18002b575  xor     edx, edx; dwFlags
0x18002b577  mov     rcx, rax; hHeap
0x18002b57a  call    cs:__imp_HeapFree
0x18002b580  mov     [rbp+40h], r12
0x18002b584  lea     rbx, [rbp+20h]
0x18002b588  mov     [rdi], r15
0x18002b58b  xor     r12d, r12d
0x18002b58e  mov     rcx, [rbp+40h]; Destination
0x18002b592  test    rcx, rcx
0x18002b595  jz      loc_18002B623
0x18002b59b  mov     rdi, [rdi]
0x18002b59e  lea     r9, [rbp+10h]
0x18002b5a2  mov     r8, [r14+38h]
0x18002b5a6  add     rdi, rcx
0x18002b5a9  mov     rdx, rdi
0x18002b5ac  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002b5b1  mov     r8, [r14+80h]
0x18002b5b8  mov     r9, rbx
0x18002b5bb  mov     rdx, rdi
0x18002b5be  mov     rcx, rax; Destination
0x18002b5c1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002b5c6  mov     rbx, rax
0x18002b5c9  cmp     rax, rdi
0x18002b5cc  jz      short loc_18002B60B
0x18002b5ce  mov     rcx, [r14+18h]; this
0x18002b5d2  test    rcx, rcx
0x18002b5d5  jz      short loc_18002B60B
0x18002b5d7  cmp     [rcx], r12w
0x18002b5db  jz      short loc_18002B60B
0x18002b5dd  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002b5e2  mov     rdx, rdi
0x18002b5e5  mov     r14, rax
0x18002b5e8  sub     rdx, rbx; DestinationSize
0x18002b5eb  cmp     rdx, rax
0x18002b5ee  jb      short loc_18002B60B
0x18002b5f0  mov     r8, rcx; Source
0x18002b5f3  mov     r9, rax; SourceSize
0x18002b5f6  mov     rcx, rbx; Destination
0x18002b5f9  call    memcpy_s
0x18002b5fe  test    rsi, rsi
0x18002b601  jz      short loc_18002B606
0x18002b603  mov     [rsi], rbx
0x18002b606  add     rbx, r14
0x18002b609  jmp     short loc_18002B613
0x18002b60b  test    rsi, rsi
0x18002b60e  jz      short loc_18002B613
0x18002b610  mov     [rsi], r12
0x18002b613  sub     rdi, rbx
0x18002b616  xor     edx, edx; Val
0x18002b618  mov     r8, rdi; Size
0x18002b61b  mov     rcx, rbx; void *
0x18002b61e  call    memset_0
0x18002b623  add     rsp, 28h
0x18002b627  pop     r15
0x18002b629  pop     r14
0x18002b62b  pop     r13
0x18002b62d  pop     r12
0x18002b62f  pop     rdi
0x18002b630  pop     rsi
0x18002b631  pop     rbp
0x18002b632  pop     rbx
0x18002b633  retn
```
