# StorageService::GetStorageDeviceInfo(void *,_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DEVICE_INFO *)

- ea: `0x180024638`
- end: `0x180024abb`
- name: `?GetStorageDeviceInfo@StorageService@@QEAAJPEAXW4_STORAGE_DEVICE_TYPE@@KPEAU_STORAGE_DEVICE_INFO@@@Z`
- size: `1155`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned int, __int64)`
- caller_count: `10`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024ac4`
- `0x180032088`
- `0x18003253c`
- `0x180037570`
- `0x1800388b4`
- `0x180038e54`
- `0x180039124`
- `0x1800393f0`
- `0x180039ff8`
- `0x18003a254`

## callees

- `0x18000d030`
- `0x18000dda4`
- `0x18000ddb0`
- `0x18000f338`
- `0x180012c9c`
- `0x180018d54`
- `0x18001fe50`
- `0x18001feb8`
- `0x180020334`
- `0x180020d2c`
- `0x180022574`
- `0x180022de0`
- `0x180024638`
- `0x180025b08`
- `0x18002cca8`
- `0x18002ccd8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002487d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002487d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800248d4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002492d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800248d4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18002492d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024813`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024813`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024a5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024a5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024a88`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024865`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024a52`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024865`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024a52`
- `RPCRT4!RpcImpersonateClient` at `0x18002483e`
- `RPCRT4!RpcImpersonateClient` at `0x1800249b6`
- `RPCRT4!RpcImpersonateClient` at `0x18002483e`
- `RPCRT4!RpcImpersonateClient` at `0x1800249b6`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFileInfoW` at `0x18002485c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFileInfoW` at `0x18002485c`

## string_xrefs

- `0x18002480c`: `shell32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall StorageService::GetStorageDeviceInfo(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  __int64 v6; // rbx
  int ActiveDeviceInstance; // r12d
  __int64 v9; // rdi
  _OWORD *v10; // r9
  _OWORD *v11; // rax
  __int64 v12; // rcx
  HMODULE Library; // r13
  DWORD_PTR v14; // rbx
  wchar_t *v15; // rax
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rdi
  wchar_t *v18; // r15
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rbx
  wchar_t *i; // rdi
  unsigned __int16 v22; // r8
  unsigned __int16 v24[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v25; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v28; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v29[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v30[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[3]; // [rsp+88h] [rbp-78h] BYREF
  SHFILEINFOW psfi; // [rsp+A0h] [rbp-60h] BYREF

  v6 = (int)a3;
  *(_DWORD *)v24 = a4;
  ActiveDeviceInstance = StorageService::CheckDeviceParameters(a1, a3, a4, 0);
  if ( ActiveDeviceInstance >= 0 )
  {
    if ( *(_DWORD *)a5 >= 0x458u )
    {
      EnterCriticalSection(&stru_1800C10F8);
      ActiveDeviceInstance = StorageService::GetActiveDeviceInstance(&g_StorageService, (unsigned int)v6, a4, v24);
      if ( ActiveDeviceInstance >= 0 )
      {
        v9 = *(unsigned int *)v24;
        if ( (unsigned int)StorageService::CheckPresenceState(
                             &g_StorageService,
                             (unsigned int)v6,
                             *(unsigned int *)v24,
                             0)
          && !*(_DWORD *)(*((_QWORD *)&g_StorageService + v6 + 5) + 1112 * v9 + 1100) )
        {
          StorageService::DetermineFormatState(&g_StorageService, (unsigned int)v6, (unsigned int)v9);
        }
        v10 = (_OWORD *)a5;
        v11 = (_OWORD *)(1112 * v9 + *((_QWORD *)&g_StorageService + v6 + 5));
        v12 = 8;
        do
        {
          *v10 = *v11;
          v10[1] = v11[1];
          v10[2] = v11[2];
          v10[3] = v11[3];
          v10[4] = v11[4];
          v10[5] = v11[5];
          v10[6] = v11[6];
          v10[7] = v11[7];
          v10 += 8;
          v11 += 8;
          --v12;
        }
        while ( v12 );
        *v10 = *v11;
        v10[1] = v11[1];
        v10[2] = v11[2];
        v10[3] = v11[3];
        v10[4] = v11[4];
        *((_QWORD *)v10 + 10) = *((_QWORD *)v11 + 10);
        if ( !(unsigned int)StorageService::CheckPresenceState(&g_StorageService, (unsigned int)v6, (unsigned int)v9, 2) )
        {
          *(_DWORD *)(a5 + 540) = *((_DWORD *)&g_StorageService + 190 * v6 + 156);
          *(_DWORD *)(a5 + 544) = *((_DWORD *)&g_StorageService + 190 * v6 + 157);
        }
        *(_WORD *)(a5 + 576) = 0;
        if ( a2 )
        {
          Library = LoadLibraryExW(L"shell32.dll", 0, 0x22u);
          memset_0(&psfi, 0, sizeof(psfi));
          if ( (unsigned __int8)IsSHGetFileInfoWPresent() )
          {
            RpcImpersonateClient(0);
            v14 = SHGetFileInfoW((LPCWSTR)(a5 + 4), 0x80u, &psfi, 0x2B8u, 0x200u);
            RevertToSelf();
            if ( v14 )
            {
              v15 = wcsrchr(psfi.szDisplayName, 0x28u);
              v25 = 0;
              v26 = 0;
              v27 = 0;
              if ( v15 )
                *v15 = 0;
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                &v25,
                psfi.szDisplayName,
                -1);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&v25);
              v16 = 0;
              v17 = v26;
              if ( v26 )
              {
                v18 = v25;
                do
                {
                  if ( !wcschr(&Str, v18[v16]) )
                    break;
                  ++v16;
                }
                while ( v16 < v17 );
                if ( v16 )
                {
                  v19 = v17 - v16;
                  memmove_0(v18, &v18[v16], 2 * v19 + 2);
                  v26 = v19;
                }
              }
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&v25);
              v20 = v26;
              for ( i = v25; v20; --v20 )
              {
                if ( !wcschr(&Str, i[v20 - 1]) )
                  break;
              }
              if ( v20 != v26 )
              {
                i[v20] = 0;
                v26 = v20;
              }
              StringCchCopyW((wchar_t *)(a5 + 576), 0x104u, i);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v25);
            }
          }
          if ( Library )
          {
            memset(v31, 0, sizeof(v31));
            memset(v30, 0, sizeof(v30));
            memset(v29, 0, sizeof(v29));
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              v29,
              &dword_180094D8C,
              -1);
            RpcImpersonateClient(0);
            v28 = 0;
            v24[0] = 0;
            if ( Windows::Internal::ResourceString::FindAndSize(
                   Library,
                   0x2408u,
                   v22,
                   (const unsigned __int16 **)&v28,
                   v24)
              && (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                        v31,
                        v28,
                        v24[0]) >= 0
              && (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
                        v30,
                        v31[0],
                        a5 + 576,
                        *(unsigned __int16 *)(a5 + 4)) >= 0
              && (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(
                        v29,
                        v30) >= 0 )
            {
              if ( v29[0] )
                StringCchCopyW((wchar_t *)(a5 + 576), 0x104u, v29[0]);
              else
                *(_WORD *)(a5 + 576) = 0;
            }
            RevertToSelf();
            FreeLibrary(Library);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v29);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v30);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v31);
          }
        }
      }
      LeaveCriticalSection(&stru_1800C10F8);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)ActiveDeviceInstance;
}

