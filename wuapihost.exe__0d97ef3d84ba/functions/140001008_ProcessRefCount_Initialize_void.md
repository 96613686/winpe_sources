# ProcessRefCount::Initialize(void)

- ea: `0x140001008`
- end: `0x140001137`
- name: `?Initialize@ProcessRefCount@@QEAAJXZ`
- size: `303`
- prototype: `__int64 __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001340`

## callees

- `0x140001008`
- `0x140001500`
- `0x1400059e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400010c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400010c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000109c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000109c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400010cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400010fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400010cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400010fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140001035`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140001035`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400010f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400010f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000107b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000107b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001057`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140001057`

## string_xrefs

- `0x140001050`: `api-ms-win-shcore-thread-l1-1-0.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProcessRefCount::Initialize(ProcessRefCount *this)
{
  HANDLE EventW; // rax
  HMODULE Library; // rax
  HMODULE v4; // rbx
  bool v5; // si
  FARPROC ProcAddress; // rax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int v8; // edi
  signed int LastError; // eax
  signed int v10; // eax
  _FILETIME pftDueTime; // [rsp+20h] [rbp-18h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 2) = EventW;
  if ( EventW )
  {
    Library = LoadLibraryExW(L"api-ms-win-shcore-thread-l1-1-0.dll", 0, 0x800u);
    v4 = Library;
    pftDueTime = (_FILETIME)Library;
    v5 = Library == 0;
    if ( Library
      && (ProcAddress = GetProcAddress(Library, "SetProcessReference")) != 0
      && (((void (__fastcall *)(ProcessRefCount *))ProcAddress)(this),
          ThreadpoolTimer = CreateThreadpoolTimer(ProcessRefCount::s_TimerCallback, *((PVOID *)this + 2), 0),
          (*((_QWORD *)this + 3) = ThreadpoolTimer) != 0) )
    {
      pftDueTime = (_FILETIME)-600000000LL;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v8 = LastError;
      if ( v8 >= 0 )
        v8 = -2147418113;
    }
    if ( !v5 )
      FreeLibrary(v4);
  }
  else
  {
    v10 = GetLastError();
    v8 = (unsigned __int16)v10 | 0x80070000;
    if ( v10 <= 0 )
      v8 = v10;
    if ( v8 >= 0 )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140001008  mov     [rsp+arg_8], rbx
0x14000100d  mov     [rsp+arg_10], rsi
0x140001012  push    rdi
0x140001013  sub     rsp, 30h
0x140001017  mov     rax, cs:__security_cookie
0x14000101e  xor     rax, rsp
0x140001021  mov     [rsp+38h+var_10], rax
0x140001026  mov     rdi, rcx
0x140001029  xor     r9d, r9d; lpName
0x14000102c  xor     r8d, r8d; bInitialState
0x14000102f  lea     edx, [r9+1]; bManualReset
0x140001033  xor     ecx, ecx; lpEventAttributes
0x140001035  call    cs:__imp_CreateEventW
0x14000103b  mov     [rdi+10h], rax
0x14000103f  test    rax, rax
0x140001042  jz      loc_1400010FA
0x140001048  xor     edx, edx; hFile
0x14000104a  mov     r8d, 800h; dwFlags
0x140001050  lea     rcx, LibFileName; "api-ms-win-shcore-thread-l1-1-0.dll"
0x140001057  call    cs:__imp_LoadLibraryExW
0x14000105d  mov     rbx, rax
0x140001060  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140001065  test    rax, rax
0x140001068  setz    sil
0x14000106c  test    rax, rax
0x14000106f  jz      short loc_1400010CC
0x140001071  lea     rdx, ProcName; "SetProcessReference"
0x140001078  mov     rcx, rax; hModule
0x14000107b  call    cs:__imp_GetProcAddress
0x140001081  test    rax, rax
0x140001084  jz      short loc_1400010CC
0x140001086  mov     rcx, rdi
0x140001089  call    _guard_dispatch_icall
0x14000108e  xor     r8d, r8d; pcbe
0x140001091  mov     rdx, [rdi+10h]; pv
0x140001095  lea     rcx, ?s_TimerCallback@ProcessRefCount@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000109c  call    cs:__imp_CreateThreadpoolTimer
0x1400010a2  mov     [rdi+18h], rax
0x1400010a6  test    rax, rax
0x1400010a9  jz      short loc_1400010CC
0x1400010ab  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0FFFFFFFFDC3CBA00h
0x1400010b4  xor     r9d, r9d; msWindowLength
0x1400010b7  xor     r8d, r8d; msPeriod
0x1400010ba  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1400010bf  mov     rcx, rax; pti
0x1400010c2  call    cs:__imp_SetThreadpoolTimer
0x1400010c8  xor     edi, edi
0x1400010ca  jmp     short loc_1400010EA
0x1400010cc  call    cs:__imp_GetLastError
0x1400010d2  movzx   edi, ax
0x1400010d5  or      edi, 80070000h
0x1400010db  test    eax, eax
0x1400010dd  cmovle  edi, eax
0x1400010e0  test    edi, edi
0x1400010e2  mov     eax, 8000FFFFh
0x1400010e7  cmovns  edi, eax
0x1400010ea  test    sil, sil
0x1400010ed  jnz     short loc_140001118
0x1400010ef  mov     rcx, rbx; hLibModule
0x1400010f2  call    cs:__imp_FreeLibrary
0x1400010f8  jmp     short loc_140001118
0x1400010fa  call    cs:__imp_GetLastError
0x140001100  movzx   edi, ax
0x140001103  or      edi, 80070000h
0x140001109  test    eax, eax
0x14000110b  cmovle  edi, eax
0x14000110e  mov     eax, 8000FFFFh
0x140001113  test    edi, edi
0x140001115  cmovns  edi, eax
0x140001118  mov     eax, edi
0x14000111a  mov     rcx, [rsp+38h+var_10]
0x14000111f  xor     rcx, rsp; StackCookie
0x140001122  call    __security_check_cookie
0x140001127  mov     rbx, [rsp+38h+arg_8]
0x14000112c  mov     rsi, [rsp+38h+arg_10]
0x140001131  add     rsp, 30h
0x140001135  pop     rdi
0x140001136  retn
```
