# ManifestProcessor::AddChannelReferences(PublisherConfigWriteData &,AbstractDomElement &)

- ea: `0x140001738`
- end: `0x140001be7`
- name: `?AddChannelReferences@ManifestProcessor@@AEAAXAEAVPublisherConfigWriteData@@AEAVAbstractDomElement@@@Z`
- size: `1199`
- prototype: `void(ManifestProcessor *__hidden this, struct PublisherConfigWriteData *, struct AbstractDomElement *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x14001663c`

## callees

- `0x140001738`
- `0x140002b9c`
- `0x140003480`
- `0x1400034c4`
- `0x1400039a0`
- `0x14000cc80`
- `0x1400175f8`
- `0x14001b518`
- `0x140022cec`
- `0x140029ce4`
- `0x14002a2d4`
- `0x14002f6c8`
- `0x140031804`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400017fd`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140001a44`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1400017fd`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140001a44`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ManifestProcessor::AddChannelReferences(
        ManifestProcessor *this,
        struct PublisherConfigWriteData *a2,
        struct AbstractDomElement *a3)
{
  wmi::RefBase *v5; // rbx
  wmi::RefBase **v6; // rdi
  wmi::RefBase *v7; // rcx
  __int64 v8; // rax
  unsigned int v9; // edx
  __int64 v10; // r8
  const char *v11; // r8
  const char *v12; // r8
  wmi::RefBase **v13; // rdi
  int v14; // edi
  wmi::RefBase **v15; // rsi
  const wchar_t *v16; // r14
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 WinMetaChannel; // rax
  unsigned int v20; // esi
  __int64 v21; // rax
  const wchar_t *v22; // rax
  unsigned int v23; // r9d
  const char *v24; // r8
  _QWORD *v25; // rbx
  void **v26; // rax
  void *v27; // rcx
  wmi::RefBase *v28; // [rsp+20h] [rbp-59h] BYREF
  __int64 v29; // [rsp+28h] [rbp-51h] BYREF
  _QWORD v30[2]; // [rsp+30h] [rbp-49h] BYREF
  void *v31; // [rsp+40h] [rbp-39h]
  __int64 v32; // [rsp+48h] [rbp-31h]
  wmi::RefBase *v33; // [rsp+50h] [rbp-29h]
  _QWORD v34[2]; // [rsp+60h] [rbp-19h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v36[56]; // [rsp+98h] [rbp+1Fh] BYREF
  wmi::RefBase *v37; // [rsp+E0h] [rbp+67h] BYREF
  wmi::RefBase *v38; // [rsp+F0h] [rbp+77h] BYREF
  wmi::RefBase *v39; // [rsp+F8h] [rbp+7Fh] BYREF

