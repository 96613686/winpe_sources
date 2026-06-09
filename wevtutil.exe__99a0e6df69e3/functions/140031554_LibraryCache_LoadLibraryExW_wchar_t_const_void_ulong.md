# LibraryCache::LoadLibraryExW(wchar_t const *,void *,ulong)

- ea: `0x140031554`
- end: `0x1400316a1`
- name: `?LoadLibraryExW@LibraryCache@@QEAAPEAUHINSTANCE__@@PEB_WPEAXK@Z`
- size: `333`
- prototype: `HINSTANCE(LibraryCache *__hidden this, const wchar_t *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400310e4`

## callees

- `0x1400224e0`
- `0x140031554`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003162c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003162c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400315cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003161e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400315cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003161e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400315df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400315df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14003159a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14003159a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400315f6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400315f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031604`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140031634`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140031634`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140031613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003168d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140031613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003168d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140031569`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140031569`

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
      v13 = (wchar_t **)off_140042278[0];
      if ( *(LPVOID **)off_140042278[0] != &lpMem )
        __fastfail(3u);
      *(_QWORD *)v10 = &lpMem;
      *((_QWORD *)v10 + 1) = v13;
      *v13 = v10;
      off_140042278[0] = (_UNKNOWN **)v10;
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
0x140031554  push    rbx
0x140031556  push    rbp
0x140031557  push    rsi
0x140031558  push    rdi
0x140031559  push    r14
0x14003155b  sub     rsp, 30h
0x14003155f  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x140031566  mov     rsi, rdx
0x140031569  call    cs:__imp_EnterCriticalSection
0x14003156f  mov     rbx, cs:lpMem
0x140031576  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14003157a  lea     rax, lpMem
0x140031581  cmp     rbx, rax
0x140031584  jz      short loc_1400315B6
0x140031586  lea     rcx, [rbx+1Ch]; lpString1
0x14003158a  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x140031592  mov     r9d, edi; cchCount2
0x140031595  mov     r8, rsi; lpString2
0x140031598  mov     edx, edi; cchCount1
0x14003159a  call    cs:__imp_CompareStringOrdinal
0x1400315a0  cmp     eax, 2
0x1400315a3  jz      short loc_1400315AA
0x1400315a5  mov     rbx, [rbx]
0x1400315a8  jmp     short loc_14003157A
0x1400315aa  inc     dword ptr [rbx+18h]
0x1400315ad  mov     rdi, [rbx+10h]
0x1400315b1  jmp     loc_140031686
0x1400315b6  xor     r14d, r14d
0x1400315b9  inc     rdi
0x1400315bc  cmp     [rsi+rdi*2], r14w
0x1400315c1  jnz     short loc_1400315B9
0x1400315c3  lea     rbp, ds:2[rdi*2]
0x1400315cb  call    cs:__imp_GetProcessHeap
0x1400315d1  mov     edi, 8
0x1400315d6  lea     r8, [rbp+1Ch]; dwBytes
0x1400315da  mov     rcx, rax; hHeap
0x1400315dd  mov     edx, edi; dwFlags
0x1400315df  call    cs:__imp_HeapAlloc
0x1400315e5  mov     rbx, rax
0x1400315e8  test    rax, rax
0x1400315eb  jz      short loc_14003160C
0x1400315ed  xor     edx, edx; hFile
0x1400315ef  lea     r8d, [rdi+58h]; dwFlags
0x1400315f3  mov     rcx, rsi; lpLibFileName
0x1400315f6  call    cs:__imp_LoadLibraryExW
0x1400315fc  mov     rdi, rax
0x1400315ff  test    rax, rax
0x140031602  jnz     short loc_14003163E
0x140031604  call    cs:__imp_GetLastError
0x14003160a  mov     edi, eax
0x14003160c  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x140031613  call    cs:__imp_LeaveCriticalSection
0x140031619  test    rbx, rbx
0x14003161c  jz      short loc_140031632
0x14003161e  call    cs:__imp_GetProcessHeap
0x140031624  mov     r8, rbx; lpMem
0x140031627  xor     edx, edx; dwFlags
0x140031629  mov     rcx, rax; hHeap
0x14003162c  call    cs:__imp_HeapFree
0x140031632  mov     ecx, edi; dwErrCode
0x140031634  call    cs:__imp_SetLastError
0x14003163a  xor     eax, eax
0x14003163c  jmp     short loc_140031696
0x14003163e  shr     rbp, 1
0x140031641  lea     rcx, [rbx+1Ch]; Destination
0x140031645  mov     rdx, rbp; SizeInWords
0x140031648  mov     r8, rsi; Source
0x14003164b  call    wcscpy_s
0x140031650  mov     dword ptr [rbx+18h], 1
0x140031657  lea     rcx, lpMem
0x14003165e  mov     [rbx+10h], rdi
0x140031662  mov     rax, cs:off_140042278
0x140031669  cmp     [rax], rcx
0x14003166c  jz      short loc_140031675
0x14003166e  mov     ecx, 3
0x140031673  int     29h; Win8: RtlFailFast(ecx)
0x140031675  mov     [rbx], rcx
0x140031678  mov     [rbx+8], rax
0x14003167c  mov     [rax], rbx
0x14003167f  mov     cs:off_140042278, rbx
0x140031686  lea     rcx, ?g_LibraryCache@@3VLibraryCache@@A; lpCriticalSection
0x14003168d  call    cs:__imp_LeaveCriticalSection
0x140031693  mov     rax, rdi
0x140031696  add     rsp, 30h
0x14003169a  pop     r14
0x14003169c  pop     rdi
0x14003169d  pop     rsi
0x14003169e  pop     rbp
0x14003169f  pop     rbx
0x1400316a0  retn
```
