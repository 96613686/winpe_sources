# NewHandle

- ea: `0x18000aef0`
- end: `0x18000af74`
- name: `NewHandle`
- size: `132`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800048e0`
- `0x180005030`
- `0x18000a960`
- `0x180011c1c`
- `0x180011f20`
- `0x180012180`
- `0x180017d30`
- `0x180018e40`
- `0x180019920`

## callees

- `0x18000aef0`
- `0x18001102a`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af0e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af3d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000af37`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000af37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000af57`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall NewHandle(LONG a1, ULONG_PTR a2, unsigned int a3)
{
  __int64 v3; // rdi
  struct _RTL_CRITICAL_SECTION *result; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  DWORD CurrentThreadId; // eax

  v3 = a3;
  result = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(hHeap, 0, a3 + 80LL);
  v7 = result;
  if ( result )
  {
    memset_0(result, 0, v3 + 80);
    InitializeCriticalSection(v7 + 1);
    CurrentThreadId = GetCurrentThreadId();
    v7->LockCount = a1;
    v7->OwningThread = (HANDLE)CurrentThreadId;
    v7->SpinCount = a2;
    EnterCriticalSection(&HandleListCritSec);
    v7->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)pHandleList;
    result = v7 + 2;
    pHandleList = (unsigned __int64)v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000aef0  push    rbx
0x18000aef2  push    rbp
0x18000aef3  push    rsi
0x18000aef4  push    rdi
0x18000aef5  sub     rsp, 28h
0x18000aef9  mov     edi, r8d
0x18000aefc  mov     rsi, rdx
0x18000aeff  mov     ebp, ecx
0x18000af01  xor     edx, edx; dwFlags
0x18000af03  mov     rcx, cs:hHeap; hHeap
0x18000af0a  lea     r8, [rdi+50h]; dwBytes
0x18000af0e  call    cs:__imp_HeapAlloc
0x18000af14  mov     rbx, rax
0x18000af17  test    rax, rax
0x18000af1a  jnz     short loc_18000AF25
0x18000af1c  add     rsp, 28h
0x18000af20  pop     rdi
0x18000af21  pop     rsi
0x18000af22  pop     rbp
0x18000af23  pop     rbx
0x18000af24  retn
0x18000af25  lea     r8, [rdi+50h]; Size
0x18000af29  xor     edx, edx; Val
0x18000af2b  mov     rcx, rbx; void *
0x18000af2e  call    memset_0
0x18000af33  lea     rcx, [rbx+28h]; lpCriticalSection
0x18000af37  call    cs:__imp_InitializeCriticalSection
0x18000af3d  call    cs:__imp_GetCurrentThreadId
0x18000af43  lea     rcx, HandleListCritSec; lpCriticalSection
0x18000af4a  mov     [rbx+8], ebp
0x18000af4d  mov     eax, eax
0x18000af4f  mov     [rbx+10h], rax
0x18000af53  mov     [rbx+20h], rsi
0x18000af57  call    cs:__imp_EnterCriticalSection
0x18000af5d  mov     rax, cs:pHandleList
0x18000af64  mov     [rbx], rax
0x18000af67  lea     rax, [rbx+50h]
0x18000af6b  mov     cs:pHandleList, rbx
0x18000af72  jmp     short loc_18000AF1C
```
