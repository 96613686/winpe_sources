# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008954`
- end: `0x180008a8a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008ddc`

## callees

- `0x180003c24`
- `0x180003c9c`
- `0x1800073e0`
- `0x180008770`
- `0x180008790`
- `0x180008954`
- `0x18001b0f6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a03`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008a11`

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
0x180008954  push    rbx
0x180008956  push    rbp
0x180008957  push    rsi
0x180008958  push    rdi
0x180008959  push    r12
0x18000895b  push    r13
0x18000895d  push    r14
0x18000895f  push    r15
0x180008961  sub     rsp, 28h
0x180008965  mov     [rcx+4], r8d
0x180008969  lea     r14, [rcx+38h]
0x18000896d  mov     eax, [rdx+8]
0x180008970  mov     rsi, rcx
0x180008973  mov     [rcx+8], eax
0x180008976  mov     r15, rdx
0x180008979  mov     qword ptr [rcx+10h], 0
0x180008981  movzx   eax, word ptr [rdx+40h]
0x180008985  mov     [rcx+18h], ax
0x180008989  mov     al, [rdx]
0x18000898b  mov     [rcx+1Ah], al
0x18000898e  mov     qword ptr [rcx+20h], 0
0x180008996  mov     rax, [rdx+88h]
0x18000899d  mov     [rcx+28h], rax
0x1800089a1  mov     rax, [rdx+90h]
0x1800089a8  mov     [rcx+30h], rax
0x1800089ac  mov     qword ptr [r14], 0
0x1800089b3  mov     rcx, [rdx+18h]; this
0x1800089b7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800089bc  mov     rcx, [r15+38h]; this
0x1800089c0  mov     rbp, rax
0x1800089c3  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800089c8  mov     rcx, [r15+80h]; this
0x1800089cf  add     rbp, rax
0x1800089d2  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800089d7  add     rbp, rax
0x1800089da  lea     rdi, [rsi+48h]
0x1800089de  cmp     qword ptr [rsi+40h], 0
0x1800089e3  jz      short loc_1800089EA
0x1800089e5  cmp     [rdi], rbp
0x1800089e8  jnb     short loc_180008A22
0x1800089ea  mov     rdx, rbp; dwBytes
0x1800089ed  mov     ecx, 8; dwFlags
0x1800089f2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800089f7  mov     r14, rax
0x1800089fa  test    rax, rax
0x1800089fd  jz      short loc_180008A1E
0x1800089ff  mov     rbx, [rsi+40h]
0x180008a03  call    cs:__imp_GetProcessHeap
0x180008a09  mov     r8, rbx; lpMem
0x180008a0c  xor     edx, edx; dwFlags
0x180008a0e  mov     rcx, rax; hHeap
0x180008a11  call    cs:__imp_HeapFree
0x180008a17  mov     [rsi+40h], r14
0x180008a1b  mov     [rdi], rbp
0x180008a1e  lea     r14, [rsi+38h]
0x180008a22  mov     rcx, [rsi+40h]; Destination
0x180008a26  test    rcx, rcx
0x180008a29  jz      short loc_180008A79
0x180008a2b  mov     rbx, [rdi]
0x180008a2e  lea     r9, [rsi+10h]
0x180008a32  mov     r8, [r15+38h]
0x180008a36  add     rbx, rcx
0x180008a39  mov     rdx, rbx
0x180008a3c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008a41  mov     r8, [r15+80h]
0x180008a48  lea     r9, [rsi+20h]
0x180008a4c  mov     rdx, rbx
0x180008a4f  mov     rcx, rax; Destination
0x180008a52  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008a57  mov     r8, [r15+18h]
0x180008a5b  mov     r9, r14
0x180008a5e  mov     rdx, rbx
0x180008a61  mov     rcx, rax; Destination
0x180008a64  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180008a69  sub     rbx, rax
0x180008a6c  xor     edx, edx; Val
0x180008a6e  mov     r8, rbx; Size
0x180008a71  mov     rcx, rax; void *
0x180008a74  call    memset_0
0x180008a79  add     rsp, 28h
0x180008a7d  pop     r15
0x180008a7f  pop     r14
0x180008a81  pop     r13
0x180008a83  pop     r12
0x180008a85  pop     rdi
0x180008a86  pop     rsi
0x180008a87  pop     rbp
0x180008a88  pop     rbx
0x180008a89  retn
```
