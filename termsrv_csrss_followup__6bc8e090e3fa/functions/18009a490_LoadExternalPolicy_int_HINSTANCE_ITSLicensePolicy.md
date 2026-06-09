# LoadExternalPolicy(int,HINSTANCE__ * *,ITSLicensePolicy * *)

- ea: `0x18009a490`
- end: `0x18009a5ff`
- name: `?LoadExternalPolicy@@YAJHPEAPEAUHINSTANCE__@@PEAPEAVITSLicensePolicy@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(int, HINSTANCE *, struct ITSLicensePolicy **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800255e0`
- `0x18009f97c`

## callees

- `0x180009940`
- `0x18009a490`
- `0x1800b7890`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a528`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a541`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a55a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a528`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a541`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009a55a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009a501`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18009a501`

## string_xrefs

- `0x18009a4fa`: `tssrvlic.dll`

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
0x18009a490  mov     rax, rsp
0x18009a493  mov     [rax+10h], rbx
0x18009a497  mov     [rax+18h], rbp
0x18009a49b  push    rsi
0x18009a49c  push    rdi
0x18009a49d  push    r12
0x18009a49f  push    r14
0x18009a4a1  push    r15
0x18009a4a3  sub     rsp, 20h
0x18009a4a7  mov     esi, ecx
0x18009a4a9  mov     qword ptr [rax+20h], 0
0x18009a4b1  lea     rcx, [rax+8]; int *
0x18009a4b5  mov     dword ptr [rax+8], 0
0x18009a4bc  mov     r14, r8
0x18009a4bf  mov     r15, rdx
0x18009a4c2  call    ?IsAppServerInstalled@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAppServerInstalled(int *)
0x18009a4c7  mov     r9d, [rsp+48h+arg_0]
0x18009a4cc  mov     ebx, eax
0x18009a4ce  xor     eax, eax
0x18009a4d0  test    ebx, ebx
0x18009a4d2  cmovnz  r9d, eax
0x18009a4d6  test    esi, esi
0x18009a4d8  jz      short loc_18009A4FA
0x18009a4da  test    r9d, r9d
0x18009a4dd  jz      short loc_18009A4FA
0x18009a4df  lea     rdx, aServerLicensin_0; "Server licensing module must not be loa"...
0x18009a4e6  mov     ecx, 8; int
0x18009a4eb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009a4f0  mov     ebx, 8007064Ah
0x18009a4f5  jmp     loc_18009A5E5
0x18009a4fa  lea     rcx, aTssrvlicDll; "tssrvlic.dll"
0x18009a501  call    cs:__imp_LoadLibraryW
0x18009a508  nop     dword ptr [rax+rax+00h]
0x18009a50d  mov     rdi, rax
0x18009a510  test    rax, rax
0x18009a513  jnz     short loc_18009A51E
0x18009a515  lea     rdx, aServerLicensin_2; "Server licensing module could not be lo"...
0x18009a51c  jmp     short loc_18009A4E6
0x18009a51e  lea     rdx, aSrvlicinitiali; "SrvLicInitialize"
0x18009a525  mov     rcx, rdi; hModule
0x18009a528  call    cs:__imp_GetProcAddress
0x18009a52f  nop     dword ptr [rax+rax+00h]
0x18009a534  lea     rdx, aLoadpolicy; "LoadPolicy"
0x18009a53b  mov     rcx, rdi; hModule
0x18009a53e  mov     r12, rax
0x18009a541  call    cs:__imp_GetProcAddress
0x18009a548  nop     dword ptr [rax+rax+00h]
0x18009a54d  lea     rdx, aShutdown; "Shutdown"
0x18009a554  mov     rcx, rdi; hModule
0x18009a557  mov     rbp, rax
0x18009a55a  call    cs:__imp_GetProcAddress
0x18009a561  nop     dword ptr [rax+rax+00h]
0x18009a566  test    r12, r12
0x18009a569  jz      short loc_18009A5C5
0x18009a56b  test    rbp, rbp
0x18009a56e  jz      short loc_18009A5C5
0x18009a570  test    rax, rax
0x18009a573  jz      short loc_18009A5C5
0x18009a575  neg     esi
0x18009a577  mov     rax, r12
0x18009a57a  sbb     ecx, ecx
0x18009a57c  and     ecx, 3
0x18009a57f  inc     ecx
0x18009a581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a586  mov     ebx, eax
0x18009a588  test    eax, eax
0x18009a58a  jns     short loc_18009A5A9
0x18009a58c  lea     rdx, aPfninitializeF; "pfnInitialize failed: 0x%x in %s"
0x18009a593  mov     r8d, eax
0x18009a596  lea     r9, aLoadexternalpo; "LoadExternalPolicy"
0x18009a59d  mov     ecx, 8; int
0x18009a5a2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009a5a7  jmp     short loc_18009A5E5
0x18009a5a9  lea     rcx, [rsp+48h+arg_18]
0x18009a5ae  mov     rax, rbp
0x18009a5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a5b6  mov     ebx, eax
0x18009a5b8  test    eax, eax
0x18009a5ba  jns     short loc_18009A5DA
0x18009a5bc  lea     rdx, aPfnloadpolicyF; "pfnLoadPolicy failed: 0x%x in %s"
0x18009a5c3  jmp     short loc_18009A593
0x18009a5c5  lea     rdx, aServerLicensin; "Server licensing module does not export"...
0x18009a5cc  mov     ecx, 8; int
0x18009a5d1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18009a5d6  test    ebx, ebx
0x18009a5d8  js      short loc_18009A5E5
0x18009a5da  mov     rax, [rsp+48h+arg_18]
0x18009a5df  mov     [r15], rdi
0x18009a5e2  mov     [r14], rax
0x18009a5e5  mov     rbp, [rsp+48h+arg_10]
0x18009a5ea  mov     eax, ebx
0x18009a5ec  mov     rbx, [rsp+48h+arg_8]
0x18009a5f1  add     rsp, 20h
0x18009a5f5  pop     r15
0x18009a5f7  pop     r14
0x18009a5f9  pop     r12
0x18009a5fb  pop     rdi
0x18009a5fc  pop     rsi
0x18009a5fd  retn
```
