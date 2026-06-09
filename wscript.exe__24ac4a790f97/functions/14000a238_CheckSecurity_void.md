# CheckSecurity(void)

- ea: `0x14000a238`
- end: `0x14000a352`
- name: `?CheckSecurity@@YAJXZ`
- size: `282`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006c88`

## callees

- `0x14000a238`
- `0x14000a358`
- `0x14000a568`
- `0x140015a7c`
- `0x140018010`

## import_xrefs

- `ole32!CoInitializeSecurity` at `0x14000a307`
- `ole32!CoInitializeSecurity` at `0x14000a307`
- `ADVAPI32!RegCloseKey` at `0x14000a319`
- `ADVAPI32!RegCloseKey` at `0x14000a329`
- `ADVAPI32!RegCloseKey` at `0x14000a319`
- `ADVAPI32!RegCloseKey` at `0x14000a329`

## pseudocode

```c
__int64 CheckSecurity(void)
{
  HRESULT v0; // eax
  int v1; // ebx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+10h] BYREF

  phkResult = 0;
  hKey = 0;
  OpenRegSettings(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &phkResult);
  OpenRegSettings(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows Script Host\\Settings", 0x20019u, &hKey);
  if ( CheckWSHFlag(L"Enabled", phkResult, hKey, 1) )
  {
    v1 = 0;
    if ( !Global::g_fWindowsNT )
      goto LABEL_6;
    v0 = CoInitializeSecurity(0, -1, 0, 0, 0, 3u, 0, 0, 0);
  }
  else
  {
    v0 = (*(__int64 (__fastcall **)(CHost *, _QWORD, __int64))(*(_QWORD *)g_pHost + 8LL))(
           g_pHost,
           (unsigned int)(Global::g_lResourceBase + 20),
           3208);
  }
  v1 = v0;
LABEL_6:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  LogSecurityMessage(v1 < 0, ((v1 >> 31) & 0x9B) + 3054);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14000a238  push    rbx
0x14000a23a  sub     rsp, 50h
0x14000a23e  mov     ebx, 20019h
0x14000a243  mov     [rsp+58h+phkResult], 0
0x14000a24c  mov     r8d, ebx; samDesired
0x14000a24f  mov     [rsp+58h+hKey], 0
0x14000a258  lea     r9, [rsp+58h+phkResult]; phkResult
0x14000a25d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14000a264  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x14000a26b  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x14000a270  lea     r9, [rsp+58h+hKey]; phkResult
0x14000a275  mov     r8d, ebx; samDesired
0x14000a278  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Script Hos"...
0x14000a27f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a286  call    ?OpenRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; OpenRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x14000a28b  mov     r8, [rsp+58h+hKey]; HKEY
0x14000a290  lea     rcx, aEnabled; "Enabled"
0x14000a297  mov     rdx, [rsp+58h+phkResult]; hKey
0x14000a29c  mov     r9b, 1; bool
0x14000a29f  call    ?CheckWSHFlag@@YA_NPEBGPEAUHKEY__@@1_N@Z; CheckWSHFlag(ushort const *,HKEY__ *,HKEY__ *,bool)
0x14000a2a4  test    al, al
0x14000a2a6  jnz     short loc_14000A2D8
0x14000a2a8  mov     rcx, cs:?g_pHost@@3PEAVCHost@@EA; CHost * g_pHost
0x14000a2af  lea     r9, Default
0x14000a2b6  mov     edx, cs:?g_lResourceBase@Global@@2JA; long Global::g_lResourceBase
0x14000a2bc  mov     r8d, 0C88h
0x14000a2c2  add     edx, 14h
0x14000a2c5  mov     qword ptr [rsp+58h+dwAuthnLevel], r9
0x14000a2ca  mov     rax, [rcx]
0x14000a2cd  mov     rax, [rax+8]
0x14000a2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a2d6  jmp     short loc_14000A30D
0x14000a2d8  xor     ebx, ebx
0x14000a2da  cmp     cs:?g_fWindowsNT@Global@@2_NA, bl; bool Global::g_fWindowsNT
0x14000a2e0  jz      short loc_14000A30F
0x14000a2e2  mov     [rsp+58h+pReserved3], rbx; pReserved3
0x14000a2e7  xor     r9d, r9d; pReserved1
0x14000a2ea  mov     [rsp+58h+dwCapabilities], ebx; dwCapabilities
0x14000a2ee  xor     r8d, r8d; asAuthSvc
0x14000a2f1  mov     [rsp+58h+pAuthList], rbx; pAuthList
0x14000a2f6  or      edx, 0FFFFFFFFh; cAuthSvc
0x14000a2f9  mov     [rsp+58h+dwImpLevel], 3; dwImpLevel
0x14000a301  xor     ecx, ecx; pSecDesc
0x14000a303  mov     [rsp+58h+dwAuthnLevel], ebx; dwAuthnLevel
0x14000a307  call    cs:__imp_CoInitializeSecurity
0x14000a30d  mov     ebx, eax
0x14000a30f  mov     rcx, [rsp+58h+hKey]; hKey
0x14000a314  test    rcx, rcx
0x14000a317  jz      short loc_14000A31F
0x14000a319  call    cs:__imp_RegCloseKey
0x14000a31f  mov     rcx, [rsp+58h+phkResult]; hKey
0x14000a324  test    rcx, rcx
0x14000a327  jz      short loc_14000A32F
0x14000a329  call    cs:__imp_RegCloseKey
0x14000a32f  mov     edx, ebx
0x14000a331  mov     ecx, ebx
0x14000a333  sar     edx, 1Fh
0x14000a336  and     edx, 9Bh
0x14000a33c  shr     ecx, 1Fh; bool
0x14000a33f  add     edx, 0BEEh; unsigned int
0x14000a345  call    ?LogSecurityMessage@@YAX_NI@Z; LogSecurityMessage(bool,uint)
0x14000a34a  mov     eax, ebx
0x14000a34c  add     rsp, 50h
0x14000a350  pop     rbx
0x14000a351  retn
```
