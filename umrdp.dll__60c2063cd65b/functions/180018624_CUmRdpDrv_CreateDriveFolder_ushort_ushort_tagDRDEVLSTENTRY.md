# CUmRdpDrv::CreateDriveFolder(ushort *,ushort *,tagDRDEVLSTENTRY *)

- ea: `0x180018624`
- end: `0x180018b3c`
- name: `?CreateDriveFolder@CUmRdpDrv@@AEAAHPEAG0PEAUtagDRDEVLSTENTRY@@@Z`
- size: `1304`
- prototype: `__int64 __fastcall(CUmRdpDrv *__hidden this, unsigned __int16 *, unsigned __int16 *, struct tagDRDEVLSTENTRY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018390`

## callees

- `0x1800070e0`
- `0x180009fa8`
- `0x18000a01c`
- `0x18000a41c`
- `0x18001294c`
- `0x180018624`
- `0x180018d84`
- `0x180018e74`
- `0x18001910c`
- `0x180019b98`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800186f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018710`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800186f4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180018710`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018a3d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018a3d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180018a7b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180018a7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800186a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001872b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800187a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800187f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800186a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001872b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800187a9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800187f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018927`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001894a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001896d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018a9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018ac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018aec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018927`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001894a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001896d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018a9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018ac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018aec`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018771`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180018771`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800189ed`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800189ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001885c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800188ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018906`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800189ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018a0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001885c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800188ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018906`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800189ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018a0f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001867b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001867b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018b06`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018b06`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001866e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001866e`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800186d0`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x1800186d0`

## string_xrefs

- `0x1800189a4`: `MyComputer\Namespace\%s`

## pseudocode

```c
__int64 __fastcall CUmRdpDrv::CreateDriveFolder(
        CUmRdpDrv *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        va_list *a4)
{
  HRESULT v8; // r12d
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rsi
  unsigned __int16 *v11; // rax
  WCHAR *v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // r14d
  unsigned __int16 *v17; // rax
  __int64 v18; // r11
  SIZE_T v19; // r8
  unsigned int v20; // ebx
  unsigned __int16 *v21; // rax
  void *v22; // rcx
  __int64 v23; // r11
  int VolatilePerUserCLSID; // ebx
  HKEY v25; // rcx
  void *v26; // rcx
  int v27; // ebx
  HKEY v28; // rcx
  int v29; // eax
  unsigned int v30; // edx
  CUmRdpDr *v31; // rcx
  unsigned int v32; // r8d
  unsigned __int16 *lpBuffer; // [rsp+20h] [rbp-E0h]
  HKEY v35; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v37; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  va_list Arguments[2]; // [rsp+70h] [rbp-90h] BYREF
  GUID pguid; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[32]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v42[64]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SubKey[264]; // [rsp+150h] [rbp+50h] BYREF

  pguid = 0;
  v8 = CoInitializeEx(0, 2u);
  v9 = 0;
  if ( CoCreateGuid(&pguid) < 0 )
  {
    v10 = 0;
    goto LABEL_41;
  }
  v11 = (unsigned __int16 *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 0, 0x4Eu);
  v10 = v11;
  if ( v11 )
  {
    *(_OWORD *)Arguments = 0;
    SHStringFromGUIDW(&pguid, v11, 39);
    Buffer[0] = 0;
    v42[0] = 0;
    LoadStringW(g_hInstance, 0x7D7u, Buffer, 32);
    LoadStringW(g_hInstance, 0x7D8u, v42, 64);
    v12 = (WCHAR *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 0, 0x208u);
    if ( !v12 )
      goto LABEL_40;
    Arguments[0] = a4[5];
    Arguments[1] = (va_list)a3;
    FormatMessageW(0x2400u, Buffer, 0, 0, v12, 0x104u, Arguments);
    *((_QWORD *)this + 71) = v12;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v15 = (unsigned int)(v14 + 1);
    v16 = v15;
    v17 = (unsigned __int16 *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 0, 2 * v15);
    if ( !v17 )
    {
      v9 = 0;
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, *((LPVOID *)this + 71));
      *((_QWORD *)this + 71) = 0;
      goto LABEL_41;
    }
    StringCchCopyW(v17, v16, a2);
    *((_QWORD *)this + 127) = v18;
    do
      ++v13;
    while ( v42[v13] );
    v19 = 2LL * (unsigned int)(v13 + 1);
    v20 = v13 + 1;
    v21 = (unsigned __int16 *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 0, v19);
    if ( !v21 )
    {
      v9 = 0;
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, *((LPVOID *)this + 71));
      *((_QWORD *)this + 71) = 0;
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, *((LPVOID *)this + 127));
      *((_QWORD *)this + 127) = 0;
      goto LABEL_41;
    }
    StringCchCopyW(v21, v20, v42);
    v22 = (void *)*((_QWORD *)this + 67);
    *((_QWORD *)this + 75) = v23;
    hKey = 0;
    phkResult = 0;
    GetHKCUClassesCLSID(v22, &hKey, &phkResult);
    if ( hKey )
    {
      VolatilePerUserCLSID = CUmRdpDrv::CreateVolatilePerUserCLSID(this, hKey, v10);
      RegCloseKey(hKey);
    }
    else
    {
      VolatilePerUserCLSID = 0;
    }
    v25 = phkResult;
    if ( phkResult )
    {
      if ( !VolatilePerUserCLSID )
      {
        CUmRdpDrv::CreateVolatilePerUserCLSID(this, phkResult, v10);
        v25 = phkResult;
      }
      RegCloseKey(v25);
    }
    v26 = (void *)*((_QWORD *)this + 67);
    v35 = 0;
    v37 = 0;
    GetHKCUWow64ClassesCLSID(v26, &v35, &v37);
    if ( v35 )
    {
      v27 = CUmRdpDrv::CreateVolatilePerUserCLSID(this, v35, v10);
      RegCloseKey(v35);
    }
    else
    {
      v27 = 0;
    }
    v28 = v37;
    if ( v37 )
    {
      if ( v27 || (v29 = CUmRdpDrv::CreateVolatilePerUserCLSID(this, v37, v10), v28 = v37, v9 = 0, v29) )
        v9 = 1;
      RegCloseKey(v28);
    }
    else
    {
      v9 = 0;
    }
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, *((LPVOID *)this + 71));
    *((_QWORD *)this + 71) = 0;
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, *((LPVOID *)this + 127));
    *((_QWORD *)this + 127) = 0;
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, *((LPVOID *)this + 75));
    *((_QWORD *)this + 75) = 0;
    if ( v9 )
    {
      v35 = 0;
      phkResult = 0;
      if ( CUmRdpDrv::_SHCreateSessionKey(this, v30, &v35) >= 0 )
      {
        if ( (int)StringCchPrintfW(SubKey, 0x104u, L"MyComputer\\Namespace\\%s", v10) < 0
          || RegCreateKeyExW(v35, SubKey, 0, 0, 1u, 0x20006u, 0, &phkResult, 0) )
        {
          v9 = 0;
        }
        else
        {
          v9 = 1;
          RegCloseKey(phkResult);
        }
        RegCloseKey(v35);
        if ( !v9 )
          goto LABEL_41;
        if ( (int)StringCchPrintfW(SubKey, 0x104u, L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::%s", v10) >= 0 )
        {
          RevertToSelf();
          v31 = *(CUmRdpDr **)this;
          v35 = 0;
          if ( !(unsigned int)CUmRdpDr::CreateUmRdpRpc(v31, (struct CUmRdpRpc **)&v35) )
          {
            CUmRdpRpc::SHChangeNotify((CUmRdpRpc *)v35, 2, v32, SubKey, lpBuffer);
            CUmRdpRpc::Release((CUmRdpRpc *)v35);
          }
          v9 = ImpersonateLoggedOnUser(*((HANDLE *)this + 67));
          goto LABEL_41;
        }
      }
LABEL_40:
      v9 = 0;
    }
  }
LABEL_41:
  if ( v8 >= 0 )
    CoUninitialize();
  a4[9] = (va_list)v10;
  return v9;
}

