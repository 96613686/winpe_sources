# WFDSConMgr::CDafAssociationHelper::WriteCeremonyData(ulong,uchar const *)

- ea: `0x18004b660`
- end: `0x18004b93d`
- name: `?WriteCeremonyData@CDafAssociationHelper@WFDSConMgr@@QEAAXKPEBE@Z`
- size: `733`
- prototype: `void __fastcall(WFDSConMgr::CDafAssociationHelper *__hidden this, unsigned int, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x18005b410`

## callees

- `0x180002600`
- `0x180002ffc`
- `0x18000665c`
- `0x180006740`
- `0x18000b1ac`
- `0x180019ad4`
- `0x18001a1dc`
- `0x18001a21c`
- `0x180048e9c`
- `0x180049060`
- `0x18004b660`
- `0x18004bf64`
- `0x18005c888`
- `0x18005df7c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004b7bb`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004b7bb`

## string_xrefs

- `0x18004b6d2`: `Must create association before calling Write Ceremony Data`
- `0x18004b6eb`: `WFDSConMgr::CDafAssociationHelper::WriteCeremonyData`
- `0x18004b724`: `WFDSConMgr::CDafAssociationHelper::WriteCeremonyData`
- `0x18004b7e3`: `WFDSConMgr::CDafAssociationHelper::WriteCeremonyData`
- `0x18004b840`: `WFDSConMgr::CDafAssociationHelper::WriteCeremonyData`
- `0x18004b889`: `WFDSConMgr::CDafAssociationHelper::WriteCeremonyData`
- `0x18004b8c3`: `WFDSConMgr::CDafAssociationHelper::WriteCeremonyData`
- `0x18004b70b`: `Bad parameters to WriteCeremonyData`
- `0x18004b7ca`: `memcpy_s failed for PIN data in WriteCeremonyData`
- `0x18004b827`: `Failure in DafStartWriteCeremonyData, bailing out`
- `0x18004b870`: `StartWriteCeremonyData operation canceled`
- `0x18004b8aa`: `Failure in DafStartWriteCeremonyData callback, bailing out`

## pseudocode

```c
void __fastcall WFDSConMgr::CDafAssociationHelper::WriteCeremonyData(
        WFDSConMgr::CDafAssociationHelper *this,
        unsigned int a2,
        const unsigned __int8 *a3)
{
  __int64 v4; // rdi
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // eax
  int v9; // ecx
  _BYTE v10[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh]
  __int128 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+58h] [rbp-A8h]
  _BYTE v14[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v15; // [rsp+78h] [rbp-88h]
  _BYTE v16[128]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v17; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v18[528]; // [rsp+120h] [rbp+20h] BYREF

  v4 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_bb56a6bc0d5f3da3ca648cfde167a68a_Traceguids, this);
  }
  if ( !*((_QWORD *)this + 2) )
    WFDSConMgr::CException::Throw(
      159,
      "WFDSConMgr::CDafAssociationHelper::WriteCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      137,
      L"Must create association before calling Write Ceremony Data",
      this);
  if ( (_DWORD)v4 && !a3 )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CDafAssociationHelper::WriteCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      143,
      L"Bad parameters to WriteCeremonyData",
      this);
  memset_0(&v17, 0, 0x218u);
  v17 = *(_OWORD *)((char *)this + 108);
  v12 = 0;
  v13 = 0;
  std::string::_Construct<1,char const *>(&v12, a3, v4);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v16);
  v6 = std::_String_val<std::_Simple_types<char>>::_Myptr(&v12);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v16,
    v14,
    v6,
    v6 + v13);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
  if ( (unsigned int)_o_wcsncpy_s(v18, 260, v7, v15) )
    WFDSConMgr::CException::Throw(
      111,
      "WFDSConMgr::CDafAssociationHelper::WriteCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      158,
      L"memcpy_s failed for PIN data in WriteCeremonyData",
      this);
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int128 *, void (__fastcall *)(WFDSConMgr::CDafAssociationHelper *, int), WFDSConMgr::CDafAssociationHelper *))(**(_QWORD **)this + 48LL))(
         *(_QWORD *)this,
         *((_QWORD *)this + 2),
         536,
         &v17,
         WFDSConMgr::CDafAssociationHelper::WriteCeremonyDataCallback,
         this);
  if ( v8 < 0 )
    WFDSConMgr::CException::Throw(
      v8,
      "WFDSConMgr::CDafAssociationHelper::WriteCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      163,
      L"Failure in DafStartWriteCeremonyData, bailing out",
      this);
  WFDSConMgr::WaitMultipleEvents(v10, 0xFFFFFFFFLL, (char *)this + 40, (char *)this + 72);
  if ( v11 == 1 )
    WFDSConMgr::CException::Throw(
      199,
      "WFDSConMgr::CDafAssociationHelper::WriteCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      172,
      L"StartWriteCeremonyData operation canceled",
      this);
  v9 = *((_DWORD *)this + 37);
  if ( v9 < 0 )
    WFDSConMgr::CException::Throw(
      v9,
      "WFDSConMgr::CDafAssociationHelper::WriteCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\dafassociationhelper.cpp",
      177,
      L"Failure in DafStartWriteCeremonyData callback, bailing out",
      this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_bb56a6bc0d5f3da3ca648cfde167a68a_Traceguids, this);
  }
  std::wstring::_Tidy_deallocate(v14);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v16);
  std::string::_Tidy_deallocate(&v12);
}

