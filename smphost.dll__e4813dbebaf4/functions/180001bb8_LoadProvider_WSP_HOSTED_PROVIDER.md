# LoadProvider(_WSP_HOSTED_PROVIDER *)

- ea: `0x180001bb8`
- end: `0x180001f35`
- name: `?LoadProvider@@YA?AW4_MI_Result@@PEAU_WSP_HOSTED_PROVIDER@@@Z`
- size: `893`
- prototype: `__int64 __fastcall(struct _WSP_HOSTED_PROVIDER *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001fec`

## callees

- `0x1800010b0`
- `0x180001bb8`
- `0x180002770`
- `0x180002890`
- `0x180003010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001d98`
- `msvcrt!_wcsicmp` at `0x180001d98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d84`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001c89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001bed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001bed`

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
0x180001bb8  push    rbp
0x180001bba  push    rbx
0x180001bbb  push    rsi
0x180001bbc  push    rdi
0x180001bbd  push    r12
0x180001bbf  push    r13
0x180001bc1  push    r14
0x180001bc3  push    r15
0x180001bc5  lea     rbp, [rsp-1Fh]
0x180001bca  sub     rsp, 0F8h
0x180001bd1  mov     rax, cs:__security_cookie
0x180001bd8  xor     rax, rsp
0x180001bdb  mov     [rbp+57h+var_50], rax
0x180001bdf  mov     rsi, rcx
0x180001be2  xor     edx, edx; hFile
0x180001be4  mov     rcx, [rcx]; lpLibFileName
0x180001be7  mov     r8d, 800h; dwFlags
0x180001bed  call    cs:__imp_LoadLibraryExW
0x180001bf3  mov     r13d, 4
0x180001bf9  xor     r15d, r15d
0x180001bfc  mov     [rsi+10h], rax
0x180001c00  lea     r12d, [r13-3]
0x180001c04  test    rax, rax
0x180001c07  jnz     short loc_180001C1A
0x180001c09  mov     edi, r12d
0x180001c0c  call    cs:__imp_GetLastError
0x180001c12  mov     ebx, r12d
0x180001c15  jmp     loc_180001D8A
0x180001c1a  lea     rdx, ProcName; "SetShutdownCallback"
0x180001c21  mov     rcx, rax; hModule
0x180001c24  call    cs:__imp_GetProcAddress
0x180001c2a  test    rax, rax
0x180001c2d  jnz     short loc_180001C34
0x180001c2f  lea     edi, [rax+2]
0x180001c32  jmp     short loc_180001C0C
0x180001c34  lea     rcx, ?SmpHostShutdownCallback@@YAXXZ; SmpHostShutdownCallback(void)
0x180001c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c40  mov     rcx, [rsi+10h]; hModule
0x180001c44  lea     rdx, aSmpunload; "SmpUnload"
0x180001c4b  call    cs:__imp_GetProcAddress
0x180001c51  test    rax, rax
0x180001c54  jnz     short loc_180001C5B
0x180001c56  lea     edi, [rax+3]
0x180001c59  jmp     short loc_180001C0C
0x180001c5b  mov     rcx, [rsi+10h]; hModule
0x180001c5f  lea     rdx, aPreshutdown; "PreShutdown"
0x180001c66  mov     [rsi+30h], rax
0x180001c6a  call    cs:__imp_GetProcAddress
0x180001c70  test    rax, rax
0x180001c73  jnz     short loc_180001C7A
0x180001c75  mov     edi, r13d
0x180001c78  jmp     short loc_180001C0C
0x180001c7a  mov     rcx, [rsi+10h]; hModule
0x180001c7e  lea     rdx, aMiMain; "MI_Main"
0x180001c85  mov     [rsi+38h], rax
0x180001c89  call    cs:__imp_GetProcAddress
0x180001c8f  mov     r9, rax
0x180001c92  test    rax, rax
0x180001c95  jnz     short loc_180001C9F
0x180001c97  lea     edi, [rax+5]
0x180001c9a  jmp     loc_180001C0C
0x180001c9f  mov     r10, cs:?g_Application@@3U_MI_Application@@A.ft; _MI_Application g_Application ...
0x180001ca6  lea     rax, [rsi+18h]
0x180001caa  test    r10, r10
0x180001cad  jz      loc_180001D6B
0x180001cb3  mov     r8, [rsi+8]
0x180001cb7  lea     rdx, aRootMicrosoftW; "root\\Microsoft\\Windows\\Storage\\Prov"...
0x180001cbe  mov     [rsp+130h+var_108], rax
0x180001cc3  lea     rcx, ?g_Application@@3U_MI_Application@@A; _MI_Application g_Application
0x180001cca  mov     rax, [r10+10h]
0x180001cce  mov     [rsp+130h+var_110], r15
0x180001cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cd8  mov     ebx, eax
0x180001cda  test    eax, eax
0x180001cdc  jnz     loc_180001D7F
0x180001ce2  lea     edi, [rax+2]
0x180001ce5  test    cs:Microsoft_Windows_StorageManagement_WSP_HostEnableBits, dil
0x180001cec  jz      loc_180001F13
0x180001cf2  mov     r8, [rsi+8]
0x180001cf6  lea     ecx, [rax+0Ah]
0x180001cf9  mov     rdx, [rsi]
0x180001cfc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001d00  test    r8, r8
0x180001d03  jz      short loc_180001D1C
0x180001d05  mov     r9, rax
0x180001d08  inc     r9
0x180001d0b  cmp     [r8+r9*2], r15w
0x180001d10  jnz     short loc_180001D08
0x180001d12  lea     r9d, ds:2[r9*2]
0x180001d1a  jmp     short loc_180001D26
0x180001d1c  lea     r8, aNull; "NULL"
0x180001d23  mov     r9d, ecx
0x180001d26  mov     [rbp+57h+var_A0], r8
0x180001d2a  mov     [rbp+57h+var_98], r9d
0x180001d2e  mov     [rbp+57h+var_94], r15d
0x180001d32  test    rdx, rdx
0x180001d35  jz      short loc_180001D4A
0x180001d37  inc     rax
0x180001d3a  cmp     [rdx+rax*2], r15w
0x180001d3f  jnz     short loc_180001D37
0x180001d41  lea     ecx, ds:2[rax*2]
0x180001d48  jmp     short loc_180001D51
0x180001d4a  lea     rdx, aNull; "NULL"
0x180001d51  mov     [rbp+57h+var_90], rdx
0x180001d55  lea     rax, [rbp+57h+var_B0]
0x180001d59  lea     rdx, PROVIDER_LOAD_SUCCEEDED
0x180001d60  mov     r9d, 3
0x180001d66  jmp     loc_180001F02
0x180001d6b  test    rax, rax
0x180001d6e  jz      short loc_180001D7C
0x180001d70  xorps   xmm0, xmm0
0x180001d73  xor     ecx, ecx
0x180001d75  movups  xmmword ptr [rax], xmm0
0x180001d78  mov     [rax+10h], rcx
0x180001d7c  mov     ebx, r13d
0x180001d7f  mov     edi, 6
0x180001d84  call    cs:__imp_GetLastError
0x180001d8a  mov     r14d, eax
0x180001d8d  mov     rcx, [rsi+8]; String1
0x180001d91  lea     rdx, aMispace; "MISpace"
0x180001d98  call    cs:__imp__wcsicmp
0x180001d9e  test    eax, eax
0x180001da0  jz      short loc_180001DAC
0x180001da2  cmp     r14d, 7Eh ; '~'
0x180001da6  jz      loc_180001F13
0x180001dac  mov     eax, cs:dword_180006048
0x180001db2  cmp     eax, 5
0x180001db5  jbe     loc_180001E4D
0x180001dbb  mov     rcx, cs:qword_180006060
0x180001dc2  mov     rdx, 400000000000h
0x180001dcc  mov     rax, cs:qword_180006058
0x180001dd3  test    rdx, rax
0x180001dd6  jz      short loc_180001E4D
0x180001dd8  mov     rax, rcx
0x180001ddb  and     rax, rdx
0x180001dde  cmp     rax, rcx
0x180001de1  jnz     short loc_180001E4D
0x180001de3  mov     rax, [rsi+8]
0x180001de7  lea     rdx, byte_1800048D9
0x180001dee  mov     [rbp+57h+var_C0], rax
0x180001df2  lea     rax, aLoadprovider; "LoadProvider"
0x180001df9  mov     [rbp+57h+var_B8], rax
0x180001dfd  lea     rax, [rbp+57h+var_C8]
0x180001e01  mov     [rsp+130h+var_E8], rax
0x180001e06  lea     rax, [rsp+130h+var_E0]
0x180001e0b  mov     [rsp+130h+var_F0], rax
0x180001e10  lea     rax, [rsp+130h+var_D8]
0x180001e15  mov     [rsp+130h+var_F8], rax
0x180001e1a  lea     rax, [rbp+57h+var_C0]
0x180001e1e  mov     [rsp+130h+var_100], rax
0x180001e23  lea     rax, [rbp+57h+var_D0]
0x180001e27  mov     [rsp+130h+var_108], rax
0x180001e2c  lea     rax, [rbp+57h+var_B8]
0x180001e30  mov     [rsp+130h+var_110], rax
0x180001e35  mov     [rbp+57h+var_C8], r14d
0x180001e39  mov     [rsp+130h+var_E0], ebx
0x180001e3d  mov     [rsp+130h+var_D8], edi
0x180001e41  mov     [rbp+57h+var_D0], 15Ah
0x180001e48  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180001e4d  test    cs:Microsoft_Windows_StorageManagement_WSP_HostEnableBits, r12b
0x180001e54  jz      loc_180001F13
0x180001e5a  mov     r8, [rsi+8]
0x180001e5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001e62  mov     rdx, [rsi]
0x180001e65  mov     ecx, 0Ah
0x180001e6a  mov     [rsp+130h+var_E0], r14d
0x180001e6f  mov     [rsp+130h+var_D8], edi
0x180001e73  mov     [rbp+57h+var_D0], ebx
0x180001e76  test    r8, r8
0x180001e79  jz      short loc_180001E92
0x180001e7b  mov     r9, rax
0x180001e7e  inc     r9
0x180001e81  cmp     [r8+r9*2], r15w
0x180001e86  jnz     short loc_180001E7E
0x180001e88  lea     r9d, ds:2[r9*2]
0x180001e90  jmp     short loc_180001E9C
0x180001e92  lea     r8, aNull; "NULL"
0x180001e99  mov     r9d, ecx
0x180001e9c  mov     [rbp+57h+var_A0], r8
0x180001ea0  mov     [rbp+57h+var_98], r9d
0x180001ea4  mov     [rbp+57h+var_94], r15d
0x180001ea8  test    rdx, rdx
0x180001eab  jz      short loc_180001EC0
0x180001ead  inc     rax
0x180001eb0  cmp     [rdx+rax*2], r15w
0x180001eb5  jnz     short loc_180001EAD
0x180001eb7  lea     ecx, ds:2[rax*2]
0x180001ebe  jmp     short loc_180001EC7
0x180001ec0  lea     rdx, aNull; "NULL"
0x180001ec7  lea     rax, [rbp+57h+var_D0]
0x180001ecb  mov     [rbp+57h+var_90], rdx
0x180001ecf  mov     [rbp+57h+var_80], rax
0x180001ed3  lea     rdx, PROVIDER_LOAD_FAILED
0x180001eda  lea     rax, [rsp+130h+var_D8]
0x180001edf  mov     [rbp+57h+var_78], r13
0x180001ee3  mov     [rbp+57h+var_70], rax
0x180001ee7  mov     r9d, 6
0x180001eed  lea     rax, [rsp+130h+var_E0]
0x180001ef2  mov     [rbp+57h+var_68], r13
0x180001ef6  mov     [rbp+57h+var_60], rax
0x180001efa  lea     rax, [rbp+57h+var_B0]
0x180001efe  mov     [rbp+57h+var_58], r13
0x180001f02  mov     [rsp+130h+var_110], rax
0x180001f07  mov     [rbp+57h+var_88], ecx
0x180001f0a  mov     [rbp+57h+var_84], r15d
0x180001f0e  call    McGenEventWrite_EventWriteTransfer
0x180001f13  mov     eax, ebx
0x180001f15  mov     rcx, [rbp+57h+var_50]
0x180001f19  xor     rcx, rsp; StackCookie
0x180001f1c  call    __security_check_cookie
0x180001f21  add     rsp, 0F8h
0x180001f28  pop     r15
0x180001f2a  pop     r14
0x180001f2c  pop     r13
0x180001f2e  pop     r12
0x180001f30  pop     rdi
0x180001f31  pop     rsi
0x180001f32  pop     rbx
0x180001f33  pop     rbp
0x180001f34  retn
```
