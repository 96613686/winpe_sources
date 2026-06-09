# CUPnPAutomationProxy::GetOutputArgumentNamesAndTypes(ushort *,ulong *,ushort * * *,ushort * * *)

- ea: `0x1800291a0`
- end: `0x18002955e`
- name: `?GetOutputArgumentNamesAndTypes@CUPnPAutomationProxy@@UEAAJPEAGPEAKPEAPEAPEAG2@Z`
- size: `958`
- prototype: `__int64 __fastcall(CUPnPAutomationProxy *this, unsigned __int16 *, unsigned int *, unsigned __int16 ***, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000db4c`
- `0x18000e3ec`
- `0x180013180`
- `0x1800291a0`
- `0x180029a50`
- `0x18003ae80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800292c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800292ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800292c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800292ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294c3`
- `OLEAUT32!__imp_SysAllocString` at `0x18002933c`
- `OLEAUT32!__imp_SysAllocString` at `0x180029358`
- `OLEAUT32!__imp_SysAllocString` at `0x18002933c`
- `OLEAUT32!__imp_SysAllocString` at `0x180029358`
- `OLEAUT32!__imp_SysFreeString` at `0x180029471`
- `OLEAUT32!__imp_SysFreeString` at `0x1800294ab`
- `OLEAUT32!__imp_SysFreeString` at `0x180029471`
- `OLEAUT32!__imp_SysFreeString` at `0x1800294ab`

## string_xrefs

- `0x18002922b`: `HrIsAllowedCOMCallLocality failed !`

## pseudocode

