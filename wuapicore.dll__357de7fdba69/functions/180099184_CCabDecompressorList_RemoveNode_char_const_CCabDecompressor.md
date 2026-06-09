# CCabDecompressorList::RemoveNode(char const *,CCabDecompressor * *)

- ea: `0x180099184`
- end: `0x18009929d`
- name: `?RemoveNode@CCabDecompressorList@@SAJPEBDPEAPEAVCCabDecompressor@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(PCNZCH lpString1, struct CCabDecompressor **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180098bfc`

## callees

- `0x180005690`
- `0x180006ac4`
- `0x180007ecc`
- `0x180099184`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099222`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099293`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099222`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180099293`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800991cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800991cc`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180099206`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180099206`

## string_xrefs

- `0x1800991a8`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressorList.cpp`
- `0x18009922d`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressorList.cpp`

## pseudocode

```c
int __fastcall CCabDecompressorList::RemoveNode(PCNZCH lpString1, struct CCabDecompressor **a2)
{
  unsigned int v2; // ebx
  bool v4; // zf
  unsigned int lpString2; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  v4 = CCabDecompressorList::m_fInited == 0;
  *a2 = 0;
  if ( v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressorList.cpp",
      (const char *)0x80070490LL,
      lpString2);
    return -2147023728;
  }
  else
  {
    EnterCriticalSection(&stru_1800EE3D0);
    if ( dword_1800EE3C4 )
    {
      while ( CompareStringA(0x7Fu, 1u, lpString1, -1, *(PCNZCH *)(*(_QWORD *)(qword_1800EE3B8 + 8LL * v2) + 48LL), -1) != 2 )
      {
        if ( ++v2 >= dword_1800EE3C4 )
          goto LABEL_6;
      }
      if ( v2 < dword_1800EE3C4 )
      {
        *a2 = *(struct CCabDecompressor **)(qword_1800EE3B8 + 8LL * v2);
        *(_QWORD *)(qword_1800EE3B8 + 8LL * v2) = 0;
        CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::RemoveArraySection(
          &CCabDecompressorList::m_CabDecompressorList,
          v2,
          v2);
      }
      else
      {
        *a2 = 0;
      }
      LeaveCriticalSection(&stru_1800EE3D0);
      return 0;
    }
    else
    {
LABEL_6:
      LeaveCriticalSection(&stru_1800EE3D0);
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xAF,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressorList.cpp",
               (const char *)0x490,
               lpString2);
    }
  }
}

```

## disassembly

```asm
0x180099184  mov     [rsp+arg_10], rbx
0x180099189  push    rbp
0x18009918a  push    rsi
0x18009918b  push    rdi
0x18009918c  sub     rsp, 30h
0x180099190  xor     ebx, ebx
0x180099192  mov     rdi, rdx
0x180099195  cmp     cs:?m_fInited@CCabDecompressorList@@0HA, ebx; int CCabDecompressorList::m_fInited
0x18009919b  mov     rbp, rcx
0x18009919e  mov     [rdx], rbx
0x1800991a1  jnz     short loc_1800991C5
0x1800991a3  mov     rcx, [rsp+48h]; this
0x1800991a8  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x1800991af  mov     ebx, 80070490h
0x1800991b4  mov     edx, 9Dh; void *
0x1800991b9  mov     r9d, ebx; char *
0x1800991bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800991c1  mov     eax, ebx
0x1800991c3  jmp     short loc_180099244
0x1800991c5  lea     rcx, stru_1800EE3D0; lpCriticalSection
0x1800991cc  call    cs:__imp_EnterCriticalSection
0x1800991d2  cmp     cs:dword_1800EE3C4, ebx
0x1800991d8  jbe     short loc_18009921B
0x1800991da  mov     esi, ebx
0x1800991dc  mov     rax, cs:qword_1800EE3B8
0x1800991e3  or      r9d, 0FFFFFFFFh; cchCount1
0x1800991e7  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800991ef  mov     r8, rbp; lpString1
0x1800991f2  mov     rax, [rax+rsi*8]
0x1800991f6  lea     edx, [r9+2]; dwCmpFlags
0x1800991fa  lea     ecx, [rdx+7Eh]; Locale
0x1800991fd  mov     rax, [rax+30h]
0x180099201  mov     [rsp+48h+lpString2], rax; unsigned int
0x180099206  call    cs:__imp_CompareStringA
0x18009920c  cmp     eax, 2
0x18009920f  jz      short loc_180099251
0x180099211  inc     ebx
0x180099213  cmp     ebx, cs:dword_1800EE3C4
0x180099219  jb      short loc_1800991DA
0x18009921b  lea     rcx, stru_1800EE3D0; lpCriticalSection
0x180099222  call    cs:__imp_LeaveCriticalSection
0x180099228  mov     rcx, [rsp+48h]; this
0x18009922d  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180099234  mov     r9d, 490h; char *
0x18009923a  mov     edx, 0AFh; void *
0x18009923f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180099244  mov     rbx, [rsp+48h+arg_10]
0x180099249  add     rsp, 30h
0x18009924d  pop     rdi
0x18009924e  pop     rsi
0x18009924f  pop     rbp
0x180099250  retn
0x180099251  cmp     ebx, cs:dword_1800EE3C4
0x180099257  jb      short loc_180099260
0x180099259  xor     eax, eax
0x18009925b  mov     [rdi], rax
0x18009925e  jmp     short loc_18009928C
0x180099260  mov     rax, cs:qword_1800EE3B8
0x180099267  lea     rcx, ?m_CabDecompressorList@CCabDecompressorList@@0V?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@A; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>> CCabDecompressorList::m_CabDecompressorList
0x18009926e  xor     edx, edx
0x180099270  mov     r8, [rax+rsi*8]
0x180099274  mov     [rdi], r8
0x180099277  mov     r8d, ebx
0x18009927a  mov     rax, cs:qword_1800EE3B8
0x180099281  mov     [rax+rsi*8], rdx
0x180099285  mov     edx, ebx
0x180099287  call    ?RemoveArraySection@?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@IEAAXKKH@Z; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::RemoveArraySection(ulong,ulong,int)
0x18009928c  lea     rcx, stru_1800EE3D0; lpCriticalSection
0x180099293  call    cs:__imp_LeaveCriticalSection
0x180099299  xor     eax, eax
0x18009929b  jmp     short loc_180099244
```
