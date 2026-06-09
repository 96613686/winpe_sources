# CUPnPAutomationProxy::GetOutputArgumentNamesAndTypes(ushort *,ulong *,ushort * * *,ushort * * *)

- ea: `0x18002a4b0`
- end: `0x18002a89f`
- name: `?GetOutputArgumentNamesAndTypes@CUPnPAutomationProxy@@UEAAJPEAGPEAKPEAPEAPEAG2@Z`
- size: `1007`
- prototype: `int(CUPnPAutomationProxy *__hidden this, unsigned __int16 *, unsigned int *, unsigned __int16 ***, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800071c0`
- `0x1800200f4`
- `0x1800209c8`
- `0x18002a4b0`
- `0x18002adc0`
- `0x18003d4b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a5e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a5d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a5e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a658`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a67a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a658`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a67a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a799`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a7df`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a799`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a7df`

## string_xrefs

- `0x18002a53b`: `HrIsAllowedCOMCallLocality failed !`

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
0x18002a4b0  mov     [rsp+arg_18], r9
0x18002a4b5  mov     [rsp+arg_10], r8
0x18002a4ba  push    rbx
0x18002a4bb  push    rbp
0x18002a4bc  push    rsi
0x18002a4bd  push    rdi
0x18002a4be  push    r12
0x18002a4c0  push    r14
0x18002a4c2  push    r15
0x18002a4c4  sub     rsp, 40h
0x18002a4c8  mov     rax, r9
0x18002a4cb  mov     rdi, rdx
0x18002a4ce  mov     rbx, rcx
0x18002a4d1  test    rdx, rdx
0x18002a4d4  jnz     short loc_18002A4E0
0x18002a4d6  mov     eax, 80070057h
0x18002a4db  jmp     loc_18002A88F
0x18002a4e0  test    r8, r8
0x18002a4e3  jz      loc_18002A88A
0x18002a4e9  test    rax, rax
0x18002a4ec  jz      loc_18002A88A
0x18002a4f2  cmp     [rsp+78h+arg_20], 0
0x18002a4fb  jz      loc_18002A88A
0x18002a501  mov     ecx, 1
0x18002a506  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18002a50b  mov     esi, eax
0x18002a50d  test    eax, eax
0x18002a50f  jns     short loc_18002A547
0x18002a511  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a518  lea     rbp, WPP_GLOBAL_Control
0x18002a51f  cmp     rcx, rbp
0x18002a522  jz      loc_18002A886
0x18002a528  test    byte ptr [rcx+1Ch], 1
0x18002a52c  jz      loc_18002A886
0x18002a532  mov     edx, 2Ch ; ','
0x18002a537  mov     dword ptr [rsp+78h+var_58], eax
0x18002a53b  lea     r9, aHrisallowedcom; "HrIsAllowedCOMCallLocality failed !"
0x18002a542  jmp     loc_18002A876
0x18002a547  mov     eax, [rbx+48h]
0x18002a54a  cmp     eax, 2
0x18002a54d  jz      short loc_18002A586
0x18002a54f  mov     esi, 8000FFFFh
0x18002a554  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a55b  lea     rbp, WPP_GLOBAL_Control
0x18002a562  cmp     rcx, rbp
0x18002a565  jz      loc_18002A886
0x18002a56b  test    byte ptr [rcx+1Ch], 1
0x18002a56f  jz      loc_18002A886
0x18002a575  mov     edx, 2Dh ; '-'
0x18002a57a  lea     r9, aGetoutputargum; "GetOutputArgumentNamesAndTypes failed, "...
0x18002a581  jmp     loc_18002A872
0x18002a586  lea     rcx, [rbx-8]; this
0x18002a58a  mov     rdx, rdi; unsigned __int16 *
0x18002a58d  call    ?LookupActionByName@CUPnPAutomationProxy@@AEAAPEAUtagUPNP_ACTION@@PEBG@Z; CUPnPAutomationProxy::LookupActionByName(ushort const *)
0x18002a592  mov     [rsp+78h+var_48], rax
0x18002a597  test    rax, rax
0x18002a59a  jz      loc_18002A816
0x18002a5a0  mov     r12d, [rax+18h]
0x18002a5a4  lea     rbp, WPP_GLOBAL_Control
0x18002a5ab  xor     r15d, r15d
0x18002a5ae  xor     r14d, r14d
0x18002a5b1  test    r12d, r12d
0x18002a5b4  jz      loc_18002A71E
0x18002a5ba  mov     ecx, r12d
0x18002a5bd  mov     eax, 0FFFFFFFFh
0x18002a5c2  shl     rcx, 3
0x18002a5c6  cmp     rcx, rax
0x18002a5c9  ja      loc_18002A77A
0x18002a5cf  mov     ebx, ecx
0x18002a5d1  mov     ecx, ecx; cb
0x18002a5d3  call    cs:__imp_CoTaskMemAlloc
0x18002a5da  nop     dword ptr [rax+rax+00h]
0x18002a5df  mov     ecx, ebx; cb
0x18002a5e1  mov     r15, rax
0x18002a5e4  call    cs:__imp_CoTaskMemAlloc
0x18002a5eb  nop     dword ptr [rax+rax+00h]
0x18002a5f0  mov     r14, rax
0x18002a5f3  test    r15, r15
0x18002a5f6  jz      short loc_18002A605
0x18002a5f8  mov     r8d, ebx; Size
0x18002a5fb  xor     edx, edx; Val
0x18002a5fd  mov     rcx, r15; void *
0x18002a600  call    memset_0
0x18002a605  test    r14, r14
0x18002a608  jz      short loc_18002A617
0x18002a60a  mov     r8, rbx; Size
0x18002a60d  xor     edx, edx; Val
0x18002a60f  mov     rcx, r14; void *
0x18002a612  call    memset_0
0x18002a617  test    r15, r15
0x18002a61a  jz      loc_18002A74F
0x18002a620  test    r14, r14
0x18002a623  jz      loc_18002A74F
0x18002a629  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a630  xor     eax, eax
0x18002a632  mov     [rsp+78h+arg_8], eax
0x18002a639  xor     esi, esi
0x18002a63b  cmp     eax, r12d
0x18002a63e  jnb     loc_18002A725
0x18002a644  mov     rcx, [rsp+78h+var_48]
0x18002a649  mov     ebx, eax
0x18002a64b  add     rbx, rbx
0x18002a64e  mov     edi, eax
0x18002a650  mov     rcx, [rcx+20h]
0x18002a654  mov     rcx, [rcx+rbx*8]; psz
0x18002a658  call    cs:__imp_SysAllocString
0x18002a65f  nop     dword ptr [rax+rax+00h]
0x18002a664  mov     [r15+rdi*8], rax
0x18002a668  mov     rax, [rsp+78h+var_48]
0x18002a66d  mov     rax, [rax+20h]
0x18002a671  mov     rcx, [rax+rbx*8+8]
0x18002a676  mov     rcx, [rcx+8]; psz
0x18002a67a  call    cs:__imp_SysAllocString
0x18002a681  nop     dword ptr [rax+rax+00h]
0x18002a686  mov     [r14+rdi*8], rax
0x18002a68a  mov     r9, [r15+rdi*8]
0x18002a68e  test    r9, r9
0x18002a691  jz      short loc_18002A6CD
0x18002a693  test    rax, rax
0x18002a696  jz      short loc_18002A6CD
0x18002a698  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a69f  cmp     rcx, rbp
0x18002a6a2  jz      short loc_18002A6E4
0x18002a6a4  test    byte ptr [rcx+1Ch], 40h
0x18002a6a8  jz      short loc_18002A6E4
0x18002a6aa  mov     rcx, [rcx+10h]
0x18002a6ae  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002a6b5  mov     edx, 2Eh ; '.'
0x18002a6ba  mov     [rsp+78h+var_58], rax
0x18002a6bf  call    WPP_SF_SS
0x18002a6c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6cb  jmp     short loc_18002A6E4
0x18002a6cd  mov     esi, 8007000Eh
0x18002a6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6d9  cmp     rcx, rbp
0x18002a6dc  jz      short loc_18002A6E4
0x18002a6de  test    byte ptr [rcx+1Ch], 1
0x18002a6e2  jnz     short loc_18002A6FE
0x18002a6e4  mov     eax, [rsp+78h+arg_8]
0x18002a6eb  inc     eax
0x18002a6ed  mov     [rsp+78h+arg_8], eax
0x18002a6f4  test    esi, esi
0x18002a6f6  jns     loc_18002A63B
0x18002a6fc  jmp     short loc_18002A725
0x18002a6fe  mov     edx, 2Fh ; '/'
0x18002a703  mov     dword ptr [rsp+78h+var_58], esi
0x18002a707  lea     r9, aCupnpautomatio_21; "CUPnPAutomationProxy::GetOutputArgument"...
0x18002a70e  mov     rcx, [rcx+10h]
0x18002a712  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002a719  call    WPP_SF_sd
0x18002a71e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a725  test    esi, esi
0x18002a727  js      short loc_18002A784
0x18002a729  mov     rax, [rsp+78h+arg_10]
0x18002a731  mov     [rax], r12d
0x18002a734  mov     rax, [rsp+78h+arg_18]
0x18002a73c  mov     [rax], r15
0x18002a73f  mov     rax, [rsp+78h+arg_20]
0x18002a747  mov     [rax], r14
0x18002a74a  jmp     loc_18002A809
0x18002a74f  mov     eax, 8007000Eh
0x18002a754  mov     esi, eax
0x18002a756  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a75d  cmp     rcx, rbp
0x18002a760  jz      short loc_18002A784
0x18002a762  test    byte ptr [rcx+1Ch], 1
0x18002a766  jz      short loc_18002A784
0x18002a768  mov     edx, 30h ; '0'
0x18002a76d  mov     dword ptr [rsp+78h+var_58], eax
0x18002a771  lea     r9, aCupnpautomatio_29; "CUPnPAutomationProxy::GetOutputArgument"...
0x18002a778  jmp     short loc_18002A70E
0x18002a77a  mov     esi, 80070216h
0x18002a77f  jmp     loc_18002A886
0x18002a784  test    r15, r15
0x18002a787  jz      short loc_18002A7CA
0x18002a789  xor     ebx, ebx
0x18002a78b  test    r12d, r12d
0x18002a78e  jz      short loc_18002A7B4
0x18002a790  mov     rcx, [r15+rbx*8]; bstrString
0x18002a794  test    rcx, rcx
0x18002a797  jz      short loc_18002A7AD
0x18002a799  call    cs:__imp_SysFreeString
0x18002a7a0  nop     dword ptr [rax+rax+00h]
0x18002a7a5  mov     qword ptr [r15+rbx*8], 0
0x18002a7ad  inc     ebx
0x18002a7af  cmp     ebx, r12d
0x18002a7b2  jb      short loc_18002A790
0x18002a7b4  mov     rcx, r15; pv
0x18002a7b7  call    cs:__imp_CoTaskMemFree
0x18002a7be  nop     dword ptr [rax+rax+00h]
0x18002a7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7ca  test    r14, r14
0x18002a7cd  jz      short loc_18002A810
0x18002a7cf  xor     ebx, ebx
0x18002a7d1  test    r12d, r12d
0x18002a7d4  jz      short loc_18002A7FA
0x18002a7d6  mov     rcx, [r14+rbx*8]; bstrString
0x18002a7da  test    rcx, rcx
0x18002a7dd  jz      short loc_18002A7F3
0x18002a7df  call    cs:__imp_SysFreeString
0x18002a7e6  nop     dword ptr [rax+rax+00h]
0x18002a7eb  mov     qword ptr [r14+rbx*8], 0
0x18002a7f3  inc     ebx
0x18002a7f5  cmp     ebx, r12d
0x18002a7f8  jb      short loc_18002A7D6
0x18002a7fa  mov     rcx, r14; pv
0x18002a7fd  call    cs:__imp_CoTaskMemFree
0x18002a804  nop     dword ptr [rax+rax+00h]
0x18002a809  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a810  test    esi, esi
0x18002a812  jnz     short loc_18002A85B
0x18002a814  jmp     short loc_18002A886
0x18002a816  mov     esi, 80070057h
0x18002a81b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a822  lea     rbp, WPP_GLOBAL_Control
0x18002a829  cmp     rcx, rbp
0x18002a82c  jz      short loc_18002A886
0x18002a82e  test    byte ptr [rcx+1Ch], 1
0x18002a832  jz      short loc_18002A85B
0x18002a834  mov     rcx, [rcx+10h]
0x18002a838  lea     r9, aCupnpautomatio_2; "CUPnPAutomationProxy::GetOutputArgument"...
0x18002a83f  mov     edx, 31h ; '1'
0x18002a844  mov     dword ptr [rsp+78h+var_58], esi
0x18002a848  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002a84f  call    WPP_SF_sd
0x18002a854  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a85b  cmp     rcx, rbp
0x18002a85e  jz      short loc_18002A886
0x18002a860  test    byte ptr [rcx+1Ch], 1
0x18002a864  jz      short loc_18002A886
0x18002a866  mov     edx, 32h ; '2'
0x18002a86b  lea     r9, aCupnpautomatio_30; "CUPnPAutomationProxy::GetOutputArgument"...
0x18002a872  mov     dword ptr [rsp+78h+var_58], esi
0x18002a876  mov     rcx, [rcx+10h]
0x18002a87a  lea     r8, WPP_b8ceee2bdad93570ea5240c5a3b20a1a_Traceguids
0x18002a881  call    WPP_SF_sd
0x18002a886  mov     eax, esi
0x18002a888  jmp     short loc_18002A88F
0x18002a88a  mov     eax, 80004003h
0x18002a88f  add     rsp, 40h
0x18002a893  pop     r15
0x18002a895  pop     r14
0x18002a897  pop     r12
0x18002a899  pop     rdi
0x18002a89a  pop     rsi
0x18002a89b  pop     rbp
0x18002a89c  pop     rbx
0x18002a89d  retn
```
