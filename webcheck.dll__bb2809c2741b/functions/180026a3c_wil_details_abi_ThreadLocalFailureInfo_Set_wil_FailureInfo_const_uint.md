# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180026a3c`
- end: `0x180026bad`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180026bb4`

## callees

- `0x180024828`
- `0x18002675c`
- `0x18002696c`
- `0x18002698c`
- `0x180026a3c`
- `0x18002924e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180026b71`
- `msvcrt!memcpy_s` at `0x180026b71`
- `KERNEL32!GetProcessHeap` at `0x180026ae4`
- `KERNEL32!GetProcessHeap` at `0x180026ae4`
- `KERNEL32!HeapFree` at `0x180026af2`
- `KERNEL32!HeapFree` at `0x180026af2`

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
0x180026a3c  push    rbx
0x180026a3e  push    rbp
0x180026a3f  push    rsi
0x180026a40  push    rdi
0x180026a41  push    r12
0x180026a43  push    r13
0x180026a45  push    r14
0x180026a47  push    r15
0x180026a49  sub     rsp, 28h
0x180026a4d  mov     [rcx+4], r8d
0x180026a51  lea     rbx, [rcx+20h]
0x180026a55  mov     eax, [rdx+8]
0x180026a58  lea     rsi, [rcx+38h]
0x180026a5c  mov     [rcx+8], eax
0x180026a5f  xor     r12d, r12d
0x180026a62  mov     [rcx+10h], r12
0x180026a66  mov     rbp, rcx
0x180026a69  movzx   eax, word ptr [rdx+40h]
0x180026a6d  mov     r14, rdx
0x180026a70  mov     [rcx+18h], ax
0x180026a74  mov     al, [rdx]
0x180026a76  mov     [rcx+1Ah], al
0x180026a79  mov     [rbx], r12
0x180026a7c  mov     rax, [rdx+88h]
0x180026a83  mov     [rcx+28h], rax
0x180026a87  mov     rax, [rdx+90h]
0x180026a8e  mov     [rcx+30h], rax
0x180026a92  mov     [rsi], r12
0x180026a95  mov     rcx, [rdx+18h]; this
0x180026a99  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180026a9e  mov     rcx, [r14+38h]; this
0x180026aa2  mov     r15, rax
0x180026aa5  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180026aaa  mov     rcx, [r14+80h]; this
0x180026ab1  add     r15, rax
0x180026ab4  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180026ab9  add     r15, rax
0x180026abc  lea     rdi, [rbp+48h]
0x180026ac0  cmp     [rbp+40h], r12
0x180026ac4  jz      short loc_180026ACB
0x180026ac6  cmp     [rdi], r15
0x180026ac9  jnb     short loc_180026B06
0x180026acb  mov     rdx, r15; dwBytes
0x180026ace  mov     ecx, 8; dwFlags
0x180026ad3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180026ad8  mov     r12, rax
0x180026adb  test    rax, rax
0x180026ade  jz      short loc_180026B03
0x180026ae0  mov     rbx, [rbp+40h]
0x180026ae4  call    cs:__imp_GetProcessHeap
0x180026aea  mov     r8, rbx; lpMem
0x180026aed  xor     edx, edx; dwFlags
0x180026aef  mov     rcx, rax; hHeap
0x180026af2  call    cs:__imp_HeapFree
0x180026af8  mov     [rbp+40h], r12
0x180026afc  lea     rbx, [rbp+20h]
0x180026b00  mov     [rdi], r15
0x180026b03  xor     r12d, r12d
0x180026b06  mov     rcx, [rbp+40h]; Destination
0x180026b0a  test    rcx, rcx
0x180026b0d  jz      loc_180026B9C
0x180026b13  mov     rdi, [rdi]
0x180026b16  lea     r9, [rbp+10h]
0x180026b1a  mov     r8, [r14+38h]
0x180026b1e  add     rdi, rcx
0x180026b21  mov     rdx, rdi
0x180026b24  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180026b29  mov     r8, [r14+80h]
0x180026b30  mov     r9, rbx
0x180026b33  mov     rdx, rdi
0x180026b36  mov     rcx, rax; Destination
0x180026b39  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180026b3e  mov     rbx, rax
0x180026b41  cmp     rax, rdi
0x180026b44  jz      short loc_180026B84
0x180026b46  mov     rcx, [r14+18h]; this
0x180026b4a  test    rcx, rcx
0x180026b4d  jz      short loc_180026B84
0x180026b4f  cmp     [rcx], r12w
0x180026b53  jz      short loc_180026B84
0x180026b55  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180026b5a  mov     rdx, rdi
0x180026b5d  mov     r14, rax
0x180026b60  sub     rdx, rbx; DestinationSize
0x180026b63  cmp     rdx, rax
0x180026b66  jb      short loc_180026B84
0x180026b68  mov     r8, rcx; Source
0x180026b6b  mov     r9, rax; SourceSize
0x180026b6e  mov     rcx, rbx; Destination
0x180026b71  call    cs:__imp_memcpy_s
0x180026b77  test    rsi, rsi
0x180026b7a  jz      short loc_180026B7F
0x180026b7c  mov     [rsi], rbx
0x180026b7f  add     rbx, r14
0x180026b82  jmp     short loc_180026B8C
0x180026b84  test    rsi, rsi
0x180026b87  jz      short loc_180026B8C
0x180026b89  mov     [rsi], r12
0x180026b8c  sub     rdi, rbx
0x180026b8f  xor     edx, edx; Val
0x180026b91  mov     r8, rdi; Size
0x180026b94  mov     rcx, rbx; void *
0x180026b97  call    memset_0
0x180026b9c  add     rsp, 28h
0x180026ba0  pop     r15
0x180026ba2  pop     r14
0x180026ba4  pop     r13
0x180026ba6  pop     r12
0x180026ba8  pop     rdi
0x180026ba9  pop     rsi
0x180026baa  pop     rbp
0x180026bab  pop     rbx
0x180026bac  retn
```
