# ComputeService::Management::Details::AddMappedDirectories(ComputeService::Management::SiloContainerConfiguration const *,ComputeService::Management::SiloContainerState *,Schema::Containers::Definition::Container const &)

- ea: `0x140085ee4`
- end: `0x1400863ed`
- name: `?AddMappedDirectories@Details@Management@ComputeService@@YAXPEBUSiloContainerConfiguration@23@PEAUSiloContainerState@23@AEBUContainer@Definition@Containers@Schema@@@Z`
- size: `1289`
- prototype: `void __fastcall(ComputeService::Management::Details *__hidden this, const struct ComputeService::Management::SiloContainerConfiguration *, struct ComputeService::Management::SiloContainerState *, const struct Schema::Containers::Definition::Container *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x140087d00`

## callees

- `0x140005360`
- `0x140008760`
- `0x140009f8c`
- `0x14001bfa4`
- `0x14002dd18`
- `0x1400341ac`
- `0x14003a048`
- `0x140041ff0`
- `0x140081630`
- `0x140085ee4`
- `0x1400863f4`
- `0x14008a888`
- `0x14008c2c8`
- `0x14008fe5c`
- `0x1400d90a0`
- `0x1400f1864`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140086237`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140086237`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086382`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140086382`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140086020`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140086020`

## string_xrefs

