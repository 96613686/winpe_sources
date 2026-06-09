# CUmRdpDrv::DeleteDriveFolder(tagDRDEVLSTENTRY *)

- ea: `0x180018b44`
- end: `0x180018d7c`
- name: `?DeleteDriveFolder@CUmRdpDrv@@AEAAHPEAUtagDRDEVLSTENTRY@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(CUmRdpDrv *__hidden this, struct tagDRDEVLSTENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001830c`

## callees

- `0x18000a01c`
- `0x18000a41c`
- `0x18001294c`
- `0x180018b44`
- `0x180018d84`
- `0x180018e74`
- `0x18001910c`
- `0x180019b98`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018cd3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018cd3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180018d16`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180018d16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018d34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018d34`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018bf1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180018bf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018bfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018cb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018bfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018cb2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018d4e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018d4e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180018b9b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180018b9b`
- `SHLWAPI!SHDeleteKeyW` at `0x180018c25`
- `SHLWAPI!SHDeleteKeyW` at `0x180018c43`
- `SHLWAPI!SHDeleteKeyW` at `0x180018c89`
- `SHLWAPI!SHDeleteKeyW` at `0x180018ca7`
- `SHLWAPI!SHDeleteKeyW` at `0x180018c25`
- `SHLWAPI!SHDeleteKeyW` at `0x180018c43`
- `SHLWAPI!SHDeleteKeyW` at `0x180018c89`
- `SHLWAPI!SHDeleteKeyW` at `0x180018ca7`

## string_xrefs

- `0x180018bca`: `MyComputer\Namespace\%s`

## pseudocode

```c
__int64 __fastcall CUmRdpDrv::DeleteDriveFolder(void **this, struct tagDRDEVLSTENTRY *a2)
{
  unsigned int v4; // ebx
  HRESULT v5; // eax
  unsigned int v6; // edx
  WCHAR *v7; // rdi
  int v8; // r14d
  void *v9; // rcx
  CUmRdpDr *v10; // rcx
  unsigned int v11; // r8d
  unsigned __int16 *v13; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hkey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v16; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v17; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v18; // [rsp+50h] [rbp-B0h] BYREF
  CUmRdpRpc *v19; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  hkey = 0;
  v4 = 1;
  v16 = 0;
  v5 = CoInitializeEx(0, 2u);
  v7 = (WCHAR *)*((_QWORD *)a2 + 9);
  v8 = v5;
  if ( v7 )
  {
    if ( CUmRdpDrv::_SHCreateSessionKey((CUmRdpDrv *)this, v6, &hKey) >= 0 )
    {
      if ( (int)StringCchPrintfW(SubKey, 0x104u, L"MyComputer\\Namespace\\%s", v7) >= 0 )
        RegDeleteKeyExW(hKey, SubKey, 0, 0);
      RegCloseKey(hKey);
    }
    GetHKCUClassesCLSID(this[67], &hkey, &v16);
    if ( hkey )
    {
      SHDeleteKeyW(hkey, v7);
      RegCloseKey(hkey);
    }
    if ( v16 )
    {
      SHDeleteKeyW(v16, v7);
      RegCloseKey(v16);
    }
    v9 = this[67];
    v17 = 0;
    v18 = 0;
    GetHKCUWow64ClassesCLSID(v9, &v17, &v18);
    if ( v17 )
    {
      SHDeleteKeyW(v17, v7);
      RegCloseKey(v17);
    }
    if ( v18 )
    {
      SHDeleteKeyW(v18, v7);
      RegCloseKey(v18);
    }
    if ( (int)StringCchPrintfW(SubKey, 0x104u, L"::{20D04FE0-3AEA-1069-A2D8-08002B30309D}\\::%s", v7) < 0 )
    {
      v4 = 0;
    }
    else
    {
      RevertToSelf();
      v10 = (CUmRdpDr *)*this;
      v19 = 0;
      if ( !(unsigned int)CUmRdpDr::CreateUmRdpRpc(v10, &v19) )
      {
        CUmRdpRpc::SHChangeNotify(v19, 4, v11, SubKey, v13);
        CUmRdpRpc::Release(v19);
      }
      v4 = ImpersonateLoggedOnUser(this[67]);
    }
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v7);
    *((_QWORD *)a2 + 9) = 0;
  }
  *((_DWORD *)this + 2) = 0;
  if ( v8 >= 0 )
    CoUninitialize();
  return v4;
}

