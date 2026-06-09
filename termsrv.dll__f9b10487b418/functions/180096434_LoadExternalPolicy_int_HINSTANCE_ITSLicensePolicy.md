# LoadExternalPolicy(int,HINSTANCE__ * *,ITSLicensePolicy * *)

- ea: `0x180096434`
- end: `0x18009658a`
- name: `?LoadExternalPolicy@@YAJHPEAPEAUHINSTANCE__@@PEAPEAVITSLicensePolicy@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(int, HINSTANCE *, struct ITSLicensePolicy **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180024240`
- `0x18009b758`

## callees

- `0x18000a210`
- `0x180096434`
- `0x1800b1570`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800964c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800964d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800964ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800964c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800964d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800964ec`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800964a5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800964a5`

## string_xrefs

- `0x18009649e`: `tssrvlic.dll`

## pseudocode

```c
__int64 __fastcall LoadExternalPolicy(int a1, HINSTANCE *a2, struct ITSLicensePolicy **a3)
{
  unsigned int IsAppServerInstalled; // eax
  int v7; // r9d
  unsigned int v8; // ebx
  HMODULE LibraryW; // rax
  HMODULE v10; // rdi
  FARPROC ProcAddress; // r12
  FARPROC v12; // rbp
  FARPROC v13; // rax
  int v14; // eax
  int v15; // eax
  struct ITSLicensePolicy *v16; // rax
  int v18; // [rsp+50h] [rbp+8h] BYREF
  struct ITSLicensePolicy *v19; // [rsp+68h] [rbp+20h] BYREF

  v19 = 0;
  v18 = 0;
  IsAppServerInstalled = CSLQuery::IsAppServerInstalled(&v18);
  v7 = v18;
  v8 = IsAppServerInstalled;
  if ( IsAppServerInstalled )
    v7 = 0;
  if ( a1 && v7 )
  {
    _DbgPrintMessage(8, "Server licensing module must not be loaded for default policy on AppServer");
  }
  else
  {
    LibraryW = LoadLibraryW(L"tssrvlic.dll");
    v10 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SrvLicInitialize");
      v12 = GetProcAddress(v10, "LoadPolicy");
      v13 = GetProcAddress(v10, "Shutdown");
      if ( ProcAddress && v12 && v13 )
      {
        v14 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1 != 0 ? 4 : 1);
        v8 = v14;
        if ( v14 < 0 )
        {
          _DbgPrintMessage(8, "pfnInitialize failed: 0x%x in %s", (unsigned int)v14, "LoadExternalPolicy");
          return v8;
        }
        v15 = ((__int64 (__fastcall *)(struct ITSLicensePolicy **))v12)(&v19);
        v8 = v15;
        if ( v15 < 0 )
        {
          _DbgPrintMessage(8, "pfnLoadPolicy failed: 0x%x in %s", (unsigned int)v15, "LoadExternalPolicy");
          return v8;
        }
      }
      else
      {
        _DbgPrintMessage(8, "Server licensing module does not export functions as expected");
        if ( (v8 & 0x80000000) != 0 )
          return v8;
      }
      v16 = v19;
      *a2 = v10;
      *a3 = v16;
      return v8;
    }
    _DbgPrintMessage(8, "Server licensing module could not be loaded");
  }
  return (unsigned int)-2147023286;
}

```

## disassembly

