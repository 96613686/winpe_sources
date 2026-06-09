# SettingsCopier::CopyATSettings(ATL::CRegKey &,ATL::CRegKey &)

- ea: `0x14001bcec`
- end: `0x14001bf7a`
- name: `?CopyATSettings@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@0@Z`
- size: `654`
- prototype: `int(SettingsCopier *__hidden this, struct ATL::CRegKey *, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001c64c`

## callees

- `0x140002480`
- `0x14000815c`
- `0x14000d75c`
- `0x14000e550`
- `0x1400137c4`
- `0x1400151e0`
- `0x140018084`
- `0x14001bcec`
- `0x14001bf80`
- `0x14001c2e8`
- `0x14001c708`
- `0x14001c940`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001be8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001bf28`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001be8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001bf28`

## string_xrefs

- `0x14001bd38`: `enduser\ezap\easeofaccess\atmanager\settingscopier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SettingsCopier::CopyATSettings(SettingsCopier *this, HKEY *a2, HKEY *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v9; // rcx
  __int64 Next; // rax
  LPCWSTR *v11; // rsi
  DWORD v12; // edi
  signed int RegKeyValue; // eax
  unsigned int v14; // ebx
  BYTE *v15; // rcx
  BYTE *v16; // rbx
  LSTATUS v17; // eax
  BYTE *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  DWORD lpData; // [rsp+20h] [rbp-E0h]
  DWORD dwType[2]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v26[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v6 = SettingsCopier::DeleteATSettings(a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"enduser\\ezap\\easeofaccess\\atmanager\\settingscopier.cpp",
      (const char *)(unsigned int)v6,
      lpData);
    return v7;
  }
  v9 = *(_QWORD *)ATManager::GetAccommodations(*(_QWORD *)this);
  v25 = v9;
  if ( !v9 )
    return 0;
  do
  {
    Next = ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GetNext(
             v9,
             &v25);
    v11 = *(LPCWSTR **)Next;
    if ( !*(_DWORD *)(*(_QWORD *)Next + 68LL) )
      continue;
    memset(v27, 0, 24);
    memset(v26, 0, sizeof(v26));
    v12 = 0;
    while ( 1 )
    {
      dwType[1] = 0;
      dwType[0] = 0;
      v24 = 0;
      RegKeyValue = SettingsCopier::GetRegKeyValue(*a2, *v11, v12, ValueName, lpData, &dwType[1], (void **)&v24, dwType);
      v14 = RegKeyValue;
      if ( RegKeyValue == 1 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_29;
        v20 = 10;
        v21 = 1;
        goto LABEL_28;
      }
      if ( RegKeyValue < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_29;
        v20 = 11;
        v21 = (unsigned int)RegKeyValue;
LABEL_28:
        WPP_SF_D(v19[2], v20, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids, v21);
LABEL_29:
        v18 = v24;
        goto LABEL_30;
      }
      if ( !(unsigned int)IsInteractiveUser() && (unsigned __int8)IsBlockedCopyValue(ValueName) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids, v14);
        v15 = v24;
        goto LABEL_16;
      }
      v16 = v24;
      v17 = SettingsCopier::SetRegKeyValue(*a3, *v11, ValueName, dwType[1], v24, dwType[0]);
      if ( v17 < 0 )
        break;
      v15 = v16;
LABEL_16:
      free(v15);
      if ( ++v12 > 0x64 )
        goto LABEL_31;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids,
        (unsigned int)v17);
    v18 = v16;
LABEL_30:
    free(v18);
LABEL_31:
    ATL::CRegKey::Close((ATL::CRegKey *)v26);
    ATL::CRegKey::Close((ATL::CRegKey *)v27);
  }
  while ( v25 );
  return 0;
}

```

## disassembly