  v37 = this;
  (*(void (__fastcall **)(struct AbstractDomElement *, wmi::RefBase **))(*(_QWORD *)a3 + 24LL))(a3, &v38);
  utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(v30);
  v5 = 0;
  v33 = 0;
  while ( 1 )
  {
    v6 = (wmi::RefBase **)(*(__int64 (__fastcall **)(wmi::RefBase *, wmi::RefBase **))(*(_QWORD *)v38 + 8LL))(v38, &v28);
    if ( v5 )
      wmi::RefBase::Release(v5);
    v5 = *v6;
    v33 = *v6;
    *v6 = 0;
    if ( v28 )
      wmi::RefBase::Release(v28);
    v28 = 0;
    if ( !v5 )
      break;
    (*(void (__fastcall **)(wmi::RefBase *, wmi::RefBase **, const wchar_t *))(*(_QWORD *)v5 + 40LL))(
      v5,
      &v39,
      L"value");
    v7 = v39;
    if ( v39 )
    {
      v8 = (*(__int64 (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v39 + 16LL))(v39);
      LODWORD(v37) = _o__wtoi(v8);
      if ( *(_QWORD **)utl::_Tree<unsigned long,unsigned long,utl::less<unsigned long>,utl::allocator<unsigned long>,0>::find<void>(
                         v30,
                         &v29,
                         &v37) != v30 )
      {
        eventlog::ai::WarningMessage((eventlog::ai *)0x4E, v9);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v12, 914);
        throw (EvtException *)pExceptionObject;
      }
      utl::_Tree<unsigned long,unsigned long,utl::less<unsigned long>,utl::allocator<unsigned long>,0>::_InsertImpl<unsigned long const &>(
        v30,
        v34,
        v10,
        &v37);
      if ( !v34[0] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v11, 920);
        throw (EvtException *)pExceptionObject;
      }
      v7 = v39;
    }
    if ( v7 )
      wmi::RefBase::Release(v7);
    v39 = 0;
  }
  v13 = (wmi::RefBase **)(*(__int64 (__fastcall **)(struct AbstractDomElement *, wmi::RefBase **))(*(_QWORD *)a3 + 24LL))(
                           a3,
                           &v37);
  if ( v38 )
    wmi::RefBase::Release(v38);
  v38 = 0;
  v38 = *v13;
  *v13 = 0;
  if ( v37 )
    wmi::RefBase::Release(v37);
  v14 = 16;
  while ( 1 )
  {
    v15 = (wmi::RefBase **)(*(__int64 (__fastcall **)(wmi::RefBase *, wmi::RefBase **))(*(_QWORD *)v38 + 8LL))(
                             v38,
                             &v28);
    if ( v5 )
      wmi::RefBase::Release(v5);
    v5 = *v15;
    v33 = *v15;
    *v15 = 0;
    if ( v28 )
      wmi::RefBase::Release(v28);
    v28 = 0;
    if ( !v5 )
      break;
    v16 = (const wchar_t *)(*(__int64 (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v5 + 16LL))(v5);
    (*(void (__fastcall **)(wmi::RefBase *, wmi::RefBase **, const wchar_t *))(*(_QWORD *)v5 + 40LL))(v5, &v39, L"name");
    if ( !v39 )
    {
      eventlog::ai::WarningMessage((eventlog::ai *)0x47, (unsigned int)L"{unknown}");
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_e92a5620c3b931af6feebe90701252ca_Traceguids, 13);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xDu, v24, 936);
      throw (EvtException *)pExceptionObject;
    }
    v17 = (*(__int64 (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v39 + 16LL))(v39);
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)(v17 + 2 * v18) );
    v34[0] = v17;
    v34[1] = v18;
    WinMetaChannel = FindWinMetaChannel(v34);
    if ( WinMetaChannel )
    {
      v20 = *(_DWORD *)(WinMetaChannel + 16);
    }
    else
    {
      (*(void (__fastcall **)(wmi::RefBase *, __int64 *, const wchar_t *))(*(_QWORD *)v5 + 40LL))(v5, &v29, L"value");
      if ( v29 )
      {
        v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        v20 = _o__wtoi(v21);
      }
      else
      {
        while ( 1 )
        {
          LODWORD(v37) = v14;
          if ( *(_QWORD **)utl::_Tree<unsigned long,unsigned long,utl::less<unsigned long>,utl::allocator<unsigned long>,0>::find<void>(
                             v30,
                             v36,
                             &v37) == v30 )
            break;
          ++v14;
        }
        v20 = v14++;
      }
      wmi::AutoRef<AbstractDomAttribute>::Release(&v29);
    }
    if ( !wcscmp_0(L"importChannel", v16) )
    {
      v22 = (const wchar_t *)(*(__int64 (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v39 + 16LL))(v39);
      v23 = 1;
    }
    else
    {
      if ( wcscmp_0(L"channel", v16) )
        goto LABEL_50;
      v22 = (const wchar_t *)(*(__int64 (__fastcall **)(wmi::RefBase *))(*(_QWORD *)v39 + 16LL))(v39);
      v23 = 0;
    }
    PublisherConfigWriteData::AddChannelReference(a2, v22, v20, v23);
LABEL_50:
    if ( v39 )
      wmi::RefBase::Release(v39);
    v39 = 0;
  }
  v25 = v31;
  if ( v31 == v30 )
    goto LABEL_66;
  while ( 2 )
  {
    v26 = (void **)v25[1];
    if ( v26 != &utl::_TreeSentinel )
    {
LABEL_64:
      v25 = v26;
      continue;
    }
    break;
  }
