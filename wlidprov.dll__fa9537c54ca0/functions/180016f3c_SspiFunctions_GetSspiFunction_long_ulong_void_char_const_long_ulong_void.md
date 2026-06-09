# SspiFunctions::GetSspiFunction<long (ulong,void *)>(char const *,long (**)(ulong,void *))

- ea: `0x180016f3c`
- end: `0x18001705d`
- name: `??$GetSspiFunction@$$A6AJKPEAX@Z@SspiFunctions@@AEAAJPEBDPEAP6AJKPEAX@Z@Z`
- size: `289`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18003af00`
- `0x18003afe0`

## callees

- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180016f3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016ff1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016ff1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ffc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180016fa3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180016fa3`

## string_xrefs

- `0x180016fce`: `LoadLibrary(sspicli.dll) failed, 0x%X.`
- `0x180016f9c`: `sspicli.dll`

## pseudocode

```c
__int64 __fastcall SspiFunctions::GetSspiFunction<long (unsigned long,void *)>(__int64 a1, const CHAR *a2, FARPROC *a3)
{
  HMODULE LibraryW; // rax
  signed int v7; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v12; // [rsp+20h] [rbp-38h]
  __int64 v13; // [rsp+20h] [rbp-38h]
  signed int v14; // [rsp+28h] [rbp-30h]
  const char *v15; // [rsp+30h] [rbp-28h] BYREF
  signed int *v16; // [rsp+38h] [rbp-20h]
  __int64 v17; // [rsp+40h] [rbp-18h]
  __int64 v18; // [rsp+48h] [rbp-10h]
  signed int v19; // [rsp+60h] [rbp+8h] BYREF

  v19 = 0;
  v17 = 0;
  v18 = 0;
  v15 = "SspiFunctions::GetSspiFunction";
  v16 = &v19;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\executioncontextlite\\sspifunctions.cpp",
    "SspiFunctions::GetSspiFunction",
    (const char *)0x28,
    0,
    v12);
  LibraryW = *(HMODULE *)(a1 + 8);
  if ( LibraryW || (LibraryW = LoadLibraryW(L"sspicli.dll"), (*(_QWORD *)(a1 + 8) = LibraryW) != 0) )
  {
    ProcAddress = GetProcAddress(LibraryW, a2);
    if ( ProcAddress )
    {
      *a3 = ProcAddress;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = LastError;
      v19 = LastError;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\executioncontextlite\\sspifunctions.cpp",
        0x3Cu,
        L"GetProcAddress(%hs) failed, 0x%X.",
        a2,
        v14,
        v15,
        v16,
        v17,
        v18);
    }
  }
  else
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    v19 = v7;
    LODWORD(v13) = v7;
    TracePrintW(
      3u,
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\executioncontextlite\\sspifunctions.cpp",
      0x33u,
      L"LoadLibrary(sspicli.dll) failed, 0x%X.",
      v13);
  }
  v10 = v19;
  CTraceFuncW<long>::~CTraceFuncW<long>(&v15);
  return v10;
}

```

## disassembly

```asm
0x180016f3c  mov     r11, rsp
0x180016f3f  mov     [r11+10h], rbx
0x180016f43  mov     [r11+18h], rsi
0x180016f47  push    rdi
0x180016f48  sub     rsp, 50h
0x180016f4c  xor     r9d, r9d; unsigned int
0x180016f4f  mov     [rsp+58h+arg_0], 0
0x180016f57  mov     rbx, rdx
0x180016f5a  mov     qword ptr [r11-18h], 0
0x180016f62  mov     rsi, r8
0x180016f65  mov     qword ptr [r11-10h], 0
0x180016f6d  mov     rdi, rcx
0x180016f70  lea     rdx, aSspifunctionsG; "SspiFunctions::GetSspiFunction"
0x180016f77  lea     rax, [r11+8]
0x180016f7b  mov     [r11-28h], rdx
0x180016f7f  lea     r8d, [r9+28h]; char *
0x180016f83  mov     [r11-20h], rax
0x180016f87  lea     rcx, aOnecoreuapDsEx_17; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180016f8e  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180016f93  mov     rax, [rdi+8]
0x180016f97  test    rax, rax
0x180016f9a  jnz     short loc_180016FEB
0x180016f9c  lea     rcx, LibFileName; "sspicli.dll"
0x180016fa3  call    cs:__imp_LoadLibraryW
0x180016fa9  mov     [rdi+8], rax
0x180016fad  test    rax, rax
0x180016fb0  jnz     short loc_180016FEB
0x180016fb2  call    cs:__imp_GetLastError
0x180016fb8  test    eax, eax
0x180016fba  jle     short loc_180016FC4
0x180016fbc  movzx   eax, ax
0x180016fbf  or      eax, 80070000h
0x180016fc4  mov     r8d, 33h ; '3'; unsigned int
0x180016fca  mov     [rsp+58h+arg_0], eax
0x180016fce  lea     r9, aLoadlibrarySsp; "LoadLibrary(sspicli.dll) failed, 0x%X."
0x180016fd5  mov     dword ptr [rsp+58h+var_38], eax
0x180016fd9  lea     rdx, aOnecoreuapDsEx_17; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x180016fe0  lea     ecx, [r8-30h]; unsigned __int8
0x180016fe4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180016fe9  jmp     short loc_18001703D
0x180016feb  mov     rdx, rbx; lpProcName
0x180016fee  mov     rcx, rax; hModule
0x180016ff1  call    cs:__imp_GetProcAddress
0x180016ff7  test    rax, rax
0x180016ffa  jnz     short loc_18001703A
0x180016ffc  call    cs:__imp_GetLastError
0x180017002  test    eax, eax
0x180017004  jle     short loc_18001700E
0x180017006  movzx   eax, ax
0x180017009  or      eax, 80070000h
0x18001700e  mov     r8d, 3Ch ; '<'; unsigned int
0x180017014  mov     [rsp+58h+var_30], eax
0x180017018  lea     r9, aGetprocaddress; "GetProcAddress(%hs) failed, 0x%X."
0x18001701f  mov     [rsp+58h+arg_0], eax
0x180017023  lea     rdx, aOnecoreuapDsEx_17; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x18001702a  mov     [rsp+58h+var_38], rbx
0x18001702f  lea     ecx, [r8-39h]; unsigned __int8
0x180017033  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180017038  jmp     short loc_18001703D
0x18001703a  mov     [rsi], rax
0x18001703d  mov     ebx, [rsp+58h+arg_0]
0x180017041  lea     rcx, [rsp+58h+var_28]
0x180017046  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18001704b  mov     rsi, [rsp+58h+arg_10]
0x180017050  mov     eax, ebx
0x180017052  mov     rbx, [rsp+58h+arg_8]
0x180017057  add     rsp, 50h
0x18001705b  pop     rdi
0x18001705c  retn
```
