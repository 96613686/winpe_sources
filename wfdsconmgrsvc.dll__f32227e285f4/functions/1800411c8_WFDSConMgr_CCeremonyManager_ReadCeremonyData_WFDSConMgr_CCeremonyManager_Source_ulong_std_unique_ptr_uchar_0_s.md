# WFDSConMgr::CCeremonyManager::ReadCeremonyData(WFDSConMgr::CCeremonyManager::Source,ulong *,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &)

- ea: `0x1800411c8`
- end: `0x180041358`
- name: `?ReadCeremonyData@CCeremonyManager@WFDSConMgr@@QEAAXW4Source@12@PEAKAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180034924`
- `0x18005aa50`
- `0x18005b410`
- `0x18005b500`

## callees

- `0x180004260`
- `0x18000444e`
- `0x180004c7c`
- `0x180006740`
- `0x180009e5c`
- `0x1800411c8`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180041318`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180041318`

## string_xrefs

- `0x18004121e`: `Missing required pcbData to read ceremony data`
- `0x180041235`: `WFDSConMgr::CCeremonyManager::ReadCeremonyData`
- `0x180041270`: `WFDSConMgr::CCeremonyManager::ReadCeremonyData`
- `0x1800412ae`: `WFDSConMgr::CCeremonyManager::ReadCeremonyData`
- `0x180041346`: `WFDSConMgr::CCeremonyManager::ReadCeremonyData`
- `0x180041257`: `PIN display should be read by external, got read request from internal`
- `0x180041295`: `PIN entry should be read by internal state machine, got read request from external`
- `0x18004132d`: `Ceremony type does not have any data to read`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WFDSConMgr::CCeremonyManager::ReadCeremonyData(RTL_SRWLOCK *a1, int a2, _DWORD *a3, void **a4)
{
  void *v8; // rax
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-38h] BYREF
  char v10; // [rsp+38h] [rbp-30h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_5951838a41203b9c305270f0f2e23976_Traceguids, a1);
  }
  if ( !a3 )
    WFDSConMgr::CException::Throw(
      87,
      "WFDSConMgr::CCeremonyManager::ReadCeremonyData",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\ceremonymanager.cpp",
      123,
      L"Missing required pcbData to read ceremony data",
      a1);
  if ( LODWORD(a1[1].Ptr) == 2 )
  {
    if ( a2 != 1 )
      WFDSConMgr::CException::Throw(
        159,
        "WFDSConMgr::CCeremonyManager::ReadCeremonyData",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\ceremonymanager.cpp",
        131,
        L"PIN display should be read by external, got read request from internal",
        a1);
  }
  else
  {
    if ( LODWORD(a1[1].Ptr) != 3 )
      WFDSConMgr::CException::Throw(
        159,
        "WFDSConMgr::CCeremonyManager::ReadCeremonyData",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\ceremonymanager.cpp",
        145,
        L"Ceremony type does not have any data to read",
        a1);
    if ( a2 )
      WFDSConMgr::CException::Throw(
        159,
        "WFDSConMgr::CCeremonyManager::ReadCeremonyData",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\ceremonymanager.cpp",
        139,
        L"PIN entry should be read by internal state machine, got read request from external",
        a1);
  }
  WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(
    (__int64)&SRWLock,
    a1);
  std::unique_ptr<unsigned char [0]>::reset<unsigned char *,0>(a4, 0);
  *a3 = HIDWORD(a1[1].Ptr);
  if ( HIDWORD(a1[1].Ptr) )
  {
    v8 = operator new[](HIDWORD(a1[1].Ptr));
    std::unique_ptr<unsigned char [0]>::reset<unsigned char *,0>(a4, v8);
    memcpy_0(*a4, a1[2].Ptr, HIDWORD(a1[1].Ptr));
  }
  if ( v10 )
  {
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
  }
}

