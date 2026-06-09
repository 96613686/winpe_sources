# PAL_System_ThreadAlloc(uint (*)(void *),void *,ulong *,void * *)

- ea: `0x18001aa68`
- end: `0x18001ac78`
- name: `?PAL_System_ThreadAlloc@@YAJP6AIPEAX@Z0PEAKPEAPEAX@Z`
- size: `528`
- prototype: `__int64 __fastcall(unsigned int (*)(void *), void *, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ac80`

## callees

- `0x1800010b0`
- `0x1800011c8`
- `0x18000b458`
- `0x18001aa68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab02`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001abb8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001abb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001aae0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001aae0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001aba1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001aba1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001abce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001abce`

## string_xrefs

- `0x18001ab24`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001ac09`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x18001ab19`: `PAL_System_ThreadAlloc`
- `0x18001abf0`: `PAL_System_ThreadAlloc`

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
        if ( (unsigned int)dword_18005C008 > 2 )
        {
          v16 = 1295;
          LastError = GetLastError();
          v19 = "PAL_System_ThreadAlloc";
          v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
          v21 = "Failed GetModuleHandleEx.  GetLastError: 0x%x";
          v17 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)byte_1800541A9,
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
    if ( (unsigned int)dword_18005C008 > 2 )
    {
      v17 = 1268;
      v21 = "PAL_System_ThreadAlloc";
      v20 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v19 = "NULL parameter passed";
      v16 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a1,
        (unsigned int)&dword_18005457C,
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
0x18001aa68  mov     [rsp-18h+arg_8], rbx
0x18001aa6d  mov     [rsp-18h+arg_10], rsi
0x18001aa72  mov     qword ptr [rsp-18h+ThreadId], rcx
0x18001aa77  push    rbp
0x18001aa78  push    rdi
0x18001aa79  push    r14
0x18001aa7b  mov     rbp, rsp
0x18001aa7e  sub     rsp, 80h
0x18001aa85  mov     [rbp+ThreadId], 0
0x18001aa8c  mov     rsi, r9
0x18001aa8f  mov     [rbp+phModule], 0
0x18001aa97  mov     rbx, r8
0x18001aa9a  mov     r14, rdx
0x18001aa9d  test    r8, r8
0x18001aaa0  jz      loc_18001ABE5
0x18001aaa6  mov     ecx, 18h
0x18001aaab  call    PAL_System_MemAlloc
0x18001aab0  mov     rdi, rax
0x18001aab3  test    rax, rax
0x18001aab6  jnz     short loc_18001AAC2
0x18001aab8  mov     ebx, 8007000Eh
0x18001aabd  jmp     loc_18001AC5E
0x18001aac2  mov     [rax+8], r14
0x18001aac6  lea     r8, [rbp+phModule]; phModule
0x18001aaca  lea     rax, ?TSStaticThreadEntry@CTSThread@@CAIPEAX@Z; CTSThread::TSStaticThreadEntry(void *)
0x18001aad1  mov     ecx, 4; dwFlags
0x18001aad6  lea     rdx, ?g_TsSystemPalDllModule@@3HA; lpModuleName
0x18001aadd  mov     [rdi], rax
0x18001aae0  call    cs:__imp_GetModuleHandleExW
0x18001aae6  test    eax, eax
0x18001aae8  jnz     loc_18001AB7A
0x18001aaee  mov     eax, cs:dword_18005C008
0x18001aaf4  mov     ebx, 80004005h
0x18001aaf9  cmp     eax, 2
0x18001aafc  jbe     loc_18001ABCB
0x18001ab02  call    cs:__imp_GetLastError
0x18001ab08  lea     rdx, byte_1800541A9
0x18001ab0f  mov     [rbp+var_2C], 50Fh
0x18001ab16  mov     [rbp+var_30], eax
0x18001ab19  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x18001ab20  mov     [rbp+var_18], rax
0x18001ab24  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ab2b  mov     [rbp+var_10], rax
0x18001ab2f  lea     rax, aFailedGetmodul; "Failed GetModuleHandleEx.  GetLastError"...
0x18001ab36  mov     [rbp+var_8], rax
0x18001ab3a  lea     rax, [rbp+var_30]
0x18001ab3e  mov     [rsp+80h+var_38], rax
0x18001ab43  lea     rax, [rbp+var_18]
0x18001ab47  mov     [rsp+80h+var_40], rax
0x18001ab4c  lea     rax, [rbp+var_2C]
0x18001ab50  mov     [rsp+80h+var_48], rax
0x18001ab55  lea     rax, [rbp+var_10]
0x18001ab59  mov     [rsp+80h+var_50], rax
0x18001ab5e  lea     rax, [rbp+var_28]
0x18001ab62  mov     [rsp+80h+lpThreadId], rax
0x18001ab67  lea     rax, [rbp+var_8]
0x18001ab6b  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x18001ab70  mov     [rbp+var_28], ebx
0x18001ab73  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001ab78  jmp     short loc_18001ABCB
0x18001ab7a  mov     rax, [rbp+phModule]
0x18001ab7e  lea     r8, ?PAL_System_Win32_ThreadProcWrapper@@YAKPEAX@Z; lpStartAddress
0x18001ab85  mov     [rdi+10h], rax
0x18001ab89  mov     r9, rdi; lpParameter
0x18001ab8c  lea     rax, [rbp+ThreadId]
0x18001ab90  xor     edx, edx; dwStackSize
0x18001ab92  mov     [rsp+80h+lpThreadId], rax; lpThreadId
0x18001ab97  xor     ecx, ecx; lpThreadAttributes
0x18001ab99  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x18001aba1  call    cs:__imp_CreateThread
0x18001aba7  mov     rcx, rax
0x18001abaa  test    rax, rax
0x18001abad  jnz     short loc_18001ABD9
0x18001abaf  mov     rcx, [rbp+phModule]; hLibModule
0x18001abb3  test    rcx, rcx
0x18001abb6  jz      short loc_18001ABC6
0x18001abb8  call    cs:__imp_FreeLibrary
0x18001abbe  mov     [rbp+phModule], 0
0x18001abc6  mov     ebx, 80004005h
0x18001abcb  mov     rcx, rdi; hMem
0x18001abce  call    cs:__imp_LocalFree
0x18001abd4  jmp     loc_18001AC5E
0x18001abd9  mov     eax, [rbp+ThreadId]
0x18001abdc  mov     [rbx], eax
0x18001abde  xor     ebx, ebx
0x18001abe0  mov     [rsi], rcx
0x18001abe3  jmp     short loc_18001AC5E
0x18001abe5  mov     eax, cs:dword_18005C008
0x18001abeb  cmp     eax, 2
0x18001abee  jbe     short loc_18001AC59
0x18001abf0  lea     rax, aPalSystemThrea_4; "PAL_System_ThreadAlloc"
0x18001abf7  mov     [rbp+var_28], 4F4h
0x18001abfe  mov     [rbp+var_8], rax
0x18001ac02  lea     rdx, dword_18005457C
0x18001ac09  lea     rax, aOnecoreTermsrv_1; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18001ac10  mov     ebx, 80004005h
0x18001ac15  mov     [rbp+var_10], rax
0x18001ac19  lea     rax, aNullParameterP; "NULL parameter passed"
0x18001ac20  mov     [rbp+var_18], rax
0x18001ac24  lea     rax, [rbp+var_8]
0x18001ac28  mov     [rsp+80h+var_40], rax
0x18001ac2d  lea     rax, [rbp+var_28]
0x18001ac31  mov     [rsp+80h+var_48], rax
0x18001ac36  lea     rax, [rbp+var_10]
0x18001ac3a  mov     [rsp+80h+var_50], rax
0x18001ac3f  lea     rax, [rbp+var_2C]
0x18001ac43  mov     [rsp+80h+lpThreadId], rax
0x18001ac48  lea     rax, [rbp+var_18]
0x18001ac4c  mov     qword ptr [rsp+80h+dwCreationFlags], rax
0x18001ac51  mov     [rbp+var_2C], ebx
0x18001ac54  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ac59  mov     ebx, 80070057h
0x18001ac5e  lea     r11, [rsp+80h+var_s0]
0x18001ac66  mov     eax, ebx
0x18001ac68  mov     rbx, [r11+28h]
0x18001ac6c  mov     rsi, [r11+30h]
0x18001ac70  mov     rsp, r11
0x18001ac73  pop     r14
0x18001ac75  pop     rdi
0x18001ac76  pop     rbp
0x18001ac77  retn
```
