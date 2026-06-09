# WABOpenEx

- ea: `0x180075a40`
- end: `0x180075b5c`
- name: `WABOpenEx`
- size: `284`
- prototype: `HRESULT __stdcall(LPADRBOOK *lppAdrBook, LPWABOBJECT *lppWABObject, LPWAB_PARAM lpWP, DWORD Reserved, ALLOCATEBUFFER *fnAllocateBuffer, ALLOCATEMORE *fnAllocateMore, FREEBUFFER *fnFreeBuffer)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180001010`
- `0x1800010a0`
- `0x180001150`
- `0x1800011fc`
- `0x180075960`
- `0x180075a40`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180075aa3`
- `SHLWAPI!PathFindFileNameW` at `0x180075aa3`
- `SHLWAPI!StrCmpNIW` at `0x180075ab9`
- `SHLWAPI!StrCmpNIW` at `0x180075ab9`
- `KERNEL32!GetModuleFileNameW` at `0x180075a98`
- `KERNEL32!GetModuleFileNameW` at `0x180075a98`
- `ntdll!WinSqmIncrementDWORD` at `0x180075a73`
- `ntdll!WinSqmIncrementDWORD` at `0x180075a73`

## string_xrefs

- `0x180075b09`: `WABOpenEx API called`

## pseudocode

```c
HRESULT __stdcall WABOpenEx(
        LPADRBOOK *lppAdrBook,
        LPWABOBJECT *lppWABObject,
        LPWAB_PARAM lpWP,
        DWORD Reserved,
        ALLOCATEBUFFER *fnAllocateBuffer,
        ALLOCATEMORE *fnAllocateMore,
        FREEBUFFER *fnFreeBuffer)
{
  const WCHAR *FileNameW; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  const char *v15; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-238h] BYREF

  WinSqmIncrementDWORD(0, 7228, 1);
  memset_0(Filename, 0, 0x208u);
  GetModuleFileNameW(0, Filename, 0x104u);
  FileNameW = PathFindFileNameW(Filename);
  if ( !StrCmpNIW(FileNameW, L"OUTLOOK", 7) )
  {
    lpfnAllocateBufferExternal = fnAllocateBuffer;
    lpfnAllocateMoreExternal = fnAllocateMore;
    lpfnFreeBufferExternal = fnFreeBuffer;
  }
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  if ( (unsigned int)dword_1800A9A40 > 5 && (unsigned __int8)tlgKeywordOn() )
  {
    v15 = "WABOpenEx API called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v11,
      (unsigned int)word_1800A001A,
      v12,
      v13,
      (__int64)&v15);
  }
  TraceLoggingUnregister_EventUnregister();
  return WABOpen(lppAdrBook, lppWABObject, lpWP, 0);
}

```

## disassembly

```asm
0x180075a40  push    rbx
0x180075a42  push    rsi
0x180075a43  push    rdi
0x180075a44  sub     rsp, 260h
0x180075a4b  mov     rax, cs:__security_cookie
0x180075a52  xor     rax, rsp
0x180075a55  mov     [rsp+278h+var_28], rax
0x180075a5d  mov     rsi, r8
0x180075a60  mov     rdi, rdx
0x180075a63  mov     rbx, rcx
0x180075a66  mov     edx, 1C3Ch
0x180075a6b  mov     r8d, 1
0x180075a71  xor     ecx, ecx
0x180075a73  call    cs:__imp_WinSqmIncrementDWORD
0x180075a79  xor     edx, edx; Val
0x180075a7b  lea     rcx, [rsp+278h+Filename]; void *
0x180075a80  mov     r8d, 208h; Size
0x180075a86  call    memset_0
0x180075a8b  mov     r8d, 104h; nSize
0x180075a91  lea     rdx, [rsp+278h+Filename]; lpFilename
0x180075a96  xor     ecx, ecx; hModule
0x180075a98  call    cs:__imp_GetModuleFileNameW
0x180075a9e  lea     rcx, [rsp+278h+Filename]; pszPath
0x180075aa3  call    cs:__imp_PathFindFileNameW
0x180075aa9  mov     r8d, 7; nChar
0x180075aaf  lea     rdx, aOutlook; "OUTLOOK"
0x180075ab6  mov     rcx, rax; psz1
0x180075ab9  call    cs:__imp_StrCmpNIW
0x180075abf  test    eax, eax
0x180075ac1  jnz     short loc_180075AF0
0x180075ac3  mov     rax, [rsp+278h+fnAllocateBuffer]
0x180075acb  mov     cs:?lpfnAllocateBufferExternal@@3P6AJKPEAPEAX@ZEA, rax; long (*lpfnAllocateBufferExternal)(ulong,void * *)
0x180075ad2  mov     rax, [rsp+278h+fnAllocateMore]
0x180075ada  mov     cs:?lpfnAllocateMoreExternal@@3P6AJKPEAXPEAPEAX@ZEA, rax; long (*lpfnAllocateMoreExternal)(ulong,void *,void * *)
0x180075ae1  mov     rax, [rsp+278h+fnFreeBuffer]
0x180075ae9  mov     cs:?lpfnFreeBufferExternal@@3P6AKPEAX@ZEA, rax; ulong (*lpfnFreeBufferExternal)(void *)
0x180075af0  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180075af5  mov     eax, cs:dword_1800A9A40
0x180075afb  cmp     eax, 5
0x180075afe  jbe     short loc_180075B2B
0x180075b00  call    _tlgKeywordOn
0x180075b05  test    al, al
0x180075b07  jz      short loc_180075B2B
0x180075b09  lea     rax, aWabopenexApiCa; "WABOpenEx API called"
0x180075b10  mov     [rsp+278h+var_248], rax
0x180075b15  lea     rdx, word_1800A001A
0x180075b1c  lea     rax, [rsp+278h+var_248]
0x180075b21  mov     [rsp+278h+var_258], rax
0x180075b26  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180075b2b  call    TraceLoggingUnregister_EventUnregister
0x180075b30  xor     r9d, r9d; Reserved2
0x180075b33  mov     r8, rsi; lpWP
0x180075b36  mov     rdx, rdi; lppWABObject
0x180075b39  mov     rcx, rbx; lppAdrBook
0x180075b3c  call    WABOpen
0x180075b41  mov     rcx, [rsp+278h+var_28]
0x180075b49  xor     rcx, rsp; StackCookie
0x180075b4c  call    __security_check_cookie
0x180075b51  add     rsp, 260h
0x180075b58  pop     rdi
0x180075b59  pop     rsi
0x180075b5a  pop     rbx
0x180075b5b  retn
```