```c
__int64 __fastcall CUPnPAutomationProxy::GetOutputArgumentNamesAndTypes(
        CUPnPAutomationProxy *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 ***a4,
        unsigned __int16 ***a5)
{
  int IsAllowedCOMCallLocality; // eax
  unsigned int v9; // esi
  STRSAFE_PCNZWCH v10; // rcx
  int v11; // edx
  const char *v12; // r9
  struct tagUPNP_ACTION *v13; // rax
  unsigned int v14; // r12d
  void *v15; // r15
  void *v16; // r14
  unsigned __int64 v17; // rcx
  size_t v18; // rbx
  unsigned int v19; // eax
  __int64 v20; // rbx
  __int64 v21; // rdi
  BSTR v22; // rax
  __int64 v23; // r9
  __int64 i; // rbx
  OLECHAR *v25; // rcx
  __int64 j; // rbx
  OLECHAR *v27; // rcx
  struct tagUPNP_ACTION *v28; // [rsp+30h] [rbp-48h]
  int v29; // [rsp+88h] [rbp+10h]

  if ( !a2 )
    return 2147942487LL;
  if ( a3 && a4 && a5 )
  {
    IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
    v9 = IsAllowedCOMCallLocality;
    if ( IsAllowedCOMCallLocality < 0 )
    {
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"HrIsAllowedCOMCallLocality failed !",
          IsAllowedCOMCallLocality);
      return v9;
    }
    if ( *((_DWORD *)this + 18) != 2 )
    {
      v9 = -2147418113;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return v9;
      v11 = 45;
      v12 = "GetOutputArgumentNamesAndTypes failed, CUPnPAutomationProxy is not initialized!";
      goto LABEL_63;
    }
    v13 = CUPnPAutomationProxy::LookupActionByName((CUPnPAutomationProxy *)((char *)this - 8), a2);
    v28 = v13;
    if ( v13 )
    {
      v14 = *((_DWORD *)v13 + 6);
      v15 = 0;
      v16 = 0;
      if ( !v14 )
        goto LABEL_35;
      v17 = 8LL * v14;
      if ( v17 <= 0xFFFFFFFF )
      {
        v18 = (unsigned int)v17;
        v15 = CoTaskMemAlloc((unsigned int)v17);
        v16 = CoTaskMemAlloc((unsigned int)v18);
        if ( v15 )
          memset_0(v15, 0, (unsigned int)v18);
        if ( v16 )
          memset_0(v16, 0, v18);
        if ( v15 && v16 )
        {
          v10 = WPP_GLOBAL_Control;
          v19 = 0;
          v29 = 0;
          v9 = 0;
          while ( v19 < v14 )
          {
            v20 = 2LL * v19;
            v21 = v19;
            *((_QWORD *)v15 + v19) = SysAllocString(*(const OLECHAR **)(*((_QWORD *)v28 + 4) + 16LL * v19));
            v22 = SysAllocString(*(const OLECHAR **)(*(_QWORD *)(*((_QWORD *)v28 + 4) + 8 * v20 + 8) + 8LL));
            *((_QWORD *)v16 + v21) = v22;
            v23 = *((_QWORD *)v15 + v21);
            if ( v23 && v22 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
              {
                WPP_SF_SS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  46,
                  (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                  v23,
                  (__int64)v22);
                v10 = WPP_GLOBAL_Control;
              }
            }
            else
            {
              v9 = -2147024882;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  47,
                  (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
                  (unsigned int)"CUPnPAutomationProxy::GetOutputArgumentNamesAndTypes(): Failed to allocate argument name and/or type",
                  14);
                goto LABEL_35;
              }
            }
            v19 = ++v29;
            if ( (v9 & 0x80000000) != 0 )
              break;
          }
LABEL_36:
          if ( (v9 & 0x80000000) == 0 )
          {
            *a3 = v14;
            *a4 = (unsigned __int16 **)v15;
            *a5 = (unsigned __int16 **)v16;
            goto LABEL_54;
          }
LABEL_42:
          if ( v15 )
          {
            for ( i = 0; (unsigned int)i < v14; i = (unsigned int)(i + 1) )
            {
              v25 = (OLECHAR *)*((_QWORD *)v15 + i);
              if ( v25 )
              {
                SysFreeString(v25);
                *((_QWORD *)v15 + i) = 0;
              }
            }
            CoTaskMemFree(v15);
            v10 = WPP_GLOBAL_Control;
          }
          if ( !v16 )
          {
LABEL_55:
            if ( !v9 )
              return v9;
            goto LABEL_60;
          }
          for ( j = 0; (unsigned int)j < v14; j = (unsigned int)(j + 1) )
          {
            v27 = (OLECHAR *)*((_QWORD *)v16 + j);
            if ( v27 )
            {
              SysFreeString(v27);
              *((_QWORD *)v16 + j) = 0;
            }
          }
          CoTaskMemFree(v16);
LABEL_54:
          v10 = WPP_GLOBAL_Control;
          goto LABEL_55;
        }
        v9 = -2147024882;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_42;
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (unsigned int)"CUPnPAutomationProxy::GetOutputArgumentNamesAndTypes(): Failed to allocate output arrays",
          14);
LABEL_35:
        v10 = WPP_GLOBAL_Control;
        goto LABEL_36;
      }
      return (unsigned int)-2147024362;
    }
    else
    {
      v9 = -2147024809;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
            (unsigned int)"CUPnPAutomationProxy::GetOutputArgumentNamesAndTypes(): No such action",
            87);
          v10 = WPP_GLOBAL_Control;
        }
LABEL_60:
        if ( v10 == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (v10[14] & 1) == 0 )
          return v9;
        v11 = 50;
        v12 = "CUPnPAutomationProxy::GetOutputArgumentNamesAndTypes(): Exiting";
LABEL_63:
        WPP_SF_sd(
          *((_QWORD *)v10 + 2),
          v11,
          (unsigned int)WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids,
          (_DWORD)v12,
          v9);
      }
    }
    return v9;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800291a0  mov     [rsp+arg_18], r9
0x1800291a5  mov     [rsp+arg_10], r8
0x1800291aa  push    rbx
0x1800291ab  push    rbp
0x1800291ac  push    rsi
0x1800291ad  push    rdi
0x1800291ae  push    r12
0x1800291b0  push    r14
0x1800291b2  push    r15
0x1800291b4  sub     rsp, 40h
0x1800291b8  mov     rax, r9
0x1800291bb  mov     rdi, rdx
0x1800291be  mov     rbx, rcx
0x1800291c1  test    rdx, rdx
0x1800291c4  jnz     short loc_1800291D0
0x1800291c6  mov     eax, 80070057h
0x1800291cb  jmp     loc_18002954F
0x1800291d0  test    r8, r8
0x1800291d3  jz      loc_18002954A
0x1800291d9  test    rax, rax
0x1800291dc  jz      loc_18002954A
0x1800291e2  cmp     [rsp+78h+arg_20], 0
0x1800291eb  jz      loc_18002954A
0x1800291f1  mov     ecx, 1
0x1800291f6  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800291fb  mov     esi, eax
0x1800291fd  test    eax, eax
0x1800291ff  jns     short loc_180029237
0x180029201  mov     rcx, cs:WPP_GLOBAL_Control
0x180029208  lea     rbp, WPP_GLOBAL_Control
0x18002920f  cmp     rcx, rbp
0x180029212  jz      loc_180029546
0x180029218  test    byte ptr [rcx+1Ch], 1
0x18002921c  jz      loc_180029546
0x180029222  mov     edx, 2Ch ; ','
0x180029227  mov     dword ptr [rsp+78h+var_58], eax
0x18002922b  lea     r9, aHrisallowedcom; "HrIsAllowedCOMCallLocality failed !"
0x180029232  jmp     loc_180029536
0x180029237  mov     eax, [rbx+48h]
0x18002923a  cmp     eax, 2
0x18002923d  jz      short loc_180029276
0x18002923f  mov     esi, 8000FFFFh
0x180029244  mov     rcx, cs:WPP_GLOBAL_Control
0x18002924b  lea     rbp, WPP_GLOBAL_Control
0x180029252  cmp     rcx, rbp
0x180029255  jz      loc_180029546
0x18002925b  test    byte ptr [rcx+1Ch], 1
0x18002925f  jz      loc_180029546
0x180029265  mov     edx, 2Dh ; '-'
0x18002926a  lea     r9, aGetoutputargum; "GetOutputArgumentNamesAndTypes failed, "...
0x180029271  jmp     loc_180029532
0x180029276  lea     rcx, [rbx-8]; this
0x18002927a  mov     rdx, rdi; unsigned __int16 *
0x18002927d  call    ?LookupActionByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_ACTION@@PEBG@Z; CUPnPAutomationProxy::LookupActionByName(ushort const *)
0x180029282  mov     [rsp+78h+var_48], rax
0x180029287  test    rax, rax
0x18002928a  jz      loc_1800294D6
0x180029290  mov     r12d, [rax+18h]
0x180029294  lea     rbp, WPP_GLOBAL_Control
0x18002929b  xor     r15d, r15d
0x18002929e  xor     r14d, r14d
0x1800292a1  test    r12d, r12d
0x1800292a4  jz      loc_1800293F6
0x1800292aa  mov     ecx, r12d
0x1800292ad  mov     eax, 0FFFFFFFFh
0x1800292b2  shl     rcx, 3
0x1800292b6  cmp     rcx, rax
0x1800292b9  ja      loc_180029452
0x1800292bf  mov     ebx, ecx
0x1800292c1  mov     ecx, ecx; cb
0x1800292c3  call    cs:__imp_CoTaskMemAlloc
0x1800292c9  mov     ecx, ebx; cb
0x1800292cb  mov     r15, rax
0x1800292ce  call    cs:__imp_CoTaskMemAlloc
0x1800292d4  mov     r14, rax
0x1800292d7  test    r15, r15
0x1800292da  jz      short loc_1800292E9
0x1800292dc  mov     r8d, ebx; Size
0x1800292df  xor     edx, edx; Val
0x1800292e1  mov     rcx, r15; void *
0x1800292e4  call    memset_0
0x1800292e9  test    r14, r14
0x1800292ec  jz      short loc_1800292FB
0x1800292ee  mov     r8, rbx; Size
0x1800292f1  xor     edx, edx; Val
0x1800292f3  mov     rcx, r14; void *
0x1800292f6  call    memset_0
0x1800292fb  test    r15, r15
0x1800292fe  jz      loc_180029427
0x180029304  test    r14, r14
0x180029307  jz      loc_180029427
0x18002930d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029314  xor     eax, eax
0x180029316  mov     [rsp+78h+arg_8], eax
0x18002931d  xor     esi, esi
0x18002931f  cmp     eax, r12d
0x180029322  jnb     loc_1800293FD
0x180029328  mov     rcx, [rsp+78h+var_48]
0x18002932d  mov     ebx, eax
0x18002932f  add     rbx, rbx
0x180029332  mov     edi, eax
0x180029334  mov     rcx, [rcx+20h]
0x180029338  mov     rcx, [rcx+rbx*8]; psz
0x18002933c  call    cs:__imp_SysAllocString
0x180029342  mov     [r15+rdi*8], rax
0x180029346  mov     rax, [rsp+78h+var_48]
0x18002934b  mov     rax, [rax+20h]
0x18002934f  mov     rcx, [rax+rbx*8+8]
0x180029354  mov     rcx, [rcx+8]; psz
0x180029358  call    cs:__imp_SysAllocString
0x18002935e  mov     [r14+rdi*8], rax
0x180029362  mov     r9, [r15+rdi*8]
0x180029366  test    r9, r9
0x180029369  jz      short loc_1800293A5
0x18002936b  test    rax, rax
0x18002936e  jz      short loc_1800293A5
0x180029370  mov     rcx, cs:WPP_GLOBAL_Control
0x180029377  cmp     rcx, rbp
0x18002937a  jz      short loc_1800293BC
0x18002937c  test    byte ptr [rcx+1Ch], 40h
0x180029380  jz      short loc_1800293BC
0x180029382  mov     rcx, [rcx+10h]
0x180029386  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002938d  mov     edx, 2Eh ; '.'
0x180029392  mov     [rsp+78h+var_58], rax
0x180029397  call    WPP_SF_SS
0x18002939c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293a3  jmp     short loc_1800293BC
0x1800293a5  mov     esi, 8007000Eh
0x1800293aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293b1  cmp     rcx, rbp
0x1800293b4  jz      short loc_1800293BC
0x1800293b6  test    byte ptr [rcx+1Ch], 1
0x1800293ba  jnz     short loc_1800293D6
0x1800293bc  mov     eax, [rsp+78h+arg_8]
0x1800293c3  inc     eax
0x1800293c5  mov     [rsp+78h+arg_8], eax
0x1800293cc  test    esi, esi
0x1800293ce  jns     loc_18002931F
0x1800293d4  jmp     short loc_1800293FD
0x1800293d6  mov     edx, 2Fh ; '/'
0x1800293db  mov     dword ptr [rsp+78h+var_58], esi
0x1800293df  lea     r9, aCupnpautomatio_21; "CUPnPAutomationProxy::GetOutputArgument"...
0x1800293e6  mov     rcx, [rcx+10h]
0x1800293ea  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x1800293f1  call    WPP_SF_sd
0x1800293f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293fd  test    esi, esi
0x1800293ff  js      short loc_18002945C
0x180029401  mov     rax, [rsp+78h+arg_10]
0x180029409  mov     [rax], r12d
0x18002940c  mov     rax, [rsp+78h+arg_18]
0x180029414  mov     [rax], r15
0x180029417  mov     rax, [rsp+78h+arg_20]
0x18002941f  mov     [rax], r14
0x180029422  jmp     loc_1800294C9
0x180029427  mov     eax, 8007000Eh
0x18002942c  mov     esi, eax
0x18002942e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029435  cmp     rcx, rbp
0x180029438  jz      short loc_18002945C
0x18002943a  test    byte ptr [rcx+1Ch], 1
0x18002943e  jz      short loc_18002945C
0x180029440  mov     edx, 30h ; '0'
0x180029445  mov     dword ptr [rsp+78h+var_58], eax
0x180029449  lea     r9, aCupnpautomatio_29; "CUPnPAutomationProxy::GetOutputArgument"...
0x180029450  jmp     short loc_1800293E6
0x180029452  mov     esi, 80070216h
0x180029457  jmp     loc_180029546
0x18002945c  test    r15, r15
0x18002945f  jz      short loc_180029496
0x180029461  xor     ebx, ebx
0x180029463  test    r12d, r12d
0x180029466  jz      short loc_180029486
0x180029468  mov     rcx, [r15+rbx*8]; bstrString
0x18002946c  test    rcx, rcx
0x18002946f  jz      short loc_18002947F
0x180029471  call    cs:__imp_SysFreeString
0x180029477  mov     qword ptr [r15+rbx*8], 0
0x18002947f  inc     ebx
0x180029481  cmp     ebx, r12d
0x180029484  jb      short loc_180029468
0x180029486  mov     rcx, r15; pv
0x180029489  call    cs:__imp_CoTaskMemFree
0x18002948f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029496  test    r14, r14
0x180029499  jz      short loc_1800294D0
0x18002949b  xor     ebx, ebx
0x18002949d  test    r12d, r12d
0x1800294a0  jz      short loc_1800294C0
0x1800294a2  mov     rcx, [r14+rbx*8]; bstrString
0x1800294a6  test    rcx, rcx
0x1800294a9  jz      short loc_1800294B9
0x1800294ab  call    cs:__imp_SysFreeString
0x1800294b1  mov     qword ptr [r14+rbx*8], 0
0x1800294b9  inc     ebx
0x1800294bb  cmp     ebx, r12d
0x1800294be  jb      short loc_1800294A2
0x1800294c0  mov     rcx, r14; pv
0x1800294c3  call    cs:__imp_CoTaskMemFree
0x1800294c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294d0  test    esi, esi
0x1800294d2  jnz     short loc_18002951B
0x1800294d4  jmp     short loc_180029546
0x1800294d6  mov     esi, 80070057h
0x1800294db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294e2  lea     rbp, WPP_GLOBAL_Control
0x1800294e9  cmp     rcx, rbp
0x1800294ec  jz      short loc_180029546
0x1800294ee  test    byte ptr [rcx+1Ch], 1
0x1800294f2  jz      short loc_18002951B
0x1800294f4  mov     rcx, [rcx+10h]
0x1800294f8  lea     r9, aCupnpautomatio_2; "CUPnPAutomationProxy::GetOutputArgument"...
0x1800294ff  mov     edx, 31h ; '1'
0x180029504  mov     dword ptr [rsp+78h+var_58], esi
0x180029508  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002950f  call    WPP_SF_sd
0x180029514  mov     rcx, cs:WPP_GLOBAL_Control
0x18002951b  cmp     rcx, rbp
0x18002951e  jz      short loc_180029546
0x180029520  test    byte ptr [rcx+1Ch], 1
0x180029524  jz      short loc_180029546
0x180029526  mov     edx, 32h ; '2'
0x18002952b  lea     r9, aCupnpautomatio_30; "CUPnPAutomationProxy::GetOutputArgument"...
0x180029532  mov     dword ptr [rsp+78h+var_58], esi
0x180029536  mov     rcx, [rcx+10h]
0x18002953a  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x180029541  call    WPP_SF_sd
0x180029546  mov     eax, esi
0x180029548  jmp     short loc_18002954F
0x18002954a  mov     eax, 80004003h
0x18002954f  add     rsp, 40h
0x180029553  pop     r15
0x180029555  pop     r14
0x180029557  pop     r12
0x180029559  pop     rdi
0x18002955a  pop     rsi
0x18002955b  pop     rbp
0x18002955c  pop     rbx
0x18002955d  retn
```
