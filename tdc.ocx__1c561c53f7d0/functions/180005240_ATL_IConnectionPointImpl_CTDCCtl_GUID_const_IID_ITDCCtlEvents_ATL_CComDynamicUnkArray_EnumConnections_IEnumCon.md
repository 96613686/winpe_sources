# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::EnumConnections(IEnumConnections * *)

- ea: `0x180005240`
- end: `0x1800053dd`
- name: `?EnumConnections@?$IConnectionPointImpl@VCTDCCtl@@$1?IID_ITDCCtlEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800011ac`
- `0x1800011b8`
- `0x180005240`
- `0x180006bb0`
- `0x1800070ac`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::EnumConnections(
        __int64 a1,
        char **a2)
{
  char *v5; // rax
  char *v6; // rbx
  struct ATL::CAtlModule *v7; // rcx
  _DWORD *v8; // rax
  int v9; // ebp
  _QWORD *v10; // rdi
  _DWORD *v11; // r15
  unsigned __int64 i; // rcx
  _QWORD *v13; // rcx
  int v14; // edx
  _QWORD *v15; // r8
  int Interface; // edi

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = (char *)operator new(0x40u);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  v7 = ATL::_pAtlModule;
  *((_QWORD *)v5 + 1) = 0;
  *((_QWORD *)v5 + 4) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_DWORD *)v5 + 10) = 0;
  *((_DWORD *)v5 + 12) = 0;
  *(_QWORD *)v5 = &ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v7 + 8LL))(v7);
  v8 = operator new[](saturated_mul(*(int *)(a1 + 16), 0x10u));
  v9 = (int)v8;
  if ( !v8 )
  {
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 56LL))(v6, 1);
    return 2147942414LL;
  }
  v10 = *(_QWORD **)(a1 + 8);
  v11 = v8;
  for ( i = (unsigned __int64)&v10[*(int *)(a1 + 16)];
        (unsigned __int64)v10 < i;
        i = *(_QWORD *)(a1 + 8) + 8LL * *(int *)(a1 + 16) )
  {
    if ( *v10 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
      *(_QWORD *)v11 = *v10;
      if ( *v10 )
      {
        v13 = *(_QWORD **)(a1 + 8);
        v14 = 1;
        v15 = &v13[*(int *)(a1 + 16)];
        while ( v13 < v15 )
        {
          if ( *v13 == *v10 )
            goto LABEL_15;
          ++v14;
          ++v13;
        }
      }
      v14 = 0;
LABEL_15:
      v11[2] = v14;
      v11 += 4;
    }
    ++v10;
  }
  ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(
    (_DWORD)v6,
    v9,
    (_DWORD)v11,
    0,
    2);
  Interface = ATL::CComObjectRootBase::InternalQueryInterface(
                v6,
                (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                &GUID_b196b287_bab4_101a_b69c_00aa00341d07,
                a2);
  if ( Interface < 0 )
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 56LL))(v6, 1);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x180005240  push    rbx
0x180005242  push    rbp
0x180005243  push    rsi
0x180005244  push    rdi
0x180005245  push    r14
0x180005247  push    r15
0x180005249  sub     rsp, 38h
0x18000524d  mov     r14, rdx
0x180005250  mov     rsi, rcx
0x180005253  test    rdx, rdx
0x180005256  jnz     short loc_180005262
0x180005258  mov     eax, 80004003h
0x18000525d  jmp     loc_180005308
0x180005262  mov     ecx, 40h ; '@'; Size
0x180005267  mov     qword ptr [rdx], 0
0x18000526e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005273  mov     rbx, rax
0x180005276  test    rax, rax
0x180005279  jz      loc_180005303
0x18000527f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005286  mov     qword ptr [rax+8], 0
0x18000528e  mov     qword ptr [rax+20h], 0
0x180005296  mov     qword ptr [rax+18h], 0
0x18000529e  mov     qword ptr [rax+10h], 0
0x1800052a6  mov     dword ptr [rax+28h], 0
0x1800052ad  mov     dword ptr [rax+30h], 0
0x1800052b4  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vftable'
0x1800052bb  mov     [rbx], rax
0x1800052be  mov     rax, [rcx]
0x1800052c1  mov     rax, [rax+8]
0x1800052c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ca  movsxd  rcx, dword ptr [rsi+10h]
0x1800052ce  mov     eax, 10h
0x1800052d3  mul     rcx
0x1800052d6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800052dd  cmovb   rax, rcx
0x1800052e1  mov     rcx, rax; unsigned __int64
0x1800052e4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800052e9  mov     rbp, rax
0x1800052ec  test    rax, rax
0x1800052ef  jnz     short loc_180005315
0x1800052f1  mov     rax, [rbx]
0x1800052f4  lea     edx, [rbp+1]
0x1800052f7  mov     rcx, rbx
0x1800052fa  mov     rax, [rax+38h]
0x1800052fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005303  mov     eax, 8007000Eh
0x180005308  add     rsp, 38h
0x18000530c  pop     r15
0x18000530e  pop     r14
0x180005310  pop     rdi
0x180005311  pop     rsi
0x180005312  pop     rbp
0x180005313  pop     rbx
0x180005314  retn
0x180005315  mov     rdi, [rsi+8]
0x180005319  mov     r15, rbp
0x18000531c  movsxd  rax, dword ptr [rsi+10h]
0x180005320  lea     rcx, [rdi+rax*8]
0x180005324  jmp     short loc_180005385
0x180005326  mov     rcx, [rdi]
0x180005329  test    rcx, rcx
0x18000532c  jz      short loc_180005375
0x18000532e  mov     rax, [rcx]
0x180005331  mov     rax, [rax+8]
0x180005335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000533a  mov     rax, [rdi]
0x18000533d  mov     [r15], rax
0x180005340  mov     r9, [rdi]
0x180005343  test    r9, r9
0x180005346  jz      short loc_18000536B
0x180005348  mov     rcx, [rsi+8]
0x18000534c  mov     edx, 1
0x180005351  movsxd  rax, dword ptr [rsi+10h]
0x180005355  lea     r8, [rcx+rax*8]
0x180005359  jmp     short loc_180005366
0x18000535b  cmp     [rcx], r9
0x18000535e  jz      short loc_18000536D
0x180005360  inc     edx
0x180005362  add     rcx, 8
0x180005366  cmp     rcx, r8
0x180005369  jb      short loc_18000535B
0x18000536b  xor     edx, edx
0x18000536d  mov     [r15+8], edx
0x180005371  add     r15, 10h
0x180005375  movsxd  rcx, dword ptr [rsi+10h]
0x180005379  add     rdi, 8
0x18000537d  mov     rax, [rsi+8]
0x180005381  lea     rcx, [rax+rcx*8]
0x180005385  cmp     rdi, rcx
0x180005388  jb      short loc_180005326
0x18000538a  xor     r9d, r9d
0x18000538d  mov     [rsp+68h+var_48], 2
0x180005395  mov     r8, r15
0x180005398  mov     rdx, rbp
0x18000539b  mov     rcx, rbx
0x18000539e  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x1800053a3  mov     r9, r14; void **
0x1800053a6  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x1800053ad  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800053b4  mov     rcx, rbx; void *
0x1800053b7  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800053bc  mov     edi, eax
0x1800053be  test    eax, eax
0x1800053c0  jns     short loc_1800053D6
0x1800053c2  mov     rdx, [rbx]
0x1800053c5  mov     rcx, rbx
0x1800053c8  mov     rax, [rdx+38h]
0x1800053cc  mov     edx, 1
0x1800053d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d6  mov     eax, edi
0x1800053d8  jmp     loc_180005308
```
