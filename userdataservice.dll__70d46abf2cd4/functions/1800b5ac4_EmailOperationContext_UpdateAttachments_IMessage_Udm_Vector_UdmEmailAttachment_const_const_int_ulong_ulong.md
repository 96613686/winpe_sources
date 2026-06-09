# EmailOperationContext::UpdateAttachments(IMessage *,Udm::Vector<UdmEmailAttachment const> const &,int *,ulong *,ulong * *)

- ea: `0x1800b5ac4`
- end: `0x1800b6179`
- name: `?UpdateAttachments@EmailOperationContext@@AEAAJPEAUIMessage@@AEBV?$Vector@$$CBUUdmEmailAttachment@@@Udm@@PEAHPEAKPEAPEAK@Z`
- size: `1717`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b2bf4`

## callees

- `0x1800049f0`
- `0x1800054c0`
- `0x180008ee8`
- `0x180008f0c`
- `0x18000e1f8`
- `0x180012988`
- `0x180013000`
- `0x18003b470`
- `0x18005b080`
- `0x18005b624`
- `0x18005de08`
- `0x18005e048`
- `0x180062408`
- `0x180064828`
- `0x1800977ac`
- `0x1800b093c`
- `0x1800b5938`
- `0x1800b5ac4`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b5e13`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b5e13`
- `CEMAPI!HrSetOneProp` at `0x1800b604f`
- `CEMAPI!HrSetOneProp` at `0x1800b604f`
- `CEMAPI!CreateMAPITableWalker` at `0x1800b5b8a`
- `CEMAPI!CreateMAPITableWalker` at `0x1800b5b8a`

## string_xrefs

- `0x1800b5b50`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b5b9c`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b5d82`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b5def`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b5e2b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b5f72`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b5fd6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b607b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`
- `0x1800b611b`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\emailcontext.cpp`

## pseudocode

```c
__int64 __fastcall EmailOperationContext::UpdateAttachments(
        __int64 a1,
        struct IMAPIProp *a2,
        unsigned __int64 *a3,
        _DWORD *a4,
        unsigned int *a5,
        _QWORD *a6)
{
  struct IMAPIPropVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IMAPIProp *, const IID *const, LPVOID *); // rax
  int v11; // eax
  int v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  const struct _SPropValue *v18; // rdx
  unsigned __int64 v19; // rcx
  const struct _SPropValue *PropByMapiPropId; // rax
  __int64 v21; // r10
  __int64 v22; // r9
  __int64 v23; // rdx
  unsigned int i; // edi
  __int64 v25; // rbx
  void *v26; // rax
  __int64 v27; // r9
  __int64 *j; // rbx
  __int64 v29; // rdx
  int v30; // eax
  HRESULT v31; // edi
  _DWORD *v32; // rbx
  unsigned int k; // r14d
  __int64 v34; // r12
  unsigned __int64 v35; // rcx
  __int64 v36; // rcx
  int updated; // r15d
  EmailOperationContext *v38; // rcx
  struct IMAPIPropVtbl *v39; // rax
  unsigned __int64 v40; // r8
  __int64 v41; // r9
  BYTE *v42; // r9
  __int64 v43; // r9
  __int64 v45; // [rsp+30h] [rbp-A9h] BYREF
  LONG l; // [rsp+38h] [rbp-A1h] BYREF
  struct IAttach *v47; // [rsp+40h] [rbp-99h] BYREF
  _DWORD *v48; // [rsp+48h] [rbp-91h] BYREF
  int v49; // [rsp+50h] [rbp-89h]
  _QWORD v50[4]; // [rsp+58h] [rbp-81h] BYREF
  char v51; // [rsp+78h] [rbp-61h]
  __int64 v52; // [rsp+80h] [rbp-59h] BYREF
  _QWORD v53[3]; // [rsp+88h] [rbp-51h] BYREF
  unsigned int *v54; // [rsp+A0h] [rbp-39h]
  _QWORD *v55; // [rsp+A8h] [rbp-31h]
  __int64 v56; // [rsp+B0h] [rbp-29h] BYREF
  int v57; // [rsp+B8h] [rbp-21h]
  struct _SPropValue Prop; // [rsp+C0h] [rbp-19h] BYREF
  _DWORD v59[4]; // [rsp+D8h] [rbp-1h] BYREF

  lpVtbl = a2->lpVtbl;
  v54 = a5;
  QueryInterface = lpVtbl[1].QueryInterface;
  v55 = a6;
  v52 = 0;
  v11 = ((__int64 (__fastcall *)(struct IMAPIProp *, __int64, __int64 *))QueryInterface)(a2, 0x80000000LL, &v52);
  v12 = v11;
  if ( v11 < 0 )
  {
    v13 = 2714;
    v14 = 1;
    v15 = (unsigned int)v11;
LABEL_5:
    Log_HREvent(
      v15,
      v14,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
      v13);
    goto LABEL_85;
  }
  v14 = v52;
  if ( !v52 )
  {
    v12 = -2147221233;
    v13 = 2716;
    v15 = 2147746063LL;
    goto LABEL_5;
  }
  v59[0] = 2;
  v59[1] = 237043715;
  v59[2] = -2108293109;
  v45 = 0;
  v16 = CreateMAPITableWalker(0, v52, v59, &v45);
  v12 = v16;
  if ( v16 < 0 )
  {
    Log_HREvent(
      (unsigned int)v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
      2726);
    goto LABEL_84;
  }
  utl::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>::unordered_map<enum _SebiEventType,_GUID,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>>(v50);
  while ( 1 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 24LL))(v45);
    if ( v12 < 0 )
    {
      v22 = 2733;
      goto LABEL_81;
    }
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 32LL))(v45);
    if ( !v17 )
      break;
    if ( !FindPropByMapiPropId(*(unsigned int *)(v17 + 4), *(const struct _SPropValue **)(v17 + 8), 0xE210003u) )
    {
      v22 = 2743;
      v23 = 0;
      v12 = -2147418113;
      goto LABEL_82;
    }
    PropByMapiPropId = FindPropByMapiPropId(v19, v18, 0x8256000B);
    l = 0;
    if ( PropByMapiPropId )
      l = PropByMapiPropId->Value.l;
    if ( !*(_QWORD *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,int>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,int>>,0>::emplace<unsigned long const &,int &,0>(
                       v50,
                       &v56,
                       v21 + 8,
                       &l) )
    {
      v22 = 2753;
      v23 = 0;
      v12 = -2147024882;
      goto LABEL_82;
    }
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *a3 )
    {
      for ( j = (__int64 *)v50[0]; j != v50; j = (__int64 *)*j )
      {
        v29 = *((unsigned int *)j + 6);
        if ( *((_DWORD *)j + 7) )
          *a4 = 0;
        v30 = ((__int64 (__fastcall *)(struct IMAPIProp *, __int64, _QWORD, _QWORD, _DWORD))a2->lpVtbl[1].GetLastError)(
                a2,
                v29,
                0,
                0,
                0);
        v31 = v30;
        if ( v30 < 0 )
        {
          Log_HREvent(
            (unsigned int)v30,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
            2795);
LABEL_78:
          utl::_HashTable<unsigned long,utl::pair<unsigned long const,int>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,int>>,0>::_ClearList(v50);
          utl::_HashTable<enum _SebiEventType,utl::pair<enum _SebiEventType const,_GUID>,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>,0>::_FreeBuckets(v50);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v45);
          v12 = v31;
          goto LABEL_85;
        }
      }
      v48 = LocalAlloc(0x40u, 4 * *a3);
      v32 = v48;
      if ( !v48 )
      {
        v12 = -2147024882;
        Log_HREvent(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
          2799);
LABEL_52:
        auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v48);
        goto LABEL_83;
      }
      utl::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>::vector<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>,utl::allocator<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>>(v53);
      for ( k = 0; k < *a3; ++k )
      {
        v34 = 80LL * k;
        v35 = v34 + a3[1];
        v47 = 0;
        v56 = 0;
        v57 = 0;
        if ( (unsigned __int8)operator==(v35, &v56) )
        {
          v39 = a2->lpVtbl;
          l = 0;
          updated = ((__int64 (__fastcall *)(struct IMAPIProp *, _QWORD, _QWORD, LONG *, struct IAttach **))v39[1].Release)(
                      a2,
                      0,
                      0,
                      &l,
                      &v47);
          if ( updated < 0 )
          {
            v41 = 2822;
            goto LABEL_67;
          }
          v32[k] = l;
        }
        else
        {
          if ( !*(_DWORD *)(v36 + 32) )
          {
            updated = ((__int64 (__fastcall *)(struct IMAPIProp *, _QWORD, _QWORD, _QWORD, struct IAttach **))a2->lpVtbl[1].AddRef)(
                        a2,
                        *(unsigned int *)(v36 + 8),
                        0,
                        0,
                        &v47);
            if ( updated < 0 )
            {
              v41 = 2813;
LABEL_67:
              Log_HREvent(
                (unsigned int)updated,
                1,
                "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
                v41);
              ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v47);
              utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v53);
              auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v48);
              utl::_HashTable<unsigned long,utl::pair<unsigned long const,int>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,int>>,0>::_ClearList(v50);
              utl::_HashTable<enum _SebiEventType,utl::pair<enum _SebiEventType const,_GUID>,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>,0>::_FreeBuckets(v50);
              ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v45);
              v12 = updated;
              goto LABEL_85;
            }
          }
          v38 = (EmailOperationContext *)*(unsigned int *)(v34 + a3[1] + 8);
          v32[k] = (_DWORD)v38;
        }
        v40 = v34 + a3[1];
        if ( !*(_DWORD *)(v40 + 32) )
        {
          updated = EmailOperationContext::UpdateAttachment(v38, v47, (const struct UdmEmailAttachment *)v40);
          if ( updated < 0 )
          {
            v41 = 2830;
            goto LABEL_67;
          }
        }
        if ( *(_DWORD *)(v34 + a3[1] + 12) == 3
          && !(unsigned __int8)utl::vector<unsigned long,utl::allocator<unsigned long>>::_PushBackOne<unsigned long const &>(
                                 v53,
                                 &v32[k]) )
        {
          v12 = -2147024882;
          Log_HREvent(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
            2835);
          ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v47);
          utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v53);
          goto LABEL_52;
        }
        ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v47);
      }
      *(_QWORD *)&Prop.dwAlignPad = 0;
      Prop.Value.cur.Hi = 0;
      Prop.ulPropTag = -2127298302;
      v31 = ULongLongToULong((v53[1] - v53[0]) & 0xFFFFFFFFFFFFFFFCuLL, (unsigned int *)&Prop.Value);
      if ( v31 >= 0 )
      {
        Prop.Value.bin.lpb = v42;
        v31 = HrSetOneProp(a2, &Prop);
        if ( v31 >= 0 )
        {
          v31 = ULongLongToULong(*a3, v54);
          if ( v31 >= 0 )
          {
            v48 = 0;
            *v55 = v32;
            utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v53);
            auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v48);
            utl::_HashTable<unsigned long,utl::pair<unsigned long const,int>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,int>>,0>::_ClearList(v50);
            utl::_HashTable<enum _SebiEventType,utl::pair<enum _SebiEventType const,_GUID>,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>,0>::_FreeBuckets(v50);
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v45);
            ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
            return 0;
          }
          v43 = 2846;
        }
        else
        {
          v43 = 2844;
        }
      }
      else
      {
        v43 = 2842;
      }
      Log_HREvent(
        (unsigned int)v31,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
        v43);
      utl::vector<UdmEmailParticipant,utl::allocator<UdmEmailParticipant>>::_Uninit(v53);
      auto_local_array_ptr<unsigned long>::~auto_local_array_ptr<unsigned long>(&v48);
      goto LABEL_78;
    }
    v25 = a3[1] + 80LL * i;
    v48 = 0;
    v49 = 0;
    if ( (unsigned __int8)operator==(v25, &v48) )
    {
      if ( !*(_DWORD *)(v25 + 32) )
        goto LABEL_25;
      v22 = 2777;
LABEL_36:
      v23 = 0;
      v12 = -2147024809;
      goto LABEL_82;
    }
    if ( *(_DWORD *)(v25 + 4) != 9 )
    {
      v22 = 2763;
      goto LABEL_36;
    }
    utl::_HashTable<unsigned long,utl::pair<unsigned long const,bool>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,bool>>,0>::find<void>(
      v50,
      &v47,
      v25 + 8);
    if ( v47 == (struct IAttach *)v50 )
    {
      v22 = 2767;
      v23 = 0;
      v12 = -2147467259;
      goto LABEL_82;
    }
    if ( *(_DWORD *)(v25 + 32) != HIDWORD(v47[3].lpVtbl) )
    {
      v22 = 2770;
      goto LABEL_36;
    }
    v26 = (void *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,int>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,int>>,0>::_UnlinkNode(
                    v50,
                    v47,
                    (8LL << v51) - 1);
    operator delete(v26);
LABEL_25:
    if ( *(_DWORD *)(v25 + 32) )
      continue;
    if ( !*(_QWORD *)(v25 + 40) )
      break;
    if ( !*(_QWORD *)(v25 + 48) )
    {
      v27 = 2690;
      goto LABEL_41;
    }
    if ( *(_DWORD *)(v25 + 24) && !*(_QWORD *)(v25 + 64) && !*(_QWORD *)(v25 + 72) )
    {
      v27 = 2696;
      goto LABEL_41;
    }
    if ( *(_QWORD *)(v25 + 16) > 0xFFFFFFFF )
    {
      v27 = 2700;
      goto LABEL_41;
    }
  }
  v27 = 2689;
