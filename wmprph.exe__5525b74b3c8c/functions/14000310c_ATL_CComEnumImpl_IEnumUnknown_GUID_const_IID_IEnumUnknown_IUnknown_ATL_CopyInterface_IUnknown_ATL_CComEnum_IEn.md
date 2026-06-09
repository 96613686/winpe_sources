# ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Clone(IEnumUnknown * *)

- ea: `0x14000310c`
- end: `0x1400032b2`
- name: `?Clone@?$CComEnumImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJPEAPEAUIEnumUnknown@@@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140003100`

## callees

- `0x140001008`
- `0x140001014`
- `0x140002014`
- `0x14000310c`
- `0x140005808`
- `0x1400059b4`
- `0x14000c818`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Clone(
        __int64 a1,
        char **a2)
{
  int Interface; // ebx
  _QWORD *v5; // rax
  _QWORD *v6; // r14
  __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rbx
  char v10; // bp
  CExeModule *v11; // rcx
  __int64 v13; // [rsp+68h] [rbp+10h]

  LODWORD(v13) = 0;
  Interface = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    v5 = operator new(0x40u);
    v6 = v5;
    if ( v5 )
    {
      v5[1] = 0;
      v5[4] = 0;
      v5[3] = 0;
      v5[2] = 0;
      *((_DWORD *)v5 + 10) = 0;
      *((_DWORD *)v5 + 12) = 0;
      *v5 = &ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::`vftable';
      _InterlockedIncrement(&dword_1400153D8);
      if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
      {
        v7 = a1;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
        v8 = v13;
        LODWORD(v9) = a1;
        v10 = 1;
      }
      else
      {
        v9 = *(_QWORD *)(a1 + 8);
        v8 = v9;
        if ( v9 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*(_QWORD *)(a1 + 8));
        v7 = v13;
        v10 = 2;
      }
      Interface = ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Init(
                    (_DWORD)v6,
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 24),
                    v9,
                    0);
      if ( (v10 & 2) != 0 )
      {
        v10 &= ~2u;
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      if ( (v10 & 1) != 0 && v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      if ( Interface < 0
        || (v6[4] = *(_QWORD *)(a1 + 32),
            Interface = ATL::CComObjectRootBase::InternalQueryInterface(
                          (char *)v6,
                          (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                          &IID_IEnumUnknown,
                          a2),
            Interface < 0) )
      {
        *((_DWORD *)v6 + 12) = 1;
        *v6 = &ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::`vftable';
        CExeModule::Unlock(v11);
        ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>(v6);
        operator delete(v6);
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
0x14000310c  mov     [rsp+arg_0], rbx
0x140003111  mov     [rsp+arg_10], rbp
0x140003116  push    rsi
0x140003117  push    rdi
0x140003118  push    r12
0x14000311a  push    r14
0x14000311c  push    r15
0x14000311e  sub     rsp, 30h
0x140003122  mov     dword ptr [rsp+58h+arg_8], 0
0x14000312a  mov     r12, rdx
0x14000312d  mov     r15, rcx
0x140003130  mov     ebx, 80004003h
0x140003135  test    rdx, rdx
0x140003138  jz      loc_140003299
0x14000313e  mov     ecx, 40h ; '@'; Size
0x140003143  mov     qword ptr [rdx], 0
0x14000314a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000314f  mov     r14, rax
0x140003152  test    rax, rax
0x140003155  jz      loc_140003294
0x14000315b  mov     qword ptr [rax+8], 0
0x140003163  mov     qword ptr [rax+20h], 0
0x14000316b  mov     qword ptr [rax+18h], 0
0x140003173  mov     qword ptr [rax+10h], 0
0x14000317b  mov     dword ptr [rax+28h], 0
0x140003182  mov     dword ptr [rax+30h], 0
0x140003189  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::`vftable'
0x140003190  mov     [r14], rax
0x140003193  lock inc cs:dword_1400153D8
0x14000319a  test    byte ptr [r15+28h], 1
0x14000319f  jz      short loc_1400031C2
0x1400031a1  mov     rax, [r15]
0x1400031a4  mov     rcx, r15
0x1400031a7  mov     rdi, r15
0x1400031aa  mov     rax, [rax+8]
0x1400031ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031b3  mov     rsi, [rsp+58h+arg_8]
0x1400031b8  mov     rbx, r15
0x1400031bb  mov     ebp, 1
0x1400031c0  jmp     short loc_1400031E7
0x1400031c2  mov     rbx, [r15+8]
0x1400031c6  mov     rsi, rbx
0x1400031c9  test    rbx, rbx
0x1400031cc  jz      short loc_1400031DD
0x1400031ce  mov     rax, [rbx]
0x1400031d1  mov     rcx, rbx
0x1400031d4  mov     rax, [rax+8]
0x1400031d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031dd  mov     rdi, [rsp+58h+arg_8]
0x1400031e2  mov     ebp, 2
0x1400031e7  mov     r8, [r15+18h]
0x1400031eb  mov     r9, rbx
0x1400031ee  mov     rdx, [r15+10h]
0x1400031f2  mov     rcx, r14
0x1400031f5  mov     [rsp+58h+var_38], 0
0x1400031fd  call    ?Init@?$CComEnumImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAAJPEAPEAUIUnknown@@0PEAU3@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::Init(IUnknown * *,IUnknown * *,IUnknown *,ATL::CComEnumFlags)
0x140003202  mov     ebx, eax
0x140003204  test    bpl, 2
0x140003208  jz      short loc_140003221
0x14000320a  and     ebp, 0FFFFFFFDh
0x14000320d  test    rsi, rsi
0x140003210  jz      short loc_140003221
0x140003212  mov     rcx, [rsi]
0x140003215  mov     rax, [rcx+10h]
0x140003219  mov     rcx, rsi
0x14000321c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003221  test    bpl, 1
0x140003225  jz      short loc_14000323B
0x140003227  test    rdi, rdi
0x14000322a  jz      short loc_14000323B
0x14000322c  mov     rax, [rdi]
0x14000322f  mov     rcx, rdi
0x140003232  mov     rax, [rax+10h]
0x140003236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000323b  test    ebx, ebx
0x14000323d  js      short loc_140003266
0x14000323f  mov     rax, [r15+20h]
0x140003243  lea     r8, IID_IEnumUnknown; struct _GUID *
0x14000324a  mov     r9, r12; void **
0x14000324d  mov     [r14+20h], rax
0x140003251  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x140003258  mov     rcx, r14; void *
0x14000325b  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x140003260  mov     ebx, eax
0x140003262  test    eax, eax
0x140003264  jns     short loc_140003299
0x140003266  lea     rax, ??_7?$CComObject@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::`vftable'
0x14000326d  mov     dword ptr [r14+30h], 1
0x140003275  mov     [r14], rax
0x140003278  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x14000327d  mov     rcx, r14
0x140003280  call    ??1?$CComEnumImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@V?$CComEnum@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$_CopyInterface@UIUnknown@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAA@XZ; ATL::CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComEnum<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,ATL::_CopyInterface<IUnknown>,ATL::CComSingleThreadModel>>(void)
0x140003285  mov     edx, 40h ; '@'; unsigned __int64
0x14000328a  mov     rcx, r14; void *
0x14000328d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003292  jmp     short loc_140003299
0x140003294  mov     ebx, 8007000Eh
0x140003299  mov     rbp, [rsp+58h+arg_10]
0x14000329e  mov     eax, ebx
0x1400032a0  mov     rbx, [rsp+58h+arg_0]
0x1400032a5  add     rsp, 30h
0x1400032a9  pop     r15
0x1400032ab  pop     r14
0x1400032ad  pop     r12
0x1400032af  pop     rdi
0x1400032b0  pop     rsi
0x1400032b1  retn
```
