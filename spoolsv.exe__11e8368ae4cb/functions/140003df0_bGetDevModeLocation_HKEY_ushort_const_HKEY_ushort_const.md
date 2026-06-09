# bGetDevModeLocation(HKEY__ *,ushort const *,HKEY__ * *,ushort const * *)

- ea: `0x140003df0`
- end: `0x1400040d2`
- name: `?bGetDevModeLocation@@YAHPEAUHKEY__@@PEBGPEAPEAU1@PEAPEBG@Z`
- size: `738`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, PHKEY phkResult, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1400104d0`
- `0x140017710`

## callees

- `0x140003c70`
- `0x140003df0`
- `0x1400041c0`
- `0x14000c490`
- `0x1400140cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004038`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000409c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000409c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004045`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004058`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004045`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004058`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004024`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004024`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003ec8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003ec8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x140003ef5`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x140003ef5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003e4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004086`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003e4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004086`

## string_xrefs

- `0x140004066`: `RegOpenCurrentUser failed. Error %d.`

## pseudocode

```c
__int64 __fastcall bGetDevModeLocation(
        HKEY hKey,
        const unsigned __int16 *a2,
        PHKEY phkResult,
        const unsigned __int16 **a4)
{
  HKEY ClientUserHandle; // r14
  HKEY v8; // rbx
  DWORD LastError; // esi
  LSTATUS v11; // eax
  unsigned int v12; // ebx
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  WCHAR *v15; // r13
  __int64 v16; // rcx
  const unsigned __int16 *v17; // r9
  __int64 v18; // r8
  _WORD *v19; // rdx
  _WORD *v20; // rcx
  __int64 v21; // r10
  unsigned __int16 i; // ax
  DWORD dwDisposition; // [rsp+90h] [rbp+8h] BYREF
  HKEY hKeya; // [rsp+A0h] [rbp+18h] BYREF

  ClientUserHandle = hKey;
  *phkResult = 0;
  v8 = 0;
  *a4 = 0;
  if ( !hKey )
  {
    hKeya = 0;
    v11 = RegOpenCurrentUser(0x2001Fu, &hKeya);
    v12 = v11;
    if ( v11 )
    {
      SetLastError(v11);
      if ( v12 != 5 )
        PrvSpoolssTelemetry::WriteDbgTraceError("SplGetClientUserHandle", L"RegOpenCurrentUser failed. Error %d.", v12);
      if ( hKeya )
        RegCloseKey(hKeya);
      ClientUserHandle = 0;
      hKeya = 0;
    }
    else
    {
      ClientUserHandle = hKeya;
    }
    if ( !ClientUserHandle && GetLastError() == 5 )
      ClientUserHandle = (HKEY)SplGetClientUserHandle(131097);
    v8 = ClientUserHandle;
    if ( !ClientUserHandle )
    {
      LastError = GetLastError();
      goto LABEL_6;
    }
  }
  LastError = 0;
  if ( *a2 != 92 || a2[1] != 92 )
    goto LABEL_3;
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  if ( v13 >= 0x21B )
  {
    LastError = 87;
LABEL_3:
    if ( !*a4 )
    {
      dwDisposition = 0;
      LastError = RegCreateKeyExW(
                    ClientUserHandle,
                    L"Printers\\DevModePerUser",
                    0,
                    0,
                    0,
                    0x2001Fu,
                    0,
                    phkResult,
                    &dwDisposition);
      if ( !LastError )
        *a4 = a2;
    }
    goto LABEL_4;
  }
  v14 = DllAllocSplMem(0x462u);
  v15 = (WCHAR *)v14;
  if ( v14 )
  {
    v16 = 2147483646;
    v17 = L"Printers\\Connections\\";
    v18 = 561;
    v19 = (_WORD *)v14;
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v19++ = *v17++;
      --v16;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    v21 = v14 + 42;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    if ( (const unsigned __int16 *)v21 != a2 )
      StringCchCopyW((unsigned __int16 *)(v14 + 42), 0x21Cu, a2);
    for ( i = *(_WORD *)v21; i; v21 += 2 )
    {
      if ( i == 92 )
        *(_WORD *)v21 = 44;
      i = *(_WORD *)(v21 + 2);
    }
    LastError = RegOpenKeyExW(ClientUserHandle, v15, 0, 0x2001Fu, phkResult);
    HeapFree(g_hSpoolssHeap, 0, v15);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError )
    goto LABEL_3;
  *a4 = L"DevMode";
LABEL_4:
  if ( v8 )
    RegCloseKey(v8);
LABEL_6:
  if ( !LastError )
    return 1;
  SetLastError(LastError);
  return 0;
}

```

