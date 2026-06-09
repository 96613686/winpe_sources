# ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Clone(IEnumConnections * *)

- ea: `0x18000415c`
- end: `0x1800042f6`
- name: `?Clone@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnections@@@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003fb0`

## callees

- `0x1800011b8`
- `0x18000415c`
- `0x180006bb0`
- `0x1800070ac`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Clone(
        __int64 a1,
        char **a2)
{
  int Interface; // ebx
  char *v5; // rax
  char *v6; // r14
  struct ATL::CAtlModule *v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // rbx
  char v11; // bp
  __int64 v13; // [rsp+68h] [rbp+10h]

  LODWORD(v13) = 0;
  Interface = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    v5 = (char *)operator new(0x40u);
    v6 = v5;
    if ( v5 )
    {
      v7 = ATL::_pAtlModule;
      *((_QWORD *)v5 + 1) = 0;
      *((_QWORD *)v5 + 4) = 0;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)v5 + 2) = 0;
      *((_DWORD *)v5 + 10) = 0;
      *((_DWORD *)v5 + 12) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
      {
        v8 = a1;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
        v9 = v13;
        LODWORD(v10) = a1;
        v11 = 1;
      }
      else
      {
        v10 = *(_QWORD *)(a1 + 8);
        v9 = v10;
        if ( v10 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*(_QWORD *)(a1 + 8));
        v8 = v13;
        v11 = 2;
      }
      Interface = ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(
                    (_DWORD)v6,
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 24),
                    v10,
                    0);
      if ( (v11 & 2) != 0 )
      {
        v11 &= ~2u;
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      if ( (v11 & 1) != 0 && v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      if ( Interface < 0
        || (*((_QWORD *)v6 + 4) = *(_QWORD *)(a1 + 32),
            Interface = ATL::CComObjectRootBase::InternalQueryInterface(
                          v6,
                          (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                          &GUID_b196b287_bab4_101a_b69c_00aa00341d07,
                          a2),
            Interface < 0) )
      {
        (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v6 + 56LL))(v6, 1);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000415c  mov     [rsp+arg_0], rbx
0x180004161  mov     [rsp+arg_10], rbp
0x180004166  push    rsi
0x180004167  push    rdi
0x180004168  push    r12
0x18000416a  push    r14
0x18000416c  push    r15
0x18000416e  sub     rsp, 30h
0x180004172  mov     dword ptr [rsp+58h+arg_8], 0
0x18000417a  mov     r12, rdx
0x18000417d  mov     r15, rcx
0x180004180  mov     ebx, 80004003h
0x180004185  test    rdx, rdx
0x180004188  jz      loc_1800042DD
0x18000418e  mov     ecx, 40h ; '@'; Size
0x180004193  mov     qword ptr [rdx], 0
0x18000419a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000419f  mov     r14, rax
0x1800041a2  test    rax, rax
0x1800041a5  jz      loc_1800042D8
0x1800041ab  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800041b2  mov     qword ptr [rax+8], 0
0x1800041ba  mov     qword ptr [rax+20h], 0
0x1800041c2  mov     qword ptr [rax+18h], 0
0x1800041ca  mov     qword ptr [rax+10h], 0
0x1800041d2  mov     dword ptr [rax+28h], 0
0x1800041d9  mov     dword ptr [rax+30h], 0
0x1800041e0  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::`vftable'
0x1800041e7  mov     [r14], rax
0x1800041ea  mov     rax, [rcx]
0x1800041ed  mov     rax, [rax+8]
0x1800041f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041f6  test    byte ptr [r15+28h], 2
0x1800041fb  jz      short loc_18000421E
0x1800041fd  mov     rax, [r15]
0x180004200  mov     rcx, r15
0x180004203  mov     rdi, r15
0x180004206  mov     rax, [rax+8]
0x18000420a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000420f  mov     rsi, [rsp+58h+arg_8]
0x180004214  mov     rbx, r15
0x180004217  mov     ebp, 1
0x18000421c  jmp     short loc_180004243
0x18000421e  mov     rbx, [r15+8]
0x180004222  mov     rsi, rbx
0x180004225  test    rbx, rbx
0x180004228  jz      short loc_180004239
0x18000422a  mov     rax, [rbx]
0x18000422d  mov     rcx, rbx
0x180004230  mov     rax, [rax+8]
0x180004234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004239  mov     rdi, [rsp+58h+arg_8]
0x18000423e  mov     ebp, 2
0x180004243  mov     r8, [r15+18h]
0x180004247  mov     r9, rbx
0x18000424a  mov     rdx, [r15+10h]
0x18000424e  mov     rcx, r14
0x180004251  mov     [rsp+58h+var_38], 0
0x180004259  call    ?Init@?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAAJPEAUtagCONNECTDATA@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::Init(tagCONNECTDATA *,tagCONNECTDATA *,IUnknown *,ATL::CComEnumFlags)
0x18000425e  mov     ebx, eax
0x180004260  test    bpl, 2
0x180004264  jz      short loc_18000427D
0x180004266  and     ebp, 0FFFFFFFDh
0x180004269  test    rsi, rsi
0x18000426c  jz      short loc_18000427D
0x18000426e  mov     rcx, [rsi]
0x180004271  mov     rax, [rcx+10h]
0x180004275  mov     rcx, rsi
0x180004278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000427d  test    bpl, 1
0x180004281  jz      short loc_180004297
0x180004283  test    rdi, rdi
0x180004286  jz      short loc_180004297
0x180004288  mov     rax, [rdi]
0x18000428b  mov     rcx, rdi
0x18000428e  mov     rax, [rax+10h]
0x180004292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004297  test    ebx, ebx
0x180004299  js      short loc_1800042C2
0x18000429b  mov     rax, [r15+20h]
0x18000429f  lea     r8, _GUID_b196b287_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x1800042a6  mov     r9, r12; void **
0x1800042a9  mov     [r14+20h], rax
0x1800042ad  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800042b4  mov     rcx, r14; void *
0x1800042b7  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800042bc  mov     ebx, eax
0x1800042be  test    eax, eax
0x1800042c0  jns     short loc_1800042DD
0x1800042c2  mov     rax, [r14]
0x1800042c5  mov     edx, 1
0x1800042ca  mov     rcx, r14
0x1800042cd  mov     rax, [rax+38h]
0x1800042d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042d6  jmp     short loc_1800042DD
0x1800042d8  mov     ebx, 8007000Eh
0x1800042dd  mov     rbp, [rsp+58h+arg_10]
0x1800042e2  mov     eax, ebx
0x1800042e4  mov     rbx, [rsp+58h+arg_0]
0x1800042e9  add     rsp, 30h
0x1800042ed  pop     r15
0x1800042ef  pop     r14
0x1800042f1  pop     r12
0x1800042f3  pop     rdi
0x1800042f4  pop     rsi
0x1800042f5  retn
```