- `0x1400863bf`: `onecore\vm\common\vml\VmFiles.h`
- `0x1400863db`: `onecore\vm\common\vml\VmFiles.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ComputeService::Management::Details::AddMappedDirectories(
        ComputeService::Management::Details *this,
        const struct ComputeService::Management::SiloContainerConfiguration *a2,
        struct ComputeService::Management::SiloContainerState *a3,
        const struct Schema::Containers::Definition::Container *a4)
{
  __int64 v6; // rbx
  __int64 v7; // r14
  const struct Schema::Containers::Resources::MappedDirectory *v8; // r8
  __int64 v9; // rax
  HANDLE FileW; // rbx
  int v11; // esi
  __m128i si128; // xmm6
  __int64 v13; // rax
  __int64 v14; // rax
  const struct Schema::Containers::Resources::MappedDirectory *v15; // r8
  __int64 v16; // rax
  __int64 v17; // rax
  _WORD **i; // rsi
  _WORD **v19; // r14
  DWORD LastError; // eax
  _WORD *v21; // rdx
  unsigned __int64 v22; // r8
  const WCHAR *v23; // r8
  const WCHAR *v24; // rdx
  const char *v25; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  DWORD dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  _BYTE Src[32]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h]
  __int128 v32; // [rsp+70h] [rbp-90h] BYREF
  __m128i v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int128 v35; // [rsp+98h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int16 v38; // [rsp+B8h] [rbp-48h]
  int v39; // [rsp+BAh] [rbp-46h]
  __int16 v40; // [rsp+BEh] [rbp-42h]
  _OWORD v41[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-20h]
  __int128 v43; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-8h]
  __int64 v45; // [rsp+100h] [rbp+0h]
  __int16 v46; // [rsp+108h] [rbp+8h]
  int v47; // [rsp+10Ah] [rbp+Ah]
  __int16 v48; // [rsp+10Eh] [rbp+Eh]
  __int128 v49; // [rsp+110h] [rbp+10h] BYREF
  __int64 v50; // [rsp+120h] [rbp+20h]
  PCWSTR pszPathIn[4]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v6 = *((_QWORD *)this + 25);
  v7 = *((_QWORD *)this + 26);
  while ( v6 != v7 )
  {
    ComputeService::ContainerUtilities::NormalizeMappedDirectory(&v32, v6);
    if ( ComputeService::Management::Details::ValidateNewMappedDirectory(
           a2,
           (const struct ComputeService::Management::SiloContainerState *)&v32,
           v8) )
    {
      LOBYTE(dwFlagsAndAttributes) = HIBYTE(v38);
      LOBYTE(dwCreationDisposition) = v38;
      ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(
        *((_QWORD *)a2 + 16),
        (char *)a2 + 144,
        &v32,
        &v35,
        dwCreationDisposition,
        dwFlagsAndAttributes);
    }
    std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(
      (__int64)a2 + 432,
      (__int64)&v32);
    std::wstring::~wstring(&v35);
    std::wstring::~wstring(&v32);
    v6 += 80;
  }
  if ( *((_BYTE *)a3 + 496) && *((_BYTE *)a3 + 440) )
  {
    v31 = -1;
    v9 = Vml::AppendToSystemPath(Src, L"HostDriverStore");
    if ( *(_QWORD *)(v9 + 24) > 7u )
      v9 = *(_QWORD *)v9;
    FileW = CreateFileW((LPCWSTR)v9, 0x80000000, 1u, 0, 3u, 0x2100000u, 0);
    v31 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v11 = 0;
      LastError = GetLastError();
      if ( LastError != 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x35A,
          (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
          (const char *)LastError,
          dwCreationDispositiona);
    }
    else
    {
      v11 = 1;
    }
    std::wstring::~wstring(Src);
    v41[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v41[1] = si128;
    LOWORD(v41[0]) = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 7;
    LOWORD(v43) = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v13 = Vml::AppendToSystemPath(Src, L"DriverStore");
    std::wstring::operator=(v41, v13);
    std::wstring::~wstring(Src);
    v14 = Vml::AppendToSystemPath(Src, L"HostDriverStore");
    std::wstring::operator=(&v43, v14);
    std::wstring::~wstring(Src);
    LOBYTE(v46) = 1;
    if ( ComputeService::Management::Details::ValidateNewMappedDirectory(
           a2,
           (const struct ComputeService::Management::SiloContainerState *)v41,
           v15) )
    {
      if ( v11 )
      {
        v32 = 0;
        v33 = si128;
        LOWORD(v32) = 0;
        v34 = 0;
        v35 = 0;
        v36 = 0;
        v37 = 7;
        LOWORD(v35) = 0;
        v38 = 0;
        v39 = 0;
        v40 = 0;
        v16 = Vml::AppendToSystemPath(Src, L"HostDriverStore");
        std::wstring::operator=(&v32, v16);
        std::wstring::~wstring(Src);
        v17 = Vml::AppendToSystemPath(Src, L"HostDriverStore");
        std::wstring::operator=(&v35, v17);
        std::wstring::~wstring(Src);
        LOBYTE(v38) = 1;
        LOBYTE(dwFlagsAndAttributesa) = HIBYTE(v38);
        LOBYTE(dwCreationDispositiona) = 1;
        ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(
          *((_QWORD *)a2 + 16),
          (char *)a2 + 144,
          &v32,
          &v35,
          dwCreationDispositiona,
          dwFlagsAndAttributesa);
        std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(
          (__int64)a2 + 432,
          (__int64)&v32);
        std::wstring::~wstring(&v35);
        std::wstring::~wstring(&v32);
      }
      LOBYTE(dwFlagsAndAttributesa) = HIBYTE(v46);
      LOBYTE(dwCreationDispositiona) = v46;
      ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(
        *((_QWORD *)a2 + 16),
        (char *)a2 + 144,
        v41,
        &v43,
        dwCreationDispositiona,
        dwFlagsAndAttributesa);
      std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(
        (__int64)a2 + 432,
        (__int64)v41);
    }
    CommonUtilities::GetWindowsFolderPath(pszPathIn);
    v49 = 0;
    v50 = 0;
    ComputeService::GetAcceleratorFileMappings((__int64 *)&v49);
    v19 = (_WORD **)*((_QWORD *)&v49 + 1);
    for ( i = (_WORD **)v49; i != v19; i += 8 )
    {
      v32 = 0;
      v33 = si128;
      LOWORD(v32) = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v37 = 7;
      LOWORD(v35) = 0;
      v38 = 0;
      v39 = 0;
      v40 = 0;
      if ( (unsigned __int64)i[3] <= 7 )
        v21 = i;
      else
        v21 = *i;
      v22 = -1;
      do
        ++v22;
      while ( v21[v22] );
      std::wstring::_Assign<unsigned short>((void **)&v32, v21, v22);
      v23 = (const WCHAR *)(i + 4);
      if ( (unsigned __int64)i[7] > 7 )
        v23 = *(const WCHAR **)v23;
      v24 = (const WCHAR *)pszPathIn;
      if ( pszPathIn[3] > (PCWSTR)7 )
        v24 = pszPathIn[0];
      CommonUtilities::CombineFilePath(Src, v24, v23);
      std::wstring::operator=(&v35, Src);
      std::wstring::~wstring(Src);
      LOBYTE(v38) = 1;
      LOBYTE(dwFlagsAndAttributesa) = HIBYTE(v38);
      LOBYTE(dwCreationDispositiona) = 1;
      ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(
        *((_QWORD *)a2 + 16),
        (char *)a2 + 144,
        &v32,
        &v35,
        dwCreationDispositiona,
        dwFlagsAndAttributesa);
      std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(
        (__int64)a2 + 432,
        (__int64)&v32);
      std::wstring::~wstring(&v35);
      std::wstring::~wstring(&v32);
    }
    std::vector<Schema::Containers::Definition::NamedPipeSymlink>::_Tidy(&v49);
    std::wstring::~wstring(pszPathIn);
    std::wstring::~wstring(&v43);
    std::wstring::~wstring(v41);
    if ( FileW != (HANDLE)-1LL && !CloseHandle(FileW) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x308,
        (unsigned int)"onecore\\vm\\common\\vml\\VmFiles.h",
        v25);
  }
}

```