## disassembly

```asm
0x140003df0  mov     rax, rsp
0x140003df3  push    rsi
0x140003df4  sub     rsp, 80h
0x140003dfb  mov     [rax+10h], rbx
0x140003dff  mov     [rax-10h], rbp
0x140003e03  mov     rbp, rdx
0x140003e06  mov     [rax-18h], rdi
0x140003e0a  mov     rdi, r9
0x140003e0d  mov     [rax-20h], r12
0x140003e11  xor     r12d, r12d
0x140003e14  mov     [rax-30h], r14
0x140003e18  mov     r14, rcx
0x140003e1b  mov     [rax-38h], r15
0x140003e1f  mov     r15, r8
0x140003e22  mov     [r8], r12
0x140003e25  mov     ebx, r12d
0x140003e28  mov     [r9], r12
0x140003e2b  test    rcx, rcx
0x140003e2e  jz      loc_140003EE0
0x140003e34  cmp     word ptr [rbp+0], 5Ch ; '\'
0x140003e39  mov     esi, r12d
0x140003e3c  jz      loc_140003F2F
0x140003e42  cmp     [rdi], r12
0x140003e45  jz      short loc_140003E8C
0x140003e47  test    rbx, rbx
0x140003e4a  jz      short loc_140003E55
0x140003e4c  mov     rcx, rbx; hKey
0x140003e4f  call    cs:__imp_RegCloseKey
0x140003e55  mov     r15, [rsp+88h+var_38]
0x140003e5a  mov     r14, [rsp+88h+var_30]
0x140003e5f  mov     r12, [rsp+88h+var_20]
0x140003e64  mov     rdi, [rsp+88h+var_18]
0x140003e69  mov     rbp, [rsp+88h+var_10]
0x140003e6e  mov     rbx, [rsp+88h+arg_8]
0x140003e76  test    esi, esi
0x140003e78  jnz     loc_140004043
0x140003e7e  mov     eax, 1
0x140003e83  add     rsp, 80h
0x140003e8a  pop     rsi
0x140003e8b  retn
0x140003e8c  lea     rax, [rsp+88h+dwDisposition]
0x140003e94  mov     [rsp+88h+dwDisposition], r12d
0x140003e9c  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x140003ea1  lea     rdx, gszDevModePerUserLocal; "Printers\\DevModePerUser"
0x140003ea8  mov     [rsp+88h+phkResult], r15; phkResult
0x140003ead  xor     r9d, r9d; lpClass
0x140003eb0  mov     [rsp+88h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140003eb5  xor     r8d, r8d; Reserved
0x140003eb8  mov     [rsp+88h+samDesired], 2001Fh; samDesired
0x140003ec0  mov     rcx, r14; hKey
0x140003ec3  mov     [rsp+88h+dwOptions], r12d; dwOptions
0x140003ec8  call    cs:__imp_RegCreateKeyExW
0x140003ece  mov     esi, eax
0x140003ed0  test    eax, eax
0x140003ed2  jnz     loc_140003E47
0x140003ed8  mov     [rdi], rbp
0x140003edb  jmp     loc_140003E47
0x140003ee0  lea     rdx, [rsp+88h+hKey]; phkResult
0x140003ee8  mov     [rsp+88h+hKey], r12
0x140003ef0  mov     ecx, 2001Fh; samDesired
0x140003ef5  call    cs:__imp_RegOpenCurrentUser
0x140003efb  mov     ebx, eax
0x140003efd  test    eax, eax
0x140003eff  jnz     loc_140004056
0x140003f05  mov     r14, [rsp+88h+hKey]
0x140003f0d  test    r14, r14
0x140003f10  jz      loc_14000409C
0x140003f16  mov     rbx, r14
0x140003f19  test    r14, r14
0x140003f1c  jnz     loc_140003E34
0x140003f22  call    cs:__imp_GetLastError
0x140003f28  mov     esi, eax
0x140003f2a  jmp     loc_140003E55
0x140003f2f  cmp     word ptr [rbp+2], 5Ch ; '\'
0x140003f34  jnz     loc_140003E42
0x140003f3a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140003f41  inc     rax
0x140003f44  cmp     [rbp+rax*2+0], si
0x140003f49  jnz     short loc_140003F41
0x140003f4b  cmp     rax, 21Bh
0x140003f51  jb      short loc_140003F5D
0x140003f53  mov     esi, 57h ; 'W'
0x140003f58  jmp     loc_140003E42
0x140003f5d  mov     ecx, 462h; dwBytes
0x140003f62  mov     [rsp+88h+var_28], r13
0x140003f67  call    DllAllocSplMem
0x140003f6c  mov     r13, rax
0x140003f6f  test    rax, rax
0x140003f72  jnz     short loc_140003F98
0x140003f74  call    cs:__imp_GetLastError
0x140003f7a  mov     esi, eax
0x140003f7c  mov     r13, [rsp+88h+var_28]
0x140003f81  test    esi, esi
0x140003f83  jnz     loc_140003E42
0x140003f89  lea     rax, gszDevMode; "DevMode"
0x140003f90  mov     [rdi], rax
0x140003f93  jmp     loc_140003E47
0x140003f98  mov     ecx, 7FFFFFFEh
0x140003f9d  lea     r9, gszPrinterConnections; "Printers\\Connections\\"
0x140003fa4  mov     r8d, 231h
0x140003faa  mov     rdx, r13
0x140003fad  test    rcx, rcx
0x140003fb0  jz      short loc_140003FD1
0x140003fb2  movzx   r10d, word ptr [r9]
0x140003fb6  test    r10w, r10w
0x140003fba  jz      short loc_140003FD1
0x140003fbc  mov     [rdx], r10w
0x140003fc0  add     r9, 2
0x140003fc4  add     rdx, 2
0x140003fc8  dec     rcx
0x140003fcb  sub     r8, 1
0x140003fcf  jnz     short loc_140003FAD
0x140003fd1  test    r8, r8
0x140003fd4  lea     rcx, [rdx-2]
0x140003fd8  lea     r10, [rax+2Ah]
0x140003fdc  cmovnz  rcx, rdx
0x140003fe0  mov     [rcx], r12w
0x140003fe4  cmp     r10, rbp
0x140003fe7  jnz     loc_1400040BD
0x140003fed  movzx   eax, word ptr [r10]
0x140003ff1  test    ax, ax
0x140003ff4  jz      short loc_140004010
0x140003ff6  cmp     ax, 5Ch ; '\'
0x140003ffa  jnz     short loc_140004002
0x140003ffc  mov     word ptr [r10], 2Ch ; ','
0x140004002  movzx   eax, word ptr [r10+2]
0x140004007  add     r10, 2
0x14000400b  test    ax, ax
0x14000400e  jnz     short loc_140003FF6
0x140004010  mov     r9d, 2001Fh; samDesired
0x140004016  mov     qword ptr [rsp+88h+dwOptions], r15; phkResult
0x14000401b  xor     r8d, r8d; ulOptions
0x14000401e  mov     rdx, r13; lpSubKey
0x140004021  mov     rcx, r14; hKey
0x140004024  call    cs:__imp_RegOpenKeyExW
0x14000402a  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140004031  mov     r8, r13; lpMem
0x140004034  xor     edx, edx; dwFlags
0x140004036  mov     esi, eax
0x140004038  call    cs:__imp_HeapFree
0x14000403e  jmp     loc_140003F7C
0x140004043  mov     ecx, esi; dwErrCode
0x140004045  call    cs:__imp_SetLastError
0x14000404b  xor     eax, eax
0x14000404d  add     rsp, 80h
0x140004054  pop     rsi
0x140004055  retn
0x140004056  mov     ecx, ebx; dwErrCode
0x140004058  call    cs:__imp_SetLastError
0x14000405e  cmp     ebx, 5
0x140004061  jz      short loc_140004079
0x140004063  mov     r8d, ebx
0x140004066  lea     rdx, aRegopencurrent; "RegOpenCurrentUser failed. Error %d."
0x14000406d  lea     rcx, aSplgetclientus; "SplGetClientUserHandle"
0x140004074  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140004079  mov     rcx, [rsp+88h+hKey]; hKey
0x140004081  test    rcx, rcx
0x140004084  jz      short loc_14000408C
0x140004086  call    cs:__imp_RegCloseKey
0x14000408c  mov     r14, r12
0x14000408f  mov     [rsp+88h+hKey], r12
0x140004097  jmp     loc_140003F0D
0x14000409c  call    cs:__imp_GetLastError
0x1400040a2  cmp     eax, 5
0x1400040a5  jnz     loc_140003F16
0x1400040ab  mov     ecx, 20019h
0x1400040b0  call    SplGetClientUserHandle
0x1400040b5  mov     r14, rax
0x1400040b8  jmp     loc_140003F16
0x1400040bd  mov     r8, rbp; unsigned __int16 *
0x1400040c0  mov     edx, 21Ch; unsigned __int64
0x1400040c5  mov     rcx, r10; unsigned __int16 *
0x1400040c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400040cd  jmp     loc_140003FED
```