```asm
0x14001bcec  push    rbp
0x14001bcee  push    rbx
0x14001bcef  push    rsi
0x14001bcf0  push    rdi
0x14001bcf1  push    r13
0x14001bcf3  push    r14
0x14001bcf5  push    r15
0x14001bcf7  lea     rbp, [rsp-1B0h]
0x14001bcff  sub     rsp, 2B0h
0x14001bd06  mov     rax, cs:__security_cookie
0x14001bd0d  xor     rax, rsp
0x14001bd10  mov     [rbp+1E0h+var_40], rax
0x14001bd17  mov     r14, r8
0x14001bd1a  mov     r15, rdx
0x14001bd1d  mov     rdi, rcx
0x14001bd20  mov     rcx, r8; struct ATL::CRegKey *
0x14001bd23  call    ?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z; SettingsCopier::DeleteATSettings(ATL::CRegKey &)
0x14001bd28  mov     ebx, eax
0x14001bd2a  test    eax, eax
0x14001bd2c  jns     short loc_14001BD50
0x14001bd2e  mov     rcx, [rbp+1E8h]; this
0x14001bd35  mov     r9d, eax; char *
0x14001bd38  lea     r8, aEnduserEzapEas; "enduser\\ezap\\easeofaccess\\atmanager"...
0x14001bd3f  mov     edx, 1FCh; void *
0x14001bd44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001bd49  mov     eax, ebx
0x14001bd4b  jmp     loc_14001BF58
0x14001bd50  mov     rcx, [rdi]
0x14001bd53  call    ?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ; ATManager::GetAccommodations(void)
0x14001bd58  mov     rcx, [rax]
0x14001bd5b  mov     [rsp+2E0h+var_290], rcx
0x14001bd60  test    rcx, rcx
0x14001bd63  jz      loc_14001BF56
0x14001bd69  lea     r13, WPP_GLOBAL_Control
0x14001bd70  lea     rdx, [rsp+2E0h+var_290]
0x14001bd75  call    ?GetNext@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBAAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAPEAU__POSITION@@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GetNext(__POSITION * &)
0x14001bd7a  mov     rsi, [rax]
0x14001bd7d  cmp     dword ptr [rsi+44h], 0
0x14001bd81  jz      loc_14001BF4A
0x14001bd87  mov     [rsp+2E0h+var_270], 0
0x14001bd90  mov     [rsp+2E0h+var_268], 0
0x14001bd99  mov     [rbp+1E0h+var_260], 0
0x14001bda1  mov     [rsp+2E0h+var_288], 0
0x14001bdaa  mov     [rsp+2E0h+var_280], 0
0x14001bdb3  mov     [rsp+2E0h+var_278], 0
0x14001bdbc  xor     edi, edi
0x14001bdbe  mov     [rsp+2E0h+dwType+4], 0
0x14001bdc6  mov     [rsp+2E0h+dwType], 0
0x14001bdce  mov     [rsp+2E0h+var_298], 0
0x14001bdd7  lea     rax, [rsp+2E0h+dwType]
0x14001bddc  mov     [rsp+2E0h+var_2A8], rax; __int64
0x14001bde1  lea     rax, [rsp+2E0h+var_298]
0x14001bde6  mov     [rsp+2E0h+var_2B0], rax; __int64
0x14001bdeb  lea     rax, [rsp+2E0h+dwType+4]
0x14001bdf0  mov     qword ptr [rsp+2E0h+var_2B8], rax; __int64
0x14001bdf5  lea     r9, [rbp+1E0h+ValueName]
0x14001bdf9  mov     r8d, edi
0x14001bdfc  mov     rdx, [rsi]; lpSubKey
0x14001bdff  mov     rcx, [r15]; hKey
0x14001be02  call    ?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z; SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)
0x14001be07  mov     ebx, eax
0x14001be09  cmp     eax, 1
0x14001be0c  jz      loc_14001BEF7
0x14001be12  test    eax, eax
0x14001be14  js      loc_14001BEDB
0x14001be1a  call    ?IsInteractiveUser@@YAHXZ; IsInteractiveUser(void)
0x14001be1f  test    eax, eax
0x14001be21  jnz     short loc_14001BE62
0x14001be23  lea     rcx, [rbp+1E0h+ValueName]
0x14001be27  call    IsBlockedCopyValue
0x14001be2c  test    al, al
0x14001be2e  jz      short loc_14001BE62
0x14001be30  mov     rcx, cs:WPP_GLOBAL_Control
0x14001be37  cmp     rcx, r13
0x14001be3a  jz      short loc_14001BE5B
0x14001be3c  test    byte ptr [rcx+1Ch], 10h
0x14001be40  jz      short loc_14001BE5B
0x14001be42  mov     edx, 0Ch
0x14001be47  mov     r9d, ebx
0x14001be4a  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x14001be51  mov     rcx, [rcx+10h]
0x14001be55  call    WPP_SF_D
0x14001be5a  nop
0x14001be5b  mov     rcx, [rsp+2E0h+var_298]
0x14001be60  jmp     short loc_14001BE8F
0x14001be62  mov     eax, [rsp+2E0h+dwType]
0x14001be66  mov     [rsp+2E0h+var_2B8], eax; DWORD
0x14001be6a  mov     rbx, [rsp+2E0h+var_298]
0x14001be6f  mov     [rsp+2E0h+lpData], rbx; lpData
0x14001be74  mov     r9d, [rsp+2E0h+dwType+4]; dwType
0x14001be79  lea     r8, [rbp+1E0h+ValueName]; lpValueName
0x14001be7d  mov     rdx, [rsi]; lpSubKey
0x14001be80  mov     rcx, [r14]; hKey
0x14001be83  call    ?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z; SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)
0x14001be88  test    eax, eax
0x14001be8a  js      short loc_14001BEAB
0x14001be8c  mov     rcx, rbx; Block
0x14001be8f  call    cs:__imp_free
0x14001be96  nop     dword ptr [rax+rax+00h]
0x14001be9b  inc     edi
0x14001be9d  cmp     edi, 64h ; 'd'
0x14001bea0  jbe     loc_14001BDBE
0x14001bea6  jmp     loc_14001BF35
0x14001beab  mov     rcx, cs:WPP_GLOBAL_Control
0x14001beb2  cmp     rcx, r13
0x14001beb5  jz      short loc_14001BED6
0x14001beb7  test    byte ptr [rcx+1Ch], 8
0x14001bebb  jz      short loc_14001BED6
0x14001bebd  mov     edx, 0Dh
0x14001bec2  mov     r9d, eax
0x14001bec5  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x14001becc  mov     rcx, [rcx+10h]
0x14001bed0  call    WPP_SF_D
0x14001bed5  nop
0x14001bed6  mov     rcx, rbx
0x14001bed9  jmp     short loc_14001BF28
0x14001bedb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bee2  cmp     rcx, r13
0x14001bee5  jz      short loc_14001BF23
0x14001bee7  test    byte ptr [rcx+1Ch], 8
0x14001beeb  jz      short loc_14001BF23
0x14001beed  mov     edx, 0Bh
0x14001bef2  mov     r9d, ebx
0x14001bef5  jmp     short loc_14001BF12
0x14001bef7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001befe  cmp     rcx, r13
0x14001bf01  jz      short loc_14001BF23
0x14001bf03  test    byte ptr [rcx+1Ch], 10h
0x14001bf07  jz      short loc_14001BF23
0x14001bf09  mov     edx, 0Ah
0x14001bf0e  lea     r9d, [rdx-9]
0x14001bf12  lea     r8, WPP_fe5ab529b727364d0549539a0e90a98d_Traceguids
0x14001bf19  mov     rcx, [rcx+10h]
0x14001bf1d  call    WPP_SF_D
0x14001bf22  nop
0x14001bf23  mov     rcx, [rsp+2E0h+var_298]; Block
0x14001bf28  call    cs:__imp_free
0x14001bf2f  nop     dword ptr [rax+rax+00h]
0x14001bf34  nop
0x14001bf35  lea     rcx, [rsp+2E0h+var_288]; this
0x14001bf3a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001bf3f  nop
0x14001bf40  lea     rcx, [rsp+2E0h+var_270]; this
0x14001bf45  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14001bf4a  cmp     [rsp+2E0h+var_290], 0
0x14001bf50  jnz     loc_14001BD70
0x14001bf56  xor     eax, eax
0x14001bf58  mov     rcx, [rbp+1E0h+var_40]
0x14001bf5f  xor     rcx, rsp; StackCookie
0x14001bf62  call    __security_check_cookie
0x14001bf67  add     rsp, 2B0h
0x14001bf6e  pop     r15
0x14001bf70  pop     r14
0x14001bf72  pop     r13
0x14001bf74  pop     rdi
0x14001bf75  pop     rsi
0x14001bf76  pop     rbx
0x14001bf77  pop     rbp
0x14001bf78  retn
```
