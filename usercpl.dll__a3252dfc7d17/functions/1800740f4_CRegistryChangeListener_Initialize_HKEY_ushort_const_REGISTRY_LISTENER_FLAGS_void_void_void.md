# CRegistryChangeListener::_Initialize(HKEY__ *,ushort const *,REGISTRY_LISTENER_FLAGS,void (*)(void *),void *)

- ea: `0x1800740f4`
- end: `0x1800742d2`
- name: `?_Initialize@CRegistryChangeListener@@QEAAJPEAUHKEY__@@PEBGW4REGISTRY_LISTENER_FLAGS@@P6AXPEAX@Z3@Z`
- size: `478`
- prototype: `__int64 __fastcall(__int64, void *, const WCHAR *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180073e80`

## callees

- `0x1800034b7`
- `0x1800740f4`
- `0x1800742d8`
- `0x180078010`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007416e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007416e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007425e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007425e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074280`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800741a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800741a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074142`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180074142`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007421c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007421c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180074238`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180074238`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180074256`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180074256`

## pseudocode

```c
__int64 __fastcall CRegistryChangeListener::_Initialize(
        __int64 a1,
        void *a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  LSTATUS v8; // eax
  int v9; // ebx
  unsigned int *v10; // rsi
  HANDLE EventW_0; // rax
  PTP_WORK ThreadpoolWork; // rax
  PTP_WAIT ThreadpoolWait; // rax
  signed int LastError; // eax
  signed int v15; // eax
  LPVOID ppv; // [rsp+68h] [rbp+10h] BYREF

  ppv = a2;
  *(_DWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 56) = UserTile::s_UserTileChangeCallback;
  *(_QWORD *)(a1 + 72) = a6;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, (PHKEY)(a1 + 32));
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    if ( !a3 || (v9 = SHStrDupW(a3, (LPWSTR *)(a1 + 80)), v9 >= 0) )
    {
      ppv = 0;
      v9 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
      if ( v9 >= 0 )
      {
        v10 = (unsigned int *)(a1 + 48);
        v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, __int64))(*(_QWORD *)ppv + 24LL))(
               ppv,
               a1,
               &IID_IOleCommandTarget,
               a1 + 48);
        if ( v9 >= 0 )
        {
          EventW_0 = CreateEventW_0(0, 0, 0, 0);
          *(_QWORD *)(a1 + 24) = EventW_0;
          if ( EventW_0 )
          {
            v9 = CRegistryChangeListener::_RestoreChangeCallback((CRegistryChangeListener *)a1);
            if ( v9 >= 0 )
            {
              ThreadpoolWork = CreateThreadpoolWork(CRegistryChangeListener::s_CleanupCB, (PVOID)a1, 0);
              *(_QWORD *)(a1 + 64) = ThreadpoolWork;
              if ( ThreadpoolWork
                && (ThreadpoolWait = CreateThreadpoolWait(
                                       CRegistryChangeListener::s_RegistryChangeCB,
                                       (PVOID)(int)*v10,
                                       0),
                    (*(_QWORD *)(a1 + 40) = ThreadpoolWait) != 0) )
              {
                _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
                SetThreadpoolWait(*(PTP_WAIT *)(a1 + 40), *(HANDLE *)(a1 + 24), 0);
              }
              else
              {
                LastError = GetLastError();
                v9 = LastError;
                if ( LastError > 0 )
                  v9 = (unsigned __int16)LastError | 0x80070000;
                if ( v9 >= 0 )
                  v9 = -2147467259;
              }
              if ( v9 >= 0 )
                goto LABEL_24;
            }
          }
          else
          {
            v15 = GetLastError();
            v9 = v15;
            if ( v15 > 0 )
              v9 = (unsigned __int16)v15 | 0x80070000;
            if ( v9 >= 0 )
              v9 = -2147467259;
          }
          (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, *v10);
          *v10 = 0;
        }