LABEL_41:
  v12 = -2147024809;
  Log_HREvent(
    2147942487LL,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
    v27);
  v22 = 2782;
LABEL_81:
  v23 = 1;
LABEL_82:
  Log_HREvent(
    (unsigned int)v12,
    v23,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\emailcontext.cpp",
    v22);
LABEL_83:
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,int>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,int>>,0>::_ClearList(v50);
  utl::_HashTable<enum _SebiEventType,utl::pair<enum _SebiEventType const,_GUID>,utl::hash<enum _SebiEventType>,utl::equal_to<enum _SebiEventType>,utl::allocator<utl::pair<enum _SebiEventType const,_GUID>>,0>::_FreeBuckets(v50);
LABEL_84:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v45);
LABEL_85:
  ATL::CComPtrBase<ISODACompletionCallback>::~CComPtrBase<ISODACompletionCallback>(&v52);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800b5ac4  mov     [rsp-8+arg_0], rbx
0x1800b5ac9  push    rbp
0x1800b5aca  push    rsi
0x1800b5acb  push    rdi
0x1800b5acc  push    r12
0x1800b5ace  push    r13
0x1800b5ad0  push    r14
0x1800b5ad2  push    r15
0x1800b5ad4  lea     rbp, [rsp-17h]
0x1800b5ad9  sub     rsp, 0F0h
0x1800b5ae0  mov     rax, cs:__security_cookie
0x1800b5ae7  xor     rax, rsp
0x1800b5aea  mov     [rbp+47h+var_38], rax
0x1800b5aee  mov     rax, [rdx]
0x1800b5af1  mov     r13, rdx
0x1800b5af4  mov     r15, [rbp+47h+arg_20]
0x1800b5af8  mov     rsi, r8
0x1800b5afb  mov     [rbp+47h+var_80], r15
0x1800b5aff  lea     r8, [rbp+47h+var_A0]
0x1800b5b03  mov     r15, [rbp+47h+arg_28]
0x1800b5b07  mov     edx, 80000000h
0x1800b5b0c  mov     rax, [rax+70h]
0x1800b5b10  mov     rcx, r13
0x1800b5b13  mov     [rbp+47h+var_78], r15
0x1800b5b17  mov     r14, r9
0x1800b5b1a  xor     r15d, r15d
0x1800b5b1d  mov     [rbp+47h+var_A0], r15
0x1800b5b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5b26  mov     ebx, eax
0x1800b5b28  test    eax, eax
0x1800b5b2a  jns     short loc_1800B5B3A
0x1800b5b2c  mov     r9d, 0A9Ah
0x1800b5b32  lea     edx, [r15+1]
0x1800b5b36  mov     ecx, eax
0x1800b5b38  jmp     short loc_1800B5B50
0x1800b5b3a  mov     rdx, [rbp+47h+var_A0]
0x1800b5b3e  test    rdx, rdx
0x1800b5b41  jnz     short loc_1800B5B61
0x1800b5b43  mov     ebx, 8004010Fh
0x1800b5b48  mov     r9d, 0A9Ch
0x1800b5b4e  mov     ecx, ebx
0x1800b5b50  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b5b57  call    Log_HREvent
0x1800b5b5c  jmp     loc_1800B6147
0x1800b5b61  mov     edi, 0E210003h
0x1800b5b66  mov     [rbp+47h+var_48], 2
0x1800b5b6d  mov     r12d, 8256000Bh
0x1800b5b73  mov     [rbp+47h+var_44], edi
0x1800b5b76  lea     r9, [rsp+120h+var_F0]
0x1800b5b7b  mov     [rbp+47h+var_40], r12d
0x1800b5b7f  lea     r8, [rbp+47h+var_48]
0x1800b5b83  mov     [rsp+120h+var_F0], r15
0x1800b5b88  xor     ecx, ecx
0x1800b5b8a  call    cs:__imp_CreateMAPITableWalker
0x1800b5b90  mov     ebx, eax
0x1800b5b92  test    eax, eax
0x1800b5b94  jns     short loc_1800B5BB4
0x1800b5b96  mov     r9d, 0AA6h
0x1800b5b9c  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b5ba3  mov     edx, 1
0x1800b5ba8  mov     ecx, eax
0x1800b5baa  call    Log_HREvent
0x1800b5baf  jmp     loc_1800B613D
0x1800b5bb4  lea     rcx, [rsp+120h+var_C8]
0x1800b5bb9  call    ??0?$unordered_map@W4_SebiEventType@@U_GUID@@U?$hash@W4_SebiEventType@@@utl@@U?$equal_to@W4_SebiEventType@@@4@V?$allocator@U?$pair@$$CBW4_SebiEventType@@U_GUID@@@utl@@@4@@utl@@QEAA@XZ; utl::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>::unordered_map<_SebiEventType,_GUID,utl::hash<_SebiEventType>,utl::equal_to<_SebiEventType>,utl::allocator<utl::pair<_SebiEventType const,_GUID>>>(void)
0x1800b5bbe  mov     rcx, [rsp+120h+var_F0]
0x1800b5bc3  mov     rax, [rcx]
0x1800b5bc6  mov     rax, [rax+18h]
0x1800b5bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5bcf  mov     ebx, eax
0x1800b5bd1  test    eax, eax
0x1800b5bd3  js      loc_1800B6110
0x1800b5bd9  mov     rcx, [rsp+120h+var_F0]
0x1800b5bde  mov     rax, [rcx]
0x1800b5be1  mov     rax, [rax+20h]
0x1800b5be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5bea  test    rax, rax
0x1800b5bed  jz      short loc_1800B5C5F
0x1800b5bef  mov     rdx, [rax+8]; struct _SPropValue *
0x1800b5bf3  mov     r8d, edi; unsigned int
0x1800b5bf6  mov     ecx, [rax+4]; unsigned __int64
0x1800b5bf9  call    ?FindPropByMapiPropId@@YAPEBU_SPropValue@@_KPEBU1@K@Z; FindPropByMapiPropId(unsigned __int64,_SPropValue const *,ulong)
0x1800b5bfe  mov     r10, rax
0x1800b5c01  test    rax, rax
0x1800b5c04  jz      short loc_1800B5C4D
0x1800b5c06  mov     r8d, r12d; unsigned int
0x1800b5c09  call    ?FindPropByMapiPropId@@YAPEBU_SPropValue@@_KPEBU1@K@Z; FindPropByMapiPropId(unsigned __int64,_SPropValue const *,ulong)
0x1800b5c0e  mov     [rsp+120h+var_E8], r15d
0x1800b5c13  test    rax, rax
0x1800b5c16  jz      short loc_1800B5C1F
0x1800b5c18  mov     ecx, [rax+8]
0x1800b5c1b  mov     [rsp+120h+var_E8], ecx
0x1800b5c1f  lea     r8, [r10+8]
0x1800b5c23  lea     r9, [rsp+120h+var_E8]
0x1800b5c28  lea     rdx, [rbp+47h+var_70]
0x1800b5c2c  lea     rcx, [rsp+120h+var_C8]
0x1800b5c31  call    ??$emplace@AEBKAEAH$0A@@?$_HashTable@KU?$pair@$$CBKH@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKH@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBKH@utl@@@utl@@U?$pair@$$CBKH@2@@utl@@_N@1@AEBKAEAH@Z; utl::_HashTable<ulong,utl::pair<ulong const,int>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,int>>,0>::emplace<ulong const &,int &,0>(ulong const &,int &)
0x1800b5c36  cmp     [rax], r15
0x1800b5c39  jnz     short loc_1800B5BBE
0x1800b5c3b  mov     r9d, 0AC1h
0x1800b5c41  xor     edx, edx
0x1800b5c43  mov     ebx, 8007000Eh
0x1800b5c48  jmp     loc_1800B611B
0x1800b5c4d  mov     r9d, 0AB7h
0x1800b5c53  xor     edx, edx
0x1800b5c55  mov     ebx, 8000FFFFh
0x1800b5c5a  jmp     loc_1800B611B
0x1800b5c5f  mov     edi, r15d
0x1800b5c62  mov     eax, edi
0x1800b5c64  cmp     rax, [rsi]
0x1800b5c67  jnb     loc_1800B5DA5
0x1800b5c6d  lea     rbx, [rax+rax*4]
0x1800b5c71  xor     eax, eax
0x1800b5c73  shl     rbx, 4
0x1800b5c77  lea     rdx, [rsp+120h+var_D8]
0x1800b5c7c  add     rbx, [rsi+8]
0x1800b5c80  mov     rcx, rbx
0x1800b5c83  mov     [rsp+120h+var_D8], rax
0x1800b5c88  mov     [rsp+120h+var_D0], eax
0x1800b5c8c  call    ??8@YA_NAEBUUdmObjectId@@0@Z; operator==(UdmObjectId const &,UdmObjectId const &)
0x1800b5c91  test    al, al
0x1800b5c93  jnz     short loc_1800B5CF3
0x1800b5c95  cmp     dword ptr [rbx+4], 9
0x1800b5c99  jnz     loc_1800B5D4D
0x1800b5c9f  lea     r8, [rbx+8]
0x1800b5ca3  lea     rdx, [rsp+120h+var_E0]
0x1800b5ca8  lea     rcx, [rsp+120h+var_C8]
0x1800b5cad  call    ??$find@X@?$_HashTable@KU?$pair@$$CBK_N@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBK_N@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBK_N@utl@@@utl@@U?$pair@$$CBK_N@2@@1@AEBK@Z; utl::_HashTable<ulong,utl::pair<ulong const,bool>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,bool>>,0>::find<void>(ulong const &)
0x1800b5cb2  mov     rdx, [rsp+120h+var_E0]
0x1800b5cb7  lea     rax, [rsp+120h+var_C8]
0x1800b5cbc  cmp     rdx, rax
0x1800b5cbf  jz      short loc_1800B5D3B
0x1800b5cc1  mov     eax, [rdx+1Ch]
0x1800b5cc4  cmp     [rbx+20h], eax
0x1800b5cc7  jnz     short loc_1800B5D33
0x1800b5cc9  mov     cl, [rbp+47h+var_A8]
0x1800b5ccc  mov     r8d, 8
0x1800b5cd2  shl     r8, cl
0x1800b5cd5  lea     rcx, [rsp+120h+var_C8]
0x1800b5cda  dec     r8
0x1800b5cdd  call    ?_UnlinkNode@?$_HashTable@KU?$pair@$$CBKH@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKH@utl@@@2@$0A@@utl@@AEAAPEAU?$_HashNode@U?$pair@$$CBKH@utl@@@2@V?$_DlistConstIt@U?$_HashNode@U?$pair@$$CBKH@utl@@@utl@@U?$pair@$$CBKH@2@@2@_K@Z; utl::_HashTable<ulong,utl::pair<ulong const,int>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,int>>,0>::_UnlinkNode(utl::_DlistConstIt<utl::_HashNode<utl::pair<ulong const,int>>,utl::pair<ulong const,int>>,unsigned __int64)
0x1800b5ce2  mov     rcx, rax; Block
0x1800b5ce5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800b5cec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800b5cf1  jmp     short loc_1800B5CFD
0x1800b5cf3  cmp     [rbx+20h], r15d
0x1800b5cf7  jnz     loc_1800B5D9D
0x1800b5cfd  cmp     [rbx+20h], r15d
0x1800b5d01  jnz     short loc_1800B5D2C
0x1800b5d03  cmp     [rbx+28h], r15
0x1800b5d07  jz      short loc_1800B5D77
0x1800b5d09  cmp     [rbx+30h], r15
0x1800b5d0d  jz      short loc_1800B5D6F
0x1800b5d0f  cmp     [rbx+18h], r15d
0x1800b5d13  jz      short loc_1800B5D21
0x1800b5d15  cmp     [rbx+40h], r15
0x1800b5d19  jnz     short loc_1800B5D21
0x1800b5d1b  cmp     [rbx+48h], r15
0x1800b5d1f  jz      short loc_1800B5D5F
0x1800b5d21  mov     eax, 0FFFFFFFFh
0x1800b5d26  cmp     [rbx+10h], rax
0x1800b5d2a  ja      short loc_1800B5D67
0x1800b5d2c  inc     edi
0x1800b5d2e  jmp     loc_1800B5C62
0x1800b5d33  mov     r9d, 0AD2h
0x1800b5d39  jmp     short loc_1800B5D53
0x1800b5d3b  mov     r9d, 0ACFh
0x1800b5d41  xor     edx, edx
0x1800b5d43  mov     ebx, 80004005h
0x1800b5d48  jmp     loc_1800B611B
0x1800b5d4d  mov     r9d, 0ACBh
0x1800b5d53  xor     edx, edx
0x1800b5d55  mov     ebx, 80070057h
0x1800b5d5a  jmp     loc_1800B611B
0x1800b5d5f  mov     r9d, 0A88h
0x1800b5d65  jmp     short loc_1800B5D7D
0x1800b5d67  mov     r9d, 0A8Ch
0x1800b5d6d  jmp     short loc_1800B5D7D
0x1800b5d6f  mov     r9d, 0A82h
0x1800b5d75  jmp     short loc_1800B5D7D
0x1800b5d77  mov     r9d, 0A81h
0x1800b5d7d  mov     ebx, 80070057h
0x1800b5d82  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b5d89  mov     ecx, ebx
0x1800b5d8b  xor     edx, edx
0x1800b5d8d  call    Log_HREvent
0x1800b5d92  mov     r9d, 0ADEh
0x1800b5d98  jmp     loc_1800B6116
0x1800b5d9d  mov     r9d, 0AD9h
0x1800b5da3  jmp     short loc_1800B5D53
0x1800b5da5  mov     rbx, [rsp+120h+var_C8]
0x1800b5daa  lea     rax, [rsp+120h+var_C8]
0x1800b5daf  cmp     rbx, rax
0x1800b5db2  jz      short loc_1800B5E07
0x1800b5db4  mov     edx, [rbx+18h]
0x1800b5db7  cmp     [rbx+1Ch], r15d
0x1800b5dbb  jz      short loc_1800B5DC0
0x1800b5dbd  mov     [r14], r15d
0x1800b5dc0  mov     rax, [r13+0]
0x1800b5dc4  xor     r9d, r9d
0x1800b5dc7  xor     r8d, r8d
0x1800b5dca  mov     dword ptr [rsp+120h+var_100], r15d
0x1800b5dcf  mov     rcx, r13
0x1800b5dd2  mov     rax, [rax+88h]
0x1800b5dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5dde  mov     edi, eax
0x1800b5de0  test    eax, eax
0x1800b5de2  js      short loc_1800B5DE9
0x1800b5de4  mov     rbx, [rbx]
0x1800b5de7  jmp     short loc_1800B5DAA
0x1800b5de9  mov     r9d, 0AEBh
0x1800b5def  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b5df6  mov     edx, 1
0x1800b5dfb  mov     ecx, edi
0x1800b5dfd  call    Log_HREvent
0x1800b5e02  jmp     loc_1800B60A1
0x1800b5e07  mov     rdx, [rsi]
0x1800b5e0a  mov     ecx, 40h ; '@'; uFlags
0x1800b5e0f  shl     rdx, 2; uBytes
0x1800b5e13  call    cs:__imp_LocalAlloc
0x1800b5e19  mov     [rsp+120h+var_D8], rax
0x1800b5e1e  mov     rbx, rax
0x1800b5e21  test    rax, rax
0x1800b5e24  jnz     short loc_1800B5E50
0x1800b5e26  mov     ebx, 8007000Eh
0x1800b5e2b  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800b5e32  mov     ecx, ebx
0x1800b5e34  mov     r9d, 0AEFh
0x1800b5e3a  xor     edx, edx
0x1800b5e3c  call    Log_HREvent
0x1800b5e41  lea     rcx, [rsp+120h+var_D8]
0x1800b5e46  call    ??1?$auto_local_array_ptr@K@@QEAA@XZ; auto_local_array_ptr<ulong>::~auto_local_array_ptr<ulong>(void)
0x1800b5e4b  jmp     loc_1800B6129
0x1800b5e50  lea     rcx, [rbp+47h+var_98]
0x1800b5e54  call    ??0?$vector@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>::vector<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>,utl::allocator<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>>(void)
0x1800b5e59  mov     r14d, r15d
0x1800b5e5c  mov     edi, r14d
0x1800b5e5f  cmp     rdi, [rsi]
0x1800b5e62  jnb     loc_1800B600F
0x1800b5e68  mov     rcx, [rsi+8]
0x1800b5e6c  lea     r12, [rdi+rdi*4]
0x1800b5e70  xor     eax, eax
0x1800b5e72  shl     r12, 4
0x1800b5e76  add     rcx, r12
0x1800b5e79  mov     [rsp+120h+var_E0], r15
0x1800b5e7e  lea     rdx, [rbp+47h+var_70]
0x1800b5e82  mov     [rbp+47h+var_70], rax
0x1800b5e86  mov     [rbp+47h+var_68], eax
0x1800b5e89  call    ??8@YA_NAEBUUdmObjectId@@0@Z; operator==(UdmObjectId const &,UdmObjectId const &)
0x1800b5e8e  test    al, al
0x1800b5e90  jnz     short loc_1800B5ED7
0x1800b5e92  cmp     [rcx+20h], r15d
0x1800b5e96  jnz     short loc_1800B5EC9
0x1800b5e98  mov     rax, [r13+0]
0x1800b5e9c  lea     rdx, [rsp+120h+var_E0]
0x1800b5ea1  mov     [rsp+120h+var_100], rdx
0x1800b5ea6  xor     r9d, r9d
0x1800b5ea9  mov     edx, [rcx+8]
0x1800b5eac  xor     r8d, r8d
0x1800b5eaf  mov     rcx, r13
0x1800b5eb2  mov     rax, [rax+78h]
0x1800b5eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5ebb  mov     r15d, eax
0x1800b5ebe  test    eax, eax
0x1800b5ec0  js      loc_1800B5F6C
0x1800b5ec6  xor     r15d, r15d
0x1800b5ec9  mov     rax, [rsi+8]
0x1800b5ecd  mov     ecx, [r12+rax+8]
0x1800b5ed2  mov     [rbx+rdi*4], ecx
0x1800b5ed5  jmp     short loc_1800B5F18
0x1800b5ed7  mov     rax, [r13+0]
0x1800b5edb  lea     rcx, [rsp+120h+var_E0]
0x1800b5ee0  mov     [rsp+120h+var_100], rcx
0x1800b5ee5  lea     r9, [rsp+120h+var_E8]
0x1800b5eea  xor     r8d, r8d
0x1800b5eed  mov     [rsp+120h+var_E8], r15d
0x1800b5ef2  xor     edx, edx
0x1800b5ef4  mov     rcx, r13
0x1800b5ef7  mov     rax, [rax+80h]
0x1800b5efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5f03  mov     r15d, eax
0x1800b5f06  test    eax, eax
0x1800b5f08  js      loc_1800B6004
0x1800b5f0e  mov     eax, [rsp+120h+var_E8]
0x1800b5f12  xor     r15d, r15d
0x1800b5f15  mov     [rbx+rdi*4], eax
0x1800b5f18  mov     r8, [rsi+8]
0x1800b5f1c  add     r8, r12; struct UdmEmailAttachment *
0x1800b5f1f  cmp     [r8+20h], r15d
0x1800b5f23  jnz     short loc_1800B5F3D
0x1800b5f25  mov     rdx, [rsp+120h+var_E0]; struct IAttach *
0x1800b5f2a  call    ?UpdateAttachment@EmailOperationContext@@QEAAJPEAUIAttach@@AEBUUdmEmailAttachment@@@Z; EmailOperationContext::UpdateAttachment(IAttach *,UdmEmailAttachment const &)
0x1800b5f2f  mov     r15d, eax
0x1800b5f32  test    eax, eax
0x1800b5f34  js      loc_1800B5FC9
0x1800b5f3a  xor     r15d, r15d
0x1800b5f3d  mov     rax, [rsi+8]
0x1800b5f41  cmp     dword ptr [r12+rax+0Ch], 3
0x1800b5f47  jnz     short loc_1800B5F5A
0x1800b5f49  lea     rdx, [rbx+rdi*4]
  ... truncated ...
```
