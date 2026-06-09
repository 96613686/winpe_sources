# WldpSmartAppControlTelemetryAndToast(CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *,SAC_REPUTATION_EXTRA_INFO_ *,ushort const *,ulong,void * const)

- ea: `0x1800175fc`
- end: `0x1800177db`
- name: `?WldpSmartAppControlTelemetryAndToast@@YAXPEAUCONFIG_CI_PROV_INFO_RESULT2_PRIVATE_@@PEAUSAC_REPUTATION_EXTRA_INFO_@@PEBGKQEAX@Z`
- size: `479`
- prototype: `void __fastcall(struct CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *, struct SAC_REPUTATION_EXTRA_INFO_ *, const unsigned __int16 *, int, void *const)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180015118`
- `0x18001e1d4`

## callees

- `0x1800175fc`
- `0x1800177e4`
- `0x180018260`
- `0x18002b4e8`
- `0x18003104c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017728`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017736`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017728`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017736`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001774d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001774d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800177d0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800177d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017774`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017774`
- `WINTRUST!WintrustGetHash` at `0x1800176c9`
- `WINTRUST!WintrustGetHash` at `0x1800176c9`

## string_xrefs

- `0x180017746`: `Shlwapi.dll`
- `0x18001776a`: `PathFindFileNameW`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall WldpSmartAppControlTelemetryAndToast(
        struct CONFIG_CI_PROV_INFO_RESULT2_PRIVATE_ *a1,
        struct SAC_REPUTATION_EXTRA_INFO_ *a2,
        const unsigned __int16 *a3,
        int a4,
        void *const a5)
{
  HMODULE v7; // rbx
  __int64 v8; // rax
  bool v9; // bp
  __int64 v10; // rax
  bool v11; // al
  void *v12; // rdi
  void **unique_hlocal; // rax
  HLOCAL v14; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // rcx
  HLOCAL hMem; // [rsp+28h] [rbp-50h] BYREF
  HMODULE hModule[9]; // [rsp+30h] [rbp-48h] BYREF

  v7 = 0;
  hModule[0] = 0;
  v8 = *(_QWORD *)((char *)a1 + 36) - 0x49AEFFF10283AC0FLL;
  if ( *(_QWORD *)((char *)a1 + 36) == 0x49AEFFF10283AC0FLL )
    v8 = *(_QWORD *)((char *)a1 + 44) + 0x2935CFCE6C755E53LL;
  v9 = v8 == 0;
  v10 = *(_QWORD *)((char *)a1 + 36) - 0x49AEFFF11283AC0FLL;
  if ( *(_QWORD *)((char *)a1 + 36) == 0x49AEFFF11283AC0FLL )
    v10 = *(_QWORD *)((char *)a1 + 44) + 0x2935CFCE6C755E53LL;
  v11 = v10 == 0;
  if ( v9 || (v12 = 0, v11) )
  {
    v12 = 0;
    if ( a4 == 6 )
    {
      if ( !*((_QWORD *)a1 + 20) )
      {
        unique_hlocal = (void **)wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, 32);
        v12 = *unique_hlocal;
        *unique_hlocal = 0;
        v14 = hMem;
        hMem = 0;
        if ( v14 )
          LocalFree(v14);
        if ( v12 )
        {
          if ( (int)WintrustGetHash(a5, L"SHA256", 32, v12) < 0 )
            goto LABEL_12;
          *((_DWORD *)a1 + 38) = 32;
          *((_QWORD *)a1 + 20) = v12;
        }
        v12 = 0;
      }
LABEL_12:
      WldpTraceLoggingSACDecision(a3);
      if ( v9 && *((int *)a1 + 15) < 0 )
      {
        Library = LoadLibraryExW(L"Shlwapi.dll", 0, 0x800u);
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
          hModule,
          Library);
        v7 = hModule[0];
        if ( hModule[0] )
        {
          ProcAddress = GetProcAddress(hModule[0], "PathFindFileNameW");
          if ( ProcAddress )
          {
            v17 = (const unsigned __int16 *)((__int64 (__fastcall *)(const unsigned __int16 *))ProcAddress)(a3);
            WldpSendSmartAppControlBlockToastWldp(v18, v17, *((_DWORD *)a1 + 15));
          }
        }
      }
    }
  }
  if ( v12 )
    LocalFree(v12);
  if ( v7 )
    FreeLibrary(v7);
}

```

## disassembly