LABEL_24:
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800740f4  mov     [rsp+ppv], rdx
0x1800740f9  push    rbx
0x1800740fa  push    rsi
0x1800740fb  push    rdi
0x1800740fc  push    r14
0x1800740fe  sub     rsp, 38h
0x180074102  mov     rsi, r8
0x180074105  mov     dword ptr [rcx+58h], 0
0x18007410c  lea     rax, ?s_UserTileChangeCallback@UserTile@@CAXPEAX@Z; UserTile::s_UserTileChangeCallback(void *)
0x180074113  mov     rdi, rcx
0x180074116  mov     [rcx+38h], rax
0x18007411a  mov     r9d, 20019h; samDesired
0x180074120  mov     rax, [rsp+58h+arg_28]
0x180074128  xor     r8d, r8d; ulOptions
0x18007412b  mov     [rcx+48h], rax
0x18007412f  mov     rdx, rsi; lpSubKey
0x180074132  lea     rax, [rcx+20h]
0x180074136  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007413d  mov     [rsp+58h+phkResult], rax; phkResult
0x180074142  call    cs:__imp_RegOpenKeyExW
0x180074148  mov     ebx, eax
0x18007414a  mov     r14d, 80070000h
0x180074150  test    eax, eax
0x180074152  jle     short loc_18007415A
0x180074154  movzx   ebx, ax
0x180074157  or      ebx, r14d
0x18007415a  test    ebx, ebx
0x18007415c  js      loc_1800742C6
0x180074162  test    rsi, rsi
0x180074165  jz      short loc_18007417E
0x180074167  lea     rdx, [rdi+50h]; ppwsz
0x18007416b  mov     rcx, rsi; psz
0x18007416e  call    cs:__imp_SHStrDupW
0x180074174  mov     ebx, eax
0x180074176  test    eax, eax
0x180074178  js      loc_1800742C6
0x18007417e  xor     edx, edx; pUnkOuter
0x180074180  mov     [rsp+58h+ppv], 0
0x180074189  lea     rax, [rsp+58h+ppv]
0x18007418e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180074195  mov     [rsp+58h+phkResult], rax; ppv
0x18007419a  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800741a1  lea     r8d, [rdx+1]; dwClsContext
0x1800741a5  call    cs:__imp_CoCreateInstance
0x1800741ab  mov     ebx, eax
0x1800741ad  test    eax, eax
0x1800741af  js      loc_1800742C6
0x1800741b5  mov     rcx, [rsp+58h+ppv]
0x1800741ba  lea     rsi, [rdi+30h]
0x1800741be  mov     r9, rsi
0x1800741c1  lea     r8, IID_IOleCommandTarget
0x1800741c8  mov     rdx, rdi
0x1800741cb  mov     rax, [rcx]
0x1800741ce  mov     rax, [rax+18h]
0x1800741d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800741d7  mov     ebx, eax
0x1800741d9  test    eax, eax
0x1800741db  js      loc_1800742B5
0x1800741e1  xor     r9d, r9d; lpName
0x1800741e4  xor     r8d, r8d; bInitialState
0x1800741e7  xor     edx, edx; bManualReset
0x1800741e9  xor     ecx, ecx; lpEventAttributes
0x1800741eb  call    CreateEventW_0
0x1800741f0  mov     [rdi+18h], rax
0x1800741f4  test    rax, rax
0x1800741f7  jz      loc_180074280
0x1800741fd  mov     rcx, rdi; this
0x180074200  call    ?_RestoreChangeCallback@CRegistryChangeListener@@AEAAJXZ; CRegistryChangeListener::_RestoreChangeCallback(void)
0x180074205  mov     ebx, eax
0x180074207  test    eax, eax
0x180074209  js      loc_18007429C
0x18007420f  xor     r8d, r8d; pcbe
0x180074212  lea     rcx, ?s_CleanupCB@CRegistryChangeListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180074219  mov     rdx, rdi; pv
0x18007421c  call    cs:__imp_CreateThreadpoolWork
0x180074222  mov     [rdi+40h], rax
0x180074226  test    rax, rax
0x180074229  jz      short loc_18007425E
0x18007422b  movsxd  rdx, dword ptr [rsi]; pv
0x18007422e  lea     rcx, ?s_RegistryChangeCB@CRegistryChangeListener@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180074235  xor     r8d, r8d; pcbe
0x180074238  call    cs:__imp_CreateThreadpoolWait
0x18007423e  mov     [rdi+28h], rax
0x180074242  test    rax, rax
0x180074245  jz      short loc_18007425E
0x180074247  lock inc dword ptr [rdi+10h]
0x18007424b  mov     rdx, [rdi+18h]; h
0x18007424f  xor     r8d, r8d; pftTimeout
0x180074252  mov     rcx, [rdi+28h]; pwa
0x180074256  call    cs:__imp_SetThreadpoolWait
0x18007425c  jmp     short loc_18007427A
0x18007425e  call    cs:__imp_GetLastError
0x180074264  mov     ebx, eax
0x180074266  test    eax, eax
0x180074268  jle     short loc_180074270
0x18007426a  movzx   ebx, ax
0x18007426d  or      ebx, r14d
0x180074270  test    ebx, ebx
0x180074272  mov     eax, 80004005h
0x180074277  cmovns  ebx, eax
0x18007427a  test    ebx, ebx
0x18007427c  jns     short loc_1800742B5
0x18007427e  jmp     short loc_18007429C
0x180074280  call    cs:__imp_GetLastError
0x180074286  mov     ebx, eax
0x180074288  test    eax, eax
0x18007428a  jle     short loc_180074292
0x18007428c  movzx   ebx, ax
0x18007428f  or      ebx, r14d
0x180074292  test    ebx, ebx
0x180074294  mov     eax, 80004005h
0x180074299  cmovns  ebx, eax
0x18007429c  mov     rcx, [rsp+58h+ppv]
0x1800742a1  mov     edx, [rsi]
0x1800742a3  mov     rax, [rcx]
0x1800742a6  mov     rax, [rax+20h]
0x1800742aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742af  mov     dword ptr [rsi], 0
0x1800742b5  mov     rcx, [rsp+58h+ppv]
0x1800742ba  mov     rax, [rcx]
0x1800742bd  mov     rax, [rax+10h]
0x1800742c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800742c6  mov     eax, ebx
0x1800742c8  add     rsp, 38h
0x1800742cc  pop     r14
0x1800742ce  pop     rdi
0x1800742cf  pop     rsi
0x1800742d0  pop     rbx
0x1800742d1  retn
```
