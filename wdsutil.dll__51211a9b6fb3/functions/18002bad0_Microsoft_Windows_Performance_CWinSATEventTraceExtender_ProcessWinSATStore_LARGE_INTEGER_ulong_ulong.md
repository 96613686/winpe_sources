# Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(_LARGE_INTEGER,ulong,ulong)

- ea: `0x18002bad0`
- end: `0x18002bd0f`
- name: `?ProcessWinSATStore@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJT_LARGE_INTEGER@@KK@Z`
- size: `575`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CWinSATEventTraceExtender *__hidden this, union _LARGE_INTEGER, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b330`

## callees

- `0x18002b490`
- `0x18002bad0`
- `0x180034010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002bb19`
- `ole32!CoCreateInstance` at `0x18002bb19`

## string_xrefs

- `0x18002bcaa`: `WinSAT/SystemConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATStore(
        Microsoft::Windows::Performance::CWinSATEventTraceExtender *this,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int a4)
{
  HRESULT Instance; // edi
  int v10; // ebx
  __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 v11; // [rsp+40h] [rbp-28h] BYREF
  struct IQueryRecentWinSATAssessment *ppv; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+50h] [rbp-18h] BYREF

  v13[1] = -2;
  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764,
               0,
               1u,
               &GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7,
               (LPVOID *)&ppv);
  if ( Instance < 0 )
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *, struct IQueryRecentWinSATAssessmentVtbl *))ppv->lpVtbl->Release)(
        ppv,
        ppv->lpVtbl);
    return (unsigned int)Instance;
  }
  v11 = WINSAT_ASSESSMENT_STATE_MIN;
  v13[0] = 0;
  Instance = ((__int64 (__fastcall *)(struct IQueryRecentWinSATAssessment *, _QWORD *))ppv->lpVtbl->get_Info)(ppv, v13);
  if ( Instance < 0 )
  {
    if ( v13[0] )
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0], *(_QWORD *)v13[0]);
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return (unsigned int)Instance;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *))(*(_QWORD *)v13[0] + 64LL))(
               v13[0],
               &v11);
  if ( Instance < 0 )
  {
    if ( v13[0] )
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0], *(_QWORD *)v13[0]);
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return (unsigned int)Instance;
  }
  if ( v13[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
  Instance = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
               this,
               ppv,
               v11,
               0x20u,
               (OLECHAR *)L"WinSAT/WinSPR",
               a2,
               a3,
               a4);
  if ( Instance < 0 )
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *, struct IQueryRecentWinSATAssessmentVtbl *))ppv->lpVtbl->Release)(
        ppv,
        ppv->lpVtbl);
    return (unsigned int)Instance;
  }
  Instance = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
               this,
               ppv,
               v11,
               0x22u,
               (OLECHAR *)L"WinSAT/Metrics",
               a2,
               a3,
               a4);
  if ( Instance < 0 )
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *, struct IQueryRecentWinSATAssessmentVtbl *))ppv->lpVtbl->Release)(
        ppv,
        ppv->lpVtbl);
    return (unsigned int)Instance;
  }
  v10 = Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(
          this,
          ppv,
          v11,
          0x24u,
          (OLECHAR *)L"WinSAT/SystemConfig",
          a2,
          a3,
          a4);
  if ( v10 >= 0 )
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *))ppv->lpVtbl->Release)(ppv);
    return 0;
  }
  else
  {
    if ( ppv )
      ((void (__fastcall *)(struct IQueryRecentWinSATAssessment *, struct IQueryRecentWinSATAssessmentVtbl *))ppv->lpVtbl->Release)(
        ppv,
        ppv->lpVtbl);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x18002bad0  push    rbp
0x18002bad2  push    rbx
0x18002bad3  push    rsi
0x18002bad4  push    rdi
0x18002bad5  push    r14
0x18002bad7  push    r15
0x18002bad9  mov     rbp, rsp
0x18002badc  sub     rsp, 68h
0x18002bae0  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x18002bae8  mov     esi, r9d
0x18002baeb  mov     r14d, r8d
0x18002baee  mov     rbx, rdx
0x18002baf1  mov     r15, rcx
0x18002baf4  mov     [rbp+var_20], 0
0x18002bafc  lea     rax, [rbp+var_20]
0x18002bb00  mov     [rsp+68h+ppv], rax; ppv
0x18002bb05  lea     r9, _GUID_f8ad5d1f_3b47_4bdc_9375_7c6b1da4eca7; riid
0x18002bb0c  xor     edx, edx; pUnkOuter
0x18002bb0e  lea     r8d, [rdx+1]; dwClsContext
0x18002bb12  lea     rcx, _GUID_f3bdfad3_f276_49e9_9b17_c474f48f0764; rclsid
0x18002bb19  call    cs:__imp_CoCreateInstance
0x18002bb20  nop     dword ptr [rax+rax+00h]
0x18002bb25  mov     edi, eax
0x18002bb27  test    eax, eax
0x18002bb29  jns     short loc_18002BB48
0x18002bb2b  mov     rcx, [rbp+var_20]
0x18002bb2f  test    rcx, rcx
0x18002bb32  jz      short loc_18002BB41
0x18002bb34  mov     rdx, [rcx]
0x18002bb37  mov     rax, [rdx+10h]
0x18002bb3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb40  nop
0x18002bb41  mov     eax, edi
0x18002bb43  jmp     loc_18002BD01
0x18002bb48  mov     [rbp+var_28], 0
0x18002bb4f  mov     [rbp+var_18], 0
0x18002bb57  mov     rcx, [rbp+var_20]
0x18002bb5b  mov     rax, [rcx]
0x18002bb5e  lea     rdx, [rbp+var_18]
0x18002bb62  mov     rax, [rax+40h]
0x18002bb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb6b  mov     edi, eax
0x18002bb6d  test    eax, eax
0x18002bb6f  jns     short loc_18002BB9F
0x18002bb71  mov     rcx, [rbp+var_18]
0x18002bb75  test    rcx, rcx
0x18002bb78  jz      short loc_18002BB87
0x18002bb7a  mov     rdx, [rcx]
0x18002bb7d  mov     rax, [rdx+10h]
0x18002bb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb86  nop
0x18002bb87  mov     rcx, [rbp+var_20]
0x18002bb8b  test    rcx, rcx
0x18002bb8e  jz      short loc_18002BB9D
0x18002bb90  mov     rax, [rcx]
0x18002bb93  mov     rax, [rax+10h]
0x18002bb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb9c  nop
0x18002bb9d  jmp     short loc_18002BB41
0x18002bb9f  mov     rcx, [rbp+var_18]
0x18002bba3  mov     rax, [rcx]
0x18002bba6  lea     rdx, [rbp+var_28]
0x18002bbaa  mov     rax, [rax+40h]
0x18002bbae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbb3  mov     edi, eax
0x18002bbb5  test    eax, eax
0x18002bbb7  jns     short loc_18002BBEA
0x18002bbb9  mov     rcx, [rbp+var_18]
0x18002bbbd  test    rcx, rcx
0x18002bbc0  jz      short loc_18002BBCF
0x18002bbc2  mov     rdx, [rcx]
0x18002bbc5  mov     rax, [rdx+10h]
0x18002bbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbce  nop
0x18002bbcf  mov     rcx, [rbp+var_20]
0x18002bbd3  test    rcx, rcx
0x18002bbd6  jz      short loc_18002BBE5
0x18002bbd8  mov     rax, [rcx]
0x18002bbdb  mov     rax, [rax+10h]
0x18002bbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbe4  nop
0x18002bbe5  jmp     loc_18002BB41
0x18002bbea  mov     rcx, [rbp+var_18]
0x18002bbee  test    rcx, rcx
0x18002bbf1  jz      short loc_18002BC00
0x18002bbf3  mov     rax, [rcx]
0x18002bbf6  mov     rax, [rax+10h]
0x18002bbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbff  nop
0x18002bc00  mov     [rsp+68h+var_30], esi; unsigned int
0x18002bc04  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002bc09  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18002bc0e  lea     rax, psz; "WinSAT/WinSPR"
0x18002bc15  mov     [rsp+68h+ppv], rax; psz
0x18002bc1a  mov     r9b, 20h ; ' '; unsigned __int8
0x18002bc1d  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18002bc21  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002bc25  mov     rcx, r15; this
0x18002bc28  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18002bc2d  mov     edi, eax
0x18002bc2f  test    eax, eax
0x18002bc31  jns     short loc_18002BC4E
0x18002bc33  mov     rcx, [rbp+var_20]
0x18002bc37  test    rcx, rcx
0x18002bc3a  jz      short loc_18002BC49
0x18002bc3c  mov     rdx, [rcx]
0x18002bc3f  mov     rax, [rdx+10h]
0x18002bc43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc48  nop
0x18002bc49  jmp     loc_18002BB41
0x18002bc4e  mov     [rsp+68h+var_30], esi; unsigned int
0x18002bc52  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002bc57  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18002bc5c  lea     rax, aWinsatMetrics; "WinSAT/Metrics"
0x18002bc63  mov     [rsp+68h+ppv], rax; psz
0x18002bc68  mov     r9b, 22h ; '"'; unsigned __int8
0x18002bc6b  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18002bc6f  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002bc73  mov     rcx, r15; this
0x18002bc76  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18002bc7b  mov     edi, eax
0x18002bc7d  test    eax, eax
0x18002bc7f  jns     short loc_18002BC9C
0x18002bc81  mov     rcx, [rbp+var_20]
0x18002bc85  test    rcx, rcx
0x18002bc88  jz      short loc_18002BC97
0x18002bc8a  mov     rdx, [rcx]
0x18002bc8d  mov     rax, [rdx+10h]
0x18002bc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc96  nop
0x18002bc97  jmp     loc_18002BB41
0x18002bc9c  mov     [rsp+68h+var_30], esi; unsigned int
0x18002bca0  mov     [rsp+68h+var_38], r14d; unsigned int
0x18002bca5  mov     qword ptr [rsp+68h+var_40], rbx; union _LARGE_INTEGER
0x18002bcaa  lea     rax, aWinsatSystemco; "WinSAT/SystemConfig"
0x18002bcb1  mov     [rsp+68h+ppv], rax; psz
0x18002bcb6  mov     r9b, 24h ; '$'; unsigned __int8
0x18002bcb9  mov     r8d, [rbp+var_28]; enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002
0x18002bcbd  mov     rdx, [rbp+var_20]; struct IQueryRecentWinSATAssessment *
0x18002bcc1  mov     rcx, r15; this
0x18002bcc4  call    ?ProcessWinSATAssessmentInfo@CWinSATEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEAUIQueryRecentWinSATAssessment@@W4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@EPEBGT_LARGE_INTEGER@@KK@Z; Microsoft::Windows::Performance::CWinSATEventTraceExtender::ProcessWinSATAssessmentInfo(IQueryRecentWinSATAssessment *,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002,uchar,ushort const *,_LARGE_INTEGER,ulong,ulong)
0x18002bcc9  mov     ebx, eax
0x18002bccb  test    eax, eax
0x18002bccd  jns     short loc_18002BCE9
0x18002bccf  mov     rcx, [rbp+var_20]
0x18002bcd3  test    rcx, rcx
0x18002bcd6  jz      short loc_18002BCE5
0x18002bcd8  mov     rdx, [rcx]
0x18002bcdb  mov     rax, [rdx+10h]
0x18002bcdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bce4  nop
0x18002bce5  mov     eax, ebx
0x18002bce7  jmp     short loc_18002BD01
0x18002bce9  mov     rcx, [rbp+var_20]
0x18002bced  test    rcx, rcx
0x18002bcf0  jz      short loc_18002BCFF
0x18002bcf2  mov     rax, [rcx]
0x18002bcf5  mov     rax, [rax+10h]
0x18002bcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcfe  nop
0x18002bcff  xor     eax, eax
0x18002bd01  add     rsp, 68h
0x18002bd05  pop     r15
0x18002bd07  pop     r14
0x18002bd09  pop     rdi
0x18002bd0a  pop     rsi
0x18002bd0b  pop     rbx
0x18002bd0c  pop     rbp
0x18002bd0d  retn
```
