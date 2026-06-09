# InitDiamond(void)

- ea: `0x180002398`
- end: `0x1800025b1`
- name: `?InitDiamond@@YAKXZ`
- size: `537`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002b00`

## callees

- `0x180002398`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800023dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800023dc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800023ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800024e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002549`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000255e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000256f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800023ad`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800024e1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002549`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000255e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000256f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800024ce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002582`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800024ce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002582`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002425`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000245b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002476`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002425`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000245b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002476`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800023c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800023c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800025a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800025a0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800023ff`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800023ff`

## string_xrefs

- `0x1800023f8`: `CABINET.DLL`
- `0x18000241b`: `FDICreate`
- `0x180002468`: `FDICopy`

## pseudocode

```c
__int64 InitDiamond(void)
{
  HLOCAL v0; // rax
  void *v1; // rbx
  HMODULE LibraryW; // rax
  int (*ProcAddress)(void *, char *, char *, int, __int64 (*)(enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *), int (*)(struct FDIDECRYPT *), void *); // rax
  void *(*v5)(void *(*)(unsigned int), void (*)(void *), __int64 (*)(char *, int, int), unsigned int (*)(__int64, void *, unsigned int), unsigned int (*)(__int64, void *, unsigned int), int (*)(__int64), int (*)(__int64, int, int), int, struct ERF *); // rbx
  char *Value; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx

  if ( itlsDiamondContext == -1 )
    return 0x8000;
  if ( TlsGetValue(itlsDiamondContext) )
    return 0x8000;
  v0 = LocalAlloc(0, 0x20u);
  v1 = v0;
  if ( !v0 )
    return 0x8000;
  if ( !TlsSetValue(itlsDiamondContext, v0) )
  {
    LocalFree(v1);
    return 0x8000;
  }
  if ( !cCabinetLoad )
  {
    LibraryW = LoadLibraryW(L"CABINET.DLL");
    hCabinet = LibraryW;
    if ( !LibraryW )
      return 0x100000;
    pFDICreate = (void *(*)(void *(*)(unsigned int), void (*)(void *), __int64 (*)(char *, int, int), unsigned int (*)(__int64, void *, unsigned int), unsigned int (*)(__int64, void *, unsigned int), int (*)(__int64), int (*)(__int64, int, int), int, struct ERF *))GetProcAddress(LibraryW, "FDICreate");
    pFDIDestroy = (int (*)(void *))GetProcAddress(hCabinet, "FDIDestroy");
    pFDIIsCabinet = (int (*)(void *, __int64, struct FDICABINETINFO *))GetProcAddress(hCabinet, "FDIIsCabinet");
    ProcAddress = (int (*)(void *, char *, char *, int, __int64 (*)(enum FDINOTIFICATIONTYPE, struct FDINOTIFICATION *), int (*)(struct FDIDECRYPT *), void *))GetProcAddress(hCabinet, "FDICopy");
    pFDICopy = ProcAddress;
    if ( !pFDICreate || !pFDIDestroy || !pFDIIsCabinet || !ProcAddress )
    {
      FreeLibrary(hCabinet);
      return 0x100000;
    }
    if ( _InterlockedExchangeAdd(&cCabinetLoad, 1u) )
      FreeLibrary(hCabinet);
  }
  v5 = pFDICreate;
  Value = (char *)TlsGetValue(itlsDiamondContext);
  v7 = ((__int64 (__fastcall *)(void *(__fastcall *)(unsigned int), HLOCAL (__stdcall *)(HLOCAL), __int64 (__fastcall *)(char *, int, int), unsigned int (__fastcall *)(__int64, void *, unsigned int), unsigned int (__fastcall *)(__int64, void *, unsigned int), __int64 (__fastcall *)(__int64), __int64 (__fastcall *)(__int64, int, int), int, char *))v5)(
         SpdFdiAlloc,
         SpdFdiFree,
         SpdFdiOpen,
         SpdFdiRead,
         SpdFdiWrite,
         SpdFdiClose,
         SpdFdiSeek,
         -1,
         Value + 16);
  *((_QWORD *)TlsGetValue(itlsDiamondContext) + 1) = v7;
  if ( itlsDiamondContext == -1 || !TlsGetValue(itlsDiamondContext) )
    v8 = 0;
  else
    v8 = *((_QWORD *)TlsGetValue(itlsDiamondContext) + 1);
  return v8 == 0 ? 0x100000 : 0;
}

```

## disassembly

