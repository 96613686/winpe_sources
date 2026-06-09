# WiaEventClient::RegisterUnregisterForEventNotification(EventRegistrationInfo *)

- ea: `0x180054430`
- end: `0x1800547a0`
- name: `?RegisterUnregisterForEventNotification@WiaEventClient@@UEAAJPEAVEventRegistrationInfo@@@Z`
- size: `880`
- prototype: `int(WiaEventClient *__hidden this, struct EventRegistrationInfo *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x180011a94`
- `0x180027590`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033884`
- `0x180033cc0`
- `0x180053f54`
- `0x180054430`
- `0x180073b7c`
- `0x180078010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x1800545ba`
- `KERNEL32!lstrcmpW` at `0x1800545ba`

## string_xrefs

- `0x1800544e1`: `Removed registration:`
- `0x18005450b`: `Removed registration:`
- `0x1800546c6`: `Runtime event client Error: Registration already exists in the list`
- `0x1800546ee`: `Runtime event client Error: Registration already exists in the list`
- `0x180054541`: `Runtime event Error: Attempting to unregister when you have not first registered`
- `0x180054569`: `Runtime event Error: Attempting to unregister when you have not first registered`

## pseudocode

```c
__int64 __fastcall WiaEventClient::RegisterUnregisterForEventNotification(WiaEventClient *this, LPCWSTR *a2)
{
  struct EventRegistrationInfo *EqualEventRegistration; // rax
  EventRegistrationInfo *v5; // rsi
  _QWORD *v6; // rcx
  unsigned int v7; // edi
  _QWORD *v8; // rdx
  char *v9; // rbx
  void *v10; // rdx
  void **lpMem; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  char *v14; // rbx
  void *v15; // rdx
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  LPCWSTR v19; // rdi
  __int64 v20; // rcx
  __int64 USDWrapperFromDeviceList; // rdi
  _QWORD *v22; // rax
  __int64 v23; // rcx
  char *v24; // rbx
  void *v25; // rdx
  void **v26; // rax
  void *v27; // rdx
  __int64 v28; // rcx
  char *v29; // rbx
  void *v30; // rdx
  void **v31; // rax
  void *v32; // rdx
  __int64 v33; // rcx
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  _QWORD v40[38]; // [rsp+30h] [rbp-158h] BYREF

  if ( !a2 )
  {
    v34 = (char *)WiaTrace_TraceLogWithSubComp(1, "Runtime event Error: Cannot handle a NULL registration");
    WriteDbgTraceWarningWI("WiaEventClient::RegisterUnregisterForEventNotification", v34);
    WiaTrcLib::Free((WiaTrcLib *)v34, v35);
    v36 = (void **)WiaTrace_TraceWithSubComp(1, "Runtime event Error: Cannot handle a NULL registration");
    WiaTrace_ProcessTrace_Ex(v38, v37, (void *)"WiaEventClient::RegisterUnregisterForEventNotification", 2, v36);
    return (unsigned int)-2147467261;
  }
  EqualEventRegistration = WiaEventClient::FindEqualEventRegistration(this, (struct EventRegistrationInfo *)a2);
  v5 = EqualEventRegistration;
  if ( (*((_BYTE *)a2 + 12) & 2) != 0 )
  {
    if ( EqualEventRegistration )
    {
      v6 = (_QWORD *)*((_QWORD *)this + 4);
      v7 = 0;
      v8 = 0;
      while ( v6 )
      {
        if ( (struct EventRegistrationInfo *)v6[1] == EqualEventRegistration )
        {
          if ( v6 == *((_QWORD **)this + 5) )
            *((_QWORD *)this + 5) = v8;
          if ( v6 == *((_QWORD **)this + 4) )
            *((_QWORD *)this + 4) = *v6;
          if ( v8 )
            *v8 = *v6;
          operator delete(v6, 0x10u);
          --*((_DWORD *)this + 12);
          break;
        }
        v8 = v6;
        v6 = (_QWORD *)*v6;
      }
      (*(void (__fastcall **)(EventRegistrationInfo *, _QWORD *))(*(_QWORD *)v5 + 16LL))(v5, v8);
      v9 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Removed registration:");
      WriteDbgTraceInfoWI("WiaEventClient::RegisterUnregisterForEventNotification", v9);
      WiaTrcLib::Free((WiaTrcLib *)v9, v10);
      lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Removed registration:");
      WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"WiaEventClient::RegisterUnregisterForEventNotification", 4, lpMem);
      EventRegistrationInfo::Dump(v5);
    }
    else
    {
      v14 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "Runtime event Error: Attempting to unregister when you have not first registered");
      WriteDbgTraceWarningWI("WiaEventClient::RegisterUnregisterForEventNotification", v14);
      WiaTrcLib::Free((WiaTrcLib *)v14, v15);
      v16 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "Runtime event Error: Attempting to unregister when you have not first registered");
      WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"WiaEventClient::RegisterUnregisterForEventNotification", 2, v16);
      v7 = -2147024809;
    }
    if ( v5 )
      goto LABEL_33;
  }
  else
  {
    if ( EqualEventRegistration )
    {
      v7 = 1;
      v29 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "Runtime event client Error: Registration already exists in the list");
      WriteDbgTraceWarningWI("WiaEventClient::RegisterUnregisterForEventNotification", v29);
      WiaTrcLib::Free((WiaTrcLib *)v29, v30);
      v31 = (void **)WiaTrace_TraceWithSubComp(1, "Runtime event client Error: Registration already exists in the list");
      WiaTrace_ProcessTrace_Ex(v33, v32, (void *)"WiaEventClient::RegisterUnregisterForEventNotification", 2, v31);
LABEL_33:
      (*(void (__fastcall **)(EventRegistrationInfo *))(*(_QWORD *)v5 + 16LL))(v5);
      return v7;
    }
    v19 = a2[4];
    if ( v19 && lstrcmpW(a2[4], L"*") )
    {
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v40, v19);
      USDWrapperFromDeviceList = GetUSDWrapperFromDeviceList(v20, v40);
      v40[0] = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(v40);
      v40[34] = 0;
      if ( !USDWrapperFromDeviceList )
        return (unsigned int)-2147024809;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)USDWrapperFromDeviceList + 16LL))(USDWrapperFromDeviceList);
    }
    v22 = operator new(0x10u);
    if ( v22 )
    {
      *v22 = 0;
      v22[1] = a2;
      v23 = *((_QWORD *)this + 4);
      if ( v23 )
        *v22 = v23;
      else
        *((_QWORD *)this + 5) = v22;
      *((_QWORD *)this + 4) = v22;
      ++*((_DWORD *)this + 12);
    }
    (*((void (__fastcall **)(LPCWSTR *))*a2 + 1))(a2);
    v24 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Added new registration:");
    WriteDbgTraceInfoWI("WiaEventClient::RegisterUnregisterForEventNotification", v24);
    WiaTrcLib::Free((WiaTrcLib *)v24, v25);
    v26 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Added new registration:");
    WiaTrace_ProcessTrace_Ex(v28, v27, (void *)"WiaEventClient::RegisterUnregisterForEventNotification", 4, v26);
    EventRegistrationInfo::Dump((EventRegistrationInfo *)a2);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180054430  mov     [rsp+arg_10], rbx