```asm
0x180096434  mov     rax, rsp
0x180096437  mov     [rax+10h], rbx
0x18009643b  mov     [rax+18h], rbp
0x18009643f  push    rsi
0x180096440  push    rdi
0x180096441  push    r12
0x180096443  push    r14
0x180096445  push    r15
0x180096447  sub     rsp, 20h
0x18009644b  mov     esi, ecx
0x18009644d  mov     qword ptr [rax+20h], 0
0x180096455  lea     rcx, [rax+8]; int *
0x180096459  mov     dword ptr [rax+8], 0
0x180096460  mov     r14, r8
0x180096463  mov     r15, rdx
0x180096466  call    ?IsAppServerInstalled@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAppServerInstalled(int *)
0x18009646b  mov     r9d, [rsp+48h+arg_0]
0x180096470  mov     ebx, eax
0x180096472  xor     eax, eax
0x180096474  test    ebx, ebx
0x180096476  cmovnz  r9d, eax
0x18009647a  test    esi, esi
0x18009647c  jz      short loc_18009649E
0x18009647e  test    r9d, r9d
0x180096481  jz      short loc_18009649E
0x180096483  lea     rdx, aServerLicensin_0; "Server licensing module must not be loa"...
0x18009648a  mov     ecx, 8; int
0x18009648f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180096494  mov     ebx, 8007064Ah
0x180096499  jmp     loc_180096571
0x18009649e  lea     rcx, aTssrvlicDll; "tssrvlic.dll"
0x1800964a5  call    cs:__imp_LoadLibraryW
0x1800964ab  mov     rdi, rax
0x1800964ae  test    rax, rax
0x1800964b1  jnz     short loc_1800964BC
0x1800964b3  lea     rdx, aServerLicensin_2; "Server licensing module could not be lo"...
0x1800964ba  jmp     short loc_18009648A
0x1800964bc  lea     rdx, aSrvlicinitiali; "SrvLicInitialize"
0x1800964c3  mov     rcx, rdi; hModule
0x1800964c6  call    cs:__imp_GetProcAddress
0x1800964cc  lea     rdx, aLoadpolicy; "LoadPolicy"
0x1800964d3  mov     rcx, rdi; hModule
0x1800964d6  mov     r12, rax
0x1800964d9  call    cs:__imp_GetProcAddress
0x1800964df  lea     rdx, aShutdown; "Shutdown"
0x1800964e6  mov     rcx, rdi; hModule
0x1800964e9  mov     rbp, rax
0x1800964ec  call    cs:__imp_GetProcAddress
0x1800964f2  test    r12, r12
0x1800964f5  jz      short loc_180096551
0x1800964f7  test    rbp, rbp
0x1800964fa  jz      short loc_180096551
0x1800964fc  test    rax, rax
0x1800964ff  jz      short loc_180096551
0x180096501  neg     esi
0x180096503  mov     rax, r12
0x180096506  sbb     ecx, ecx
0x180096508  and     ecx, 3
0x18009650b  inc     ecx
0x18009650d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096512  mov     ebx, eax
0x180096514  test    eax, eax
0x180096516  jns     short loc_180096535
0x180096518  lea     rdx, aPfninitializeF; "pfnInitialize failed: 0x%x in %s"
0x18009651f  mov     r8d, eax
0x180096522  lea     r9, aLoadexternalpo; "LoadExternalPolicy"
0x180096529  mov     ecx, 8; int
0x18009652e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180096533  jmp     short loc_180096571
0x180096535  lea     rcx, [rsp+48h+arg_18]
0x18009653a  mov     rax, rbp
0x18009653d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096542  mov     ebx, eax
0x180096544  test    eax, eax
0x180096546  jns     short loc_180096566
0x180096548  lea     rdx, aPfnloadpolicyF; "pfnLoadPolicy failed: 0x%x in %s"
0x18009654f  jmp     short loc_18009651F
0x180096551  lea     rdx, aServerLicensin; "Server licensing module does not export"...
0x180096558  mov     ecx, 8; int
0x18009655d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180096562  test    ebx, ebx
0x180096564  js      short loc_180096571
0x180096566  mov     rax, [rsp+48h+arg_18]
0x18009656b  mov     [r15], rdi
0x18009656e  mov     [r14], rax
0x180096571  mov     rbp, [rsp+48h+arg_10]
0x180096576  mov     eax, ebx
0x180096578  mov     rbx, [rsp+48h+arg_8]
0x18009657d  add     rsp, 20h
0x180096581  pop     r15
0x180096583  pop     r14
0x180096585  pop     r12
0x180096587  pop     rdi
0x180096588  pop     rsi
0x180096589  retn
```
