# ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Clone(IEnumConnectionPoints * *)

- ea: `0x180003fbc`
- end: `0x180004156`
- name: `?Clone@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003fa0`

## callees

- `0x1800011b8`
- `0x180003fbc`
- `0x180006a9c`
- `0x1800070ac`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Clone(
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
      *(_QWORD *)v5 = &ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`vftable';
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
      Interface = ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(
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
                          (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                          &GUID_b196b285_bab4_101a_b69c_00aa00341d07,
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
0x180003fbc  mov     [rsp+arg_0], rbx
0x180003fc1  mov     [rsp+arg_10], rbp
0x180003fc6  push    rsi
0x180003fc7  push    rdi
0x180003fc8  push    r12
0x180003fca  push    r14
0x180003fcc  push    r15
0x180003fce  sub     rsp, 30h
0x180003fd2  mov     dword ptr [rsp+58h+arg_8], 0
0x180003fda  mov     r12, rdx
0x180003fdd  mov     r15, rcx
0x180003fe0  mov     ebx, 80004003h
0x180003fe5  test    rdx, rdx
0x180003fe8  jz      loc_18000413D
0x180003fee  mov     ecx, 40h ; '@'; Size
0x180003ff3  mov     qword ptr [rdx], 0
0x180003ffa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003fff  mov     r14, rax
0x180004002  test    rax, rax
0x180004005  jz      loc_180004138
0x18000400b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004012  mov     qword ptr [rax+8], 0
0x18000401a  mov     qword ptr [rax+20h], 0
0x180004022  mov     qword ptr [rax+18h], 0
0x18000402a  mov     qword ptr [rax+10h], 0
0x180004032  mov     dword ptr [rax+28h], 0
0x180004039  mov     dword ptr [rax+30h], 0
0x180004040  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`vftable'
0x180004047  mov     [r14], rax
0x18000404a  mov     rax, [rcx]
0x18000404d  mov     rax, [rax+8]
0x180004051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004056  test    byte ptr [r15+28h], 2
0x18000405b  jz      short loc_18000407E
0x18000405d  mov     rax, [r15]
0x180004060  mov     rcx, r15
0x180004063  mov     rdi, r15
0x180004066  mov     rax, [rax+8]
0x18000406a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000406f  mov     rsi, [rsp+58h+arg_8]
0x180004074  mov     rbx, r15
0x180004077  mov     ebp, 1
0x18000407c  jmp     short loc_1800040A3
0x18000407e  mov     rbx, [r15+8]
0x180004082  mov     rsi, rbx
0x180004085  test    rbx, rbx
0x180004088  jz      short loc_180004099
0x18000408a  mov     rax, [rbx]
0x18000408d  mov     rcx, rbx
0x180004090  mov     rax, [rax+8]
0x180004094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004099  mov     rdi, [rsp+58h+arg_8]
0x18000409e  mov     ebp, 2
0x1800040a3  mov     r8, [r15+18h]
0x1800040a7  mov     r9, rbx
0x1800040aa  mov     rdx, [r15+10h]
0x1800040ae  mov     rcx, r14
0x1800040b1  mov     [rsp+58h+var_38], 0
0x1800040b9  call    ?Init@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@QEAAJPEAPEAUIConnectionPoint@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(IConnectionPoint * *,IConnectionPoint * *,IUnknown *,ATL::CComEnumFlags)
0x1800040be  mov     ebx, eax
0x1800040c0  test    bpl, 2
0x1800040c4  jz      short loc_1800040DD
0x1800040c6  and     ebp, 0FFFFFFFDh
0x1800040c9  test    rsi, rsi
0x1800040cc  jz      short loc_1800040DD
0x1800040ce  mov     rcx, [rsi]
0x1800040d1  mov     rax, [rcx+10h]
0x1800040d5  mov     rcx, rsi
0x1800040d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040dd  test    bpl, 1
0x1800040e1  jz      short loc_1800040F7
0x1800040e3  test    rdi, rdi
0x1800040e6  jz      short loc_1800040F7
0x1800040e8  mov     rax, [rdi]
0x1800040eb  mov     rcx, rdi
0x1800040ee  mov     rax, [rax+10h]
0x1800040f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f7  test    ebx, ebx
0x1800040f9  js      short loc_180004122
0x1800040fb  mov     rax, [r15+20h]
0x1800040ff  lea     r8, _GUID_b196b285_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x180004106  mov     r9, r12; void **
0x180004109  mov     [r14+20h], rax
0x18000410d  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x180004114  mov     rcx, r14; void *
0x180004117  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000411c  mov     ebx, eax
0x18000411e  test    eax, eax
0x180004120  jns     short loc_18000413D
0x180004122  mov     rax, [r14]
0x180004125  mov     edx, 1
0x18000412a  mov     rcx, r14
0x18000412d  mov     rax, [rax+38h]
0x180004131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004136  jmp     short loc_18000413D
0x180004138  mov     ebx, 8007000Eh
0x18000413d  mov     rbp, [rsp+58h+arg_10]
0x180004142  mov     eax, ebx
0x180004144  mov     rbx, [rsp+58h+arg_0]
0x180004149  add     rsp, 30h
0x18000414d  pop     r15
0x18000414f  pop     r14
0x180004151  pop     r12
0x180004153  pop     rdi
0x180004154  pop     rsi
0x180004155  retn
```