```asm
0x1800175fc  mov     rax, rsp
0x1800175ff  push    rbx
0x180017600  push    rbp
0x180017601  push    rsi
0x180017602  push    rdi
0x180017603  push    r14
0x180017605  push    r15
0x180017607  sub     rsp, 48h
0x18001760b  mov     r14, r8
0x18001760e  mov     r15, rdx
0x180017611  mov     rsi, rcx
0x180017614  xor     ebx, ebx
0x180017616  mov     [rax-48h], rbx
0x18001761a  mov     [rax+8], rbx
0x18001761e  mov     rax, [rcx+24h]
0x180017622  sub     rax, cs:qword_180047BB0
0x180017629  jnz     short loc_180017636
0x18001762b  mov     rax, [rcx+2Ch]
0x18001762f  sub     rax, cs:qword_180047BB8
0x180017636  test    rax, rax
0x180017639  setz    bpl
0x18001763d  mov     rax, [rcx+24h]
0x180017641  sub     rax, cs:qword_180047BA0
0x180017648  jnz     short loc_180017655
0x18001764a  mov     rax, [rcx+2Ch]
0x18001764e  sub     rax, cs:qword_180047BA8
0x180017655  test    rax, rax
0x180017658  setz    al
0x18001765b  test    bpl, bpl
0x18001765e  jz      loc_18001771C
0x180017664  xor     edi, edi
0x180017666  cmp     r9d, 6
0x18001766a  jnz     loc_1800176F1
0x180017670  cmp     [rcx+0A0h], rdi
0x180017677  jnz     short loc_1800176D7
0x180017679  lea     edx, [rdi+20h]
0x18001767c  lea     rcx, [rsp+78h+hMem]
0x180017681  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z
0x180017686  nop
0x180017687  mov     rdi, [rax]
0x18001768a  mov     qword ptr [rax], 0
0x180017691  mov     [rsp+78h+arg_0], rdi
0x180017699  mov     rcx, [rsp+78h+hMem]; hMem
0x18001769e  mov     [rsp+78h+hMem], 0
0x1800176a7  test    rcx, rcx
0x1800176aa  jnz     short loc_180017728
0x1800176ac  test    rdi, rdi
0x1800176af  jz      short loc_180017718
0x1800176b1  mov     r9, rdi
0x1800176b4  mov     r8d, 20h ; ' '
0x1800176ba  lea     rdx, pwszCNGHashAlgid
0x1800176c1  mov     rcx, [rsp+78h+arg_20]
0x1800176c9  call    cs:__imp_WintrustGetHash
0x1800176cf  test    eax, eax
0x1800176d1  jns     loc_18001779C
0x1800176d7  mov     r9, rsi
0x1800176da  mov     r8, r15
0x1800176dd  mov     dl, bpl
0x1800176e0  mov     rcx, r14; SourceString
0x1800176e3  call    WldpTraceLoggingSACDecision
0x1800176e8  test    bpl, bpl
0x1800176eb  jnz     loc_1800177BE
0x1800176f1  mov     [rsp+78h+arg_0], 0
0x1800176fd  test    rdi, rdi
0x180017700  jnz     short loc_180017733
0x180017702  test    rbx, rbx
0x180017705  jnz     loc_1800177CD
0x18001770b  add     rsp, 48h
0x18001770f  pop     r15
0x180017711  pop     r14
0x180017713  pop     rdi
0x180017714  pop     rsi
0x180017715  pop     rbp
0x180017716  pop     rbx
0x180017717  retn
0x180017718  xor     edi, edi
0x18001771a  jmp     short loc_1800176D7
0x18001771c  xor     edi, edi
0x18001771e  test    al, al
0x180017720  jnz     loc_180017664
0x180017726  jmp     short loc_1800176F1
0x180017728  call    cs:__imp_LocalFree
0x18001772e  jmp     loc_1800176AC
0x180017733  mov     rcx, rdi; hMem
0x180017736  call    cs:__imp_LocalFree
0x18001773c  jmp     short loc_180017702
0x18001773e  xor     edx, edx; hFile
0x180017740  mov     r8d, 800h; dwFlags
0x180017746  lea     rcx, LibFileName
0x18001774d  call    cs:__imp_LoadLibraryExW
0x180017753  mov     rdx, rax
0x180017756  lea     rcx, [rsp+78h+hModule]
0x18001775b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z
0x180017760  mov     rbx, [rsp+78h+hModule]
0x180017765  test    rbx, rbx
0x180017768  jz      short loc_1800176F1
0x18001776a  lea     rdx, aPathfindfilena
0x180017771  mov     rcx, rbx; hModule
0x180017774  call    cs:__imp_GetProcAddress
0x18001777a  test    rax, rax
0x18001777d  jz      loc_1800176F1
0x180017783  mov     rcx, r14
0x180017786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001778b  mov     r8d, [rsi+3Ch]; int
0x18001778f  mov     rdx, rax; unsigned __int16 *
0x180017792  call    ?WldpSendSmartAppControlBlockToastWldp@@YAJPEBG0J@Z
0x180017797  jmp     loc_1800176F1
0x18001779c  mov     dword ptr [rsi+98h], 20h ; ' '
0x1800177a6  mov     [rsp+78h+arg_0], 0
0x1800177b2  mov     [rsi+0A0h], rdi
0x1800177b9  jmp     loc_180017718
0x1800177be  cmp     dword ptr [rsi+3Ch], 0
0x1800177c2  jge     loc_1800176F1
0x1800177c8  jmp     loc_18001773E
0x1800177cd  mov     rcx, rbx; hLibModule
0x1800177d0  call    cs:__imp_FreeLibrary
0x1800177d6  jmp     loc_18001770B
```