```

## disassembly

```asm
0x180024638  mov     [rsp-8+arg_0], rbx
0x18002463d  push    rbp
0x18002463e  push    rsi
0x18002463f  push    rdi
0x180024640  push    r12
0x180024642  push    r13
0x180024644  push    r14
0x180024646  push    r15
0x180024648  lea     rbp, [rsp-270h]
0x180024650  sub     rsp, 370h
0x180024657  mov     rax, cs:__security_cookie
0x18002465e  xor     rax, rsp
0x180024661  mov     [rbp+2A0h+var_40], rax
0x180024668  mov     edi, r9d
0x18002466b  movsxd  rbx, r8d
0x18002466e  mov     r15, rdx
0x180024671  mov     r14, [rbp+2A0h+arg_20]
0x180024678  mov     dword ptr [rsp+3A0h+var_370], r9d
0x18002467d  xor     r9d, r9d
0x180024680  mov     r8d, edi
0x180024683  mov     edx, ebx
0x180024685  call    ?CheckDeviceParameters@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::CheckDeviceParameters(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x18002468a  mov     r12d, eax
0x18002468d  test    eax, eax
0x18002468f  js      loc_180024A8E
0x180024695  cmp     dword ptr [r14], 458h
0x18002469c  jnb     short loc_1800246A9
0x18002469e  mov     r12d, 80070057h
0x1800246a4  jmp     loc_180024A8E
0x1800246a9  lea     rcx, stru_1800C10F8; lpCriticalSection
0x1800246b0  call    cs:__imp_EnterCriticalSection
0x1800246b6  lea     r9, [rsp+3A0h+var_370]
0x1800246bb  mov     r8d, edi
0x1800246be  mov     edx, ebx
0x1800246c0  lea     r13, ?g_StorageService@@3VStorageService@@A; StorageService g_StorageService
0x1800246c7  mov     rcx, r13
0x1800246ca  call    ?GetActiveDeviceInstance@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAK@Z; StorageService::GetActiveDeviceInstance(_STORAGE_DEVICE_TYPE,ulong,ulong *)
0x1800246cf  mov     r12d, eax
0x1800246d2  test    eax, eax
0x1800246d4  js      loc_180024A81
0x1800246da  xor     r9d, r9d
0x1800246dd  mov     edi, dword ptr [rsp+3A0h+var_370]
0x1800246e1  mov     r8d, edi
0x1800246e4  mov     edx, ebx
0x1800246e6  mov     rcx, r13
0x1800246e9  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x1800246ee  test    eax, eax
0x1800246f0  jz      short loc_180024715
0x1800246f2  imul    rcx, rdi, 458h
0x1800246f9  mov     rax, [r13+rbx*8+28h]
0x1800246fe  cmp     dword ptr [rax+rcx+44Ch], 0
0x180024706  jnz     short loc_180024715
0x180024708  mov     r8d, edi
0x18002470b  mov     edx, ebx
0x18002470d  mov     rcx, r13
0x180024710  call    ?DetermineFormatState@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::DetermineFormatState(_STORAGE_DEVICE_TYPE,ulong)
0x180024715  mov     rsi, rbx
0x180024718  imul    rcx, rdi, 458h
0x18002471f  mov     rax, [r13+rbx*8+28h]
0x180024724  mov     r9, r14
0x180024727  add     rax, rcx
0x18002472a  mov     ecx, 8
0x18002472f  lea     edx, [rcx+78h]
0x180024732  movups  xmm0, xmmword ptr [rax]
0x180024735  movups  xmmword ptr [r9], xmm0
0x180024739  movups  xmm1, xmmword ptr [rax+10h]
0x18002473d  movups  xmmword ptr [r9+10h], xmm1
0x180024742  movups  xmm0, xmmword ptr [rax+20h]
0x180024746  movups  xmmword ptr [r9+20h], xmm0
0x18002474b  movups  xmm1, xmmword ptr [rax+30h]
0x18002474f  movups  xmmword ptr [r9+30h], xmm1
0x180024754  movups  xmm0, xmmword ptr [rax+40h]
0x180024758  movups  xmmword ptr [r9+40h], xmm0
0x18002475d  movups  xmm1, xmmword ptr [rax+50h]
0x180024761  movups  xmmword ptr [r9+50h], xmm1
0x180024766  movups  xmm0, xmmword ptr [rax+60h]
0x18002476a  movups  xmmword ptr [r9+60h], xmm0
0x18002476f  movups  xmm1, xmmword ptr [rax+70h]
0x180024773  movups  xmmword ptr [r9+70h], xmm1
0x180024778  add     r9, rdx
0x18002477b  add     rax, rdx
0x18002477e  sub     rcx, 1
0x180024782  jnz     short loc_180024732
0x180024784  movups  xmm0, xmmword ptr [rax]
0x180024787  movups  xmmword ptr [r9], xmm0
0x18002478b  movups  xmm1, xmmword ptr [rax+10h]
0x18002478f  movups  xmmword ptr [r9+10h], xmm1
0x180024794  movups  xmm0, xmmword ptr [rax+20h]
0x180024798  movups  xmmword ptr [r9+20h], xmm0
0x18002479d  movups  xmm1, xmmword ptr [rax+30h]
0x1800247a1  movups  xmmword ptr [r9+30h], xmm1
0x1800247a6  movups  xmm0, xmmword ptr [rax+40h]
0x1800247aa  movups  xmmword ptr [r9+40h], xmm0
0x1800247af  mov     rax, [rax+50h]
0x1800247b3  mov     [r9+50h], rax
0x1800247b7  lea     r9d, [rcx+2]
0x1800247bb  mov     r8d, edi
0x1800247be  mov     edx, ebx
0x1800247c0  mov     rcx, r13
0x1800247c3  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x1800247c8  xor     edi, edi
0x1800247ca  test    eax, eax
0x1800247cc  jnz     short loc_1800247F3
0x1800247ce  imul    rcx, rsi, 2F8h
0x1800247d5  mov     eax, [rcx+r13+270h]
0x1800247dd  mov     [r14+21Ch], eax
0x1800247e4  mov     eax, [rcx+r13+274h]
0x1800247ec  mov     [r14+220h], eax
0x1800247f3  lea     rsi, [r14+240h]
0x1800247fa  mov     [rsi], di
0x1800247fd  test    r15, r15
0x180024800  jz      loc_180024A81
0x180024806  xor     edx, edx; hFile
0x180024808  lea     r8d, [rdx+22h]; dwFlags
0x18002480c  lea     rcx, LibFileName; "shell32.dll"
0x180024813  call    cs:__imp_LoadLibraryExW
0x180024819  mov     r13, rax
0x18002481c  mov     ebx, 2B8h
0x180024821  mov     r8d, ebx; Size
0x180024824  xor     edx, edx; Val
0x180024826  lea     rcx, [rbp+2A0h+psfi]; void *
0x18002482a  call    memset_0
0x18002482f  call    IsSHGetFileInfoWPresent
0x180024834  test    al, al
0x180024836  jz      loc_18002496D
0x18002483c  xor     ecx, ecx; BindingHandle
0x18002483e  call    cs:__imp_RpcImpersonateClient
0x180024844  lea     rcx, [r14+4]; pszPath
0x180024848  mov     [rsp+3A0h+uFlags], 200h; uFlags
0x180024850  mov     r9d, ebx; cbFileInfo
0x180024853  lea     r8, [rbp+2A0h+psfi]; psfi
0x180024857  mov     edx, 80h; dwFileAttributes
0x18002485c  call    cs:__imp_SHGetFileInfoW
0x180024862  mov     rbx, rax
0x180024865  call    cs:__imp_RevertToSelf
0x18002486b  test    rbx, rbx
0x18002486e  jz      loc_18002496D
0x180024874  mov     edx, 28h ; '('; Ch
0x180024879  lea     rcx, [rbp+2A0h+psfi.szDisplayName]; Str
0x18002487d  call    cs:__imp_wcsrchr
0x180024883  mov     [rsp+3A0h+var_368], rdi
0x180024888  mov     [rsp+3A0h+var_360], rdi
0x18002488d  mov     [rsp+3A0h+var_358], rdi
0x180024892  test    rax, rax
0x180024895  jz      short loc_18002489A
0x180024897  mov     [rax], di
0x18002489a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002489e  lea     rdx, [rbp+2A0h+psfi.szDisplayName]
0x1800248a2  lea     rcx, [rsp+3A0h+var_368]
0x1800248a7  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800248ac  lea     rcx, [rsp+3A0h+var_368]
0x1800248b1  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800248b6  mov     rbx, rdi
0x1800248b9  mov     rdi, [rsp+3A0h+var_360]
0x1800248be  test    rdi, rdi
0x1800248c1  jz      short loc_180024908
0x1800248c3  mov     r15, [rsp+3A0h+var_368]
0x1800248c8  movzx   edx, word ptr [r15+rbx*2]; Ch
0x1800248cd  lea     rcx, Str; Str
0x1800248d4  call    cs:__imp_wcschr
0x1800248da  test    rax, rax
0x1800248dd  jz      short loc_1800248E7
0x1800248df  inc     rbx
0x1800248e2  cmp     rbx, rdi
0x1800248e5  jb      short loc_1800248C8
0x1800248e7  test    rbx, rbx
0x1800248ea  jz      short loc_180024908
0x1800248ec  sub     rdi, rbx
0x1800248ef  lea     r8, ds:2[rdi*2]; Size
0x1800248f7  lea     rdx, [r15+rbx*2]; Src
0x1800248fb  mov     rcx, r15; void *
0x1800248fe  call    memmove_0
0x180024903  mov     [rsp+3A0h+var_360], rdi
0x180024908  lea     rcx, [rsp+3A0h+var_368]
0x18002490d  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180024912  mov     rbx, [rsp+3A0h+var_360]
0x180024917  mov     rdi, [rsp+3A0h+var_368]
0x18002491c  test    rbx, rbx
0x18002491f  jz      short loc_18002493E
0x180024921  movzx   edx, word ptr [rdi+rbx*2-2]; Ch
0x180024926  lea     rcx, Str; Str
0x18002492d  call    cs:__imp_wcschr
0x180024933  test    rax, rax
0x180024936  jz      short loc_18002493E
0x180024938  sub     rbx, 1
0x18002493c  jnz     short loc_180024921
0x18002493e  cmp     rbx, [rsp+3A0h+var_360]
0x180024943  jz      short loc_180024950
0x180024945  xor     eax, eax
0x180024947  mov     [rdi+rbx*2], ax
0x18002494b  mov     [rsp+3A0h+var_360], rbx
0x180024950  mov     r8, rdi; wchar_t *
0x180024953  mov     edx, 104h; unsigned __int64
0x180024958  mov     rcx, rsi; wchar_t *
0x18002495b  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180024960  nop
0x180024961  lea     rcx, [rsp+3A0h+var_368]
0x180024966  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002496b  xor     edi, edi
0x18002496d  test    r13, r13
0x180024970  jz      loc_180024A81
0x180024976  mov     [rbp+2A0h+var_318], rdi
0x18002497a  mov     [rbp+2A0h+var_310], rdi
0x18002497e  mov     [rbp+2A0h+var_308], rdi
0x180024982  mov     [rsp+3A0h+var_330], rdi
0x180024987  mov     [rsp+3A0h+var_328], rdi
0x18002498c  mov     [rbp+2A0h+var_320], rdi
0x180024990  mov     [rsp+3A0h+var_348], rdi
0x180024995  mov     [rsp+3A0h+var_340], rdi
0x18002499a  mov     [rsp+3A0h+var_338], rdi
0x18002499f  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800249a3  lea     rdx, dword_180094D8C
0x1800249aa  lea     rcx, [rsp+3A0h+var_348]
0x1800249af  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800249b4  xor     ecx, ecx; BindingHandle
0x1800249b6  call    cs:__imp_RpcImpersonateClient
0x1800249bc  mov     [rsp+3A0h+var_350], rdi
0x1800249c1  mov     [rsp+3A0h+var_370], di
0x1800249c6  lea     rax, [rsp+3A0h+var_370]
0x1800249cb  mov     qword ptr [rsp+3A0h+uFlags], rax; unsigned __int16 *
0x1800249d0  lea     r9, [rsp+3A0h+var_350]; unsigned __int16 **
0x1800249d5  mov     edx, 2408h; unsigned int
0x1800249da  mov     rcx, r13; hModule
0x1800249dd  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x1800249e2  test    al, al
0x1800249e4  jz      short loc_180024A52
0x1800249e6  movzx   r8d, [rsp+3A0h+var_370]
0x1800249ec  mov     rdx, [rsp+3A0h+var_350]
0x1800249f1  lea     rcx, [rbp+2A0h+var_318]
0x1800249f5  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800249fa  test    eax, eax
0x1800249fc  js      short loc_180024A52
0x1800249fe  movzx   r9d, word ptr [r14+4]
0x180024a03  mov     r8, rsi
0x180024a06  mov     rdx, [rbp+2A0h+var_318]
0x180024a0a  lea     rcx, [rsp+3A0h+var_330]
0x180024a0f  call    ?InitializeMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeMessage(ushort const *,...)
0x180024a14  test    eax, eax
0x180024a16  js      short loc_180024A52
0x180024a18  lea     rdx, [rsp+3A0h+var_330]
0x180024a1d  lea     rcx, [rsp+3A0h+var_348]
0x180024a22  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x180024a27  test    eax, eax
0x180024a29  js      short loc_180024A52
0x180024a2b  mov     rax, [rsp+3A0h+var_348]
0x180024a30  test    rax, rax
0x180024a33  jz      short loc_180024A4F
0x180024a35  lea     r8, word_180092AF0
0x180024a3c  cmovnz  r8, rax; wchar_t *
0x180024a40  mov     edx, 104h; unsigned __int64
0x180024a45  mov     rcx, rsi; wchar_t *
0x180024a48  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180024a4d  jmp     short loc_180024A52
0x180024a4f  mov     [rsi], di
0x180024a52  call    cs:__imp_RevertToSelf
0x180024a58  mov     rcx, r13; hLibModule
0x180024a5b  call    cs:__imp_FreeLibrary
0x180024a61  nop
0x180024a62  lea     rcx, [rsp+3A0h+var_348]
0x180024a67  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180024a6c  nop
0x180024a6d  lea     rcx, [rsp+3A0h+var_330]
0x180024a72  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180024a77  nop
0x180024a78  lea     rcx, [rbp+2A0h+var_318]
0x180024a7c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180024a81  lea     rcx, stru_1800C10F8; lpCriticalSection
0x180024a88  call    cs:__imp_LeaveCriticalSection
0x180024a8e  mov     eax, r12d
0x180024a91  mov     rcx, [rbp+2A0h+var_40]
0x180024a98  xor     rcx, rsp; StackCookie
0x180024a9b  call    __security_check_cookie
0x180024aa0  mov     rbx, [rsp+3A0h+arg_0]
0x180024aa8  add     rsp, 370h
0x180024aaf  pop     r15
0x180024ab1  pop     r14
0x180024ab3  pop     r13
0x180024ab5  pop     r12
0x180024ab7  pop     rdi
0x180024ab8  pop     rsi
0x180024ab9  pop     rbp
0x180024aba  retn
```
