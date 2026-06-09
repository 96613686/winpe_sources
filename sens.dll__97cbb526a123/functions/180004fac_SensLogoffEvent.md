# SensLogoffEvent

- ea: `0x180004fac`
- end: `0x1800050a4`
- name: `SensLogoffEvent`
- size: `248`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004f10`

## callees

- `0x180004fac`
- `0x180005960`
- `0x180005c70`
- `0x1800098f4`
- `0x18000b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180005025`
- `RPCRT4!NdrClientCall3` at `0x180005025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000509c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005094`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000509c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000506f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000506f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005040`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005040`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005058`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005058`

## string_xrefs

- `0x180005037`: `ES.DLL`

## pseudocode

```c
__int64 __fastcall SensLogoffEvent(__int64 a1)
{
  int v2; // edx
  unsigned int v3; // edx
  void *v4; // rcx
  unsigned int Pointer; // esi
  HMODULE Library; // rax
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  int v12; // [rsp+38h] [rbp-40h]
  int v13; // [rsp+3Ch] [rbp-3Ch]
  __int64 v14; // [rsp+40h] [rbp-38h]
  __int64 v15; // [rsp+48h] [rbp-30h]
  __int64 v16; // [rsp+50h] [rbp-28h]
  int v17; // [rsp+58h] [rbp-20h]
  int v18; // [rsp+5Ch] [rbp-1Ch]
  int v19; // [rsp+60h] [rbp-18h]
  int v20; // [rsp+64h] [rbp-14h]

  v2 = *(_DWORD *)(a1 + 4);
  v14 = *(_QWORD *)(a1 + 8);
  v15 = *(_QWORD *)(a1 + 16);
  v16 = *(_QWORD *)(a1 + 24);
  v17 = *(_DWORD *)(a1 + 32);
  v18 = *(_DWORD *)(a1 + 40);
  v11 = 0x2000;
  v20 = 0;
  v12 = 56;
  v13 = v2;
  v19 = v2;
  Pointer = DoRpcSetup();
  if ( !Pointer )
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, ghSensNotify, &v11).Pointer;
  if ( (*(_BYTE *)(a1 + 4) & 2) == 0 && (unsigned int)IsAutoSyncEnabled(v4, v3) )
    SensNotifyOneStop(*(HANDLE *)(a1 + 32), v10);
  Library = LoadLibraryExW(L"ES.DLL", 0, 0);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "NotifyLogoffUser");
    if ( ProcAddress )
      ((void (__fastcall *)(_QWORD))ProcAddress)(*(_QWORD *)(a1 + 32));
    else
      GetLastError();
    FreeLibrary(v7);
  }
  else
  {
    GetLastError();
  }
  return Pointer;
}

```

## disassembly

```asm
0x180004fac  push    rbp
0x180004fae  push    rbx
0x180004faf  push    rsi
0x180004fb0  push    rdi
0x180004fb1  mov     rbp, rsp
0x180004fb4  sub     rsp, 78h
0x180004fb8  mov     rax, [rcx+8]
0x180004fbc  mov     rbx, rcx
0x180004fbf  mov     edx, [rcx+4]
0x180004fc2  mov     [rbp+var_38], rax
0x180004fc6  mov     rax, [rcx+10h]
0x180004fca  mov     [rbp+var_30], rax
0x180004fce  mov     rax, [rcx+18h]
0x180004fd2  mov     [rbp+var_28], rax
0x180004fd6  mov     eax, [rcx+20h]
0x180004fd9  mov     [rbp+var_20], eax
0x180004fdc  mov     eax, [rcx+28h]
0x180004fdf  mov     [rbp+var_1C], eax
0x180004fe2  mov     [rbp+var_48], 2000h
0x180004fea  mov     [rbp+var_14], 0
0x180004ff1  mov     [rbp+var_40], 38h ; '8'
0x180004ff8  mov     [rbp+var_3C], edx
0x180004ffb  mov     [rbp+var_18], edx
0x180004ffe  call    ?DoRpcSetup@@YAJXZ; DoRpcSetup(void)
0x180005003  mov     esi, eax
0x180005005  test    eax, eax
0x180005007  jnz     short loc_18000502E
0x180005009  mov     r9, cs:?ghSensNotify@@3PEAXEA; void * ghSensNotify
0x180005010  lea     rax, [rbp+var_48]
0x180005014  xor     r8d, r8d; pReturnValue
0x180005017  mov     [rsp+78h+var_58], rax
0x18000501c  xor     edx, edx; nProcNum
0x18000501e  lea     rcx, pProxyInfo; pProxyInfo
0x180005025  call    cs:__imp_NdrClientCall3
0x18000502b  mov     rsi, rax
0x18000502e  test    byte ptr [rbx+4], 2
0x180005032  jz      short loc_180005080
0x180005034  xor     r8d, r8d; dwFlags
0x180005037  lea     rcx, aEsDll; "ES.DLL"
0x18000503e  xor     edx, edx; hFile
0x180005040  call    cs:__imp_LoadLibraryExW
0x180005046  mov     rdi, rax
0x180005049  test    rax, rax
0x18000504c  jz      short loc_180005094
0x18000504e  lea     rdx, aNotifylogoffus; "NotifyLogoffUser"
0x180005055  mov     rcx, rax; hModule
0x180005058  call    cs:__imp_GetProcAddress
0x18000505e  test    rax, rax
0x180005061  jz      short loc_18000509C
0x180005063  mov     rcx, [rbx+20h]
0x180005067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506c  mov     rcx, rdi; hLibModule
0x18000506f  call    cs:__imp_FreeLibrary
0x180005075  mov     eax, esi
0x180005077  add     rsp, 78h
0x18000507b  pop     rdi
0x18000507c  pop     rsi
0x18000507d  pop     rbx
0x18000507e  pop     rbp
0x18000507f  retn
0x180005080  call    ?IsAutoSyncEnabled@@YAHPEAXK@Z; IsAutoSyncEnabled(void *,ulong)
0x180005085  test    eax, eax
0x180005087  jz      short loc_180005034
0x180005089  mov     rcx, [rbx+20h]; hToken
0x18000508d  call    ?SensNotifyOneStop@@YAJPEAXPEBGH@Z; SensNotifyOneStop(void *,ushort const *,int)
0x180005092  jmp     short loc_180005034
0x180005094  call    cs:__imp_GetLastError
0x18000509a  jmp     short loc_180005075
0x18000509c  call    cs:__imp_GetLastError
0x1800050a2  jmp     short loc_18000506C
```
