# CUPnPAutomationProxy::GetInputArgumentNamesAndTypes(ushort *,ulong *,ushort * * *,ushort * * *)

- ea: `0x180029570`
- end: `0x18002999b`
- name: `?GetInputArgumentNamesAndTypes@CUPnPAutomationProxy@@UEAAJPEAGPEAKPEAPEAPEAG2@Z`
- size: `1067`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *this, unsigned __int16 *, unsigned int *, unsigned __int16 ***, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x18000e3ec`
- `0x180013180`
- `0x180029570`
- `0x180029a50`
- `0x18003ae80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002969b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002969b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800298d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002990d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800298d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002990d`
- `OLEAUT32!__imp_SysAllocString` at `0x180029708`
- `OLEAUT32!__imp_SysAllocString` at `0x180029724`
- `OLEAUT32!__imp_SysAllocString` at `0x180029708`
- `OLEAUT32!__imp_SysAllocString` at `0x180029724`
- `OLEAUT32!__imp_SysFreeString` at `0x1800298ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800298f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800298ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800298f6`

## string_xrefs

- `0x1800297b1`: `HrIsAllowedCOMCallLocality failed !`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::GetInputArgumentNamesAndTypes(
        CUPnPAutomationProxy *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 ***a4,
        unsigned __int16 ***a5)
{
  unsigned __int16 ***v5; // r13
  unsigned __int16 ***v8; // r12
  int IsAllowedCOMCallLocality; // eax
  unsigned int v10; // esi
  struct tagUPNP_ACTION *v11; // rax
  unsigned int v12; // ebp
  void *v13; // r15
  void *v14; // r14
  unsigned __int64 v15; // rcx
  STRSAFE_PCNZWCH v17; // rcx
  size_t v18; // rbx
  __int64 v19; // r13
  BSTR v20; // rax
  __int64 v21; // r9
  int v22; // edx
  const char *v23; // r9
  __int64 i; // rbx
  OLECHAR *v25; // rcx
  __int64 j; // rbx
  OLECHAR *v27; // rcx
  struct tagUPNP_ACTION *v28; // [rsp+78h] [rbp+10h]

  v5 = a4;
  if ( a2 )
  {
    if ( !a3 )
      return 2147500035LL;
    if ( !a4 )
      return 2147500035LL;
    v8 = a5;
    if ( !a5 )
      return 2147500035LL;
    IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
    v10 = IsAllowedCOMCallLocality;
    if ( IsAllowedCOMCallLocality < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_67;
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"HrIsAllowedCOMCallLocality failed !",
          IsAllowedCOMCallLocality);
        goto LABEL_66;
      }
      return v10;
    }
    if ( *((_DWORD *)this + 18) == 2 )
    {
      v11 = CUPnPAutomationProxy::LookupActionByName((CUPnPAutomationProxy *)((char *)this - 8), a2);
      v28 = v11;
      if ( v11 )
      {
        v12 = *((_DWORD *)v11 + 3);
        v13 = 0;
        v14 = 0;
        if ( v12 )
        {
          v15 = 8LL * v12;
          if ( v15 > 0xFFFFFFFF )
          {
            v10 = -2147024362;
LABEL_66:
            v17 = WPP_GLOBAL_Control;
            goto LABEL_67;
          }
          v18 = (unsigned int)v15;
          v13 = CoTaskMemAlloc((unsigned int)v15);
          v14 = CoTaskMemAlloc((unsigned int)v18);
          if ( v13 )
            memset_0(v13, 0, (unsigned int)v18);
          if ( v14 )
            memset_0(v14, 0, v18);
          if ( v13 && v14 )
          {
            v17 = WPP_GLOBAL_Control;
            v19 = 0;
            v10 = 0;
            while ( (unsigned int)v19 < v12 )
            {
              *((_QWORD *)v13 + v19) = SysAllocString(*(const OLECHAR **)(*((_QWORD *)v28 + 2) + 16LL
                                                                                               * (unsigned int)v19));
              v20 = SysAllocString(*(const OLECHAR **)(*(_QWORD *)(*((_QWORD *)v28 + 2) + 16LL * (unsigned int)v19 + 8)
                                                     + 8LL));
              *((_QWORD *)v14 + v19) = v20;
              v21 = *((_QWORD *)v13 + v19);
              if ( v21 && v20 )
              {
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
                {
                  WPP_SF_SS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    39,
                    (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                    v21,
                    (__int64)v20);
                  v17 = WPP_GLOBAL_Control;
                }
              }
              else
              {
                v10 = -2147024882;
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
                {
                  WPP_SF_sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    40,
                    (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                    (unsigned int)"CUPnPAutomationProxy::GetInputArgumentNamesAndTypes(): Failed to allocate argument name and/or type",
                    14);
                  v17 = WPP_GLOBAL_Control;
                  break;
                }
              }
              v19 = (unsigned int)(v19 + 1);
              if ( (v10 & 0x80000000) != 0 )
                break;
            }
            v5 = a4;
          }
          else
          {
            v10 = -2147024882;
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
              goto LABEL_49;
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              41,
              (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
              (unsigned int)"CUPnPAutomationProxy::GetInputArgumentNamesAndTypes(): Failed to allocate output arrays",
              14);
            v17 = WPP_GLOBAL_Control;
          }
          v8 = a5;
        }
        else
        {
          v17 = WPP_GLOBAL_Control;
        }
        if ( (v10 & 0x80000000) == 0 )
        {
          *a3 = v12;
          *v5 = (unsigned __int16 **)v13;
          *v8 = (unsigned __int16 **)v14;
          goto LABEL_16;
        }
LABEL_49:
        if ( v13 )
        {
          for ( i = 0; (unsigned int)i < v12; i = (unsigned int)(i + 1) )
          {
            v25 = (OLECHAR *)*((_QWORD *)v13 + i);
            if ( v25 )
            {
              SysFreeString(v25);
              *((_QWORD *)v13 + i) = 0;
            }
          }
          CoTaskMemFree(v13);
          v17 = WPP_GLOBAL_Control;
        }
        if ( !v14 )
        {
LABEL_17:
          if ( v10 )
          {
LABEL_67:
            if ( v17 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v17[14] & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)v17 + 2),
                43,
                (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                (unsigned int)"CUPnPAutomationProxy::GetInputArgumentNamesAndTypes(): Exiting",
                v10);
            return v10;
          }
          return v10;
        }
        for ( j = 0; (unsigned int)j < v12; j = (unsigned int)(j + 1) )
        {
          v27 = (OLECHAR *)*((_QWORD *)v14 + j);
          if ( v27 )
          {
            SysFreeString(v27);
            *((_QWORD *)v14 + j) = 0;
          }
        }
        CoTaskMemFree(v14);
LABEL_16:
        v17 = WPP_GLOBAL_Control;
        goto LABEL_17;
      }
      v10 = -2147220985;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        return v10;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_67;
      v22 = 42;
      v23 = "CUPnPAutomationProxy::GetIntputArgumentNamesAndTypes(): No such action";
    }
    else
    {
      v10 = -2147418113;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
        return v10;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_67;
      v22 = 38;
      v23 = "GetInputArgumentNamesAndTypes failed, CUPnPAutomationProxy is not initialized!";
    }
    WPP_SF_sd(
      *((_QWORD *)v17 + 2),
      v22,
      (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
      (_DWORD)v23,
      v10);
    goto LABEL_66;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180029570  mov     [rsp+arg_0], rbx
0x180029575  mov     [rsp+arg_18], r9
0x18002957a  mov     [rsp+arg_10], r8
0x18002957f  push    rbp
0x180029580  push    rsi
0x180029581  push    rdi
0x180029582  push    r12
0x180029584  push    r13
0x180029586  push    r14
0x180029588  push    r15
0x18002958a  sub     rsp, 30h
0x18002958e  mov     r13, r9
0x180029591  mov     rax, r8
0x180029594  mov     rbx, rdx
0x180029597  mov     rdi, rcx
0x18002959a  test    rdx, rdx
0x18002959d  jz      loc_180029784
0x1800295a3  test    rax, rax
0x1800295a6  jz      loc_180029635
0x1800295ac  test    r9, r9
0x1800295af  jz      loc_180029635
0x1800295b5  mov     r12, [rsp+68h+arg_20]
0x1800295bd  test    r12, r12
0x1800295c0  jz      short loc_180029635
0x1800295c2  mov     ecx, 1
0x1800295c7  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800295cc  lea     rbp, WPP_GLOBAL_Control
0x1800295d3  mov     esi, eax
0x1800295d5  test    eax, eax
0x1800295d7  js      loc_18002978E
0x1800295dd  mov     eax, [rdi+48h]
0x1800295e0  cmp     eax, 2
0x1800295e3  jnz     loc_1800297BD
0x1800295e9  lea     rcx, [rdi-8]; this
0x1800295ed  mov     rdx, rbx; unsigned __int16 *
0x1800295f0  call    ?LookupActionByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_ACTION@@PEBG@Z; CUPnPAutomationProxy::LookupActionByName(ushort const *)
0x1800295f5  mov     [rsp+68h+arg_8], rax
0x1800295fa  test    rax, rax
0x1800295fd  jz      loc_180029921
0x180029603  mov     ebp, [rax+0Ch]
0x180029606  xor     r15d, r15d
0x180029609  xor     r14d, r14d
0x18002960c  test    ebp, ebp
0x18002960e  jz      loc_18002989A
0x180029614  mov     ecx, ebp
0x180029616  mov     eax, 0FFFFFFFFh
0x18002961b  shl     rcx, 3
0x18002961f  cmp     rcx, rax
0x180029622  jbe     short loc_18002968C
0x180029624  mov     esi, 80070216h
0x180029629  lea     rbp, WPP_GLOBAL_Control
0x180029630  jmp     loc_18002995C
0x180029635  mov     eax, 80004003h
0x18002963a  jmp     short loc_180029677
0x18002963c  mov     r13, [rsp+68h+arg_18]
0x180029644  mov     r12, [rsp+68h+arg_20]
0x18002964c  test    esi, esi
0x18002964e  js      loc_1800298A6
0x180029654  mov     rax, [rsp+68h+arg_10]
0x18002965c  mov     [rax], ebp
0x18002965e  mov     [r13+0], r15
0x180029662  mov     [r12], r14
0x180029666  mov     rcx, cs:WPP_GLOBAL_Control
0x18002966d  test    esi, esi
0x18002966f  jnz     loc_180029918
0x180029675  mov     eax, esi
0x180029677  mov     rbx, [rsp+68h+arg_0]
0x18002967c  add     rsp, 30h
0x180029680  pop     r15
0x180029682  pop     r14
0x180029684  pop     r13
0x180029686  pop     r12
0x180029688  pop     rdi
0x180029689  pop     rsi
0x18002968a  pop     rbp
0x18002968b  retn
0x18002968c  mov     ebx, ecx
0x18002968e  mov     ecx, ecx; cb
0x180029690  call    cs:__imp_CoTaskMemAlloc
0x180029696  mov     ecx, ebx; cb
0x180029698  mov     r15, rax
0x18002969b  call    cs:__imp_CoTaskMemAlloc
0x1800296a1  mov     r14, rax
0x1800296a4  test    r15, r15
0x1800296a7  jz      short loc_1800296B6
0x1800296a9  mov     r8d, ebx; Size
0x1800296ac  xor     edx, edx; Val
0x1800296ae  mov     rcx, r15; void *
0x1800296b1  call    memset_0
0x1800296b6  test    r14, r14
0x1800296b9  jz      short loc_1800296C8
0x1800296bb  mov     r8, rbx; Size
0x1800296be  xor     edx, edx; Val
0x1800296c0  mov     rcx, r14; void *
0x1800296c3  call    memset_0
0x1800296c8  test    r15, r15
0x1800296cb  jz      loc_18002984B
0x1800296d1  test    r14, r14
0x1800296d4  jz      loc_18002984B
0x1800296da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296e1  xor     r13d, r13d
0x1800296e4  xor     esi, esi
0x1800296e6  mov     r12d, 8007000Eh
0x1800296ec  cmp     r13d, ebp
0x1800296ef  jnb     loc_18002963C
0x1800296f5  mov     rcx, [rsp+68h+arg_8]
0x1800296fa  mov     ebx, r13d
0x1800296fd  add     rbx, rbx
0x180029700  mov     rcx, [rcx+10h]
0x180029704  mov     rcx, [rcx+rbx*8]; psz
0x180029708  call    cs:__imp_SysAllocString
0x18002970e  mov     [r15+r13*8], rax
0x180029712  mov     rax, [rsp+68h+arg_8]
0x180029717  mov     rax, [rax+10h]
0x18002971b  mov     rcx, [rax+rbx*8+8]
0x180029720  mov     rcx, [rcx+8]; psz
0x180029724  call    cs:__imp_SysAllocString
0x18002972a  mov     [r14+r13*8], rax
0x18002972e  mov     r9, [r15+r13*8]
0x180029732  test    r9, r9
0x180029735  jz      loc_1800297FA
0x18002973b  test    rax, rax
0x18002973e  jz      loc_1800297FA
0x180029744  mov     rcx, cs:WPP_GLOBAL_Control
0x18002974b  lea     rdx, WPP_GLOBAL_Control
0x180029752  cmp     rcx, rdx
0x180029755  jz      short loc_18002975D
0x180029757  test    byte ptr [rcx+1Ch], 40h
0x18002975b  jnz     short loc_1800297D4
0x18002975d  inc     r13d
0x180029760  test    esi, esi
0x180029762  jns     short loc_1800296EC
0x180029764  jmp     loc_18002963C
0x180029769  test    byte ptr [rcx+1Ch], 1
0x18002976d  jz      loc_180029963
0x180029773  mov     edx, 26h ; '&'
0x180029778  lea     r9, aGetinputargume; "GetInputArgumentNamesAndTypes failed, C"...
0x18002977f  jmp     loc_180029948
0x180029784  mov     eax, 80070057h
0x180029789  jmp     loc_180029677
0x18002978e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029795  cmp     rcx, rbp
0x180029798  jz      loc_180029675
0x18002979e  test    byte ptr [rcx+1Ch], 1
0x1800297a2  jz      loc_180029963
0x1800297a8  mov     edx, 25h ; '%'
0x1800297ad  mov     dword ptr [rsp+68h+var_48], eax
0x1800297b1  lea     r9, aHrisallowedcom; "HrIsAllowedCOMCallLocality failed !"
0x1800297b8  jmp     loc_18002994C
0x1800297bd  mov     esi, 8000FFFFh
0x1800297c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297c9  cmp     rcx, rbp
0x1800297cc  jz      loc_180029675
0x1800297d2  jmp     short loc_180029769
0x1800297d4  mov     rcx, [rcx+10h]
0x1800297d8  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800297df  mov     edx, 27h ; '''
0x1800297e4  mov     [rsp+68h+var_48], rax
0x1800297e9  call    WPP_SF_SS
0x1800297ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297f5  jmp     loc_18002975D
0x1800297fa  mov     esi, r12d
0x1800297fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180029804  lea     rax, WPP_GLOBAL_Control
0x18002980b  cmp     rcx, rax
0x18002980e  jz      loc_18002975D
0x180029814  test    byte ptr [rcx+1Ch], 1
0x180029818  jz      loc_18002975D
0x18002981e  mov     rcx, [rcx+10h]
0x180029822  lea     r9, aCupnpautomatio_8; "CUPnPAutomationProxy::GetInputArgumentN"...
0x180029829  mov     edx, 28h ; '('
0x18002982e  mov     dword ptr [rsp+68h+var_48], r12d
0x180029833  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002983a  call    WPP_SF_sd
0x18002983f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029846  jmp     loc_18002963C
0x18002984b  mov     r12d, 8007000Eh
0x180029851  mov     esi, r12d
0x180029854  mov     rcx, cs:WPP_GLOBAL_Control
0x18002985b  lea     rax, WPP_GLOBAL_Control
0x180029862  cmp     rcx, rax
0x180029865  jz      short loc_1800298A6
0x180029867  test    byte ptr [rcx+1Ch], 1
0x18002986b  jz      short loc_1800298A6
0x18002986d  mov     rcx, [rcx+10h]
0x180029871  lea     r9, aCupnpautomatio_42; "CUPnPAutomationProxy::GetInputArgumentN"...
0x180029878  mov     edx, 29h ; ')'
0x18002987d  mov     dword ptr [rsp+68h+var_48], r12d
0x180029882  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180029889  call    WPP_SF_sd
0x18002988e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029895  jmp     loc_180029644
0x18002989a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298a1  jmp     loc_18002964C
0x1800298a6  test    r15, r15
0x1800298a9  jz      short loc_1800298DE
0x1800298ab  xor     ebx, ebx
0x1800298ad  test    ebp, ebp
0x1800298af  jz      short loc_1800298CE
0x1800298b1  mov     rcx, [r15+rbx*8]; bstrString
0x1800298b5  test    rcx, rcx
0x1800298b8  jz      short loc_1800298C8
0x1800298ba  call    cs:__imp_SysFreeString
0x1800298c0  mov     qword ptr [r15+rbx*8], 0
0x1800298c8  inc     ebx
0x1800298ca  cmp     ebx, ebp
0x1800298cc  jb      short loc_1800298B1
0x1800298ce  mov     rcx, r15; pv
0x1800298d1  call    cs:__imp_CoTaskMemFree
0x1800298d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800298de  test    r14, r14
0x1800298e1  jz      loc_18002966D
0x1800298e7  xor     ebx, ebx
0x1800298e9  test    ebp, ebp
0x1800298eb  jz      short loc_18002990A
0x1800298ed  mov     rcx, [r14+rbx*8]; bstrString
0x1800298f1  test    rcx, rcx
0x1800298f4  jz      short loc_180029904
0x1800298f6  call    cs:__imp_SysFreeString
0x1800298fc  mov     qword ptr [r14+rbx*8], 0
0x180029904  inc     ebx
0x180029906  cmp     ebx, ebp
0x180029908  jb      short loc_1800298ED
0x18002990a  mov     rcx, r14; pv
0x18002990d  call    cs:__imp_CoTaskMemFree
0x180029913  jmp     loc_180029666
0x180029918  lea     rbp, WPP_GLOBAL_Control
0x18002991f  jmp     short loc_180029963
0x180029921  mov     esi, 80040207h
0x180029926  mov     rcx, cs:WPP_GLOBAL_Control
0x18002992d  cmp     rcx, rbp
0x180029930  jz      loc_180029675
0x180029936  test    byte ptr [rcx+1Ch], 1
0x18002993a  jz      short loc_180029963
0x18002993c  mov     edx, 2Ah ; '*'
0x180029941  lea     r9, aCupnpautomatio_48; "CUPnPAutomationProxy::GetIntputArgument"...
0x180029948  mov     dword ptr [rsp+68h+var_48], esi
0x18002994c  mov     rcx, [rcx+10h]
0x180029950  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180029957  call    WPP_SF_sd
0x18002995c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029963  cmp     rcx, rbp
0x180029966  jz      loc_180029675
0x18002996c  test    byte ptr [rcx+1Ch], 1
0x180029970  jz      loc_180029675
0x180029976  mov     rcx, [rcx+10h]
0x18002997a  lea     r9, aCupnpautomatio_0; "CUPnPAutomationProxy::GetInputArgumentN"...
0x180029981  mov     edx, 2Bh ; '+'
0x180029986  mov     dword ptr [rsp+68h+var_48], esi
0x18002998a  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180029991  call    WPP_SF_sd
0x180029996  jmp     loc_180029675
```
