# ChatOperationContext::_DeduplicateRecipients(ulong,UdmChatParticipant const *,int *,ulong *,UdmChatParticipant * *)

- ea: `0x18006e770`
- end: `0x18006ee60`
- name: `?_DeduplicateRecipients@ChatOperationContext@@AEAAJKPEBUUdmChatParticipant@@PEAHPEAKPEAPEAU2@@Z`
- size: `1776`
- prototype: `__int64 __fastcall(ChatOperationContext *__hidden this, unsigned int, const struct UdmChatParticipant *, int *, unsigned int *, struct UdmChatParticipant **)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d3654`
- `0x1800d49d4`

## callees

- `0x180008f0c`
- `0x180018c20`
- `0x18001b340`
- `0x180035c40`
- `0x18006dd94`
- `0x18006df70`
- `0x18006e770`
- `0x18006ee68`
- `0x18006eea0`
- `0x180092c30`
- `0x1800977b8`
- `0x1800d0894`
- `0x1800d08d4`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `PhoneUtil!GetTelUriFromDialString` at `0x18006e9d5`
- `PhoneUtil!GetTelUriFromDialString` at `0x18006e9d5`
- `UserDataTypeHelperUtil!DupString` at `0x18006ec70`
- `UserDataTypeHelperUtil!DupString` at `0x18006ec70`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x18006e91b`
- `PhoneOm!PhoneGetProviderLineServiceInfo` at `0x18006e91b`
- `PhoneOm!PhoneAPIInitialize` at `0x18006e7e5`
- `PhoneOm!PhoneAPIInitialize` at `0x18006e7e5`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x18006e87f`
- `PhoneOm!PhoneGetDefaultOutgoingLine` at `0x18006e87f`

## string_xrefs

- `0x18006e7f8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18006e892`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18006e92e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18006ea56`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18006eadd`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18006eb64`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18006ec96`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`
- `0x18006edb6`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\chatcontext.cpp`

## pseudocode

