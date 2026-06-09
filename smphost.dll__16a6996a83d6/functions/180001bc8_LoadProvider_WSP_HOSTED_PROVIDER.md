# LoadProvider(_WSP_HOSTED_PROVIDER *)

- ea: `0x180001bc8`
- end: `0x180001f79`
- name: `?LoadProvider@@YA?AW4_MI_Result@@PEAU_WSP_HOSTED_PROVIDER@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(struct _WSP_HOSTED_PROVIDER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002044`

## callees

- `0x1800010b0`
- `0x180001bc8`
- `0x180002820`
- `0x180002950`
- `0x180003010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001dd5`
- `msvcrt!_wcsicmp` at `0x180001dd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001dbb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001cba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001cba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001bfd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001bfd`

## pseudocode

```c
__int64 __fastcall LoadProvider(struct _WSP_HOSTED_PROVIDER *a1)
{
  HMODULE Library; // rax
  int v3; // edi
  DWORD LastError; // eax
  unsigned int v5; // ebx
  FARPROC ProcAddress; // rax
  FARPROC v7; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  HMODULE v10; // rcx
  FARPROC v11; // r9
  const wchar_t *v12; // r8
  __int64 v13; // rcx
  const wchar_t *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r9
  int v17; // r9d
  __int64 *v18; // rdx
  __int64 v19; // r9
  DWORD v20; // r14d
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rax
  const wchar_t *v24; // rdx
  __int64 v25; // r9
  int v26; // r9d
  unsigned int v28; // [rsp+50h] [rbp-89h] BYREF
  int v29; // [rsp+58h] [rbp-81h] BYREF
  int v30; // [rsp+60h] [rbp-79h] BYREF
  DWORD v31; // [rsp+68h] [rbp-71h] BYREF
  __int64 v32; // [rsp+70h] [rbp-69h] BYREF
  const char *v33; // [rsp+78h] [rbp-61h] BYREF
  char v34[16]; // [rsp+80h] [rbp-59h] BYREF
  const wchar_t *v35; // [rsp+90h] [rbp-49h]
  int v36; // [rsp+98h] [rbp-41h]
  int v37; // [rsp+9Ch] [rbp-3Dh]
  const wchar_t *v38; // [rsp+A0h] [rbp-39h]
  int v39; // [rsp+A8h] [rbp-31h]
  int v40; // [rsp+ACh] [rbp-2Dh]
  int *v41; // [rsp+B0h] [rbp-29h]
  __int64 v42; // [rsp+B8h] [rbp-21h]
  int *v43; // [rsp+C0h] [rbp-19h]
  __int64 v44; // [rsp+C8h] [rbp-11h]
  unsigned int *v45; // [rsp+D0h] [rbp-9h]
  __int64 v46; // [rsp+D8h] [rbp-1h]

  Library = LoadLibraryExW(*(LPCWSTR *)a1, 0, 0x800u);
  *((_QWORD *)a1 + 2) = Library;
  if ( !Library )
  {
    v3 = 1;
LABEL_3:
    LastError = GetLastError();
    v5 = 1;
    goto LABEL_29;
  }
  ProcAddress = GetProcAddress(Library, "SetShutdownCallback");
  if ( !ProcAddress )
  {
    v3 = 2;
    goto LABEL_3;
  }
  ((void (__fastcall *)(void (*)(void)))ProcAddress)(SmpHostShutdownCallback);
  v7 = GetProcAddress(*((HMODULE *)a1 + 2), "SmpUnload");
  if ( !v7 )
  {
    v3 = 3;
    goto LABEL_3;
  }
  v8 = (HMODULE)*((_QWORD *)a1 + 2);
  *((_QWORD *)a1 + 6) = v7;
  v9 = GetProcAddress(v8, "PreShutdown");
  if ( !v9 )
  {
    v3 = 4;
    goto LABEL_3;
  }
  v10 = (HMODULE)*((_QWORD *)a1 + 2);
  *((_QWORD *)a1 + 7) = v9;
  v11 = GetProcAddress(v10, "MI_Main");
  if ( !v11 )
  {
    v3 = 5;
    goto LABEL_3;
  }
  if ( !g_Application.ft )
  {
    if ( a1 != (struct _WSP_HOSTED_PROVIDER *)-24LL )
    {
      *(_OWORD *)((char *)a1 + 24) = 0;
      *((_QWORD *)a1 + 5) = 0;
    }
    v5 = 4;
    goto LABEL_28;
  }
  v5 = ((__int64 (__fastcall *)(MI_Application *, const wchar_t *, _QWORD, FARPROC, _QWORD, char *))g_Application.ft->NewHostedProvider)(
         &g_Application,
         L"root\\Microsoft\\Windows\\Storage\\Providers_v2",
         *((_QWORD *)a1 + 1),
         v11,
         0,
         (char *)a1 + 24);
  if ( v5 )
  {
LABEL_28:
    v3 = 6;
    LastError = GetLastError();
LABEL_29:
    v20 = LastError;
    if ( !_wcsicmp(*((const wchar_t **)a1 + 1), L"MISpace") || v20 != 126 )
    {
      if ( (unsigned int)dword_180006048 > 5
        && (qword_180006058 & 0x400000000000LL) != 0
        && (qword_180006060 & 0x400000000000LL) == qword_180006060 )
      {
        v32 = *((_QWORD *)a1 + 1);
        v33 = "LoadProvider";
        v31 = v20;
        v28 = v5;
        v29 = v3;
        v30 = 346;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          qword_180006060,
          (unsigned int)byte_1800048D9,
          v21,
          v22,
          (__int64)&v33,
          (__int64)&v30,
          (__int64)&v32,
          (__int64)&v29,
          (__int64)&v28,
          (__int64)&v31);
      }
      if ( (Microsoft_Windows_StorageManagement_WSP_HostEnableBits & 1) != 0 )
      {
        v12 = (const wchar_t *)*((_QWORD *)a1 + 1);
        v23 = -1;
        v24 = *(const wchar_t **)a1;
        v13 = 10;
        v28 = v20;
        v29 = v3;
        v30 = v5;
        if ( v12 )
        {
          v25 = -1;
          do
            ++v25;
          while ( v12[v25] );
          v26 = 2 * v25 + 2;
        }
        else
        {
          v12 = L"NULL";
          v26 = 10;
        }
        v35 = v12;
        v36 = v26;
        v37 = 0;
        if ( v24 )
        {
          do
            ++v23;
          while ( v24[v23] );
          v13 = (unsigned int)(2 * v23 + 2);
        }
        else
        {
          v24 = L"NULL";
        }
        v38 = v24;
        v41 = &v30;
        v18 = PROVIDER_LOAD_FAILED;
        v42 = 4;
        v43 = &v29;
        v19 = 6;
        v44 = 4;
        v45 = &v28;
        v46 = 4;
LABEL_46:
        v39 = v13;
        v40 = 0;
        McGenEventWrite_EventWriteTransfer(v13, v18, v12, v19, v34);
        return v5;
      }
    }
    return v5;
  }
  if ( (Microsoft_Windows_StorageManagement_WSP_HostEnableBits & 2) != 0 )
  {
    v12 = (const wchar_t *)*((_QWORD *)a1 + 1);
    v13 = 10;
    v14 = *(const wchar_t **)a1;
    v15 = -1;
    if ( v12 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v12[v16] );
      v17 = 2 * v16 + 2;
    }
    else
    {
      v12 = L"NULL";
      v17 = 10;
    }
    v35 = v12;
    v36 = v17;
    v37 = 0;
    if ( v14 )
    {
      do
        ++v15;
      while ( v14[v15] );
      v13 = (unsigned int)(2 * v15 + 2);
    }
    else
    {
      v14 = L"NULL";
    }
    v38 = v14;
    v18 = PROVIDER_LOAD_SUCCEEDED;
    v19 = 3;
    goto LABEL_46;
  }
  return v5;
}

```

