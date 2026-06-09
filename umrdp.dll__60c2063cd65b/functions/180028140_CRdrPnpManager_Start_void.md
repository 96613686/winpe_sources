# CRdrPnpManager::Start(void)

- ea: `0x180028140`
- end: `0x18002861e`
- name: `?Start@CRdrPnpManager@@UEAAJXZ`
- size: `1246`
- prototype: `__int64 __fastcall(CRdrPnpManager *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000abc0`
- `0x18000abf0`
- `0x18000b8f8`
- `0x18000b98c`
- `0x18000bd04`
- `0x18000f75c`
- `0x18001ba64`
- `0x180027900`
- `0x180028140`
- `0x180028698`
- `0x180028948`
- `0x180029320`
- `0x1800352bc`
- `0x180047ef0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800283e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800283e3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800283b9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800283b9`

## string_xrefs

- `0x1800281d5`: `CSessionThreadPool`
- `0x180028250`: `Failed to initialize pSessionThreadPool`
- `0x1800282a0`: `CreateComTsBus FAILED`
- `0x1800282f7`: `Unable to initialize TsComBus instance`
- `0x180028351`: `CreateBusEnumerator FAILED`
- `0x1800283b2`: `Microsoft.PointOfService.Management.Explorer`

## pseudocode

```c
__int64 __fastcall CRdrPnpManager::Start(CRdrPnpManager *this)
{
  _DWORD *v2; // rax
  __int64 v3; // rax
  unsigned int v4; // eax
  int Instance; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // eax
  void **v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rbx
  unsigned int v17; // eax
  LPVOID v18; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF
  GUID clsid; // [rsp+38h] [rbp-30h] BYREF

  ppv = 0;
  clsid = 0;
  v2 = operator new(0x30u);
  if ( v2 )
  {
    *v2 = 0;
    v2[4] = 0;
    *((_QWORD *)v2 + 1) = 0;
    *((_QWORD *)v2 + 3) = &CDynamicArray<CSessionThread>::`vftable';
    *((_QWORD *)v2 + 4) = 0;
    *((_QWORD *)v2 + 5) = 0;
  }
  else
  {
    v2 = 0;
  }
  *((_QWORD *)this + 15) = v2;
  if ( v2 )
  {
    Instance = CSessionThreadPool::Initialize((CSessionThreadPool *)v2);
    if ( Instance < 0 )
    {
      v3 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_64;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 16;
        v8 = "Failed to initialize pSessionThreadPool";
LABEL_62:
        WPP_SF_DsD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          v7,
          (unsigned int)WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v8,
          Instance);
        goto LABEL_63;
      }
      goto LABEL_69;
    }
    Instance = CComTsBus::CreateInstance((struct IComTsBus **)this + 13);
    if ( Instance < 0 )
    {
      v3 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_64;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 17;
        v8 = "CreateComTsBus FAILED";
        goto LABEL_62;
      }
LABEL_69:
      if ( *((_BYTE *)this + 112) )
      {
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 32LL))(*((_QWORD *)this + 13));
        if ( *((_QWORD *)this + 13) )
        {
          TCntPtr<IDispatch>::SafeRelease((char *)this + 104);
          *((_QWORD *)this + 13) = 0;
        }
        *((_BYTE *)this + 112) = 0;
      }
      CRdrPnpManager::Terminate((CRdrPnpManager *)((char *)this + 16));
      goto LABEL_74;
    }
    v9 = *((_QWORD *)this + 13);
    if ( !v9 )
    {
      Instance = -2147024882;
      v3 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(unsigned int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
        || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
      {
        goto LABEL_64;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        18,
        (unsigned int)WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
        v10,
        (__int64)"Unable to initialize TsComBus instance",
        14);
      goto LABEL_63;
    }
    Instance = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v9 + 24LL))(v9, L"TS_PNP_BUS");
    if ( Instance < 0 )
    {
      v3 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_64;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 19;
        v8 = "CreateBusEnumerator FAILED";
        goto LABEL_62;
      }
      goto LABEL_69;
    }
    *((_BYTE *)this + 112) = 1;
    if ( IsPOSRedirectionRegistryEnabled() )
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          20,
          WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
          v12);
      }
      if ( CLSIDFromProgID(L"Microsoft.PointOfService.Management.Explorer", &clsid) < 0 )
      {
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          v14 = 23;
          goto LABEL_50;
        }
      }
      else
      {
        if ( CoCreateInstance(&clsid, 0, 0x15u, &IID_IUnknown, &ppv) >= 0 )
        {
          Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))ppv)(ppv, &IID_IDispatch, (char *)this + 96);
          if ( Instance < 0 )
          {
            v3 = *(_QWORD *)&WPP_GLOBAL_Control;
            if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
                || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
              {
                goto LABEL_64;
              }
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v7 = 21;
              v8 = "failed to get IDispatch";
              goto LABEL_62;
            }
            goto LABEL_69;
          }
          goto LABEL_57;
        }
        if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
          && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          v14 = 22;
