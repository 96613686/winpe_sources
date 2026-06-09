# IASAttributesCollection::Add(_ATTRIBUTEID,tagVARIANT,IIASItem * *)

- ea: `0x180031200`
- end: `0x18003155f`
- name: `?Add@IASAttributesCollection@@UEAAJW4_ATTRIBUTEID@@UtagVARIANT@@PEAPEAUIIASItem@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(IASAttributesCollection *__hidden this, enum _ATTRIBUTEID, struct tagVARIANT *__struct_ptr, struct IIASItem **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180024cac`
- `0x18002844c`
- `0x180029ef4`
- `0x18002cd00`
- `0x18002f14c`
- `0x180031200`
- `0x1800317ec`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x180031287`: `m_pDict->CreateAttribute(%d) failed with 0x%x`
- `0x18003150b`: `IASSDOCreateItem failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IASAttributesCollection::Add(
        IASAttributesCollection *this,
        __int64 a2,
        struct tagVARIANT *a3,
        struct IIASItem **a4)
{
  enum _ATTRIBUTEID v6; // esi
  int v9; // ebx
  int v10; // edx
  _QWORD v11[2]; // [rsp+30h] [rbp-38h] BYREF
  struct tagVARIANT v12; // [rsp+40h] [rbp-28h] BYREF
  struct ISdo *v13; // [rsp+B8h] [rbp+50h] BYREF

  v6 = (int)a2;
  if ( !a4 )
    return 2147500035LL;
  v11[0] = 0;
  v13 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *))(**((_QWORD **)this + 6) + 80LL))(
         *((_QWORD *)this + 6),
         a2,
         v11);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("m_pDict->CreateAttribute(%d) failed with 0x%x");
      WPP_SF_sdD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids);
    }
    goto LABEL_39;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**((_QWORD **)this + 3) + 64LL))(
         *((_QWORD *)this + 3),
         0,
         v11);
  if ( v9 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct ISdo **))v11[0])(v11[0], &IID_ISdo, &v13);
    if ( v9 >= 0 )
    {
      v12 = *a3;
      v9 = IASAttributesCollection::ValidateAttribute(this, v6, &v12, v13);
      if ( v9 >= 0 )
      {
        v12 = *a3;
        v9 = PutSdoProperty(v13, 0x40Cu, &v12);
        if ( v9 >= 0 )
        {
          v9 = ((__int64 (__fastcall *)(struct ISdo *))v13->lpVtbl->Apply)(v13);
          if ( v9 >= 0 )
          {
            v9 = IASSDOCreateItem(
                   *((_DWORD *)this + 4),
                   v13,
                   *((struct ISdo **)this + 4),
                   *((struct ISdoMachine **)this + 5),
                   *((struct ISdoDictionaryOld **)this + 6),
                   (__int64)a4);
            if ( v9 >= 0
              || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_39;
            }
            WppDbgPrint("IASSDOCreateItem failed with 0x%x");
            v10 = 34;
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_39;
            }
            WppDbgPrint("pSdo->Apply hr=0x%X");
            v10 = 33;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          {
            goto LABEL_39;
          }
          WppDbgPrint("PutSdoProperty(PROPERTY_ATTRIBUTE_VALUE) hr=0x%X");
          v10 = 32;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          goto LABEL_39;
        }
        WppDbgPrint("ValidateAttribute returned 0x%x");
        v10 = 31;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        goto LABEL_39;
      }
      WppDbgPrint("IASAttributesCollection::Add -- QI(ISdo) failed with 0x%x");
      v10 = 30;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_39;
    }
    WppDbgPrint("AttributesCollection::Add failed with 0x%x");
    v10 = 29;
  }
  WPP_SF_sd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v10,
    (unsigned int)WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids,
    (unsigned int)"NPSSDO",
    v9);
