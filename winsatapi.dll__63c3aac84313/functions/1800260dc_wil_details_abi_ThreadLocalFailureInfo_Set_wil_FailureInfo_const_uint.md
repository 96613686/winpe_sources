# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800260dc`
- end: `0x180026212`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180026560`

## callees

- `0x1800151bb`
- `0x180022388`
- `0x180022400`
- `0x1800255a8`
- `0x180025f18`
- `0x180025f38`
- `0x1800260dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002618b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002618b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026199`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026199`

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
0x1800260dc  push    rbx
0x1800260de  push    rbp
0x1800260df  push    rsi
0x1800260e0  push    rdi
0x1800260e1  push    r12
0x1800260e3  push    r13
0x1800260e5  push    r14
0x1800260e7  push    r15
0x1800260e9  sub     rsp, 28h
0x1800260ed  mov     [rcx+4], r8d
0x1800260f1  lea     r14, [rcx+38h]
0x1800260f5  mov     eax, [rdx+8]
0x1800260f8  mov     rsi, rcx
0x1800260fb  mov     [rcx+8], eax
0x1800260fe  mov     r15, rdx
0x180026101  mov     qword ptr [rcx+10h], 0
0x180026109  movzx   eax, word ptr [rdx+40h]
0x18002610d  mov     [rcx+18h], ax
0x180026111  mov     al, [rdx]
0x180026113  mov     [rcx+1Ah], al
0x180026116  mov     qword ptr [rcx+20h], 0
0x18002611e  mov     rax, [rdx+88h]
0x180026125  mov     [rcx+28h], rax
0x180026129  mov     rax, [rdx+90h]
0x180026130  mov     [rcx+30h], rax
0x180026134  mov     qword ptr [r14], 0
0x18002613b  mov     rcx, [rdx+18h]; this
0x18002613f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180026144  mov     rcx, [r15+38h]; this
0x180026148  mov     rbp, rax
0x18002614b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180026150  mov     rcx, [r15+80h]; this
0x180026157  add     rbp, rax
0x18002615a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002615f  add     rbp, rax
0x180026162  lea     rdi, [rsi+48h]
0x180026166  cmp     qword ptr [rsi+40h], 0
0x18002616b  jz      short loc_180026172
0x18002616d  cmp     [rdi], rbp
0x180026170  jnb     short loc_1800261AA
0x180026172  mov     rdx, rbp; dwBytes
0x180026175  mov     ecx, 8; dwFlags
0x18002617a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002617f  mov     r14, rax
0x180026182  test    rax, rax
0x180026185  jz      short loc_1800261A6
0x180026187  mov     rbx, [rsi+40h]
0x18002618b  call    cs:__imp_GetProcessHeap
0x180026191  mov     r8, rbx; lpMem
0x180026194  xor     edx, edx; dwFlags
0x180026196  mov     rcx, rax; hHeap
0x180026199  call    cs:__imp_HeapFree
0x18002619f  mov     [rsi+40h], r14
0x1800261a3  mov     [rdi], rbp
0x1800261a6  lea     r14, [rsi+38h]
0x1800261aa  mov     rcx, [rsi+40h]; Destination
0x1800261ae  test    rcx, rcx
0x1800261b1  jz      short loc_180026201
0x1800261b3  mov     rbx, [rdi]
0x1800261b6  lea     r9, [rsi+10h]
0x1800261ba  mov     r8, [r15+38h]
0x1800261be  add     rbx, rcx
0x1800261c1  mov     rdx, rbx
0x1800261c4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800261c9  mov     r8, [r15+80h]
0x1800261d0  lea     r9, [rsi+20h]
0x1800261d4  mov     rdx, rbx
0x1800261d7  mov     rcx, rax; Destination
0x1800261da  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800261df  mov     r8, [r15+18h]
0x1800261e3  mov     r9, r14
0x1800261e6  mov     rdx, rbx
0x1800261e9  mov     rcx, rax; Destination
0x1800261ec  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800261f1  sub     rbx, rax
0x1800261f4  xor     edx, edx; Val
0x1800261f6  mov     r8, rbx; Size
0x1800261f9  mov     rcx, rax; void *
0x1800261fc  call    memset_0
0x180026201  add     rsp, 28h
0x180026205  pop     r15
0x180026207  pop     r14
0x180026209  pop     r13
0x18002620b  pop     r12
0x18002620d  pop     rdi
0x18002620e  pop     rsi
0x18002620f  pop     rbp
0x180026210  pop     rbx
0x180026211  retn
```
