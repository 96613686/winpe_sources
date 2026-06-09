# TSInitRedirectedLogon(void *,_UNICODE_STRING const *,ulong,_LUID const *)

- ea: `0x18001b000`
- end: `0x18001b1e8`
- name: `?TSInitRedirectedLogon@@YAJPEAXPEBU_UNICODE_STRING@@KPEBU_LUID@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(char *, const struct _UNICODE_STRING *, unsigned int, const struct _LUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003e00`
- `0x180007df0`
- `0x1800090d0`
- `0x18000a5d4`
- `0x18000c610`
- `0x18001b000`
- `0x18001b77c`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b0ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b0ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b0f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b112`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b12d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b0f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b112`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b12d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b148`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1b4`
- `ntdll!RtlEnterCriticalSection` at `0x18001b08b`
- `ntdll!RtlEnterCriticalSection` at `0x18001b08b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b0d8`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b18b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b0d8`
- `ntdll!RtlLeaveCriticalSection` at `0x18001b18b`

## string_xrefs

- `0x18001b0a1`: `wtsapi32.dll`
- `0x18001b0e3`: `WTSVirtualChannelOpenEx`
- `0x18001b11f`: `WTSVirtualChannelRead`
- `0x18001b13a`: `WTSVirtualChannelWrite`

## pseudocode

```c
__int64 __fastcall TSInitRedirectedLogon(
        char *a1,
        const struct _UNICODE_STRING *a2,
        unsigned int a3,
        const struct _LUID *a4)
{
  signed int v9; // ebx
  unsigned __int8 v10; // r8
  HMODULE Library; // rax
  signed int LastError; // eax
  int (*ProcAddress)(void *, char *, unsigned int, unsigned int *); // rax
  __int64 v14; // rcx
  signed int v15; // eax

  if ( !TSContextIsValid(*(struct _TS_CONTEXT **)a1) )
    return 3221225485LL;
  TSReferenceCredential(*(struct _TS_CREDENTIAL **)a1);
  if ( a1[24] )
  {
    v9 = TSContextSetLogonId(*(struct _TS_CONTEXT **)a1, a4);
    if ( v9 < 0 )
      goto LABEL_24;
    v9 = TSDuplicateStringEx((struct _UNICODE_STRING *)(a1 + 8), a2, v10);
    if ( v9 < 0 )
      goto LABEL_24;
    if ( !(unsigned __int8)IsWTSVirtualChannelOpenExPresent() )
    {
      v9 = -1073740670;
      goto LABEL_24;
    }
    RtlEnterCriticalSection(&WTSVirtualChannelLoaderLock);
    if ( WTSVirtualChannelModule )
    {
      ++WTSVirtualChannelRefCount;
    }
    else
    {
      Library = LoadLibraryExW(L"wtsapi32.dll", 0, 0x800u);
      WTSVirtualChannelModule = Library;
      if ( !Library )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0xC0070000;
        goto LABEL_13;
      }
      WTSVirtualChannelRefCount = 1;
      WTSVirtualChannelOpenExFunc = (void *(*)(unsigned int, char *, unsigned int))GetProcAddress(
                                                                                     Library,
                                                                                     "WTSVirtualChannelOpenEx");
      WTSVirtualChannelCloseFunc = (int (*)(void *))GetProcAddress(WTSVirtualChannelModule, "WTSVirtualChannelClose");
      WTSVirtualChannelReadFunc = (int (*)(void *, unsigned int, char *, unsigned int, unsigned int *))GetProcAddress(WTSVirtualChannelModule, "WTSVirtualChannelRead");
      ProcAddress = (int (*)(void *, char *, unsigned int, unsigned int *))GetProcAddress(
                                                                             WTSVirtualChannelModule,
                                                                             "WTSVirtualChannelWrite");
      WTSVirtualChannelWriteFunc = ProcAddress;
      if ( !WTSVirtualChannelOpenExFunc || !WTSVirtualChannelCloseFunc || !WTSVirtualChannelReadFunc || !ProcAddress )
      {
        v9 = -1073741595;
LABEL_13:
        RtlLeaveCriticalSection(&WTSVirtualChannelLoaderLock);
        goto LABEL_24;
      }
    }
    RtlLeaveCriticalSection(&WTSVirtualChannelLoaderLock);
    v14 = ((__int64 (__fastcall *)(_QWORD, const char *, __int64))WTSVirtualChannelOpenExFunc)(
            a3,
            "Microsoft::Windows::RDS::AuthRedirection",
            1);
    if ( v14 )
    {
      *(_QWORD *)(*(_QWORD *)a1 + 168LL) = v14;
    }
    else
    {
      v15 = GetLastError();
      v9 = v15;
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0xC0070000;
    }
    goto LABEL_24;
  }
  v9 = -1073741811;
