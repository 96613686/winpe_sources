# CFspEvents::ActionString(__MIDL___MIDL_itf_synchronization_0000_0000_0001,CFspEvents::_FSP_EVENT_ACTION)

- ea: `0x1800f2be8`
- end: `0x1800f2d4b`
- name: `?ActionString@CFspEvents@@AEAAPEBGW4__MIDL___MIDL_itf_synchronization_0000_0000_0001@@W4_FSP_EVENT_ACTION@1@@Z`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800f3224`

## callees

- `0x1800f2be8`

## string_xrefs

- `0x1800f2d43`: `SSA_UPDATE_VERSION_AND_DATA (FSP_EVENT_ACTION_SWAP)`
- `0x1800f2d3b`: `SSA_CREATE (FSP_EVENT_ACTION_CONFLICT_SOURCE_WINS)`
- `0x1800f2c62`: `SSA_CREATE`
- `0x1800f2c5a`: `SSA_UPDATE_VERSION_ONLY`
- `0x1800f2d33`: `SSA_CREATE (FSP_EVENT_ACTION_CONFLICT_DESTINATION_WINS)`
- `0x1800f2c42`: `SSA_DELETE_AND_STORE_TOMBSTONE`
- `0x1800f2c6a`: `SSA_DELETE_AND_REMOVE_TOMBSTONE`
- `0x1800f2c52`: `SSA_UPDATE_VERSION_AND_DATA`
- `0x1800f2c4a`: `SSA_UPDATE_VERSION_AND_MERGE_DATA`
- `0x1800f2c8e`: `SSA_DELETE_CONFLICTING_AND_SAVE_SOURCE_ITEM`
- `0x1800f2c9e`: `SSA_RENAME_SOURCE_AND_UPDATE_VERSION_AND_DATA`
- `0x1800f2c96`: `SSA_RENAME_DESTINATION_AND_UPDATE_VERSION_AND_DATA`
- `0x1800f2d1b`: `SSA_CHANGE_ID_UPDATE_VERSION_AND_DELETE_AND_STORE_TOMBSTONE`
- `0x1800f2d13`: `SSA_CHANGE_ID_UPDATE_VERSION_ONLY`
- `0x1800f2ca6`: `SSA_CHANGE_ID_UPDATE_VERSION_AND_MERGE_DATA`
- `0x1800f2d23`: `SSA_CHANGE_ID_UPDATE_VERSION_AND_SAVE_DATA`
- `0x1800f2cf3`: `SSA_UPDATE_GHOST`
- `0x1800f2d0b`: `SSA_CREATE_GHOST`
- `0x1800f2ceb`: `SSA_DELETE_GHOST_AND_STORE_TOMBSTONE`
- `0x1800f2ce3`: `SSA_DELETE_GHOST_WITHOUT_TOMBSTONE`

## pseudocode

```c
const wchar_t *__fastcall CFspEvents::ActionString(__int64 a1, int a2, int a3)
{
  int v3; // r8d
  int v4; // r8d
  int v5; // r8d
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx

  v3 = a3 - 1;
  if ( !v3 )
    return L"SSA_UPDATE_VERSION_AND_DATA (FSP_EVENT_ACTION_SWAP)";
  v4 = v3 - 1;
  if ( !v4 )
    return L"SSA_CREATE (FSP_EVENT_ACTION_CONFLICT_SOURCE_WINS)";
  v5 = v4 - 1;
  if ( !v5 )
    return L"SSA_CREATE (FSP_EVENT_ACTION_CONFLICT_DESTINATION_WINS)";
  if ( v5 == 1 )
    return L"(FSP_EVENT_ACTION_UPLOAD)";
  if ( a2 <= 10 )
  {
    if ( a2 == 10 )
      return L"SSA_CHANGE_ID_UPDATE_VERSION_AND_MERGE_DATA";
    if ( a2 > 5 )
    {
      v10 = a2 - 6;
      if ( !v10 )
        return L"SSA_RENAME_SOURCE_AND_UPDATE_VERSION_AND_DATA";
      v11 = v10 - 1;
      if ( !v11 )
        return L"SSA_RENAME_DESTINATION_AND_UPDATE_VERSION_AND_DATA";
      v12 = v11 - 1;
      if ( !v12 )
        return L"SSA_DELETE_CONFLICTING_AND_SAVE_SOURCE_ITEM";
      if ( v12 == 1 )
        return L"SSA_STORE_MERGE_TOMBSTONE";
    }
    else
    {
      if ( a2 == 5 )
        return L"SSA_DELETE_AND_REMOVE_TOMBSTONE";
      if ( !a2 )
        return L"SSA_CREATE";
      v6 = a2 - 1;
      if ( !v6 )
        return L"SSA_UPDATE_VERSION_ONLY";
      v7 = v6 - 1;
      if ( !v7 )
        return L"SSA_UPDATE_VERSION_AND_DATA";
      v8 = v7 - 1;
      if ( !v8 )
        return L"SSA_UPDATE_VERSION_AND_MERGE_DATA";
      if ( v8 == 1 )
        return L"SSA_DELETE_AND_STORE_TOMBSTONE";
    }
    return L"UNKNOWN";
  }
  v13 = a2 - 11;
  if ( !v13 )
    return L"SSA_CHANGE_ID_UPDATE_VERSION_AND_SAVE_DATA";
  v14 = v13 - 1;
  if ( !v14 )
    return L"SSA_CHANGE_ID_UPDATE_VERSION_AND_DELETE_AND_STORE_TOMBSTONE";
  v15 = v14 - 1;
  if ( !v15 )
    return L"SSA_CHANGE_ID_UPDATE_VERSION_ONLY";
  v16 = v15 - 1;
  if ( !v16 )
    return L"SSA_CREATE_GHOST";
  v17 = v16 - 1;
  if ( !v17 )
    return L"SSA_GHOST_ITEM";
  v18 = v17 - 1;
  if ( !v18 )
    return L"SSA_UNGHOST_ITEM";
  v19 = v18 - 1;
  if ( !v19 )
    return L"SSA_UPDATE_GHOST";
  v20 = v19 - 1;
  if ( !v20 )
    return L"SSA_DELETE_GHOST_AND_STORE_TOMBSTONE";
  if ( v20 != 1 )
    return L"UNKNOWN";
  return L"SSA_DELETE_GHOST_WITHOUT_TOMBSTONE";
}

