# CCloudFileSystemApplier::SetShellState(ushort const *,long,int)

- ea: `0x1800942b0`
- end: `0x1800946b5`
- name: `?SetShellState@CCloudFileSystemApplier@@UEAAJPEBGJH@Z`
- size: `1029`
- prototype: `int(CCloudFileSystemApplier *__hidden this, const unsigned __int16 *, int, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180007e10`
- `0x180009188`
- `0x180011314`
- `0x18002dad0`
- `0x180058d88`
- `0x18008c47c`
- `0x1800918b4`
- `0x1800942b0`
- `0x180098914`
- `0x180098eec`
- `0x18009ac24`
- `0x1800bb748`
- `0x18013e010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18009448c`
- `SHELL32!SHCreateItemFromParsingName` at `0x18009448c`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18009445a`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18009445a`
- `ntdll!NtClose` at `0x18009465f`
- `ntdll!NtClose` at `0x18009465f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CCloudFileSystemApplier::SetShellState(
        CCloudFileSystemApplier *this,
        const unsigned __int16 *a2,
        int a3,
        int a4)
{
  _DWORD *v7; // rax
  char v8; // cl
  HANDLE v9; // rdi
  __int16 v10; // ax
  unsigned int v11; // r8d
  __int16 v12; // ax
  HRESULT v13; // ebx
  void *v14; // rdx
  int v15; // ebx
  unsigned int v16; // ebx
  HRESULT NormalizedNtPath; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+44h] [rbp-BCh]
  char v20; // [rsp+48h] [rbp-B8h]
  const char *v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  void *ppv; // [rsp+68h] [rbp-98h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-88h] BYREF
  __int128 v27; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+90h] [rbp-70h]
  WCHAR pszPathOut[256]; // [rsp+A0h] [rbp-60h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) == 0 )
      goto LABEL_8;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 57, &WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( (v7[17] & 0x100) != 0 && *((_BYTE *)v7 + 65) >= 6u )
  {
    v8 = 1;
    goto LABEL_9;
  }
LABEL_8:
  v8 = 0;
LABEL_9:
  v19 = 2436;
  v20 = v8;
  v21 = "CCloudFileSystemApplier::SetShellState";
  v22 = 0;
  ppv = 0;
  SourceString = 0;
  v23 = 0;
  v9 = 0;
  FileHandle = 0;
  NormalizedNtPath = 0;
  v10 = 2445;
  if ( !a2 )
  {
    NormalizedNtPath = -2147024809;
LABEL_11:
    HIWORD(v19) = v10;
    goto LABEL_53;
  }
  LOWORD(v19) = 2445;
  NormalizedNtPath = CPathUtilities::GetNormalizedNtPath(a2, (unsigned __int16 **)&SourceString);
  v10 = 2448;
  if ( NormalizedNtPath < 0 )
    goto LABEL_11;
  LOWORD(v19) = 2448;
  if ( a4 )
  {
    NormalizedNtPath = CFspCloudFileSystemOperations::CreateFileW(
                         SourceString,
                         0x100180u,
                         v11,
                         7u,
                         0x22u,
                         1u,
                         8u,
                         &FileHandle);
    v9 = FileHandle;
    v12 = 2460;
    if ( NormalizedNtPath < 0 )
      goto LABEL_49;
    LOWORD(v19) = 2460;
    NormalizedNtPath = CFspCloudFileSystemOperations::ClearReadOnly(FileHandle);
    v12 = 2462;
    if ( NormalizedNtPath < 0 )
      goto LABEL_49;
    LOWORD(v19) = 2462;
  }
  NormalizedNtPath = PathCchCanonicalizeEx(pszPathOut, 0x100u, a2, 0);
  v12 = 2466;
  if ( NormalizedNtPath < 0 )
  {
LABEL_49:
    HIWORD(v19) = v12;
    goto LABEL_50;
  }
  LOWORD(v19) = 2466;
  v13 = SHCreateItemFromParsingName(pszPathOut, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
  v14 = ppv;
  if ( v13 < 0 || !ppv )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        58,
        (unsigned int)&WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
        (unsigned int)pszPathOut,
        v13);
      v14 = ppv;
    }
    NormalizedNtPath = v13;
    v12 = 2472;
    if ( v13 < 0 )
      goto LABEL_49;
    LOWORD(v19) = 2472;
  }
  v15 = CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v23, v14, 1026);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        59,
        (unsigned int)&WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
        (unsigned int)pszPathOut,
        v15);
    }
    v12 = 2479;
LABEL_48:
    NormalizedNtPath = v15;
    goto LABEL_49;
  }
  if ( a3 < 0 )
  {
    if ( a3 == -2134375651 )
      goto LABEL_42;
    LOWORD(v27) = 19;
    DWORD2(v27) = a3;
  }
  else
  {
    v27 = 0;
    v28 = 0;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, __int128 *))(*(_QWORD *)v23 + 48LL))(
          v23,
          &PKEY_LastSyncError,
          &v27);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        60,
        (unsigned int)&WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
        (unsigned int)pszPathOut,
        v15);
    }
    v12 = 2496;
    goto LABEL_48;
  }
LABEL_42:
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 56LL))(v23);
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        61,
        (unsigned int)&WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids,
        (unsigned int)pszPathOut,
        v15);
    }
    v12 = 2503;
    goto LABEL_48;
  }
LABEL_50:
  if ( v9 && a4 )
  {
    CFspCloudFileSystemOperations::SetReadOnly(v9);
    NtClose(v9);
  }
LABEL_53:
  v16 = NormalizedNtPath;
  CPropertyStoreHelper::~CPropertyStoreHelper((CPropertyStoreHelper *)&v23);
  CEcsMemPtr<unsigned short,0>::~CEcsMemPtr<unsigned short,0>(&SourceString);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&NormalizedNtPath);
  return v16;
}

```

