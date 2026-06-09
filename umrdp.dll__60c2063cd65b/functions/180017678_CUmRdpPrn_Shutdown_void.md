# CUmRdpPrn::Shutdown(void)

- ea: `0x180017678`
- end: `0x1800177f2`
- name: `?Shutdown@CUmRdpPrn@@QEAAHXZ`
- size: `378`
- prototype: `__int64 __fastcall(CUmRdpPrn *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800130e8`

## callees

- `0x180014570`
- `0x180017678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800177d4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800177d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800176a7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800176a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017723`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017751`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001777f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800177a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017723`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017751`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001777f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800177a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800176e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800176e2`
- `WINSPOOL!ClosePrinter` at `0x1800176fb`
- `WINSPOOL!ClosePrinter` at `0x1800176fb`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::Shutdown(CUmRdpPrn *this)
{
  HMODULE v2; // rcx
  HKEY v3; // rcx
  void *v4; // rcx
  void *v5; // r8
  void *v6; // r8
  void *v7; // r8
  void *v8; // r8

  *((_DWORD *)this + 53) = 0;
  if ( *((_DWORD *)this + 7) )
  {
    v2 = (HMODULE)*((_QWORD *)this + 20);
    if ( v2 )
    {
      FreeLibrary(v2);
      *((_QWORD *)this + 20) = 0;
    }
    *((_QWORD *)this + 21) = 0;
    *((_QWORD *)this + 22) = 0;
    CUmRdpPrn::CloseWaitablePrintingObjects(this);
    v3 = (HKEY)*((_QWORD *)this + 16);
    *((_QWORD *)this + 15) = 0;
    *((_QWORD *)this + 5) = 0;
    if ( v3 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      RegCloseKey(v3);
      *((_QWORD *)this + 16) = -1;
    }
    v4 = (void *)*((_QWORD *)this + 24);
    if ( v4 )
    {
      ClosePrinter(v4);
      *((_QWORD *)this + 24) = 0;
    }
    v5 = (void *)*((_QWORD *)this + 25);
    if ( v5 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v5);
      *((_QWORD *)this + 25) = 0;
      *((_DWORD *)this + 52) = 0;
    }
    v6 = (void *)*((_QWORD *)this + 31);
    if ( v6 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v6);
      *((_QWORD *)this + 31) = 0;
      *((_DWORD *)this + 64) = 0;
    }
    v7 = (void *)*((_QWORD *)this + 29);
    if ( v7 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v7);
      *((_QWORD *)this + 29) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 30);
    if ( v8 )
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v8);
      *((_QWORD *)this + 30) = 0;
    }
    *((_QWORD *)this + 23) = -1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    *((_DWORD *)this + 7) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180017678  mov     [rsp+arg_0], rbx
0x18001767d  mov     [rsp+arg_8], rsi
0x180017682  push    rdi
0x180017683  sub     rsp, 20h
0x180017687  xor     esi, esi
0x180017689  mov     rdi, rcx
0x18001768c  mov     [rcx+0D4h], esi
0x180017692  cmp     [rcx+1Ch], esi
0x180017695  jz      loc_1800177DD
0x18001769b  mov     rcx, [rcx+0A0h]; hLibModule
0x1800176a2  test    rcx, rcx
0x1800176a5  jz      short loc_1800176B4
0x1800176a7  call    cs:__imp_FreeLibrary
0x1800176ad  mov     [rdi+0A0h], rsi
0x1800176b4  mov     rcx, rdi; this
0x1800176b7  mov     [rdi+0A8h], rsi
0x1800176be  mov     [rdi+0B0h], rsi
0x1800176c5  call    ?CloseWaitablePrintingObjects@CUmRdpPrn@@AEAAXXZ; CUmRdpPrn::CloseWaitablePrintingObjects(void)
0x1800176ca  mov     rcx, [rdi+80h]; hKey
0x1800176d1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800176d5  mov     [rdi+78h], rsi
0x1800176d9  mov     [rdi+28h], rsi
0x1800176dd  cmp     rcx, rbx
0x1800176e0  jz      short loc_1800176EF
0x1800176e2  call    cs:__imp_RegCloseKey
0x1800176e8  mov     [rdi+80h], rbx
0x1800176ef  mov     rcx, [rdi+0C0h]; hPrinter
0x1800176f6  test    rcx, rcx
0x1800176f9  jz      short loc_180017708
0x1800176fb  call    cs:__imp_ClosePrinter
0x180017701  mov     [rdi+0C0h], rsi
0x180017708  mov     r8, [rdi+0C8h]; lpMem
0x18001770f  test    r8, r8
0x180017712  jz      short loc_180017736
0x180017714  mov     rcx, gs:60h
0x18001771d  xor     edx, edx; dwFlags
0x18001771f  mov     rcx, [rcx+30h]; hHeap
0x180017723  call    cs:__imp_HeapFree
0x180017729  mov     [rdi+0C8h], rsi
0x180017730  mov     [rdi+0D0h], esi
0x180017736  mov     r8, [rdi+0F8h]; lpMem
0x18001773d  test    r8, r8
0x180017740  jz      short loc_180017764
0x180017742  mov     rcx, gs:60h
0x18001774b  xor     edx, edx; dwFlags
0x18001774d  mov     rcx, [rcx+30h]; hHeap
0x180017751  call    cs:__imp_HeapFree
0x180017757  mov     [rdi+0F8h], rsi
0x18001775e  mov     [rdi+100h], esi
0x180017764  mov     r8, [rdi+0E8h]; lpMem
0x18001776b  test    r8, r8
0x18001776e  jz      short loc_18001778C
0x180017770  mov     rcx, gs:60h
0x180017779  xor     edx, edx; dwFlags
0x18001777b  mov     rcx, [rcx+30h]; hHeap
0x18001777f  call    cs:__imp_HeapFree
0x180017785  mov     [rdi+0E8h], rsi
0x18001778c  mov     r8, [rdi+0F0h]; lpMem
0x180017793  test    r8, r8
0x180017796  jz      short loc_1800177B4
0x180017798  mov     rcx, gs:60h
0x1800177a1  xor     edx, edx; dwFlags
0x1800177a3  mov     rcx, [rcx+30h]; hHeap
0x1800177a7  call    cs:__imp_HeapFree
0x1800177ad  mov     [rdi+0F0h], rsi
0x1800177b4  mov     [rdi+0B8h], rbx
0x1800177bb  lea     rbx, [rdi+30h]
0x1800177bf  mov     rcx, rbx; lpCriticalSection
0x1800177c2  call    cs:__imp_EnterCriticalSection
0x1800177c8  mov     rcx, rbx; lpCriticalSection
0x1800177cb  call    cs:__imp_LeaveCriticalSection
0x1800177d1  mov     rcx, rbx; lpCriticalSection
0x1800177d4  call    cs:__imp_DeleteCriticalSection
0x1800177da  mov     [rdi+1Ch], esi
0x1800177dd  mov     rbx, [rsp+28h+arg_0]
0x1800177e2  mov     eax, 1
0x1800177e7  mov     rsi, [rsp+28h+arg_8]
0x1800177ec  add     rsp, 20h
0x1800177f0  pop     rdi
0x1800177f1  retn
```