LABEL_50:
          WPP_SF_D(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
            v14,
            WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
            v13);
        }
      }
    }
    else
    {
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 4u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
          24,
          WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
          v15);
      }
      if ( *((_QWORD *)this + 12) )
      {
        TCntPtr<IDispatch>::SafeRelease((char *)this + 96);
        *((_QWORD *)this + 12) = 0;
      }
    }
LABEL_57:
    Instance = CRdrPnpManager::StartRpc(v11);
    if ( Instance < 0 )
    {
      v3 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) == 0
          || *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_64;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 25;
        v8 = "StartRpc FAILED";
        goto LABEL_62;
      }
      goto LABEL_69;
    }
LABEL_63:
    v3 = *(_QWORD *)&WPP_GLOBAL_Control;
    goto LABEL_64;
  }
  v3 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
    && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v4 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      15,
      (unsigned int)WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
      v4,
      (__int64)"CSessionThreadPool");
    v3 = *(_QWORD *)&WPP_GLOBAL_Control;
  }
  Instance = -2147024882;
LABEL_64:
  if ( (unsigned int *)v3 != &WPP_GLOBAL_Control && (*(_BYTE *)(v3 + 28) & 1) != 0 && *(_BYTE *)(v3 + 25) >= 4u )
  {
    v16 = *((_QWORD *)this + 12);
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dq(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
      26,
      WPP_94246e01360c359abb577584ca0bcde6_Traceguids,
      v17,
      v16);
  }
  if ( Instance )
    goto LABEL_69;
LABEL_74:
  v18 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180028140  mov     [rsp+arg_8], rbx
