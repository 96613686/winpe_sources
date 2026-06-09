# WFDSConMgr::CCeremonyManager::WriteCeremonyData(WFDSConMgr::CCeremonyManager::Source,ulong,uchar const *)

- ea: `0x180041418`
- end: `0x1800415b5`
- name: `?WriteCeremonyData@CCeremonyManager@WFDSConMgr@@QEAAXW4Source@12@KPEBE@Z`
- size: `413`
- prototype: `void __fastcall(__int64, int, unsigned int, const void *)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180035280`
- `0x18005a6e0`
- `0x18005b210`

## callees

- `0x180004260`
- `0x18000444e`
- `0x180006780`
- `0x180006c60`
- `0x180008a10`
- `0x180009b5c`
- `0x180009e5c`
- `0x180041418`
- `0x18005c888`
- `0x18006d010`

## string_xrefs

- `0x18004147a`: `PIN display should be written by internal state machine, got write request from external`
- `0x180041493`: `WFDSConMgr::CCeremonyManager::WriteCeremonyData`
- `0x1800414d2`: `WFDSConMgr::CCeremonyManager::WriteCeremonyData`
- `0x1800415a3`: `WFDSConMgr::CCeremonyManager::WriteCeremonyData`
- `0x1800414b9`: `PIN entry should be written by external user input, got write request from internal`
- `0x18004158a`: `Ceremony type does not have any data to write`

## pseudocode

```c
void __fastcall WFDSConMgr::CCeremonyManager::WriteCeremonyData(__int64 a1, int a2, unsigned int a3, const void *a4)
{
  unsigned __int64 v5; // rbp
  void *v8; // rax
  _BYTE v9[72]; // [rsp+30h] [rbp-48h] BYREF

  v5 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_5951838a41203b9c305270f0f2e23976_Traceguids, a1, a3);
  }
  if ( *(_DWORD *)(a1 + 8) == 2 )
  {
    if ( a2 )
      WFDSConMgr::CException::Throw(
        159,
        "WFDSConMgr::CCeremonyManager::WriteCeremonyData",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\ceremonymanager.cpp",
        81,
        L"PIN display should be written by internal state machine, got write request from external",
        (const void *)a1);
  }
  else
  {
    if ( *(_DWORD *)(a1 + 8) != 3 )
      WFDSConMgr::CException::Throw(
        159,
        "WFDSConMgr::CCeremonyManager::WriteCeremonyData",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\ceremonymanager.cpp",
        95,
        L"Ceremony type does not have any data to write",
        (const void *)a1);
    if ( a2 != 1 )
      WFDSConMgr::CException::Throw(
        159,
        "WFDSConMgr::CCeremonyManager::WriteCeremonyData",
        "onecoreuap\\net\\wlan\\wfdsconmgr\\conmgr\\src\\ceremonymanager.cpp",
        89,
        L"PIN entry should be written by external user input, got write request from internal",
        (const void *)a1);
  }
  if ( (_DWORD)v5 )
  {
    WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(v9, a1);
    v8 = operator new[](v5);
    std::unique_ptr<unsigned char [0]>::reset<unsigned char *,0>(a1 + 16, v8);
    *(_DWORD *)(a1 + 12) = v5;
    memcpy_0(*(void **)(a1 + 16), a4, v5);
    if ( *(_QWORD *)(a1 + 24) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          &WPP_5951838a41203b9c305270f0f2e23976_Traceguids,
          a1,
          *(_QWORD *)(a1 + 24));
      }
      (***(void (__fastcall ****)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 24));
    }
    WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(v9);
  }
}

```

## disassembly

