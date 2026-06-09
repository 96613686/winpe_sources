# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x180387334`
- end: `0x180387629`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1803870ac`

## callees

- `0x18004719c`
- `0x1801321ac`
- `0x18037fc58`
- `0x18037fe30`
- `0x180380898`
- `0x180380b74`
- `0x180381e08`
- `0x180387334`
- `0x180387dc0`
- `0x180387f00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18038743a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18038746b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803874dd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803875af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803875e0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803875f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180387605`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18038743a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18038746b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803874dd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803875af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803875e0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803875f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180387605`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1803874b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1803874b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180387597`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180387597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803874c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803874c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387549`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803875a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387549`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803875a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18038757f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18038757f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180387539`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180387539`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1803875d2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1803875d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387553`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038758c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387553`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038758c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180387503`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180387503`

## string_xrefs

- `0x180387574`: `SymbolicLinkValue`
- `0x1803873f1`: `%s\ATConfig`
- `0x18038744e`: `%s\ATConfig`
- `0x18038749f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SettingsCopier::DeleteATSettings(HKEY *a1)
{
  void *v2; // rbx
  __int64 v3; // rdx
  unsigned __int16 *v4; // rdi
  int *v5; // rbx
  __int64 v6; // rdi
  unsigned int v7; // r11d
  unsigned __int64 v8; // rbx
  LSTATUS v9; // r14d
  unsigned __int64 v10; // rdx
  __int64 v12; // rsi
  const WCHAR *v13; // r14
  void *v14; // rcx
  HANDLE EventW; // r15
  signed int LastError; // eax
  DWORD v17; // esi
  LSTATUS v18; // eax
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-18h] BYREF
  __int64 v23; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v26; // [rsp+B8h] [rbp+58h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
  v21 = 0;
  v22 = 0;
  v2 = 0;
  Block = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !CATUtils::IsInteractiveUser() )
  {
    v12 = -2147483647;
    v13 = SettingsCopier::_ATConfigKeyString;
    v4 = v26;
LABEL_17:
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError <= 0 )
      {
LABEL_21:
        free(v2);
        goto LABEL_37;
      }
      v9 = (unsigned __int16)LastError;
LABEL_20:
      v9 |= 0x80070000;
      goto LABEL_21;
    }
    v9 = RegOpenKeyExW((HKEY)v12, v13, 8u, 0x20019u, &hKey);
    if ( v9 )
    {
      CloseHandle(EventW);
LABEL_24:
      if ( v9 <= 0 )
        goto LABEL_21;
      v9 = (unsigned __int16)v9;
      goto LABEL_20;
    }
    v9 = RegNotifyChangeKeyValue(hKey, 0, 5u, EventW, 1);
    if ( v9 )
    {
      CloseHandle(EventW);
      RegCloseKey(hKey);
      goto LABEL_24;
    }
    v9 = RegQueryValueExW(hKey, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    v17 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v17 )
    {
      free(v2);
      v9 = -2147023590;
      goto LABEL_37;
    }
    if ( v9 )
    {
      if ( v9 != 2 )
        goto LABEL_24;
    }
    else if ( Type == 6 )
    {
      free(v2);
      v9 = -2147023432;
      goto LABEL_37;
    }
    v18 = RegDeleteTreeW(*a1, 0);
    v14 = v2;
    if ( !v18 )
    {
      free(v2);
      v9 = 0;
      goto LABEL_37;
    }