```

## disassembly

```asm
0x18004b660  push    rbp
0x18004b662  push    rbx
0x18004b663  push    rsi
0x18004b664  push    rdi
0x18004b665  push    r14
0x18004b667  lea     rbp, [rsp-240h]
0x18004b66f  sub     rsp, 340h
0x18004b676  mov     rax, cs:__security_cookie
0x18004b67d  xor     rax, rsp
0x18004b680  mov     [rbp+260h+var_30], rax
0x18004b687  mov     rsi, r8
0x18004b68a  mov     edi, edx
0x18004b68c  mov     rbx, rcx
0x18004b68f  lea     r14, WPP_GLOBAL_Control
0x18004b696  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b69d  cmp     rcx, r14
0x18004b6a0  jz      short loc_18004B6C6
0x18004b6a2  cmp     byte ptr [rcx+19h], 4
0x18004b6a6  jb      short loc_18004B6C6
0x18004b6a8  test    byte ptr [rcx+1Ch], 1
0x18004b6ac  jz      short loc_18004B6C6
0x18004b6ae  mov     edx, 18h
0x18004b6b3  mov     r9, rbx
0x18004b6b6  lea     r8, WPP_bb56a6bc0d5f3da3ca648cfde167a68a_Traceguids
0x18004b6bd  mov     rcx, [rcx+10h]
0x18004b6c1  call    WPP_SF_q
0x18004b6c6  cmp     qword ptr [rbx+10h], 0
0x18004b6cb  jnz     short loc_18004B6FD
0x18004b6cd  mov     [rsp+360h+var_338], rbx; void *
0x18004b6d2  lea     rax, aMustCreateAsso_0; "Must create association before calling "...
0x18004b6d9  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x18004b6de  mov     r9d, 189h; char
0x18004b6e4  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004b6eb  lea     rdx, aWfdsconmgrCdaf_9; "WFDSConMgr::CDafAssociationHelper::Writ"...
0x18004b6f2  mov     ecx, 8007139Fh; char
0x18004b6f7  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004b6fd  test    edi, edi
0x18004b6ff  jz      short loc_18004B736
0x18004b701  test    rsi, rsi
0x18004b704  jnz     short loc_18004B736
0x18004b706  mov     [rsp+360h+var_338], rbx; void *
0x18004b70b  lea     rax, aBadParametersT_1; "Bad parameters to WriteCeremonyData"
0x18004b712  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x18004b717  mov     r9d, 18Fh; char
0x18004b71d  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004b724  lea     rdx, aWfdsconmgrCdaf_9; "WFDSConMgr::CDafAssociationHelper::Writ"...
0x18004b72b  mov     ecx, 80070057h; char
0x18004b730  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004b736  xor     edx, edx; Val
0x18004b738  mov     r8d, 218h; Size
0x18004b73e  lea     rcx, [rbp+260h+var_250]; void *
0x18004b742  call    memset_0
0x18004b747  movups  xmm0, xmmword ptr [rbx+6Ch]
0x18004b74b  movdqu  [rbp+260h+var_250], xmm0
0x18004b750  xorps   xmm1, xmm1
0x18004b753  movups  [rsp+360h+var_318], xmm1
0x18004b758  xorps   xmm0, xmm0
0x18004b75b  movdqu  [rsp+360h+var_308], xmm0
0x18004b761  mov     r8, rdi
0x18004b764  mov     rdx, rsi
0x18004b767  lea     rcx, [rsp+360h+var_318]
0x18004b76c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004b771  nop
0x18004b772  lea     rcx, [rbp+260h+var_2D0]
0x18004b776  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18004b77b  nop
0x18004b77c  lea     rcx, [rsp+360h+var_318]
0x18004b781  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18004b786  mov     r9, qword ptr [rsp+360h+var_308]
0x18004b78b  add     r9, rax
0x18004b78e  mov     r8, rax
0x18004b791  lea     rdx, [rsp+360h+var_2F8]
0x18004b796  lea     rcx, [rbp+260h+var_2D0]
0x18004b79a  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x18004b79f  nop
0x18004b7a0  lea     rcx, [rsp+360h+var_2F8]
0x18004b7a5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004b7aa  mov     r8, rax
0x18004b7ad  mov     r9, [rsp+360h+var_2E8]
0x18004b7b2  mov     edx, 104h
0x18004b7b7  lea     rcx, [rbp+260h+var_240]
0x18004b7bb  call    cs:__imp__o_wcsncpy_s
0x18004b7c1  mov     [rsp+360h+var_338], rbx; void *
0x18004b7c6  test    eax, eax
0x18004b7c8  jz      short loc_18004B7F5
0x18004b7ca  lea     rax, aMemcpySFailedF; "memcpy_s failed for PIN data in WriteCe"...
0x18004b7d1  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x18004b7d6  mov     r9d, 19Eh; char
0x18004b7dc  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004b7e3  lea     rdx, aWfdsconmgrCdaf_9; "WFDSConMgr::CDafAssociationHelper::Writ"...
0x18004b7ea  mov     ecx, 8007006Fh; char
0x18004b7ef  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004b7f5  mov     rcx, [rbx]
0x18004b7f8  mov     rax, [rcx]
0x18004b7fb  lea     rdx, ?WriteCeremonyDataCallback@CDafAssociationHelper@WFDSConMgr@@KAXPEAXJ@Z; WFDSConMgr::CDafAssociationHelper::WriteCeremonyDataCallback(void *,long)
0x18004b802  mov     [rsp+360h+var_340], rdx
0x18004b807  lea     r9, [rbp+260h+var_250]
0x18004b80b  mov     r8d, 218h
0x18004b811  mov     rdx, [rbx+10h]
0x18004b815  mov     rax, [rax+30h]
0x18004b819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b81e  test    eax, eax
0x18004b820  jns     short loc_18004B84F
0x18004b822  mov     [rsp+360h+var_338], rbx; void *
0x18004b827  lea     rcx, aFailureInDafst_5; "Failure in DafStartWriteCeremonyData, b"...
0x18004b82e  mov     [rsp+360h+var_340], rcx; unsigned __int16 *
0x18004b833  mov     r9d, 1A3h; char
0x18004b839  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004b840  lea     rdx, aWfdsconmgrCdaf_9; "WFDSConMgr::CDafAssociationHelper::Writ"...
0x18004b847  mov     ecx, eax; char
0x18004b849  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004b84f  lea     r9, [rbx+48h]
0x18004b853  lea     r8, [rbx+28h]
0x18004b857  or      edx, 0FFFFFFFFh
0x18004b85a  lea     rcx, [rsp+360h+var_320]
0x18004b85f  call    ?WaitMultipleEvents@WFDSConMgr@@YA?AVCWaitResult@1@KAEBVCEventWrapper@1@0@Z; WFDSConMgr::WaitMultipleEvents(ulong,WFDSConMgr::CEventWrapper const &,WFDSConMgr::CEventWrapper const &)
0x18004b864  cmp     [rsp+360h+var_31C], 1
0x18004b869  jnz     short loc_18004B89B
0x18004b86b  mov     [rsp+360h+var_338], rbx; void *
0x18004b870  lea     rax, aStartwritecere; "StartWriteCeremonyData operation cancel"...
0x18004b877  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x18004b87c  mov     r9d, 1ACh; char
0x18004b882  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004b889  lea     rdx, aWfdsconmgrCdaf_9; "WFDSConMgr::CDafAssociationHelper::Writ"...
0x18004b890  mov     ecx, 800704C7h; char
0x18004b895  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004b89b  mov     ecx, [rbx+94h]; char
0x18004b8a1  test    ecx, ecx
0x18004b8a3  jns     short loc_18004B8D0
0x18004b8a5  mov     [rsp+360h+var_338], rbx; void *
0x18004b8aa  lea     rax, aFailureInDafst_0; "Failure in DafStartWriteCeremonyData ca"...
0x18004b8b1  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x18004b8b6  mov     r9d, 1B1h; char
0x18004b8bc  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x18004b8c3  lea     rdx, aWfdsconmgrCdaf_9; "WFDSConMgr::CDafAssociationHelper::Writ"...
0x18004b8ca  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18004b8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b8d7  cmp     rcx, r14
0x18004b8da  jz      short loc_18004B901
0x18004b8dc  cmp     byte ptr [rcx+19h], 4
0x18004b8e0  jb      short loc_18004B901
0x18004b8e2  test    byte ptr [rcx+1Ch], 1
0x18004b8e6  jz      short loc_18004B901
0x18004b8e8  mov     edx, 19h
0x18004b8ed  mov     r9, rbx
0x18004b8f0  lea     r8, WPP_bb56a6bc0d5f3da3ca648cfde167a68a_Traceguids
0x18004b8f7  mov     rcx, [rcx+10h]
0x18004b8fb  call    WPP_SF_q
0x18004b900  nop
0x18004b901  lea     rcx, [rsp+360h+var_2F8]
0x18004b906  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004b90b  nop
0x18004b90c  lea     rcx, [rbp+260h+var_2D0]
0x18004b910  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18004b915  nop
0x18004b916  lea     rcx, [rsp+360h+var_318]
0x18004b91b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004b920  mov     rcx, [rbp+260h+var_30]
0x18004b927  xor     rcx, rsp; StackCookie
0x18004b92a  call    __security_check_cookie
0x18004b92f  add     rsp, 340h
0x18004b936  pop     r14
0x18004b938  pop     rdi
0x18004b939  pop     rsi
0x18004b93a  pop     rbx
0x18004b93b  pop     rbp
0x18004b93c  retn
```
