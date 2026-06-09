# KsppGetPinFromNgcPinCache

- ea: `0x180019514`
- end: `0x180019802`
- name: `KsppGetPinFromNgcPinCache`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18001b6f8`

## callees

- `0x180009e82`
- `0x18000a408`
- `0x18000d9d0`
- `0x18001147c`
- `0x180011fd8`
- `0x180013734`
- `0x180019220`
- `0x180019514`
- `0x18002b140`
- `0x18002ec0c`
- `0x180039d7c`
- `0x18003c240`

## import_xrefs

- `cryptngc!NgcCreateTicketForSmartCardVpn` at `0x180019696`
- `cryptngc!NgcCreateTicketForSmartCardVpn` at `0x180019696`

## string_xrefs

- `0x1800196ef`: `_$PinCache$_`

## pseudocode

```c
__int64 __fastcall KsppGetPinFromNgcPinCache(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int NgcKeyName; // ebx
  void *v6; // rax
  void *v7; // rdi
  __int64 v8; // rcx
  _QWORD *v9; // rax
  int v10; // edx
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // rcx
  size_t size; // [rsp+30h] [rbp-248h] BYREF
  __int64 v18; // [rsp+38h] [rbp-240h] BYREF
  WCHAR SourceString[264]; // [rsp+40h] [rbp-238h] BYREF

  LODWORD(size) = 0;
  memset_0(SourceString, 0, 0x202u);
  NgcKeyName = KsppGetNgcKeyName(a1, 0, 0, &size);
  if ( NgcKeyName )
  {
    WppTraceIndent(v4, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        236,
        (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
        (_DWORD)WPP_pszIndent,
        NgcKeyName);
    }
    return NgcKeyName;
  }
  v6 = MIDL_user_allocate((unsigned int)size);
  v7 = v6;
  if ( v6 )
  {
    NgcKeyName = KsppGetNgcKeyName(a1, v6, (unsigned int)size, &size);
    if ( NgcKeyName )
    {
      WppTraceIndent(v8, 2);
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      v10 = 238;
    }
    else
    {
      v18 = 0;
      v12 = NgcCreateTicketForSmartCardVpn(v7, 0, &v18);
      if ( v12 >= 0 )
      {
        v14 = StringCchPrintfW(SourceString, 0x101u, L"%s%I64u", L"_$PinCache$_", v18);
        if ( v14 >= 0 )
        {
          CspFreeH(*(_QWORD *)(a2 + 16));
          *(_QWORD *)(a2 + 16) = 0;
          *(_DWORD *)(a2 + 12) = 0;
          NgcKeyName = PinStringToBytesW(SourceString);
          if ( !NgcKeyName )
            goto LABEL_32;
          WppTraceIndent(v15, 2);
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_32;
          }
          v10 = 241;
        }
        else
        {
          WppTraceIndent(v13, 2);
          NgcKeyName = HR_Remap((unsigned int)v14);
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_32;
          }
          v10 = 240;
        }
      }
      else
      {
        WppTraceIndent(v11, 2);
        NgcKeyName = HR_Remap((unsigned int)v12);
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_32;
        }
        v10 = 239;
      }
    }
    WPP_SF_sd(
      v9[2],
      v10,
      (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
      (_DWORD)WPP_pszIndent,
      NgcKeyName);
LABEL_32:
    CspFreeH(v7);
    return NgcKeyName;
  }
  NgcKeyName = -2146893810;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, WPP_pszIndent);
  }
  return NgcKeyName;
}

