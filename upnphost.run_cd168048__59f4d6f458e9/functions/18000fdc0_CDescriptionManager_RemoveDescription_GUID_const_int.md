# CDescriptionManager::RemoveDescription(_GUID const &,int)

- ea: `0x18000fdc0`
- end: `0x18001020d`
- name: `?RemoveDescription@CDescriptionManager@@UEAAJAEBU_GUID@@H@Z`
- size: `1101`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18000b0d0`
- `0x18000fb0c`
- `0x18000fdc0`
- `0x180010214`
- `0x1800105b0`
- `0x1800106a8`
- `0x180010780`
- `0x18001094c`
- `0x180010b74`
- `0x180010be0`
- `0x180010d88`
- `0x180012d00`
- `0x1800200f4`
- `0x18003b1cc`
- `0x180042774`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ff2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001009a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ff2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001009a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ff3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001007b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001008b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001007b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001008b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001000a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001000a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180010045`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180010045`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001012f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001012f`

## string_xrefs

- `0x18001010a`: `HrRegDeleteKeyTree`
- `0x1800100e8`: `HrRegOpenKeyEx`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::RemoveDescription(CDescriptionManager *this, struct _GUID *a2, int a3)
{
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  CDescriptionManager *v10; // rcx
  unsigned int v11; // eax
  STRSAFE_PCNZWCH v12; // rcx
  unsigned int i; // r10d
  _QWORD *v14; // rdx
  __int64 v15; // rax
  unsigned int v16; // ebx
  unsigned int v17; // r10d
  __int64 v18; // r11
  int v20; // eax
  void *v21; // rbx
  const WCHAR *v22; // rdx
  LSTATUS v23; // eax
  signed int v24; // edi
  int v25; // eax
  bool v26; // zf
  void *Block; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+48h] BYREF

  ATL::CComSafeDeleteCriticalSection::Lock((CDescriptionManager *)((char *)this + 24));
  hKey = 0;
  if ( (int)HrIsAllowedCOMCallLocality(1) < 0 || (int)HrCreateOrOpenDescriptionKey(&hKey) < 0 )
    goto LABEL_2;
  Block = 0;
  v20 = CUString::HrInitFromGUID((CUString *)&Block, a2);
  v21 = Block;
  if ( v20 >= 0 )
  {
    v22 = (const WCHAR *)Block;
    if ( !a3 )
    {
      Block = 0;
      v23 = RegOpenKeyExW(hKey, v22, 0, 0x2001Fu, (PHKEY)&Block);
      v24 = v23;
      if ( v23 > 0 )
        v24 = (unsigned __int16)v23 | 0x80070000;
      if ( v24 < 0 )
      {
        Block = 0;
      }
      else if ( !v24 )
      {
LABEL_33:
        v25 = RegDeleteTreeW((HKEY)Block, L"Files");
        v26 = v25 == 0;
        if ( v25 > 0 )
        {
          v25 = (unsigned __int16)v25 | 0x80070000;
          v26 = v25 == 0;
        }
        if ( !v26 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
            (unsigned int)"HrRegDeleteKeyTree",
            v25);
        RegCloseKey((HKEY)Block);
        goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids,
          (unsigned int)"HrRegOpenKeyEx",
          v24);
      if ( v24 < 0 )
        goto LABEL_40;
      goto LABEL_33;
    }
    HrRegDeleteKeyTree(hKey, (const unsigned __int16 *)Block);
  }
LABEL_40:
  RegCloseKey(hKey);
  free(v21);
LABEL_2:
  Block = 0;
  if ( (int)HrGetDescriptionDocumentPath(a2, (struct CUString *)&Block) >= 0 )
    DeleteFileW((LPCWSTR)Block);
  v6 = CDescriptionManager::HrRD_RemoveFromEventing(this, a2);
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v6);
  v7 = CDescriptionManager::HrRD_RemoveFromDataStructures(this, a2);
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v7);
  v8 = CDescriptionManager::HrRD_CleanupPublication(this, a2);
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v8);
  v9 = HrRemovePresentationVirtualDir(a2);
  v10 = (CDescriptionManager *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v9);
  v11 = CDescriptionManager::Hr_DoStopUrlListening(v10, a2);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v11);
    v12 = WPP_GLOBAL_Control;
  }
  for ( i = 0; ; ++i )
  {
    if ( (signed int)i >= *((_DWORD *)this + 90) )
    {
      v16 = -2147024809;
      goto LABEL_18;
    }
    v14 = (_QWORD *)(*((_QWORD *)this + 44) + 16LL * (int)i);
    v15 = *(_QWORD *)&a2->Data1 - *v14;
    if ( *(_QWORD *)&a2->Data1 == *v14 )
      v15 = *(_QWORD *)a2->Data4 - v14[1];
    if ( !v15 )
      break;
  }
  v16 = CUArray<_GUID>::HrErase((char *)this + 352, i);
  if ( (v16 & 0x80000000) == 0 )
    v16 = CUArray<long>::HrErase(v18 + 16, v17);
  v12 = WPP_GLOBAL_Control;
