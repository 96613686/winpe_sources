# try_get_function_slow

- ea: `0x14004f8d0`
- end: `0x14004fa73`
- name: `try_get_function_slow`
- size: `419`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14004f890`
- `0x14004fa7c`
- `0x14004fbf0`
- `0x14004fcd4`
- `0x14004fd7c`

## callees

- `0x14004c840`
- `0x14004f810`
- `0x14004f870`
- `0x14004f8d0`
- `0x140051360`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004fa5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004fa5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004f932`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004f986`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004f932`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14004f986`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004fa53`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004fa53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f944`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x14004f9eb`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x14004fa1b`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x14004f9eb`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x14004fa1b`

## pseudocode

```c
FARPROC __fastcall try_get_function_slow(unsigned int a1, const CHAR *a2, unsigned int *a3, unsigned int *a4)
{
  __int64 v4; // r12
  unsigned int *v6; // rsi
  __int64 v8; // rdi
  HMODULE Library; // rbx
  const WCHAR *v10; // rbp
  FARPROC ProcAddress; // rbx
  __int64 v12; // rax
  DWORD flOldProtect; // [rsp+80h] [rbp+18h] BYREF

  v4 = a1;
  v6 = a3;
  if ( a3 == a4 )
  {
LABEL_12:
    ProcAddress = 0;
    goto LABEL_13;
  }
  while ( 1 )
  {
    v8 = *v6;
    Library = (HMODULE)qword_1400BBA40[v8];
    if ( !Library )
      break;
    if ( Library != (HMODULE)-1LL )
      goto LABEL_20;
LABEL_11:
    if ( ++v6 == a4 )
      goto LABEL_12;
  }
  v10 = off_140095A70[v8];
  Library = LoadLibraryExW(v10, 0, 0x800u);
  if ( !Library
    && (GetLastError() != 87
     || !wcsncmp(v10, L"api-ms-", 7u)
     || !wcsncmp(v10, L"ext-ms-", 7u)
     || (Library = LoadLibraryExW(v10, 0, 0)) == 0) )
  {
    _InterlockedExchange64(&qword_1400BBA40[v8], -1);
    goto LABEL_11;
  }
  if ( _InterlockedExchange64(&qword_1400BBA40[v8], (__int64)Library) )
    FreeLibrary(Library);
LABEL_20:
  ProcAddress = GetProcAddress(Library, a2);
LABEL_13:
  _acrt_lock(14);
  flOldProtect = 0;
  if ( !VirtualProtect(qword_1400C4000, 0x100u, 4u, &flOldProtect) )
    goto LABEL_21;
  v12 = (__int64)ProcAddress;
  if ( !ProcAddress )
    v12 = -1;
  _InterlockedExchange64(&qword_1400C4000[v4], v12);
  if ( !VirtualProtect(qword_1400C4000, 0x100u, 2u, &flOldProtect) )
LABEL_21:
    abort();
  _acrt_unlock(14);
  return ProcAddress;
}

