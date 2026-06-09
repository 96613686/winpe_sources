# CDescriptionManager::RemoveDescription(_GUID const &,int)

- ea: `0x18001b060`
- end: `0x18001b46c`
- name: `?RemoveDescription@CDescriptionManager@@UEAAJAEBU_GUID@@H@Z`
- size: `1036`
- prototype: `__int64 __fastcall(CDescriptionManager *__hidden this, const struct _GUID *, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callees

- `0x18000db4c`
- `0x180013180`
- `0x180016d5c`
- `0x18001add0`
- `0x18001b060`
- `0x18001b474`
- `0x18001b7ac`
- `0x18001b890`
- `0x18001b960`
- `0x18001bb18`
- `0x18001bd14`
- `0x18001bd7c`
- `0x18001bf14`
- `0x18001d100`
- `0x180038ce4`
- `0x18003fea4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b1cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b309`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b1cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b309`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b1d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b2f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b2f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b300`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b29d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b29d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001b2ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001b2ca`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b394`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b394`

## string_xrefs

- `0x18001b36f`: `HrRegDeleteKeyTree`
- `0x18001b34d`: `HrRegOpenKeyEx`

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
0x18001b060  mov     [rsp-28h+arg_8], rbx
0x18001b065  mov     [rsp-28h+arg_10], rsi
0x18001b06a  push    rbp
0x18001b06b  push    rdi
0x18001b06c  push    r13
0x18001b06e  push    r14
0x18001b070  push    r15
0x18001b072  mov     rbp, rsp
0x18001b075  sub     rsp, 30h
0x18001b079  mov     r14, rcx
0x18001b07c  mov     edi, r8d
0x18001b07f  add     rcx, 18h; this
0x18001b083  mov     rsi, rdx
0x18001b086  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x18001b08b  mov     ecx, 1
0x18001b090  mov     [rbp+hKey], 0
0x18001b098  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18001b09d  lea     rbx, WPP_GLOBAL_Control
0x18001b0a4  test    eax, eax
0x18001b0a6  jns     loc_18001B243
0x18001b0ac  lea     rdx, [rbp+Block]; struct CUString *
0x18001b0b0  mov     [rbp+Block], 0
0x18001b0b8  mov     rcx, rsi; struct _GUID *
0x18001b0bb  call    ?HrGetDescriptionDocumentPath@@YAJAEBU_GUID@@AEAVCUString@@@Z; HrGetDescriptionDocumentPath(_GUID const &,CUString &)
0x18001b0c0  test    eax, eax
0x18001b0c2  jns     loc_18001B390
0x18001b0c8  mov     rdx, rsi; struct _GUID *
0x18001b0cb  mov     rcx, r14; this
0x18001b0ce  call    ?HrRD_RemoveFromEventing@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::HrRD_RemoveFromEventing(_GUID const &)
0x18001b0d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0da  lea     r13, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x18001b0e1  mov     dil, 40h ; '@'
0x18001b0e4  cmp     rcx, rbx
0x18001b0e7  jnz     loc_18001B220
0x18001b0ed  mov     rdx, rsi; struct _GUID *
0x18001b0f0  mov     rcx, r14; this
0x18001b0f3  call    ?HrRD_RemoveFromDataStructures@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::HrRD_RemoveFromDataStructures(_GUID const &)
0x18001b0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0ff  cmp     rcx, rbx
0x18001b102  jnz     loc_18001B39F
0x18001b108  mov     rdx, rsi; struct _GUID *
0x18001b10b  mov     rcx, r14; this
0x18001b10e  call    ?HrRD_CleanupPublication@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::HrRD_CleanupPublication(_GUID const &)
0x18001b113  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b11a  cmp     rcx, rbx
0x18001b11d  jnz     loc_18001B1FD
0x18001b123  mov     rcx, rsi; Uuid
0x18001b126  call    ?HrRemovePresentationVirtualDir@@YAJAEBU_GUID@@@Z; HrRemovePresentationVirtualDir(_GUID const &)
0x18001b12b  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18001b132  cmp     rcx, rbx
0x18001b135  jnz     loc_18001B3C2
0x18001b13b  mov     rdx, rsi; struct _GUID *
0x18001b13e  call    ?Hr_DoStopUrlListening@CDescriptionManager@@AEAAJAEBU_GUID@@@Z; CDescriptionManager::Hr_DoStopUrlListening(_GUID const &)
0x18001b143  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b14a  cmp     rcx, rbx
0x18001b14d  jnz     loc_18001B3E5
0x18001b153  lea     r11, [r14+160h]
0x18001b15a  xor     r10d, r10d
0x18001b15d  cmp     r10d, [r11+8]
0x18001b161  jge     loc_18001B1F6
0x18001b167  mov     rax, [rsi]
0x18001b16a  movsxd  rdx, r10d
0x18001b16d  shl     rdx, 4
0x18001b171  add     rdx, [r11]
0x18001b174  sub     rax, [rdx]
0x18001b177  jnz     short loc_18001B181
0x18001b179  mov     rax, [rsi+8]
0x18001b17d  sub     rax, [rdx+8]
0x18001b181  test    rax, rax
0x18001b184  jz      short loc_18001B18B
0x18001b186  inc     r10d
0x18001b189  jmp     short loc_18001B15D
0x18001b18b  mov     edx, r10d
0x18001b18e  mov     rcx, r11
0x18001b191  call    ?HrErase@?$CUArray@U_GUID@@@@QEAAJJ@Z; CUArray<_GUID>::HrErase(long)
0x18001b196  mov     ebx, eax
0x18001b198  test    eax, eax
0x18001b19a  js      short loc_18001B1AA
0x18001b19c  lea     rcx, [r11+10h]
0x18001b1a0  mov     edx, r10d
0x18001b1a3  call    ?HrErase@?$CUArray@J@@QEAAJJ@Z; CUArray<long>::HrErase(long)
0x18001b1a8  mov     ebx, eax
0x18001b1aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1b1  lea     rax, WPP_GLOBAL_Control
0x18001b1b8  cmp     rcx, rax
0x18001b1bb  jnz     loc_18001B40F
0x18001b1c1  test    ebx, ebx
0x18001b1c3  jnz     loc_18001B440
0x18001b1c9  mov     rcx, [rbp+Block]; Block
0x18001b1cd  call    cs:__imp_free
0x18001b1d3  lea     rcx, [r14+18h]; lpCriticalSection
0x18001b1d7  call    cs:__imp_LeaveCriticalSection
0x18001b1dd  mov     rsi, [rsp+30h+arg_10]
0x18001b1e2  mov     eax, ebx
0x18001b1e4  mov     rbx, [rsp+30h+arg_8]
0x18001b1e9  add     rsp, 30h
0x18001b1ed  pop     r15
0x18001b1ef  pop     r14
0x18001b1f1  pop     r13
0x18001b1f3  pop     rdi
0x18001b1f4  pop     rbp
0x18001b1f5  retn
0x18001b1f6  mov     ebx, 80070057h
0x18001b1fb  jmp     short loc_18001B1B1
0x18001b1fd  test    [rcx+1Ch], dil
0x18001b201  jz      loc_18001B123
0x18001b207  mov     rcx, [rcx+10h]
0x18001b20b  mov     edx, 64h ; 'd'
0x18001b210  mov     r9d, eax
0x18001b213  mov     r8, r13
0x18001b216  call    WPP_SF_d
0x18001b21b  jmp     loc_18001B123
0x18001b220  test    [rcx+1Ch], dil
0x18001b224  jz      loc_18001B0ED
0x18001b22a  mov     rcx, [rcx+10h]
0x18001b22e  mov     edx, 62h ; 'b'
0x18001b233  mov     r9d, eax
0x18001b236  mov     r8, r13
0x18001b239  call    WPP_SF_d
0x18001b23e  jmp     loc_18001B0ED
0x18001b243  lea     rcx, [rbp+hKey]; phkResult
0x18001b247  call    ?HrCreateOrOpenDescriptionKey@@YAJPEAPEAUHKEY__@@@Z; HrCreateOrOpenDescriptionKey(HKEY__ * *)
0x18001b24c  test    eax, eax
0x18001b24e  js      loc_18001B0AC
0x18001b254  mov     rdx, rsi; struct _GUID *
0x18001b257  mov     [rbp+Block], 0
0x18001b25f  lea     rcx, [rbp+Block]; this
0x18001b263  call    ?HrInitFromGUID@CUString@@QEAAJAEBU_GUID@@@Z; CUString::HrInitFromGUID(_GUID const &)
0x18001b268  mov     rbx, [rbp+Block]
0x18001b26c  test    eax, eax
0x18001b26e  js      loc_18001B2FC
0x18001b274  mov     rcx, [rbp+hKey]; HKEY
0x18001b278  mov     rdx, rbx; unsigned __int16 *
0x18001b27b  test    edi, edi
0x18001b27d  jnz     loc_18001B31B
0x18001b283  lea     rax, [rbp+Block]
0x18001b287  mov     [rbp+Block], 0
0x18001b28f  mov     r9d, 2001Fh; samDesired
0x18001b295  mov     [rsp+30h+phkResult], rax; phkResult
0x18001b29a  xor     r8d, r8d; ulOptions
0x18001b29d  call    cs:__imp_RegOpenKeyExW
0x18001b2a3  mov     edi, eax
0x18001b2a5  test    eax, eax
0x18001b2a7  jle     short loc_18001B2B2
0x18001b2a9  movzx   edi, ax
0x18001b2ac  or      edi, 80070000h
0x18001b2b2  test    edi, edi
0x18001b2b4  js      short loc_18001B328
0x18001b2b6  jnz     short loc_18001B330
0x18001b2b8  lea     r13, WPP_GLOBAL_Control
0x18001b2bf  mov     rcx, [rbp+Block]; hKey
0x18001b2c3  lea     rdx, SubKey; "Files"
0x18001b2ca  call    cs:__imp_RegDeleteTreeW
0x18001b2d0  test    eax, eax
0x18001b2d2  jle     short loc_18001B2DE
0x18001b2d4  movzx   eax, ax
0x18001b2d7  or      eax, 80070000h
0x18001b2dc  test    eax, eax
0x18001b2de  jz      short loc_18001B2F2
0x18001b2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2e7  cmp     rcx, r13
0x18001b2ea  jz      short loc_18001B2F2
0x18001b2ec  test    byte ptr [rcx+1Ch], 1
0x18001b2f0  jnz     short loc_18001B36B
0x18001b2f2  mov     rcx, [rbp+Block]; hKey
0x18001b2f6  call    cs:__imp_RegCloseKey
0x18001b2fc  mov     rcx, [rbp+hKey]; hKey
0x18001b300  call    cs:__imp_RegCloseKey
0x18001b306  mov     rcx, rbx; Block
0x18001b309  call    cs:__imp_free
0x18001b30f  lea     rbx, WPP_GLOBAL_Control
0x18001b316  jmp     loc_18001B0AC
0x18001b31b  call    ?HrRegDeleteKeyTree@@YAJPEAUHKEY__@@PEBG@Z; HrRegDeleteKeyTree(HKEY__ *,ushort const *)
0x18001b320  jmp     short loc_18001B2FC
0x18001b322  test    edi, edi
0x18001b324  jns     short loc_18001B2BF
0x18001b326  jmp     short loc_18001B2FC
0x18001b328  mov     [rbp+Block], 0
0x18001b330  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b337  lea     r13, WPP_GLOBAL_Control
0x18001b33e  cmp     rcx, r13
0x18001b341  jz      short loc_18001B322
0x18001b343  test    byte ptr [rcx+1Ch], 1
0x18001b347  jz      short loc_18001B322
0x18001b349  mov     rcx, [rcx+10h]
0x18001b34d  lea     r9, aHrregopenkeyex; "HrRegOpenKeyEx"
0x18001b354  mov     edx, 0Fh
0x18001b359  mov     dword ptr [rsp+30h+phkResult], edi
0x18001b35d  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001b364  call    WPP_SF_sd
0x18001b369  jmp     short loc_18001B322
0x18001b36b  mov     rcx, [rcx+10h]
0x18001b36f  lea     r9, aHrregdeletekey; "HrRegDeleteKeyTree"
0x18001b376  mov     edx, 0Ch
0x18001b37b  mov     dword ptr [rsp+30h+phkResult], eax
0x18001b37f  lea     r8, WPP_c680b5d87c9d36903333b9725f9279d1_Traceguids
0x18001b386  call    WPP_SF_sd
0x18001b38b  jmp     loc_18001B2F2
0x18001b390  mov     rcx, [rbp+Block]; lpFileName
0x18001b394  call    cs:__imp_DeleteFileW
0x18001b39a  jmp     loc_18001B0C8
0x18001b39f  test    [rcx+1Ch], dil
0x18001b3a3  jz      loc_18001B108
0x18001b3a9  mov     rcx, [rcx+10h]
0x18001b3ad  mov     edx, 63h ; 'c'
0x18001b3b2  mov     r9d, eax
0x18001b3b5  mov     r8, r13
0x18001b3b8  call    WPP_SF_d
0x18001b3bd  jmp     loc_18001B108
0x18001b3c2  test    [rcx+1Ch], dil
0x18001b3c6  jz      loc_18001B13B
0x18001b3cc  mov     rcx, [rcx+10h]
0x18001b3d0  mov     edx, 65h ; 'e'
0x18001b3d5  mov     r9d, eax
0x18001b3d8  mov     r8, r13
0x18001b3db  call    WPP_SF_d
0x18001b3e0  jmp     loc_18001B13B
0x18001b3e5  test    [rcx+1Ch], dil
0x18001b3e9  jz      loc_18001B153
0x18001b3ef  mov     rcx, [rcx+10h]
0x18001b3f3  mov     edx, 66h ; 'f'
0x18001b3f8  mov     r9d, eax
0x18001b3fb  mov     r8, r13
0x18001b3fe  call    WPP_SF_d
0x18001b403  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b40a  jmp     loc_18001B153
0x18001b40f  test    [rcx+1Ch], dil
0x18001b413  jz      loc_18001B1C1
0x18001b419  mov     rcx, [rcx+10h]
0x18001b41d  mov     edx, 67h ; 'g'
0x18001b422  mov     r9d, ebx
0x18001b425  mov     r8, r13
0x18001b428  call    WPP_SF_d
0x18001b42d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b434  lea     rax, WPP_GLOBAL_Control
0x18001b43b  jmp     loc_18001B1C1
0x18001b440  cmp     rcx, rax
0x18001b443  jz      loc_18001B1C9
0x18001b449  test    byte ptr [rcx+1Ch], 1
0x18001b44d  jz      loc_18001B1C9
0x18001b453  mov     rcx, [rcx+10h]
0x18001b457  mov     edx, 68h ; 'h'
0x18001b45c  mov     r9d, ebx
0x18001b45f  mov     r8, r13
0x18001b462  call    WPP_SF_d
0x18001b467  jmp     loc_18001B1C9
```