```

## disassembly

```asm
0x180018b44  mov     [rsp-8+arg_10], rbx
0x180018b49  push    rbp
0x180018b4a  push    rsi
0x180018b4b  push    rdi
0x180018b4c  push    r14
0x180018b4e  push    r15
0x180018b50  lea     rbp, [rsp-180h]
0x180018b58  sub     rsp, 280h
0x180018b5f  mov     rax, cs:__security_cookie
0x180018b66  xor     rax, rsp
0x180018b69  mov     [rbp+1A0h+var_30], rax
0x180018b70  mov     r15, rdx
0x180018b73  mov     [rsp+2A0h+hKey], 0
0x180018b7c  mov     rsi, rcx
0x180018b7f  mov     [rsp+2A0h+hkey], 0
0x180018b88  mov     ebx, 1
0x180018b8d  mov     [rsp+2A0h+var_260], 0
0x180018b96  xor     ecx, ecx; pvReserved
0x180018b98  lea     edx, [rbx+1]; dwCoInit
0x180018b9b  call    cs:__imp_CoInitializeEx
0x180018ba1  mov     rdi, [r15+48h]
0x180018ba5  mov     r14d, eax
0x180018ba8  test    rdi, rdi
0x180018bab  jz      loc_180018D42
0x180018bb1  lea     r8, [rsp+2A0h+hKey]; HKEY *
0x180018bb6  mov     rcx, rsi; this
0x180018bb9  call    ?_SHCreateSessionKey@CUmRdpDrv@@AEAAJKPEAPEAUHKEY__@@@Z; CUmRdpDrv::_SHCreateSessionKey(ulong,HKEY__ * *)
0x180018bbe  mov     ebx, 104h
0x180018bc3  test    eax, eax
0x180018bc5  js      short loc_180018C02
0x180018bc7  mov     r9, rdi
0x180018bca  lea     r8, aMycomputerName; "MyComputer\\Namespace\\%s"
0x180018bd1  mov     edx, ebx; unsigned __int64
0x180018bd3  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x180018bd8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018bdd  test    eax, eax
0x180018bdf  js      short loc_180018BF7
0x180018be1  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180018be6  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x180018beb  xor     r9d, r9d; Reserved
0x180018bee  xor     r8d, r8d; samDesired
0x180018bf1  call    cs:__imp_RegDeleteKeyExW
0x180018bf7  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180018bfc  call    cs:__imp_RegCloseKey
0x180018c02  mov     rcx, [rsi+218h]; void *
0x180018c09  lea     r8, [rsp+2A0h+var_260]; HKEY *
0x180018c0e  lea     rdx, [rsp+2A0h+hkey]; HKEY *
0x180018c13  call    ?GetHKCUClassesCLSID@@YAXPEAXPEAPEAUHKEY__@@1@Z; GetHKCUClassesCLSID(void *,HKEY__ * *,HKEY__ * *)
0x180018c18  mov     rcx, [rsp+2A0h+hkey]; hkey
0x180018c1d  test    rcx, rcx
0x180018c20  jz      short loc_180018C36
0x180018c22  mov     rdx, rdi; pszSubKey
0x180018c25  call    cs:__imp_SHDeleteKeyW
0x180018c2b  mov     rcx, [rsp+2A0h+hkey]; hKey
0x180018c30  call    cs:__imp_RegCloseKey
0x180018c36  mov     rcx, [rsp+2A0h+var_260]; hkey
0x180018c3b  test    rcx, rcx
0x180018c3e  jz      short loc_180018C54
0x180018c40  mov     rdx, rdi; pszSubKey
0x180018c43  call    cs:__imp_SHDeleteKeyW
0x180018c49  mov     rcx, [rsp+2A0h+var_260]; hKey
0x180018c4e  call    cs:__imp_RegCloseKey
0x180018c54  mov     rcx, [rsi+218h]; void *
0x180018c5b  lea     r8, [rsp+2A0h+var_250]; HKEY *
0x180018c60  lea     rdx, [rsp+2A0h+var_258]; HKEY *
0x180018c65  mov     [rsp+2A0h+var_258], 0
0x180018c6e  mov     [rsp+2A0h+var_250], 0
0x180018c77  call    ?GetHKCUWow64ClassesCLSID@@YAXPEAXPEAPEAUHKEY__@@1@Z; GetHKCUWow64ClassesCLSID(void *,HKEY__ * *,HKEY__ * *)
0x180018c7c  mov     rcx, [rsp+2A0h+var_258]; hkey
0x180018c81  test    rcx, rcx
0x180018c84  jz      short loc_180018C9A
0x180018c86  mov     rdx, rdi; pszSubKey
0x180018c89  call    cs:__imp_SHDeleteKeyW
0x180018c8f  mov     rcx, [rsp+2A0h+var_258]; hKey
0x180018c94  call    cs:__imp_RegCloseKey
0x180018c9a  mov     rcx, [rsp+2A0h+var_250]; hkey
0x180018c9f  test    rcx, rcx
0x180018ca2  jz      short loc_180018CB8
0x180018ca4  mov     rdx, rdi; pszSubKey
0x180018ca7  call    cs:__imp_SHDeleteKeyW
0x180018cad  mov     rcx, [rsp+2A0h+var_250]; hKey
0x180018cb2  call    cs:__imp_RegCloseKey
0x180018cb8  mov     r9, rdi
0x180018cbb  lea     r8, a20d04fe03aea10; "::{20D04FE0-3AEA-1069-A2D8-08002B30309D"...
0x180018cc2  mov     rdx, rbx; unsigned __int64
0x180018cc5  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x180018cca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018ccf  test    eax, eax
0x180018cd1  js      short loc_180018D20
0x180018cd3  call    cs:__imp_RevertToSelf
0x180018cd9  mov     rcx, [rsi]; this
0x180018cdc  lea     rdx, [rsp+2A0h+var_248]; struct CUmRdpRpc **
0x180018ce1  mov     [rsp+2A0h+var_248], 0
0x180018cea  call    ?CreateUmRdpRpc@CUmRdpDr@@QEAAJAEAPEAVCUmRdpRpc@@@Z; CUmRdpDr::CreateUmRdpRpc(CUmRdpRpc * &)
0x180018cef  test    eax, eax
0x180018cf1  jnz     short loc_180018D0F
0x180018cf3  mov     rcx, [rsp+2A0h+var_248]; this
0x180018cf8  lea     r9, [rsp+2A0h+SubKey]; unsigned __int16 *
0x180018cfd  lea     edx, [rax+4]; int
0x180018d00  call    ?SHChangeNotify@CUmRdpRpc@@QEAAXJIPEAG0@Z; CUmRdpRpc::SHChangeNotify(long,uint,ushort *,ushort *)
0x180018d05  mov     rcx, [rsp+2A0h+var_248]; this
0x180018d0a  call    ?Release@CUmRdpRpc@@QEAAXXZ; CUmRdpRpc::Release(void)
0x180018d0f  mov     rcx, [rsi+218h]; hToken
0x180018d16  call    cs:__imp_ImpersonateLoggedOnUser
0x180018d1c  mov     ebx, eax
0x180018d1e  jmp     short loc_180018D22
0x180018d20  xor     ebx, ebx
0x180018d22  mov     rcx, gs:60h
0x180018d2b  mov     r8, rdi; lpMem
0x180018d2e  xor     edx, edx; dwFlags
0x180018d30  mov     rcx, [rcx+30h]; hHeap
0x180018d34  call    cs:__imp_HeapFree
0x180018d3a  mov     qword ptr [r15+48h], 0
0x180018d42  mov     dword ptr [rsi+8], 0
0x180018d49  test    r14d, r14d
0x180018d4c  js      short loc_180018D54
0x180018d4e  call    cs:__imp_CoUninitialize
0x180018d54  mov     eax, ebx
0x180018d56  mov     rcx, [rbp+1A0h+var_30]
0x180018d5d  xor     rcx, rsp; StackCookie
0x180018d60  call    __security_check_cookie
0x180018d65  mov     rbx, [rsp+2A0h+arg_10]
0x180018d6d  add     rsp, 280h
0x180018d74  pop     r15
0x180018d76  pop     r14
0x180018d78  pop     rdi
0x180018d79  pop     rsi
0x180018d7a  pop     rbp
0x180018d7b  retn
```