```c
__int64 __fastcall ChatOperationContext::_DeduplicateRecipients(
        ChatOperationContext *this,
        unsigned int a2,
        const unsigned __int16 **a3,
        int *a4,
        unsigned int *a5,
        struct UdmChatParticipant **a6)
{
  unsigned __int64 v8; // rdi
  int v9; // eax
  unsigned int v10; // r14d
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  void **v13; // rax
  __int64 v14; // rdx
  int DefaultOutgoingLine; // eax
  __int64 v17; // rcx
  _QWORD *v18; // rbx
  void **v19; // rax
  __int64 v20; // rdx
  int ProviderLineServiceInfo; // eax
  __int64 v22; // rcx
  _QWORD *v23; // rbx
  void **v24; // rax
  __int64 v25; // rdx
  __int64 i; // rbx
  int TelUriFromDialString; // eax
  __int64 v28; // rcx
  _QWORD *v29; // rbx
  void **v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  _QWORD *v33; // rbx
  void **v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rcx
  _QWORD *v37; // rbx
  void **v38; // rax
  __int64 v39; // rdx
  Udm *v40; // rbx
  unsigned int v41; // r14d
  _QWORD *v42; // rdi
  int v43; // r15d
  _OWORD *v44; // rax
  __int128 v45; // xmm1
  __int128 v46; // xmm2
  _OWORD *v47; // rcx
  int v48; // eax
  __int64 v49; // rdx
  unsigned int v50; // r12d
  struct UdmChatParticipant *v51; // rdx
  __int64 v52; // rcx
  _QWORD *v53; // rsi
  void **v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  _QWORD *v57; // rbx
  void **v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  _QWORD *v61; // rbx
  void **v62; // rax
  __int64 v63; // rdx
  _BYTE v64[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v65[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v66; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v67; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 **v68; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int *v69; // [rsp+60h] [rbp-A0h]
  struct UdmChatParticipant **v70; // [rsp+68h] [rbp-98h]
  _BYTE v71[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v72[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v73[16]; // [rsp+98h] [rbp-68h] BYREF
  GUID v74; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v75[128]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v76[96]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v77[64]; // [rsp+200h] [rbp+100h] BYREF

  v69 = a5;
  v70 = a6;
  v8 = a2;
  *a4 = 0;
  utl::map<unsigned long,_GUID,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,_GUID>>>::map<unsigned long,_GUID,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,_GUID>>>(v65);
  memset_0(v77, 0, sizeof(v77));
  v9 = PhoneAPIInitialize();
  v10 = v9;
  if ( v9 >= 0 )
  {
    v64[1] = 1;
    v74 = GUID_NULL;
    DefaultOutgoingLine = PhoneGetDefaultOutgoingLine(&v74);
    v10 = DefaultOutgoingLine;
    if ( DefaultOutgoingLine < 0 )
    {
      Log_HREvent(
        (unsigned int)DefaultOutgoingLine,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        2733);
      tlx::_UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___::__UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___(v64);
      v18 = v66;
      if ( v66 == v65 )
        return v10;
      while ( 1 )
      {
        v19 = (void **)v18[1];
        if ( v19 == &utl::_TreeSentinel )
        {
          while ( 1 )
          {
            v19 = (void **)v18[2];
            if ( v19 != &utl::_TreeSentinel )
              break;
            do
            {
              v20 = (__int64)v18;
              v18 = (_QWORD *)(*v18 & 0xFFFFFFFFFFFFFFFEuLL);
              utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
                v17,
                v20);
              if ( v18 == v65 )
                return v10;
            }
            while ( (void **)v18[1] == &utl::_TreeSentinel );
            v18[1] = &utl::_TreeSentinel;
          }
        }
        v18 = v19;
      }
    }
    memset_0(v75, 0, 0x13Cu);
    ProviderLineServiceInfo = PhoneGetProviderLineServiceInfo(&v74, v75);
    v10 = ProviderLineServiceInfo;
    if ( ProviderLineServiceInfo < 0 )
    {
      Log_HREvent(
        (unsigned int)ProviderLineServiceInfo,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
        2736);
      tlx::_UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___::__UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___(v64);
      v23 = v66;
      if ( v66 == v65 )
        return v10;
      while ( 1 )
      {
        v24 = (void **)v23[1];
        if ( v24 == &utl::_TreeSentinel )
        {
          while ( 1 )
          {
            v24 = (void **)v23[2];
            if ( v24 != &utl::_TreeSentinel )
              break;
            do
            {
              v25 = (__int64)v23;
              v23 = (_QWORD *)(*v23 & 0xFFFFFFFFFFFFFFFEuLL);
              utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
                v22,
                v25);
              if ( v23 == v65 )
                return v10;
            }
            while ( (void **)v23[1] == &utl::_TreeSentinel );
            v23[1] = &utl::_TreeSentinel;
          }
        }
        v23 = v24;
      }
    }
    for ( i = 0; (unsigned int)i < (unsigned int)v8; i = (unsigned int)(i + 1) )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v71);
      TelUriFromDialString = GetTelUriFromDialString(a3[6 * i], v76, v77, 0x40u);
      v10 = TelUriFromDialString;
      if ( TelUriFromDialString < 0 )
      {
        Log_HREvent(
          (unsigned int)TelUriFromDialString,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
          2746);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v71);
        tlx::_UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___::__UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___(v64);
        v37 = v66;
        if ( v66 == v65 )
          return v10;
        while ( 1 )
        {
          v38 = (void **)v37[1];
          if ( v38 == &utl::_TreeSentinel )
          {
            while ( 1 )
            {
              v38 = (void **)v37[2];
              if ( v38 != &utl::_TreeSentinel )
                break;
              do
              {
                v39 = (__int64)v37;
                v37 = (_QWORD *)(*v37 & 0xFFFFFFFFFFFFFFFEuLL);
                utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
                  v36,
                  v39);
                if ( v37 == v65 )
                  return v10;
              }
              while ( (void **)v37[1] == &utl::_TreeSentinel );
              v37[1] = &utl::_TreeSentinel;
            }
          }
          v37 = v38;
        }
      }
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v71,
                               v77) )
      {
        Log_HREvent(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
          2747);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v71);
        tlx::_UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___::__UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___(v64);
        v33 = v66;
        if ( v66 != v65 )
        {
          while ( 1 )
          {
            v34 = (void **)v33[1];
            if ( v34 == &utl::_TreeSentinel )
            {
              while ( 1 )
              {
                v34 = (void **)v33[2];
                if ( v34 != &utl::_TreeSentinel )
                  break;
                do
                {
                  v35 = (__int64)v33;
                  v33 = (_QWORD *)(*v33 & 0xFFFFFFFFFFFFFFFEuLL);
                  utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
                    v32,
                    v35);
                  if ( v33 == v65 )
                    return 2147942414LL;
                }
                while ( (void **)v33[1] == &utl::_TreeSentinel );
                v33[1] = &utl::_TreeSentinel;
              }
            }
            v33 = v34;
          }
        }
        return 2147942414LL;
      }
      if ( *(_QWORD **)utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,UdmChatParticipant const *>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,UdmChatParticipant const *>>,0>::find<void>(
                         v65,
                         v72,
                         v71) == v65 )
      {
        v68 = &a3[6 * i];
        if ( !*(_QWORD *)utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,UdmChatParticipant const *>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,UdmChatParticipant const *>>,0>::emplace<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> &,UdmChatParticipant const *,0>(
                           v65,
                           v73,
                           v71,
                           &v68) )
        {
          Log_HREvent(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            2752);
          utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v71);
          tlx::_UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___::__UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___(v64);
          v29 = v66;
          if ( v66 != v65 )
          {
            while ( 1 )
            {
              v30 = (void **)v29[1];
              if ( v30 == &utl::_TreeSentinel )
              {
                while ( 1 )
                {
                  v30 = (void **)v29[2];
                  if ( v30 != &utl::_TreeSentinel )
                    break;
                  do
                  {
                    v31 = (__int64)v29;
                    v29 = (_QWORD *)(*v29 & 0xFFFFFFFFFFFFFFFEuLL);
                    utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
                      v28,
                      v31);
                    if ( v29 == v65 )
                      return 2147942414LL;
                  }
                  while ( (void **)v29[1] == &utl::_TreeSentinel );
                  v29[1] = &utl::_TreeSentinel;
                }
              }
              v29 = v30;
            }
          }
          return 2147942414LL;
        }
      }
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v71);
    }
    v40 = 0;
    v41 = 0;
    if ( v67 && v67 < v8 )
    {
      v41 = v67;
      v40 = (Udm *)operator new[](saturated_mul((unsigned int)v67, 0x30u));
      if ( !v40 )
      {
        Log_HREvent(
          2147942414LL,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
          2761);
        tlx::_UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___::__UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___(v64);
        v61 = v66;
        if ( v66 != v65 )
        {
          while ( 1 )
          {
            v62 = (void **)v61[1];
            if ( v62 == &utl::_TreeSentinel )
            {
              while ( 1 )
              {
                v62 = (void **)v61[2];
                if ( v62 != &utl::_TreeSentinel )
                  break;
                do
                {
                  v63 = (__int64)v61;
                  v61 = (_QWORD *)(*v61 & 0xFFFFFFFFFFFFFFFEuLL);
                  utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
                    v60,
                    v63);
                  if ( v61 == v65 )
                    return 2147942414LL;
                }
                while ( (void **)v61[1] == &utl::_TreeSentinel );
                v61[1] = &utl::_TreeSentinel;
              }
            }
            v61 = v62;
          }
        }
        return 2147942414LL;
      }
      v42 = v66;
      v43 = 0;
      while ( v42 != v65 )
      {
        v44 = (_OWORD *)v42[7];
        v45 = v44[1];
        v46 = v44[2];
        v47 = (_OWORD *)((char *)v40 + 48 * v43);
        *v47 = *v44;
        v47[1] = v45;
        v47[2] = v46;
        *(_QWORD *)v47 = 0;
        v48 = DupString(v47, *(_QWORD *)v42[7]);
        v50 = v48;
        if ( v48 < 0 )
        {
          Log_HREvent(
            (unsigned int)v48,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
            2768);
          tlx::_UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___::__UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___(v64);
          v53 = v66;
          if ( v66 != v65 )
          {
            while ( 1 )
            {
              v54 = (void **)v53[1];
              if ( v54 == &utl::_TreeSentinel )
                break;
LABEL_67:
              v53 = v54;
            }
LABEL_63:
            v54 = (void **)v53[2];
            if ( v54 != &utl::_TreeSentinel )
              goto LABEL_67;
            while ( 1 )
            {
              v55 = (__int64)v53;
              v53 = (_QWORD *)(*v53 & 0xFFFFFFFFFFFFFFFEuLL);
              utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
                v52,
                v55);
              if ( v53 == v65 )
                break;
              if ( (void **)v53[1] != &utl::_TreeSentinel )
              {
                v53[1] = &utl::_TreeSentinel;
                goto LABEL_63;
              }
            }
            v67 = 0;
            v65[0] = v65;
            v65[1] = v65;
            v66 = v65;
          }
          Udm::FreeUdmChatParticipant(v40, v51);
          return v50;
        }
        LOBYTE(v49) = 1;
        v42 = (_QWORD *)utl::_TreeNodeHeader<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,UdmChatParticipant const *>>::_Traverse(
                          v42,
                          v49);
        ++v43;
      }
      *a4 = 1;
    }
    *v69 = v41;
    *v70 = v40;
    tlx::_UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___::__UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___(v64);
    v57 = v66;
    if ( v66 != v65 )
    {
      while ( 1 )
      {
        v58 = (void **)v57[1];
        if ( v58 == &utl::_TreeSentinel )
        {
          while ( 1 )
          {
            v58 = (void **)v57[2];
            if ( v58 != &utl::_TreeSentinel )
              break;
            do
            {
              v59 = (__int64)v57;
              v57 = (_QWORD *)(*v57 & 0xFFFFFFFFFFFFFFFEuLL);
              utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
                v56,
                v59);
              if ( v57 == v65 )
                return 0;
            }
            while ( (void **)v57[1] == &utl::_TreeSentinel );
            v57[1] = &utl::_TreeSentinel;
          }
        }
        v57 = v58;
      }
    }
    return 0;
  }
  Log_HREvent(
    (unsigned int)v9,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\chatcontext.cpp",
    2727);
  v12 = v66;
  if ( v66 == v65 )
    return v10;
  while ( 1 )
  {
    v13 = (void **)v12[1];
    if ( v13 != &utl::_TreeSentinel )
      goto LABEL_8;
LABEL_4:
    v13 = (void **)v12[2];
    if ( v13 == &utl::_TreeSentinel )
      break;
LABEL_8:
    v12 = v13;
  }
  while ( 1 )
  {
    v14 = (__int64)v12;
    v12 = (_QWORD *)(*v12 & 0xFFFFFFFFFFFFFFFEuLL);
    utl::_ContainerBase<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>(
      v11,
      v14);
    if ( v12 == v65 )
      return v10;
    if ( (void **)v12[1] != &utl::_TreeSentinel )
    {
      v12[1] = &utl::_TreeSentinel;
      goto LABEL_4;
    }
  }
}

```

