# CWcnUpnpDiscoveryListener::DeviceAdded(long,IUPnPDevice *)

- ea: `0x180042400`
- end: `0x18004279f`
- name: `?DeviceAdded@CWcnUpnpDiscoveryListener@@UEAAJJPEAUIUPnPDevice@@@Z`
- size: `927`
- prototype: `__int64 __fastcall(CWcnUpnpDiscoveryListener *this, __int64, struct IUnknown *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops`

## callees

- `0x180001b68`
- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180026ab4`
- `0x180042400`
- `0x180042a40`
- `0x180043160`
- `0x180043338`
- `0x180043478`
- `0x180053004`
- `0x180056dfe`
- `0x18005a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180042750`
- `msvcrt!??3@YAXPEAX@Z` at `0x180042750`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800426b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800426b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004266f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004266f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800426c7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800426c7`
- `OLEAUT32!__imp_SysFreeString` at `0x180042714`
- `OLEAUT32!__imp_SysFreeString` at `0x18004272e`
- `OLEAUT32!__imp_SysFreeString` at `0x180042714`
- `OLEAUT32!__imp_SysFreeString` at `0x18004272e`

## pseudocode

```c
__int64 __fastcall CWcnUpnpDiscoveryListener::DeviceAdded(
        CWcnUpnpDiscoveryListener *this,
        __int64 a2,
        struct IUnknown *a3)
{
  CWcnUpnpDiscoveryListener *v4; // r13
  unsigned int *v5; // rdi
  _QWORD *v6; // r10
  const char *Indent; // rax
  __int64 v8; // r10
  int PeerGuidForUdn; // eax
  int v11; // ebx
  _QWORD *v12; // r10
  __int64 v13; // rdx
  const char *v14; // rax
  __int64 v15; // rdx
  const char *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // r10
  char *v19; // rax
  CWcnUpnpDiscoveryListener *v20; // rcx
  CWcnUpnpGit *v21; // rcx
  RTL_SRWLOCK *v22; // r15
  CWcnUpnpGit *v23; // rcx
  unsigned int v24; // edx
  unsigned int v25; // eax
  __int64 v26; // r10
  __int64 v27; // rax
  unsigned int *v28; // [rsp+30h] [rbp-48h] BYREF
  wchar_t *String1; // [rsp+38h] [rbp-40h] BYREF
  RTL_SRWLOCK *v30; // [rsp+40h] [rbp-38h]
  std::bad_alloc *v31; // [rsp+48h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+20h] BYREF

  v4 = this;
  String1 = 0;
  bstrString = 0;
  v5 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v8 + 16), 22, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, Indent);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_s(v6[2], 23, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, "pDevice");
    return 2147500035LL;
  }
  PeerGuidForUdn = ((__int64 (__fastcall *)(struct IUnknown *, wchar_t **))a3->lpVtbl[4].Release)(a3, &String1);
  v11 = PeerGuidForUdn;
  if ( PeerGuidForUdn < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_42;
    v13 = 24;
    goto LABEL_13;
  }
  if ( wcscmp_0(String1, L"urn:schemas-wifialliance-org:device:WFADevice:1") )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      goto LABEL_42;
    v14 = GetIndent(0);
    v15 = 25;
    v16 = v14;
    goto LABEL_40;
  }
  PeerGuidForUdn = ((__int64 (__fastcall *)(struct IUnknown *, BSTR *))a3->lpVtbl[4].QueryInterface)(a3, &bstrString);
  v11 = PeerGuidForUdn;
  if ( PeerGuidForUdn >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v17 = (unsigned int)GetIndent(0);
      WPP_SF_sS(
        *(_QWORD *)(v18 + 16),
        27,
        (unsigned int)WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids,
        v17,
        (__int64)bstrString);
    }
    v19 = (char *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v19 )
    {
      *((_DWORD *)v19 + 5) = 0;
      v5 = (unsigned int *)v19;
      v28 = (unsigned int *)v19;
      *(_DWORD *)v19 = 0;
      PeerGuidForUdn = CWcnUpnpDiscoveryListener::GetPeerGuidForUdn(v20, bstrString, (struct _GUID *)(v19 + 4));
      v11 = PeerGuidForUdn;
      if ( PeerGuidForUdn >= 0 )
      {
        PeerGuidForUdn = CWcnUpnpGit::PutItem(v21, &GUID_3d44d0d1_98c9_4889_acd1_f9d674bf2221, a3, v5 + 5);
        v11 = PeerGuidForUdn;
        if ( PeerGuidForUdn >= 0 )
        {
          v22 = (RTL_SRWLOCK *)((char *)v4 + 88);
          v30 = (RTL_SRWLOCK *)((char *)v4 + 88);
          AcquireSRWLockExclusive((PSRWLOCK)v4 + 11);
          if ( *((_QWORD *)v4 + 16) < 0x384u )
          {
            if ( __eh34_try(-1, 0) )
            {
              __eh34_scope_strut(0);
              std::queue<CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA *>::push((char *)v4 + 96, &v28);
              v5 = 0;
              v28 = 0;
            }
            if ( __eh34_catch(0) )
            {
              if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', &v31) )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v27 = (*(__int64 (__fastcall **)(std::bad_alloc *))(*(_QWORD *)v31 + 8LL))(v31);
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    31,
                    WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids,
                    v27);
                }
                v4 = this;
                v11 = -2147024882;
                v5 = v28;
                v22 = v30;
                __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180042696);
              }
            }
          }
          ReleaseSRWLockExclusive(v22);
          if ( v11 >= 0 )
            SubmitThreadpoolWork(*((PTP_WORK *)v4 + 9));
          goto LABEL_41;
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_42;
        v13 = 30;
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_42;
        v13 = 29;
      }
      goto LABEL_13;
    }
    v11 = -2147024882;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_42;
    v15 = 28;
    v16 = "pCallbackData";
LABEL_40:
    WPP_SF_s(v12[2], v15, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, v16);
    goto LABEL_41;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_42;
  v13 = 26;
LABEL_13:
  WPP_SF_d(v12[2], v13, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, (unsigned int)PeerGuidForUdn);
LABEL_41:
  v12 = WPP_GLOBAL_Control;
LABEL_42:
  if ( String1 )
  {
    SysFreeString(String1);
    v12 = WPP_GLOBAL_Control;
  }
  v23 = (CWcnUpnpGit *)bstrString;
  if ( bstrString )
  {
    SysFreeString(bstrString);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    v24 = v5[5];
    if ( v24 )
      CWcnUpnpGit::RemoveItem(v23, v24);
    operator delete(v5);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && (v11 < 0 || *((_BYTE *)v12 + 25) >= 6u) )
  {
    v25 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v26 + 16), 32, (unsigned int)WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids, v25, v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180042400  mov     rax, rsp
0x180042403  mov     [rax+8], rcx
0x180042407  push    rbx
0x180042408  push    rsi
0x180042409  push    rdi
0x18004240a  push    r13
0x18004240c  push    r15
0x18004240e  sub     rsp, 50h
0x180042412  mov     r15, r8
0x180042415  mov     r13, rcx
0x180042418  mov     qword ptr [rax-40h], 0
0x180042420  mov     qword ptr [rax+20h], 0
0x180042428  xor     edi, edi
0x18004242a  lea     rsi, WPP_GLOBAL_Control
0x180042431  mov     r10, cs:WPP_GLOBAL_Control
0x180042438  cmp     r10, rsi
0x18004243b  jz      short loc_180042469
0x18004243d  cmp     byte ptr [r10+19h], 6
0x180042442  jb      short loc_180042469
0x180042444  lea     ecx, [rdi+1]; int
0x180042447  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18004244c  lea     edx, [rdi+16h]
0x18004244f  mov     r9, rax
0x180042452  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x180042459  mov     rcx, [r10+10h]
0x18004245d  call    WPP_SF_s
0x180042462  mov     r10, cs:WPP_GLOBAL_Control
0x180042469  test    r15, r15
0x18004246c  jnz     short loc_18004249F
0x18004246e  cmp     r10, rsi
0x180042471  jz      short loc_180042495
0x180042473  cmp     byte ptr [r10+19h], 2
0x180042478  jb      short loc_180042495
0x18004247a  lea     edx, [r15+17h]
0x18004247e  lea     r9, aPdevice; "pDevice"
0x180042485  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x18004248c  mov     rcx, [r10+10h]
0x180042490  call    WPP_SF_s
0x180042495  mov     eax, 80004003h
0x18004249a  jmp     loc_180042793
0x18004249f  mov     rax, [r15]
0x1800424a2  lea     rdx, [rsp+78h+String1]
0x1800424a7  mov     rcx, r15
0x1800424aa  mov     rax, [rax+70h]
0x1800424ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800424b3  mov     ebx, eax
0x1800424b5  test    eax, eax
0x1800424b7  jns     short loc_1800424F1
0x1800424b9  mov     r10, cs:WPP_GLOBAL_Control
0x1800424c0  cmp     r10, rsi
0x1800424c3  jz      loc_18004270A
0x1800424c9  cmp     byte ptr [r10+19h], 2
0x1800424ce  jb      loc_18004270A
0x1800424d4  mov     edx, 18h
0x1800424d9  mov     r9d, eax
0x1800424dc  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x1800424e3  mov     rcx, [r10+10h]
0x1800424e7  call    WPP_SF_d
0x1800424ec  jmp     loc_180042703
0x1800424f1  lea     rdx, aUrnSchemasWifi; "urn:schemas-wifialliance-org:device:WFA"...
0x1800424f8  mov     rcx, [rsp+78h+String1]; String1
0x1800424fd  call    wcscmp_0
0x180042502  test    eax, eax
0x180042504  jz      short loc_180042535
0x180042506  mov     r10, cs:WPP_GLOBAL_Control
0x18004250d  cmp     r10, rsi
0x180042510  jz      loc_18004270A
0x180042516  cmp     byte ptr [r10+19h], 5
0x18004251b  jb      loc_18004270A
0x180042521  xor     ecx, ecx; int
0x180042523  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180042528  mov     edx, 19h
0x18004252d  mov     r9, rax
0x180042530  jmp     loc_1800426F3
0x180042535  mov     rax, [r15]
0x180042538  lea     rdx, [rsp+78h+bstrString]
0x180042540  mov     rcx, r15
0x180042543  mov     rax, [rax+60h]
0x180042547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004254c  mov     ebx, eax
0x18004254e  test    eax, eax
0x180042550  jns     short loc_180042577
0x180042552  mov     r10, cs:WPP_GLOBAL_Control
0x180042559  cmp     r10, rsi
0x18004255c  jz      loc_18004270A
0x180042562  cmp     byte ptr [r10+19h], 2
0x180042567  jb      loc_18004270A
0x18004256d  mov     edx, 1Ah
0x180042572  jmp     loc_1800424D9
0x180042577  mov     r10, cs:WPP_GLOBAL_Control
0x18004257e  cmp     r10, rsi
0x180042581  jz      short loc_1800425B6
0x180042583  cmp     byte ptr [r10+19h], 4
0x180042588  jb      short loc_1800425B6
0x18004258a  xor     ecx, ecx; int
0x18004258c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180042591  mov     edx, 1Bh
0x180042596  mov     r8, [rsp+78h+bstrString]
0x18004259e  mov     [rsp+78h+var_58], r8
0x1800425a3  mov     r9, rax
0x1800425a6  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x1800425ad  mov     rcx, [r10+10h]
0x1800425b1  call    WPP_SF_sS
0x1800425b6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800425bd  mov     ecx, 20h ; ' '; unsigned __int64
0x1800425c2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800425c7  mov     [rsp+78h+arg_10], rax
0x1800425cf  test    rax, rax
0x1800425d2  jz      loc_1800426CF
0x1800425d8  mov     [rax+14h], edi
0x1800425db  mov     rdi, rax
0x1800425de  mov     [rsp+78h+var_48], rax
0x1800425e3  mov     dword ptr [rax], 0
0x1800425e9  lea     r8, [rax+4]; struct _GUID *
0x1800425ed  mov     rdx, [rsp+78h+bstrString]; unsigned __int16 *
0x1800425f5  call    ?GetPeerGuidForUdn@CWcnUpnpDiscoveryListener@@AEAAJPEBGPEAU_GUID@@@Z; CWcnUpnpDiscoveryListener::GetPeerGuidForUdn(ushort const *,_GUID *)
0x1800425fa  mov     ebx, eax
0x1800425fc  test    eax, eax
0x1800425fe  jns     short loc_180042625
0x180042600  mov     r10, cs:WPP_GLOBAL_Control
0x180042607  cmp     r10, rsi
0x18004260a  jz      loc_18004270A
0x180042610  cmp     byte ptr [r10+19h], 2
0x180042615  jb      loc_18004270A
0x18004261b  mov     edx, 1Dh
0x180042620  jmp     loc_1800424D9
0x180042625  lea     r9, [rdi+14h]; unsigned int *
0x180042629  mov     r8, r15; struct IUnknown *
0x18004262c  lea     rdx, _GUID_3d44d0d1_98c9_4889_acd1_f9d674bf2221; struct _GUID *
0x180042633  call    ?PutItem@CWcnUpnpGit@@QEAAJAEBU_GUID@@PEAUIUnknown@@PEAK@Z; CWcnUpnpGit::PutItem(_GUID const &,IUnknown *,ulong *)
0x180042638  mov     ebx, eax
0x18004263a  test    eax, eax
0x18004263c  jns     short loc_180042663
0x18004263e  mov     r10, cs:WPP_GLOBAL_Control
0x180042645  cmp     r10, rsi
0x180042648  jz      loc_18004270A
0x18004264e  cmp     byte ptr [r10+19h], 2
0x180042653  jb      loc_18004270A
0x180042659  mov     edx, 1Eh
0x18004265e  jmp     loc_1800424D9
0x180042663  lea     r15, [r13+58h]
0x180042667  mov     [rsp+78h+var_38], r15
0x18004266c  mov     rcx, r15; SRWLock
0x18004266f  call    cs:__imp_AcquireSRWLockExclusive
0x180042675  lea     rcx, [r13+60h]
0x180042679  cmp     qword ptr [rcx+20h], 384h
0x180042681  jnb     short loc_1800426B6
0x180042683  lea     rdx, [rsp+78h+var_48]
0x180042688  call    ?push@?$queue@PEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@V?$deque@PEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@V?$allocator@PEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@@std@@@std@@@std@@QEAAXAEBQEAUtagWCN_CALLBACK_DATA@CWcnUpnpDiscoveryListener@@@Z; std::queue<CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA *>::push(CWcnUpnpDiscoveryListener::tagWCN_CALLBACK_DATA * const &)
0x18004268d  xor     edi, edi
0x18004268f  mov     [rsp+78h+var_48], rdi
0x180042694  jmp     short loc_1800426B6
0x180042696  lea     rsi, WPP_GLOBAL_Control
0x18004269d  mov     r13, [rsp+78h+arg_0]
0x1800426a5  mov     ebx, dword ptr [rsp+78h+arg_10]
0x1800426ac  mov     rdi, [rsp+78h+var_48]
0x1800426b1  mov     r15, [rsp+78h+var_38]
0x1800426b6  mov     rcx, r15; SRWLock
0x1800426b9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800426bf  test    ebx, ebx
0x1800426c1  js      short loc_180042703
0x1800426c3  mov     rcx, [r13+48h]; pwk
0x1800426c7  call    cs:__imp_SubmitThreadpoolWork
0x1800426cd  jmp     short loc_180042703
0x1800426cf  mov     ebx, 8007000Eh
0x1800426d4  mov     r10, cs:WPP_GLOBAL_Control
0x1800426db  cmp     r10, rsi
0x1800426de  jz      short loc_18004270A
0x1800426e0  cmp     byte ptr [r10+19h], 2
0x1800426e5  jb      short loc_18004270A
0x1800426e7  mov     edx, 1Ch
0x1800426ec  lea     r9, aPcallbackdata; "pCallbackData"
0x1800426f3  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x1800426fa  mov     rcx, [r10+10h]
0x1800426fe  call    WPP_SF_s
0x180042703  mov     r10, cs:WPP_GLOBAL_Control
0x18004270a  mov     rcx, [rsp+78h+String1]; bstrString
0x18004270f  test    rcx, rcx
0x180042712  jz      short loc_180042721
0x180042714  call    cs:__imp_SysFreeString
0x18004271a  mov     r10, cs:WPP_GLOBAL_Control
0x180042721  mov     rcx, [rsp+78h+bstrString]; bstrString
0x180042729  test    rcx, rcx
0x18004272c  jz      short loc_18004273B
0x18004272e  call    cs:__imp_SysFreeString
0x180042734  mov     r10, cs:WPP_GLOBAL_Control
0x18004273b  test    rdi, rdi
0x18004273e  jz      short loc_18004275D
0x180042740  mov     edx, [rdi+14h]; unsigned int
0x180042743  test    edx, edx
0x180042745  jz      short loc_18004274D
0x180042747  call    ?RemoveItem@CWcnUpnpGit@@QEAAXK@Z; CWcnUpnpGit::RemoveItem(ulong)
0x18004274c  nop
0x18004274d  mov     rcx, rdi
0x180042750  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180042756  mov     r10, cs:WPP_GLOBAL_Control
0x18004275d  cmp     r10, rsi
0x180042760  jz      short loc_180042791
0x180042762  test    ebx, ebx
0x180042764  js      short loc_18004276D
0x180042766  cmp     byte ptr [r10+19h], 6
0x18004276b  jb      short loc_180042791
0x18004276d  or      ecx, 0FFFFFFFFh; int
0x180042770  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180042775  mov     edx, 20h ; ' '
0x18004277a  mov     dword ptr [rsp+78h+var_58], ebx
0x18004277e  mov     r9, rax
0x180042781  lea     r8, WPP_7bf47ecc9a493a7bd583ff0da065602e_Traceguids
0x180042788  mov     rcx, [r10+10h]
0x18004278c  call    WPP_SF_sd
0x180042791  mov     eax, ebx
0x180042793  add     rsp, 50h
0x180042797  pop     r15
0x180042799  pop     r13
0x18004279b  pop     rdi
0x18004279c  pop     rsi
0x18004279d  pop     rbx
0x18004279e  retn
```