```

## disassembly

```asm
0x180018624  mov     [rsp-8+arg_10], rbx
0x180018629  push    rbp
0x18001862a  push    rsi
0x18001862b  push    rdi
0x18001862c  push    r12
0x18001862e  push    r13
0x180018630  push    r14
0x180018632  push    r15
0x180018634  lea     rbp, [rsp-270h]
0x18001863c  sub     rsp, 370h
0x180018643  mov     rax, cs:__security_cookie
0x18001864a  xor     rax, rsp
0x18001864d  mov     [rbp+2A0h+var_40], rax
0x180018654  mov     r15, rdx
0x180018657  mov     rdi, rcx
0x18001865a  xorps   xmm0, xmm0
0x18001865d  mov     edx, 2; dwCoInit
0x180018662  xor     ecx, ecx; pvReserved
0x180018664  mov     r13, r9
0x180018667  movups  xmmword ptr [rbp+2A0h+pguid.Data1], xmm0
0x18001866b  mov     r14, r8
0x18001866e  call    cs:__imp_CoInitializeEx
0x180018674  lea     rcx, [rbp+2A0h+pguid]; pguid
0x180018678  mov     r12d, eax
0x18001867b  call    cs:__imp_CoCreateGuid
0x180018681  xor     ebx, ebx
0x180018683  test    eax, eax
0x180018685  jns     short loc_180018692
0x180018687  xor     r14d, r14d
0x18001868a  mov     esi, r14d
0x18001868d  jmp     loc_180018B01
0x180018692  mov     rcx, gs:60h
0x18001869b  xor     edx, edx; dwFlags
0x18001869d  mov     rcx, [rcx+30h]; hHeap
0x1800186a1  lea     r8d, [rdx+4Eh]; dwBytes
0x1800186a5  call    cs:__imp_HeapAlloc
0x1800186ab  mov     rsi, rax
0x1800186ae  test    rax, rax
0x1800186b1  jnz     short loc_1800186BB
0x1800186b3  xor     r14d, r14d
0x1800186b6  jmp     loc_180018B01
0x1800186bb  xorps   xmm0, xmm0
0x1800186be  lea     rcx, [rbp+2A0h+pguid]
0x1800186c2  mov     r8d, 27h ; '''
0x1800186c8  mov     rdx, rsi
0x1800186cb  movups  xmmword ptr [rsp+3A0h+var_330], xmm0
0x1800186d0  call    cs:__imp_SHStringFromGUIDW
0x1800186d6  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800186dd  lea     r8, [rbp+2A0h+Buffer]; lpBuffer
0x1800186e1  mov     r9d, 20h ; ' '; cchBufferMax
0x1800186e7  mov     [rbp+2A0h+Buffer], bx
0x1800186eb  mov     edx, 7D7h; uID
0x1800186f0  mov     [rbp+2A0h+var_2D0], bx
0x1800186f4  call    cs:__imp_LoadStringW
0x1800186fa  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180018701  lea     r8, [rbp+2A0h+var_2D0]; lpBuffer
0x180018705  mov     r9d, 40h ; '@'; cchBufferMax
0x18001870b  mov     edx, 7D8h; uID
0x180018710  call    cs:__imp_LoadStringW
0x180018716  mov     rcx, gs:60h
0x18001871f  xor     edx, edx; dwFlags
0x180018721  mov     r8d, 208h; dwBytes
0x180018727  mov     rcx, [rcx+30h]; hHeap
0x18001872b  call    cs:__imp_HeapAlloc
0x180018731  mov     rbx, rax
0x180018734  test    rax, rax
0x180018737  jz      loc_180018AFB
0x18001873d  mov     rcx, [r13+28h]
0x180018741  lea     rax, [rsp+3A0h+var_330]
0x180018746  mov     [rsp+3A0h+Arguments], rax; Arguments
0x18001874b  lea     rdx, [rbp+2A0h+Buffer]; lpSource
0x18001874f  mov     [rsp+3A0h+var_330], rcx
0x180018754  xor     r9d, r9d; dwLanguageId
0x180018757  mov     [rsp+3A0h+nSize], 104h; nSize
0x18001875f  mov     ecx, 2400h; dwFlags
0x180018764  xor     r8d, r8d; dwMessageId
0x180018767  mov     [rsp+3A0h+lpBuffer], rbx; unsigned __int16 *
0x18001876c  mov     [rsp+3A0h+var_330+8], r14
0x180018771  call    cs:__imp_FormatMessageW
0x180018777  mov     [rdi+238h], rbx
0x18001877e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018782  mov     rax, rbx
0x180018785  xor     ecx, ecx
0x180018787  inc     rax
0x18001878a  cmp     [r15+rax*2], cx
0x18001878f  jnz     short loc_180018787
0x180018791  mov     rcx, gs:60h
0x18001879a  inc     eax
0x18001879c  xor     edx, edx; dwFlags
0x18001879e  mov     r14d, eax
0x1800187a1  mov     rcx, [rcx+30h]; hHeap
0x1800187a5  lea     r8, [rax+rax]; dwBytes
0x1800187a9  call    cs:__imp_HeapAlloc
0x1800187af  mov     r11, rax
0x1800187b2  test    rax, rax
0x1800187b5  jz      loc_180018AD0
0x1800187bb  mov     r8, r15; unsigned __int16 *
0x1800187be  mov     edx, r14d; unsigned __int64
0x1800187c1  mov     rcx, rax; unsigned __int16 *
0x1800187c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800187c9  lea     rax, [rbp+2A0h+var_2D0]
0x1800187cd  mov     [rdi+3F8h], r11
0x1800187d4  xor     r14d, r14d
0x1800187d7  inc     rbx
0x1800187da  cmp     [rax+rbx*2], r14w
0x1800187df  jnz     short loc_1800187D7
0x1800187e1  mov     rcx, gs:60h
0x1800187ea  lea     eax, [rbx+1]
0x1800187ed  lea     r8, [rax+rax]; dwBytes
0x1800187f1  mov     ebx, eax
0x1800187f3  xor     edx, edx; dwFlags
0x1800187f5  mov     rcx, [rcx+30h]; hHeap
0x1800187f9  call    cs:__imp_HeapAlloc
0x1800187ff  mov     r11, rax
0x180018802  test    rax, rax
0x180018805  jz      loc_180018A85
0x18001880b  lea     r8, [rbp+2A0h+var_2D0]; unsigned __int16 *
0x18001880f  mov     edx, ebx; unsigned __int64
0x180018811  mov     rcx, rax; unsigned __int16 *
0x180018814  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018819  mov     rcx, [rdi+218h]; void *
0x180018820  lea     r8, [rsp+3A0h+var_348]; HKEY *
0x180018825  lea     rdx, [rsp+3A0h+hKey]; HKEY *
0x18001882a  mov     [rdi+258h], r11
0x180018831  mov     [rsp+3A0h+hKey], r14
0x180018836  mov     [rsp+3A0h+var_348], r14
0x18001883b  call    ?GetHKCUClassesCLSID@@YAXPEAXPEAPEAUHKEY__@@1@Z; GetHKCUClassesCLSID(void *,HKEY__ * *,HKEY__ * *)
0x180018840  mov     rdx, [rsp+3A0h+hKey]; HKEY
0x180018845  test    rdx, rdx
0x180018848  jz      short loc_180018864
0x18001884a  mov     r8, rsi; unsigned __int16 *
0x18001884d  mov     rcx, rdi; this
0x180018850  call    ?CreateVolatilePerUserCLSID@CUmRdpDrv@@AEAAHPEAUHKEY__@@PEAG@Z; CUmRdpDrv::CreateVolatilePerUserCLSID(HKEY__ *,ushort *)
0x180018855  mov     rcx, [rsp+3A0h+hKey]; hKey
0x18001885a  mov     ebx, eax
0x18001885c  call    cs:__imp_RegCloseKey
0x180018862  jmp     short loc_180018867
0x180018864  mov     ebx, r14d
0x180018867  mov     rcx, [rsp+3A0h+var_348]
0x18001886c  test    rcx, rcx
0x18001886f  jz      short loc_18001888E
0x180018871  test    ebx, ebx
0x180018873  jnz     short loc_180018888
0x180018875  mov     rdx, rcx; HKEY
0x180018878  mov     r8, rsi; unsigned __int16 *
0x18001887b  mov     rcx, rdi; this
0x18001887e  call    ?CreateVolatilePerUserCLSID@CUmRdpDrv@@AEAAHPEAUHKEY__@@PEAG@Z; CUmRdpDrv::CreateVolatilePerUserCLSID(HKEY__ *,ushort *)
0x180018883  mov     rcx, [rsp+3A0h+var_348]; hKey
0x180018888  call    cs:__imp_RegCloseKey
0x18001888e  mov     rcx, [rdi+218h]; void *
0x180018895  lea     r8, [rsp+3A0h+var_340]; HKEY *
0x18001889a  lea     rdx, [rsp+3A0h+var_350]; HKEY *
0x18001889f  mov     [rsp+3A0h+var_350], r14
0x1800188a4  mov     [rsp+3A0h+var_340], r14
0x1800188a9  call    ?GetHKCUWow64ClassesCLSID@@YAXPEAXPEAPEAUHKEY__@@1@Z; GetHKCUWow64ClassesCLSID(void *,HKEY__ * *,HKEY__ * *)
0x1800188ae  mov     rdx, [rsp+3A0h+var_350]; HKEY
0x1800188b3  test    rdx, rdx
0x1800188b6  jz      short loc_1800188D2
0x1800188b8  mov     r8, rsi; unsigned __int16 *
0x1800188bb  mov     rcx, rdi; this
0x1800188be  call    ?CreateVolatilePerUserCLSID@CUmRdpDrv@@AEAAHPEAUHKEY__@@PEAG@Z; CUmRdpDrv::CreateVolatilePerUserCLSID(HKEY__ *,ushort *)
0x1800188c3  mov     rcx, [rsp+3A0h+var_350]; hKey
0x1800188c8  mov     ebx, eax
0x1800188ca  call    cs:__imp_RegCloseKey
0x1800188d0  jmp     short loc_1800188D5
0x1800188d2  mov     ebx, r14d
0x1800188d5  mov     rcx, [rsp+3A0h+var_340]
0x1800188da  mov     r15d, 1
0x1800188e0  test    rcx, rcx
0x1800188e3  jz      short loc_18001890E
0x1800188e5  test    ebx, ebx
0x1800188e7  jnz     short loc_180018903
0x1800188e9  mov     rdx, rcx; HKEY
0x1800188ec  mov     r8, rsi; unsigned __int16 *
0x1800188ef  mov     rcx, rdi; this
0x1800188f2  call    ?CreateVolatilePerUserCLSID@CUmRdpDrv@@AEAAHPEAUHKEY__@@PEAG@Z; CUmRdpDrv::CreateVolatilePerUserCLSID(HKEY__ *,ushort *)
0x1800188f7  mov     rcx, [rsp+3A0h+var_340]; hKey
0x1800188fc  mov     ebx, r14d
0x1800188ff  test    eax, eax
0x180018901  jz      short loc_180018906
0x180018903  mov     ebx, r15d
0x180018906  call    cs:__imp_RegCloseKey
0x18001890c  jmp     short loc_180018911
0x18001890e  mov     ebx, r14d
0x180018911  mov     rcx, gs:60h
0x18001891a  xor     edx, edx; dwFlags
0x18001891c  mov     r8, [rdi+238h]; lpMem
0x180018923  mov     rcx, [rcx+30h]; hHeap
0x180018927  call    cs:__imp_HeapFree
0x18001892d  mov     [rdi+238h], r14
0x180018934  xor     edx, edx; dwFlags
0x180018936  mov     rcx, gs:60h
0x18001893f  mov     r8, [rdi+3F8h]; lpMem
0x180018946  mov     rcx, [rcx+30h]; hHeap
0x18001894a  call    cs:__imp_HeapFree
0x180018950  mov     [rdi+3F8h], r14
0x180018957  xor     edx, edx; dwFlags
0x180018959  mov     rcx, gs:60h
0x180018962  mov     r8, [rdi+258h]; lpMem
0x180018969  mov     rcx, [rcx+30h]; hHeap
0x18001896d  call    cs:__imp_HeapFree
0x180018973  mov     [rdi+258h], r14
0x18001897a  test    ebx, ebx
0x18001897c  jz      loc_180018B01
0x180018982  lea     r8, [rsp+3A0h+var_350]; HKEY *
0x180018987  mov     [rsp+3A0h+var_350], r14
0x18001898c  mov     rcx, rdi; this
0x18001898f  mov     [rsp+3A0h+var_348], r14
0x180018994  call    ?_SHCreateSessionKey@CUmRdpDrv@@AEAAJKPEAPEAUHKEY__@@@Z; CUmRdpDrv::_SHCreateSessionKey(ulong,HKEY__ * *)
0x180018999  test    eax, eax
0x18001899b  js      loc_180018AFE
0x1800189a1  mov     r9, rsi
0x1800189a4  lea     r8, aMycomputerName; "MyComputer\\Namespace\\%s"
0x1800189ab  mov     edx, 104h; unsigned __int64
0x1800189b0  lea     rcx, [rbp+2A0h+SubKey]; unsigned __int16 *
0x1800189b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800189b9  test    eax, eax
0x1800189bb  js      short loc_180018A07
0x1800189bd  mov     rcx, [rsp+3A0h+var_350]; hKey
0x1800189c2  lea     rax, [rsp+3A0h+var_348]
0x1800189c7  mov     [rsp+3A0h+lpdwDisposition], r14; lpdwDisposition
0x1800189cc  lea     rdx, [rbp+2A0h+SubKey]; lpSubKey
0x1800189d0  mov     [rsp+3A0h+phkResult], rax; phkResult
0x1800189d5  xor     r9d, r9d; lpClass
0x1800189d8  mov     [rsp+3A0h+Arguments], r14; lpSecurityAttributes
0x1800189dd  xor     r8d, r8d; Reserved
0x1800189e0  mov     [rsp+3A0h+nSize], 20006h; samDesired
0x1800189e8  mov     dword ptr [rsp+3A0h+lpBuffer], r15d; dwOptions
0x1800189ed  call    cs:__imp_RegCreateKeyExW
0x1800189f3  test    eax, eax
0x1800189f5  jnz     short loc_180018A07
0x1800189f7  mov     rcx, [rsp+3A0h+var_348]; hKey
0x1800189fc  mov     ebx, r15d
0x1800189ff  call    cs:__imp_RegCloseKey
0x180018a05  jmp     short loc_180018A0A
0x180018a07  mov     ebx, r14d
0x180018a0a  mov     rcx, [rsp+3A0h+var_350]; hKey
0x180018a0f  call    cs:__imp_RegCloseKey
0x180018a15  test    ebx, ebx
0x180018a17  jz      loc_180018B01
0x180018a1d  mov     r9, rsi
0x180018a20  lea     r8, a20d04fe03aea10; "::{20D04FE0-3AEA-1069-A2D8-08002B30309D"...
0x180018a27  mov     edx, 104h; unsigned __int64
0x180018a2c  lea     rcx, [rbp+2A0h+SubKey]; unsigned __int16 *
0x180018a30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018a35  test    eax, eax
0x180018a37  js      loc_180018AFE
0x180018a3d  call    cs:__imp_RevertToSelf
0x180018a43  mov     rcx, [rdi]; this
0x180018a46  lea     rdx, [rsp+3A0h+var_350]; struct CUmRdpRpc **
0x180018a4b  mov     [rsp+3A0h+var_350], r14
0x180018a50  call    ?CreateUmRdpRpc@CUmRdpDr@@QEAAJAEAPEAVCUmRdpRpc@@@Z; CUmRdpDr::CreateUmRdpRpc(CUmRdpRpc * &)
0x180018a55  test    eax, eax
0x180018a57  jnz     short loc_180018A74
0x180018a59  mov     rcx, [rsp+3A0h+var_350]; this
0x180018a5e  lea     r9, [rbp+2A0h+SubKey]; unsigned __int16 *
0x180018a62  lea     edx, [rax+2]; int
0x180018a65  call    ?SHChangeNotify@CUmRdpRpc@@QEAAXJIPEAG0@Z; CUmRdpRpc::SHChangeNotify(long,uint,ushort *,ushort *)
0x180018a6a  mov     rcx, [rsp+3A0h+var_350]; this
0x180018a6f  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x180018a74  mov     rcx, [rdi+218h]; hToken
0x180018a7b  call    cs:__imp_ImpersonateLoggedOnUser
0x180018a81  mov     ebx, eax
0x180018a83  jmp     short loc_180018B01
0x180018a85  mov     rcx, gs:60h
0x180018a8e  xor     edx, edx; dwFlags
0x180018a90  mov     r8, [rdi+238h]; lpMem
0x180018a97  mov     ebx, r14d
0x180018a9a  mov     rcx, [rcx+30h]; hHeap
0x180018a9e  call    cs:__imp_HeapFree
0x180018aa4  mov     [rdi+238h], r14
0x180018aab  xor     edx, edx; dwFlags
0x180018aad  mov     rcx, gs:60h
0x180018ab6  mov     r8, [rdi+3F8h]; lpMem
0x180018abd  mov     rcx, [rcx+30h]; hHeap
0x180018ac1  call    cs:__imp_HeapFree
0x180018ac7  mov     [rdi+3F8h], r14
0x180018ace  jmp     short loc_180018B01
0x180018ad0  mov     rcx, gs:60h
0x180018ad9  xor     r14d, r14d
0x180018adc  mov     r8, [rdi+238h]; lpMem
0x180018ae3  xor     edx, edx; dwFlags
0x180018ae5  mov     ebx, r14d
0x180018ae8  mov     rcx, [rcx+30h]; hHeap
0x180018aec  call    cs:__imp_HeapFree
0x180018af2  mov     [rdi+238h], r14
0x180018af9  jmp     short loc_180018B01
0x180018afb  xor     r14d, r14d
0x180018afe  mov     ebx, r14d
0x180018b01  test    r12d, r12d
0x180018b04  js      short loc_180018B0C
0x180018b06  call    cs:__imp_CoUninitialize
0x180018b0c  mov     [r13+48h], rsi
0x180018b10  mov     eax, ebx
0x180018b12  mov     rcx, [rbp+2A0h+var_40]
0x180018b19  xor     rcx, rsp; StackCookie
0x180018b1c  call    __security_check_cookie
0x180018b21  mov     rbx, [rsp+3A0h+arg_10]
0x180018b29  add     rsp, 370h
0x180018b30  pop     r15
  ... truncated ...
```
