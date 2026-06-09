# PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)

- ea: `0x18001bb84`
- end: `0x18001bd94`
- name: `?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z`
- size: `528`
- prototype: `__int64 __fastcall(unsigned int (*)(void *), void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bd9c`

## callees

- `0x180001180`
- `0x1800013f4`
- `0x18001bb84`
- `0x18001c6e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001bbfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001bbfc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001bcd4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001bcd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc1e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bcea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bcea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001bcbd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001bcbd`

## string_xrefs

- `0x18001bc40`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001bd25`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001bc35`: `PAL_System_ThreadAlloc`
- `0x18001bd0c`: `PAL_System_ThreadAlloc`

## pseudocode

```c
__int64 __fastcall PAL_System_ThreadAlloc(unsigned int (*a1)(void *), void *a2, unsigned int *a3, void **a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  HANDLE v13; // rcx
  DWORD LastError; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+54h] [rbp-2Ch] BYREF
  int v17; // [rsp+58h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-20h] BYREF
  const char *v19; // [rsp+68h] [rbp-18h] BYREF
  const char *v20; // [rsp+70h] [rbp-10h] BYREF
  const char *v21; // [rsp+78h] [rbp-8h] BYREF
  DWORD ThreadId; // [rsp+A0h] [rbp+20h] BYREF
  int v23; // [rsp+A4h] [rbp+24h]

  v23 = HIDWORD(a1);
  ThreadId = 0;
  phModule = 0;
  if ( a3 )
  {
    v7 = (_QWORD *)PAL_System_MemAlloc(24);
    v8 = v7;
    if ( v7 )
    {
      v7[1] = a2;
      *v7 = CTSThread::TSStaticThreadEntry;
      if ( GetModuleHandleExW(4u, &g_TsSystemPalDllModule, &phModule) )
      {
        v8[2] = phModule;
        v13 = CreateThread(0, 0, PAL_System_Win32_ThreadProcWrapper, v8, 0, &ThreadId);
        if ( v13 )
        {
          *a3 = ThreadId;
          v9 = 0;
          *a4 = v13;
          return v9;
        }
        if ( phModule )
        {
          FreeLibrary(phModule);
          phModule = 0;
        }
        v9 = -2147467259;
      }
      else
      {
        v9 = -2147467259;
        if ( (unsigned int)dword_1800EB958 > 2 )
        {
          v16 = 1295;
          LastError = GetLastError();
          v19 = "PAL_System_ThreadAlloc";
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v21 = "Failed GetModuleHandleEx.  GetLastError: 0x%x";
          v17 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)byte_1800CD4A5,
            v11,
            v12,
            (__int64)&v21,
            (__int64)&v17,
            (__int64)&v20,
            (__int64)&v16,
            (__int64)&v19,
            (__int64)&LastError);
        }
      }
      LocalFree(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      v17 = 1268;
      v21 = "PAL_System_ThreadAlloc";
      v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v19 = "NULL parameter passed";
      v16 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)qword_1800CD878,
        0,
        (_DWORD)a4,
        (__int64)&v19,
        (__int64)&v16,
        (__int64)&v20,
        (__int64)&v17,
        (__int64)&v21);
    }
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x18001bb84  mov     [rsp-18h+arg_8], rbx
0x18001bb89  mov     [rsp-18h+arg_10], rsi
0x18001bb8e  mov     qword ptr [rsp-18h+ThreadId], rcx
0x18001bb93  push    rbp
0x18001bb94  push    rdi
0x18001bb95  push    r14
0x18001bb97  mov     rbp, rsp
0x18001bb9a  sub     rsp, 80h
0x18001bba1  mov     [rbp+ThreadId], 0
0x18001bba8  mov     rsi, r9
0x18001bbab  mov     [rbp+phModule], 0
0x18001bbb3  mov     rbx, r8
0x18001bbb6  mov     r14, rdx
0x18001bbb9  test    r8, r8
0x18001bbbc  jz      loc_18001BD01
0x18001bbc2  mov     ecx, 18h
0x18001bbc7  call    PAL_System_MemAlloc
0x18001bbcc  mov     rdi, rax
0x18001bbcf  test    rax, rax
0x18001bbd2  jnz     short loc_18001BBDE
0x18001bbd4  mov     ebx, 8007000Eh
0x18001bbd9  jmp     loc_18001BD7A
0x18001bbde  mov     [rax+8], r14
0x18001bbe2  lea     r8, [rbp+phModule]; phModule
0x18001bbe6  lea     rax, ?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z; CTSThread::TSStaticThreadEntry(void *)
0x18001bbed  mov     ecx, 4; dwFlags
0x18001bbf2  lea     rdx, ?g_TsSystemPalDllModule@@3HA; lpModuleName
0x18001bbf9  mov     [rdi], rax
0x18001bbfc  call    cs:__imp_GetModuleHandleExW
0x18001bc02  test    eax, eax
0x18001bc04  jnz     loc_18001BC96
0x18001bc0a  mov     eax, cs:dword_1800EB958
0x18001bc10  mov     ebx, 80004005h
0x18001bc15  cmp     eax, 2
0x18001bc18  jbe     loc_18001BCE7
0x18001bc1e  call    cs:__imp_GetLastError
0x18001bc24  lea     rdx, byte_1800CD4A5
0x18001bc2b  mov     [rbp+var_2C], 50Fh
0x18001bc32  mov     [rbp+var_30], eax
0x18001bc35  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x18001bc3c  mov     [rbp+var_18], rax
0x18001bc40  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001bc47  mov     [rbp+var_10], rax
0x18001bc4b  lea     rax, aFailedGetmodul; "Failed GetModuleHandleEx.  GetLastError"...
0x18001bc52  mov     [rbp+var_8], rax
0x18001bc56  lea     rax, [rbp+var_30]
0x18001bc5a  mov     [rsp+80h+var_38], rax
0x18001bc5f  lea     rax, [rbp+var_18]
0x18001bc63  mov     [rsp+80h+var_40], rax
0x18001bc68  lea     rax, [rbp+var_2C]
0x18001bc6c  mov     [rsp+80h+var_48], rax
0x18001bc71  lea     rax, [rbp+var_10]
0x18001bc75  mov     [rsp+80h+var_50], rax
0x18001bc7a  lea     rax, [rbp+var_28]
0x18001bc7e  mov     [rsp+80h+lpThreadId], rax
0x18001bc83  lea     rax, [rbp+var_8]
0x18001bc87  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x18001bc8c  mov     [rbp+var_28], ebx
0x18001bc8f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001bc94  jmp     short loc_18001BCE7
0x18001bc96  mov     rax, [rbp+phModule]
0x18001bc9a  lea     r8, ?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z; lpStartAddress
0x18001bca1  mov     [rdi+10h], rax
0x18001bca5  mov     r9, rdi; lpParameter
0x18001bca8  lea     rax, [rbp+ThreadId]
0x18001bcac  xor     edx, edx; dwStackSize
0x18001bcae  mov     [rsp+80h+lpThreadId], rax; lpThreadId
0x18001bcb3  xor     ecx, ecx; lpThreadAttributes
0x18001bcb5  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x18001bcbd  call    cs:__imp_CreateThread
0x18001bcc3  mov     rcx, rax
0x18001bcc6  test    rax, rax
0x18001bcc9  jnz     short loc_18001BCF5
0x18001bccb  mov     rcx, [rbp+phModule]; hLibModule
0x18001bccf  test    rcx, rcx
0x18001bcd2  jz      short loc_18001BCE2
0x18001bcd4  call    cs:__imp_FreeLibrary
0x18001bcda  mov     [rbp+phModule], 0
0x18001bce2  mov     ebx, 80004005h
0x18001bce7  mov     rcx, rdi; hMem
0x18001bcea  call    cs:__imp_LocalFree
0x18001bcf0  jmp     loc_18001BD7A
0x18001bcf5  mov     eax, [rbp+ThreadId]
0x18001bcf8  mov     [rbx], eax
0x18001bcfa  xor     ebx, ebx
0x18001bcfc  mov     [rsi], rcx
0x18001bcff  jmp     short loc_18001BD7A
0x18001bd01  mov     eax, cs:dword_1800EB958
0x18001bd07  cmp     eax, 2
0x18001bd0a  jbe     short loc_18001BD75
0x18001bd0c  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x18001bd13  mov     [rbp+var_28], 4F4h
0x18001bd1a  mov     [rbp+var_8], rax
0x18001bd1e  lea     rdx, qword_1800CD878
0x18001bd25  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001bd2c  mov     ebx, 80004005h
0x18001bd31  mov     [rbp+var_10], rax
0x18001bd35  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001bd3c  mov     [rbp+var_18], rax
0x18001bd40  lea     rax, [rbp+var_8]
0x18001bd44  mov     [rsp+80h+var_40], rax
0x18001bd49  lea     rax, [rbp+var_28]
0x18001bd4d  mov     [rsp+80h+var_48], rax
0x18001bd52  lea     rax, [rbp+var_10]
0x18001bd56  mov     [rsp+80h+var_50], rax
0x18001bd5b  lea     rax, [rbp+var_2C]
0x18001bd5f  mov     [rsp+80h+lpThreadId], rax
0x18001bd64  lea     rax, [rbp+var_18]
0x18001bd68  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x18001bd6d  mov     [rbp+var_2C], ebx
0x18001bd70  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001bd75  mov     ebx, 80070057h
0x18001bd7a  lea     r11, [rsp+80h+var_s0]
0x18001bd82  mov     eax, ebx
0x18001bd84  mov     rbx, [r11+28h]
0x18001bd88  mov     rsi, [r11+30h]
0x18001bd8c  mov     rsp, r11
0x18001bd8f  pop     r14
0x18001bd91  pop     rdi
0x18001bd92  pop     rbp
0x18001bd93  retn
```