```asm
0x180041418  push    rbx
0x18004141a  push    rbp
0x18004141b  push    rsi
0x18004141c  push    rdi
0x18004141d  push    r14
0x18004141f  push    r15
0x180041421  sub     rsp, 48h
0x180041425  mov     r14, r9
0x180041428  mov     ebp, r8d
0x18004142b  mov     ebx, edx
0x18004142d  mov     rsi, rcx
0x180041430  lea     r15, WPP_GLOBAL_Control
0x180041437  mov     rcx, cs:WPP_GLOBAL_Control
0x18004143e  cmp     rcx, r15
0x180041441  jz      short loc_18004146B
0x180041443  cmp     byte ptr [rcx+19h], 4
0x180041447  jb      short loc_18004146B
0x180041449  test    byte ptr [rcx+1Ch], 1
0x18004144d  jz      short loc_18004146B
0x18004144f  mov     edx, 0Dh
0x180041454  mov     dword ptr [rsp+78h+var_58], ebp
0x180041458  mov     r9, rsi
0x18004145b  lea     r8, WPP_5951838a41203b9c305270f0f2e23976_Traceguids
0x180041462  mov     rcx, [rcx+10h]
0x180041466  call    WPP_SF_qD
0x18004146b  cmp     dword ptr [rsi+8], 2
0x18004146f  jnz     short loc_1800414A5
0x180041471  test    ebx, ebx
0x180041473  jz      short loc_1800414E4
0x180041475  mov     [rsp+78h+var_50], rsi; void *
0x18004147a  lea     rax, aPinDisplayShou_0; "PIN display should be written by intern"...
0x180041481  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x180041486  mov     r9d, 51h ; 'Q'; char
0x18004148c  lea     r8, aOnecoreuapNetW_18; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x180041493  lea     rdx, aWfdsconmgrCcer; "WFDSConMgr::CCeremonyManager::WriteCere"...
0x18004149a  mov     ecx, 8007139Fh; char
0x18004149f  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800414a5  cmp     dword ptr [rsi+8], 3
0x1800414a9  jnz     loc_180041585
0x1800414af  cmp     ebx, 1
0x1800414b2  jz      short loc_1800414E4
0x1800414b4  mov     [rsp+78h+var_50], rsi; void *
0x1800414b9  lea     rax, aPinEntryShould_0; "PIN entry should be written by external"...
0x1800414c0  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x1800414c5  mov     r9d, 59h ; 'Y'; char
0x1800414cb  lea     r8, aOnecoreuapNetW_18; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800414d2  lea     rdx, aWfdsconmgrCcer; "WFDSConMgr::CCeremonyManager::WriteCere"...
0x1800414d9  mov     ecx, 8007139Fh; char
0x1800414de  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x1800414e4  test    ebp, ebp
0x1800414e6  jz      loc_180041578
0x1800414ec  mov     rdx, rsi
0x1800414ef  lea     rcx, [rsp+78h+var_48]
0x1800414f4  call    ??0?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAA@AEAVReadersWriterLock@1@@Z; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::LockSentry<WFDSConMgr::ReadersWriterLock,0>(WFDSConMgr::ReadersWriterLock &)
0x1800414f9  nop
0x1800414fa  mov     rcx, rbp; unsigned __int64
0x1800414fd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180041502  mov     rdx, rax
0x180041505  lea     rcx, [rsi+10h]
0x180041509  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0]>::reset<uchar *,0>(uchar *)
0x18004150e  mov     [rsi+0Ch], ebp
0x180041511  mov     r8, rbp; Size
0x180041514  mov     rdx, r14; Src
0x180041517  mov     rcx, [rsi+10h]; void *
0x18004151b  call    memcpy_0
0x180041520  mov     rax, [rsi+18h]
0x180041524  test    rax, rax
0x180041527  jz      short loc_18004156E
0x180041529  mov     rcx, cs:WPP_GLOBAL_Control
0x180041530  cmp     rcx, r15
0x180041533  jz      short loc_18004155E
0x180041535  cmp     byte ptr [rcx+19h], 4
0x180041539  jb      short loc_18004155E
0x18004153b  test    byte ptr [rcx+1Ch], 1
0x18004153f  jz      short loc_18004155E
0x180041541  mov     edx, 0Eh
0x180041546  mov     [rsp+78h+var_58], rax
0x18004154b  mov     r9, rsi
0x18004154e  lea     r8, WPP_5951838a41203b9c305270f0f2e23976_Traceguids
0x180041555  mov     rcx, [rcx+10h]
0x180041559  call    WPP_SF_qq
0x18004155e  mov     rcx, [rsi+18h]
0x180041562  mov     rax, [rcx]
0x180041565  mov     rax, [rax]
0x180041568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004156d  nop
0x18004156e  lea     rcx, [rsp+78h+var_48]
0x180041573  call    ?Unlock@?$LockSentry@VReadersWriterLock@WFDSConMgr@@$0A@@WFDSConMgr@@QEAAXXZ; WFDSConMgr::LockSentry<WFDSConMgr::ReadersWriterLock,0>::Unlock(void)
0x180041578  add     rsp, 48h
0x18004157c  pop     r15
0x18004157e  pop     r14
0x180041580  pop     rdi
0x180041581  pop     rsi
0x180041582  pop     rbp
0x180041583  pop     rbx
0x180041584  retn
0x180041585  mov     [rsp+78h+var_50], rsi; void *
0x18004158a  lea     rax, aCeremonyTypeDo; "Ceremony type does not have any data to"...
0x180041591  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x180041596  mov     r9d, 5Fh ; '_'; char
0x18004159c  lea     r8, aOnecoreuapNetW_18; "onecoreuap\\net\\wlan\\wfdsconmgr\\conm"...
0x1800415a3  lea     rdx, aWfdsconmgrCcer; "WFDSConMgr::CCeremonyManager::WriteCere"...
0x1800415aa  mov     ecx, 8007139Fh; char
0x1800415af  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
```