0x180054435  mov     [rsp+arg_18], rbp
0x18005443a  push    rsi
0x18005443b  push    rdi
0x18005443c  push    r14
0x18005443e  sub     rsp, 170h
0x180054445  mov     rax, cs:__security_cookie
0x18005444c  xor     rax, rsp
0x18005444f  mov     [rsp+188h+var_28], rax
0x180054457  mov     r14, rdx
0x18005445a  mov     rbx, rcx
0x18005445d  test    rdx, rdx
0x180054460  jz      loc_180054721
0x180054466  call    ?FindEqualEventRegistration@WiaEventClient@@IEAAPEAVEventRegistrationInfo@@PEAV2@@Z; WiaEventClient::FindEqualEventRegistration(EventRegistrationInfo *)
0x18005446b  mov     ebp, 2
0x180054470  mov     rsi, rax
0x180054473  test    [r14+0Ch], bpl
0x180054477  jz      loc_18005459E
0x18005447d  test    rax, rax
0x180054480  jz      loc_18005453C
0x180054486  mov     rcx, [rbx+20h]
0x18005448a  xor     edi, edi
0x18005448c  xor     edx, edx
0x18005448e  jmp     short loc_18005449C
0x180054490  cmp     [rcx+8], rsi
0x180054494  jz      short loc_1800544A3
0x180054496  mov     rdx, rcx
0x180054499  mov     rcx, [rcx]; void *
0x18005449c  test    rcx, rcx
0x18005449f  jnz     short loc_180054490
0x1800544a1  jmp     short loc_1800544D2
0x1800544a3  cmp     rcx, [rbx+28h]
0x1800544a7  jnz     short loc_1800544AD
0x1800544a9  mov     [rbx+28h], rdx
0x1800544ad  cmp     rcx, [rbx+20h]
0x1800544b1  jnz     short loc_1800544BA
0x1800544b3  mov     rax, [rcx]
0x1800544b6  mov     [rbx+20h], rax
0x1800544ba  test    rdx, rdx
0x1800544bd  jz      short loc_1800544C5
0x1800544bf  mov     rax, [rcx]
0x1800544c2  mov     [rdx], rax
0x1800544c5  mov     edx, 10h; unsigned __int64
0x1800544ca  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800544cf  dec     dword ptr [rbx+30h]
0x1800544d2  mov     rax, [rsi]
0x1800544d5  mov     rcx, rsi
0x1800544d8  mov     rax, [rax+10h]
0x1800544dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800544e1  lea     r8, aRemovedRegistr; "Removed registration:"
0x1800544e8  xor     edx, edx
0x1800544ea  mov     ecx, ebp
0x1800544ec  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800544f1  mov     rdx, rax; char *
0x1800544f4  lea     rcx, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x1800544fb  mov     rbx, rax
0x1800544fe  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180054503  mov     rcx, rbx; this
0x180054506  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005450b  lea     r8, aRemovedRegistr; "Removed registration:"
0x180054512  xor     edx, edx
0x180054514  mov     ecx, ebp
0x180054516  call    WiaTrace_TraceWithSubCompTraceLevel
0x18005451b  mov     r9d, 4; int
0x180054521  mov     [rsp+188h+lpMem], rax; lpMem
0x180054526  lea     r8, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x18005452d  call    WiaTrace_ProcessTrace_Ex
0x180054532  mov     rcx, rsi; this
0x180054535  call    ?Dump@EventRegistrationInfo@@QEAAXXZ; EventRegistrationInfo::Dump(void)
0x18005453a  jmp     short loc_180054590
0x18005453c  mov     edi, 1
0x180054541  lea     rdx, aRuntimeEventEr_4; "Runtime event Error: Attempting to unre"...
0x180054548  mov     ecx, edi
0x18005454a  call    WiaTrace_TraceLogWithSubComp
0x18005454f  mov     rdx, rax; char *
0x180054552  lea     rcx, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x180054559  mov     rbx, rax
0x18005455c  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180054561  mov     rcx, rbx; this
0x180054564  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180054569  lea     rdx, aRuntimeEventEr_4; "Runtime event Error: Attempting to unre"...
0x180054570  mov     ecx, edi
0x180054572  call    WiaTrace_TraceWithSubComp
0x180054577  mov     r9d, ebp; int
0x18005457a  mov     [rsp+188h+lpMem], rax; lpMem
0x18005457f  lea     r8, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x180054586  call    WiaTrace_ProcessTrace_Ex
0x18005458b  mov     edi, 80070057h
0x180054590  test    rsi, rsi
0x180054593  jz      loc_180054776
0x180054599  jmp     loc_180054710
0x18005459e  test    rsi, rsi
0x1800545a1  jnz     loc_1800546C1
0x1800545a7  mov     rdi, [r14+20h]
0x1800545ab  test    rdi, rdi
0x1800545ae  jz      short loc_180054610
0x1800545b0  lea     rdx, asc_180086378; "*"
0x1800545b7  mov     rcx, rdi; lpString1
0x1800545ba  call    cs:__imp_lstrcmpW
0x1800545c0  test    eax, eax
0x1800545c2  jz      short loc_180054610
0x1800545c4  mov     rdx, rdi
0x1800545c7  lea     rcx, [rsp+188h+var_158]
0x1800545cc  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800545d1  lea     rdx, [rsp+188h+var_158]
0x1800545d6  call    ?GetUSDWrapperFromDeviceList@@YAPEAVUSDWrapper@@JAEBV?$CSimpleStringBase@G@@@Z; GetUSDWrapperFromDeviceList(long,CSimpleStringBase<ushort> const &)
0x1800545db  mov     rdi, rax
0x1800545de  lea     rcx, [rsp+188h+var_158]
0x1800545e3  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800545ea  mov     [rsp+188h+var_158], rax
0x1800545ef  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800545f4  mov     [rsp+188h+var_48], rsi
0x1800545fc  test    rdi, rdi
0x1800545ff  jz      short loc_180054639
0x180054601  mov     rcx, [rdi]
0x180054604  mov     rax, [rcx+10h]
0x180054608  mov     rcx, rdi
0x18005460b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054610  mov     ecx, 10h; Size
0x180054615  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005461a  test    rax, rax
0x18005461d  jz      short loc_180054652
0x18005461f  mov     qword ptr [rax], 0
0x180054626  mov     [rax+8], r14
0x18005462a  mov     rcx, [rbx+20h]
0x18005462e  test    rcx, rcx
0x180054631  jnz     short loc_180054643
0x180054633  mov     [rbx+28h], rax
0x180054637  jmp     short loc_180054646
0x180054639  mov     edi, 80070057h
0x18005463e  jmp     loc_180054776
0x180054643  mov     [rax], rcx
0x180054646  mov     edi, 1
0x18005464b  mov     [rbx+20h], rax
0x18005464f  add     [rbx+30h], edi
0x180054652  mov     rax, [r14]
0x180054655  mov     rcx, r14
0x180054658  mov     rax, [rax+8]
0x18005465c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054661  lea     r8, aAddedNewRegist; "Added new registration:"
0x180054668  xor     edx, edx
0x18005466a  mov     ecx, ebp
0x18005466c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180054671  mov     rdx, rax; char *
0x180054674  lea     rcx, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x18005467b  mov     rbx, rax
0x18005467e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180054683  mov     rcx, rbx; this
0x180054686  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005468b  lea     r8, aAddedNewRegist; "Added new registration:"
0x180054692  xor     edx, edx
0x180054694  mov     ecx, ebp
0x180054696  call    WiaTrace_TraceWithSubCompTraceLevel
0x18005469b  mov     r9d, 4; int
0x1800546a1  mov     [rsp+188h+lpMem], rax; lpMem
0x1800546a6  lea     r8, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x1800546ad  call    WiaTrace_ProcessTrace_Ex
0x1800546b2  mov     rcx, r14; this
0x1800546b5  call    ?Dump@EventRegistrationInfo@@QEAAXXZ; EventRegistrationInfo::Dump(void)
0x1800546ba  xor     edi, edi
0x1800546bc  jmp     loc_180054776
0x1800546c1  mov     edi, 1
0x1800546c6  lea     rdx, aRuntimeEventCl_1; "Runtime event client Error: Registratio"...
0x1800546cd  mov     ecx, edi
0x1800546cf  call    WiaTrace_TraceLogWithSubComp
0x1800546d4  mov     rdx, rax; char *
0x1800546d7  lea     rcx, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x1800546de  mov     rbx, rax
0x1800546e1  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800546e6  mov     rcx, rbx; this
0x1800546e9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800546ee  lea     rdx, aRuntimeEventCl_1; "Runtime event client Error: Registratio"...
0x1800546f5  mov     ecx, edi
0x1800546f7  call    WiaTrace_TraceWithSubComp
0x1800546fc  mov     r9d, ebp; int
0x1800546ff  mov     [rsp+188h+lpMem], rax; lpMem
0x180054704  lea     r8, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x18005470b  call    WiaTrace_ProcessTrace_Ex
0x180054710  mov     rax, [rsi]
0x180054713  mov     rcx, rsi
0x180054716  mov     rax, [rax+10h]
0x18005471a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005471f  jmp     short loc_180054776
0x180054721  mov     edi, 1
0x180054726  lea     rdx, aRuntimeEventEr_12; "Runtime event Error: Cannot handle a NU"...
0x18005472d  mov     ecx, edi
0x18005472f  call    WiaTrace_TraceLogWithSubComp
0x180054734  mov     rdx, rax; char *
0x180054737  lea     rcx, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x18005473e  mov     rbx, rax
0x180054741  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180054746  mov     rcx, rbx; this
0x180054749  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18005474e  lea     rdx, aRuntimeEventEr_12; "Runtime event Error: Cannot handle a NU"...
0x180054755  mov     ecx, edi
0x180054757  call    WiaTrace_TraceWithSubComp
0x18005475c  lea     r9d, [rdi+1]; int
0x180054760  mov     [rsp+188h+lpMem], rax; lpMem
0x180054765  lea     r8, aWiaeventclient_6; "WiaEventClient::RegisterUnregisterForEv"...
0x18005476c  call    WiaTrace_ProcessTrace_Ex
0x180054771  mov     edi, 80004003h
0x180054776  mov     eax, edi
0x180054778  mov     rcx, [rsp+188h+var_28]
0x180054780  xor     rcx, rsp; StackCookie
0x180054783  call    __security_check_cookie
0x180054788  lea     r11, [rsp+188h+var_18]
0x180054790  mov     rbx, [r11+30h]
0x180054794  mov     rbp, [r11+38h]
0x180054798  mov     rsp, r11
0x18005479b  pop     r14
0x18005479d  pop     rdi
0x18005479e  pop     rsi
0x18005479f  retn
```