LABEL_24:
  TSDereferenceContext(*(struct _TS_CONTEXT **)a1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001b000  push    rbx
0x18001b002  push    rbp
0x18001b003  push    rsi
0x18001b004  push    rdi
0x18001b005  sub     rsp, 28h
0x18001b009  mov     rdi, rcx
0x18001b00c  mov     rbx, r9
0x18001b00f  mov     rcx, [rcx]; struct _TS_CONTEXT *
0x18001b012  mov     ebp, r8d
0x18001b015  mov     rsi, rdx
0x18001b018  call    ?TSContextIsValid@@YAEPEAU_TS_CONTEXT@@@Z; TSContextIsValid(_TS_CONTEXT *)
0x18001b01d  test    al, al
0x18001b01f  jnz     short loc_18001B02B
0x18001b021  mov     eax, 0C000000Dh
0x18001b026  jmp     loc_18001B1DF
0x18001b02b  mov     rcx, [rdi]; struct _TS_CREDENTIAL *
0x18001b02e  call    ?TSReferenceCredential@@YAXPEAU_TS_CREDENTIAL@@@Z; TSReferenceCredential(_TS_CREDENTIAL *)
0x18001b033  cmp     byte ptr [rdi+18h], 0
0x18001b037  jnz     short loc_18001B043
0x18001b039  mov     ebx, 0C000000Dh
0x18001b03e  jmp     loc_18001B1D5
0x18001b043  mov     rcx, [rdi]; struct _TS_CONTEXT *
0x18001b046  mov     rdx, rbx; struct _LUID *
0x18001b049  call    ?TSContextSetLogonId@@YAJPEAU_TS_CONTEXT@@AEBU_LUID@@@Z; TSContextSetLogonId(_TS_CONTEXT *,_LUID const &)
0x18001b04e  mov     ebx, eax
0x18001b050  test    eax, eax
0x18001b052  js      loc_18001B1D5
0x18001b058  lea     rcx, [rdi+8]; struct _UNICODE_STRING *
0x18001b05c  mov     rdx, rsi; struct _UNICODE_STRING *
0x18001b05f  call    ?TSDuplicateStringEx@@YAJPEAU_UNICODE_STRING@@PEBU1@E@Z; TSDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING const *,uchar)
0x18001b064  mov     ebx, eax
0x18001b066  test    eax, eax
0x18001b068  js      loc_18001B1D5
0x18001b06e  call    IsWTSVirtualChannelOpenExPresent
0x18001b073  test    al, al
0x18001b075  jnz     short loc_18001B081
0x18001b077  mov     ebx, 0C0000482h
0x18001b07c  jmp     loc_18001B1D5
0x18001b081  lea     rsi, ?WTSVirtualChannelLoaderLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION WTSVirtualChannelLoaderLock
0x18001b088  mov     rcx, rsi; CriticalSection
0x18001b08b  call    cs:__imp_RtlEnterCriticalSection
0x18001b091  cmp     cs:?WTSVirtualChannelModule@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * WTSVirtualChannelModule
0x18001b099  jnz     loc_18001B182
0x18001b09f  xor     edx, edx; hFile
0x18001b0a1  lea     rcx, LibFileName; "wtsapi32.dll"
0x18001b0a8  mov     r8d, 800h; dwFlags
0x18001b0ae  call    cs:__imp_LoadLibraryExW
0x18001b0b4  mov     cs:?WTSVirtualChannelModule@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * WTSVirtualChannelModule
0x18001b0bb  test    rax, rax
0x18001b0be  jnz     short loc_18001B0E3
0x18001b0c0  call    cs:__imp_GetLastError
0x18001b0c6  mov     ebx, eax
0x18001b0c8  test    eax, eax
0x18001b0ca  jle     short loc_18001B0D5
0x18001b0cc  movzx   ebx, ax
0x18001b0cf  or      ebx, 0C0070000h
0x18001b0d5  mov     rcx, rsi; CriticalSection
0x18001b0d8  call    cs:__imp_RtlLeaveCriticalSection
0x18001b0de  jmp     loc_18001B1D5
0x18001b0e3  lea     rdx, ProcName; "WTSVirtualChannelOpenEx"
0x18001b0ea  mov     cs:?WTSVirtualChannelRefCount@@3KA, 1; ulong WTSVirtualChannelRefCount
0x18001b0f4  mov     rcx, rax; hModule
0x18001b0f7  call    cs:__imp_GetProcAddress
0x18001b0fd  mov     rcx, cs:?WTSVirtualChannelModule@@3PEAUHINSTANCE__@@EA; hModule
0x18001b104  lea     rdx, aWtsvirtualchan_2; "WTSVirtualChannelClose"
0x18001b10b  mov     cs:?WTSVirtualChannelOpenExFunc@@3P6APEAXKPEADK@ZEA, rax; void * (*WTSVirtualChannelOpenExFunc)(ulong,char *,ulong)
0x18001b112  call    cs:__imp_GetProcAddress
0x18001b118  mov     rcx, cs:?WTSVirtualChannelModule@@3PEAUHINSTANCE__@@EA; hModule
0x18001b11f  lea     rdx, aWtsvirtualchan_0; "WTSVirtualChannelRead"
0x18001b126  mov     cs:?WTSVirtualChannelCloseFunc@@3P6AHPEAX@ZEA, rax; int (*WTSVirtualChannelCloseFunc)(void *)
0x18001b12d  call    cs:__imp_GetProcAddress
0x18001b133  mov     rcx, cs:?WTSVirtualChannelModule@@3PEAUHINSTANCE__@@EA; hModule
0x18001b13a  lea     rdx, aWtsvirtualchan; "WTSVirtualChannelWrite"
0x18001b141  mov     cs:?WTSVirtualChannelReadFunc@@3P6AHPEAXKPEADKPEAK@ZEA, rax; int (*WTSVirtualChannelReadFunc)(void *,ulong,char *,ulong,ulong *)
0x18001b148  call    cs:__imp_GetProcAddress
0x18001b14e  cmp     cs:?WTSVirtualChannelOpenExFunc@@3P6APEAXKPEADK@ZEA, 0; void * (*WTSVirtualChannelOpenExFunc)(ulong,char *,ulong)
0x18001b156  mov     cs:?WTSVirtualChannelWriteFunc@@3P6AHPEAXPEADKPEAK@ZEA, rax; int (*WTSVirtualChannelWriteFunc)(void *,char *,ulong,ulong *)
0x18001b15d  jz      short loc_18001B178
0x18001b15f  cmp     cs:?WTSVirtualChannelCloseFunc@@3P6AHPEAX@ZEA, 0; int (*WTSVirtualChannelCloseFunc)(void *)
0x18001b167  jz      short loc_18001B178
0x18001b169  cmp     cs:?WTSVirtualChannelReadFunc@@3P6AHPEAXKPEADKPEAK@ZEA, 0; int (*WTSVirtualChannelReadFunc)(void *,ulong,char *,ulong,ulong *)
0x18001b171  jz      short loc_18001B178
0x18001b173  test    rax, rax
0x18001b176  jnz     short loc_18001B188
0x18001b178  mov     ebx, 0C00000E5h
0x18001b17d  jmp     loc_18001B0D5
0x18001b182  inc     cs:?WTSVirtualChannelRefCount@@3KA; ulong WTSVirtualChannelRefCount
0x18001b188  mov     rcx, rsi; CriticalSection
0x18001b18b  call    cs:__imp_RtlLeaveCriticalSection
0x18001b191  mov     rax, cs:?WTSVirtualChannelOpenExFunc@@3P6APEAXKPEADK@ZEA; void * (*WTSVirtualChannelOpenExFunc)(ulong,char *,ulong)
0x18001b198  lea     rdx, aMicrosoftWindo; "Microsoft::Windows::RDS::AuthRedirectio"...
0x18001b19f  mov     r8d, 1
0x18001b1a5  mov     ecx, ebp
0x18001b1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1ac  mov     rcx, rax
0x18001b1af  test    rax, rax
0x18001b1b2  jnz     short loc_18001B1CB
0x18001b1b4  call    cs:__imp_GetLastError
0x18001b1ba  mov     ebx, eax
0x18001b1bc  test    eax, eax
0x18001b1be  jle     short loc_18001B1D5
0x18001b1c0  movzx   ebx, ax
0x18001b1c3  or      ebx, 0C0070000h
0x18001b1c9  jmp     short loc_18001B1D5
0x18001b1cb  mov     rax, [rdi]
0x18001b1ce  mov     [rax+0A8h], rcx
0x18001b1d5  mov     rcx, [rdi]; struct _TS_CONTEXT *
0x18001b1d8  call    ?TSDereferenceContext@@YAXPEAU_TS_CONTEXT@@@Z; TSDereferenceContext(_TS_CONTEXT *)
0x18001b1dd  mov     eax, ebx
0x18001b1df  add     rsp, 28h
0x18001b1e3  pop     rdi
0x18001b1e4  pop     rsi
0x18001b1e5  pop     rbp
0x18001b1e6  pop     rbx
0x18001b1e7  retn
```
