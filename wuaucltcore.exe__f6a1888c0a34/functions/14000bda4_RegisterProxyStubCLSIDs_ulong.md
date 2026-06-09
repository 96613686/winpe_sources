# RegisterProxyStubCLSIDs(ulong)

- ea: `0x14000bda4`
- end: `0x14000be6a`
- name: `?RegisterProxyStubCLSIDs@@YAXK@Z`
- size: `198`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140005f84`
- `0x1400066b0`
- `0x1400080bc`
- `0x140008afc`
- `0x140008bbc`

## callees

- `0x14000bda4`
- `0x14000fd28`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000be45`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000be45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000be32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000be32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000be1c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000be1c`

## string_xrefs

- `0x14000bdb8`: `wups.dll`
- `0x14000bdd0`: `wups2.dll`

## pseudocode

```c
void __fastcall RegisterProxyStubCLSIDs(int a1)
{
  __int64 v1; // rsi
  LPCWSTR *v3; // rbx
  HMODULE Library; // rax
  HMODULE v5; // rdi
  FARPROC ProcAddress; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // [rsp+20h] [rbp-38h]
  const wchar_t *v12; // [rsp+28h] [rbp-30h]
  int v13; // [rsp+30h] [rbp-28h]
  const wchar_t *v14; // [rsp+38h] [rbp-20h] BYREF
  int v15; // [rsp+40h] [rbp-18h]
  const wchar_t *v16; // [rsp+48h] [rbp-10h]

  v13 = 1;
  v14 = L"wups.dll";
  v1 = 2;
  v15 = 2;
  v16 = L"wups2.dll";
  v12 = L"Registering proxy/stubs.";
  v11 = 0;
  WUTrace(0, 0, 2048, 4);
  v3 = &v14;
  do
  {
    if ( (a1 & *(_DWORD *)(v3 - 1)) != 0 )
    {
      Library = LoadLibraryExW(*v3, 0, 0x880u);
      v5 = Library;
      if ( Library )
      {
        ProcAddress = GetProcAddress(Library, (LPCSTR)0xA);
        if ( ProcAddress )
          ((void (__fastcall *)(__int64, __int64, __int64, __int64, __int64, const wchar_t *))ProcAddress)(
            v8,
            v7,
            v9,
            v10,
            v11,
            v12);
        FreeLibrary(v5);
      }
    }
    v3 += 2;
    --v1;
  }
  while ( v1 );
}

```

## disassembly

```asm
0x14000bda4  mov     r11, rsp
0x14000bda7  mov     [r11+8], rbx
0x14000bdab  mov     [r11+10h], rbp
0x14000bdaf  mov     [r11+18h], rsi
0x14000bdb3  push    rdi
0x14000bdb4  sub     rsp, 50h
0x14000bdb8  lea     rax, aWupsDll; "wups.dll"
0x14000bdbf  mov     [rsp+58h+var_28], 1
0x14000bdc7  mov     [r11-20h], rax
0x14000bdcb  mov     esi, 2
0x14000bdd0  lea     rax, aWups2Dll; "wups2.dll"
0x14000bdd7  mov     [rsp+58h+var_18], esi
0x14000bddb  mov     [r11-10h], rax
0x14000bddf  mov     ebp, ecx
0x14000bde1  lea     rax, aRegisteringPro; "Registering proxy/stubs."
0x14000bde8  xor     edx, edx
0x14000bdea  mov     [r11-30h], rax
0x14000bdee  lea     r9d, [rsi+2]
0x14000bdf2  xor     ecx, ecx
0x14000bdf4  mov     qword ptr [r11-38h], 0
0x14000bdfc  mov     r8d, 800h
0x14000be02  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14000be07  lea     rbx, [rsp+58h+var_20]
0x14000be0c  test    [rbx-8], ebp
0x14000be0f  jz      short loc_14000BE4B
0x14000be11  mov     rcx, [rbx]; lpLibFileName
0x14000be14  xor     edx, edx; hFile
0x14000be16  mov     r8d, 880h; dwFlags
0x14000be1c  call    cs:__imp_LoadLibraryExW
0x14000be22  mov     rdi, rax
0x14000be25  test    rax, rax
0x14000be28  jz      short loc_14000BE4B
0x14000be2a  mov     edx, 0Ah; lpProcName
0x14000be2f  mov     rcx, rax; hModule
0x14000be32  call    cs:__imp_GetProcAddress
0x14000be38  test    rax, rax
0x14000be3b  jz      short loc_14000BE42
0x14000be3d  call    _guard_dispatch_icall
0x14000be42  mov     rcx, rdi; hLibModule
0x14000be45  call    cs:__imp_FreeLibrary
0x14000be4b  add     rbx, 10h
0x14000be4f  sub     rsi, 1
0x14000be53  jnz     short loc_14000BE0C
0x14000be55  mov     rbx, [rsp+58h+arg_0]
0x14000be5a  mov     rbp, [rsp+58h+arg_8]
0x14000be5f  mov     rsi, [rsp+58h+arg_10]
0x14000be64  add     rsp, 50h
0x14000be68  pop     rdi
0x14000be69  retn
```