```

## disassembly

```asm
0x180019514  mov     [rsp+arg_10], rbx
0x180019519  push    rbp
0x18001951a  push    rsi
0x18001951b  push    rdi
0x18001951c  sub     rsp, 260h
0x180019523  mov     rax, cs:__security_cookie
0x18001952a  xor     rax, rsp
0x18001952d  mov     [rsp+278h+var_28], rax
0x180019535  mov     rsi, rdx
0x180019538  mov     dword ptr [rsp+278h+size], 0
0x180019540  mov     rbp, rcx
0x180019543  xor     edx, edx; Val
0x180019545  lea     rcx, [rsp+278h+SourceString]; void *
0x18001954a  mov     r8d, 202h; Size
0x180019550  call    memset_0
0x180019555  lea     r9, [rsp+278h+size]
0x18001955a  xor     r8d, r8d
0x18001955d  xor     edx, edx
0x18001955f  mov     rcx, rbp
0x180019562  call    KsppGetNgcKeyName
0x180019567  mov     ebx, eax
0x180019569  test    eax, eax
0x18001956b  jz      short loc_1800195C7
0x18001956d  mov     edx, 2
0x180019572  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180019577  mov     rax, cs:WPP_GLOBAL_Control
0x18001957e  lea     rcx, WPP_GLOBAL_Control
0x180019585  cmp     rax, rcx
0x180019588  jz      loc_1800197DD
0x18001958e  test    byte ptr [rax+1Ch], 1
0x180019592  jz      loc_1800197DD
0x180019598  cmp     byte ptr [rax+19h], 2
0x18001959c  jb      loc_1800197DD
0x1800195a2  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800195a9  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x1800195b0  mov     rcx, [rax+10h]
0x1800195b4  mov     edx, 0ECh
0x1800195b9  mov     dword ptr [rsp+278h+var_258], ebx
0x1800195bd  call    WPP_SF_sd
0x1800195c2  jmp     loc_1800197DD
0x1800195c7  mov     ecx, dword ptr [rsp+278h+size]; size
0x1800195cb  call    MIDL_user_allocate
0x1800195d0  mov     rdi, rax
0x1800195d3  test    rax, rax
0x1800195d6  jnz     short loc_180019629
0x1800195d8  mov     ebx, 8009000Eh
0x1800195dd  mov     rax, cs:WPP_GLOBAL_Control
0x1800195e4  lea     rcx, WPP_GLOBAL_Control
0x1800195eb  cmp     rax, rcx
0x1800195ee  jz      loc_1800197DD
0x1800195f4  test    byte ptr [rax+1Ch], 1
0x1800195f8  jz      loc_1800197DD
0x1800195fe  cmp     byte ptr [rax+19h], 2
0x180019602  jb      loc_1800197DD
0x180019608  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001960f  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180019616  mov     rcx, [rax+10h]
0x18001961a  mov     edx, 0EDh
0x18001961f  call    WPP_SF_s
0x180019624  jmp     loc_1800197DD
0x180019629  mov     r8d, dword ptr [rsp+278h+size]
0x18001962e  lea     r9, [rsp+278h+size]
0x180019633  mov     rdx, rdi
0x180019636  mov     rcx, rbp
0x180019639  call    KsppGetNgcKeyName
0x18001963e  mov     ebx, eax
0x180019640  test    eax, eax
0x180019642  jz      short loc_180019683
0x180019644  mov     edx, 2
0x180019649  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001964e  mov     rax, cs:WPP_GLOBAL_Control
0x180019655  lea     rcx, WPP_GLOBAL_Control
0x18001965c  cmp     rax, rcx
0x18001965f  jz      loc_1800197D5
0x180019665  test    byte ptr [rax+1Ch], 1
0x180019669  jz      loc_1800197D5
0x18001966f  cmp     byte ptr [rax+19h], 2
0x180019673  jb      loc_1800197D5
0x180019679  mov     edx, 0EEh
0x18001967e  jmp     loc_1800197BA
0x180019683  lea     r8, [rsp+278h+var_240]
0x180019688  mov     [rsp+278h+var_240], 0
0x180019691  xor     edx, edx
0x180019693  mov     rcx, rdi
0x180019696  call    cs:__imp_NgcCreateTicketForSmartCardVpn
0x18001969c  mov     ebx, eax
0x18001969e  test    eax, eax
0x1800196a0  jns     short loc_1800196EA
0x1800196a2  mov     edx, 2
0x1800196a7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800196ac  mov     ecx, ebx
0x1800196ae  call    HR_Remap
0x1800196b3  mov     ebx, eax
0x1800196b5  mov     rax, cs:WPP_GLOBAL_Control
0x1800196bc  lea     rcx, WPP_GLOBAL_Control
0x1800196c3  cmp     rax, rcx
0x1800196c6  jz      loc_1800197D5
0x1800196cc  test    byte ptr [rax+1Ch], 1
0x1800196d0  jz      loc_1800197D5
0x1800196d6  cmp     byte ptr [rax+19h], 2
0x1800196da  jb      loc_1800197D5
0x1800196e0  mov     edx, 0EFh
0x1800196e5  jmp     loc_1800197BA
0x1800196ea  mov     rax, [rsp+278h+var_240]
0x1800196ef  lea     r9, aPincache; "_$PinCache$_"
0x1800196f6  lea     r8, aSI64u; "%s%I64u"
0x1800196fd  mov     [rsp+278h+var_258], rax
0x180019702  mov     edx, 101h; unsigned __int64
0x180019707  lea     rcx, [rsp+278h+SourceString]; unsigned __int16 *
0x18001970c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019711  mov     ebx, eax
0x180019713  test    eax, eax
0x180019715  jns     short loc_18001975C
0x180019717  mov     edx, 2
0x18001971c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180019721  mov     ecx, ebx
0x180019723  call    HR_Remap
0x180019728  mov     ebx, eax
0x18001972a  mov     rax, cs:WPP_GLOBAL_Control
0x180019731  lea     rcx, WPP_GLOBAL_Control
0x180019738  cmp     rax, rcx
0x18001973b  jz      loc_1800197D5
0x180019741  test    byte ptr [rax+1Ch], 1
0x180019745  jz      loc_1800197D5
0x18001974b  cmp     byte ptr [rax+19h], 2
0x18001974f  jb      loc_1800197D5
0x180019755  mov     edx, 0F0h
0x18001975a  jmp     short loc_1800197BA
0x18001975c  lea     rbx, [rsi+10h]
0x180019760  mov     rcx, [rbx]
0x180019763  call    CspFreeH
0x180019768  lea     rdx, [rsi+0Ch]
0x18001976c  mov     qword ptr [rbx], 0
0x180019773  mov     r8, rbx
0x180019776  mov     dword ptr [rdx], 0
0x18001977c  lea     rcx, [rsp+278h+SourceString]; SourceString
0x180019781  call    PinStringToBytesW
0x180019786  mov     ebx, eax
0x180019788  test    eax, eax
0x18001978a  jz      short loc_1800197D5
0x18001978c  mov     edx, 2
0x180019791  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180019796  mov     rax, cs:WPP_GLOBAL_Control
0x18001979d  lea     rcx, WPP_GLOBAL_Control
0x1800197a4  cmp     rax, rcx
0x1800197a7  jz      short loc_1800197D5
0x1800197a9  test    byte ptr [rax+1Ch], 1
0x1800197ad  jz      short loc_1800197D5
0x1800197af  cmp     byte ptr [rax+19h], 2
0x1800197b3  jb      short loc_1800197D5
0x1800197b5  mov     edx, 0F1h
0x1800197ba  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800197c1  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x1800197c8  mov     rcx, [rax+10h]
0x1800197cc  mov     dword ptr [rsp+278h+var_258], ebx
0x1800197d0  call    WPP_SF_sd
0x1800197d5  mov     rcx, rdi
0x1800197d8  call    CspFreeH
0x1800197dd  mov     eax, ebx
0x1800197df  mov     rcx, [rsp+278h+var_28]
0x1800197e7  xor     rcx, rsp; StackCookie
0x1800197ea  call    __security_check_cookie
0x1800197ef  mov     rbx, [rsp+278h+arg_10]
0x1800197f7  add     rsp, 260h
0x1800197fe  pop     rdi
0x1800197ff  pop     rsi
0x180019800  pop     rbp
0x180019801  retn
```