```

## disassembly

```asm
0x1800411c8  push    rbx
0x1800411ca  push    rsi
0x1800411cb  push    rdi
0x1800411cc  push    r14
0x1800411ce  sub     rsp, 48h
0x1800411d2  mov     r14, r9
0x1800411d5  mov     rsi, r8
0x1800411d8  mov     edi, edx
0x1800411da  mov     rbx, rcx
0x1800411dd  lea     rax, WPP_GLOBAL_Control
0x1800411e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800411eb  cmp     rcx, rax
0x1800411ee  jz      short loc_180041214
0x1800411f0  cmp     byte ptr [rcx+19h], 4
0x1800411f4  jb      short loc_180041214
0x1800411f6  test    byte ptr [rcx+1Ch], 1
0x1800411fa  jz      short loc_180041214
0x1800411fc  mov     edx, 0Fh
0x180041201  mov     r9, rbx
0x180041204  lea     r8, WPP_5951838a41203b9c305270f0f2e23976_Traceguids
0x18004120b  mov     rcx, [rcx+10h]
0x18004120f  call    WPP_SF_q
0x180041214  test    rsi, rsi
0x180041217  jnz     short loc_180041247
0x180041219  mov     [rsp+68h+var_40], rbx; void *
0x18004121e  lea     rax, aMissingRequire_0; "Missing required pcbData to read ceremo"...
0x180041225  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18004122a  lea     r9d, [rsi+7Bh]; char
0x18004122e  lea     r8, aOnecoreuapNetW_18; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180041235  lea     rdx, aWfdsconmgrCcer_0; "WFDSConMgr::CCeremonyManager::ReadCerem"...
0x18004123c  mov     ecx, 80070057h; char
0x180041241  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180041247  cmp     dword ptr [rbx+8], 2
0x18004124b  jnz     short loc_180041282
0x18004124d  cmp     edi, 1
0x180041250  jz      short loc_1800412C0
0x180041252  mov     [rsp+68h+var_40], rbx; void *
0x180041257  lea     rax, aPinDisplayShou; "PIN display should be read by external,"...
0x18004125e  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x180041263  mov     r9d, 83h; char
0x180041269  lea     r8, aOnecoreuapNetW_18; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180041270  lea     rdx, aWfdsconmgrCcer_0; "WFDSConMgr::CCeremonyManager::ReadCerem"...
0x180041277  mov     ecx, 8007139Fh; char
0x18004127c  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x180041282  cmp     dword ptr [rbx+8], 3
0x180041286  jnz     loc_180041328
0x18004128c  test    edi, edi
0x18004128e  jz      short loc_1800412C0
0x180041290  mov     [rsp+68h+var_40], rbx; void *
0x180041295  lea     rax, aPinEntryShould; "PIN entry should be read by internal st"...
0x18004129c  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x1800412a1  mov     r9d, 8Bh; char
0x1800412a7  lea     r8, aOnecoreuapNetW_18; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800412ae  lea     rdx, aWfdsconmgrCcer_0; "WFDSConMgr::CCeremonyManager::ReadCerem"...
0x1800412b5  mov     ecx, 8007139Fh; char
0x1800412ba  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800412c0  mov     rdx, rbx
0x1800412c3  lea     rcx, [rsp+68h+SRWLock]
0x1800412c8  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$00@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,1>::LockSentry<WFDSConMgr::ReadersWriterLock,1>(WFDSConMgr::ReadersWriterLock &)
0x1800412cd  nop
0x1800412ce  xor     edx, edx
0x1800412d0  mov     rcx, r14
0x1800412d3  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset<uchar *,0>(uchar *)
0x1800412d8  mov     eax, [rbx+0Ch]
0x1800412db  mov     [rsi], eax
0x1800412dd  cmp     dword ptr [rbx+0Ch], 0
0x1800412e1  jbe     short loc_180041307
0x1800412e3  mov     ecx, [rbx+0Ch]; unsigned __int64
0x1800412e6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800412eb  mov     rdx, rax
0x1800412ee  mov     rcx, r14
0x1800412f1  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset<uchar *,0>(uchar *)
0x1800412f6  mov     r8d, [rbx+0Ch]; Size
0x1800412fa  mov     rdx, [rbx+10h]; Src
0x1800412fe  mov     rcx, [r14]; void *
0x180041301  call    memcpy_0
0x180041306  nop
0x180041307  cmp     [rsp+68h+var_30], 0
0x18004130c  jz      short loc_18004131E
0x18004130e  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x180041313  test    rcx, rcx
0x180041316  jz      short loc_18004131E
0x180041318  call    cs:__imp_ReleaseSRWLockShared
0x18004131e  add     rsp, 48h
0x180041322  pop     r14
0x180041324  pop     rdi
0x180041325  pop     rsi
0x180041326  pop     rbx
0x180041327  retn
0x180041328  mov     [rsp+68h+var_40], rbx; void *
0x18004132d  lea     rax, aCeremonyTypeDo_1; "Ceremony type does not have any data to"...
0x180041334  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x180041339  mov     r9d, 91h; char
0x18004133f  lea     r8, aOnecoreuapNetW_18; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180041346  lea     rdx, aWfdsconmgrCcer_0; "WFDSConMgr::CCeremonyManager::ReadCerem"...
0x18004134d  mov     ecx, 8007139Fh; char
0x180041352  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
