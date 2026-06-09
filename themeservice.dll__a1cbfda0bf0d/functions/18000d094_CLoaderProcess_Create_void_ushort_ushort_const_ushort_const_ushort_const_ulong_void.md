# CLoaderProcess::Create(void *,ushort *,ushort const *,ushort const *,ushort const *,ulong,void * *)

- ea: `0x18000d094`
- end: `0x18000d375`
- name: `?Create@CLoaderProcess@@QEAAJPEAXPEAGPEBG22KPEAPEAX@Z`
- size: `737`
- prototype: `__int64 __fastcall(CLoaderProcess *this, HANDLE hToken, unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpString, LPCWSTR, unsigned int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000aefc`

## callees

- `0x180002ae0`
- `0x18000674c`
- `0x180006a08`
- `0x18000cfa8`
- `0x18000d094`
- `0x18000f9da`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d348`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d348`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d14b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d178`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d19f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d1c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d14b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d178`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d19f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d1c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d1d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d1db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d1d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000d1db`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000d2cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000d2cc`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d200`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000d200`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d0e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d0f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d105`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d114`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d0e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d0f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d105`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000d114`

## string_xrefs

- `0x18000d10b`: `rundll32.exe uxtheme.dll,#64 %s?%s?%s`
- `0x18000d25e`: `rundll32.exe uxtheme.dll,#64 %s?%s?%s`

## pseudocode

```c
__int64 __fastcall CLoaderProcess::Create(
        CLoaderProcess *this,
        HANDLE hToken,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCWSTR lpString,
        LPCWSTR a6,
        unsigned int a7,
        void **a8)
{
  int v12; // ebx
  int v13; // edi
  int v14; // esi
  int v15; // ebp
  SIZE_T v16; // rax
  SIZE_T v17; // rax
  SIZE_T v18; // rax
  SIZE_T v19; // rax
  unsigned __int16 *v20; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v22; // rax
  unsigned int Error; // ebx
  struct _STARTUPINFOW StartupInfo; // [rsp+70h] [rbp-A8h] BYREF
  unsigned __int64 v26; // [rsp+120h] [rbp+8h]
  unsigned __int64 v27; // [rsp+158h] [rbp+40h]

  if ( a8 )
    *a8 = 0;
  CLoaderProcess::Clear(this, 1);
  *((_DWORD *)this + 14) = a7;
  v12 = lstrlenW(a4);
  v13 = lstrlenW(lpString);
  v14 = lstrlenW(a6);
  v27 = (unsigned int)(v12 + 1);
  v15 = v12 + v13 + v14 + lstrlenW(L"rundll32.exe uxtheme.dll,#64 %s?%s?%s");
  v16 = 2 * v27;
  if ( !is_mul_ok(v27, 2u) )
    v16 = -1;
  *((_QWORD *)this + 4) = HeapAlloc(s_hHeapToUse, 0, v16);
  v26 = (unsigned int)(v13 + 1);
  v17 = 2 * v26;
  if ( !is_mul_ok(v26, 2u) )
    v17 = -1;
  *((_QWORD *)this + 5) = HeapAlloc(s_hHeapToUse, 0, v17);
  v18 = 2LL * (unsigned int)(v14 + 1);
  if ( !is_mul_ok((unsigned int)(v14 + 1), 2u) )
    v18 = -1;
  *((_QWORD *)this + 6) = HeapAlloc(s_hHeapToUse, 0, v18);
  v19 = 2LL * (unsigned int)(v15 + 1);
  if ( !is_mul_ok((unsigned int)(v15 + 1), 2u) )
    v19 = -1;
  v20 = (unsigned __int16 *)HeapAlloc(s_hHeapToUse, 0, v19);
  CurrentProcess = GetCurrentProcess();
  v22 = GetCurrentProcess();
  if ( !DuplicateHandle(v22, hToken, CurrentProcess, (LPHANDLE)this + 3, 0, 0, 2u) )
    goto LABEL_19;
  if ( !*((_QWORD *)this + 4) || !*((_QWORD *)this + 5) || !*((_QWORD *)this + 6) || !v20 )
  {
    CLoaderProcess::Clear(this, 0);
    Error = -1073741801;
    goto LABEL_21;
  }
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.lpDesktop = L"WinSta0\\Default";
  StartupInfo.cb = 104;
  StartupInfo.dwFlags = 128;
  StringCchPrintfW(v20, (unsigned int)(v15 + 1), L"rundll32.exe uxtheme.dll,#64 %s?%s?%s", a4, lpString, a6);
  Error = 0;
  if ( CreateProcessAsUserW(hToken, 0, v20, 0, 0, 0, 0, 0, 0, &StartupInfo, (LPPROCESS_INFORMATION)this) )
  {
    StringCchCopyW(*((unsigned __int16 **)this + 4), v27, a4);
    StringCchCopyW(*((unsigned __int16 **)this + 5), v26, lpString);
    StringCchCopyW(*((unsigned __int16 **)this + 6), (unsigned int)(v14 + 1), a6);
    *((_DWORD *)this + 20) = 128;
    if ( a8 )
      *a8 = *(void **)this;
  }
  else
  {
LABEL_19:
    Error = CStatusCode::StatusCodeOfLastError();
  }
LABEL_21:
  HeapFree(s_hHeapToUse, 0, v20);
  *((_DWORD *)this + 20) = Error | 0x10000000;
  return Error;
}

```

