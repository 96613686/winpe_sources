# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x14001bf80`
- end: `0x14001c2df`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14001bcec`

## callees

- `0x1400088cc`
- `0x14000e550`
- `0x140013bac`
- `0x140013fdc`
- `0x140014490`
- `0x1400169b8`
- `0x1400171ec`
- `0x140017a8c`
- `0x14001bf80`
- `0x14001cdb0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001c164`
- `ADVAPI32!RegOpenKeyExW` at `0x14001c164`
- `ADVAPI32!RegCloseKey` at `0x14001c1cc`
- `ADVAPI32!RegCloseKey` at `0x14001c211`
- `ADVAPI32!RegCloseKey` at `0x14001c1cc`
- `ADVAPI32!RegCloseKey` at `0x14001c211`
- `ADVAPI32!RegQueryValueExW` at `0x14001c1fe`
- `ADVAPI32!RegQueryValueExW` at `0x14001c1fe`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14001c1a6`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14001c1a6`
- `ADVAPI32!RegDeleteTreeW` at `0x14001c26f`
- `ADVAPI32!RegDeleteTreeW` at `0x14001c26f`
- `KERNEL32!WaitForSingleObject` at `0x14001c222`
- `KERNEL32!WaitForSingleObject` at `0x14001c222`
- `KERNEL32!GetLastError` at `0x14001c117`
- `KERNEL32!GetLastError` at `0x14001c117`
- `KERNEL32!CloseHandle` at `0x14001c17a`
- `KERNEL32!CloseHandle` at `0x14001c1bc`
- `KERNEL32!CloseHandle` at `0x14001c233`
- `KERNEL32!CloseHandle` at `0x14001c17a`
- `KERNEL32!CloseHandle` at `0x14001c1bc`
- `KERNEL32!CloseHandle` at `0x14001c233`
- `KERNEL32!CreateEventW` at `0x14001c103`
- `KERNEL32!CreateEventW` at `0x14001c103`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c07d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c0b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c138`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c246`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c283`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c2a0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c2b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c07d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c0b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c138`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c246`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c283`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c2a0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001c2b4`

## string_xrefs

- `0x14001c1f3`: `SymbolicLinkValue`
- `0x14001c0ee`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`
- `0x14001c033`: `%s\ATConfig`
- `0x14001c097`: `%s\ATConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SettingsCopier::DeleteATSettings(HKEY *a1)
{
  void *v2; // rbx
  __int64 v3; // rdx
  unsigned __int16 *v4; // rdi
  int *v5; // rbx
  __int64 v6; // rdi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  LSTATUS v10; // r14d
  unsigned __int64 v11; // rdx
  __int64 v13; // rsi
  const WCHAR *v14; // r14
  void *v15; // rcx
  HANDLE EventW; // r15
  signed int LastError; // eax
  DWORD v18; // esi
  LSTATUS v19; // eax
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  __int64 v24; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v27; // [rsp+B8h] [rbp+58h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v27);
  v22 = 0;
  v23 = 0;
  v2 = 0;
  Block = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !IsInteractiveUser() )
  {
    v13 = -2147483647;
    v14 = SettingsCopier::_ATConfigKeyString;
    v4 = v27;
LABEL_17:
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError <= 0 )
      {
LABEL_21:
        free(v2);
        goto LABEL_37;
      }
      v10 = (unsigned __int16)LastError;
LABEL_20:
      v10 |= 0x80070000;
      goto LABEL_21;
    }
    v10 = RegOpenKeyExW((HKEY)v13, v14, 8u, 0x20019u, &hKey);
    if ( v10 )
    {
      CloseHandle(EventW);
LABEL_24:
      if ( v10 <= 0 )
        goto LABEL_21;
      v10 = (unsigned __int16)v10;
      goto LABEL_20;
    }
    v10 = RegNotifyChangeKeyValue(hKey, 0, 5u, EventW, 1);
    if ( v10 )
    {
      CloseHandle(EventW);
      RegCloseKey(hKey);
      goto LABEL_24;
    }
    v10 = RegQueryValueExW(hKey, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    v18 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v18 )
    {
      free(v2);
      v10 = -2147023590;
      goto LABEL_37;
    }
    if ( v10 )
    {
      if ( v10 != 2 )
        goto LABEL_24;
    }
    else if ( Type == 6 )
    {
      free(v2);
      v10 = -2147023432;
      goto LABEL_37;
    }
    v19 = RegDeleteTreeW(*a1, 0);
    v15 = v2;
    if ( !v19 )
    {
      free(v2);
      v10 = 0;
      goto LABEL_37;
    }
