# CCabDecompressorList::RemoveNode(char const *,CCabDecompressor * *)

- ea: `0x180016684`
- end: `0x18001679d`
- name: `?RemoveNode@CCabDecompressorList@@SAJPEBDPEAPEAVCCabDecompressor@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(PCNZCH lpString1, struct CCabDecompressor **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015dfc`

## callees

- `0x180003950`
- `0x18000b658`
- `0x180016684`
- `0x18001689c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016722`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016722`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016793`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800166cc`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180016706`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180016706`

## string_xrefs

- `0x1800166a8`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressorList.cpp`
- `0x18001672d`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressorList.cpp`

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
    EnterCriticalSection(&CriticalSection);
    if ( dword_180075684 )
    {
      while ( CompareStringA(0x7Fu, 1u, lpString1, -1, *(PCNZCH *)(*(_QWORD *)(qword_180075678 + 8LL * v2) + 48LL), -1) != 2 )
      {
        if ( ++v2 >= dword_180075684 )
          goto LABEL_6;
      }
      if ( v2 < dword_180075684 )
      {
        *a2 = *(struct CCabDecompressor **)(qword_180075678 + 8LL * v2);
        *(_QWORD *)(qword_180075678 + 8LL * v2) = 0;
        CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::RemoveArraySection(
          &CCabDecompressorList::m_CabDecompressorList,
          v2,
          v2);
      }
      else
      {
        *a2 = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      return 0;
    }
    else
    {
LABEL_6:
      LeaveCriticalSection(&CriticalSection);
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
0x180016684  mov     [rsp+arg_10], rbx
0x180016689  push    rbp
0x18001668a  push    rsi
0x18001668b  push    rdi
0x18001668c  sub     rsp, 30h
0x180016690  xor     ebx, ebx
0x180016692  mov     rdi, rdx
0x180016695  cmp     cs:?m_fInited@CCabDecompressorList@@0HA, ebx; int CCabDecompressorList::m_fInited
0x18001669b  mov     rbp, rcx
0x18001669e  mov     [rdx], rbx
0x1800166a1  jnz     short loc_1800166C5
0x1800166a3  mov     rcx, [rsp+48h]; this
0x1800166a8  lea     r8, aCW1SSrcClientL_6; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x1800166af  mov     ebx, 80070490h
0x1800166b4  mov     edx, 9Dh; void *
0x1800166b9  mov     r9d, ebx; char *
0x1800166bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800166c1  mov     eax, ebx
0x1800166c3  jmp     short loc_180016744
0x1800166c5  lea     rcx, CriticalSection; lpCriticalSection
0x1800166cc  call    cs:__imp_EnterCriticalSection
0x1800166d2  cmp     cs:dword_180075684, ebx
0x1800166d8  jbe     short loc_18001671B
0x1800166da  mov     esi, ebx
0x1800166dc  mov     rax, cs:qword_180075678
0x1800166e3  or      r9d, 0FFFFFFFFh; cchCount1
0x1800166e7  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800166ef  mov     r8, rbp; lpString1
0x1800166f2  mov     rax, [rax+rsi*8]
0x1800166f6  lea     edx, [r9+2]; dwCmpFlags
0x1800166fa  lea     ecx, [rdx+7Eh]; Locale
0x1800166fd  mov     rax, [rax+30h]
0x180016701  mov     [rsp+48h+lpString2], rax; unsigned int
0x180016706  call    cs:__imp_CompareStringA
0x18001670c  cmp     eax, 2
0x18001670f  jz      short loc_180016751
0x180016711  inc     ebx
0x180016713  cmp     ebx, cs:dword_180075684
0x180016719  jb      short loc_1800166DA
0x18001671b  lea     rcx, CriticalSection; lpCriticalSection
0x180016722  call    cs:__imp_LeaveCriticalSection
0x180016728  mov     rcx, [rsp+48h]; this
0x18001672d  lea     r8, aCW1SSrcClientL_6; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x180016734  mov     r9d, 490h; char *
0x18001673a  mov     edx, 0AFh; void *
0x18001673f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180016744  mov     rbx, [rsp+48h+arg_10]
0x180016749  add     rsp, 30h
0x18001674d  pop     rdi
0x18001674e  pop     rsi
0x18001674f  pop     rbp
0x180016750  retn
0x180016751  cmp     ebx, cs:dword_180075684
0x180016757  jb      short loc_180016760
0x180016759  xor     eax, eax
0x18001675b  mov     [rdi], rax
0x18001675e  jmp     short loc_18001678C
0x180016760  mov     rax, cs:qword_180075678
0x180016767  lea     rcx, ?m_CabDecompressorList@CCabDecompressorList@@0V?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@A; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>> CCabDecompressorList::m_CabDecompressorList
0x18001676e  xor     edx, edx
0x180016770  mov     r8, [rax+rsi*8]
0x180016774  mov     [rdi], r8
0x180016777  mov     r8d, ebx
0x18001677a  mov     rax, cs:qword_180075678
0x180016781  mov     [rax+rsi*8], rdx
0x180016785  mov     edx, ebx
0x180016787  call    ?RemoveArraySection@?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@IEAAXKKH@Z; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::RemoveArraySection(ulong,ulong,int)
0x18001678c  lea     rcx, CriticalSection; lpCriticalSection
0x180016793  call    cs:__imp_LeaveCriticalSection
0x180016799  xor     eax, eax
0x18001679b  jmp     short loc_180016744
```
