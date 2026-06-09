# IASSDOCreateItem(_ITEMTYPE,ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,IIASItem * *)

- ea: `0x18002844c`
- end: `0x18002910a`
- name: `?IASSDOCreateItem@@YAJW4_ITEMTYPE@@PEAUISdo@@1PEAUISdoMachine@@PEAUISdoDictionaryOld@@PEAPEAUIIASItem@@@Z`
- size: `3262`
- prototype: `int __high(enum _ITEMTYPE, struct ISdo *, struct ISdo *, struct ISdoMachine *, struct ISdoDictionaryOld *, struct IIASItem **)`
- caller_count: `11`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002fed0`
- `0x180030e10`
- `0x180030f40`
- `0x180031200`
- `0x1800317ec`
- `0x18003233c`
- `0x1800360c0`
- `0x180036eec`
- `0x180037180`
- `0x180037e30`
- `0x180038320`

## callees

- `0x180026c98`
- `0x180026db0`
- `0x180026ecc`
- `0x180026fe4`
- `0x180027100`
- `0x180027230`
- `0x180027348`
- `0x180027460`
- `0x180027584`
- `0x180027644`
- `0x18002844c`
- `0x18002cd00`
- `0x18002f904`
- `0x1800356fc`
- `0x1800370e4`
- `0x180040cd0`
- `0x180042a80`
- `0x180058010`

## string_xrefs

- `0x180028b19`: `pService->Initialize failed with 0x%x`
- `0x180029004`: `CreateInstance(pPolicy) failed with 0x%x`
- `0x180028ed3`: `CreateInstance(IASAttribute) failed with 0x%x`
- `0x18002888f`: `CreateInstance(IASServerGroup) failed with 0x%x`
- `0x18002875e`: `CreateInstance(IASRemoteServer) failed with 0x%x`
- `0x1800289bf`: `CreateInstance(IASClient) failed with 0x%x`
- `0x18002862d`: `CreateInstance(IASFileAccounting) failed with 0x%x`
- `0x1800284fc`: `CreateInstance(IASSQLAccounting) failed with 0x%x`
- `0x180028da2`: `CreateInstance(IASSharedSecret) failed with 0x%x`
- `0x180028c72`: `CreateInstance(IASIPFilter) failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASSDOCreateItem(
        int a1,
        struct ISdo *a2,
        struct ISdo *a3,
        struct ISdoMachine *a4,
        struct ISdoDictionaryOld *a5,
        __int64 a6)
{
  int Instance; // ebx
  int v11; // edx
  IASIPFilter *v12; // rdi
  IASIPFilter *v13; // rdi
  IASIPFilter *v14; // rdi
  IASIPFilter *v15; // rdi
  IASIPFilter *v16; // rdi
  IASIPFilter *v17; // rdi
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  IASIPFilter *v23; // rdi
  IASIPFilter *v24; // rdi
  IASIPFilter *v25; // rdi
  IASIPFilter *v26; // rdi
  int v28; // [rsp+28h] [rbp-20h]
  IASIPFilter *v29[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( a1 > 9 )
  {
    v18 = a1 - 10;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( !v19 || (v20 = v19 - 1) == 0 || (v21 = v20 - 2) == 0 )
      {
        v29[0] = 0;
        Instance = ATL::CComObject<IASAttribute>::CreateInstance(v29);
        if ( Instance >= 0 )
        {
          v25 = v29[0];
          Instance = IASItem::Initialize((IASIPFilter *)((char *)v29[0] + 16), a2, a3, a4, a5);
          if ( Instance >= 0 )
          {
            Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v25)(v25, &IID_IIASItem, a6);
            if ( Instance < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WppDbgPrint("QI(IIASItem) failed with 0x%x");
              v11 = 17;
              goto LABEL_166;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("Attrib::Initialize failed with 0x%x");
            v11 = 16;
            goto LABEL_166;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("CreateInstance(IASAttribute) failed with 0x%x");
          v11 = 15;
          goto LABEL_166;
        }
        return (unsigned int)Instance;
      }
      v22 = v21 - 4;
      if ( !v22 )
      {
        v29[0] = 0;
        Instance = ATL::CComObject<IASSharedSecret>::CreateInstance(v29);
        if ( Instance >= 0 )
        {
          v24 = v29[0];
          Instance = IASItem::Initialize((IASIPFilter *)((char *)v29[0] + 16), a2, a3, a4, a5);
          if ( Instance >= 0 )
          {
            Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v24)(v24, &IID_IIASItem, a6);
            if ( Instance < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WppDbgPrint("QI(IIASItem) failed with 0x%x, for pSecret");
              v11 = 35;
              goto LABEL_166;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pSecret::Initialize failed with 0x%x");
            v11 = 34;
            goto LABEL_166;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("CreateInstance(IASSharedSecret) failed with 0x%x");
          v11 = 33;
          goto LABEL_166;
        }
        return (unsigned int)Instance;
      }
      if ( v22 == 1 )
      {
        v29[0] = 0;
        Instance = ATL::CComObject<IASIPFilter>::CreateInstance(v29);
        if ( Instance >= 0 )
        {
          v23 = v29[0];
          Instance = IASIPFilter::Initialize(v29[0], a2, a3, a4, a5);
          if ( Instance >= 0 )
          {
            Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v23)(v23, &IID_IIASItem, a6);
            if ( Instance < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WppDbgPrint("QI(IIASItem) failed with 0x%x, for pIPFilter");
              v11 = 38;
              goto LABEL_166;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("pIPFilter::Initialize failed with 0x%x");
            v11 = 37;
            goto LABEL_166;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("CreateInstance(IASIPFilter) failed with 0x%x");
          v11 = 36;
          goto LABEL_166;
        }
        return (unsigned int)Instance;
      }
      goto LABEL_101;
    }
LABEL_151:
    v29[0] = 0;
    Instance = ATL::CComObject<IASPolicy>::CreateInstance(v29);
    if ( Instance >= 0 )
    {
      v28 = a1;
      v26 = v29[0];
      Instance = IASPolicy::Initialize(v29[0], a2, a3, a4, a5, v28);
      if ( Instance >= 0 )
      {
        Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v26)(v26, &IID_IIASItem, a6);
        if ( Instance < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("QI(IIASItem) failed with 0x%x");
          v11 = 14;
          goto LABEL_166;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("Policy::Initialize failed with 0x%x");
        v11 = 13;
        goto LABEL_166;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("CreateInstance(pPolicy) failed with 0x%x");
      v11 = 12;
      goto LABEL_166;
    }
    return (unsigned int)Instance;
  }
  switch ( a1 )
  {
    case 9:
      goto LABEL_151;
    case 1:
      v29[0] = 0;
      Instance = ATL::CComObject<IASService>::CreateInstance(v29);
      if ( Instance >= 0 )
      {
        v17 = v29[0];
        Instance = IASItem::Initialize((IASIPFilter *)((char *)v29[0] + 16), a2, a3, a4, a5);
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v17)(v17, &IID_IIASItem, a6);
          if ( Instance < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("QI(IID_IIASItem) failed with 0x%x");
            v11 = 11;
            goto LABEL_166;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pService->Initialize failed with 0x%x");
          v11 = 10;
          goto LABEL_166;
        }
      }
      return (unsigned int)Instance;
    case 2:
      v29[0] = 0;
      Instance = ATL::CComObject<IASClient>::CreateInstance(v29);
      if ( Instance >= 0 )
      {
        v16 = v29[0];
        Instance = IASItem::Initialize((IASIPFilter *)((char *)v29[0] + 16), a2, a3, a4, a5);
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v16)(v16, &IID_IIASItem, a6);
          if ( Instance < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("QI(IIASItem) failed with 0x%x");
            v11 = 26;
            goto LABEL_166;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pClient::Initialize failed with 0x%x");
          v11 = 25;
          goto LABEL_166;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("CreateInstance(IASClient) failed with 0x%x");
        v11 = 24;
        goto LABEL_166;
      }
      return (unsigned int)Instance;
    case 3:
      v29[0] = 0;
      Instance = ATL::CComObject<IASServerGroup>::CreateInstance(v29);
      if ( Instance >= 0 )
      {
        v15 = v29[0];
        Instance = IASServerGroup::Initialize(v29[0], a2, a3, a4, a5);
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v15)(v15, &IID_IIASItem, a6);
          if ( Instance < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("QI(IIASItem) failed with 0x%x");
            v11 = 20;
            goto LABEL_166;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pSrvGrp::Initialize failed with 0x%x");
          v11 = 19;
          goto LABEL_166;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("CreateInstance(IASServerGroup) failed with 0x%x");
        v11 = 18;
        goto LABEL_166;
      }
      return (unsigned int)Instance;
    case 5:
      v29[0] = 0;
      Instance = ATL::CComObject<IASRemoteServer>::CreateInstance(v29);
      if ( Instance >= 0 )
      {
        v14 = v29[0];
        Instance = IASItem::Initialize((IASIPFilter *)((char *)v29[0] + 16), a2, a3, a4, a5);
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v14)(v14, &IID_IIASItem, a6);
          if ( Instance < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("QI(IIASItem) failed with 0x%x");
            v11 = 23;
            goto LABEL_166;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pRemoteServer::Initialize failed with 0x%x");
          v11 = 22;
          goto LABEL_166;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("CreateInstance(IASRemoteServer) failed with 0x%x");
        v11 = 21;
        goto LABEL_166;
      }
      return (unsigned int)Instance;
    case 7:
      v29[0] = 0;
      Instance = ATL::CComObject<IASFileAccounting>::CreateInstance(v29);
      if ( Instance >= 0 )
      {
        v13 = v29[0];
        Instance = IASItem::Initialize((IASIPFilter *)((char *)v29[0] + 16), a2, a3, a4, a5);
        if ( Instance >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v13)(v13, &IID_IIASItem, a6);
          if ( Instance < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("QI(IIASItem) failed with 0x%x");
            v11 = 29;
            goto LABEL_166;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
               && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("pClient::Initialize failed with 0x%x");
          v11 = 28;
          goto LABEL_166;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("CreateInstance(IASFileAccounting) failed with 0x%x");
        v11 = 27;
        goto LABEL_166;
      }
      return (unsigned int)Instance;
  }
  if ( a1 != 8 )
  {
LABEL_101:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("Itemtype %d Not found");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)WPP_9723200e762c301790c48b34da45e129_Traceguids,
        (unsigned int)"NPSSDO",
        a1);
    }
    return (unsigned int)-2147418113;
  }
  v29[0] = 0;
  Instance = ATL::CComObject<IASSQLAccounting>::CreateInstance(v29);
  if ( Instance >= 0 )
  {
    v12 = v29[0];
    Instance = IASItem::Initialize((IASIPFilter *)((char *)v29[0] + 16), a2, a3, a4, a5);
    if ( Instance >= 0 )
    {
      Instance = (**(__int64 (__fastcall ***)(IASIPFilter *, GUID *, __int64))v12)(v12, &IID_IIASItem, a6);
      if ( Instance < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("QI(IIASItem) failed with 0x%x");
        v11 = 32;
        goto LABEL_166;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pClient::Initialize failed with 0x%x");
      v11 = 31;
      goto LABEL_166;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("CreateInstance(IASSQLAccounting) failed with 0x%x");
    v11 = 30;
LABEL_166:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_9723200e762c301790c48b34da45e129_Traceguids,
      (unsigned int)"NPSSDO",
      Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002844c  push    rbp
0x18002844e  push    rbx
0x18002844f  push    rsi
0x180028450  push    rdi
0x180028451  push    r14
0x180028453  push    r15
0x180028455  mov     rbp, rsp
0x180028458  sub     rsp, 48h
0x18002845c  mov     rsi, r9
0x18002845f  mov     r14, r8
0x180028462  mov     r15, rdx
0x180028465  mov     edi, ecx
0x180028467  cmp     ecx, 9
0x18002846a  jg      loc_180028B98
0x180028470  jz      loc_180028FBD
0x180028476  mov     r10d, ecx
0x180028479  sub     r10d, 1
0x18002847d  jz      loc_180028AA9
0x180028483  sub     r10d, 1
0x180028487  jz      loc_180028978
0x18002848d  sub     r10d, 1
0x180028491  jz      loc_180028848
0x180028497  sub     r10d, 2
0x18002849b  jz      loc_180028717
0x1800284a1  sub     r10d, 2
0x1800284a5  jz      loc_1800285E6
0x1800284ab  cmp     r10d, 1
0x1800284af  jnz     loc_180028BCA
0x1800284b5  lea     rcx, [rbp+var_18]
0x1800284b9  mov     [rbp+var_18], 0
0x1800284c1  call    ?CreateInstance@?$CComObject@VIASSQLAccounting@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASSQLAccounting>::CreateInstance(ATL::CComObject<IASSQLAccounting> * *)
0x1800284c6  mov     ebx, eax
0x1800284c8  test    eax, eax
0x1800284ca  jns     short loc_180028512
0x1800284cc  mov     rax, cs:WPP_GLOBAL_Control
0x1800284d3  lea     rcx, WPP_GLOBAL_Control
0x1800284da  cmp     rax, rcx
0x1800284dd  jz      loc_1800290FB
0x1800284e3  cmp     byte ptr [rax+19h], 2
0x1800284e7  jb      loc_1800290FB
0x1800284ed  test    dword ptr [rax+1Ch], 400h
0x1800284f4  jz      loc_1800290FB
0x1800284fa  mov     edx, ebx
0x1800284fc  lea     rcx, aCreateinstance_3; "CreateInstance(IASSQLAccounting) failed"...
0x180028503  call    WppDbgPrint
0x180028508  mov     edx, 1Eh
0x18002850d  jmp     loc_1800290D9
0x180028512  mov     rax, [rbp+arg_20]
0x180028516  mov     r9, rsi; struct ISdoMachine *
0x180028519  mov     rdi, [rbp+var_18]
0x18002851d  mov     r8, r14; struct ISdo *
0x180028520  mov     rdx, r15; struct ISdo *
0x180028523  mov     [rsp+48h+var_28], rax; struct ISdoDictionaryOld *
0x180028528  lea     rcx, [rdi+10h]; this
0x18002852c  call    ?Initialize@IASItem@@QEAAJPEAUISdo@@0PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASItem::Initialize(ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x180028531  mov     ebx, eax
0x180028533  test    eax, eax
0x180028535  jns     short loc_18002857D
0x180028537  mov     rax, cs:WPP_GLOBAL_Control
0x18002853e  lea     rcx, WPP_GLOBAL_Control
0x180028545  cmp     rax, rcx
0x180028548  jz      loc_1800290FB
0x18002854e  cmp     byte ptr [rax+19h], 2
0x180028552  jb      loc_1800290FB
0x180028558  test    dword ptr [rax+1Ch], 400h
0x18002855f  jz      loc_1800290FB
0x180028565  mov     edx, ebx
0x180028567  lea     rcx, aPclientInitial; "pClient::Initialize failed with 0x%x"
0x18002856e  call    WppDbgPrint
0x180028573  mov     edx, 1Fh
0x180028578  jmp     loc_1800290D9
0x18002857d  mov     rax, [rdi]
0x180028580  lea     rdx, IID_IIASItem
0x180028587  mov     r8, [rbp+arg_28]
0x18002858b  mov     rcx, rdi
0x18002858e  mov     rax, [rax]
0x180028591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028596  mov     ebx, eax
0x180028598  test    eax, eax
0x18002859a  jns     loc_1800290FB
0x1800285a0  mov     rax, cs:WPP_GLOBAL_Control
0x1800285a7  lea     rcx, WPP_GLOBAL_Control
0x1800285ae  cmp     rax, rcx
0x1800285b1  jz      loc_1800290FB
0x1800285b7  cmp     byte ptr [rax+19h], 2
0x1800285bb  jb      loc_1800290FB
0x1800285c1  test    dword ptr [rax+1Ch], 400h
0x1800285c8  jz      loc_1800290FB
0x1800285ce  mov     edx, ebx
0x1800285d0  lea     rcx, aQiIiasitemFail; "QI(IIASItem) failed with 0x%x"
0x1800285d7  call    WppDbgPrint
0x1800285dc  mov     edx, 20h ; ' '
0x1800285e1  jmp     loc_1800290D9
0x1800285e6  lea     rcx, [rbp+var_18]
0x1800285ea  mov     [rbp+var_18], 0
0x1800285f2  call    ?CreateInstance@?$CComObject@VIASFileAccounting@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASFileAccounting>::CreateInstance(ATL::CComObject<IASFileAccounting> * *)
0x1800285f7  mov     ebx, eax
0x1800285f9  test    eax, eax
0x1800285fb  jns     short loc_180028643
0x1800285fd  mov     rax, cs:WPP_GLOBAL_Control
0x180028604  lea     rcx, WPP_GLOBAL_Control
0x18002860b  cmp     rax, rcx
0x18002860e  jz      loc_1800290FB
0x180028614  cmp     byte ptr [rax+19h], 2
0x180028618  jb      loc_1800290FB
0x18002861e  test    dword ptr [rax+1Ch], 400h
0x180028625  jz      loc_1800290FB
0x18002862b  mov     edx, ebx
0x18002862d  lea     rcx, aCreateinstance_4; "CreateInstance(IASFileAccounting) faile"...
0x180028634  call    WppDbgPrint
0x180028639  mov     edx, 1Bh
0x18002863e  jmp     loc_1800290D9
0x180028643  mov     rax, [rbp+arg_20]
0x180028647  mov     r9, rsi; struct ISdoMachine *
0x18002864a  mov     rdi, [rbp+var_18]
0x18002864e  mov     r8, r14; struct ISdo *
0x180028651  mov     rdx, r15; struct ISdo *
0x180028654  mov     [rsp+48h+var_28], rax; struct ISdoDictionaryOld *
0x180028659  lea     rcx, [rdi+10h]; this
0x18002865d  call    ?Initialize@IASItem@@QEAAJPEAUISdo@@0PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASItem::Initialize(ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x180028662  mov     ebx, eax
0x180028664  test    eax, eax
0x180028666  jns     short loc_1800286AE
0x180028668  mov     rax, cs:WPP_GLOBAL_Control
0x18002866f  lea     rcx, WPP_GLOBAL_Control
0x180028676  cmp     rax, rcx
0x180028679  jz      loc_1800290FB
0x18002867f  cmp     byte ptr [rax+19h], 2
0x180028683  jb      loc_1800290FB
0x180028689  test    dword ptr [rax+1Ch], 400h
0x180028690  jz      loc_1800290FB
0x180028696  mov     edx, ebx
0x180028698  lea     rcx, aPclientInitial; "pClient::Initialize failed with 0x%x"
0x18002869f  call    WppDbgPrint
0x1800286a4  mov     edx, 1Ch
0x1800286a9  jmp     loc_1800290D9
0x1800286ae  mov     rax, [rdi]
0x1800286b1  lea     rdx, IID_IIASItem
0x1800286b8  mov     r8, [rbp+arg_28]
0x1800286bc  mov     rcx, rdi
0x1800286bf  mov     rax, [rax]
0x1800286c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286c7  mov     ebx, eax
0x1800286c9  test    eax, eax
0x1800286cb  jns     loc_1800290FB
0x1800286d1  mov     rax, cs:WPP_GLOBAL_Control
0x1800286d8  lea     rcx, WPP_GLOBAL_Control
0x1800286df  cmp     rax, rcx
0x1800286e2  jz      loc_1800290FB
0x1800286e8  cmp     byte ptr [rax+19h], 2
0x1800286ec  jb      loc_1800290FB
0x1800286f2  test    dword ptr [rax+1Ch], 400h
0x1800286f9  jz      loc_1800290FB
0x1800286ff  mov     edx, ebx
0x180028701  lea     rcx, aQiIiasitemFail; "QI(IIASItem) failed with 0x%x"
0x180028708  call    WppDbgPrint
0x18002870d  mov     edx, 1Dh
0x180028712  jmp     loc_1800290D9
0x180028717  lea     rcx, [rbp+var_18]
0x18002871b  mov     [rbp+var_18], 0
0x180028723  call    ?CreateInstance@?$CComObject@VIASRemoteServer@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASRemoteServer>::CreateInstance(ATL::CComObject<IASRemoteServer> * *)
0x180028728  mov     ebx, eax
0x18002872a  test    eax, eax
0x18002872c  jns     short loc_180028774
0x18002872e  mov     rax, cs:WPP_GLOBAL_Control
0x180028735  lea     rcx, WPP_GLOBAL_Control
0x18002873c  cmp     rax, rcx
0x18002873f  jz      loc_1800290FB
0x180028745  cmp     byte ptr [rax+19h], 2
0x180028749  jb      loc_1800290FB
0x18002874f  test    dword ptr [rax+1Ch], 400h
0x180028756  jz      loc_1800290FB
0x18002875c  mov     edx, ebx
0x18002875e  lea     rcx, aCreateinstance; "CreateInstance(IASRemoteServer) failed "...
0x180028765  call    WppDbgPrint
0x18002876a  mov     edx, 15h
0x18002876f  jmp     loc_1800290D9
0x180028774  mov     rax, [rbp+arg_20]
0x180028778  mov     r9, rsi; struct ISdoMachine *
0x18002877b  mov     rdi, [rbp+var_18]
0x18002877f  mov     r8, r14; struct ISdo *
0x180028782  mov     rdx, r15; struct ISdo *
0x180028785  mov     [rsp+48h+var_28], rax; struct ISdoDictionaryOld *
0x18002878a  lea     rcx, [rdi+10h]; this
0x18002878e  call    ?Initialize@IASItem@@QEAAJPEAUISdo@@0PEAUISdoMachine@@PEAUISdoDictionaryOld@@@Z; IASItem::Initialize(ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *)
0x180028793  mov     ebx, eax
0x180028795  test    eax, eax
0x180028797  jns     short loc_1800287DF
0x180028799  mov     rax, cs:WPP_GLOBAL_Control
0x1800287a0  lea     rcx, WPP_GLOBAL_Control
0x1800287a7  cmp     rax, rcx
0x1800287aa  jz      loc_1800290FB
0x1800287b0  cmp     byte ptr [rax+19h], 2
0x1800287b4  jb      loc_1800290FB
0x1800287ba  test    dword ptr [rax+1Ch], 400h
0x1800287c1  jz      loc_1800290FB
0x1800287c7  mov     edx, ebx
0x1800287c9  lea     rcx, aPremoteserverI; "pRemoteServer::Initialize failed with 0"...
0x1800287d0  call    WppDbgPrint
0x1800287d5  mov     edx, 16h
0x1800287da  jmp     loc_1800290D9
0x1800287df  mov     rax, [rdi]
0x1800287e2  lea     rdx, IID_IIASItem
0x1800287e9  mov     r8, [rbp+arg_28]
0x1800287ed  mov     rcx, rdi
0x1800287f0  mov     rax, [rax]
0x1800287f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287f8  mov     ebx, eax
0x1800287fa  test    eax, eax
0x1800287fc  jns     loc_1800290FB
0x180028802  mov     rax, cs:WPP_GLOBAL_Control
0x180028809  lea     rcx, WPP_GLOBAL_Control
0x180028810  cmp     rax, rcx
0x180028813  jz      loc_1800290FB
0x180028819  cmp     byte ptr [rax+19h], 2
0x18002881d  jb      loc_1800290FB
0x180028823  test    dword ptr [rax+1Ch], 400h
0x18002882a  jz      loc_1800290FB
0x180028830  mov     edx, ebx
0x180028832  lea     rcx, aQiIiasitemFail; "QI(IIASItem) failed with 0x%x"
0x180028839  call    WppDbgPrint
0x18002883e  mov     edx, 17h
0x180028843  jmp     loc_1800290D9
0x180028848  lea     rcx, [rbp+var_18]
0x18002884c  mov     [rbp+var_18], 0
0x180028854  call    ?CreateInstance@?$CComObject@VIASServerGroup@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASServerGroup>::CreateInstance(ATL::CComObject<IASServerGroup> * *)
0x180028859  mov     ebx, eax
0x18002885b  test    eax, eax
0x18002885d  jns     short loc_1800288A5
0x18002885f  mov     rax, cs:WPP_GLOBAL_Control
0x180028866  lea     rcx, WPP_GLOBAL_Control
0x18002886d  cmp     rax, rcx
0x180028870  jz      loc_1800290FB
0x180028876  cmp     byte ptr [rax+19h], 2
0x18002887a  jb      loc_1800290FB
0x180028880  test    dword ptr [rax+1Ch], 400h
0x180028887  jz      loc_1800290FB
0x18002888d  mov     edx, ebx
0x18002888f  lea     rcx, aCreateinstance_9; "CreateInstance(IASServerGroup) failed w"...
0x180028896  call    WppDbgPrint
0x18002889b  mov     edx, 12h
0x1800288a0  jmp     loc_1800290D9
0x1800288a5  mov     rax, [rbp+arg_20]
0x1800288a9  mov     r9, rsi
0x1800288ac  mov     rdi, [rbp+var_18]
0x1800288b0  mov     r8, r14
0x1800288b3  mov     rcx, rdi
0x1800288b6  mov     [rsp+48h+var_28], rax
0x1800288bb  mov     rdx, r15
0x1800288be  call    ?Initialize@IASServerGroup@@QEAAJPEAUISdo@@0PEAUISdoMachine@@PEAUISdoDictionaryOld@@W4_ITEMTYPE@@@Z; IASServerGroup::Initialize(ISdo *,ISdo *,ISdoMachine *,ISdoDictionaryOld *,_ITEMTYPE)
0x1800288c3  mov     ebx, eax
0x1800288c5  test    eax, eax
0x1800288c7  jns     short loc_18002890F
0x1800288c9  mov     rax, cs:WPP_GLOBAL_Control
0x1800288d0  lea     rcx, WPP_GLOBAL_Control
0x1800288d7  cmp     rax, rcx
0x1800288da  jz      loc_1800290FB
0x1800288e0  cmp     byte ptr [rax+19h], 2
0x1800288e4  jb      loc_1800290FB
0x1800288ea  test    dword ptr [rax+1Ch], 400h
0x1800288f1  jz      loc_1800290FB
0x1800288f7  mov     edx, ebx
0x1800288f9  lea     rcx, aPsrvgrpInitial; "pSrvGrp::Initialize failed with 0x%x"
0x180028900  call    WppDbgPrint
0x180028905  mov     edx, 13h
0x18002890a  jmp     loc_1800290D9
0x18002890f  mov     rax, [rdi]
0x180028912  lea     rdx, IID_IIASItem
0x180028919  mov     r8, [rbp+arg_28]
0x18002891d  mov     rcx, rdi
0x180028920  mov     rax, [rax]
0x180028923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028928  mov     ebx, eax
0x18002892a  test    eax, eax
0x18002892c  jns     loc_1800290FB
0x180028932  mov     rax, cs:WPP_GLOBAL_Control
0x180028939  lea     rcx, WPP_GLOBAL_Control
0x180028940  cmp     rax, rcx
0x180028943  jz      loc_1800290FB
0x180028949  cmp     byte ptr [rax+19h], 2
0x18002894d  jb      loc_1800290FB
0x180028953  test    dword ptr [rax+1Ch], 400h
0x18002895a  jz      loc_1800290FB
0x180028960  mov     edx, ebx
0x180028962  lea     rcx, aQiIiasitemFail; "QI(IIASItem) failed with 0x%x"
0x180028969  call    WppDbgPrint
0x18002896e  mov     edx, 14h
0x180028973  jmp     loc_1800290D9
0x180028978  lea     rcx, [rbp+var_18]
0x18002897c  mov     [rbp+var_18], 0
0x180028984  call    ?CreateInstance@?$CComObject@VIASClient@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<IASClient>::CreateInstance(ATL::CComObject<IASClient> * *)
0x180028989  mov     ebx, eax
0x18002898b  test    eax, eax
0x18002898d  jns     short loc_1800289D5
0x18002898f  mov     rax, cs:WPP_GLOBAL_Control
0x180028996  lea     rcx, WPP_GLOBAL_Control
0x18002899d  cmp     rax, rcx
0x1800289a0  jz      loc_1800290FB
0x1800289a6  cmp     byte ptr [rax+19h], 2
0x1800289aa  jb      loc_1800290FB
  ... truncated ...
```