```

## disassembly

```asm
0x1800f2be8  sub     r8d, 1
0x1800f2bec  jz      loc_1800F2D43
0x1800f2bf2  sub     r8d, 1
0x1800f2bf6  jz      loc_1800F2D3B
0x1800f2bfc  sub     r8d, 1
0x1800f2c00  jz      loc_1800F2D33
0x1800f2c06  cmp     r8d, 1
0x1800f2c0a  jz      loc_1800F2D2B
0x1800f2c10  cmp     edx, 0Ah
0x1800f2c13  jg      loc_1800F2CAE
0x1800f2c19  jz      loc_1800F2CA6
0x1800f2c1f  cmp     edx, 5
0x1800f2c22  jg      short loc_1800F2C72
0x1800f2c24  jz      short loc_1800F2C6A
0x1800f2c26  test    edx, edx
0x1800f2c28  jz      short loc_1800F2C62
0x1800f2c2a  sub     edx, 1
0x1800f2c2d  jz      short loc_1800F2C5A
0x1800f2c2f  sub     edx, 1
0x1800f2c32  jz      short loc_1800F2C52
0x1800f2c34  sub     edx, 1
0x1800f2c37  jz      short loc_1800F2C4A
0x1800f2c39  cmp     edx, 1
0x1800f2c3c  jnz     loc_1800F2CDB
0x1800f2c42  lea     rax, aSsaDeleteAndSt; "SSA_DELETE_AND_STORE_TOMBSTONE"
0x1800f2c49  retn
0x1800f2c4a  lea     rax, aSsaUpdateVersi_2; "SSA_UPDATE_VERSION_AND_MERGE_DATA"
0x1800f2c51  retn
0x1800f2c52  lea     rax, aSsaUpdateVersi; "SSA_UPDATE_VERSION_AND_DATA"
0x1800f2c59  retn
0x1800f2c5a  lea     rax, aSsaUpdateVersi_0; "SSA_UPDATE_VERSION_ONLY"
0x1800f2c61  retn
0x1800f2c62  lea     rax, aSsaCreate; "SSA_CREATE"
0x1800f2c69  retn
0x1800f2c6a  lea     rax, aSsaDeleteAndRe; "SSA_DELETE_AND_REMOVE_TOMBSTONE"
0x1800f2c71  retn
0x1800f2c72  sub     edx, 6
0x1800f2c75  jz      short loc_1800F2C9E
0x1800f2c77  sub     edx, 1
0x1800f2c7a  jz      short loc_1800F2C96
0x1800f2c7c  sub     edx, 1
0x1800f2c7f  jz      short loc_1800F2C8E
0x1800f2c81  cmp     edx, 1
0x1800f2c84  jnz     short loc_1800F2CDB
0x1800f2c86  lea     rax, aSsaStoreMergeT; "SSA_STORE_MERGE_TOMBSTONE"
0x1800f2c8d  retn
0x1800f2c8e  lea     rax, aSsaDeleteConfl; "SSA_DELETE_CONFLICTING_AND_SAVE_SOURCE_"...
0x1800f2c95  retn
0x1800f2c96  lea     rax, aSsaRenameDesti; "SSA_RENAME_DESTINATION_AND_UPDATE_VERSI"...
0x1800f2c9d  retn
0x1800f2c9e  lea     rax, aSsaRenameSourc; "SSA_RENAME_SOURCE_AND_UPDATE_VERSION_AN"...
0x1800f2ca5  retn
0x1800f2ca6  lea     rax, aSsaChangeIdUpd_2; "SSA_CHANGE_ID_UPDATE_VERSION_AND_MERGE_"...
0x1800f2cad  retn
0x1800f2cae  sub     edx, 0Bh
0x1800f2cb1  jz      short loc_1800F2D23
0x1800f2cb3  sub     edx, 1
0x1800f2cb6  jz      short loc_1800F2D1B
0x1800f2cb8  sub     edx, 1
0x1800f2cbb  jz      short loc_1800F2D13
0x1800f2cbd  sub     edx, 1
0x1800f2cc0  jz      short loc_1800F2D0B
0x1800f2cc2  sub     edx, 1
0x1800f2cc5  jz      short loc_1800F2D03
0x1800f2cc7  sub     edx, 1
0x1800f2cca  jz      short loc_1800F2CFB
0x1800f2ccc  sub     edx, 1
0x1800f2ccf  jz      short loc_1800F2CF3
0x1800f2cd1  sub     edx, 1
0x1800f2cd4  jz      short loc_1800F2CEB
0x1800f2cd6  cmp     edx, 1
0x1800f2cd9  jz      short loc_1800F2CE3
0x1800f2cdb  lea     rax, aUnknown_0; "UNKNOWN"
0x1800f2ce2  retn
0x1800f2ce3  lea     rax, aSsaDeleteGhost_0; "SSA_DELETE_GHOST_WITHOUT_TOMBSTONE"
0x1800f2cea  retn
0x1800f2ceb  lea     rax, aSsaDeleteGhost; "SSA_DELETE_GHOST_AND_STORE_TOMBSTONE"
0x1800f2cf2  retn
0x1800f2cf3  lea     rax, aSsaUpdateGhost; "SSA_UPDATE_GHOST"
0x1800f2cfa  retn
0x1800f2cfb  lea     rax, aSsaUnghostItem; "SSA_UNGHOST_ITEM"
0x1800f2d02  retn
0x1800f2d03  lea     rax, aSsaGhostItem; "SSA_GHOST_ITEM"
0x1800f2d0a  retn
0x1800f2d0b  lea     rax, aSsaCreateGhost; "SSA_CREATE_GHOST"
0x1800f2d12  retn
0x1800f2d13  lea     rax, aSsaChangeIdUpd_1; "SSA_CHANGE_ID_UPDATE_VERSION_ONLY"
0x1800f2d1a  retn
0x1800f2d1b  lea     rax, aSsaChangeIdUpd; "SSA_CHANGE_ID_UPDATE_VERSION_AND_DELETE"...
0x1800f2d22  retn
0x1800f2d23  lea     rax, aSsaChangeIdUpd_0; "SSA_CHANGE_ID_UPDATE_VERSION_AND_SAVE_D"...
0x1800f2d2a  retn
0x1800f2d2b  lea     rax, aFspEventAction; "(FSP_EVENT_ACTION_UPLOAD)"
0x1800f2d32  retn
0x1800f2d33  lea     rax, aSsaCreateFspEv; "SSA_CREATE (FSP_EVENT_ACTION_CONFLICT_D"...
0x1800f2d3a  retn
0x1800f2d3b  lea     rax, aSsaCreateFspEv_0; "SSA_CREATE (FSP_EVENT_ACTION_CONFLICT_S"...
0x1800f2d42  retn
0x1800f2d43  lea     rax, aSsaUpdateVersi_1; "SSA_UPDATE_VERSION_AND_DATA (FSP_EVENT_"...
0x1800f2d4a  retn
```