## disassembly

```asm
0x18000d094  mov     [rsp+arg_8], rbx
0x18000d099  mov     [rsp+arg_10], r8
0x18000d09e  push    rbp
0x18000d09f  push    rsi
0x18000d0a0  push    rdi
0x18000d0a1  push    r12
0x18000d0a3  push    r13
0x18000d0a5  push    r14
0x18000d0a7  push    r15
0x18000d0a9  sub     rsp, 0E0h
0x18000d0b0  mov     r15, [rsp+118h+arg_38]
0x18000d0b8  mov     r12, r9
0x18000d0bb  mov     r13, rdx
0x18000d0be  mov     r14, rcx
0x18000d0c1  test    r15, r15
0x18000d0c4  jz      short loc_18000D0CD
0x18000d0c6  mov     qword ptr [r15], 0
0x18000d0cd  mov     edx, 1; int
0x18000d0d2  call    ?Clear@CLoaderProcess@@QEAAXH@Z; CLoaderProcess::Clear(int)
0x18000d0d7  mov     eax, [rsp+118h+arg_30]
0x18000d0de  mov     rcx, r12; lpString
0x18000d0e1  mov     [r14+38h], eax
0x18000d0e5  call    cs:__imp_lstrlenW
0x18000d0eb  mov     rcx, [rsp+118h+lpString]; lpString
0x18000d0f3  mov     ebx, eax
0x18000d0f5  call    cs:__imp_lstrlenW
0x18000d0fb  mov     rcx, [rsp+118h+arg_28]; lpString
0x18000d103  mov     edi, eax
0x18000d105  call    cs:__imp_lstrlenW
0x18000d10b  lea     rcx, String; "rundll32.exe uxtheme.dll,#64 %s?%s?%s"
0x18000d112  mov     esi, eax
0x18000d114  call    cs:__imp_lstrlenW
0x18000d11a  lea     ecx, [rbx+1]
0x18000d11d  mov     [rsp+118h+arg_38], rcx
0x18000d125  lea     ebp, [rsi+rax]
0x18000d128  mov     eax, 2
0x18000d12d  add     ebp, edi
0x18000d12f  add     ebp, ebx
0x18000d131  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000d138  mul     rcx
0x18000d13b  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d142  cmovb   rax, rbx
0x18000d146  xor     edx, edx; dwFlags
0x18000d148  mov     r8, rax; dwBytes
0x18000d14b  call    cs:__imp_HeapAlloc
0x18000d151  lea     ecx, [rdi+1]
0x18000d154  mov     [r14+20h], rax
0x18000d158  mov     [rsp+118h+arg_0], rcx
0x18000d160  lea     edi, [rbx+3]
0x18000d163  mov     eax, edi
0x18000d165  mul     rcx
0x18000d168  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d16f  cmovb   rax, rbx
0x18000d173  xor     edx, edx; dwFlags
0x18000d175  mov     r8, rax; dwBytes
0x18000d178  call    cs:__imp_HeapAlloc
0x18000d17e  mov     [r14+28h], rax
0x18000d182  lea     ecx, [rsi+1]
0x18000d185  mov     [rsp+118h+var_B8], rcx
0x18000d18a  mov     eax, edi
0x18000d18c  mul     rcx
0x18000d18f  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d196  cmovb   rax, rbx
0x18000d19a  xor     edx, edx; dwFlags
0x18000d19c  mov     r8, rax; dwBytes
0x18000d19f  call    cs:__imp_HeapAlloc
0x18000d1a5  mov     [r14+30h], rax
0x18000d1a9  lea     ecx, [rbp+1]
0x18000d1ac  mov     [rsp+118h+arg_10], rcx
0x18000d1b4  mov     eax, edi
0x18000d1b6  mul     rcx
0x18000d1b9  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d1c0  cmovb   rax, rbx
0x18000d1c4  xor     edx, edx; dwFlags
0x18000d1c6  mov     r8, rax; dwBytes
0x18000d1c9  call    cs:__imp_HeapAlloc
0x18000d1cf  mov     rdi, rax
0x18000d1d2  call    cs:__imp_GetCurrentProcess
0x18000d1d8  mov     rbx, rax
0x18000d1db  call    cs:__imp_GetCurrentProcess
0x18000d1e1  xor     esi, esi
0x18000d1e3  mov     [rsp+118h+dwOptions], 2; dwOptions
0x18000d1eb  mov     [rsp+118h+bInheritHandle], esi; bInheritHandle
0x18000d1ef  lea     r9, [r14+18h]; lpTargetHandle
0x18000d1f3  mov     rcx, rax; hSourceProcessHandle
0x18000d1f6  mov     [rsp+118h+dwDesiredAccess], esi; dwDesiredAccess
0x18000d1fa  mov     r8, rbx; hTargetProcessHandle
0x18000d1fd  mov     rdx, r13; hSourceHandle
0x18000d200  call    cs:__imp_DuplicateHandle
0x18000d206  test    eax, eax
0x18000d208  jz      loc_18000D324
0x18000d20e  cmp     [r14+20h], rsi
0x18000d212  jz      loc_18000D32D
0x18000d218  cmp     [r14+28h], rsi
0x18000d21c  jz      loc_18000D32D
0x18000d222  cmp     [r14+30h], rsi
0x18000d226  jz      loc_18000D32D
0x18000d22c  test    rdi, rdi
0x18000d22f  jz      loc_18000D32D
0x18000d235  lea     ebx, [rsi+68h]
0x18000d238  xor     edx, edx; Val
0x18000d23a  mov     r8d, ebx; Size
0x18000d23d  lea     rcx, [rsp+118h+StartupInfo]; void *
0x18000d242  call    memset_0
0x18000d247  mov     rbp, [rsp+118h+arg_28]
0x18000d24f  lea     rax, aWinsta0Default; "WinSta0\\Default"
0x18000d256  mov     rsi, [rsp+118h+lpString]
0x18000d25e  lea     r8, String; "rundll32.exe uxtheme.dll,#64 %s?%s?%s"
0x18000d265  mov     rdx, [rsp+118h+arg_10]; unsigned __int64
0x18000d26d  mov     r9, r12
0x18000d270  mov     qword ptr [rsp+118h+bInheritHandle], rbp
0x18000d275  mov     rcx, rdi; unsigned __int16 *
0x18000d278  mov     [rsp+118h+StartupInfo.lpDesktop], rax
0x18000d280  mov     qword ptr [rsp+118h+dwDesiredAccess], rsi
0x18000d285  mov     [rsp+118h+StartupInfo.cb], ebx
0x18000d289  mov     [rsp+118h+StartupInfo.dwFlags], 80h
0x18000d294  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d299  mov     [rsp+118h+lpProcessInformation], r14; lpProcessInformation
0x18000d29e  lea     rax, [rsp+118h+StartupInfo]
0x18000d2a3  mov     [rsp+118h+lpStartupInfo], rax; lpStartupInfo
0x18000d2a8  xor     ebx, ebx
0x18000d2aa  mov     [rsp+118h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x18000d2af  xor     r9d, r9d; lpProcessAttributes
0x18000d2b2  mov     [rsp+118h+lpEnvironment], rbx; lpEnvironment
0x18000d2b7  mov     r8, rdi; lpCommandLine
0x18000d2ba  mov     [rsp+118h+dwOptions], ebx; dwCreationFlags
0x18000d2be  xor     edx, edx; lpApplicationName
0x18000d2c0  mov     [rsp+118h+bInheritHandle], ebx; bInheritHandles
0x18000d2c4  mov     rcx, r13; hToken
0x18000d2c7  mov     qword ptr [rsp+118h+dwDesiredAccess], rbx; lpThreadAttributes
0x18000d2cc  call    cs:__imp_CreateProcessAsUserW
0x18000d2d2  test    eax, eax
0x18000d2d4  jz      short loc_18000D324
0x18000d2d6  mov     rdx, [rsp+118h+arg_38]; unsigned __int64
0x18000d2de  mov     r8, r12; unsigned __int16 *
0x18000d2e1  mov     rcx, [r14+20h]; unsigned __int16 *
0x18000d2e5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d2ea  mov     rdx, [rsp+118h+arg_0]; unsigned __int64
0x18000d2f2  mov     r8, rsi; unsigned __int16 *
0x18000d2f5  mov     rcx, [r14+28h]; unsigned __int16 *
0x18000d2f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d2fe  mov     rdx, [rsp+118h+var_B8]; unsigned __int64
0x18000d303  mov     r8, rbp; unsigned __int16 *
0x18000d306  mov     rcx, [r14+30h]; unsigned __int16 *
0x18000d30a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d30f  mov     dword ptr [r14+50h], 80h
0x18000d317  test    r15, r15
0x18000d31a  jz      short loc_18000D33C
0x18000d31c  mov     rax, [r14]
0x18000d31f  mov     [r15], rax
0x18000d322  jmp     short loc_18000D33C
0x18000d324  call    ?StatusCodeOfLastError@CStatusCode@@SAJXZ; CStatusCode::StatusCodeOfLastError(void)
0x18000d329  mov     ebx, eax
0x18000d32b  jmp     short loc_18000D33C
0x18000d32d  xor     edx, edx; int
0x18000d32f  mov     rcx, r14; this
0x18000d332  call    ?Clear@CLoaderProcess@@QEAAXH@Z; CLoaderProcess::Clear(int)
0x18000d337  mov     ebx, 0C0000017h
0x18000d33c  mov     rcx, cs:?s_hHeapToUse@@3PEAXEA; hHeap
0x18000d343  mov     r8, rdi; lpMem
0x18000d346  xor     edx, edx; dwFlags
0x18000d348  call    cs:__imp_HeapFree
0x18000d34e  mov     eax, ebx
0x18000d350  bts     eax, 1Ch
0x18000d354  mov     [r14+50h], eax
0x18000d358  mov     eax, ebx
0x18000d35a  mov     rbx, [rsp+118h+arg_8]
0x18000d362  add     rsp, 0E0h
0x18000d369  pop     r15
0x18000d36b  pop     r14
0x18000d36d  pop     r13
0x18000d36f  pop     r12
0x18000d371  pop     rdi
0x18000d372  pop     rsi
0x18000d373  pop     rbp
0x18000d374  retn
```