## disassembly

```asm
0x1800942b0  push    rbp
0x1800942b2  push    rbx
0x1800942b3  push    rsi
0x1800942b4  push    rdi
0x1800942b5  push    r12
0x1800942b7  push    r14
0x1800942b9  lea     rbp, [rsp-1B8h]
0x1800942c1  sub     rsp, 2B8h
0x1800942c8  mov     rax, cs:__security_cookie
0x1800942cf  xor     rax, rsp
0x1800942d2  mov     [rbp+1E0h+var_40], rax
0x1800942d9  mov     r14d, r9d
0x1800942dc  mov     esi, r8d
0x1800942df  mov     rbx, rdx
0x1800942e2  lea     rcx, WPP_GLOBAL_Control
0x1800942e9  mov     r12d, 100h
0x1800942ef  mov     rax, cs:WPP_GLOBAL_Control
0x1800942f6  cmp     rax, rcx
0x1800942f9  jz      short loc_180094323
0x1800942fb  test    [rax+44h], r12d
0x1800942ff  jz      short loc_180094333
0x180094301  cmp     byte ptr [rax+41h], 6
0x180094305  jb      short loc_180094323
0x180094307  mov     edx, 39h ; '9'
0x18009430c  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x180094313  mov     rcx, [rax+38h]
0x180094317  call    WPP_SF_
0x18009431c  mov     rax, cs:WPP_GLOBAL_Control
0x180094323  test    [rax+44h], r12d
0x180094327  jz      short loc_180094333
0x180094329  cmp     byte ptr [rax+41h], 6
0x18009432d  jb      short loc_180094333
0x18009432f  mov     cl, 1
0x180094331  jmp     short loc_180094335
0x180094333  xor     cl, cl
0x180094335  mov     [rsp+2E0h+var_2A0], 0
0x18009433d  mov     [rsp+2E0h+var_29C], 984h
0x180094345  mov     [rsp+2E0h+var_298], cl
0x180094349  lea     rax, aCcloudfilesyst_33; "CCloudFileSystemApplier::SetShellState"
0x180094350  mov     [rsp+2E0h+var_290], rax
0x180094355  mov     [rsp+2E0h+var_288], 0
0x18009435e  mov     [rsp+2E0h+ppv], 0
0x180094367  mov     [rsp+2E0h+SourceString], 0
0x180094370  mov     [rsp+2E0h+var_280], 0
0x180094379  xor     edi, edi
0x18009437b  mov     [rsp+2E0h+FileHandle], rdi
0x180094380  mov     eax, [rsp+2E0h+var_2A0]
0x180094384  mov     [rsp+2E0h+var_2A0], eax
0x180094388  mov     eax, 98Dh
0x18009438d  test    rbx, rbx
0x180094390  jnz     short loc_1800943A4
0x180094392  mov     [rsp+2E0h+var_2A0], 80070057h
0x18009439a  mov     word ptr [rsp+2E0h+var_29C+2], ax
0x18009439f  jmp     loc_180094665
0x1800943a4  mov     [rsp+2E0h+var_2A0], edi
0x1800943a8  mov     word ptr [rsp+2E0h+var_29C], ax
0x1800943ad  lea     rdx, [rsp+2E0h+SourceString]; unsigned __int16 **
0x1800943b2  mov     rcx, rbx; unsigned __int16 *
0x1800943b5  call    ?GetNormalizedNtPath@CPathUtilities@@SAJPEBGPEAPEAG@Z; CPathUtilities::GetNormalizedNtPath(ushort const *,ushort * *)
0x1800943ba  mov     [rsp+2E0h+var_2A0], eax
0x1800943be  mov     [rsp+2E0h+var_2A0], eax
0x1800943c2  test    eax, eax
0x1800943c4  mov     eax, 990h
0x1800943c9  js      short loc_18009439A
0x1800943cb  mov     word ptr [rsp+2E0h+var_29C], ax
0x1800943d0  test    r14d, r14d
0x1800943d3  jz      short loc_18009444D
0x1800943d5  lea     rax, [rsp+2E0h+FileHandle]
0x1800943da  mov     [rsp+2E0h+var_2A8], rax; void **
0x1800943df  mov     [rsp+2E0h+var_2B0], 8; unsigned int
0x1800943e7  mov     [rsp+2E0h+var_2B8], 1; ULONG
0x1800943ef  mov     [rsp+2E0h+var_2C0], 22h ; '"'; ULONG
0x1800943f7  mov     edx, 100180h; DesiredAccess
0x1800943fc  mov     r9d, 7; unsigned int
0x180094402  mov     rcx, [rsp+2E0h+SourceString]; SourceString
0x180094407  call    ?CreateFileW@CFspCloudFileSystemOperations@@SAJPEBGKKKKKKPEAPEAX@Z; CFspCloudFileSystemOperations::CreateFileW(ushort const *,ulong,ulong,ulong,ulong,ulong,ulong,void * *)
0x18009440c  mov     [rsp+2E0h+var_2A0], eax
0x180094410  mov     [rsp+2E0h+var_2A0], eax
0x180094414  mov     rdi, [rsp+2E0h+FileHandle]
0x180094419  test    eax, eax
0x18009441b  mov     eax, 99Ch
0x180094420  js      loc_180094645
0x180094426  mov     word ptr [rsp+2E0h+var_29C], ax
0x18009442b  mov     rcx, rdi; FileHandle
0x18009442e  call    ?ClearReadOnly@CFspCloudFileSystemOperations@@SAJPEAX@Z; CFspCloudFileSystemOperations::ClearReadOnly(void *)
0x180094433  mov     [rsp+2E0h+var_2A0], eax
0x180094437  mov     [rsp+2E0h+var_2A0], eax
0x18009443b  test    eax, eax
0x18009443d  mov     eax, 99Eh
0x180094442  js      loc_180094645
0x180094448  mov     word ptr [rsp+2E0h+var_29C], ax
0x18009444d  xor     r9d, r9d; dwFlags
0x180094450  mov     r8, rbx; pszPathIn
0x180094453  mov     rdx, r12; cchPathOut
0x180094456  lea     rcx, [rbp+1E0h+pszPathOut]; pszPathOut
0x18009445a  call    cs:__imp_PathCchCanonicalizeEx
0x180094460  mov     [rsp+2E0h+var_2A0], eax
0x180094464  mov     [rsp+2E0h+var_2A0], eax
0x180094468  test    eax, eax
0x18009446a  mov     eax, 9A2h
0x18009446f  js      loc_180094645
0x180094475  mov     word ptr [rsp+2E0h+var_29C], ax
0x18009447a  lea     r9, [rsp+2E0h+ppv]; ppv
0x18009447f  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180094486  xor     edx, edx; pbc
0x180094488  lea     rcx, [rbp+1E0h+pszPathOut]; pszPath
0x18009448c  call    cs:__imp_SHCreateItemFromParsingName
0x180094492  mov     ebx, eax
0x180094494  mov     rdx, [rsp+2E0h+ppv]
0x180094499  test    eax, eax
0x18009449b  js      short loc_1800944A2
0x18009449d  test    rdx, rdx
0x1800944a0  jnz     short loc_1800944FD
0x1800944a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800944a9  lea     rax, WPP_GLOBAL_Control
0x1800944b0  cmp     rcx, rax
0x1800944b3  jz      short loc_1800944E3
0x1800944b5  test    [rcx+44h], r12d
0x1800944b9  jz      short loc_1800944E3
0x1800944bb  cmp     byte ptr [rcx+41h], 2
0x1800944bf  jb      short loc_1800944E3
0x1800944c1  mov     edx, 3Ah ; ':'
0x1800944c6  mov     [rsp+2E0h+var_2C0], ebx
0x1800944ca  lea     r9, [rbp+1E0h+pszPathOut]
0x1800944ce  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x1800944d5  mov     rcx, [rcx+38h]
0x1800944d9  call    WPP_SF_Sd
0x1800944de  mov     rdx, [rsp+2E0h+ppv]
0x1800944e3  mov     [rsp+2E0h+var_2A0], ebx
0x1800944e7  mov     [rsp+2E0h+var_2A0], ebx
0x1800944eb  mov     eax, 9A8h
0x1800944f0  test    ebx, ebx
0x1800944f2  js      loc_180094645
0x1800944f8  mov     word ptr [rsp+2E0h+var_29C], ax
0x1800944fd  mov     r8d, 402h
0x180094503  lea     rcx, [rsp+2E0h+var_280]
0x180094508  call    ?InitFromItem@?$CPropertyStoreHelperBase@UIPropertyStore@@@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; CPropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x18009450d  mov     ebx, eax
0x18009450f  test    eax, eax
0x180094511  jns     short loc_180094559
0x180094513  mov     rcx, cs:WPP_GLOBAL_Control
0x18009451a  lea     rax, WPP_GLOBAL_Control
0x180094521  cmp     rcx, rax
0x180094524  jz      short loc_18009454F
0x180094526  test    [rcx+44h], r12d
0x18009452a  jz      short loc_18009454F
0x18009452c  cmp     byte ptr [rcx+41h], 2
0x180094530  jb      short loc_18009454F
0x180094532  mov     edx, 3Bh ; ';'
0x180094537  mov     [rsp+2E0h+var_2C0], ebx
0x18009453b  lea     r9, [rbp+1E0h+pszPathOut]
0x18009453f  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x180094546  mov     rcx, [rcx+38h]
0x18009454a  call    WPP_SF_Sd
0x18009454f  mov     eax, 9AFh
0x180094554  jmp     loc_18009463D
0x180094559  test    esi, esi
0x18009455b  js      short loc_18009456C
0x18009455d  xorps   xmm0, xmm0
0x180094560  xor     eax, eax
0x180094562  movups  [rbp+1E0h+var_260], xmm0
0x180094566  mov     [rbp+1E0h+var_250], rax
0x18009456a  jmp     short loc_180094580
0x18009456c  cmp     esi, 80C8031Dh
0x180094572  jz      short loc_1800945E5
0x180094574  mov     eax, 13h
0x180094579  mov     word ptr [rbp+1E0h+var_260], ax
0x18009457d  mov     dword ptr [rbp+1E0h+var_260+8], esi
0x180094580  mov     rcx, [rsp+2E0h+var_280]
0x180094585  mov     rax, [rcx]
0x180094588  lea     r8, [rbp+1E0h+var_260]
0x18009458c  lea     rdx, PKEY_LastSyncError
0x180094593  mov     rax, [rax+30h]
0x180094597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009459c  mov     ebx, eax
0x18009459e  test    eax, eax
0x1800945a0  jns     short loc_1800945E5
0x1800945a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800945a9  lea     rax, WPP_GLOBAL_Control
0x1800945b0  cmp     rcx, rax
0x1800945b3  jz      short loc_1800945DE
0x1800945b5  test    [rcx+44h], r12d
0x1800945b9  jz      short loc_1800945DE
0x1800945bb  cmp     byte ptr [rcx+41h], 2
0x1800945bf  jb      short loc_1800945DE
0x1800945c1  mov     edx, 3Ch ; '<'
0x1800945c6  mov     [rsp+2E0h+var_2C0], ebx
0x1800945ca  lea     r9, [rbp+1E0h+pszPathOut]
0x1800945ce  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x1800945d5  mov     rcx, [rcx+38h]
0x1800945d9  call    WPP_SF_Sd
0x1800945de  mov     eax, 9C0h
0x1800945e3  jmp     short loc_18009463D
0x1800945e5  mov     rcx, [rsp+2E0h+var_280]
0x1800945ea  mov     rax, [rcx]
0x1800945ed  mov     rax, [rax+38h]
0x1800945f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800945f6  mov     ebx, eax
0x1800945f8  test    eax, eax
0x1800945fa  jns     short loc_18009464A
0x1800945fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180094603  lea     rax, WPP_GLOBAL_Control
0x18009460a  cmp     rcx, rax
0x18009460d  jz      short loc_180094638
0x18009460f  test    [rcx+44h], r12d
0x180094613  jz      short loc_180094638
0x180094615  cmp     byte ptr [rcx+41h], 2
0x180094619  jb      short loc_180094638
0x18009461b  mov     edx, 3Dh ; '='
0x180094620  mov     [rsp+2E0h+var_2C0], ebx
0x180094624  lea     r9, [rbp+1E0h+pszPathOut]
0x180094628  lea     r8, WPP_e4cf962a26e73539d62b7553e52927b0_Traceguids
0x18009462f  mov     rcx, [rcx+38h]
0x180094633  call    WPP_SF_Sd
0x180094638  mov     eax, 9C7h
0x18009463d  mov     [rsp+2E0h+var_2A0], ebx
0x180094641  mov     [rsp+2E0h+var_2A0], ebx
0x180094645  mov     word ptr [rsp+2E0h+var_29C+2], ax
0x18009464a  test    rdi, rdi
0x18009464d  jz      short loc_180094665
0x18009464f  test    r14d, r14d
0x180094652  jz      short loc_180094665
0x180094654  mov     rcx, rdi; FileHandle
0x180094657  call    ?SetReadOnly@CFspCloudFileSystemOperations@@SAJPEAX@Z; CFspCloudFileSystemOperations::SetReadOnly(void *)
0x18009465c  mov     rcx, rdi; Handle
0x18009465f  call    cs:__imp_NtClose
0x180094665  mov     ebx, [rsp+2E0h+var_2A0]
0x180094669  lea     rcx, [rsp+2E0h+var_280]; this
0x18009466e  call    ??1CPropertyStoreHelper@@QEAA@XZ; CPropertyStoreHelper::~CPropertyStoreHelper(void)
0x180094673  nop
0x180094674  lea     rcx, [rsp+2E0h+SourceString]
0x180094679  call    ??1?$CEcsMemPtr@G$0A@@@QEAA@XZ; CEcsMemPtr<ushort,0>::~CEcsMemPtr<ushort,0>(void)
0x18009467e  nop
0x18009467f  lea     rcx, [rsp+2E0h+ppv]
0x180094684  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180094689  nop
0x18009468a  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18009468f  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180094694  mov     eax, ebx
0x180094696  mov     rcx, [rbp+1E0h+var_40]
0x18009469d  xor     rcx, rsp; StackCookie
0x1800946a0  call    __security_check_cookie
0x1800946a5  add     rsp, 2B8h
0x1800946ac  pop     r14
0x1800946ae  pop     r12
0x1800946b0  pop     rdi
0x1800946b1  pop     rsi
0x1800946b2  pop     rbx
0x1800946b3  pop     rbp
0x1800946b4  retn
```