LABEL_33:
    free(v14);
    v9 = -2147467259;
    goto LABEL_37;
  }
  v3 = *(_QWORD *)CATUtils::SessionKeyString(&v23);
  v4 = v26;
  v5 = (int *)(v26 - 12);
  if ( (unsigned __int16 *)(v3 - 24) != v26 - 12 )
  {
    if ( v5[4] >= 0 && *(_QWORD *)(v3 - 24) == *(_QWORD *)v5 )
    {
      v6 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v5);
      v4 = (unsigned __int16 *)(v6 + 24);
      v26 = v4;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v26, v3, *(unsigned int *)(v3 - 16));
      v4 = v26;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  if ( (int)StringCchLengthW(SettingsCopier::_ATSessionConfigKeyString, 0x7FFFFFFFu, &v21) < 0
    || (int)StringCchLengthW(v4, v7, &v22) < 0
    || (v8 = v21 + v22, v21 + v22 < v21) )
  {
    v14 = 0;
    goto LABEL_33;
  }
  if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v21 + v22) )
  {
    v10 = v8;
    v2 = Block;
    if ( (int)StringCchPrintfW((unsigned __int16 *)Block, v10, SettingsCopier::_ATSessionConfigKeyString, v4) < 0 )
    {
      free(v2);
      ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
      return 2147500037LL;
    }
    v12 = -2147483646;
    v13 = (const WCHAR *)v2;
    goto LABEL_17;
  }
  free(Block);
  v9 = -2147024882;
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180387334  push    rbp
0x180387336  push    rbx
0x180387337  push    rsi
0x180387338  push    rdi
0x180387339  push    r12
0x18038733b  push    r14
0x18038733d  push    r15
0x18038733f  mov     rbp, rsp
0x180387342  sub     rsp, 60h
0x180387346  mov     r12, rcx
0x180387349  lea     rcx, [rbp+arg_18]
0x18038734d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180387352  nop
0x180387353  mov     [rbp+var_20], 0
0x18038735b  mov     [rbp+var_18], 0
0x180387363  xor     ebx, ebx
0x180387365  mov     [rbp+Block], rbx
0x180387369  mov     [rbp+hKey], rbx
0x18038736d  mov     [rbp+Type], ebx
0x180387370  mov     [rbp+cbData], ebx
0x180387373  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x180387378  test    eax, eax
0x18038737a  jz      loc_180387498
0x180387380  lea     rcx, [rbp+var_10]
0x180387384  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x180387389  nop
0x18038738a  mov     rdx, [rax]
0x18038738d  lea     rcx, [rdx-18h]
0x180387391  mov     rdi, [rbp+arg_18]
0x180387395  lea     rbx, [rdi-18h]
0x180387399  cmp     rcx, rbx
0x18038739c  jz      short loc_1803873D7
0x18038739e  cmp     dword ptr [rbx+10h], 0
0x1803873a2  jl      short loc_1803873C6
0x1803873a4  mov     rax, [rbx]
0x1803873a7  cmp     [rcx], rax
0x1803873aa  jnz     short loc_1803873C6
0x1803873ac  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1803873b1  mov     rdi, rax
0x1803873b4  mov     rcx, rbx; this
0x1803873b7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1803873bc  add     rdi, 18h
0x1803873c0  mov     [rbp+arg_18], rdi
0x1803873c4  jmp     short loc_1803873D7
0x1803873c6  mov     r8d, [rdx-10h]
0x1803873ca  lea     rcx, [rbp+arg_18]
0x1803873ce  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1803873d3  mov     rdi, [rbp+arg_18]
0x1803873d7  mov     rcx, [rbp+var_10]
0x1803873db  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1803873df  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1803873e4  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1803873e8  mov     r11d, 7FFFFFFFh
0x1803873ee  mov     edx, r11d; unsigned __int64
0x1803873f1  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x1803873f8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1803873fd  test    eax, eax
0x1803873ff  js      loc_180387491
0x180387405  lea     r8, [rbp+var_18]; unsigned __int64 *
0x180387409  mov     edx, r11d; unsigned __int64
0x18038740c  mov     rcx, rdi; unsigned __int16 *
0x18038740f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180387414  test    eax, eax
0x180387416  js      short loc_180387491
0x180387418  mov     rbx, [rbp+var_18]
0x18038741c  add     rbx, [rbp+var_20]
0x180387420  cmp     rbx, [rbp+var_20]
0x180387424  jb      short loc_180387491
0x180387426  mov     rdx, rbx
0x180387429  lea     rcx, [rbp+Block]
0x18038742d  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x180387432  test    al, al
0x180387434  jnz     short loc_18038744B
0x180387436  mov     rcx, [rbp+Block]; Block
0x18038743a  call    cs:__imp_free
0x180387440  mov     r14d, 8007000Eh
0x180387446  jmp     loc_18038760E
0x18038744b  mov     r9, rdi
0x18038744e  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x180387455  mov     rdx, rbx; unsigned __int64
0x180387458  mov     rbx, [rbp+Block]
0x18038745c  mov     rcx, rbx; unsigned __int16 *
0x18038745f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180387464  test    eax, eax
0x180387466  jns     short loc_180387485
0x180387468  mov     rcx, rbx; Block
0x18038746b  call    cs:__imp_free
0x180387471  nop
0x180387472  lea     rcx, [rdi-18h]; this
0x180387476  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18038747b  mov     eax, 80004005h
0x180387480  jmp     loc_18038761A
0x180387485  mov     rsi, 0FFFFFFFF80000002h
0x18038748c  mov     r14, rbx
0x18038748f  jmp     short loc_1803874AA
0x180387491  xor     ecx, ecx
0x180387493  jmp     loc_1803875E0
0x180387498  mov     rsi, 0FFFFFFFF80000001h
0x18038749f  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1803874a6  mov     rdi, [rbp+arg_18]
0x1803874aa  xor     r9d, r9d; lpName
0x1803874ad  xor     r8d, r8d; bInitialState
0x1803874b0  xor     edx, edx; bManualReset
0x1803874b2  xor     ecx, ecx; lpEventAttributes
0x1803874b4  call    cs:__imp_CreateEventW
0x1803874ba  mov     r15, rax
0x1803874bd  test    rax, rax
0x1803874c0  jnz     short loc_1803874E8
0x1803874c2  call    cs:__imp_GetLastError
0x1803874c8  mov     r14d, eax
0x1803874cb  test    eax, eax
0x1803874cd  jle     short loc_1803874DA
0x1803874cf  movzx   r14d, ax
0x1803874d3  or      r14d, 80070000h
0x1803874da  mov     rcx, rbx; Block
0x1803874dd  call    cs:__imp_free
0x1803874e3  jmp     loc_18038760E
0x1803874e8  lea     rax, [rbp+hKey]
0x1803874ec  mov     [rsp+60h+phkResult], rax; phkResult
0x1803874f1  mov     r9d, 20019h; samDesired
0x1803874f7  mov     r8d, 8; ulOptions
0x1803874fd  mov     rdx, r14; lpSubKey
0x180387500  mov     rcx, rsi; hKey
0x180387503  call    cs:__imp_RegOpenKeyExW
0x180387509  mov     r14d, eax
0x18038750c  test    eax, eax
0x18038750e  jz      short loc_180387524
0x180387510  mov     rcx, r15; hObject
0x180387513  call    cs:__imp_CloseHandle
0x180387519  test    r14d, r14d
0x18038751c  jle     short loc_1803874DA
0x18038751e  movzx   r14d, r14w
0x180387522  jmp     short loc_1803874D3
0x180387524  mov     dword ptr [rsp+60h+phkResult], 1; fAsynchronous
0x18038752c  mov     r9, r15; hEvent
0x18038752f  xor     edx, edx; bWatchSubtree
0x180387531  lea     r8d, [rdx+5]; dwNotifyFilter
0x180387535  mov     rcx, [rbp+hKey]; hKey
0x180387539  call    cs:__imp_RegNotifyChangeKeyValue
0x18038753f  mov     r14d, eax
0x180387542  test    eax, eax
0x180387544  jz      short loc_18038755B
0x180387546  mov     rcx, r15; hObject
0x180387549  call    cs:__imp_CloseHandle
0x18038754f  mov     rcx, [rbp+hKey]; hKey
0x180387553  call    cs:__imp_RegCloseKey
0x180387559  jmp     short loc_180387519
0x18038755b  lea     rax, [rbp+cbData]
0x18038755f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180387564  mov     [rsp+60h+phkResult], 0; lpData
0x18038756d  lea     r9, [rbp+Type]; lpType
0x180387571  xor     r8d, r8d; lpReserved
0x180387574  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x18038757b  mov     rcx, [rbp+hKey]; hKey
0x18038757f  call    cs:__imp_RegQueryValueExW
0x180387585  mov     r14d, eax
0x180387588  mov     rcx, [rbp+hKey]; hKey
0x18038758c  call    cs:__imp_RegCloseKey
0x180387592  xor     edx, edx; dwMilliseconds
0x180387594  mov     rcx, r15; hHandle
0x180387597  call    cs:__imp_WaitForSingleObject
0x18038759d  mov     esi, eax
0x18038759f  mov     rcx, r15; hObject
0x1803875a2  call    cs:__imp_CloseHandle
0x1803875a8  test    esi, esi
0x1803875aa  jnz     short loc_1803875BD
0x1803875ac  mov     rcx, rbx; Block
0x1803875af  call    cs:__imp_free
0x1803875b5  mov     r14d, 8007051Ah
0x1803875bb  jmp     short loc_18038760E
0x1803875bd  test    r14d, r14d
0x1803875c0  jz      short loc_1803875EE
0x1803875c2  cmp     r14d, 2
0x1803875c6  jnz     loc_180387519
0x1803875cc  xor     edx, edx; lpSubKey
0x1803875ce  mov     rcx, [r12]; hKey
0x1803875d2  call    cs:__imp_RegDeleteTreeW
0x1803875d8  nop
0x1803875d9  mov     rcx, rbx; Block
0x1803875dc  test    eax, eax
0x1803875de  jz      short loc_180387605
0x1803875e0  call    cs:__imp_free
0x1803875e6  mov     r14d, 80004005h
0x1803875ec  jmp     short loc_18038760E
0x1803875ee  cmp     [rbp+Type], 6
0x1803875f2  jnz     short loc_1803875CC
0x1803875f4  mov     rcx, rbx; Block
0x1803875f7  call    cs:__imp_free
0x1803875fd  mov     r14d, 800705B8h
0x180387603  jmp     short loc_18038760E
0x180387605  call    cs:__imp_free
0x18038760b  xor     r14d, r14d
0x18038760e  lea     rcx, [rdi-18h]; this
0x180387612  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180387617  mov     eax, r14d
0x18038761a  add     rsp, 60h
0x18038761e  pop     r15
0x180387620  pop     r14
0x180387622  pop     r12
0x180387624  pop     rdi
0x180387625  pop     rsi
0x180387626  pop     rbx
0x180387627  pop     rbp
0x180387628  retn
```
