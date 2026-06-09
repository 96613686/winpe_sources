# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180020f2c`
- end: `0x180021062`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180021158`

## callees

- `0x18001d118`
- `0x18001d190`
- `0x18001fc00`
- `0x180020cd0`
- `0x180020cf0`
- `0x180020f2c`
- `0x180032c6a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020fdb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020fdb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020fe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020fe9`

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
0x180020f2c  push    rbx
0x180020f2e  push    rbp
0x180020f2f  push    rsi
0x180020f30  push    rdi
0x180020f31  push    r12
0x180020f33  push    r13
0x180020f35  push    r14
0x180020f37  push    r15
0x180020f39  sub     rsp, 28h
0x180020f3d  mov     [rcx+4], r8d
0x180020f41  lea     r14, [rcx+38h]
0x180020f45  mov     eax, [rdx+8]
0x180020f48  mov     rsi, rcx
0x180020f4b  mov     [rcx+8], eax
0x180020f4e  mov     r15, rdx
0x180020f51  mov     qword ptr [rcx+10h], 0
0x180020f59  movzx   eax, word ptr [rdx+40h]
0x180020f5d  mov     [rcx+18h], ax
0x180020f61  mov     al, [rdx]
0x180020f63  mov     [rcx+1Ah], al
0x180020f66  mov     qword ptr [rcx+20h], 0
0x180020f6e  mov     rax, [rdx+88h]
0x180020f75  mov     [rcx+28h], rax
0x180020f79  mov     rax, [rdx+90h]
0x180020f80  mov     [rcx+30h], rax
0x180020f84  mov     qword ptr [r14], 0
0x180020f8b  mov     rcx, [rdx+18h]; this
0x180020f8f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180020f94  mov     rcx, [r15+38h]; this
0x180020f98  mov     rbp, rax
0x180020f9b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180020fa0  mov     rcx, [r15+80h]; this
0x180020fa7  add     rbp, rax
0x180020faa  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180020faf  add     rbp, rax
0x180020fb2  lea     rdi, [rsi+48h]
0x180020fb6  cmp     qword ptr [rsi+40h], 0
0x180020fbb  jz      short loc_180020FC2
0x180020fbd  cmp     [rdi], rbp
0x180020fc0  jnb     short loc_180020FFA
0x180020fc2  mov     rdx, rbp; dwBytes
0x180020fc5  mov     ecx, 8; dwFlags
0x180020fca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180020fcf  mov     r14, rax
0x180020fd2  test    rax, rax
0x180020fd5  jz      short loc_180020FF6
0x180020fd7  mov     rbx, [rsi+40h]
0x180020fdb  call    cs:__imp_GetProcessHeap
0x180020fe1  mov     r8, rbx; lpMem
0x180020fe4  xor     edx, edx; dwFlags
0x180020fe6  mov     rcx, rax; hHeap
0x180020fe9  call    cs:__imp_HeapFree
0x180020fef  mov     [rsi+40h], r14
0x180020ff3  mov     [rdi], rbp
0x180020ff6  lea     r14, [rsi+38h]
0x180020ffa  mov     rcx, [rsi+40h]; Destination
0x180020ffe  test    rcx, rcx
0x180021001  jz      short loc_180021051
0x180021003  mov     rbx, [rdi]
0x180021006  lea     r9, [rsi+10h]
0x18002100a  mov     r8, [r15+38h]
0x18002100e  add     rbx, rcx
0x180021011  mov     rdx, rbx
0x180021014  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180021019  mov     r8, [r15+80h]
0x180021020  lea     r9, [rsi+20h]
0x180021024  mov     rdx, rbx
0x180021027  mov     rcx, rax; Destination
0x18002102a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002102f  mov     r8, [r15+18h]
0x180021033  mov     r9, r14
0x180021036  mov     rdx, rbx
0x180021039  mov     rcx, rax; Destination
0x18002103c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180021041  sub     rbx, rax
0x180021044  xor     edx, edx; Val
0x180021046  mov     r8, rbx; Size
0x180021049  mov     rcx, rax; void *
0x18002104c  call    memset_0
0x180021051  add     rsp, 28h
0x180021055  pop     r15
0x180021057  pop     r14
0x180021059  pop     r13
0x18002105b  pop     r12
0x18002105d  pop     rdi
0x18002105e  pop     rsi
0x18002105f  pop     rbp
0x180021060  pop     rbx
0x180021061  retn
```
