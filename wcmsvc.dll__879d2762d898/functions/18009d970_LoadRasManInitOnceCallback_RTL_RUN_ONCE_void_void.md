# LoadRasManInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18009d970`
- end: `0x18009da51`
- name: `?LoadRasManInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `225`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180036f60`
- `0x18009d970`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009d985`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009d985`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009d9ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009d9ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d9eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009d9eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d9dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009d9dc`

## string_xrefs

- `0x18009d9b7`: `LoadLibraryExW for rasapi32.dll failed`
- `0x18009d978`: `rasapi32.dll`

## pseudocode

```c
__int64 __fastcall LoadRasManInitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  HMODULE Library; // rax
  DWORD LastError; // eax
  int v5; // r8d
  int v6; // r9d
  int v7; // ecx
  __int16 *v8; // rdx
  const char *v9; // rax
  DWORD v10; // ebx
  const char *v12; // [rsp+30h] [rbp-18h] BYREF
  DWORD v13; // [rsp+68h] [rbp+20h] BYREF

  Library = LoadLibraryExW(L"rasapi32.dll", 0, 0x800u);
  hLibModule = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v7 = dword_18013A120;
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v13 = LastError;
      v8 = (__int16 *)byte_1801179F3;
      v9 = "LoadLibraryExW for rasapi32.dll failed";
LABEL_7:
      v12 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v7,
        (_DWORD)v8,
        v5,
        v6,
        (__int64)&v12,
        (__int64)&v13);
      return 0;
    }
    return 0;
  }
  qword_18013F8D8 = (__int64)GetProcAddress(Library, "RasNQMStateEnteredNotification");
  if ( !qword_18013F8D8 )
  {
    v10 = GetLastError();
    FreeLibrary(hLibModule);
    v7 = dword_18013A120;
    hLibModule = 0;
    qword_18013F8D8 = 0;
    if ( (unsigned int)dword_18013A120 > 5 )
    {
      v13 = v10;
      v9 = "GetProcAddress for RasNQMStateEnteredNotification failed";
      v8 = &word_180117946;
      goto LABEL_7;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18009d970  push    rbx
0x18009d972  sub     rsp, 40h
0x18009d976  xor     edx, edx; hFile
0x18009d978  lea     rcx, aRasapi32Dll; "rasapi32.dll"
0x18009d97f  mov     r8d, 800h; dwFlags
0x18009d985  call    cs:__imp_LoadLibraryExW
0x18009d98b  mov     cs:hLibModule, rax
0x18009d992  test    rax, rax
0x18009d995  jnz     short loc_18009D9C0
0x18009d997  call    cs:__imp_GetLastError
0x18009d99d  mov     ecx, cs:dword_18013A120
0x18009d9a3  cmp     ecx, 5
0x18009d9a6  jbe     loc_18009DA42
0x18009d9ac  mov     [rsp+48h+arg_18], eax
0x18009d9b0  lea     rdx, byte_1801179F3
0x18009d9b7  lea     rax, aLoadlibraryexw; "LoadLibraryExW for rasapi32.dll failed"
0x18009d9be  jmp     short loc_18009DA24
0x18009d9c0  lea     rdx, aRasnqmstateent; "RasNQMStateEnteredNotification"
0x18009d9c7  mov     rcx, rax; hModule
0x18009d9ca  call    cs:__imp_GetProcAddress
0x18009d9d0  mov     cs:qword_18013F8D8, rax
0x18009d9d7  test    rax, rax
0x18009d9da  jnz     short loc_18009DA46
0x18009d9dc  call    cs:__imp_GetLastError
0x18009d9e2  mov     rcx, cs:hLibModule; hLibModule
0x18009d9e9  mov     ebx, eax
0x18009d9eb  call    cs:__imp_FreeLibrary
0x18009d9f1  mov     ecx, cs:dword_18013A120
0x18009d9f7  mov     cs:hLibModule, 0
0x18009da02  mov     cs:qword_18013F8D8, 0
0x18009da0d  cmp     ecx, 5
0x18009da10  jbe     short loc_18009DA42
0x18009da12  mov     [rsp+48h+arg_18], ebx
0x18009da16  lea     rax, aGetprocaddress; "GetProcAddress for RasNQMStateEnteredNo"...
0x18009da1d  lea     rdx, word_180117946
0x18009da24  mov     [rsp+48h+var_18], rax
0x18009da29  lea     rax, [rsp+48h+arg_18]
0x18009da2e  mov     [rsp+48h+var_20], rax
0x18009da33  lea     rax, [rsp+48h+var_18]
0x18009da38  mov     [rsp+48h+var_28], rax
0x18009da3d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009da42  xor     eax, eax
0x18009da44  jmp     short loc_18009DA4B
0x18009da46  mov     eax, 1
0x18009da4b  add     rsp, 40h
0x18009da4f  pop     rbx
0x18009da50  retn
```