LABEL_60:
  v26 = (void **)v25[2];
  if ( v26 != &utl::_TreeSentinel )
    goto LABEL_64;
  while ( 1 )
  {
    v27 = v25;
    v25 = (_QWORD *)(*v25 & 0xFFFFFFFFFFFFFFFEuLL);
    operator delete(v27);
    if ( v25 == v30 )
      break;
    if ( (void **)v25[1] != &utl::_TreeSentinel )
    {
      v25[1] = &utl::_TreeSentinel;
      goto LABEL_60;
    }
  }
  v30[0] = v30;
  v30[1] = v30;
  v31 = v30;
  v32 = 0;
LABEL_66:
  if ( v38 )
    wmi::RefBase::Release(v38);
}

```

## disassembly

```asm
0x140001738  mov     [rsp-8+arg_0], rcx
0x14000173d  push    rbp
0x14000173e  push    rbx
0x14000173f  push    rsi
0x140001740  push    rdi
0x140001741  push    r12
0x140001743  push    r14
0x140001745  push    r15
0x140001747  lea     rbp, [rsp-27h]
0x14000174c  sub     rsp, 0A0h
0x140001753  mov     rsi, r8
0x140001756  mov     r15, rdx
0x140001759  mov     rax, [r8]
0x14000175c  lea     rdx, [rbp+57h+arg_10]
0x140001760  mov     rcx, r8
0x140001763  mov     rax, [rax+18h]
0x140001767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000176c  nop
0x14000176d  lea     rcx, [rbp+57h+var_A0]
0x140001771  call    ??0?$_Tree@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@Uistring_less_ordinal@tlx@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@$0A@@utl@@IEAA@XZ; utl::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>::_Tree<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,tlx::istring_less_ordinal,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>,0>(void)
0x140001776  nop
0x140001777  xor     r12d, r12d
0x14000177a  mov     ebx, r12d
0x14000177d  mov     [rbp+57h+var_80], rbx
0x140001781  mov     rcx, [rbp+57h+arg_10]
0x140001785  mov     rax, [rcx]
0x140001788  lea     rdx, [rbp+57h+var_B0]
0x14000178c  mov     rax, [rax+8]
0x140001790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001795  mov     rdi, rax
0x140001798  test    rbx, rbx
0x14000179b  jz      short loc_1400017A5
0x14000179d  mov     rcx, rbx; this
0x1400017a0  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1400017a5  mov     rbx, [rdi]
0x1400017a8  mov     [rbp+57h+var_80], rbx
0x1400017ac  mov     [rdi], r12
0x1400017af  mov     rcx, [rbp+57h+var_B0]; this
0x1400017b3  test    rcx, rcx
0x1400017b6  jz      short loc_1400017BD
0x1400017b8  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1400017bd  mov     [rbp+57h+var_B0], r12
0x1400017c1  test    rbx, rbx
0x1400017c4  jz      loc_140001914
0x1400017ca  mov     rax, [rbx]
0x1400017cd  lea     r8, aValue; "value"
0x1400017d4  lea     rdx, [rbp+57h+arg_18]
0x1400017d8  mov     rcx, rbx
0x1400017db  mov     rax, [rax+28h]
0x1400017df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400017e4  nop
0x1400017e5  mov     rcx, [rbp+57h+arg_18]
0x1400017e9  test    rcx, rcx
0x1400017ec  jz      short loc_14000183F
0x1400017ee  mov     rax, [rcx]
0x1400017f1  mov     rax, [rax+10h]
0x1400017f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400017fa  mov     rcx, rax
0x1400017fd  call    cs:__imp__o__wtoi
0x140001803  mov     dword ptr [rbp+57h+arg_0], eax
0x140001806  lea     r8, [rbp+57h+arg_0]
0x14000180a  lea     rdx, [rbp+57h+var_A8]
0x14000180e  lea     rcx, [rbp+57h+var_A0]
0x140001812  call    ??$find@X@?$_Tree@KKU?$less@K@utl@@V?$allocator@K@2@$0A@@utl@@QEAA?AV?$_TreeConstIt@K@1@AEBK@Z; utl::_Tree<ulong,ulong,utl::less<ulong>,utl::allocator<ulong>,0>::find<void>(ulong const &)
0x140001817  lea     rcx, [rbp+57h+var_A0]
0x14000181b  cmp     [rax], rcx
0x14000181e  jnz     loc_1400018AE
0x140001824  lea     r9, [rbp+57h+arg_0]
0x140001828  lea     rdx, [rbp+57h+var_70]
0x14000182c  lea     rcx, [rbp+57h+var_A0]
0x140001830  call    ??$_InsertImpl@AEBK@?$_Tree@KKU?$less@K@utl@@V?$allocator@K@2@$0A@@utl@@AEAA?AU?$pair@V?$_TreeConstIt@K@utl@@_N@1@PEAU?$_TreeNode@K@1@AEBK@Z; utl::_Tree<ulong,ulong,utl::less<ulong>,utl::allocator<ulong>,0>::_InsertImpl<ulong const &>(utl::_TreeNode<ulong> *,ulong const &)
0x140001835  cmp     [rbp+57h+var_70], r12
0x140001839  jz      short loc_140001852
0x14000183b  mov     rcx, [rbp+57h+arg_18]; this
0x14000183f  test    rcx, rcx
0x140001842  jz      short loc_140001849
0x140001844  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001849  mov     [rbp+57h+arg_18], r12
0x14000184d  jmp     loc_140001781
0x140001852  lea     rax, WPP_GLOBAL_Control
0x140001859  mov     ebx, 0Eh
0x14000185e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001865  cmp     rcx, rax
0x140001868  jz      short loc_14000188C
0x14000186a  test    byte ptr [rcx+1Ch], 4
0x14000186e  jz      short loc_14000188C
0x140001870  cmp     byte ptr [rcx+19h], 2
0x140001874  jb      short loc_14000188C
0x140001876  lea     edx, [rbx+27h]
0x140001879  mov     r9d, ebx
0x14000187c  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140001883  mov     rcx, [rcx+10h]
0x140001887  call    WPP_SF_d
0x14000188c  mov     r9d, 398h; int
0x140001892  mov     edx, ebx; unsigned int
0x140001894  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140001898  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14000189d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400018a4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400018a8  call    _CxxThrowException_0
0x1400018ae  mov     ecx, 4Eh ; 'N'; this
0x1400018b3  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x1400018b8  lea     rax, WPP_GLOBAL_Control
0x1400018bf  mov     ebx, 0Dh
0x1400018c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018cb  cmp     rcx, rax
0x1400018ce  jz      short loc_1400018F2
0x1400018d0  test    byte ptr [rcx+1Ch], 4
0x1400018d4  jz      short loc_1400018F2
0x1400018d6  cmp     byte ptr [rcx+19h], 2
0x1400018da  jb      short loc_1400018F2
0x1400018dc  lea     edx, [rbx+27h]
0x1400018df  mov     r9d, ebx
0x1400018e2  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x1400018e9  mov     rcx, [rcx+10h]
0x1400018ed  call    WPP_SF_d
0x1400018f2  mov     r9d, 392h; int
0x1400018f8  mov     edx, ebx; unsigned int
0x1400018fa  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400018fe  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140001903  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000190a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000190e  call    _CxxThrowException_0
0x140001914  mov     rax, [rsi]
0x140001917  lea     rdx, [rbp+57h+arg_0]
0x14000191b  mov     rcx, rsi
0x14000191e  mov     rax, [rax+18h]
0x140001922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001927  mov     rdi, rax
0x14000192a  mov     rcx, [rbp+57h+arg_10]; this
0x14000192e  test    rcx, rcx
0x140001931  jz      short loc_140001938
0x140001933  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001938  mov     [rbp+57h+arg_10], r12
0x14000193c  mov     rcx, [rdi]
0x14000193f  mov     [rbp+57h+arg_10], rcx
0x140001943  mov     [rdi], r12
0x140001946  mov     rcx, [rbp+57h+arg_0]; this
0x14000194a  test    rcx, rcx
0x14000194d  jz      short loc_140001954
0x14000194f  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001954  mov     edi, 10h
0x140001959  mov     rcx, [rbp+57h+arg_10]
0x14000195d  mov     rax, [rcx]
0x140001960  lea     rdx, [rbp+57h+var_B0]
0x140001964  mov     rax, [rax+8]
0x140001968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000196d  mov     rsi, rax
0x140001970  test    rbx, rbx
0x140001973  jz      short loc_14000197D
0x140001975  mov     rcx, rbx; this
0x140001978  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x14000197d  mov     rbx, [rsi]
0x140001980  mov     [rbp+57h+var_80], rbx
0x140001984  mov     [rsi], r12
0x140001987  mov     rcx, [rbp+57h+var_B0]; this
0x14000198b  test    rcx, rcx
0x14000198e  jz      short loc_140001995
0x140001990  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001995  mov     [rbp+57h+var_B0], r12
0x140001999  test    rbx, rbx
0x14000199c  jz      loc_140001B60
0x1400019a2  mov     rax, [rbx]
0x1400019a5  mov     rcx, rbx
0x1400019a8  mov     rax, [rax+10h]
0x1400019ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400019b1  mov     r14, rax
0x1400019b4  mov     rax, [rbx]
0x1400019b7  lea     r8, aName_0; "name"
0x1400019be  lea     rdx, [rbp+57h+arg_18]
0x1400019c2  mov     rcx, rbx
0x1400019c5  mov     rax, [rax+28h]
0x1400019c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400019ce  nop
0x1400019cf  mov     rcx, [rbp+57h+arg_18]
0x1400019d3  test    rcx, rcx
0x1400019d6  jz      loc_140001AF3
0x1400019dc  mov     rax, [rcx]
0x1400019df  mov     rax, [rax+10h]
0x1400019e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400019e8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400019ec  inc     rcx
0x1400019ef  cmp     [rax+rcx*2], r12w
0x1400019f4  jnz     short loc_1400019EC
0x1400019f6  mov     [rbp+57h+var_70], rax
0x1400019fa  mov     [rbp+57h+var_68], rcx
0x1400019fe  lea     rcx, [rbp+57h+var_70]
0x140001a02  call    ?FindWinMetaChannel@@YAPEBUWinMetaChannel@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; FindWinMetaChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140001a07  test    rax, rax
0x140001a0a  jz      short loc_140001A11
0x140001a0c  mov     esi, [rax+10h]
0x140001a0f  jmp     short loc_140001A7C
0x140001a11  mov     rax, [rbx]
0x140001a14  lea     r8, aValue; "value"
0x140001a1b  lea     rdx, [rbp+57h+var_A8]
0x140001a1f  mov     rcx, rbx
0x140001a22  mov     rax, [rax+28h]
0x140001a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a2b  nop
0x140001a2c  mov     rcx, [rbp+57h+var_A8]
0x140001a30  test    rcx, rcx
0x140001a33  jz      short loc_140001A4E
0x140001a35  mov     rax, [rcx]
0x140001a38  mov     rax, [rax+10h]
0x140001a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a41  mov     rcx, rax
0x140001a44  call    cs:__imp__o__wtoi
0x140001a4a  mov     esi, eax
0x140001a4c  jmp     short loc_140001A73
0x140001a4e  mov     dword ptr [rbp+57h+arg_0], edi
0x140001a51  lea     r8, [rbp+57h+arg_0]
0x140001a55  lea     rdx, [rbp+57h+var_38]
0x140001a59  lea     rcx, [rbp+57h+var_A0]
0x140001a5d  call    ??$find@X@?$_Tree@KKU?$less@K@utl@@V?$allocator@K@2@$0A@@utl@@QEAA?AV?$_TreeConstIt@K@1@AEBK@Z; utl::_Tree<ulong,ulong,utl::less<ulong>,utl::allocator<ulong>,0>::find<void>(ulong const &)
0x140001a62  lea     rdx, [rbp+57h+var_A0]
0x140001a66  cmp     [rax], rdx
0x140001a69  jz      short loc_140001A6F
0x140001a6b  inc     edi
0x140001a6d  jmp     short loc_140001A4E
0x140001a6f  mov     esi, edi
0x140001a71  inc     edi
0x140001a73  lea     rcx, [rbp+57h+var_A8]
0x140001a77  call    ?Release@?$AutoRef@VAbstractDomAttribute@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractDomAttribute>::Release(void)
0x140001a7c  mov     rdx, r14; String2
0x140001a7f  lea     rcx, aImportchannel; "importChannel"
0x140001a86  call    wcscmp_0
0x140001a8b  test    eax, eax
0x140001a8d  jnz     short loc_140001AA7
0x140001a8f  mov     rcx, [rbp+57h+arg_18]
0x140001a93  mov     rax, [rcx]
0x140001a96  mov     rax, [rax+10h]
0x140001a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a9f  mov     r9d, 1
0x140001aa5  jmp     short loc_140001ACD
0x140001aa7  mov     rdx, r14; String2
0x140001aaa  lea     rcx, aChannel; "channel"
0x140001ab1  call    wcscmp_0
0x140001ab6  test    eax, eax
0x140001ab8  jnz     short loc_140001ADC
0x140001aba  mov     rcx, [rbp+57h+arg_18]
0x140001abe  mov     rax, [rcx]
0x140001ac1  mov     rax, [rax+10h]
0x140001ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001aca  xor     r9d, r9d; unsigned int
0x140001acd  mov     r8d, esi; unsigned int
0x140001ad0  mov     rdx, rax; wchar_t *
0x140001ad3  mov     rcx, r15; this
0x140001ad6  call    ?AddChannelReference@PublisherConfigWriteData@@QEAAXPEB_WKK@Z; PublisherConfigWriteData::AddChannelReference(wchar_t const *,ulong,ulong)
0x140001adb  nop
0x140001adc  mov     rcx, [rbp+57h+arg_18]; this
0x140001ae0  test    rcx, rcx
0x140001ae3  jz      short loc_140001AEA
0x140001ae5  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x140001aea  mov     [rbp+57h+arg_18], r12
0x140001aee  jmp     loc_140001959
0x140001af3  lea     rdx, aUnknown_0; "{unknown}"
0x140001afa  mov     ecx, 47h ; 'G'; this
0x140001aff  call    ?WarningMessage@ai@eventlog@@YAXIZZ; eventlog::ai::WarningMessage(uint,...)
0x140001b04  lea     rax, WPP_GLOBAL_Control
0x140001b0b  mov     ebx, 0Dh
0x140001b10  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b17  cmp     rcx, rax
0x140001b1a  jz      short loc_140001B3E
0x140001b1c  test    byte ptr [rcx+1Ch], 4
0x140001b20  jz      short loc_140001B3E
0x140001b22  cmp     byte ptr [rcx+19h], 2
0x140001b26  jb      short loc_140001B3E
0x140001b28  lea     edx, [rbx+29h]
0x140001b2b  mov     r9d, ebx
0x140001b2e  lea     r8, WPP_e92a5620c3b931af6feebe90701252ca_Traceguids
0x140001b35  mov     rcx, [rcx+10h]
0x140001b39  call    WPP_SF_d
0x140001b3e  mov     r9d, 3A8h; int
0x140001b44  mov     edx, ebx; unsigned int
0x140001b46  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140001b4a  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140001b4f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140001b56  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140001b5a  call    _CxxThrowException_0
0x140001b60  mov     rbx, [rbp+57h+var_90]
0x140001b64  lea     rax, [rbp+57h+var_A0]
0x140001b68  cmp     rbx, rax
0x140001b6b  jz      short loc_140001BC7
0x140001b6d  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x140001b74  mov     rax, [rbx+8]
0x140001b78  cmp     rax, rdi
0x140001b7b  jnz     short loc_140001BAA
0x140001b7d  mov     rax, [rbx+10h]
0x140001b81  cmp     rax, rdi
0x140001b84  jnz     short loc_140001BAA
0x140001b86  mov     rcx, rbx; void *
0x140001b89  mov     rbx, [rbx]
0x140001b8c  and     rbx, 0FFFFFFFFFFFFFFFEh
0x140001b90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001b95  lea     rax, [rbp+57h+var_A0]
0x140001b99  cmp     rbx, rax
0x140001b9c  jz      short loc_140001BAF
0x140001b9e  cmp     [rbx+8], rdi
0x140001ba2  jz      short loc_140001B86
0x140001ba4  mov     [rbx+8], rdi
  ... truncated ...
```
