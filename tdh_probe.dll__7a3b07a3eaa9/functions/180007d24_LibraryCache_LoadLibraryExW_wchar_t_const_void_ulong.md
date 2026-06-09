# LibraryCache::LoadLibraryExW(wchar_t const *,void *,ulong)

- ea: `0x180007d24`
- end: `0x180007e71`
- name: `?LoadLibraryExW@LibraryCache@@QEAAPEAUHINSTANCE__@@PEB_WPEAXK@Z`
- size: `333`
- prototype: `HINSTANCE(LibraryCache *__hidden this, const wchar_t *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a70`

## callees

- `0x180007d24`
- `0x180021454`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007daf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007daf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dfc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007dfc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007dee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007dee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007de3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007de3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007dd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007dc6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007dc6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007d6a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007d6a`

## pseudocode

```c
HINSTANCE __fastcall LibraryCache::LoadLibraryExW(LibraryCache *this, const wchar_t *a2, void *a3)
{
  LPVOID *v4; // rbx
  __int64 v5; // rdi
  HMODULE Library; // rdi
  unsigned __int64 v7; // rbp
  HANDLE ProcessHeap; // rax
  DWORD LastError; // edi
  wchar_t *v10; // rbx
  HANDLE v11; // rax
  wchar_t **v13; // rax

  EnterCriticalSection(&g_LibraryCache);
  v4 = (LPVOID *)lpMem;
  v5 = -1;
  while ( v4 != &lpMem )
  {
    if ( CompareStringOrdinal((LPCWCH)v4 + 14, -1, a2, -1, 1) == 2 )
    {
      ++*((_DWORD *)v4 + 6);
      Library = (HMODULE)v4[2];
LABEL_16:
      LeaveCriticalSection(&g_LibraryCache);
      return Library;
    }
    v4 = (LPVOID *)*v4;
  }
  do
    ++v5;
  while ( a2[v5] );
  v7 = 2 * v5 + 2;
  ProcessHeap = GetProcessHeap();
  LastError = 8;
  v10 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v7 + 28);
  if ( v10 )
  {
    Library = LoadLibraryExW(a2, 0, 0x60u);
    if ( Library )
    {
      wcscpy_s(v10 + 14, v7 >> 1, a2);
      *((_DWORD *)v10 + 6) = 1;
      *((_QWORD *)v10 + 2) = Library;
      v13 = (wchar_t **)off_18006A040[0];
      if ( *(LPVOID **)off_18006A040[0] != &lpMem )
        __fastfail(3u);
      *(_QWORD *)v10 = &lpMem;
      *((_QWORD *)v10 + 1) = v13;
      *v13 = v10;
      off_18006A040[0] = (_UNKNOWN **)v10;
      goto LABEL_16;
    }
    LastError = GetLastError();
  }
  LeaveCriticalSection(&g_LibraryCache);
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x180007d24  push    rbx
0x180007d26  push    rbp
0x180007d27  push    rsi
0x180007d28  push    rdi
0x180007d29  push    r14
0x180007d2b  sub     rsp, 30h
0x180007d2f  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x180007d36  mov     rsi, rdx
0x180007d39  call    cs:__imp_EnterCriticalSection
0x180007d3f  mov     rbx, cs:lpMem
0x180007d46  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007d4a  lea     rax, lpMem
0x180007d51  cmp     rbx, rax
0x180007d54  jz      short loc_180007D86
0x180007d56  lea     rcx, [rbx+1Ch]; lpString1
0x180007d5a  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180007d62  mov     r9d, edi; cchCount2
0x180007d65  mov     r8, rsi; lpString2
0x180007d68  mov     edx, edi; cchCount1
0x180007d6a  call    cs:__imp_CompareStringOrdinal
0x180007d70  cmp     eax, 2
0x180007d73  jz      short loc_180007D7A
0x180007d75  mov     rbx, [rbx]
0x180007d78  jmp     short loc_180007D4A
0x180007d7a  inc     dword ptr [rbx+18h]
0x180007d7d  mov     rdi, [rbx+10h]
0x180007d81  jmp     loc_180007E56
0x180007d86  xor     r14d, r14d
0x180007d89  inc     rdi
0x180007d8c  cmp     [rsi+rdi*2], r14w
0x180007d91  jnz     short loc_180007D89
0x180007d93  lea     rbp, ds:2[rdi*2]
0x180007d9b  call    cs:__imp_GetProcessHeap
0x180007da1  mov     edi, 8
0x180007da6  lea     r8, [rbp+1Ch]; dwBytes
0x180007daa  mov     rcx, rax; hHeap
0x180007dad  mov     edx, edi; dwFlags
0x180007daf  call    cs:__imp_HeapAlloc
0x180007db5  mov     rbx, rax
0x180007db8  test    rax, rax
0x180007dbb  jz      short loc_180007DDC
0x180007dbd  xor     edx, edx; hFile
0x180007dbf  lea     r8d, [rdi+58h]; dwFlags
0x180007dc3  mov     rcx, rsi; lpLibFileName
0x180007dc6  call    cs:__imp_LoadLibraryExW
0x180007dcc  mov     rdi, rax
0x180007dcf  test    rax, rax
0x180007dd2  jnz     short loc_180007E0E
0x180007dd4  call    cs:__imp_GetLastError
0x180007dda  mov     edi, eax
0x180007ddc  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x180007de3  call    cs:__imp_LeaveCriticalSection
0x180007de9  test    rbx, rbx
0x180007dec  jz      short loc_180007E02
0x180007dee  call    cs:__imp_GetProcessHeap
0x180007df4  mov     r8, rbx; lpMem
0x180007df7  xor     edx, edx; dwFlags
0x180007df9  mov     rcx, rax; hHeap
0x180007dfc  call    cs:__imp_HeapFree
0x180007e02  mov     ecx, edi; dwErrCode
0x180007e04  call    cs:__imp_SetLastError
0x180007e0a  xor     eax, eax
0x180007e0c  jmp     short loc_180007E66
0x180007e0e  shr     rbp, 1
0x180007e11  lea     rcx, [rbx+1Ch]; Destination
0x180007e15  mov     rdx, rbp; SizeInWords
0x180007e18  mov     r8, rsi; Source
0x180007e1b  call    wcscpy_s
0x180007e20  mov     dword ptr [rbx+18h], 1
0x180007e27  lea     rcx, lpMem
0x180007e2e  mov     [rbx+10h], rdi
0x180007e32  mov     rax, cs:off_18006A040
0x180007e39  cmp     [rax], rcx
0x180007e3c  jz      short loc_180007E45
0x180007e3e  mov     ecx, 3
0x180007e43  int     29h; Win8: RtlFailFast(ecx)
0x180007e45  mov     [rbx], rcx
0x180007e48  mov     [rbx+8], rax
0x180007e4c  mov     [rax], rbx
0x180007e4f  mov     cs:off_18006A040, rbx
0x180007e56  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x180007e5d  call    cs:__imp_LeaveCriticalSection
0x180007e63  mov     rax, rdi
0x180007e66  add     rsp, 30h
0x180007e6a  pop     r14
0x180007e6c  pop     rdi
0x180007e6d  pop     rsi
0x180007e6e  pop     rbp
0x180007e6f  pop     rbx
0x180007e70  retn
```
