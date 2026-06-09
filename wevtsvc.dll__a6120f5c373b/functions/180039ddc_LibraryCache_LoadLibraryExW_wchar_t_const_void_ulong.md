# LibraryCache::LoadLibraryExW(wchar_t const *,void *,ulong)

- ea: `0x180039ddc`
- end: `0x180039f29`
- name: `?LoadLibraryExW@LibraryCache@@QEAAPEAUHINSTANCE__@@PEB_WPEAXK@Z`
- size: `333`
- prototype: `HINSTANCE __fastcall(LibraryCache *this, const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180039c70`

## callees

- `0x180039ddc`
- `0x18009bb4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039eb4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039eb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039ea6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e53`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039ea6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039e9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039f15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039e9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039f15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039df1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039df1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039ebc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e8c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039e7e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039e7e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039e22`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180039e22`

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
      v13 = (wchar_t **)off_18010F1A0;
      if ( *off_18010F1A0 != (_UNKNOWN *)&lpMem )
        __fastfail(3u);
      *(_QWORD *)v10 = &lpMem;
      *((_QWORD *)v10 + 1) = v13;
      *v13 = v10;
      off_18010F1A0 = (_UNKNOWN **)v10;
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
0x180039ddc  push    rbx
0x180039dde  push    rbp
0x180039ddf  push    rsi
0x180039de0  push    rdi
0x180039de1  push    r14
0x180039de3  sub     rsp, 30h
0x180039de7  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x180039dee  mov     rsi, rdx
0x180039df1  call    cs:__imp_EnterCriticalSection
0x180039df7  mov     rbx, cs:lpMem
0x180039dfe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180039e02  lea     rax, lpMem
0x180039e09  cmp     rbx, rax
0x180039e0c  jz      short loc_180039E3E
0x180039e0e  lea     rcx, [rbx+1Ch]; lpString1
0x180039e12  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180039e1a  mov     r9d, edi; cchCount2
0x180039e1d  mov     r8, rsi; lpString2
0x180039e20  mov     edx, edi; cchCount1
0x180039e22  call    cs:__imp_CompareStringOrdinal
0x180039e28  cmp     eax, 2
0x180039e2b  jz      short loc_180039E32
0x180039e2d  mov     rbx, [rbx]
0x180039e30  jmp     short loc_180039E02
0x180039e32  inc     dword ptr [rbx+18h]
0x180039e35  mov     rdi, [rbx+10h]
0x180039e39  jmp     loc_180039F0E
0x180039e3e  xor     r14d, r14d
0x180039e41  inc     rdi
0x180039e44  cmp     [rsi+rdi*2], r14w
0x180039e49  jnz     short loc_180039E41
0x180039e4b  lea     rbp, ds:2[rdi*2]
0x180039e53  call    cs:__imp_GetProcessHeap
0x180039e59  mov     edi, 8
0x180039e5e  lea     r8, [rbp+1Ch]; dwBytes
0x180039e62  mov     rcx, rax; hHeap
0x180039e65  mov     edx, edi; dwFlags
0x180039e67  call    cs:__imp_HeapAlloc
0x180039e6d  mov     rbx, rax
0x180039e70  test    rax, rax
0x180039e73  jz      short loc_180039E94
0x180039e75  xor     edx, edx; hFile
0x180039e77  lea     r8d, [rdi+58h]; dwFlags
0x180039e7b  mov     rcx, rsi; lpLibFileName
0x180039e7e  call    cs:__imp_LoadLibraryExW
0x180039e84  mov     rdi, rax
0x180039e87  test    rax, rax
0x180039e8a  jnz     short loc_180039EC6
0x180039e8c  call    cs:__imp_GetLastError
0x180039e92  mov     edi, eax
0x180039e94  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x180039e9b  call    cs:__imp_LeaveCriticalSection
0x180039ea1  test    rbx, rbx
0x180039ea4  jz      short loc_180039EBA
0x180039ea6  call    cs:__imp_GetProcessHeap
0x180039eac  mov     r8, rbx; lpMem
0x180039eaf  xor     edx, edx; dwFlags
0x180039eb1  mov     rcx, rax; hHeap
0x180039eb4  call    cs:__imp_HeapFree
0x180039eba  mov     ecx, edi; dwErrCode
0x180039ebc  call    cs:__imp_SetLastError
0x180039ec2  xor     eax, eax
0x180039ec4  jmp     short loc_180039F1E
0x180039ec6  shr     rbp, 1
0x180039ec9  lea     rcx, [rbx+1Ch]; Destination
0x180039ecd  mov     rdx, rbp; SizeInWords
0x180039ed0  mov     r8, rsi; Source
0x180039ed3  call    wcscpy_s
0x180039ed8  mov     dword ptr [rbx+18h], 1
0x180039edf  lea     rcx, lpMem
0x180039ee6  mov     [rbx+10h], rdi
0x180039eea  mov     rax, cs:off_18010F1A0
0x180039ef1  cmp     [rax], rcx
0x180039ef4  jz      short loc_180039EFD
0x180039ef6  mov     ecx, 3
0x180039efb  int     29h; Win8: RtlFailFast(ecx)
0x180039efd  mov     [rbx], rcx
0x180039f00  mov     [rbx+8], rax
0x180039f04  mov     [rax], rbx
0x180039f07  mov     cs:off_18010F1A0, rbx
0x180039f0e  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x180039f15  call    cs:__imp_LeaveCriticalSection
0x180039f1b  mov     rax, rdi
0x180039f1e  add     rsp, 30h
0x180039f22  pop     r14
0x180039f24  pop     rdi
0x180039f25  pop     rsi
0x180039f26  pop     rbp
0x180039f27  pop     rbx
0x180039f28  retn
```