0x180028145  mov     [rsp+arg_10], rbp
0x18002814a  push    rsi
0x18002814b  push    rdi
0x18002814c  push    r14
0x18002814e  sub     rsp, 50h
0x180028152  mov     rax, cs:__security_cookie
0x180028159  xor     rax, rsp
0x18002815c  mov     [rsp+68h+var_20], rax
0x180028161  xor     ebp, ebp
0x180028163  mov     rsi, rcx
0x180028166  xorps   xmm0, xmm0
0x180028169  mov     [rsp+68h+var_38], rbp
0x18002816e  movups  xmmword ptr [rsp+68h+clsid.Data1], xmm0
0x180028173  lea     ecx, [rbp+30h]; Size
0x180028176  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002817b  test    rax, rax
0x18002817e  jz      short loc_18002819E
0x180028180  mov     [rax], ebp
0x180028182  lea     rcx, ??_7?$CDynamicArray@VCSessionThread@@@@6B@; const CDynamicArray<CSessionThread>::`vftable'
0x180028189  mov     [rax+10h], ebp
0x18002818c  mov     [rax+8], rbp
0x180028190  mov     [rax+18h], rcx
0x180028194  mov     [rax+20h], rbp
0x180028198  mov     [rax+28h], rbp
0x18002819c  jmp     short loc_1800281A1
0x18002819e  mov     rax, rbp
0x1800281a1  mov     [rsi+78h], rax
0x1800281a5  lea     r14, WPP_94246e01360c359abb577584ca0bcde6_Traceguids
0x1800281ac  test    rax, rax
0x1800281af  jnz     short loc_18002820D
0x1800281b1  mov     rax, cs:WPP_GLOBAL_Control
0x1800281b8  lea     rbx, WPP_GLOBAL_Control
0x1800281bf  cmp     rax, rbx
0x1800281c2  jz      short loc_180028203
0x1800281c4  test    byte ptr [rax+1Ch], 8
0x1800281c8  jz      short loc_180028203
0x1800281ca  cmp     byte ptr [rax+19h], 2
0x1800281ce  jb      short loc_180028203
0x1800281d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800281d5  lea     rcx, aCsessionthread_1; "CSessionThreadPool"
0x1800281dc  mov     edx, 0Fh
0x1800281e1  mov     [rsp+68h+ppv], rcx
0x1800281e6  mov     r9d, eax
0x1800281e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281f0  mov     r8, r14
0x1800281f3  mov     rcx, [rcx+10h]
0x1800281f7  call    WPP_SF_Ds
0x1800281fc  mov     rax, cs:WPP_GLOBAL_Control
0x180028203  mov     edi, 8007000Eh
0x180028208  jmp     loc_18002856B
0x18002820d  mov     rcx, rax; this
0x180028210  call    ?Initialize@CSessionThreadPool@@QEAAJXZ; CSessionThreadPool::Initialize(void)
0x180028215  mov     edi, eax
0x180028217  test    eax, eax
0x180028219  jns     short loc_18002825C
0x18002821b  mov     rax, cs:WPP_GLOBAL_Control
0x180028222  lea     rbx, WPP_GLOBAL_Control
0x180028229  cmp     rax, rbx
0x18002822c  jz      loc_1800285A9
0x180028232  test    byte ptr [rax+1Ch], 8
0x180028236  jz      loc_18002856B
0x18002823c  cmp     byte ptr [rax+19h], 2
0x180028240  jb      loc_18002856B
0x180028246  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002824b  mov     edx, 10h
0x180028250  lea     rcx, aFailedToInitia_1; "Failed to initialize pSessionThreadPool"
0x180028257  jmp     loc_180028545
0x18002825c  lea     rcx, [rsi+68h]; struct IComTsBus **
0x180028260  call    ?CreateInstance@CComTsBus@@SAJPEAPEAUIComTsBus@@@Z; CComTsBus::CreateInstance(IComTsBus * *)
0x180028265  mov     edi, eax
0x180028267  test    eax, eax
0x180028269  jns     short loc_1800282AC
0x18002826b  mov     rax, cs:WPP_GLOBAL_Control
0x180028272  lea     rbx, WPP_GLOBAL_Control
0x180028279  cmp     rax, rbx
0x18002827c  jz      loc_1800285A9
0x180028282  test    byte ptr [rax+1Ch], 8
0x180028286  jz      loc_18002856B
0x18002828c  cmp     byte ptr [rax+19h], 2
0x180028290  jb      loc_18002856B
0x180028296  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002829b  mov     edx, 11h
0x1800282a0  lea     rcx, aCreatecomtsbus; "CreateComTsBus FAILED"
0x1800282a7  jmp     loc_180028545
0x1800282ac  mov     rcx, [rsi+68h]
0x1800282b0  test    rcx, rcx
0x1800282b3  jnz     short loc_180028303
0x1800282b5  mov     edi, 8007000Eh
0x1800282ba  mov     rax, cs:WPP_GLOBAL_Control
0x1800282c1  lea     rbx, WPP_GLOBAL_Control
0x1800282c8  cmp     rax, rbx
0x1800282cb  jz      loc_1800285A9
0x1800282d1  test    byte ptr [rax+1Ch], 8
0x1800282d5  jz      loc_18002856B
0x1800282db  cmp     byte ptr [rax+19h], 2
0x1800282df  jb      loc_18002856B
0x1800282e5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800282ea  mov     edx, 12h
0x1800282ef  mov     [rsp+68h+var_40], 8007000Eh
0x1800282f7  lea     rcx, aUnableToInitia; "Unable to initialize TsComBus instance"
0x1800282fe  jmp     loc_180028549
0x180028303  mov     rax, [rcx]
0x180028306  lea     rdx, aTsPnpBus; "TS_PNP_BUS"
0x18002830d  mov     rax, [rax+18h]
0x180028311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028316  mov     edi, eax
0x180028318  test    eax, eax
0x18002831a  jns     short loc_18002835D
0x18002831c  mov     rax, cs:WPP_GLOBAL_Control
0x180028323  lea     rbx, WPP_GLOBAL_Control
0x18002832a  cmp     rax, rbx
0x18002832d  jz      loc_1800285A9
0x180028333  test    byte ptr [rax+1Ch], 8
0x180028337  jz      loc_18002856B
0x18002833d  cmp     byte ptr [rax+19h], 2
0x180028341  jb      loc_18002856B
0x180028347  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002834c  mov     edx, 13h
0x180028351  lea     rcx, aCreatebusenume; "CreateBusEnumerator FAILED"
0x180028358  jmp     loc_180028545
0x18002835d  mov     byte ptr [rsi+70h], 1
0x180028361  call    ?IsPOSRedirectionRegistryEnabled@@YA_NXZ; IsPOSRedirectionRegistryEnabled(void)
0x180028366  test    al, al
0x180028368  jz      loc_1800284BA
0x18002836e  mov     rax, cs:WPP_GLOBAL_Control
0x180028375  lea     rbx, WPP_GLOBAL_Control
0x18002837c  cmp     rax, rbx
0x18002837f  jz      short loc_1800283AD
0x180028381  test    byte ptr [rax+1Ch], 1
0x180028385  jz      short loc_1800283AD
0x180028387  cmp     byte ptr [rax+19h], 4
0x18002838b  jb      short loc_1800283AD
0x18002838d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028392  mov     rcx, cs:WPP_GLOBAL_Control
0x180028399  mov     edx, 14h
0x18002839e  mov     r9d, eax
0x1800283a1  mov     r8, r14
0x1800283a4  mov     rcx, [rcx+10h]
0x1800283a8  call    WPP_SF_D
0x1800283ad  lea     rdx, [rsp+68h+clsid]; lpclsid
0x1800283b2  lea     rcx, szProgID; "Microsoft.PointOfService.Management.Exp"...
0x1800283b9  call    cs:__imp_CLSIDFromProgID
0x1800283bf  test    eax, eax
0x1800283c1  js      loc_18002847C
0x1800283c7  xor     edx, edx; pUnkOuter
0x1800283c9  lea     rax, [rsp+68h+var_38]
0x1800283ce  lea     r9, IID_IUnknown; riid
0x1800283d5  mov     [rsp+68h+ppv], rax; ppv
0x1800283da  lea     rcx, [rsp+68h+clsid]; rclsid
0x1800283df  lea     r8d, [rdx+15h]; dwClsContext
0x1800283e3  call    cs:__imp_CoCreateInstance
0x1800283e9  test    eax, eax
0x1800283eb  js      short loc_18002844C
0x1800283ed  mov     rcx, [rsp+68h+var_38]
0x1800283f2  lea     r8, [rsi+60h]
0x1800283f6  lea     rdx, IID_IDispatch
0x1800283fd  mov     rax, [rcx]
0x180028400  mov     rax, [rax]
0x180028403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028408  mov     edi, eax
0x18002840a  test    eax, eax
0x18002840c  jns     loc_18002850D
0x180028412  mov     rax, cs:WPP_GLOBAL_Control
0x180028419  cmp     rax, rbx
0x18002841c  jz      loc_1800285A9
0x180028422  test    byte ptr [rax+1Ch], 8
0x180028426  jz      loc_18002856B
0x18002842c  cmp     byte ptr [rax+19h], 2
0x180028430  jb      loc_18002856B
0x180028436  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002843b  mov     edx, 15h
0x180028440  lea     rcx, aFailedToGetIdi; "failed to get IDispatch"
0x180028447  jmp     loc_180028545
0x18002844c  mov     rax, cs:WPP_GLOBAL_Control
0x180028453  cmp     rax, rbx
0x180028456  jz      loc_18002850D
0x18002845c  test    byte ptr [rax+1Ch], 1
0x180028460  jz      loc_18002850D
0x180028466  cmp     byte ptr [rax+19h], 2
0x18002846a  jb      loc_18002850D
0x180028470  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028475  mov     edx, 16h
0x18002847a  jmp     short loc_1800284A2
0x18002847c  mov     rax, cs:WPP_GLOBAL_Control
0x180028483  cmp     rax, rbx
0x180028486  jz      loc_18002850D
0x18002848c  test    byte ptr [rax+1Ch], 1
0x180028490  jz      short loc_18002850D
0x180028492  cmp     byte ptr [rax+19h], 4
0x180028496  jb      short loc_18002850D
0x180028498  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002849d  mov     edx, 17h
0x1800284a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284a9  mov     r9d, eax
0x1800284ac  mov     r8, r14
0x1800284af  mov     rcx, [rcx+10h]
0x1800284b3  call    WPP_SF_D
0x1800284b8  jmp     short loc_18002850D
0x1800284ba  mov     rax, cs:WPP_GLOBAL_Control
0x1800284c1  lea     rbx, WPP_GLOBAL_Control
0x1800284c8  cmp     rax, rbx
0x1800284cb  jz      short loc_1800284F9
0x1800284cd  test    byte ptr [rax+1Ch], 1
0x1800284d1  jz      short loc_1800284F9
0x1800284d3  cmp     byte ptr [rax+19h], 4
0x1800284d7  jb      short loc_1800284F9
0x1800284d9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800284de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284e5  mov     edx, 18h
0x1800284ea  mov     r9d, eax
0x1800284ed  mov     r8, r14
0x1800284f0  mov     rcx, [rcx+10h]
0x1800284f4  call    WPP_SF_D
0x1800284f9  lea     rdi, [rsi+60h]
0x1800284fd  cmp     [rdi], rbp
0x180028500  jz      short loc_18002850D
0x180028502  mov     rcx, rdi
0x180028505  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x18002850a  mov     [rdi], rbp
0x18002850d  call    ?StartRpc@CRdrPnpManager@@AEAAJXZ; CRdrPnpManager::StartRpc(void)
0x180028512  mov     edi, eax
0x180028514  test    eax, eax
0x180028516  jns     short loc_180028564
0x180028518  mov     rax, cs:WPP_GLOBAL_Control
0x18002851f  cmp     rax, rbx
0x180028522  jz      loc_1800285A9
0x180028528  test    byte ptr [rax+1Ch], 8
0x18002852c  jz      short loc_18002856B
0x18002852e  cmp     byte ptr [rax+19h], 2
0x180028532  jb      short loc_18002856B
0x180028534  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028539  mov     edx, 19h
0x18002853e  lea     rcx, aStartrpcFailed; "StartRpc FAILED"
0x180028545  mov     [rsp+68h+var_40], edi
0x180028549  mov     [rsp+68h+ppv], rcx
0x18002854e  mov     r9d, eax
0x180028551  mov     rcx, cs:WPP_GLOBAL_Control
0x180028558  mov     r8, r14
0x18002855b  mov     rcx, [rcx+10h]
0x18002855f  call    WPP_SF_DsD
0x180028564  mov     rax, cs:WPP_GLOBAL_Control
0x18002856b  cmp     rax, rbx
0x18002856e  jz      short loc_1800285A5
0x180028570  test    byte ptr [rax+1Ch], 1
0x180028574  jz      short loc_1800285A5
0x180028576  cmp     byte ptr [rax+19h], 4
0x18002857a  jb      short loc_1800285A5
0x18002857c  mov     rbx, [rsi+60h]
0x180028580  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180028585  mov     rcx, cs:WPP_GLOBAL_Control
0x18002858c  mov     edx, 1Ah
0x180028591  mov     r9d, eax
0x180028594  mov     [rsp+68h+ppv], rbx
0x180028599  mov     r8, r14
0x18002859c  mov     rcx, [rcx+10h]
0x1800285a0  call    WPP_SF_Dq
0x1800285a5  test    edi, edi
0x1800285a7  jz      short loc_1800285DF
0x1800285a9  cmp     [rsi+70h], bpl
0x1800285ad  jz      short loc_1800285D6
0x1800285af  lea     rbx, [rsi+68h]
0x1800285b3  mov     rcx, [rbx]
0x1800285b6  mov     rax, [rcx]
0x1800285b9  mov     rax, [rax+20h]
0x1800285bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285c2  cmp     [rbx], rbp
0x1800285c5  jz      short loc_1800285D2
0x1800285c7  mov     rcx, rbx
0x1800285ca  call    ?SafeRelease@?$TCntPtr@UIDispatch@@@@AEAAXXZ; TCntPtr<IDispatch>::SafeRelease(void)
0x1800285cf  mov     [rbx], rbp
0x1800285d2  mov     [rsi+70h], bpl
0x1800285d6  lea     rcx, [rsi+10h]; this
0x1800285da  call    ?Terminate@CRdrPnpManager@@UEAAJXZ; CRdrPnpManager::Terminate(void)
0x1800285df  mov     rcx, [rsp+68h+var_38]
0x1800285e4  test    rcx, rcx
0x1800285e7  jz      short loc_1800285FA
0x1800285e9  mov     [rsp+68h+var_38], rbp
0x1800285ee  mov     rax, [rcx]
0x1800285f1  mov     rax, [rax+10h]
0x1800285f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285fa  mov     eax, edi
0x1800285fc  mov     rcx, [rsp+68h+var_20]
0x180028601  xor     rcx, rsp; StackCookie
0x180028604  call    __security_check_cookie
0x180028609  lea     r11, [rsp+68h+var_18]
0x18002860e  mov     rbx, [r11+28h]
0x180028612  mov     rbp, [r11+30h]
0x180028616  mov     rsp, r11
0x180028619  pop     r14
0x18002861b  pop     rdi
0x18002861c  pop     rsi
0x18002861d  retn
```