LABEL_39:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180031200  push    rbp
0x180031202  push    rbx
0x180031203  push    rsi
0x180031204  push    rdi
0x180031205  push    r14
0x180031207  push    r15
0x180031209  mov     rbp, rsp
0x18003120c  sub     rsp, 68h
0x180031210  mov     r15, r9
0x180031213  mov     r14, r8
0x180031216  mov     esi, edx
0x180031218  mov     rdi, rcx
0x18003121b  test    r9, r9
0x18003121e  jnz     short loc_18003122A
0x180031220  mov     eax, 80004003h
0x180031225  jmp     loc_180031552
0x18003122a  mov     [rbp+var_38], 0
0x180031232  mov     [rbp+arg_18], 0
0x18003123a  mov     rcx, [rcx+30h]
0x18003123e  mov     rax, [rcx]
0x180031241  lea     r8, [rbp+var_38]
0x180031245  mov     rax, [rax+50h]
0x180031249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003124e  mov     ebx, eax
0x180031250  test    eax, eax
0x180031252  jns     short loc_1800312BC
0x180031254  lea     rax, WPP_GLOBAL_Control
0x18003125b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031262  cmp     rcx, rax
0x180031265  jz      loc_18003153E
0x18003126b  cmp     byte ptr [rcx+19h], 2
0x18003126f  jb      loc_18003153E
0x180031275  test    dword ptr [rcx+1Ch], 400h
0x18003127c  jz      loc_18003153E
0x180031282  mov     r8d, ebx
0x180031285  mov     edx, esi
0x180031287  lea     rcx, aMPdictCreateat; "m_pDict->CreateAttribute(%d) failed wit"...
0x18003128e  call    WppDbgPrint
0x180031293  mov     edx, 1Ch
0x180031298  mov     dword ptr [rsp+68h+var_40], ebx
0x18003129c  mov     dword ptr [rsp+68h+var_48], esi
0x1800312a0  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x1800312a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312ae  mov     rcx, [rcx+10h]
0x1800312b2  call    WPP_SF_sdD
0x1800312b7  jmp     loc_18003153E
0x1800312bc  mov     rcx, [rdi+18h]
0x1800312c0  mov     rax, [rcx]
0x1800312c3  lea     r8, [rbp+var_38]
0x1800312c7  xor     edx, edx
0x1800312c9  mov     rax, [rax+40h]
0x1800312cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800312d2  mov     ebx, eax
0x1800312d4  test    eax, eax
0x1800312d6  jns     short loc_18003131E
0x1800312d8  lea     rax, WPP_GLOBAL_Control
0x1800312df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312e6  cmp     rcx, rax
0x1800312e9  jz      loc_18003153E
0x1800312ef  cmp     byte ptr [rcx+19h], 2
0x1800312f3  jb      loc_18003153E
0x1800312f9  test    dword ptr [rcx+1Ch], 400h
0x180031300  jz      loc_18003153E
0x180031306  mov     edx, ebx
0x180031308  lea     rcx, aAttributescoll; "AttributesCollection::Add failed with 0"...
0x18003130f  call    WppDbgPrint
0x180031314  mov     edx, 1Dh
0x180031319  jmp     loc_18003151C
0x18003131e  mov     rcx, [rbp+var_38]
0x180031322  mov     rax, [rcx]
0x180031325  lea     r8, [rbp+arg_18]
0x180031329  lea     rdx, IID_ISdo
0x180031330  mov     rax, [rax]
0x180031333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031338  mov     ebx, eax
0x18003133a  test    eax, eax
0x18003133c  jns     short loc_180031384
0x18003133e  lea     rax, WPP_GLOBAL_Control
0x180031345  mov     rcx, cs:WPP_GLOBAL_Control
0x18003134c  cmp     rcx, rax
0x18003134f  jz      loc_18003153E
0x180031355  cmp     byte ptr [rcx+19h], 2
0x180031359  jb      loc_18003153E
0x18003135f  test    dword ptr [rcx+1Ch], 400h
0x180031366  jz      loc_18003153E
0x18003136c  mov     edx, ebx
0x18003136e  lea     rcx, aIasattributesc; "IASAttributesCollection::Add -- QI(ISdo"...
0x180031375  call    WppDbgPrint
0x18003137a  mov     edx, 1Eh
0x18003137f  jmp     loc_18003151C
0x180031384  movups  xmm0, xmmword ptr [r14]
0x180031388  movaps  xmmword ptr [rbp+var_28], xmm0
0x18003138c  movsd   xmm1, qword ptr [r14+10h]
0x180031392  movsd   qword ptr [rbp+var_28+10h], xmm1
0x180031397  mov     r9, [rbp+arg_18]; struct ISdo *
0x18003139b  lea     r8, [rbp+var_28]; struct tagVARIANT
0x18003139f  mov     edx, esi; enum _ATTRIBUTEID
0x1800313a1  mov     rcx, rdi; this
0x1800313a4  call    ?ValidateAttribute@IASAttributesCollection@@QEAAJW4_ATTRIBUTEID@@UtagVARIANT@@PEAUISdo@@@Z; IASAttributesCollection::ValidateAttribute(_ATTRIBUTEID,tagVARIANT,ISdo *)
0x1800313a9  mov     ebx, eax
0x1800313ab  test    eax, eax
0x1800313ad  jns     short loc_1800313F5
0x1800313af  lea     rax, WPP_GLOBAL_Control
0x1800313b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313bd  cmp     rcx, rax
0x1800313c0  jz      loc_18003153E
0x1800313c6  cmp     byte ptr [rcx+19h], 2
0x1800313ca  jb      loc_18003153E
0x1800313d0  test    dword ptr [rcx+1Ch], 400h
0x1800313d7  jz      loc_18003153E
0x1800313dd  mov     edx, ebx
0x1800313df  lea     rcx, aValidateattrib; "ValidateAttribute returned 0x%x"
0x1800313e6  call    WppDbgPrint
0x1800313eb  mov     edx, 1Fh
0x1800313f0  jmp     loc_18003151C
0x1800313f5  movups  xmm0, xmmword ptr [r14]
0x1800313f9  movaps  xmmword ptr [rbp+var_28], xmm0
0x1800313fd  movsd   xmm1, qword ptr [r14+10h]
0x180031403  movsd   qword ptr [rbp+var_28+10h], xmm1
0x180031408  lea     r8, [rbp+var_28]; struct tagVARIANT
0x18003140c  mov     edx, 40Ch; unsigned int
0x180031411  mov     rcx, [rbp+arg_18]; struct ISdo *
0x180031415  call    ?PutSdoProperty@@YAJPEAUISdo@@KUtagVARIANT@@@Z; PutSdoProperty(ISdo *,ulong,tagVARIANT)
0x18003141a  mov     ebx, eax
0x18003141c  test    eax, eax
0x18003141e  jns     short loc_180031466
0x180031420  lea     rax, WPP_GLOBAL_Control
0x180031427  mov     rcx, cs:WPP_GLOBAL_Control
0x18003142e  cmp     rcx, rax
0x180031431  jz      loc_18003153E
0x180031437  cmp     byte ptr [rcx+19h], 2
0x18003143b  jb      loc_18003153E
0x180031441  test    dword ptr [rcx+1Ch], 400h
0x180031448  jz      loc_18003153E
0x18003144e  mov     edx, ebx
0x180031450  lea     rcx, aPutsdoproperty_1; "PutSdoProperty(PROPERTY_ATTRIBUTE_VALUE"...
0x180031457  call    WppDbgPrint
0x18003145c  mov     edx, 20h ; ' '
0x180031461  jmp     loc_18003151C
0x180031466  mov     rcx, [rbp+arg_18]
0x18003146a  mov     rax, [rcx]
0x18003146d  mov     rax, [rax+58h]
0x180031471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031476  mov     ebx, eax
0x180031478  test    eax, eax
0x18003147a  jns     short loc_1800314BF
0x18003147c  lea     rax, WPP_GLOBAL_Control
0x180031483  mov     rcx, cs:WPP_GLOBAL_Control
0x18003148a  cmp     rcx, rax
0x18003148d  jz      loc_18003153E
0x180031493  cmp     byte ptr [rcx+19h], 2
0x180031497  jb      loc_18003153E
0x18003149d  test    dword ptr [rcx+1Ch], 400h
0x1800314a4  jz      loc_18003153E
0x1800314aa  mov     edx, ebx
0x1800314ac  lea     rcx, aPsdoApplyHr0xX; "pSdo->Apply hr=0x%X"
0x1800314b3  call    WppDbgPrint
0x1800314b8  mov     edx, 21h ; '!'
0x1800314bd  jmp     short loc_18003151C
0x1800314bf  mov     [rsp+68h+var_40], r15
0x1800314c4  mov     rax, [rdi+30h]
0x1800314c8  mov     [rsp+68h+var_48], rax
0x1800314cd  mov     r9, [rdi+28h]
0x1800314d1  mov     r8, [rdi+20h]
0x1800314d5  mov     rdx, [rbp+arg_18]
0x1800314d9  mov     ecx, [rdi+10h]
0x1800314dc  call    ?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z; IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)
0x1800314e1  mov     ebx, eax
0x1800314e3  test    eax, eax
0x1800314e5  jns     short loc_18003153E
0x1800314e7  lea     rax, WPP_GLOBAL_Control
0x1800314ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800314f5  cmp     rcx, rax
0x1800314f8  jz      short loc_18003153E
0x1800314fa  cmp     byte ptr [rcx+19h], 2
0x1800314fe  jb      short loc_18003153E
0x180031500  test    dword ptr [rcx+1Ch], 400h
0x180031507  jz      short loc_18003153E
0x180031509  mov     edx, ebx
0x18003150b  lea     rcx, aIassdocreateit_1; "IASSDOCreateItem failed with 0x%x"
0x180031512  call    WppDbgPrint
0x180031517  mov     edx, 22h ; '"'
0x18003151c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031523  mov     dword ptr [rsp+68h+var_48], ebx
0x180031527  lea     r9, aNpssdo; "NPSSDO"
0x18003152e  lea     r8, WPP_4b583fe665f33bdd9967a3ff271ecbd4_Traceguids
0x180031535  mov     rcx, [rcx+10h]
0x180031539  call    WPP_SF_sd
0x18003153e  lea     rcx, [rbp+arg_18]
0x180031542  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031547  lea     rcx, [rbp+var_38]
0x18003154b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031550  mov     eax, ebx
0x180031552  add     rsp, 68h
0x180031556  pop     r15
0x180031558  pop     r14
0x18003155a  pop     rdi
0x18003155b  pop     rsi
0x18003155c  pop     rbx
0x18003155d  pop     rbp
0x18003155e  retn
```
