# CForwardFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800052a0`
- end: `0x180005743`
- name: `?CreateInstance@CForwardFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `1187`
- prototype: `__int64 __fastcall(CForwardFactory *this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800041e8`
- `0x1800052a0`
- `0x18000574c`
- `0x18000a3cc`
- `0x18000b648`
- `0x180012c34`
- `0x18001d3a0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800054a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005553`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000557b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800055ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800055c3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800054a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180005553`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000557b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800055ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800055c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800052ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800052ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005487`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005487`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800054e1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005529`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005529`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180005393`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180005393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005674`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005674`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005616`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000569c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005616`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000569c`
- `wbemcomn!GetMemLogObject` at `0x180005608`
- `wbemcomn!GetMemLogObject` at `0x180005691`
- `wbemcomn!GetMemLogObject` at `0x180005608`
- `wbemcomn!GetMemLogObject` at `0x180005691`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005340`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005340`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005512`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005512`

## string_xrefs

- `0x1800053f5`: `\wbem\wbemcore.dll`

## pseudocode

```c
__int64 __fastcall CForwardFactory::CreateInstance(
        CForwardFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HANDLE v7; // rbx
  CWbemBackupRestore *v8; // r14
  __int64 v9; // rax
  CWbemBackupRestore *v10; // rax
  HINSTANCE v11; // rdx
  HRESULT Instance; // edi
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // r8
  const unsigned __int16 *v16; // r9
  WCHAR *v17; // rdx
  __int64 v18; // r10
  unsigned __int16 v19; // ax
  HMODULE Library; // rax
  HMODULE v21; // rsi
  FARPROC ProcAddress; // rax
  int v24; // r14d
  CMemoryLog *v25; // rax
  signed int LastError; // eax
  unsigned int v27; // edi
  CMemoryLog *MemLogObject; // rax
  __int64 v29; // [rsp+78h] [rbp-240h]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-238h] BYREF

  v7 = hMutex;
  HIWORD(v29) = HIWORD(hMutex);
  if ( hMutex )
    WaitForSingleObject(hMutex, 0xFFFFFFFF);
  if ( !g_bTracing_Initialized )
  {
    v24 = InitializeTracing();
    if ( v24 < 0 )
    {
      if ( v7 )
        ReleaseMutex(v7);
      return (unsigned int)v24;
    }
  }
  if ( !HIBYTE(word_180032CD8) )
    InitializeAndSubscribeVssWriter();
  v8 = 0;
  *a4 = 0;
  if ( (_DWORD)qword_180032A60 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids);
    }
    if ( v7 )
      ReleaseMutex(v7);
    return 2148007944LL;
  }
  else
  {
    v9 = *(_QWORD *)((char *)this + 12) - *(_QWORD *)&CLSID_WbemBackupRestore.Data1;
    if ( !v9 )
      v9 = *(_QWORD *)((char *)this + 20) - *(_QWORD *)CLSID_WbemBackupRestore.Data4;
    if ( v9 )
    {
      if ( GetSystemDirectoryW(Buffer, 0x104u) )
      {
        v13 = 260;
        v14 = Buffer;
        while ( v13 )
        {
          if ( !*v14 )
          {
            v15 = 2147483646;
            v16 = L"\\wbem\\wbemcore.dll";
            v17 = &Buffer[260 - v13];
            v18 = 0;
            while ( v13 )
            {
              if ( !v15 )
                goto LABEL_26;
              v19 = *v16;
              if ( !*v16 )
                goto LABEL_26;
              ++v16;
              *v17++ = v19;
              --v13;
              --v15;
              ++v18;
            }
            --v17;
LABEL_26:
            *v17 = 0;
            break;
          }
          ++v14;
          --v13;
        }
        Library = LoadLibraryExW(Buffer, 0, 8u);
        v21 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "Reinitialize");
          if ( ProcAddress )
          {
            ((void (__fastcall *)(_QWORD))ProcAddress)(0);
            Instance = CoCreateInstance(&CLSID_InProcWbemLevel1Login, 0, 1u, &IID_IUnknown, a4);
            if ( Instance < 0
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids,
                (unsigned int)Instance);
            }
          }
          else
          {
            Instance = -2147217398;
          }
          FreeLibrary(v21);
        }
        else
        {
          Instance = -2147217398;
        }
        goto LABEL_29;
      }
      LastError = GetLastError();
      v27 = LastError;
      if ( LastError > 0 )
        v27 = (unsigned __int16)LastError | 0x80070000;
      if ( (v27 & 0x80000000) != 0 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v27);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids, v27);
      }
      if ( v7 )
        ReleaseMutex(v7);
      return v27;
    }
    else
    {
      v10 = (CWbemBackupRestore *)CWin32DefaultArena::WbemMemAlloc(0xA0u);
      if ( v10 )
        v8 = CWbemBackupRestore::CWbemBackupRestore(v10, v11);
      if ( v8 )
      {
        Instance = (**(__int64 (__fastcall ***)(CWbemBackupRestore *, const struct _GUID *, void **))v8)(v8, a3, a4);
        if ( Instance < 0 )
          (*(void (__fastcall **)(CWbemBackupRestore *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
LABEL_29:
        if ( v7 )
          ReleaseMutex(v7);
        return (unsigned int)Instance;
      }
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, -2147217402);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids, 2147749894LL);
      }
      if ( v7 )
        ReleaseMutex(v7);
      return 2147749894LL;
    }
  }
}

```

## disassembly

```asm
0x1800052a0  mov     [rsp+arg_0], rbx
0x1800052a5  mov     [rsp+arg_8], rsi
0x1800052aa  push    rdi
0x1800052ab  push    r14
0x1800052ad  push    r15
0x1800052af  sub     rsp, 2A0h
0x1800052b6  mov     rax, cs:__security_cookie
0x1800052bd  xor     rax, rsp
0x1800052c0  mov     [rsp+2B8h+var_28], rax
0x1800052c8  mov     r15, r9
0x1800052cb  mov     rsi, r8
0x1800052ce  mov     rdi, rcx
0x1800052d1  mov     rbx, cs:hMutex
0x1800052d8  mov     [rsp+2B8h+var_240], rbx
0x1800052dd  test    rbx, rbx
0x1800052e0  jz      short loc_1800052F1
0x1800052e2  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800052e7  mov     rcx, rbx; hHandle
0x1800052ea  call    cs:__imp_WaitForSingleObject
0x1800052f0  nop
0x1800052f1  cmp     cs:?g_bTracing_Initialized@@3_NA, 0; bool g_bTracing_Initialized
0x1800052f8  jz      loc_180005563
0x1800052fe  cmp     byte ptr cs:word_180032CD8+1, 0
0x180005305  jz      loc_1800055D0
0x18000530b  xor     r14d, r14d
0x18000530e  mov     [r15], r14
0x180005311  cmp     dword ptr cs:qword_180032A60, r14d
0x180005318  jnz     loc_180005534
0x18000531e  mov     rax, [rdi+0Ch]
0x180005322  sub     rax, qword ptr cs:CLSID_WbemBackupRestore.Data1
0x180005329  jnz     short loc_180005336
0x18000532b  mov     rax, [rdi+14h]
0x18000532f  sub     rax, qword ptr cs:CLSID_WbemBackupRestore.Data4
0x180005336  test    rax, rax
0x180005339  jnz     short loc_180005384
0x18000533b  mov     ecx, 0A0h
0x180005340  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180005346  mov     [rsp+2B8h+var_280], rax
0x18000534b  test    rax, rax
0x18000534e  jnz     loc_180005593
0x180005354  test    r14, r14
0x180005357  jz      loc_180005608
0x18000535d  mov     rax, [r14]
0x180005360  mov     r8, r15
0x180005363  mov     rdx, rsi
0x180005366  mov     rcx, r14
0x180005369  mov     rax, [rax]
0x18000536c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005371  mov     edi, eax
0x180005373  mov     [rsp+2B8h+var_288], eax
0x180005377  test    eax, eax
0x180005379  js      loc_18000565B
0x18000537f  jmp     loc_18000549E
0x180005384  mov     edi, 104h
0x180005389  mov     edx, edi; uSize
0x18000538b  lea     rcx, [rsp+2B8h+Buffer]; lpBuffer
0x180005393  call    cs:__imp_GetSystemDirectoryW
0x180005399  test    eax, eax
0x18000539b  jz      loc_180005674
0x1800053a1  mov     [rsp+2B8h+var_280], r14
0x1800053a6  mov     ecx, edi
0x1800053a8  mov     [rsp+2B8h+var_260], rcx
0x1800053ad  lea     rax, [rsp+2B8h+Buffer]
0x1800053b5  mov     [rsp+2B8h+var_268], rax
0x1800053ba  nop     word ptr [rax+rax+00h]
0x1800053c0  test    rcx, rcx
0x1800053c3  jz      loc_180005589
0x1800053c9  cmp     [rax], r14w
0x1800053cd  jz      short loc_1800053E2
0x1800053cf  add     rax, 2
0x1800053d3  mov     [rsp+2B8h+var_268], rax
0x1800053d8  dec     rcx
0x1800053db  mov     [rsp+2B8h+var_260], rcx
0x1800053e0  jmp     short loc_1800053C0
0x1800053e2  sub     rdi, rcx
0x1800053e5  mov     [rsp+2B8h+var_280], rdi
0x1800053ea  mov     r8d, 7FFFFFFEh
0x1800053f0  mov     [rsp+2B8h+var_248], r8
0x1800053f5  lea     r9, aWbemWbemcoreDl; "\\wbem\\wbemcore.dll"
0x1800053fc  mov     [rsp+2B8h+var_258], r9
0x180005401  mov     [rsp+2B8h+var_250], rcx
0x180005406  lea     rdx, [rsp+2B8h+Buffer]
0x18000540e  lea     rdx, [rdx+rdi*2]
0x180005412  mov     [rsp+2B8h+var_278], rdx
0x180005417  mov     r10, r14
0x18000541a  mov     [rsp+2B8h+var_270], r14
0x18000541f  nop
0x180005420  test    rcx, rcx
0x180005423  jz      short loc_180005462
0x180005425  test    r8, r8
0x180005428  jz      short loc_180005473
0x18000542a  movzx   eax, word ptr [r9]
0x18000542e  test    ax, ax
0x180005431  jz      short loc_180005473
0x180005433  add     r9, 2
0x180005437  mov     [rsp+2B8h+var_258], r9
0x18000543c  mov     [rdx], ax
0x18000543f  add     rdx, 2
0x180005443  mov     [rsp+2B8h+var_278], rdx
0x180005448  dec     rcx
0x18000544b  mov     [rsp+2B8h+var_250], rcx
0x180005450  dec     r8
0x180005453  mov     [rsp+2B8h+var_248], r8
0x180005458  inc     r10
0x18000545b  mov     [rsp+2B8h+var_270], r10
0x180005460  jmp     short loc_180005420
0x180005462  sub     rdx, 2
0x180005466  mov     [rsp+2B8h+var_278], rdx
0x18000546b  dec     r10
0x18000546e  mov     [rsp+2B8h+var_270], r10
0x180005473  mov     [rdx], r14w
0x180005477  xor     edx, edx; hFile
0x180005479  mov     r8d, 8; dwFlags
0x18000547f  lea     rcx, [rsp+2B8h+Buffer]; lpLibFileName
0x180005487  call    cs:__imp_LoadLibraryExW
0x18000548d  mov     rsi, rax
0x180005490  test    rax, rax
0x180005493  jnz     short loc_1800054D7
0x180005495  mov     edi, 8004100Ah
0x18000549a  mov     [rsp+2B8h+var_288], edi
0x18000549e  test    rbx, rbx
0x1800054a1  jz      short loc_1800054AC
0x1800054a3  mov     rcx, rbx; hMutex
0x1800054a6  call    cs:__imp_ReleaseMutex
0x1800054ac  mov     eax, edi
0x1800054ae  mov     rcx, [rsp+2B8h+var_28]
0x1800054b6  xor     rcx, rsp; StackCookie
0x1800054b9  call    __security_check_cookie
0x1800054be  lea     r11, [rsp+2B8h+var_18]
0x1800054c6  mov     rbx, [r11+20h]
0x1800054ca  mov     rsi, [r11+28h]
0x1800054ce  mov     rsp, r11
0x1800054d1  pop     r15
0x1800054d3  pop     r14
0x1800054d5  pop     rdi
0x1800054d6  retn
0x1800054d7  lea     rdx, ProcName; "Reinitialize"
0x1800054de  mov     rcx, rsi; hModule
0x1800054e1  call    cs:__imp_GetProcAddress
0x1800054e7  test    rax, rax
0x1800054ea  jz      loc_1800056DE
0x1800054f0  xor     ecx, ecx
0x1800054f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f7  mov     [rsp+2B8h+ppv], r15; ppv
0x1800054fc  lea     r9, IID_IUnknown; riid
0x180005503  xor     edx, edx; pUnkOuter
0x180005505  mov     r8d, 1; dwClsContext
0x18000550b  lea     rcx, CLSID_InProcWbemLevel1Login; rclsid
0x180005512  call    cs:__imp_CoCreateInstance
0x180005518  mov     edi, eax
0x18000551a  mov     [rsp+2B8h+var_288], eax
0x18000551e  test    eax, eax
0x180005520  js      loc_1800056EC
0x180005526  mov     rcx, rsi; hLibModule
0x180005529  call    cs:__imp_FreeLibrary
0x18000552f  jmp     loc_18000549E
0x180005534  lea     rax, WPP_GLOBAL_Control
0x18000553b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005542  cmp     rcx, rax
0x180005545  jnz     loc_1800055DA
0x18000554b  test    rbx, rbx
0x18000554e  jz      short loc_180005559
0x180005550  mov     rcx, rbx; hMutex
0x180005553  call    cs:__imp_ReleaseMutex
0x180005559  mov     eax, 80080008h
0x18000555e  jmp     loc_1800054AE
0x180005563  call    ?InitializeTracing@@YAJXZ; InitializeTracing(void)
0x180005568  mov     r14d, eax
0x18000556b  test    eax, eax
0x18000556d  jns     loc_1800052FE
0x180005573  test    rbx, rbx
0x180005576  jz      short loc_180005581
0x180005578  mov     rcx, rbx; hMutex
0x18000557b  call    cs:__imp_ReleaseMutex
0x180005581  mov     eax, r14d
0x180005584  jmp     loc_1800054AE
0x180005589  mov     [rsp+2B8h+var_280], r14
0x18000558e  jmp     loc_180005477
0x180005593  mov     rcx, rax; this
0x180005596  call    ??0CWbemBackupRestore@@QEAA@PEAUHINSTANCE__@@@Z; CWbemBackupRestore::CWbemBackupRestore(HINSTANCE__ *)
0x18000559b  mov     r14, rax
0x18000559e  jmp     loc_180005354
0x1800055a3  test    rbx, rbx
0x1800055a6  jz      short loc_1800055B1
0x1800055a8  mov     rcx, rbx; hMutex
0x1800055ab  call    cs:__imp_ReleaseMutex
0x1800055b1  mov     eax, 80041006h
0x1800055b6  jmp     loc_1800054AE
0x1800055bb  test    rbx, rbx
0x1800055be  jz      short loc_1800055C9
0x1800055c0  mov     rcx, rbx; hMutex
0x1800055c3  call    cs:__imp_ReleaseMutex
0x1800055c9  mov     eax, edi
0x1800055cb  jmp     loc_1800054AE
0x1800055d0  call    ?InitializeAndSubscribeVssWriter@@YAHXZ; InitializeAndSubscribeVssWriter(void)
0x1800055d5  jmp     loc_18000530B
0x1800055da  test    byte ptr [rcx+1Ch], 1
0x1800055de  jz      loc_18000554B
0x1800055e4  cmp     byte ptr [rcx+19h], 5
0x1800055e8  jb      loc_18000554B
0x1800055ee  mov     edx, 0Ah
0x1800055f3  lea     r8, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids
0x1800055fa  mov     rcx, [rcx+10h]
0x1800055fe  call    WPP_SF_
0x180005603  jmp     loc_18000554B
0x180005608  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000560e  mov     edx, 80041006h
0x180005613  mov     rcx, rax
0x180005616  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000561c  lea     rax, WPP_GLOBAL_Control
0x180005623  mov     rcx, cs:WPP_GLOBAL_Control
0x18000562a  cmp     rcx, rax
0x18000562d  jz      short loc_180005656
0x18000562f  test    byte ptr [rcx+1Ch], 1
0x180005633  jz      short loc_180005656
0x180005635  cmp     byte ptr [rcx+19h], 2
0x180005639  jb      short loc_180005656
0x18000563b  mov     edx, 0Bh
0x180005640  mov     r9d, 80041006h
0x180005646  lea     r8, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids
0x18000564d  mov     rcx, [rcx+10h]
0x180005651  call    WPP_SF_d
0x180005656  jmp     loc_1800055A3
0x18000565b  mov     rcx, [r14]
0x18000565e  mov     rax, [rcx+38h]
0x180005662  mov     edx, 1
0x180005667  mov     rcx, r14
0x18000566a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000566f  jmp     loc_18000549E
0x180005674  call    cs:__imp_GetLastError
0x18000567a  mov     edi, eax
0x18000567c  test    eax, eax
0x18000567e  jle     short loc_180005689
0x180005680  movzx   edi, ax
0x180005683  or      edi, 80070000h
0x180005689  mov     [rsp+2B8h+var_288], edi
0x18000568d  test    edi, edi
0x18000568f  jns     short loc_1800056A2
0x180005691  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180005697  mov     edx, edi
0x180005699  mov     rcx, rax
0x18000569c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800056a2  lea     rax, WPP_GLOBAL_Control
0x1800056a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056b0  cmp     rcx, rax
0x1800056b3  jz      short loc_1800056D9
0x1800056b5  test    byte ptr [rcx+1Ch], 1
0x1800056b9  jz      short loc_1800056D9
0x1800056bb  cmp     byte ptr [rcx+19h], 2
0x1800056bf  jb      short loc_1800056D9
0x1800056c1  mov     edx, 0Ch
0x1800056c6  mov     r9d, edi
0x1800056c9  lea     r8, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids
0x1800056d0  mov     rcx, [rcx+10h]
0x1800056d4  call    WPP_SF_d
0x1800056d9  jmp     loc_1800055BB
0x1800056de  mov     edi, 8004100Ah
0x1800056e3  mov     [rsp+2B8h+var_288], edi
0x1800056e7  jmp     loc_180005526
0x1800056ec  lea     rax, WPP_GLOBAL_Control
0x1800056f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800056fa  cmp     rcx, rax
0x1800056fd  jz      loc_180005526
0x180005703  test    byte ptr [rcx+1Ch], 1
0x180005707  jz      loc_180005526
0x18000570d  cmp     byte ptr [rcx+19h], 5
0x180005711  jb      loc_180005526
0x180005717  mov     edx, 0Dh
0x18000571c  mov     r9d, edi
0x18000571f  lea     r8, WPP_bd48e7c20c283f7fc8a31277f621c9a6_Traceguids
0x180005726  mov     rcx, [rcx+10h]
0x18000572a  call    WPP_SF_d
0x18000572f  jmp     loc_180005526
0x180005734  mov     edi, [rsp+2B8h+var_288]
0x180005738  mov     rbx, [rsp+2B8h+var_240]
0x18000573d  jmp     loc_18000549E
```