```asm
0x180002398  push    rbx
0x18000239a  sub     rsp, 50h
0x18000239e  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800023a4  cmp     ecx, 0FFFFFFFFh
0x1800023a7  jz      loc_1800025A6
0x1800023ad  call    cs:__imp_TlsGetValue
0x1800023b3  test    rax, rax
0x1800023b6  jnz     loc_1800025A6
0x1800023bc  lea     edx, [rax+20h]; uBytes
0x1800023bf  xor     ecx, ecx; uFlags
0x1800023c1  call    cs:__imp_LocalAlloc
0x1800023c7  mov     rbx, rax
0x1800023ca  test    rax, rax
0x1800023cd  jz      loc_1800025A6
0x1800023d3  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800023d9  mov     rdx, rax; lpTlsValue
0x1800023dc  call    cs:__imp_TlsSetValue
0x1800023e2  test    eax, eax
0x1800023e4  jz      loc_18000259D
0x1800023ea  mov     eax, cs:?cCabinetLoad@@3JC; long volatile cCabinetLoad
0x1800023f0  test    eax, eax
0x1800023f2  jnz     loc_1800024D4
0x1800023f8  lea     rcx, LibFileName; "CABINET.DLL"
0x1800023ff  call    cs:__imp_LoadLibraryW
0x180002405  mov     cs:?hCabinet@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * hCabinet
0x18000240c  test    rax, rax
0x18000240f  jnz     short loc_18000241B
0x180002411  mov     eax, 100000h
0x180002416  jmp     loc_1800025AB
0x18000241b  lea     rdx, ProcName; "FDICreate"
0x180002422  mov     rcx, rax; hModule
0x180002425  call    cs:__imp_GetProcAddress
0x18000242b  mov     rcx, cs:?hCabinet@@3PEAUHINSTANCE__@@EA; hModule
0x180002432  lea     rdx, aFdidestroy; "FDIDestroy"
0x180002439  mov     cs:?pFDICreate@@3P6APEAXP6APEAXK@ZP6AXPEAX@ZP6A_JPEADHH@ZP6AI_J1I@Z6P6AH5@ZP6AJ5JH@ZHPEAUERF@@@ZEA, rax; void * (*pFDICreate)(void * (*)(ulong),void (*)(void *),__int64 (*)(char *,int,int),uint (*)(__int64,void *,uint),uint (*)(__int64,void *,uint),int (*)(__int64),long (*)(__int64,long,int),int,ERF *)
0x180002440  call    cs:__imp_GetProcAddress
0x180002446  mov     rcx, cs:?hCabinet@@3PEAUHINSTANCE__@@EA; hModule
0x18000244d  lea     rdx, aFdiiscabinet; "FDIIsCabinet"
0x180002454  mov     cs:?pFDIDestroy@@3P6AHPEAX@ZEA, rax; int (*pFDIDestroy)(void *)
0x18000245b  call    cs:__imp_GetProcAddress
0x180002461  mov     rcx, cs:?hCabinet@@3PEAUHINSTANCE__@@EA; hModule
0x180002468  lea     rdx, aFdicopy; "FDICopy"
0x18000246f  mov     cs:?pFDIIsCabinet@@3P6AHPEAX_JPEAUFDICABINETINFO@@@ZEA, rax; int (*pFDIIsCabinet)(void *,__int64,FDICABINETINFO *)
0x180002476  call    cs:__imp_GetProcAddress
0x18000247c  cmp     cs:?pFDICreate@@3P6APEAXP6APEAXK@ZP6AXPEAX@ZP6A_JPEADHH@ZP6AI_J1I@Z6P6AH5@ZP6AJ5JH@ZHPEAUERF@@@ZEA, 0; void * (*pFDICreate)(void * (*)(ulong),void (*)(void *),__int64 (*)(char *,int,int),uint (*)(__int64,void *,uint),uint (*)(__int64,void *,uint),int (*)(__int64),long (*)(__int64,long,int),int,ERF *)
0x180002484  mov     cs:?pFDICopy@@3P6AHPEAXPEAD1HP6A_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@ZP6AHPEAUFDIDECRYPT@@@Z0@ZEA, rax; int (*pFDICopy)(void *,char *,char *,int,__int64 (*)(FDINOTIFICATIONTYPE,FDINOTIFICATION *),int (*)(FDIDECRYPT *),void *)
0x18000248b  jz      loc_18000257B
0x180002491  cmp     cs:?pFDIDestroy@@3P6AHPEAX@ZEA, 0; int (*pFDIDestroy)(void *)
0x180002499  jz      loc_18000257B
0x18000249f  cmp     cs:?pFDIIsCabinet@@3P6AHPEAX_JPEAUFDICABINETINFO@@@ZEA, 0; int (*pFDIIsCabinet)(void *,__int64,FDICABINETINFO *)
0x1800024a7  jz      loc_18000257B
0x1800024ad  test    rax, rax
0x1800024b0  jz      loc_18000257B
0x1800024b6  mov     eax, 1
0x1800024bb  lock xadd cs:?cCabinetLoad@@3JC, eax; long volatile cCabinetLoad
0x1800024c3  test    eax, eax
0x1800024c5  jz      short loc_1800024D4
0x1800024c7  mov     rcx, cs:?hCabinet@@3PEAUHINSTANCE__@@EA; hLibModule
0x1800024ce  call    cs:__imp_FreeLibrary
0x1800024d4  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x1800024da  mov     rbx, cs:?pFDICreate@@3P6APEAXP6APEAXK@ZP6AXPEAX@ZP6A_JPEADHH@ZP6AI_J1I@Z6P6AH5@ZP6AJ5JH@ZHPEAUERF@@@ZEA; void * (*pFDICreate)(void * (*)(ulong),void (*)(void *),__int64 (*)(char *,int,int),uint (*)(__int64,void *,uint),uint (*)(__int64,void *,uint),int (*)(__int64),long (*)(__int64,long,int),int,ERF *)
0x1800024e1  call    cs:__imp_TlsGetValue
0x1800024e7  add     rax, 10h
0x1800024eb  lea     r9, ?SpdFdiRead@@YAI_JPEAXI@Z; SpdFdiRead(__int64,void *,uint)
0x1800024f2  mov     [rsp+58h+var_18], rax
0x1800024f7  lea     r8, ?SpdFdiOpen@@YA_JPEADHH@Z; SpdFdiOpen(char *,int,int)
0x1800024fe  mov     [rsp+58h+var_20], 0FFFFFFFFh
0x180002506  lea     rax, ?SpdFdiSeek@@YAJ_JJH@Z; SpdFdiSeek(__int64,long,int)
0x18000250d  mov     [rsp+58h+var_28], rax
0x180002512  lea     rdx, ?SpdFdiFree@@YAXPEAX@Z; SpdFdiFree(void *)
0x180002519  lea     rax, ?SpdFdiClose@@YAH_J@Z; SpdFdiClose(__int64)
0x180002520  mov     [rsp+58h+var_30], rax
0x180002525  lea     rcx, ?SpdFdiAlloc@@YAPEAXK@Z; SpdFdiAlloc(ulong)
0x18000252c  lea     rax, ?SpdFdiWrite@@YAI_JPEAXI@Z; SpdFdiWrite(__int64,void *,uint)
0x180002533  mov     [rsp+58h+var_38], rax
0x180002538  mov     rax, rbx
0x18000253b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002540  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002546  mov     rbx, rax
0x180002549  call    cs:__imp_TlsGetValue
0x18000254f  mov     [rax+8], rbx
0x180002553  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x180002559  cmp     ecx, 0FFFFFFFFh
0x18000255c  jz      short loc_18000258D
0x18000255e  call    cs:__imp_TlsGetValue
0x180002564  test    rax, rax
0x180002567  jz      short loc_18000258D
0x180002569  mov     ecx, cs:?itlsDiamondContext@@3KA; dwTlsIndex
0x18000256f  call    cs:__imp_TlsGetValue
0x180002575  mov     rcx, [rax+8]
0x180002579  jmp     short loc_18000258F
0x18000257b  mov     rcx, cs:?hCabinet@@3PEAUHINSTANCE__@@EA; hLibModule
0x180002582  call    cs:__imp_FreeLibrary
0x180002588  jmp     loc_180002411
0x18000258d  xor     ecx, ecx
0x18000258f  neg     rcx
0x180002592  sbb     eax, eax
0x180002594  not     eax
0x180002596  and     eax, 100000h
0x18000259b  jmp     short loc_1800025AB
0x18000259d  mov     rcx, rbx; hMem
0x1800025a0  call    cs:__imp_LocalFree
0x1800025a6  mov     eax, 8000h
0x1800025ab  add     rsp, 50h
0x1800025af  pop     rbx
0x1800025b0  retn
```
