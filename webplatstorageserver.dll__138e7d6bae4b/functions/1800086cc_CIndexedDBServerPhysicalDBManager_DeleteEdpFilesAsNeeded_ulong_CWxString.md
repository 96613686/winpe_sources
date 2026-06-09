# CIndexedDBServerPhysicalDBManager::DeleteEdpFilesAsNeeded(ulong,CWxString *)

- ea: `0x1800086cc`
- end: `0x1800088fb`
- name: `?DeleteEdpFilesAsNeeded@CIndexedDBServerPhysicalDBManager@@SAXKPEAVCWxString@@@Z`
- size: `559`
- prototype: `static void(unsigned int, struct CWxString *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002bf80`

## callees

- `0x180007b2c`
- `0x180007f40`
- `0x1800086ac`
- `0x1800086cc`
- `0x180008904`
- `0x180009b00`
- `0x18001c800`
- `0x18005bb90`
- `0x180062204`
- `0x18006e638`
- `0x18007ce0c`
- `0x180080fb0`
- `0x1800810a4`
- `0x1800b0810`
- `0x1800b0ef4`
- `0x1800b3848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008877`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800088a8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800088a8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000886b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000886b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008748`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180008748`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CIndexedDBServerPhysicalDBManager::DeleteEdpFilesAsNeeded(BrowserUtilEdp *a1, struct CWxString *a2)
{
  int v3; // ebx
  int v4; // edi
  unsigned int v5; // edi
  unsigned __int16 *v6; // r14
  int v7; // eax
  CIndexedDBServerConnectionsMgr *v8; // rbx
  CIndexedDBAppPhysicalDatabaseHolder *v9; // rcx
  int v10; // esi
  unsigned __int64 v11; // rcx
  const char *v12; // r9
  unsigned __int64 v13; // rcx
  BOOL v14; // esi
  int v15; // edi
  signed int LastError; // eax
  signed int v17; // ecx
  wil *v18; // rcx
  struct CIndexedDBServerConnectionsMgr *v19; // [rsp+20h] [rbp-78h] BYREF
  int v20; // [rsp+28h] [rbp-70h]
  LPCWSTR lpFileName; // [rsp+30h] [rbp-68h] BYREF
  LPCWSTR v22; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v23[32]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v3 = (int)a1;
  if ( !BrowserUtilEdp::IsEdpEnforcementEnabled(a1) )
  {
    v4 = 18;
    if ( (v3 & 0x88) != 8 )
      v4 = 2;
    v5 = v3 | v4;
    lpFileName = 0;
    v22 = 0;
    if ( (int)GetIndexedDBFilePath(v5, 0, (unsigned __int16 **)&lpFileName, (unsigned __int16 **)&v22) >= 0 )
    {
      v6 = (unsigned __int16 *)lpFileName;
      if ( GetFileAttributesW(lpFileName) != -1 )
      {
        v19 = 0;
        v7 = CIndexedDBServerConnectionsMgr::EnsureSingleton(&v19);
        v8 = v19;
        if ( v7 >= 0 )
        {
          if ( (v5 & 0x98) == 0x18 )
          {
            v10 = CIndexedDBServerConnectionsMgr::ForceCloseFactoriesByAppContainer(v19, v5, a2);
            if ( v10 >= 0 )
            {
              CIndexedDBAppPhysicalDatabaseHolder::ShutdownPerPackageDatabase(v9, v5, a2, 1);
              if ( (v5 & 0x40) == 0 )
                goto LABEL_20;
              goto LABEL_35;
            }
          }
          else
          {
            v10 = CIndexedDBServerConnectionsMgr::ForceCloseFactories(v19, v5);
            if ( v10 >= 0 )
            {
              v11 = 136LL * GetIndexFromContextFlags(v5);
              if ( (v5 & 0x40) == 0 )
              {
                if ( (v5 & 8) != 0 )
                  v13 = v11 + 1126000;
                else
                  v13 = v11 + 1124912;
                CIndexedDBPhysicalDatabaseHolder::ShutdownGlobalDatabase(
                  (CIndexedDBPhysicalDatabaseHolder *)((char *)_ImageBase + v13),
                  1);
                goto LABEL_20;
              }
              CIndexedDBPhysicalDatabaseHolder::ShutdownGlobalDatabase(
                (CIndexedDBPhysicalDatabaseHolder *)&_ImageBase[v11 / 2 + 563136],
                1);
LABEL_35:
              try
              {
                ClientIdentity::s_GetPackageName((__int64)v23);
                ScheduleQuotaRecalculation(v23, 1);
                std::wstring::~wstring(v23);
              }
              catch ( ... )
              {
                wil::details::in1diag3::Log_CaughtException(
                  retaddr,
                  (void *)0x3D8,
                  (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\server\\physicaldbmanager.cxx",
                  v12);
                v20 = wil::ResultFromCaughtException(v18);
                v6 = (unsigned __int16 *)lpFileName;
                v10 = v20;
                v8 = v19;
              }
              if ( v10 < 0 )
                goto LABEL_31;
LABEL_20:
              if ( (int)DeleteDatabaseLogFiles(v6) >= 0 )
              {
                v14 = 0;
                v15 = 0;
                while ( !v14 )
                {
                  v14 = DeleteFileW(v22);
                  if ( v14 )
                    goto LABEL_30;
                  LastError = GetLastError();
                  v17 = LastError;
                  if ( LastError > 0 )
                    v17 = (unsigned __int16)LastError | 0x80070000;
                  if ( (unsigned int)(v17 + 2147024894) <= 1 )
                    break;
                  if ( v17 >= 0 || (unsigned int)(v15 + 1) >= 2 )
                  {
LABEL_30:
                    if ( (unsigned int)++v15 >= 2 )
                      break;
                  }
                  else
                  {
                    Sleep(0xBB8u);
                    ++v15;
                  }
                }
              }
            }
          }
        }
LABEL_31:
        operator delete(v6);
        operator delete((void *)v22);
        if ( v8 )
          CIndexedDBServerConnectionsMgr::Release(v8);
      }
    }
  }
}

```

## disassembly

```asm
0x1800086cc  mov     [rsp+arg_10], rbx
0x1800086d1  push    rsi
0x1800086d2  push    rdi
0x1800086d3  push    r12
0x1800086d5  push    r14
0x1800086d7  push    r15
0x1800086d9  sub     rsp, 70h
0x1800086dd  mov     rax, cs:__security_cookie
0x1800086e4  xor     rax, rsp
0x1800086e7  mov     [rsp+98h+var_38], rax
0x1800086ec  mov     r15, rdx
0x1800086ef  mov     ebx, ecx
0x1800086f1  call    ?IsEdpEnforcementEnabled@BrowserUtilEdp@@YA_NXZ; BrowserUtilEdp::IsEdpEnforcementEnabled(void)
0x1800086f6  test    al, al
0x1800086f8  jnz     loc_1800088D9
0x1800086fe  mov     eax, ebx
0x180008700  and     al, 88h
0x180008702  mov     edi, 12h
0x180008707  lea     r12d, [rdi-10h]
0x18000870b  cmp     al, 8
0x18000870d  cmovnz  edi, r12d
0x180008711  or      edi, ebx
0x180008713  mov     [rsp+98h+lpFileName], 0
0x18000871c  mov     [rsp+98h+var_60], 0
0x180008725  lea     r9, [rsp+98h+var_60]; unsigned __int16 **
0x18000872a  lea     r8, [rsp+98h+lpFileName]; unsigned __int16 **
0x18000872f  xor     edx, edx; bool
0x180008731  mov     ecx, edi; unsigned int
0x180008733  call    ?GetIndexedDBFilePath@@YAJK_NPEAPEAG1@Z; GetIndexedDBFilePath(ulong,bool,ushort * *,ushort * *)
0x180008738  test    eax, eax
0x18000873a  js      loc_1800088D9
0x180008740  mov     r14, [rsp+98h+lpFileName]
0x180008745  mov     rcx, r14; lpFileName
0x180008748  call    cs:__imp_GetFileAttributesW
0x18000874e  cmp     eax, 0FFFFFFFFh
0x180008751  jz      loc_1800088D9
0x180008757  mov     [rsp+98h+var_78], 0
0x180008760  lea     rcx, [rsp+98h+var_78]; struct CIndexedDBServerConnectionsMgr **
0x180008765  call    ?EnsureSingleton@CIndexedDBServerConnectionsMgr@@SAJPEAPEAV1@@Z; CIndexedDBServerConnectionsMgr::EnsureSingleton(CIndexedDBServerConnectionsMgr * *)
0x18000876a  mov     rbx, [rsp+98h+var_78]
0x18000876f  test    eax, eax
0x180008771  js      loc_1800088B9
0x180008777  mov     eax, edi
0x180008779  and     eax, 98h
0x18000877e  mov     edx, edi; unsigned int
0x180008780  mov     rcx, rbx; this
0x180008783  cmp     al, 18h
0x180008785  jnz     short loc_1800087B1
0x180008787  mov     r8, r15; struct CWxString *
0x18000878a  call    ?ForceCloseFactoriesByAppContainer@CIndexedDBServerConnectionsMgr@@QEAAJKPEBVCWxString@@@Z; CIndexedDBServerConnectionsMgr::ForceCloseFactoriesByAppContainer(ulong,CWxString const *)
0x18000878f  mov     esi, eax
0x180008791  test    eax, eax
0x180008793  js      loc_1800088B9
0x180008799  mov     r9b, 1; bool
0x18000879c  mov     r8, r15; struct CWxString *
0x18000879f  mov     edx, edi; unsigned int
0x1800087a1  call    ?ShutdownPerPackageDatabase@CIndexedDBAppPhysicalDatabaseHolder@@QEAAXKPEAVCWxString@@_N@Z; CIndexedDBAppPhysicalDatabaseHolder::ShutdownPerPackageDatabase(ulong,CWxString *,bool)
0x1800087a6  test    dil, 40h
0x1800087aa  jnz     short loc_1800087EF
0x1800087ac  jmp     loc_180008852
0x1800087b1  call    ?ForceCloseFactories@CIndexedDBServerConnectionsMgr@@QEAAJK@Z; CIndexedDBServerConnectionsMgr::ForceCloseFactories(ulong)
0x1800087b6  mov     esi, eax
0x1800087b8  test    eax, eax
0x1800087ba  js      loc_1800088B9
0x1800087c0  mov     ecx, edi; unsigned int
0x1800087c2  call    ?GetIndexFromContextFlags@@YAKK@Z; GetIndexFromContextFlags(ulong)
0x1800087c7  mov     edx, eax
0x1800087c9  imul    rcx, rdx, 88h
0x1800087d0  lea     rax, __ImageBase
0x1800087d7  mov     dl, 1; bool
0x1800087d9  test    dil, 40h
0x1800087dd  jz      short loc_180008834
0x1800087df  lea     rcx, [rcx+112F80h]
0x1800087e6  add     rcx, rax; this
0x1800087e9  call    ?ShutdownGlobalDatabase@CIndexedDBPhysicalDatabaseHolder@@QEAAX_N@Z; CIndexedDBPhysicalDatabaseHolder::ShutdownGlobalDatabase(bool)
0x1800087ee  nop
0x1800087ef  lea     rcx, [rsp+98h+var_58]
0x1800087f4  call    ?s_GetPackageName@ClientIdentity@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ClientIdentity::s_GetPackageName(void)
0x1800087f9  nop
0x1800087fa  mov     edx, 1
0x1800087ff  lea     rcx, [rsp+98h+var_58]
0x180008804  call    ?ScheduleQuotaRecalculation@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WebPlatStorageHandlerType@@@Z; ScheduleQuotaRecalculation(std::wstring const &,WebPlatStorageHandlerType)
0x180008809  nop
0x18000880a  lea     rcx, [rsp+98h+var_58]; void *
0x18000880f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008814  nop
0x180008815  jmp     short loc_18000882B
0x180008817  mov     r12d, 2
0x18000881d  mov     r14, [rsp+98h+lpFileName]
0x180008822  mov     esi, [rsp+98h+var_70]
0x180008826  mov     rbx, [rsp+98h+var_78]
0x18000882b  test    esi, esi
0x18000882d  jns     short loc_180008852
0x18000882f  jmp     loc_1800088B9
0x180008834  test    dil, 8
0x180008838  jz      short loc_180008843
0x18000883a  lea     rcx, [rcx+112E70h]
0x180008841  jmp     short loc_18000884A
0x180008843  lea     rcx, [rcx+112A30h]
0x18000884a  add     rcx, rax; this
0x18000884d  call    ?ShutdownGlobalDatabase@CIndexedDBPhysicalDatabaseHolder@@QEAAX_N@Z; CIndexedDBPhysicalDatabaseHolder::ShutdownGlobalDatabase(bool)
0x180008852  mov     rcx, r14; unsigned __int16 *
0x180008855  call    ?DeleteDatabaseLogFiles@@YAJPEBG@Z; DeleteDatabaseLogFiles(ushort const *)
0x18000885a  test    eax, eax
0x18000885c  js      short loc_1800088B9
0x18000885e  xor     esi, esi
0x180008860  xor     edi, edi
0x180008862  test    esi, esi
0x180008864  jnz     short loc_1800088B9
0x180008866  mov     rcx, [rsp+98h+var_60]; lpFileName
0x18000886b  call    cs:__imp_DeleteFileW
0x180008871  mov     esi, eax
0x180008873  test    eax, eax
0x180008875  jnz     short loc_1800088B2
0x180008877  call    cs:__imp_GetLastError
0x18000887d  mov     ecx, eax
0x18000887f  test    eax, eax
0x180008881  jle     short loc_18000888C
0x180008883  movzx   ecx, ax
0x180008886  or      ecx, 80070000h
0x18000888c  lea     eax, [rcx+7FF8FFFEh]
0x180008892  cmp     eax, 1
0x180008895  jbe     short loc_1800088B9
0x180008897  test    ecx, ecx
0x180008899  jns     short loc_1800088B2
0x18000889b  lea     eax, [rdi+1]
0x18000889e  cmp     eax, r12d
0x1800088a1  jnb     short loc_1800088B2
0x1800088a3  mov     ecx, 0BB8h; dwMilliseconds
0x1800088a8  call    cs:__imp_Sleep
0x1800088ae  inc     edi
0x1800088b0  jmp     short loc_180008862
0x1800088b2  inc     edi
0x1800088b4  cmp     edi, r12d
0x1800088b7  jb      short loc_180008862
0x1800088b9  mov     rcx, r14; Block
0x1800088bc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800088c1  mov     rcx, [rsp+98h+var_60]; Block
0x1800088c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800088cb  nop
0x1800088cc  test    rbx, rbx
0x1800088cf  jz      short loc_1800088D9
0x1800088d1  mov     rcx, rbx; this
0x1800088d4  call    ?Release@CIndexedDBServerConnectionsMgr@@QEAAKXZ; CIndexedDBServerConnectionsMgr::Release(void)
0x1800088d9  mov     rcx, [rsp+98h+var_38]
0x1800088de  xor     rcx, rsp; StackCookie
0x1800088e1  call    __security_check_cookie
0x1800088e6  mov     rbx, [rsp+98h+arg_10]
0x1800088ee  add     rsp, 70h
0x1800088f2  pop     r15
0x1800088f4  pop     r14
0x1800088f6  pop     r12
0x1800088f8  pop     rdi
0x1800088f9  pop     rsi
0x1800088fa  retn
```