## disassembly

```asm
0x18006e770  mov     [rsp-8+arg_0], rbx
0x18006e775  push    rbp
0x18006e776  push    rsi
0x18006e777  push    rdi
0x18006e778  push    r12
0x18006e77a  push    r13
0x18006e77c  push    r14
0x18006e77e  push    r15
0x18006e780  lea     rbp, [rsp-190h]
0x18006e788  sub     rsp, 290h
0x18006e78f  mov     rax, cs:__security_cookie
0x18006e796  xor     rax, rsp
0x18006e799  mov     [rbp+1C0h+var_40], rax
0x18006e7a0  mov     rax, [rbp+1C0h+arg_20]
0x18006e7a7  lea     rcx, [rsp+2C0h+var_288]
0x18006e7ac  mov     [rsp+2C0h+var_260], rax
0x18006e7b1  mov     r13, r9
0x18006e7b4  mov     rax, [rbp+1C0h+arg_28]
0x18006e7bb  mov     r12, r8
0x18006e7be  mov     [rsp+2C0h+var_258], rax
0x18006e7c3  mov     edi, edx
0x18006e7c5  mov     dword ptr [r9], 0
0x18006e7cc  call    ??0?$map@KU_GUID@@U?$less@K@utl@@V?$allocator@U?$pair@$$CBKU_GUID@@@utl@@@3@@utl@@QEAA@XZ; utl::map<ulong,_GUID,utl::less<ulong>,utl::allocator<utl::pair<ulong const,_GUID>>>::map<ulong,_GUID,utl::less<ulong>,utl::allocator<utl::pair<ulong const,_GUID>>>(void)
0x18006e7d1  xor     edx, edx; Val
0x18006e7d3  lea     rcx, [rbp+1C0h+var_C0]; void *
0x18006e7da  mov     r8d, 80h; Size
0x18006e7e0  call    memset_0
0x18006e7e5  call    cs:__imp_PhoneAPIInitialize
0x18006e7eb  mov     r14d, eax
0x18006e7ee  test    eax, eax
0x18006e7f0  jns     short loc_18006E865
0x18006e7f2  mov     r9d, 0AA7h
0x18006e7f8  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006e7ff  mov     edx, 1
0x18006e804  mov     ecx, eax
0x18006e806  call    Log_HREvent
0x18006e80b  mov     rbx, [rsp+2C0h+var_278]
0x18006e810  lea     rax, [rsp+2C0h+var_288]
0x18006e815  cmp     rbx, rax
0x18006e818  jz      short loc_18006E85D
0x18006e81a  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18006e821  mov     rax, [rbx+8]
0x18006e825  cmp     rax, rdi
0x18006e828  jnz     short loc_18006E858
0x18006e82a  mov     rax, [rbx+10h]
0x18006e82e  cmp     rax, rdi
0x18006e831  jnz     short loc_18006E858
0x18006e833  mov     rdx, rbx
0x18006e836  mov     rbx, [rbx]
0x18006e839  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006e83d  call    ??$_DeleteNode@U?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *)
0x18006e842  lea     rax, [rsp+2C0h+var_288]
0x18006e847  cmp     rbx, rax
0x18006e84a  jz      short loc_18006E85D
0x18006e84c  cmp     [rbx+8], rdi
0x18006e850  jz      short loc_18006E833
0x18006e852  mov     [rbx+8], rdi
0x18006e856  jmp     short loc_18006E82A
0x18006e858  mov     rbx, rax
0x18006e85b  jmp     short loc_18006E821
0x18006e85d  mov     eax, r14d
0x18006e860  jmp     loc_18006EE36
0x18006e865  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18006e86c  mov     esi, 1
0x18006e871  lea     rcx, [rbp+1C0h+var_218]
0x18006e875  mov     [rsp+2C0h+var_28F], sil
0x18006e87a  movdqu  xmmword ptr [rbp+1C0h+var_218.Data1], xmm0
0x18006e87f  call    cs:__imp_PhoneGetDefaultOutgoingLine
0x18006e885  mov     r14d, eax
0x18006e888  test    eax, eax
0x18006e88a  jns     short loc_18006E902
0x18006e88c  mov     r9d, 0AADh
0x18006e892  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006e899  mov     edx, esi
0x18006e89b  mov     ecx, eax
0x18006e89d  call    Log_HREvent
0x18006e8a2  lea     rcx, [rsp+2C0h+var_290]
0x18006e8a7  call    tlx___UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945_______UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___
0x18006e8ac  mov     rbx, [rsp+2C0h+var_278]
0x18006e8b1  lea     rax, [rsp+2C0h+var_288]
0x18006e8b6  cmp     rbx, rax
0x18006e8b9  jz      short loc_18006E85D
0x18006e8bb  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18006e8c2  mov     rax, [rbx+8]
0x18006e8c6  cmp     rax, rdi
0x18006e8c9  jnz     short loc_18006E8FD
0x18006e8cb  mov     rax, [rbx+10h]
0x18006e8cf  cmp     rax, rdi
0x18006e8d2  jnz     short loc_18006E8FD
0x18006e8d4  mov     rdx, rbx
0x18006e8d7  mov     rbx, [rbx]
0x18006e8da  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006e8de  call    ??$_DeleteNode@U?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *)
0x18006e8e3  lea     rax, [rsp+2C0h+var_288]
0x18006e8e8  cmp     rbx, rax
0x18006e8eb  jz      loc_18006E85D
0x18006e8f1  cmp     [rbx+8], rdi
0x18006e8f5  jz      short loc_18006E8D4
0x18006e8f7  mov     [rbx+8], rdi
0x18006e8fb  jmp     short loc_18006E8CB
0x18006e8fd  mov     rbx, rax
0x18006e900  jmp     short loc_18006E8C2
0x18006e902  xor     edx, edx; Val
0x18006e904  lea     rcx, [rbp+1C0h+var_200]; void *
0x18006e908  mov     r8d, 13Ch; Size
0x18006e90e  call    memset_0
0x18006e913  lea     rdx, [rbp+1C0h+var_200]
0x18006e917  lea     rcx, [rbp+1C0h+var_218]
0x18006e91b  call    cs:__imp_PhoneGetProviderLineServiceInfo
0x18006e921  mov     r14d, eax
0x18006e924  test    eax, eax
0x18006e926  jns     short loc_18006E9A2
0x18006e928  mov     r9d, 0AB0h
0x18006e92e  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006e935  mov     edx, esi
0x18006e937  mov     ecx, eax
0x18006e939  call    Log_HREvent
0x18006e93e  lea     rcx, [rsp+2C0h+var_290]
0x18006e943  call    tlx___UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945_______UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___
0x18006e948  mov     rbx, [rsp+2C0h+var_278]
0x18006e94d  lea     rax, [rsp+2C0h+var_288]
0x18006e952  cmp     rbx, rax
0x18006e955  jz      loc_18006E85D
0x18006e95b  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18006e962  mov     rax, [rbx+8]
0x18006e966  cmp     rax, rdi
0x18006e969  jnz     short loc_18006E99D
0x18006e96b  mov     rax, [rbx+10h]
0x18006e96f  cmp     rax, rdi
0x18006e972  jnz     short loc_18006E99D
0x18006e974  mov     rdx, rbx
0x18006e977  mov     rbx, [rbx]
0x18006e97a  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006e97e  call    ??$_DeleteNode@U?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *)
0x18006e983  lea     rax, [rsp+2C0h+var_288]
0x18006e988  cmp     rbx, rax
0x18006e98b  jz      loc_18006E85D
0x18006e991  cmp     [rbx+8], rdi
0x18006e995  jz      short loc_18006E974
0x18006e997  mov     [rbx+8], rdi
0x18006e99b  jmp     short loc_18006E96B
0x18006e99d  mov     rbx, rax
0x18006e9a0  jmp     short loc_18006E962
0x18006e9a2  xor     ebx, ebx
0x18006e9a4  cmp     ebx, edi
0x18006e9a6  jnb     loc_18006EBE3
0x18006e9ac  lea     rcx, [rsp+2C0h+var_250]; void *
0x18006e9b1  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18006e9b6  lea     r15, [rbx+rbx*2]
0x18006e9ba  mov     r9d, 40h ; '@'
0x18006e9c0  shl     r15, 4
0x18006e9c4  lea     r8, [rbp+1C0h+var_C0]
0x18006e9cb  add     r15, r12
0x18006e9ce  lea     rdx, [rbp+1C0h+var_180]
0x18006e9d2  mov     rcx, [r15]
0x18006e9d5  call    cs:__imp_?GetTelUriFromDialString@@YAJPEBG0PEAGI@Z; GetTelUriFromDialString(ushort const *,ushort const *,ushort *,uint)
0x18006e9db  mov     r14d, eax
0x18006e9de  test    eax, eax
0x18006e9e0  js      loc_18006EB5E
0x18006e9e6  lea     rdx, [rbp+1C0h+var_C0]
0x18006e9ed  lea     rcx, [rsp+2C0h+var_250]
0x18006e9f2  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18006e9f7  test    al, al
0x18006e9f9  jz      loc_18006EAD7
0x18006e9ff  lea     r8, [rsp+2C0h+var_250]
0x18006ea04  lea     rdx, [rbp+1C0h+var_230]
0x18006ea08  lea     rcx, [rsp+2C0h+var_288]
0x18006ea0d  call    ??$find@X@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUUdmChatParticipant@@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUUdmChatParticipant@@@utl@@@2@$0A@@utl@@QEAA?AV?$_TreeIt@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUUdmChatParticipant@@@utl@@@1@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,UdmChatParticipant const *>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,UdmChatParticipant const *>>,0>::find<void>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x18006ea12  lea     rcx, [rsp+2C0h+var_288]
0x18006ea17  cmp     [rax], rcx
0x18006ea1a  jnz     short loc_18006EA3F
0x18006ea1c  lea     r9, [rsp+2C0h+var_268]
0x18006ea21  mov     [rsp+2C0h+var_268], r15
0x18006ea26  lea     r8, [rsp+2C0h+var_250]
0x18006ea2b  lea     rdx, [rbp+1C0h+var_228]
0x18006ea2f  lea     rcx, [rsp+2C0h+var_288]
0x18006ea34  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUUdmChatParticipant@@$0A@@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUUdmChatParticipant@@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUUdmChatParticipant@@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBUUdmChatParticipant@@@utl@@@utl@@_N@1@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@$$QEAPEBUUdmChatParticipant@@@Z; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,UdmChatParticipant const *>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,UdmChatParticipant const *>>,0>::emplace<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,UdmChatParticipant const *,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,UdmChatParticipant const * &&)
0x18006ea39  cmp     qword ptr [rax], 0
0x18006ea3d  jz      short loc_18006EA50
0x18006ea3f  lea     rcx, [rsp+2C0h+var_250]; void *
0x18006ea44  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18006ea49  add     ebx, esi
0x18006ea4b  jmp     loc_18006E9A4
0x18006ea50  mov     r9d, 0AC0h
0x18006ea56  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006ea5d  xor     edx, edx
0x18006ea5f  mov     ecx, 8007000Eh
0x18006ea64  call    Log_HREvent
0x18006ea69  lea     rcx, [rsp+2C0h+var_250]; void *
0x18006ea6e  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18006ea73  lea     rcx, [rsp+2C0h+var_290]
0x18006ea78  call    tlx___UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945_______UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___
0x18006ea7d  mov     rbx, [rsp+2C0h+var_278]
0x18006ea82  lea     rax, [rsp+2C0h+var_288]
0x18006ea87  cmp     rbx, rax
0x18006ea8a  jz      loc_18006EE25
0x18006ea90  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18006ea97  mov     rax, [rbx+8]
0x18006ea9b  cmp     rax, rdi
0x18006ea9e  jnz     short loc_18006EAD2
0x18006eaa0  mov     rax, [rbx+10h]
0x18006eaa4  cmp     rax, rdi
0x18006eaa7  jnz     short loc_18006EAD2
0x18006eaa9  mov     rdx, rbx
0x18006eaac  mov     rbx, [rbx]
0x18006eaaf  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006eab3  call    ??$_DeleteNode@U?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *)
0x18006eab8  lea     rax, [rsp+2C0h+var_288]
0x18006eabd  cmp     rbx, rax
0x18006eac0  jz      loc_18006EE25
0x18006eac6  cmp     [rbx+8], rdi
0x18006eaca  jz      short loc_18006EAA9
0x18006eacc  mov     [rbx+8], rdi
0x18006ead0  jmp     short loc_18006EAA0
0x18006ead2  mov     rbx, rax
0x18006ead5  jmp     short loc_18006EA97
0x18006ead7  mov     r9d, 0ABBh
0x18006eadd  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006eae4  xor     edx, edx
0x18006eae6  mov     ecx, 8007000Eh
0x18006eaeb  call    Log_HREvent
0x18006eaf0  lea     rcx, [rsp+2C0h+var_250]; void *
0x18006eaf5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18006eafa  lea     rcx, [rsp+2C0h+var_290]
0x18006eaff  call    tlx___UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945_______UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___
0x18006eb04  mov     rbx, [rsp+2C0h+var_278]
0x18006eb09  lea     rax, [rsp+2C0h+var_288]
0x18006eb0e  cmp     rbx, rax
0x18006eb11  jz      loc_18006EE25
0x18006eb17  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18006eb1e  mov     rax, [rbx+8]
0x18006eb22  cmp     rax, rdi
0x18006eb25  jnz     short loc_18006EB59
0x18006eb27  mov     rax, [rbx+10h]
0x18006eb2b  cmp     rax, rdi
0x18006eb2e  jnz     short loc_18006EB59
0x18006eb30  mov     rdx, rbx
0x18006eb33  mov     rbx, [rbx]
0x18006eb36  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006eb3a  call    ??$_DeleteNode@U?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *)
0x18006eb3f  lea     rax, [rsp+2C0h+var_288]
0x18006eb44  cmp     rbx, rax
0x18006eb47  jz      loc_18006EE25
0x18006eb4d  cmp     [rbx+8], rdi
0x18006eb51  jz      short loc_18006EB30
0x18006eb53  mov     [rbx+8], rdi
0x18006eb57  jmp     short loc_18006EB27
0x18006eb59  mov     rbx, rax
0x18006eb5c  jmp     short loc_18006EB1E
0x18006eb5e  mov     r9d, 0ABAh
0x18006eb64  lea     r8, aOnecoreuapBase_101; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18006eb6b  mov     edx, esi
0x18006eb6d  mov     ecx, r14d
0x18006eb70  call    Log_HREvent
0x18006eb75  lea     rcx, [rsp+2C0h+var_250]; void *
0x18006eb7a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18006eb7f  lea     rcx, [rsp+2C0h+var_290]
0x18006eb84  call    tlx___UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945_______UndoSolo__lambda_cc9c0a73a53d58ae66714645155bf945___
0x18006eb89  mov     rbx, [rsp+2C0h+var_278]
0x18006eb8e  lea     rax, [rsp+2C0h+var_288]
0x18006eb93  cmp     rbx, rax
0x18006eb96  jz      loc_18006E85D
0x18006eb9c  lea     rdi, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18006eba3  mov     rax, [rbx+8]
0x18006eba7  cmp     rax, rdi
0x18006ebaa  jnz     short loc_18006EBDE
0x18006ebac  mov     rax, [rbx+10h]
0x18006ebb0  cmp     rax, rdi
0x18006ebb3  jnz     short loc_18006EBDE
0x18006ebb5  mov     rdx, rbx
0x18006ebb8  mov     rbx, [rbx]
0x18006ebbb  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18006ebbf  call    ??$_DeleteNode@U?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::_DeleteNode<utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>(utl::_HashNode<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>> *)
0x18006ebc4  lea     rax, [rsp+2C0h+var_288]
0x18006ebc9  cmp     rbx, rax
0x18006ebcc  jz      loc_18006E85D
0x18006ebd2  cmp     [rbx+8], rdi
0x18006ebd6  jz      short loc_18006EBB5
0x18006ebd8  mov     [rbx+8], rdi
0x18006ebdc  jmp     short loc_18006EBAC
0x18006ebde  mov     rbx, rax
0x18006ebe1  jmp     short loc_18006EBA3
0x18006ebe3  mov     rcx, [rsp+2C0h+var_270]
0x18006ebe8  xor     ebx, ebx
0x18006ebea  xor     r14d, r14d
0x18006ebed  test    rcx, rcx
0x18006ebf0  jz      loc_18006ED39
0x18006ebf6  cmp     rcx, rdi
0x18006ebf9  jnb     loc_18006ED39
0x18006ebff  mov     r14d, ecx
0x18006ec02  lea     eax, [rbx+30h]
0x18006ec05  mul     r14
0x18006ec08  lea     rcx, [rbx-1]
0x18006ec0c  cmovb   rax, rcx
0x18006ec10  mov     rcx, rax; unsigned __int64
0x18006ec13  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006ec18  mov     rbx, rax
0x18006ec1b  test    rax, rax
0x18006ec1e  jz      loc_18006EDB0
0x18006ec24  mov     rdi, [rsp+2C0h+var_278]
  ... truncated ...
```