```

## disassembly

```asm
0x14004f8d0  push    rbx
0x14004f8d2  push    rbp
0x14004f8d3  push    rsi
0x14004f8d4  push    rdi
0x14004f8d5  push    r12
0x14004f8d7  push    r13
0x14004f8d9  push    r14
0x14004f8db  push    r15
0x14004f8dd  sub     rsp, 28h
0x14004f8e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004f8e5  mov     r12d, ecx
0x14004f8e8  mov     r14, r9
0x14004f8eb  mov     rsi, r8
0x14004f8ee  mov     r15, rdx
0x14004f8f1  cmp     r8, r9
0x14004f8f4  jz      loc_14004F9B5
0x14004f8fa  lea     r13, __ImageBase
0x14004f901  mov     edi, [rsi]
0x14004f903  mov     rbx, rva qword_1400BBA40[r13+rdi*8]
0x14004f90b  nop
0x14004f90c  test    rbx, rbx
0x14004f90f  jz      short loc_14004F91F
0x14004f911  cmp     rbx, rax
0x14004f914  jnz     loc_14004FA59
0x14004f91a  jmp     loc_14004F9A8
0x14004f91f  mov     rbp, ds:rva off_140095A70[r13+rdi*8]; "api-ms-win-core-datetime-l1-1-1" ...
0x14004f927  xor     edx, edx; hFile
0x14004f929  mov     rcx, rbp; lpLibFileName
0x14004f92c  mov     r8d, 800h; dwFlags
0x14004f932  call    cs:__imp_LoadLibraryExW
0x14004f938  mov     rbx, rax
0x14004f93b  test    rax, rax
0x14004f93e  jnz     loc_14004FA40
0x14004f944  call    cs:__imp_GetLastError
0x14004f94a  cmp     eax, 57h ; 'W'
0x14004f94d  jnz     short loc_14004F998
0x14004f94f  lea     ebx, [rax-50h]
0x14004f952  mov     rcx, rbp; String1
0x14004f955  mov     r8d, ebx; MaxCount
0x14004f958  lea     rdx, aApiMs; "api-ms-"
0x14004f95f  call    wcsncmp
0x14004f964  test    eax, eax
0x14004f966  jz      short loc_14004F998
0x14004f968  mov     r8d, ebx; MaxCount
0x14004f96b  lea     rdx, aExtMs; "ext-ms-"
0x14004f972  mov     rcx, rbp; String1
0x14004f975  call    wcsncmp
0x14004f97a  test    eax, eax
0x14004f97c  jz      short loc_14004F998
0x14004f97e  xor     r8d, r8d; dwFlags
0x14004f981  xor     edx, edx; hFile
0x14004f983  mov     rcx, rbp; lpLibFileName
0x14004f986  call    cs:__imp_LoadLibraryExW
0x14004f98c  mov     rbx, rax
0x14004f98f  test    rax, rax
0x14004f992  jnz     loc_14004FA40
0x14004f998  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004f99c  xchg    rax, rva qword_1400BBA40[r13+rdi*8]
0x14004f9a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004f9a8  add     rsi, 4
0x14004f9ac  cmp     rsi, r14
0x14004f9af  jnz     loc_14004F901
0x14004f9b5  xor     ebx, ebx
0x14004f9b7  mov     edi, 0Eh
0x14004f9bc  mov     ecx, edi
0x14004f9be  call    __acrt_lock
0x14004f9c3  mov     ebp, 100h
0x14004f9c8  mov     [rsp+68h+flOldProtect], 0
0x14004f9d3  lea     rsi, qword_1400C4000
0x14004f9da  mov     edx, ebp; dwSize
0x14004f9dc  mov     rcx, rsi; lpAddress
0x14004f9df  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x14004f9e7  lea     r8d, [rdi-0Ah]; flNewProtect
0x14004f9eb  call    cs:__imp_VirtualProtect
0x14004f9f1  test    eax, eax
0x14004f9f3  jz      short loc_14004FA6D
0x14004f9f5  test    rbx, rbx
0x14004f9f8  mov     rax, rbx
0x14004f9fb  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14004fa02  cmovz   rax, rcx
0x14004fa06  xchg    rax, [rsi+r12*8]
0x14004fa0a  lea     r9, [rsp+68h+flOldProtect]; lpflOldProtect
0x14004fa12  mov     edx, ebp; dwSize
0x14004fa14  lea     r8d, [rdi-0Ch]; flNewProtect
0x14004fa18  mov     rcx, rsi; lpAddress
0x14004fa1b  call    cs:__imp_VirtualProtect
0x14004fa21  test    eax, eax
0x14004fa23  jz      short loc_14004FA6D
0x14004fa25  mov     ecx, edi
0x14004fa27  call    __acrt_unlock
0x14004fa2c  mov     rax, rbx
0x14004fa2f  add     rsp, 28h
0x14004fa33  pop     r15
0x14004fa35  pop     r14
0x14004fa37  pop     r13
0x14004fa39  pop     r12
0x14004fa3b  pop     rdi
0x14004fa3c  pop     rsi
0x14004fa3d  pop     rbp
0x14004fa3e  pop     rbx
0x14004fa3f  retn
0x14004fa40  mov     rax, rbx
0x14004fa43  xchg    rax, rva qword_1400BBA40[r13+rdi*8]
0x14004fa4b  test    rax, rax
0x14004fa4e  jz      short loc_14004FA59
0x14004fa50  mov     rcx, rbx; hLibModule
0x14004fa53  call    cs:__imp_FreeLibrary
0x14004fa59  mov     rdx, r15; lpProcName
0x14004fa5c  mov     rcx, rbx; hModule
0x14004fa5f  call    cs:__imp_GetProcAddress
0x14004fa65  mov     rbx, rax
0x14004fa68  jmp     loc_14004F9B7
0x14004fa6d  call    abort
```
