# ATL::CComObject<CWdsTransportNamespaceAutoCast>::CreateInstance(ATL::CComObject<CWdsTransportNamespaceAutoCast> * *)

- ea: `0x180011128`
- end: `0x180011218`
- name: `?CreateInstance@?$CComObject@VCWdsTransportNamespaceAutoCast@@@ATL@@SAJPEAPEAV12@@Z`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011448`

## callees

- `0x1800011bc`
- `0x18000452c`
- `0x180006654`
- `0x180006680`
- `0x180010b70`
- `0x180011128`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWdsTransportNamespaceAutoCast>::CreateInstance(CWdsTransportNamespace **a1)
{
  CWdsTransportNamespace **v1; // r14
  unsigned int v3; // esi
  CWdsTransportNamespace *v4; // rax
  CWdsTransportNamespace *v5; // rdi
  int v6; // eax
  int v7; // edx
  CWdsTransportNamespace *v9; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = (CWdsTransportNamespace *)operator new(0xD8u);
    v5 = v4;
    if ( v4 )
    {
      CWdsTransportNamespace::CWdsTransportNamespace(v4);
      *(_QWORD *)v5 = &ATL::CComObject<CWdsTransportNamespaceAutoCast>::`vftable'{for `CWdsTransportNamespace'};
      *((_QWORD *)v5 + 26) = &ATL::CComObject<CWdsTransportNamespaceAutoCast>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceAutoCast,&_GUID const IID_IWdsTransportNamespaceAutoCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v5 + 2);
    v6 = ATL::CComSafeDeleteCriticalSection::Init((CWdsTransportNamespace *)((char *)v5 + 16));
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v5 + 2);
    if ( v3 )
    {
      (*(void (__fastcall **)(CWdsTransportNamespace *, __int64))(*(_QWORD *)v5 + 256LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x180011128  mov     [rsp+arg_18], rbx
0x18001112d  mov     [rsp+arg_0], rcx
0x180011132  push    rsi
0x180011133  push    rdi
0x180011134  push    r14
0x180011136  sub     rsp, 20h
0x18001113a  mov     r14, rcx
0x18001113d  test    rcx, rcx
0x180011140  jnz     short loc_18001114C
0x180011142  mov     eax, 80004003h
0x180011147  jmp     loc_180011209
0x18001114c  and     qword ptr [rcx], 0
0x180011150  mov     esi, 8007000Eh
0x180011155  mov     [rsp+38h+arg_8], esi
0x180011159  and     [rsp+38h+arg_10], 0
0x18001115f  mov     ecx, 0D8h; Size
0x180011164  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011169  mov     rdi, rax
0x18001116c  test    rdi, rdi
0x18001116f  jz      short loc_1800111A4
0x180011171  mov     rcx, rax; this
0x180011174  call    ??0CWdsTransportNamespace@@QEAA@XZ; CWdsTransportNamespace::CWdsTransportNamespace(void)
0x180011179  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceAutoCast@@@ATL@@6BCWdsTransportNamespace@@@; const ATL::CComObject<CWdsTransportNamespaceAutoCast>::`vftable'{for `CWdsTransportNamespace'}
0x180011180  mov     [rdi], rax
0x180011183  lea     rax, ??_7?$CComObject@VCWdsTransportNamespaceAutoCast@@@ATL@@6B?$IDispatchImpl@UIWdsTransportNamespaceAutoCast@@$1?IID_IWdsTransportNamespaceAutoCast@@3U_GUID@@B$1?LIBID_WdsTptMgmtLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CWdsTransportNamespaceAutoCast>::`vftable'{for `ATL::IDispatchImpl<IWdsTransportNamespaceAutoCast,&_GUID const IID_IWdsTransportNamespaceAutoCast,&_GUID const LIBID_WdsTptMgmtLib,1,0,ATL::CComTypeInfoHolder>'}
0x18001118a  mov     [rdi+0D0h], rax
0x180011191  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011198  mov     rax, [rcx]
0x18001119b  mov     rax, [rax+8]
0x18001119f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111a4  mov     [rsp+38h+arg_10], rdi
0x1800111a9  jmp     short loc_1800111B9
0x1800111ab  mov     r14, [rsp+38h+arg_0]
0x1800111b0  mov     esi, [rsp+38h+arg_8]
0x1800111b4  mov     rdi, [rsp+38h+arg_10]
0x1800111b9  test    rdi, rdi
0x1800111bc  jz      short loc_180011204
0x1800111be  lea     rcx, [rdi+8]; volatile int *
0x1800111c2  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x1800111c7  lea     rcx, [rdi+10h]; this
0x1800111cb  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x1800111d0  xor     edx, edx
0x1800111d2  test    eax, eax
0x1800111d4  cmovs   edx, eax
0x1800111d7  xor     esi, esi
0x1800111d9  test    edx, edx
0x1800111db  cmovs   esi, edx
0x1800111de  lea     rcx, [rdi+8]; volatile int *
0x1800111e2  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x1800111e7  test    esi, esi
0x1800111e9  jz      short loc_180011204
0x1800111eb  mov     rdx, [rdi]
0x1800111ee  mov     rax, [rdx+100h]
0x1800111f5  mov     edx, 1
0x1800111fa  mov     rcx, rdi
0x1800111fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011202  xor     edi, edi
0x180011204  mov     [r14], rdi
0x180011207  mov     eax, esi
0x180011209  mov     rbx, [rsp+38h+arg_18]
0x18001120e  add     rsp, 20h
0x180011212  pop     r14
0x180011214  pop     rdi
0x180011215  pop     rsi
0x180011216  retn
```
