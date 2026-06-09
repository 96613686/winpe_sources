# SensNotifyNetconEvent

- ea: `0x180007020`
- end: `0x18000715e`
- name: `SensNotifyNetconEvent`
- size: `318`
- prototype: `signed int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180005960`
- `0x180007020`
- `0x18000b010`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180007106`
- `RPCRT4!NdrClientCall3` at `0x180007106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000712e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000712e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000714d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000714d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800070c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800070c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007123`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007123`

## string_xrefs

- `0x1800070b9`: `netshell.dll`

## pseudocode

```c
signed int __fastcall SensNotifyNetconEvent(__int64 a1)
{
  __int64 v2; // rcx
  signed int v3; // ebx
  __int64 v4; // rcx
  signed int Pointer; // eax
  bool v6; // cc
  HMODULE Library; // rax
  HMODULE v8; // rdi
  signed int result; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int128 v12; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-18h]
  __int64 v14; // [rsp+80h] [rbp+28h] BYREF

  v13 = 0;
  v2 = *(_QWORD *)(a1 + 8);
  v14 = 0;
  v12 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 56LL))(v2, &v14);
  if ( v3 < 0 )
  {
LABEL_8:
    v4 = v14;
    goto LABEL_9;
  }
  v4 = v14;
  if ( v14 && *(_DWORD *)(v14 + 36) == 3 && (*(_DWORD *)(v14 + 32) & 0xFFFFFFFD) == 0 )
  {
    LODWORD(v12) = *(_DWORD *)a1;
    v13 = *(_QWORD *)(v14 + 32);
    *((_QWORD *)&v12 + 1) = *(_QWORD *)(v14 + 16);
    Pointer = DoRpcSetup();
    v6 = Pointer <= 0;
    if ( Pointer
      || (Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, ghSensNotify, &v12).Pointer,
          v6 = Pointer <= 0,
          Pointer) )
    {
      if ( v6 )
        v3 = Pointer;
      else
        v3 = (unsigned __int16)Pointer | 0x80070000;
    }
    goto LABEL_8;
  }
  v3 = -2147024809;
LABEL_9:
  if ( !v4 )
    return v3;
  Library = LoadLibraryExW(L"netshell.dll", 0, 0);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "NcFreeNetconProperties");
    if ( ProcAddress )
    {
      ((void (__fastcall *)(__int64))ProcAddress)(v14);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    FreeLibrary(v8);
    return v3;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180007020  push    rbp
0x180007022  push    rbx
0x180007023  push    rsi
0x180007024  push    rdi
0x180007025  mov     rbp, rsp
0x180007028  sub     rsp, 58h
0x18000702c  xor     eax, eax
0x18000702e  lea     rdx, [rbp+arg_0]
0x180007032  mov     [rbp+var_18], rax
0x180007036  mov     rdi, rcx
0x180007039  mov     rcx, [rcx+8]
0x18000703d  xorps   xmm0, xmm0
0x180007040  mov     [rbp+arg_0], rax
0x180007044  movups  [rbp+var_28], xmm0
0x180007048  mov     rax, [rcx]
0x18000704b  mov     rax, [rax+38h]
0x18000704f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007054  mov     ebx, eax
0x180007056  mov     esi, 80070000h
0x18000705b  test    eax, eax
0x18000705d  js      short loc_1800070A9
0x18000705f  mov     rcx, [rbp+arg_0]
0x180007063  test    rcx, rcx
0x180007066  jz      loc_180007112
0x18000706c  cmp     dword ptr [rcx+24h], 3
0x180007070  jnz     loc_180007112
0x180007076  test    dword ptr [rcx+20h], 0FFFFFFFDh
0x18000707d  jnz     loc_180007112
0x180007083  mov     eax, [rdi]
0x180007085  mov     dword ptr [rbp+var_28], eax
0x180007088  mov     eax, [rcx+20h]
0x18000708b  mov     dword ptr [rbp+var_18], eax
0x18000708e  mov     eax, [rcx+24h]
0x180007091  mov     dword ptr [rbp+var_18+4], eax
0x180007094  mov     rax, [rcx+10h]
0x180007098  mov     qword ptr [rbp+var_28+8], rax
0x18000709c  call    ?DoRpcSetup@@YAJXZ; DoRpcSetup(void)
0x1800070a1  test    eax, eax
0x1800070a3  jz      short loc_1800070E8
0x1800070a5  jg      short loc_1800070E1
0x1800070a7  mov     ebx, eax
0x1800070a9  mov     rcx, [rbp+arg_0]
0x1800070ad  test    rcx, rcx
0x1800070b0  jz      loc_180007153
0x1800070b6  xor     r8d, r8d; dwFlags
0x1800070b9  lea     rcx, aNetshellDll; "netshell.dll"
0x1800070c0  xor     edx, edx; hFile
0x1800070c2  call    cs:__imp_LoadLibraryExW
0x1800070c8  mov     rdi, rax
0x1800070cb  test    rax, rax
0x1800070ce  jnz     short loc_180007119
0x1800070d0  call    cs:__imp_GetLastError
0x1800070d6  test    eax, eax
0x1800070d8  jle     short loc_180007155
0x1800070da  movzx   eax, ax
0x1800070dd  or      eax, esi
0x1800070df  jmp     short loc_180007155
0x1800070e1  movzx   ebx, ax
0x1800070e4  or      ebx, esi
0x1800070e6  jmp     short loc_1800070A9
0x1800070e8  mov     r9, cs:?ghSensNotify@@3PEAXEA; void * ghSensNotify
0x1800070ef  lea     rax, [rbp+var_28]
0x1800070f3  xor     r8d, r8d; pReturnValue
0x1800070f6  mov     [rsp+58h+var_38], rax
0x1800070fb  lea     rcx, pProxyInfo; pProxyInfo
0x180007102  lea     edx, [r8+2]; nProcNum
0x180007106  call    cs:__imp_NdrClientCall3
0x18000710c  test    eax, eax
0x18000710e  jz      short loc_1800070A9
0x180007110  jmp     short loc_1800070A5
0x180007112  mov     ebx, 80070057h
0x180007117  jmp     short loc_1800070AD
0x180007119  lea     rdx, aNcfreenetconpr; "NcFreeNetconProperties"
0x180007120  mov     rcx, rdi; hModule
0x180007123  call    cs:__imp_GetProcAddress
0x180007129  test    rax, rax
0x18000712c  jnz     short loc_180007141
0x18000712e  call    cs:__imp_GetLastError
0x180007134  mov     ebx, eax
0x180007136  test    eax, eax
0x180007138  jle     short loc_18000714A
0x18000713a  movzx   ebx, ax
0x18000713d  or      ebx, esi
0x18000713f  jmp     short loc_18000714A
0x180007141  mov     rcx, [rbp+arg_0]
0x180007145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000714a  mov     rcx, rdi; hLibModule
0x18000714d  call    cs:__imp_FreeLibrary
0x180007153  mov     eax, ebx
0x180007155  add     rsp, 58h
0x180007159  pop     rdi
0x18000715a  pop     rsi
0x18000715b  pop     rbx
0x18000715c  pop     rbp
0x18000715d  retn
```