## disassembly

```asm
0x140085ee4  mov     rax, rsp
0x140085ee7  mov     [rax+18h], rbx
0x140085eeb  push    rbp
0x140085eec  push    rsi
0x140085eed  push    rdi
0x140085eee  push    r12
0x140085ef0  push    r13
0x140085ef2  push    r14
0x140085ef4  push    r15
0x140085ef6  lea     rbp, [rsp-60h]
0x140085efb  sub     rsp, 160h
0x140085f02  movaps  xmmword ptr [rax-48h], xmm6
0x140085f06  mov     rax, cs:__security_cookie
0x140085f0d  xor     rax, rsp
0x140085f10  mov     [rbp+90h+var_48], rax
0x140085f14  mov     rsi, r8
0x140085f17  mov     rdi, rdx
0x140085f1a  xor     r13d, r13d
0x140085f1d  mov     rbx, [rcx+0C8h]
0x140085f24  mov     r14, [rcx+0D0h]
0x140085f2b  jmp     short loc_140085FA9
0x140085f2d  mov     rdx, rbx
0x140085f30  lea     rcx, [rsp+190h+var_120]
0x140085f35  call    ?NormalizeMappedDirectory@ContainerUtilities@ComputeService@@YA?AUMappedDirectory@Resources@Containers@Schema@@AEBU3456@@Z; ComputeService::ContainerUtilities::NormalizeMappedDirectory(Schema::Containers::Resources::MappedDirectory const &)
0x140085f3a  nop
0x140085f3b  lea     rdx, [rsp+190h+var_120]; struct ComputeService::Management::SiloContainerState *
0x140085f40  mov     rcx, rdi; this
0x140085f43  call    ?ValidateNewMappedDirectory@Details@Management@ComputeService@@YA_NPEBUSiloContainerState@23@AEBUMappedDirectory@Resources@Containers@Schema@@@Z; ComputeService::Management::Details::ValidateNewMappedDirectory(ComputeService::Management::SiloContainerState const *,Schema::Containers::Resources::MappedDirectory const &)
0x140085f48  test    al, al
0x140085f4a  jz      short loc_140085F80
0x140085f4c  lea     rdx, [rdi+90h]
0x140085f53  mov     al, [rdi+0B1h]
0x140085f59  mov     [rsp+190h+var_158], al
0x140085f5d  mov     al, byte ptr [rbp+90h+var_D8+1]
0x140085f60  mov     byte ptr [rsp+190h+dwFlagsAndAttributes], al
0x140085f64  mov     al, byte ptr [rbp+90h+var_D8]
0x140085f67  mov     byte ptr [rsp+190h+dwCreationDisposition], al
0x140085f6b  lea     r9, [rbp+90h+var_F8]
0x140085f6f  lea     r8, [rsp+190h+var_120]
0x140085f74  mov     rcx, [rdi+80h]
0x140085f7b  call    ?AddMappedDirectoryFromPaths@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11_N222@Z; ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(void *,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool)
0x140085f80  lea     rdx, [rsp+190h+var_120]
0x140085f85  lea     rcx, [rdi+1B0h]
0x140085f8c  call    ??$_Emplace_one_at_back@UMappedDirectory@Resources@Containers@Schema@@@?$vector@UMappedDirectory@Resources@Containers@Schema@@V?$allocator@UMappedDirectory@Resources@Containers@Schema@@@std@@@std@@AEAAAEAUMappedDirectory@Resources@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(Schema::Containers::Resources::MappedDirectory &&)
0x140085f91  nop
0x140085f92  lea     rcx, [rbp+90h+var_F8]; void *
0x140085f96  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140085f9b  lea     rcx, [rsp+190h+var_120]; void *
0x140085fa0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140085fa5  add     rbx, 50h ; 'P'
0x140085fa9  cmp     rbx, r14
0x140085fac  jnz     loc_140085F2D
0x140085fb2  cmp     [rsi+1F0h], r13b
0x140085fb9  jz      loc_14008638C
0x140085fbf  cmp     [rsi+1B8h], r13b
0x140085fc6  jz      loc_14008638C
0x140085fcc  mov     [rsp+190h+var_130], 0FFFFFFFFFFFFFFFFh
0x140085fd5  lea     r12, aHostdriverstor; "HostDriverStore"
0x140085fdc  mov     rdx, r12; pszMore
0x140085fdf  lea     rcx, [rsp+190h+Src]; Src
0x140085fe4  call    ?AppendToSystemPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::AppendToSystemPath(ushort const *)
0x140085fe9  nop
0x140085fea  mov     r14d, 7
0x140085ff0  cmp     [rax+18h], r14
0x140085ff4  jbe     short loc_140085FF9
0x140085ff6  mov     rax, [rax]
0x140085ff9  mov     [rsp+190h+hTemplateFile], r13; hTemplateFile
0x140085ffe  mov     [rsp+190h+dwFlagsAndAttributes], 2100000h; dwFlagsAndAttributes
0x140086006  mov     [rsp+190h+dwCreationDisposition], 3; unsigned int
0x14008600e  xor     r9d, r9d; lpSecurityAttributes
0x140086011  lea     r15d, [r9+1]
0x140086015  mov     r8d, r15d; dwShareMode
0x140086018  mov     edx, 80000000h; dwDesiredAccess
0x14008601d  mov     rcx, rax; lpFileName
0x140086020  call    cs:__imp_CreateFileW
0x140086026  mov     rbx, rax
0x140086029  mov     [rsp+190h+var_130], rax
0x14008602e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140086032  jz      loc_140086234
0x140086038  mov     esi, r15d
0x14008603b  lea     rcx, [rsp+190h+Src]; void *
0x140086040  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086045  xorps   xmm0, xmm0
0x140086048  movups  [rbp+90h+var_D0], xmm0
0x14008604c  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140086054  movdqa  [rbp+90h+var_C0], xmm6
0x140086059  mov     word ptr [rbp+90h+var_D0], r13w
0x14008605e  mov     [rbp+90h+var_B0], r13
0x140086062  movups  [rbp+90h+var_A8], xmm0
0x140086066  mov     [rbp+90h+var_98], r13
0x14008606a  mov     [rbp+90h+var_90], r14
0x14008606e  mov     word ptr [rbp+90h+var_A8], r13w
0x140086073  mov     [rbp+90h+var_88], r13w
0x140086078  xor     eax, eax
0x14008607a  mov     [rbp+90h+var_86], eax
0x14008607d  mov     [rbp+90h+var_82], ax
0x140086081  lea     rdx, aDriverstore; "DriverStore"
0x140086088  lea     rcx, [rsp+190h+Src]; Src
0x14008608d  call    ?AppendToSystemPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::AppendToSystemPath(ushort const *)
0x140086092  mov     rdx, rax
0x140086095  lea     rcx, [rbp+90h+var_D0]
0x140086099  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14008609e  lea     rcx, [rsp+190h+Src]; void *
0x1400860a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400860a8  mov     rdx, r12; pszMore
0x1400860ab  lea     rcx, [rsp+190h+Src]; Src
0x1400860b0  call    ?AppendToSystemPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::AppendToSystemPath(ushort const *)
0x1400860b5  mov     rdx, rax
0x1400860b8  lea     rcx, [rbp+90h+var_A8]
0x1400860bc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400860c1  lea     rcx, [rsp+190h+Src]; void *
0x1400860c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400860cb  mov     byte ptr [rbp+90h+var_88], r15b
0x1400860cf  lea     rdx, [rbp+90h+var_D0]; struct ComputeService::Management::SiloContainerState *
0x1400860d3  mov     rcx, rdi; this
0x1400860d6  call    ?ValidateNewMappedDirectory@Details@Management@ComputeService@@YA_NPEBUSiloContainerState@23@AEBUMappedDirectory@Resources@Containers@Schema@@@Z; ComputeService::Management::Details::ValidateNewMappedDirectory(ComputeService::Management::SiloContainerState const *,Schema::Containers::Resources::MappedDirectory const &)
0x1400860db  test    al, al
0x1400860dd  jz      loc_140086206
0x1400860e3  test    esi, esi
0x1400860e5  jz      loc_1400861C3
0x1400860eb  xorps   xmm0, xmm0
0x1400860ee  movups  [rsp+190h+var_120], xmm0
0x1400860f3  movdqa  [rbp+90h+var_110], xmm6
0x1400860f8  mov     word ptr [rsp+190h+var_120], r13w
0x1400860fe  mov     [rbp+90h+var_100], r13
0x140086102  movups  [rbp+90h+var_F8], xmm0
0x140086106  mov     [rbp+90h+var_E8], r13
0x14008610a  mov     [rbp+90h+var_E0], r14
0x14008610e  mov     word ptr [rbp+90h+var_F8], r13w
0x140086113  mov     [rbp+90h+var_D8], r13w
0x140086118  xor     eax, eax
0x14008611a  mov     [rbp+90h+var_D6], eax
0x14008611d  mov     [rbp+90h+var_D2], ax
0x140086121  mov     rdx, r12; pszMore
0x140086124  lea     rcx, [rsp+190h+Src]; Src
0x140086129  call    ?AppendToSystemPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::AppendToSystemPath(ushort const *)
0x14008612e  mov     rdx, rax
0x140086131  lea     rcx, [rsp+190h+var_120]
0x140086136  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14008613b  lea     rcx, [rsp+190h+Src]; void *
0x140086140  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086145  mov     rdx, r12; pszMore
0x140086148  lea     rcx, [rsp+190h+Src]; Src
0x14008614d  call    ?AppendToSystemPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::AppendToSystemPath(ushort const *)
0x140086152  mov     rdx, rax
0x140086155  lea     rcx, [rbp+90h+var_F8]
0x140086159  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14008615e  lea     rcx, [rsp+190h+Src]; void *
0x140086163  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086168  mov     byte ptr [rbp+90h+var_D8], r15b
0x14008616c  lea     rdx, [rdi+90h]
0x140086173  mov     al, [rdi+0B1h]
0x140086179  mov     [rsp+190h+var_158], al
0x14008617d  mov     al, byte ptr [rbp+90h+var_D8+1]
0x140086180  mov     byte ptr [rsp+190h+dwFlagsAndAttributes], al
0x140086184  mov     byte ptr [rsp+190h+dwCreationDisposition], r15b
0x140086189  lea     r9, [rbp+90h+var_F8]
0x14008618d  lea     r8, [rsp+190h+var_120]
0x140086192  mov     rcx, [rdi+80h]
0x140086199  call    ?AddMappedDirectoryFromPaths@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11_N222@Z; ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(void *,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool)
0x14008619e  lea     rcx, [rdi+1B0h]
0x1400861a5  lea     rdx, [rsp+190h+var_120]
0x1400861aa  call    ??$_Emplace_one_at_back@UMappedDirectory@Resources@Containers@Schema@@@?$vector@UMappedDirectory@Resources@Containers@Schema@@V?$allocator@UMappedDirectory@Resources@Containers@Schema@@@std@@@std@@AEAAAEAUMappedDirectory@Resources@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(Schema::Containers::Resources::MappedDirectory &&)
0x1400861af  nop
0x1400861b0  lea     rcx, [rbp+90h+var_F8]; void *
0x1400861b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400861b9  lea     rcx, [rsp+190h+var_120]; void *
0x1400861be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400861c3  lea     rdx, [rdi+90h]
0x1400861ca  mov     al, [rdi+0B1h]
0x1400861d0  mov     [rsp+190h+var_158], al
0x1400861d4  mov     al, byte ptr [rbp+90h+var_88+1]
0x1400861d7  mov     byte ptr [rsp+190h+dwFlagsAndAttributes], al
0x1400861db  mov     al, byte ptr [rbp+90h+var_88]
0x1400861de  mov     byte ptr [rsp+190h+dwCreationDisposition], al
0x1400861e2  lea     r9, [rbp+90h+var_A8]
0x1400861e6  lea     r8, [rbp+90h+var_D0]
0x1400861ea  mov     rcx, [rdi+80h]
0x1400861f1  call    ?AddMappedDirectoryFromPaths@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11_N222@Z; ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(void *,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool)
0x1400861f6  lea     rcx, [rdi+1B0h]
0x1400861fd  lea     rdx, [rbp+90h+var_D0]
0x140086201  call    ??$_Emplace_one_at_back@UMappedDirectory@Resources@Containers@Schema@@@?$vector@UMappedDirectory@Resources@Containers@Schema@@V?$allocator@UMappedDirectory@Resources@Containers@Schema@@@std@@@std@@AEAAAEAUMappedDirectory@Resources@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(Schema::Containers::Resources::MappedDirectory &&)
0x140086206  lea     rcx, [rbp+90h+pszPathIn]
0x14008620a  call    ?GetWindowsFolderPath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; CommonUtilities::GetWindowsFolderPath(void)
0x14008620f  nop
0x140086210  xorps   xmm0, xmm0
0x140086213  xor     eax, eax
0x140086215  movups  [rbp+90h+var_80], xmm0
0x140086219  mov     [rbp+90h+var_70], rax
0x14008621d  lea     rcx, [rbp+90h+var_80]
0x140086221  call    ?GetAcceleratorFileMappings@ComputeService@@YA?AV?$vector@UFileMapping@ComputeService@@V?$allocator@UFileMapping@ComputeService@@@std@@@std@@XZ; ComputeService::GetAcceleratorFileMappings(void)
0x140086226  nop
0x140086227  mov     rsi, qword ptr [rbp+90h+var_80]
0x14008622b  mov     r14, qword ptr [rbp+90h+var_80+8]
0x14008622f  jmp     loc_140086349
0x140086234  mov     esi, r13d
0x140086237  call    cs:__imp_GetLastError
0x14008623d  cmp     eax, 2
0x140086240  jnz     loc_1400863D1
0x140086246  jmp     loc_14008603B
0x14008624b  xorps   xmm0, xmm0
0x14008624e  movups  [rsp+190h+var_120], xmm0
0x140086253  movdqa  [rbp+90h+var_110], xmm6
0x140086258  mov     word ptr [rsp+190h+var_120], r13w
0x14008625e  mov     [rbp+90h+var_100], r13
0x140086262  movups  [rbp+90h+var_F8], xmm0
0x140086266  mov     [rbp+90h+var_E8], r13
0x14008626a  mov     [rbp+90h+var_E0], 7
0x140086272  mov     word ptr [rbp+90h+var_F8], r13w
0x140086277  mov     [rbp+90h+var_D8], r13w
0x14008627c  xor     eax, eax
0x14008627e  mov     [rbp+90h+var_D6], eax
0x140086281  mov     [rbp+90h+var_D2], ax
0x140086285  cmp     qword ptr [rsi+18h], 7
0x14008628a  jbe     short loc_140086291
0x14008628c  mov     rdx, [rsi]
0x14008628f  jmp     short loc_140086294
0x140086291  mov     rdx, rsi
0x140086294  or      r8, 0FFFFFFFFFFFFFFFFh
0x140086298  inc     r8
0x14008629b  cmp     [rdx+r8*2], r13w
0x1400862a0  jnz     short loc_140086298
0x1400862a2  lea     rcx, [rsp+190h+var_120]
0x1400862a7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400862ac  lea     r8, [rsi+20h]
0x1400862b0  cmp     qword ptr [rsi+38h], 7
0x1400862b5  jbe     short loc_1400862BA
0x1400862b7  mov     r8, [r8]; pszMore
0x1400862ba  lea     rdx, [rbp+90h+pszPathIn]
0x1400862be  cmp     [rbp+90h+var_50], 7
0x1400862c3  cmova   rdx, [rbp+90h+pszPathIn]; pszPathIn
0x1400862c8  lea     rcx, [rsp+190h+Src]; Src
0x1400862cd  call    ?CombineFilePath@CommonUtilities@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CommonUtilities::CombineFilePath(ushort const *,ushort const *)
0x1400862d2  lea     rdx, [rsp+190h+Src]
0x1400862d7  lea     rcx, [rbp+90h+var_F8]
0x1400862db  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400862e0  lea     rcx, [rsp+190h+Src]; void *
0x1400862e5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400862ea  mov     byte ptr [rbp+90h+var_D8], 1
0x1400862ee  mov     al, [rdi+0B1h]
0x1400862f4  mov     [rsp+190h+var_158], al
0x1400862f8  mov     al, byte ptr [rbp+90h+var_D8+1]
0x1400862fb  mov     byte ptr [rsp+190h+dwFlagsAndAttributes], al
0x1400862ff  mov     byte ptr [rsp+190h+dwCreationDisposition], 1
0x140086304  lea     r9, [rbp+90h+var_F8]
0x140086308  lea     r8, [rsp+190h+var_120]
0x14008630d  lea     rdx, [rdi+90h]
0x140086314  mov     rcx, [rdi+80h]
0x14008631b  call    ?AddMappedDirectoryFromPaths@ContainerUtilities@ComputeService@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11_N222@Z; ComputeService::ContainerUtilities::AddMappedDirectoryFromPaths(void *,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,bool,bool)
0x140086320  lea     rdx, [rsp+190h+var_120]
0x140086325  lea     rcx, [rdi+1B0h]
0x14008632c  call    ??$_Emplace_one_at_back@UMappedDirectory@Resources@Containers@Schema@@@?$vector@UMappedDirectory@Resources@Containers@Schema@@V?$allocator@UMappedDirectory@Resources@Containers@Schema@@@std@@@std@@AEAAAEAUMappedDirectory@Resources@Containers@Schema@@$$QEAU2345@@Z; std::vector<Schema::Containers::Resources::MappedDirectory>::_Emplace_one_at_back<Schema::Containers::Resources::MappedDirectory>(Schema::Containers::Resources::MappedDirectory &&)
0x140086331  nop
0x140086332  lea     rcx, [rbp+90h+var_F8]; void *
0x140086336  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008633b  lea     rcx, [rsp+190h+var_120]; void *
0x140086340  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086345  add     rsi, 40h ; '@'
0x140086349  cmp     rsi, r14
0x14008634c  jnz     loc_14008624B
0x140086352  lea     rcx, [rbp+90h+var_80]
0x140086356  call    ?_Tidy@?$vector@UNamedPipeSymlink@Definition@Containers@Schema@@V?$allocator@UNamedPipeSymlink@Definition@Containers@Schema@@@std@@@std@@AEAAXXZ; std::vector<Schema::Containers::Definition::NamedPipeSymlink>::_Tidy(void)
0x14008635b  nop
0x14008635c  lea     rcx, [rbp+90h+pszPathIn]; void *
0x140086360  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086365  nop
0x140086366  lea     rcx, [rbp+90h+var_A8]; void *
0x14008636a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14008636f  lea     rcx, [rbp+90h+var_D0]; void *
0x140086373  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140086378  nop
0x140086379  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14008637d  jz      short loc_14008638C
0x14008637f  mov     rcx, rbx; hObject
0x140086382  call    cs:__imp_CloseHandle
0x140086388  test    eax, eax
0x14008638a  jz      short loc_1400863B8
0x14008638c  mov     rcx, [rbp+90h+var_48]
0x140086390  xor     rcx, rsp; StackCookie
0x140086393  call    __security_check_cookie
0x140086398  lea     r11, [rsp+190h+var_30]
0x1400863a0  mov     rbx, [r11+50h]
0x1400863a4  movaps  xmm6, xmmword ptr [r11-10h]
0x1400863a9  mov     rsp, r11
0x1400863ac  pop     r15
0x1400863ae  pop     r14
0x1400863b0  pop     r13
0x1400863b2  pop     r12
0x1400863b4  pop     rdi
0x1400863b5  pop     rsi
0x1400863b6  pop     rbp
0x1400863b7  retn
0x1400863b8  mov     rcx, [rbp+98h]; this
0x1400863bf  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400863c6  mov     edx, 308h; void *
0x1400863cb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400863d1  mov     rcx, [rbp+98h]; this
0x1400863d8  mov     r9d, eax; char *
0x1400863db  lea     r8, aOnecoreVmCommo_5; "onecore\\vm\\common\\vml\\VmFiles.h"
0x1400863e2  mov     edx, 35Ah; void *
  ... truncated ...
```