## disassembly

```asm
0x180001bc8  push    rbp
0x180001bca  push    rbx
0x180001bcb  push    rsi
0x180001bcc  push    rdi
0x180001bcd  push    r12
0x180001bcf  push    r13
0x180001bd1  push    r14
0x180001bd3  push    r15
0x180001bd5  lea     rbp, [rsp-1Fh]
0x180001bda  sub     rsp, 0F8h
0x180001be1  mov     rax, cs:__security_cookie
0x180001be8  xor     rax, rsp
0x180001beb  mov     [rbp+57h+var_50], rax
0x180001bef  mov     rsi, rcx
0x180001bf2  xor     edx, edx; hFile
0x180001bf4  mov     rcx, [rcx]; lpLibFileName
0x180001bf7  mov     r8d, 800h; dwFlags
0x180001bfd  call    cs:__imp_LoadLibraryExW
0x180001c04  nop     dword ptr [rax+rax+00h]
0x180001c09  mov     r13d, 4
0x180001c0f  xor     r15d, r15d
0x180001c12  mov     [rsi+10h], rax
0x180001c16  lea     r12d, [r13-3]
0x180001c1a  test    rax, rax
0x180001c1d  jnz     short loc_180001C36
0x180001c1f  mov     edi, r12d
0x180001c22  call    cs:__imp_GetLastError
0x180001c29  nop     dword ptr [rax+rax+00h]
0x180001c2e  mov     ebx, r12d
0x180001c31  jmp     loc_180001DC7
0x180001c36  lea     rdx, ProcName; "SetShutdownCallback"
0x180001c3d  mov     rcx, rax; hModule
0x180001c40  call    cs:__imp_GetProcAddress
0x180001c47  nop     dword ptr [rax+rax+00h]
0x180001c4c  test    rax, rax
0x180001c4f  jnz     short loc_180001C56
0x180001c51  lea     edi, [rax+2]
0x180001c54  jmp     short loc_180001C22
0x180001c56  lea     rcx, ?SmpHostShutdownCallback@@YAXXZ; SmpHostShutdownCallback(void)
0x180001c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c62  mov     rcx, [rsi+10h]; hModule
0x180001c66  lea     rdx, aSmpunload; "SmpUnload"
0x180001c6d  call    cs:__imp_GetProcAddress
0x180001c74  nop     dword ptr [rax+rax+00h]
0x180001c79  test    rax, rax
0x180001c7c  jnz     short loc_180001C83
0x180001c7e  lea     edi, [rax+3]
0x180001c81  jmp     short loc_180001C22
0x180001c83  mov     rcx, [rsi+10h]; hModule
0x180001c87  lea     rdx, aPreshutdown; "PreShutdown"
0x180001c8e  mov     [rsi+30h], rax
0x180001c92  call    cs:__imp_GetProcAddress
0x180001c99  nop     dword ptr [rax+rax+00h]
0x180001c9e  test    rax, rax
0x180001ca1  jnz     short loc_180001CAB
0x180001ca3  mov     edi, r13d
0x180001ca6  jmp     loc_180001C22
0x180001cab  mov     rcx, [rsi+10h]; hModule
0x180001caf  lea     rdx, aMiMain; "MI_Main"
0x180001cb6  mov     [rsi+38h], rax
0x180001cba  call    cs:__imp_GetProcAddress
0x180001cc1  nop     dword ptr [rax+rax+00h]
0x180001cc6  mov     r9, rax
0x180001cc9  test    rax, rax
0x180001ccc  jnz     short loc_180001CD6
0x180001cce  lea     edi, [rax+5]
0x180001cd1  jmp     loc_180001C22
0x180001cd6  mov     r10, cs:?g_Application@@3U_MI_Application@@A.ft; _MI_Application g_Application ...
0x180001cdd  lea     rax, [rsi+18h]
0x180001ce1  test    r10, r10
0x180001ce4  jz      loc_180001DA2
0x180001cea  mov     r8, [rsi+8]
0x180001cee  lea     rdx, aRootMicrosoftW; "root\\Microsoft\\Windows\\Storage\\Prov"...
0x180001cf5  mov     [rsp+130h+var_108], rax
0x180001cfa  lea     rcx, ?g_Application@@3U_MI_Application@@A; _MI_Application g_Application
0x180001d01  mov     rax, [r10+10h]
0x180001d05  mov     [rsp+130h+var_110], r15
0x180001d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0f  mov     ebx, eax
0x180001d11  test    eax, eax
0x180001d13  jnz     loc_180001DB6
0x180001d19  lea     edi, [rax+2]
0x180001d1c  test    cs:Microsoft_Windows_StorageManagement_WSP_HostEnableBits, dil
0x180001d23  jz      loc_180001F56
0x180001d29  mov     r8, [rsi+8]
0x180001d2d  lea     ecx, [rax+0Ah]
0x180001d30  mov     rdx, [rsi]
0x180001d33  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001d37  test    r8, r8
0x180001d3a  jz      short loc_180001D53
0x180001d3c  mov     r9, rax
0x180001d3f  inc     r9
0x180001d42  cmp     [r8+r9*2], r15w
0x180001d47  jnz     short loc_180001D3F
0x180001d49  lea     r9d, ds:2[r9*2]
0x180001d51  jmp     short loc_180001D5D
0x180001d53  lea     r8, aNull; "NULL"
0x180001d5a  mov     r9d, ecx
0x180001d5d  mov     [rbp+57h+var_A0], r8
0x180001d61  mov     [rbp+57h+var_98], r9d
0x180001d65  mov     [rbp+57h+var_94], r15d
0x180001d69  test    rdx, rdx
0x180001d6c  jz      short loc_180001D81
0x180001d6e  inc     rax
0x180001d71  cmp     [rdx+rax*2], r15w
0x180001d76  jnz     short loc_180001D6E
0x180001d78  lea     ecx, ds:2[rax*2]
0x180001d7f  jmp     short loc_180001D88
0x180001d81  lea     rdx, aNull; "NULL"
0x180001d88  mov     [rbp+57h+var_90], rdx
0x180001d8c  lea     rax, [rbp+57h+var_B0]
0x180001d90  lea     rdx, PROVIDER_LOAD_SUCCEEDED
0x180001d97  mov     r9d, 3
0x180001d9d  jmp     loc_180001F45
0x180001da2  test    rax, rax
0x180001da5  jz      short loc_180001DB3
0x180001da7  xorps   xmm0, xmm0
0x180001daa  xor     ecx, ecx
0x180001dac  movups  xmmword ptr [rax], xmm0
0x180001daf  mov     [rax+10h], rcx
0x180001db3  mov     ebx, r13d
0x180001db6  mov     edi, 6
0x180001dbb  call    cs:__imp_GetLastError
0x180001dc2  nop     dword ptr [rax+rax+00h]
0x180001dc7  mov     r14d, eax
0x180001dca  mov     rcx, [rsi+8]; String1
0x180001dce  lea     rdx, aMispace; "MISpace"
0x180001dd5  call    cs:__imp__wcsicmp
0x180001ddc  nop     dword ptr [rax+rax+00h]
0x180001de1  test    eax, eax
0x180001de3  jz      short loc_180001DEF
0x180001de5  cmp     r14d, 7Eh ; '~'
0x180001de9  jz      loc_180001F56
0x180001def  mov     eax, cs:dword_180006048
0x180001df5  cmp     eax, 5
0x180001df8  jbe     loc_180001E90
0x180001dfe  mov     rcx, cs:qword_180006060
0x180001e05  mov     rdx, 400000000000h
0x180001e0f  mov     rax, cs:qword_180006058
0x180001e16  test    rdx, rax
0x180001e19  jz      short loc_180001E90
0x180001e1b  mov     rax, rcx
0x180001e1e  and     rax, rdx
0x180001e21  cmp     rax, rcx
0x180001e24  jnz     short loc_180001E90
0x180001e26  mov     rax, [rsi+8]
0x180001e2a  lea     rdx, byte_1800048D9
0x180001e31  mov     [rbp+57h+var_C0], rax
0x180001e35  lea     rax, aLoadprovider; "LoadProvider"
0x180001e3c  mov     [rbp+57h+var_B8], rax
0x180001e40  lea     rax, [rbp+57h+var_C8]
0x180001e44  mov     [rsp+130h+var_E8], rax
0x180001e49  lea     rax, [rsp+130h+var_E0]
0x180001e4e  mov     [rsp+130h+var_F0], rax
0x180001e53  lea     rax, [rsp+130h+var_D8]
0x180001e58  mov     [rsp+130h+var_F8], rax
0x180001e5d  lea     rax, [rbp+57h+var_C0]
0x180001e61  mov     [rsp+130h+var_100], rax
0x180001e66  lea     rax, [rbp+57h+var_D0]
0x180001e6a  mov     [rsp+130h+var_108], rax
0x180001e6f  lea     rax, [rbp+57h+var_B8]
0x180001e73  mov     [rsp+130h+var_110], rax
0x180001e78  mov     [rbp+57h+var_C8], r14d
0x180001e7c  mov     [rsp+130h+var_E0], ebx
0x180001e80  mov     [rsp+130h+var_D8], edi
0x180001e84  mov     [rbp+57h+var_D0], 15Ah
0x180001e8b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180001e90  test    cs:Microsoft_Windows_StorageManagement_WSP_HostEnableBits, r12b
0x180001e97  jz      loc_180001F56
0x180001e9d  mov     r8, [rsi+8]
0x180001ea1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001ea5  mov     rdx, [rsi]
0x180001ea8  mov     ecx, 0Ah
0x180001ead  mov     [rsp+130h+var_E0], r14d
0x180001eb2  mov     [rsp+130h+var_D8], edi
0x180001eb6  mov     [rbp+57h+var_D0], ebx
0x180001eb9  test    r8, r8
0x180001ebc  jz      short loc_180001ED5
0x180001ebe  mov     r9, rax
0x180001ec1  inc     r9
0x180001ec4  cmp     [r8+r9*2], r15w
0x180001ec9  jnz     short loc_180001EC1
0x180001ecb  lea     r9d, ds:2[r9*2]
0x180001ed3  jmp     short loc_180001EDF
0x180001ed5  lea     r8, aNull; "NULL"
0x180001edc  mov     r9d, ecx
0x180001edf  mov     [rbp+57h+var_A0], r8
0x180001ee3  mov     [rbp+57h+var_98], r9d
0x180001ee7  mov     [rbp+57h+var_94], r15d
0x180001eeb  test    rdx, rdx
0x180001eee  jz      short loc_180001F03
0x180001ef0  inc     rax
0x180001ef3  cmp     [rdx+rax*2], r15w
0x180001ef8  jnz     short loc_180001EF0
0x180001efa  lea     ecx, ds:2[rax*2]
0x180001f01  jmp     short loc_180001F0A
0x180001f03  lea     rdx, aNull; "NULL"
0x180001f0a  lea     rax, [rbp+57h+var_D0]
0x180001f0e  mov     [rbp+57h+var_90], rdx
0x180001f12  mov     [rbp+57h+var_80], rax
0x180001f16  lea     rdx, PROVIDER_LOAD_FAILED
0x180001f1d  lea     rax, [rsp+130h+var_D8]
0x180001f22  mov     [rbp+57h+var_78], r13
0x180001f26  mov     [rbp+57h+var_70], rax
0x180001f2a  mov     r9d, 6
0x180001f30  lea     rax, [rsp+130h+var_E0]
0x180001f35  mov     [rbp+57h+var_68], r13
0x180001f39  mov     [rbp+57h+var_60], rax
0x180001f3d  lea     rax, [rbp+57h+var_B0]
0x180001f41  mov     [rbp+57h+var_58], r13
0x180001f45  mov     [rsp+130h+var_110], rax
0x180001f4a  mov     [rbp+57h+var_88], ecx
0x180001f4d  mov     [rbp+57h+var_84], r15d
0x180001f51  call    McGenEventWrite_EventWriteTransfer
0x180001f56  mov     eax, ebx
0x180001f58  mov     rcx, [rbp+57h+var_50]
0x180001f5c  xor     rcx, rsp; StackCookie
0x180001f5f  call    __security_check_cookie
0x180001f64  add     rsp, 0F8h
0x180001f6b  pop     r15
0x180001f6d  pop     r14
0x180001f6f  pop     r13
0x180001f71  pop     r12
0x180001f73  pop     rdi
0x180001f74  pop     rsi
0x180001f75  pop     rbx
0x180001f76  pop     rbp
0x180001f77  retn
```