LABEL_18:
  if ( v12 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v12[14] & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v12 + 2), 103, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v16);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v16 && v12 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v12[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v12 + 2), 104, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids, v16);
  free(Block);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v16;
}

```

## disassembly

```asm
0x18000fdc0  mov     [rsp-28h+arg_8], rbx
0x18000fdc5  mov     [rsp-28h+arg_10], rsi
0x18000fdca  push    rbp
0x18000fdcb  push    rdi
0x18000fdcc  push    r13
0x18000fdce  push    r14
0x18000fdd0  push    r15
0x18000fdd2  mov     rbp, rsp
0x18000fdd5  sub     rsp, 30h
0x18000fdd9  mov     r14, rcx
0x18000fddc  mov     edi, r8d
0x18000fddf  add     rcx, 18h; this
0x18000fde3  mov     rsi, rdx
0x18000fde6  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x18000fdeb  mov     ecx, 1
0x18000fdf0  mov     [rbp+hKey], 0
0x18000fdf8  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18000fdfd  lea     rbx, WPP_GLOBAL_Control
0x18000fe04  test    eax, eax
0x18000fe06  jns     loc_18000FFB0
0x18000fe0c  lea     rdx, [rbp+Block]; struct CUString *
0x18000fe10  mov     [rbp+Block], 0
0x18000fe18  mov     rcx, rsi; struct _GUID *
0x18000fe1b  call    ?HrGetDescriptionDocumentPath@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGetDescriptionDocumentPath(_GUID const &,CUString &)
0x18000fe20  test    eax, eax
0x18000fe22  jns     loc_18001012B
0x18000fe28  mov     rdx, rsi; struct _GUID *
0x18000fe2b  mov     rcx, r14; this
0x18000fe2e  call    ?HrRD_RemoveFromEventing@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::HrRD_RemoveFromEventing(_GUID const &)
0x18000fe33  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe3a  lea     r13, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18000fe41  mov     dil, 40h ; '@'
0x18000fe44  cmp     rcx, rbx
0x18000fe47  jnz     loc_18000FF8D
0x18000fe4d  mov     rdx, rsi; struct _GUID *
0x18000fe50  mov     rcx, r14; this
0x18000fe53  call    ?HrRD_RemoveFromDataStructures@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::HrRD_RemoveFromDataStructures(_GUID const &)
0x18000fe58  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe5f  cmp     rcx, rbx
0x18000fe62  jnz     loc_180010140
0x18000fe68  mov     rdx, rsi; struct _GUID *
0x18000fe6b  mov     rcx, r14; this
0x18000fe6e  call    ?HrRD_CleanupPublication@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::HrRD_CleanupPublication(_GUID const &)
0x18000fe73  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fe7a  cmp     rcx, rbx
0x18000fe7d  jnz     loc_18000FF6A
0x18000fe83  mov     rcx, rsi; Uuid
0x18000fe86  call    ?HrRemovePresentationVirtualDir@@YAJAEBU_GUID@@@Z; HrRemovePresentationVirtualDir(_GUID const &)
0x18000fe8b  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18000fe92  cmp     rcx, rbx
0x18000fe95  jnz     loc_180010163
0x18000fe9b  mov     rdx, rsi; struct _GUID *
0x18000fe9e  call    ?Hr_DoStopUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::Hr_DoStopUrlListening(_GUID const &)
0x18000fea3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000feaa  cmp     rcx, rbx
0x18000fead  jnz     loc_180010186
0x18000feb3  lea     r11, [r14+160h]
0x18000feba  xor     r10d, r10d
0x18000febd  cmp     r10d, [r11+8]
0x18000fec1  jge     loc_18000FF63
0x18000fec7  mov     rax, [rsi]
0x18000feca  movsxd  rdx, r10d
0x18000fecd  shl     rdx, 4
0x18000fed1  add     rdx, [r11]
0x18000fed4  sub     rax, [rdx]
0x18000fed7  jnz     short loc_18000FEE1
0x18000fed9  mov     rax, [rsi+8]
0x18000fedd  sub     rax, [rdx+8]
0x18000fee1  test    rax, rax
0x18000fee4  jz      short loc_18000FEEB
0x18000fee6  inc     r10d
0x18000fee9  jmp     short loc_18000FEBD
0x18000feeb  mov     edx, r10d
0x18000feee  mov     rcx, r11
0x18000fef1  call    ?HrErase@?$CUArray@U_GUID@@@@QEAAJJ@Z; CUArray<_GUID>::HrErase(long)
0x18000fef6  mov     ebx, eax
0x18000fef8  test    eax, eax
0x18000fefa  js      short loc_18000FF0A
0x18000fefc  lea     rcx, [r11+10h]
0x18000ff00  mov     edx, r10d
0x18000ff03  call    ?HrErase@?$CUArray@J@@QEAAJJ@Z; CUArray<long>::HrErase(long)
0x18000ff08  mov     ebx, eax
0x18000ff0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff11  lea     rax, WPP_GLOBAL_Control
0x18000ff18  cmp     rcx, rax
0x18000ff1b  jnz     loc_1800101B0
0x18000ff21  test    ebx, ebx
0x18000ff23  jnz     loc_1800101E1
0x18000ff29  mov     rcx, [rbp+Block]; Block
0x18000ff2d  call    cs:__imp_free
0x18000ff34  nop     dword ptr [rax+rax+00h]
0x18000ff39  lea     rcx, [r14+18h]; lpCriticalSection
0x18000ff3d  call    cs:__imp_LeaveCriticalSection
0x18000ff44  nop     dword ptr [rax+rax+00h]
0x18000ff49  mov     rsi, [rsp+30h+arg_10]
0x18000ff4e  mov     eax, ebx
0x18000ff50  mov     rbx, [rsp+30h+arg_8]
0x18000ff55  add     rsp, 30h
0x18000ff59  pop     r15
0x18000ff5b  pop     r14
0x18000ff5d  pop     r13
0x18000ff5f  pop     rdi
0x18000ff60  pop     rbp
0x18000ff61  retn
0x18000ff63  mov     ebx, 80070057h
0x18000ff68  jmp     short loc_18000FF11
0x18000ff6a  test    [rcx+1Ch], dil
0x18000ff6e  jz      loc_18000FE83
0x18000ff74  mov     rcx, [rcx+10h]
0x18000ff78  mov     edx, 64h ; 'd'
0x18000ff7d  mov     r9d, eax
0x18000ff80  mov     r8, r13
0x18000ff83  call    WPP_SF_d
0x18000ff88  jmp     loc_18000FE83
0x18000ff8d  test    [rcx+1Ch], dil
0x18000ff91  jz      loc_18000FE4D
0x18000ff97  mov     rcx, [rcx+10h]
0x18000ff9b  mov     edx, 62h ; 'b'
0x18000ffa0  mov     r9d, eax
0x18000ffa3  mov     r8, r13
0x18000ffa6  call    WPP_SF_d
0x18000ffab  jmp     loc_18000FE4D
0x18000ffb0  lea     rcx, [rbp+hKey]; phkResult
0x18000ffb4  call    ?HrCreateOrOpenDescriptionKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDescriptionKey(HKEY__ * *)
0x18000ffb9  test    eax, eax
0x18000ffbb  js      loc_18000FE0C
0x18000ffc1  mov     rdx, rsi; struct _GUID *
0x18000ffc4  mov     [rbp+Block], 0
0x18000ffcc  lea     rcx, [rbp+Block]; this
0x18000ffd0  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x18000ffd5  mov     rbx, [rbp+Block]
0x18000ffd9  test    eax, eax
0x18000ffdb  js      loc_180010087
0x18000ffe1  mov     rcx, [rbp+hKey]; HKEY
0x18000ffe5  mov     rdx, rbx; unsigned __int16 *
0x18000ffe8  test    edi, edi
0x18000ffea  jnz     loc_1800100B2
0x18000fff0  lea     rax, [rbp+Block]
0x18000fff4  mov     [rbp+Block], 0
0x18000fffc  mov     r9d, 2001Fh; samDesired
0x180010002  mov     [rsp+30h+phkResult], rax; phkResult
0x180010007  xor     r8d, r8d; ulOptions
0x18001000a  call    cs:__imp_RegOpenKeyExW
0x180010011  nop     dword ptr [rax+rax+00h]
0x180010016  mov     edi, eax
0x180010018  test    eax, eax
0x18001001a  jle     short loc_180010025
0x18001001c  movzx   edi, ax
0x18001001f  or      edi, 80070000h
0x180010025  test    edi, edi
0x180010027  js      loc_1800100C3
0x18001002d  jnz     loc_1800100CB
0x180010033  lea     r13, WPP_GLOBAL_Control
0x18001003a  mov     rcx, [rbp+Block]; hKey
0x18001003e  lea     rdx, SubKey; "Files"
0x180010045  call    cs:__imp_RegDeleteTreeW
0x18001004c  nop     dword ptr [rax+rax+00h]
0x180010051  test    eax, eax
0x180010053  jle     short loc_18001005F
0x180010055  movzx   eax, ax
0x180010058  or      eax, 80070000h
0x18001005d  test    eax, eax
0x18001005f  jz      short loc_180010077
0x180010061  mov     rcx, cs:WPP_GLOBAL_Control
0x180010068  cmp     rcx, r13
0x18001006b  jz      short loc_180010077
0x18001006d  test    byte ptr [rcx+1Ch], 1
0x180010071  jnz     loc_180010106
0x180010077  mov     rcx, [rbp+Block]; hKey
0x18001007b  call    cs:__imp_RegCloseKey
0x180010082  nop     dword ptr [rax+rax+00h]
0x180010087  mov     rcx, [rbp+hKey]; hKey
0x18001008b  call    cs:__imp_RegCloseKey
0x180010092  nop     dword ptr [rax+rax+00h]
0x180010097  mov     rcx, rbx; Block
0x18001009a  call    cs:__imp_free
0x1800100a1  nop     dword ptr [rax+rax+00h]
0x1800100a6  lea     rbx, WPP_GLOBAL_Control
0x1800100ad  jmp     loc_18000FE0C
0x1800100b2  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x1800100b7  jmp     short loc_180010087
0x1800100b9  test    edi, edi
0x1800100bb  jns     loc_18001003A
0x1800100c1  jmp     short loc_180010087
0x1800100c3  mov     [rbp+Block], 0
0x1800100cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100d2  lea     r13, WPP_GLOBAL_Control
0x1800100d9  cmp     rcx, r13
0x1800100dc  jz      short loc_1800100B9
0x1800100de  test    byte ptr [rcx+1Ch], 1
0x1800100e2  jz      short loc_1800100B9
0x1800100e4  mov     rcx, [rcx+10h]
0x1800100e8  lea     r9, aHrregopenkeyex; "HrRegOpenKeyEx"
0x1800100ef  mov     edx, 0Fh
0x1800100f4  mov     dword ptr [rsp+30h+phkResult], edi
0x1800100f8  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x1800100ff  call    WPP_SF_sd
0x180010104  jmp     short loc_1800100B9
0x180010106  mov     rcx, [rcx+10h]
0x18001010a  lea     r9, aHrregdeletekey; "HrRegDeleteKeyTree"
0x180010111  mov     edx, 0Ch
0x180010116  mov     dword ptr [rsp+30h+phkResult], eax
0x18001011a  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x180010121  call    WPP_SF_sd
0x180010126  jmp     loc_180010077
0x18001012b  mov     rcx, [rbp+Block]; lpFileName
0x18001012f  call    cs:__imp_DeleteFileW
0x180010136  nop     dword ptr [rax+rax+00h]
0x18001013b  jmp     loc_18000FE28
0x180010140  test    [rcx+1Ch], dil
0x180010144  jz      loc_18000FE68
0x18001014a  mov     rcx, [rcx+10h]
0x18001014e  mov     edx, 63h ; 'c'
0x180010153  mov     r9d, eax
0x180010156  mov     r8, r13
0x180010159  call    WPP_SF_d
0x18001015e  jmp     loc_18000FE68
0x180010163  test    [rcx+1Ch], dil
0x180010167  jz      loc_18000FE9B
0x18001016d  mov     rcx, [rcx+10h]
0x180010171  mov     edx, 65h ; 'e'
0x180010176  mov     r9d, eax
0x180010179  mov     r8, r13
0x18001017c  call    WPP_SF_d
0x180010181  jmp     loc_18000FE9B
0x180010186  test    [rcx+1Ch], dil
0x18001018a  jz      loc_18000FEB3
0x180010190  mov     rcx, [rcx+10h]
0x180010194  mov     edx, 66h ; 'f'
0x180010199  mov     r9d, eax
0x18001019c  mov     r8, r13
0x18001019f  call    WPP_SF_d
0x1800101a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101ab  jmp     loc_18000FEB3
0x1800101b0  test    [rcx+1Ch], dil
0x1800101b4  jz      loc_18000FF21
0x1800101ba  mov     rcx, [rcx+10h]
0x1800101be  mov     edx, 67h ; 'g'
0x1800101c3  mov     r9d, ebx
0x1800101c6  mov     r8, r13
0x1800101c9  call    WPP_SF_d
0x1800101ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101d5  lea     rax, WPP_GLOBAL_Control
0x1800101dc  jmp     loc_18000FF21
0x1800101e1  cmp     rcx, rax
0x1800101e4  jz      loc_18000FF29
0x1800101ea  test    byte ptr [rcx+1Ch], 1
0x1800101ee  jz      loc_18000FF29
0x1800101f4  mov     rcx, [rcx+10h]
0x1800101f8  mov     edx, 68h ; 'h'
0x1800101fd  mov     r9d, ebx
0x180010200  mov     r8, r13
0x180010203  call    WPP_SF_d
0x180010208  jmp     loc_18000FF29
```
