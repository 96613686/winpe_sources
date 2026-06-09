# CUPnPAutomationProxy::GetInputArgumentNamesAndTypes(ushort *,ulong *,ushort * * *,ushort * * *)

- ea: `0x18002a8b0`
- end: `0x18002ad10`
- name: `?GetInputArgumentNamesAndTypes@CUPnPAutomationProxy@@UEAAJPEAGPEAKPEAPEAPEAG2@Z`
- size: `1120`
- prototype: `int(CUPnPAutomationProxy *__hidden this, unsigned __int16 *, unsigned int *, unsigned __int16 ***, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x1800200f4`
- `0x1800209c8`
- `0x18002a8b0`
- `0x18002adc0`
- `0x18003d4b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a9d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a9e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a9d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a9e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac7c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa55`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa77`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa55`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aa77`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac17`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac17`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ac5f`

## string_xrefs

- `0x18002ab0e`: `HrIsAllowedCOMCallLocality failed !`

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
0x18002a8b0  mov     [rsp+arg_0], rbx
0x18002a8b5  mov     [rsp+arg_18], r9
0x18002a8ba  mov     [rsp+arg_10], r8
0x18002a8bf  push    rbp
0x18002a8c0  push    rsi
0x18002a8c1  push    rdi
0x18002a8c2  push    r12
0x18002a8c4  push    r13
0x18002a8c6  push    r14
0x18002a8c8  push    r15
0x18002a8ca  sub     rsp, 30h
0x18002a8ce  mov     r13, r9
0x18002a8d1  mov     rax, r8
0x18002a8d4  mov     rbx, rdx
0x18002a8d7  mov     rdi, rcx
0x18002a8da  test    rdx, rdx
0x18002a8dd  jz      loc_18002AAE1
0x18002a8e3  test    rax, rax
0x18002a8e6  jz      loc_18002A975
0x18002a8ec  test    r9, r9
0x18002a8ef  jz      loc_18002A975
0x18002a8f5  mov     r12, [rsp+68h+arg_20]
0x18002a8fd  test    r12, r12
0x18002a900  jz      short loc_18002A975
0x18002a902  mov     ecx, 1
0x18002a907  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18002a90c  lea     rbp, WPP_GLOBAL_Control
0x18002a913  mov     esi, eax
0x18002a915  test    eax, eax
0x18002a917  js      loc_18002AAEB
0x18002a91d  mov     eax, [rdi+48h]
0x18002a920  cmp     eax, 2
0x18002a923  jnz     loc_18002AB1A
0x18002a929  lea     rcx, [rdi-8]; this
0x18002a92d  mov     rdx, rbx; unsigned __int16 *
0x18002a930  call    ?LookupActionByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_ACTION@@PEBG@Z; CUPnPAutomationProxy::LookupActionByName(ushort const *)
0x18002a935  mov     [rsp+68h+arg_8], rax
0x18002a93a  test    rax, rax
0x18002a93d  jz      loc_18002AC96
0x18002a943  mov     ebp, [rax+0Ch]
0x18002a946  xor     r15d, r15d
0x18002a949  xor     r14d, r14d
0x18002a94c  test    ebp, ebp
0x18002a94e  jz      loc_18002ABF7
0x18002a954  mov     ecx, ebp
0x18002a956  mov     eax, 0FFFFFFFFh
0x18002a95b  shl     rcx, 3
0x18002a95f  cmp     rcx, rax
0x18002a962  jbe     short loc_18002A9CD
0x18002a964  mov     esi, 80070216h
0x18002a969  lea     rbp, WPP_GLOBAL_Control
0x18002a970  jmp     loc_18002ACD1
0x18002a975  mov     eax, 80004003h
0x18002a97a  jmp     short loc_18002A9B7
0x18002a97c  mov     r13, [rsp+68h+arg_18]
0x18002a984  mov     r12, [rsp+68h+arg_20]
0x18002a98c  test    esi, esi
0x18002a98e  js      loc_18002AC03
0x18002a994  mov     rax, [rsp+68h+arg_10]
0x18002a99c  mov     [rax], ebp
0x18002a99e  mov     [r13+0], r15
0x18002a9a2  mov     [r12], r14
0x18002a9a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a9ad  test    esi, esi
0x18002a9af  jnz     loc_18002AC8D
0x18002a9b5  mov     eax, esi
0x18002a9b7  mov     rbx, [rsp+68h+arg_0]
0x18002a9bc  add     rsp, 30h
0x18002a9c0  pop     r15
0x18002a9c2  pop     r14
0x18002a9c4  pop     r13
0x18002a9c6  pop     r12
0x18002a9c8  pop     rdi
0x18002a9c9  pop     rsi
0x18002a9ca  pop     rbp
0x18002a9cb  retn
0x18002a9cd  mov     ebx, ecx
0x18002a9cf  mov     ecx, ecx; cb
0x18002a9d1  call    cs:__imp_CoTaskMemAlloc
0x18002a9d8  nop     dword ptr [rax+rax+00h]
0x18002a9dd  mov     ecx, ebx; cb
0x18002a9df  mov     r15, rax
0x18002a9e2  call    cs:__imp_CoTaskMemAlloc
0x18002a9e9  nop     dword ptr [rax+rax+00h]
0x18002a9ee  mov     r14, rax
0x18002a9f1  test    r15, r15
0x18002a9f4  jz      short loc_18002AA03
0x18002a9f6  mov     r8d, ebx; Size
0x18002a9f9  xor     edx, edx; Val
0x18002a9fb  mov     rcx, r15; void *
0x18002a9fe  call    memset_0
0x18002aa03  test    r14, r14
0x18002aa06  jz      short loc_18002AA15
0x18002aa08  mov     r8, rbx; Size
0x18002aa0b  xor     edx, edx; Val
0x18002aa0d  mov     rcx, r14; void *
0x18002aa10  call    memset_0
0x18002aa15  test    r15, r15
0x18002aa18  jz      loc_18002ABA8
0x18002aa1e  test    r14, r14
0x18002aa21  jz      loc_18002ABA8
0x18002aa27  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa2e  xor     r13d, r13d
0x18002aa31  xor     esi, esi
0x18002aa33  mov     r12d, 8007000Eh
0x18002aa39  cmp     r13d, ebp
0x18002aa3c  jnb     loc_18002A97C
0x18002aa42  mov     rcx, [rsp+68h+arg_8]
0x18002aa47  mov     ebx, r13d
0x18002aa4a  add     rbx, rbx
0x18002aa4d  mov     rcx, [rcx+10h]
0x18002aa51  mov     rcx, [rcx+rbx*8]; psz
0x18002aa55  call    cs:__imp_SysAllocString
0x18002aa5c  nop     dword ptr [rax+rax+00h]
0x18002aa61  mov     [r15+r13*8], rax
0x18002aa65  mov     rax, [rsp+68h+arg_8]
0x18002aa6a  mov     rax, [rax+10h]
0x18002aa6e  mov     rcx, [rax+rbx*8+8]
0x18002aa73  mov     rcx, [rcx+8]; psz
0x18002aa77  call    cs:__imp_SysAllocString
0x18002aa7e  nop     dword ptr [rax+rax+00h]
0x18002aa83  mov     [r14+r13*8], rax
0x18002aa87  mov     r9, [r15+r13*8]
0x18002aa8b  test    r9, r9
0x18002aa8e  jz      loc_18002AB57
0x18002aa94  test    rax, rax
0x18002aa97  jz      loc_18002AB57
0x18002aa9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aaa4  lea     rdx, WPP_GLOBAL_Control
0x18002aaab  cmp     rcx, rdx
0x18002aaae  jz      short loc_18002AAB6
0x18002aab0  test    byte ptr [rcx+1Ch], 40h
0x18002aab4  jnz     short loc_18002AB31
0x18002aab6  inc     r13d
0x18002aab9  test    esi, esi
0x18002aabb  jns     loc_18002AA39
0x18002aac1  jmp     loc_18002A97C
0x18002aac6  test    byte ptr [rcx+1Ch], 1
0x18002aaca  jz      loc_18002ACD8
0x18002aad0  mov     edx, 26h ; '&'
0x18002aad5  lea     r9, aGetinputargume; "GetInputArgumentNamesAndTypes failed, C"...
0x18002aadc  jmp     loc_18002ACBD
0x18002aae1  mov     eax, 80070057h
0x18002aae6  jmp     loc_18002A9B7
0x18002aaeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aaf2  cmp     rcx, rbp
0x18002aaf5  jz      loc_18002A9B5
0x18002aafb  test    byte ptr [rcx+1Ch], 1
0x18002aaff  jz      loc_18002ACD8
0x18002ab05  mov     edx, 25h ; '%'
0x18002ab0a  mov     dword ptr [rsp+68h+var_48], eax
0x18002ab0e  lea     r9, aHrisallowedcom; "HrIsAllowedCOMCallLocality failed !"
0x18002ab15  jmp     loc_18002ACC1
0x18002ab1a  mov     esi, 8000FFFFh
0x18002ab1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab26  cmp     rcx, rbp
0x18002ab29  jz      loc_18002A9B5
0x18002ab2f  jmp     short loc_18002AAC6
0x18002ab31  mov     rcx, [rcx+10h]
0x18002ab35  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002ab3c  mov     edx, 27h ; '''
0x18002ab41  mov     [rsp+68h+var_48], rax
0x18002ab46  call    WPP_SF_SS
0x18002ab4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab52  jmp     loc_18002AAB6
0x18002ab57  mov     esi, r12d
0x18002ab5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab61  lea     rax, WPP_GLOBAL_Control
0x18002ab68  cmp     rcx, rax
0x18002ab6b  jz      loc_18002AAB6
0x18002ab71  test    byte ptr [rcx+1Ch], 1
0x18002ab75  jz      loc_18002AAB6
0x18002ab7b  mov     rcx, [rcx+10h]
0x18002ab7f  lea     r9, aCupnpautomatio_8; "CUPnPAutomationProxy::GetInputArgumentN"...
0x18002ab86  mov     edx, 28h ; '('
0x18002ab8b  mov     dword ptr [rsp+68h+var_48], r12d
0x18002ab90  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002ab97  call    WPP_SF_sd
0x18002ab9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aba3  jmp     loc_18002A97C
0x18002aba8  mov     r12d, 8007000Eh
0x18002abae  mov     esi, r12d
0x18002abb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abb8  lea     rax, WPP_GLOBAL_Control
0x18002abbf  cmp     rcx, rax
0x18002abc2  jz      short loc_18002AC03
0x18002abc4  test    byte ptr [rcx+1Ch], 1
0x18002abc8  jz      short loc_18002AC03
0x18002abca  mov     rcx, [rcx+10h]
0x18002abce  lea     r9, aCupnpautomatio_42; "CUPnPAutomationProxy::GetInputArgumentN"...
0x18002abd5  mov     edx, 29h ; ')'
0x18002abda  mov     dword ptr [rsp+68h+var_48], r12d
0x18002abdf  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002abe6  call    WPP_SF_sd
0x18002abeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abf2  jmp     loc_18002A984
0x18002abf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002abfe  jmp     loc_18002A98C
0x18002ac03  test    r15, r15
0x18002ac06  jz      short loc_18002AC47
0x18002ac08  xor     ebx, ebx
0x18002ac0a  test    ebp, ebp
0x18002ac0c  jz      short loc_18002AC31
0x18002ac0e  mov     rcx, [r15+rbx*8]; bstrString
0x18002ac12  test    rcx, rcx
0x18002ac15  jz      short loc_18002AC2B
0x18002ac17  call    cs:__imp_SysFreeString
0x18002ac1e  nop     dword ptr [rax+rax+00h]
0x18002ac23  mov     qword ptr [r15+rbx*8], 0
0x18002ac2b  inc     ebx
0x18002ac2d  cmp     ebx, ebp
0x18002ac2f  jb      short loc_18002AC0E
0x18002ac31  mov     rcx, r15; pv
0x18002ac34  call    cs:__imp_CoTaskMemFree
0x18002ac3b  nop     dword ptr [rax+rax+00h]
0x18002ac40  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac47  test    r14, r14
0x18002ac4a  jz      loc_18002A9AD
0x18002ac50  xor     ebx, ebx
0x18002ac52  test    ebp, ebp
0x18002ac54  jz      short loc_18002AC79
0x18002ac56  mov     rcx, [r14+rbx*8]; bstrString
0x18002ac5a  test    rcx, rcx
0x18002ac5d  jz      short loc_18002AC73
0x18002ac5f  call    cs:__imp_SysFreeString
0x18002ac66  nop     dword ptr [rax+rax+00h]
0x18002ac6b  mov     qword ptr [r14+rbx*8], 0
0x18002ac73  inc     ebx
0x18002ac75  cmp     ebx, ebp
0x18002ac77  jb      short loc_18002AC56
0x18002ac79  mov     rcx, r14; pv
0x18002ac7c  call    cs:__imp_CoTaskMemFree
0x18002ac83  nop     dword ptr [rax+rax+00h]
0x18002ac88  jmp     loc_18002A9A6
0x18002ac8d  lea     rbp, WPP_GLOBAL_Control
0x18002ac94  jmp     short loc_18002ACD8
0x18002ac96  mov     esi, 80040207h
0x18002ac9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aca2  cmp     rcx, rbp
0x18002aca5  jz      loc_18002A9B5
0x18002acab  test    byte ptr [rcx+1Ch], 1
0x18002acaf  jz      short loc_18002ACD8
0x18002acb1  mov     edx, 2Ah ; '*'
0x18002acb6  lea     r9, aCupnpautomatio_48; "CUPnPAutomationProxy::GetIntputArgument"...
0x18002acbd  mov     dword ptr [rsp+68h+var_48], esi
0x18002acc1  mov     rcx, [rcx+10h]
0x18002acc5  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002accc  call    WPP_SF_sd
0x18002acd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acd8  cmp     rcx, rbp
0x18002acdb  jz      loc_18002A9B5
0x18002ace1  test    byte ptr [rcx+1Ch], 1
0x18002ace5  jz      loc_18002A9B5
0x18002aceb  mov     rcx, [rcx+10h]
0x18002acef  lea     r9, aCupnpautomatio_0; "CUPnPAutomationProxy::GetInputArgumentN"...
0x18002acf6  mov     edx, 2Bh ; '+'
0x18002acfb  mov     dword ptr [rsp+68h+var_48], esi
0x18002acff  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002ad06  call    WPP_SF_sd
0x18002ad0b  jmp     loc_18002A9B5
```