LABEL_33:
    free(v15);
    v10 = -2147467259;
    goto LABEL_37;
  }
  v3 = *(_QWORD *)CATUtils::SessionKeyString(&v24);
  v4 = v27;
  v5 = (int *)(v27 - 12);
  if ( (unsigned __int16 *)(v3 - 24) != v27 - 12 )
  {
    if ( v5[4] >= 0 && *(_QWORD *)(v3 - 24) == *(_QWORD *)v5 )
    {
      v6 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v5);
      v4 = (unsigned __int16 *)(v6 + 24);
      v27 = v4;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v27, v3, *(unsigned int *)(v3 - 16));
      v4 = v27;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  if ( (int)StringCchLengthW(SettingsCopier::_ATSessionConfigKeyString, v7, &v22) < 0
    || (int)StringCchLengthW(v4, v8, &v23) < 0
    || (v9 = v22 + v23, v22 + v23 < v22) )
  {
    v15 = 0;
    goto LABEL_33;
  }
  if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v22 + v23) )
  {
    v11 = v9;
    v2 = Block;
    if ( StringCchPrintfW((unsigned __int16 *)Block, v11, SettingsCopier::_ATSessionConfigKeyString, v4) < 0 )
    {
      free(v2);
      ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
      return 2147500037LL;
    }
    v13 = -2147483646;
    v14 = (const WCHAR *)v2;
    goto LABEL_17;
  }
  free(Block);
  v10 = -2147024882;
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001bf80  push    rbp
0x14001bf82  push    rbx
0x14001bf83  push    rsi
0x14001bf84  push    rdi
0x14001bf85  push    r12
0x14001bf87  push    r14
0x14001bf89  push    r15
0x14001bf8b  mov     rbp, rsp
0x14001bf8e  sub     rsp, 60h
0x14001bf92  mov     r12, rcx
0x14001bf95  lea     rcx, [rbp+arg_18]
0x14001bf99  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x14001bf9e  nop
0x14001bf9f  mov     [rbp+var_20], 0
0x14001bfa7  mov     [rbp+var_18], 0
0x14001bfaf  xor     ebx, ebx
0x14001bfb1  mov     [rbp+Block], rbx
0x14001bfb5  mov     [rbp+hKey], rbx
0x14001bfb9  mov     [rbp+Type], ebx
0x14001bfbc  mov     [rbp+cbData], ebx
0x14001bfbf  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14001bfc4  test    eax, eax
0x14001bfc6  jz      loc_14001C0E7
0x14001bfcc  lea     rcx, [rbp+var_10]
0x14001bfd0  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14001bfd5  mov     rdx, [rax]
0x14001bfd8  lea     rcx, [rdx-18h]
0x14001bfdc  mov     rdi, [rbp+arg_18]
0x14001bfe0  lea     rbx, [rdi-18h]
0x14001bfe4  cmp     rcx, rbx
0x14001bfe7  jz      short loc_14001C022
0x14001bfe9  cmp     dword ptr [rbx+10h], 0
0x14001bfed  jl      short loc_14001C011
0x14001bfef  mov     rax, [rbx]
0x14001bff2  cmp     [rcx], rax
0x14001bff5  jnz     short loc_14001C011
0x14001bff7  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001bffc  mov     rdi, rax
0x14001bfff  mov     rcx, rbx; this
0x14001c002  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c007  add     rdi, 18h
0x14001c00b  mov     [rbp+arg_18], rdi
0x14001c00f  jmp     short loc_14001C022
0x14001c011  mov     r8d, [rdx-10h]
0x14001c015  lea     rcx, [rbp+arg_18]
0x14001c019  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14001c01e  mov     rdi, [rbp+arg_18]
0x14001c022  mov     rcx, [rbp+var_10]
0x14001c026  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001c02a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c02f  lea     r8, [rbp+var_20]; unsigned __int64 *
0x14001c033  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x14001c03a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001c03f  test    eax, eax
0x14001c041  js      loc_14001C0E0
0x14001c047  lea     r8, [rbp+var_18]; unsigned __int64 *
0x14001c04b  mov     rcx, rdi; unsigned __int16 *
0x14001c04e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001c053  test    eax, eax
0x14001c055  js      loc_14001C0E0
0x14001c05b  mov     rbx, [rbp+var_18]
0x14001c05f  add     rbx, [rbp+var_20]
0x14001c063  cmp     rbx, [rbp+var_20]
0x14001c067  jb      short loc_14001C0E0
0x14001c069  mov     rdx, rbx
0x14001c06c  lea     rcx, [rbp+Block]
0x14001c070  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x14001c075  test    al, al
0x14001c077  jnz     short loc_14001C094
0x14001c079  mov     rcx, [rbp+Block]; Block
0x14001c07d  call    cs:__imp_free
0x14001c084  nop     dword ptr [rax+rax+00h]
0x14001c089  mov     r14d, 8007000Eh
0x14001c08f  jmp     loc_14001C2C3
0x14001c094  mov     r9, rdi
0x14001c097  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x14001c09e  mov     rdx, rbx; unsigned __int64
0x14001c0a1  mov     rbx, [rbp+Block]
0x14001c0a5  mov     rcx, rbx; unsigned __int16 *
0x14001c0a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001c0ad  test    eax, eax
0x14001c0af  jns     short loc_14001C0D4
0x14001c0b1  mov     rcx, rbx; Block
0x14001c0b4  call    cs:__imp_free
0x14001c0bb  nop     dword ptr [rax+rax+00h]
0x14001c0c0  nop
0x14001c0c1  lea     rcx, [rdi-18h]; this
0x14001c0c5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c0ca  mov     eax, 80004005h
0x14001c0cf  jmp     loc_14001C2CF
0x14001c0d4  mov     rsi, 0FFFFFFFF80000002h
0x14001c0db  mov     r14, rbx
0x14001c0de  jmp     short loc_14001C0F9
0x14001c0e0  xor     ecx, ecx
0x14001c0e2  jmp     loc_14001C283
0x14001c0e7  mov     rsi, 0FFFFFFFF80000001h
0x14001c0ee  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001c0f5  mov     rdi, [rbp+arg_18]
0x14001c0f9  xor     r9d, r9d; lpName
0x14001c0fc  xor     r8d, r8d; bInitialState
0x14001c0ff  xor     edx, edx; bManualReset
0x14001c101  xor     ecx, ecx; lpEventAttributes
0x14001c103  call    cs:__imp_CreateEventW
0x14001c10a  nop     dword ptr [rax+rax+00h]
0x14001c10f  mov     r15, rax
0x14001c112  test    rax, rax
0x14001c115  jnz     short loc_14001C149
0x14001c117  call    cs:__imp_GetLastError
0x14001c11e  nop     dword ptr [rax+rax+00h]
0x14001c123  mov     r14d, eax
0x14001c126  test    eax, eax
0x14001c128  jle     short loc_14001C135
0x14001c12a  movzx   r14d, ax
0x14001c12e  or      r14d, 80070000h
0x14001c135  mov     rcx, rbx; Block
0x14001c138  call    cs:__imp_free
0x14001c13f  nop     dword ptr [rax+rax+00h]
0x14001c144  jmp     loc_14001C2C3
0x14001c149  lea     rax, [rbp+hKey]
0x14001c14d  mov     [rsp+60h+phkResult], rax; phkResult
0x14001c152  mov     r9d, 20019h; samDesired
0x14001c158  mov     r8d, 8; ulOptions
0x14001c15e  mov     rdx, r14; lpSubKey
0x14001c161  mov     rcx, rsi; hKey
0x14001c164  call    cs:__imp_RegOpenKeyExW
0x14001c16b  nop     dword ptr [rax+rax+00h]
0x14001c170  mov     r14d, eax
0x14001c173  test    eax, eax
0x14001c175  jz      short loc_14001C191
0x14001c177  mov     rcx, r15; hObject
0x14001c17a  call    cs:__imp_CloseHandle
0x14001c181  nop     dword ptr [rax+rax+00h]
0x14001c186  test    r14d, r14d
0x14001c189  jle     short loc_14001C135
0x14001c18b  movzx   r14d, r14w
0x14001c18f  jmp     short loc_14001C12E
0x14001c191  mov     dword ptr [rsp+60h+phkResult], 1; fAsynchronous
0x14001c199  mov     r9, r15; hEvent
0x14001c19c  xor     edx, edx; bWatchSubtree
0x14001c19e  lea     r8d, [rdx+5]; dwNotifyFilter
0x14001c1a2  mov     rcx, [rbp+hKey]; hKey
0x14001c1a6  call    cs:__imp_RegNotifyChangeKeyValue
0x14001c1ad  nop     dword ptr [rax+rax+00h]
0x14001c1b2  mov     r14d, eax
0x14001c1b5  test    eax, eax
0x14001c1b7  jz      short loc_14001C1DA
0x14001c1b9  mov     rcx, r15; hObject
0x14001c1bc  call    cs:__imp_CloseHandle
0x14001c1c3  nop     dword ptr [rax+rax+00h]
0x14001c1c8  mov     rcx, [rbp+hKey]; hKey
0x14001c1cc  call    cs:__imp_RegCloseKey
0x14001c1d3  nop     dword ptr [rax+rax+00h]
0x14001c1d8  jmp     short loc_14001C186
0x14001c1da  lea     rax, [rbp+cbData]
0x14001c1de  mov     [rsp+60h+lpcbData], rax; lpcbData
0x14001c1e3  mov     [rsp+60h+phkResult], 0; lpData
0x14001c1ec  lea     r9, [rbp+Type]; lpType
0x14001c1f0  xor     r8d, r8d; lpReserved
0x14001c1f3  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x14001c1fa  mov     rcx, [rbp+hKey]; hKey
0x14001c1fe  call    cs:__imp_RegQueryValueExW
0x14001c205  nop     dword ptr [rax+rax+00h]
0x14001c20a  mov     r14d, eax
0x14001c20d  mov     rcx, [rbp+hKey]; hKey
0x14001c211  call    cs:__imp_RegCloseKey
0x14001c218  nop     dword ptr [rax+rax+00h]
0x14001c21d  xor     edx, edx; dwMilliseconds
0x14001c21f  mov     rcx, r15; hHandle
0x14001c222  call    cs:__imp_WaitForSingleObject
0x14001c229  nop     dword ptr [rax+rax+00h]
0x14001c22e  mov     esi, eax
0x14001c230  mov     rcx, r15; hObject
0x14001c233  call    cs:__imp_CloseHandle
0x14001c23a  nop     dword ptr [rax+rax+00h]
0x14001c23f  test    esi, esi
0x14001c241  jnz     short loc_14001C25A
0x14001c243  mov     rcx, rbx; Block
0x14001c246  call    cs:__imp_free
0x14001c24d  nop     dword ptr [rax+rax+00h]
0x14001c252  mov     r14d, 8007051Ah
0x14001c258  jmp     short loc_14001C2C3
0x14001c25a  test    r14d, r14d
0x14001c25d  jz      short loc_14001C297
0x14001c25f  cmp     r14d, 2
0x14001c263  jnz     loc_14001C186
0x14001c269  xor     edx, edx; lpSubKey
0x14001c26b  mov     rcx, [r12]; hKey
0x14001c26f  call    cs:__imp_RegDeleteTreeW
0x14001c276  nop     dword ptr [rax+rax+00h]
0x14001c27b  nop
0x14001c27c  mov     rcx, rbx; Block
0x14001c27f  test    eax, eax
0x14001c281  jz      short loc_14001C2B4
0x14001c283  call    cs:__imp_free
0x14001c28a  nop     dword ptr [rax+rax+00h]
0x14001c28f  mov     r14d, 80004005h
0x14001c295  jmp     short loc_14001C2C3
0x14001c297  cmp     [rbp+Type], 6
0x14001c29b  jnz     short loc_14001C269
0x14001c29d  mov     rcx, rbx; Block
0x14001c2a0  call    cs:__imp_free
0x14001c2a7  nop     dword ptr [rax+rax+00h]
0x14001c2ac  mov     r14d, 800705B8h
0x14001c2b2  jmp     short loc_14001C2C3
0x14001c2b4  call    cs:__imp_free
0x14001c2bb  nop     dword ptr [rax+rax+00h]
0x14001c2c0  xor     r14d, r14d
0x14001c2c3  lea     rcx, [rdi-18h]; this
0x14001c2c7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001c2cc  mov     eax, r14d
0x14001c2cf  add     rsp, 60h
0x14001c2d3  pop     r15
0x14001c2d5  pop     r14
0x14001c2d7  pop     r12
0x14001c2d9  pop     rdi
0x14001c2da  pop     rsi
0x14001c2db  pop     rbx
0x14001c2dc  pop     rbp
0x14001c2dd  retn
```
