# WcnWlanDetermineIfNetworksIsSecure(void *,_DOT11_SSID const *,_GUID const *,bool *,bool *)

- ea: `0x1800505fc`
- end: `0x18005092d`
- name: `?WcnWlanDetermineIfNetworksIsSecure@@YAJPEAXPEBU_DOT11_SSID@@PEBU_GUID@@PEA_N3@Z`
- size: `817`
- prototype: `__int64 __usercall@<rax>(HANDLE hClientHandle@<rcx>, const struct _DOT11_SSID *@<rdx>, const struct _GUID *@<r8>, bool *@<r9>, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046e54`
- `0x18004c224`

## callees

- `0x180004f2c`
- `0x180004fb8`
- `0x180005014`
- `0x1800505fc`
- `0x180053004`
- `0x180056de6`

## import_xrefs

- `wlanapi!WlanPrivateQueryInterface` at `0x180050730`
- `wlanapi!WlanPrivateQueryInterface` at `0x180050730`
- `wlanapi!WlanGetAvailableNetworkList` at `0x1800507b1`
- `wlanapi!WlanGetAvailableNetworkList` at `0x1800507b1`
- `wlanapi!WlanFreeMemory` at `0x18005078e`
- `wlanapi!WlanFreeMemory` at `0x1800508ae`
- `wlanapi!WlanFreeMemory` at `0x18005078e`
- `wlanapi!WlanFreeMemory` at `0x1800508ae`

## string_xrefs

- `0x1800506b7`: `pDot11Ssid`

## pseudocode

```c
__int64 __fastcall WcnWlanDetermineIfNetworksIsSecure(
        HANDLE hClientHandle,
        const struct _DOT11_SSID *a2,
        const struct _GUID *a3,
        bool *a4,
        bool *a5)
{
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // r11
  __int64 v13; // rdx
  const char *v14; // r9
  bool *v16; // rsi
  int v17; // eax
  _DWORD *v18; // rdx
  unsigned int v19; // r9d
  __int64 v20; // r8
  __int64 v21; // rcx
  unsigned int v22; // r11d
  signed int AvailableNetworkList; // eax
  unsigned int v24; // ebx
  signed int v25; // ebx
  _BYTE *v26; // r10
  PWLAN_AVAILABLE_NETWORK_LIST v27; // rdi
  size_t uSSIDLength; // r14
  unsigned int v29; // ebx
  __int64 v30; // rsi
  const char *v31; // rax
  __int64 v32; // r10
  unsigned int v33; // eax
  __int64 v34; // r10
  PWLAN_AVAILABLE_NETWORK_LIST ppAvailableNetworkList; // [rsp+30h] [rbp-10h] BYREF
  PVOID pMemory; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v37; // [rsp+70h] [rbp+30h] BYREF

  pMemory = 0;
  v37 = 0;
  ppAvailableNetworkList = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 45, v12, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !hClientHandle )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 46;
    v14 = "hWlan";
LABEL_20:
    WPP_SF_s(*((_QWORD *)v9 + 2), v13, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, v14);
    return 2147500035LL;
  }
  if ( !a2 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 47;
    v14 = "pDot11Ssid";
    goto LABEL_20;
  }
  if ( !a3 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 48;
    v14 = "pWlanInterface";
    goto LABEL_20;
  }
  if ( !a4 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 49;
    v14 = "pfIsApSecure";
    goto LABEL_20;
  }
  v16 = a5;
  *a5 = 0;
  v17 = WlanPrivateQueryInterface(hClientHandle, a3, 3, &v37, &pMemory);
  v18 = pMemory;
  if ( !v17 && v37 >= 0x34 )
  {
    v19 = 0;
    if ( *((_DWORD *)pMemory + 1) )
    {
      do
      {
        v20 = 0;
        v21 = 11LL * v19;
        v22 = v18[v21 + 8];
        if ( v22 )
        {
          while ( *(_DWORD *)((char *)&v18[v20] + (unsigned int)v18[v21 + 7]) != 9 )
          {
            v20 = (unsigned int)(v20 + 1);
            if ( (unsigned int)v20 >= v22 )
              goto LABEL_30;
          }
          *v16 = 1;
        }
LABEL_30:
        ++v19;
      }
      while ( v19 < v18[1] );
    }
  }
  if ( v18 )
  {
    WlanFreeMemory(v18);
    pMemory = 0;
  }
  AvailableNetworkList = WlanGetAvailableNetworkList(hClientHandle, a3, 0, 0, &ppAvailableNetworkList);
  if ( AvailableNetworkList )
  {
    if ( AvailableNetworkList > 0 )
      v24 = (unsigned __int16)AvailableNetworkList | 0x80070000;
    else
      v24 = AvailableNetworkList;
    v25 = v24 | 0x80000000;
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v27 = ppAvailableNetworkList;
    }
    else
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids,
        (unsigned int)AvailableNetworkList,
        v25);
      v26 = WPP_GLOBAL_Control;
      v27 = ppAvailableNetworkList;
    }
  }
  else
  {
    v27 = ppAvailableNetworkList;
    if ( ppAvailableNetworkList->dwNumberOfItems )
    {
      uSSIDLength = a2->uSSIDLength;
      v29 = 0;
      while ( 1 )
      {
        v30 = v29;
        if ( v27->Network[v30].dot11Ssid.uSSIDLength == (_DWORD)uSSIDLength
          && !memcmp_0(v27->Network[v30].dot11Ssid.ucSSID, a2->ucSSID, uSSIDLength) )
        {
          break;
        }
        if ( ++v29 >= v27->dwNumberOfItems )
          goto LABEL_46;
      }
      v25 = 0;
      *a4 = v27->Network[v30].bSecurityEnabled;
      v26 = WPP_GLOBAL_Control;
    }
    else
    {
LABEL_46:
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v31 = GetIndent(0);
        WPP_SF_s(*(_QWORD *)(v32 + 16), 51, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, v31);
        v26 = WPP_GLOBAL_Control;
        v27 = ppAvailableNetworkList;
      }
      v25 = -2147023728;
    }
  }
  if ( v27 )
  {
    WlanFreeMemory(v27);
    v26 = WPP_GLOBAL_Control;
  }
  if ( v26 != (_BYTE *)&WPP_GLOBAL_Control && (v25 < 0 || v26[25] >= 6u) )
  {
    v33 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v34 + 16), 52, (unsigned int)WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, v33, v25);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1800505fc  mov     [rsp-28h+arg_8], rbx
0x180050601  mov     [rsp-28h+arg_10], rsi
0x180050606  push    rbp
0x180050607  push    rdi
0x180050608  push    r12
0x18005060a  push    r14
0x18005060c  push    r15
0x18005060e  mov     rbp, rsp
0x180050611  sub     rsp, 40h
0x180050615  mov     r12, r9
0x180050618  mov     [rbp+pMemory], 0
0x180050620  mov     rbx, r8
0x180050623  mov     [rbp+arg_0], 0
0x18005062a  mov     r15, rdx
0x18005062d  mov     [rbp+var_10], 0
0x180050635  mov     rdi, rcx
0x180050638  mov     r10, cs:WPP_GLOBAL_Control
0x18005063f  lea     r14, WPP_GLOBAL_Control
0x180050646  lea     r11, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x18005064d  cmp     r10, r14
0x180050650  jz      short loc_180050685
0x180050652  cmp     byte ptr [r10+19h], 6
0x180050657  jb      short loc_180050685
0x180050659  mov     ecx, 1; int
0x18005065e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180050663  mov     rcx, [r10+10h]
0x180050667  mov     edx, 2Dh ; '-'
0x18005066c  mov     r9, rax
0x18005066f  mov     r8, r11
0x180050672  call    WPP_SF_s
0x180050677  mov     r10, cs:WPP_GLOBAL_Control
0x18005067e  lea     r11, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x180050685  test    rdi, rdi
0x180050688  jnz     short loc_1800506A2
0x18005068a  cmp     r10, r14
0x18005068d  jz      short loc_180050706
0x18005068f  cmp     byte ptr [r10+19h], 2
0x180050694  jb      short loc_180050706
0x180050696  lea     edx, [rdi+2Eh]
0x180050699  lea     r9, aHwlan; "hWlan"
0x1800506a0  jmp     short loc_1800506FA
0x1800506a2  test    r15, r15
0x1800506a5  jnz     short loc_1800506C0
0x1800506a7  cmp     r10, r14
0x1800506aa  jz      short loc_180050706
0x1800506ac  cmp     byte ptr [r10+19h], 2
0x1800506b1  jb      short loc_180050706
0x1800506b3  lea     edx, [r15+2Fh]
0x1800506b7  lea     r9, aPdot11ssid; "pDot11Ssid"
0x1800506be  jmp     short loc_1800506FA
0x1800506c0  test    rbx, rbx
0x1800506c3  jnz     short loc_1800506DD
0x1800506c5  cmp     r10, r14
0x1800506c8  jz      short loc_180050706
0x1800506ca  cmp     byte ptr [r10+19h], 2
0x1800506cf  jb      short loc_180050706
0x1800506d1  lea     edx, [rbx+30h]
0x1800506d4  lea     r9, aPwlaninterface_0; "pWlanInterface"
0x1800506db  jmp     short loc_1800506FA
0x1800506dd  test    r12, r12
0x1800506e0  jnz     short loc_180050710
0x1800506e2  cmp     r10, r14
0x1800506e5  jz      short loc_180050706
0x1800506e7  cmp     byte ptr [r10+19h], 2
0x1800506ec  jb      short loc_180050706
0x1800506ee  lea     edx, [r12+31h]
0x1800506f3  lea     r9, aPfisapsecure; "pfIsApSecure"
0x1800506fa  mov     rcx, [r10+10h]
0x1800506fe  mov     r8, r11
0x180050701  call    WPP_SF_s
0x180050706  mov     eax, 80004003h
0x18005070b  jmp     loc_1800508F1
0x180050710  mov     rsi, [rbp+arg_20]
0x180050714  lea     rax, [rbp+pMemory]
0x180050718  lea     r9, [rbp+arg_0]
0x18005071c  mov     [rsp+40h+ppAvailableNetworkList], rax
0x180050721  mov     r8d, 3
0x180050727  mov     rdx, rbx
0x18005072a  mov     rcx, rdi
0x18005072d  mov     byte ptr [rsi], 0
0x180050730  call    cs:__imp_WlanPrivateQueryInterface
0x180050736  mov     rdx, [rbp+pMemory]
0x18005073a  test    eax, eax
0x18005073c  jnz     short loc_180050786
0x18005073e  cmp     [rbp+arg_0], 34h ; '4'
0x180050742  jb      short loc_180050786
0x180050744  xor     r9d, r9d
0x180050747  cmp     [rdx+4], r9d
0x18005074b  jbe     short loc_180050786
0x18005074d  mov     eax, r9d
0x180050750  xor     r8d, r8d
0x180050753  imul    rcx, rax, 2Ch ; ','
0x180050757  mov     r10d, [rcx+rdx+1Ch]
0x18005075c  mov     r11d, [rcx+rdx+20h]
0x180050761  add     r10, rdx
0x180050764  test    r11d, r11d
0x180050767  jz      short loc_18005077D
0x180050769  cmp     dword ptr [r10+r8*4], 9
0x18005076e  jz      short loc_18005077A
0x180050770  inc     r8d
0x180050773  cmp     r8d, r11d
0x180050776  jb      short loc_180050769
0x180050778  jmp     short loc_18005077D
0x18005077a  mov     byte ptr [rsi], 1
0x18005077d  inc     r9d
0x180050780  cmp     r9d, [rdx+4]
0x180050784  jb      short loc_18005074D
0x180050786  test    rdx, rdx
0x180050789  jz      short loc_18005079C
0x18005078b  mov     rcx, rdx; pMemory
0x18005078e  call    cs:__imp_WlanFreeMemory
0x180050794  mov     [rbp+pMemory], 0
0x18005079c  lea     rax, [rbp+var_10]
0x1800507a0  xor     r9d, r9d; pReserved
0x1800507a3  xor     r8d, r8d; dwFlags
0x1800507a6  mov     [rsp+40h+ppAvailableNetworkList], rax; ppAvailableNetworkList
0x1800507ab  mov     rdx, rbx; pInterfaceGuid
0x1800507ae  mov     rcx, rdi; hClientHandle
0x1800507b1  call    cs:__imp_WlanGetAvailableNetworkList
0x1800507b7  test    eax, eax
0x1800507b9  jz      short loc_180050818
0x1800507bb  jg      short loc_1800507C1
0x1800507bd  mov     ebx, eax
0x1800507bf  jmp     short loc_1800507CA
0x1800507c1  movzx   ebx, ax
0x1800507c4  or      ebx, 80070000h
0x1800507ca  or      ebx, 80000000h
0x1800507d0  mov     r10, cs:WPP_GLOBAL_Control
0x1800507d7  cmp     r10, r14
0x1800507da  jz      short loc_18005080F
0x1800507dc  cmp     byte ptr [r10+19h], 2
0x1800507e1  jb      short loc_18005080F
0x1800507e3  mov     rcx, [r10+10h]
0x1800507e7  lea     r8, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x1800507ee  mov     edx, 32h ; '2'
0x1800507f3  mov     dword ptr [rsp+40h+ppAvailableNetworkList], ebx
0x1800507f7  mov     r9d, eax
0x1800507fa  call    WPP_SF_Dd
0x1800507ff  mov     r10, cs:WPP_GLOBAL_Control
0x180050806  mov     rdi, [rbp+var_10]
0x18005080a  jmp     loc_1800508A6
0x18005080f  mov     rdi, [rbp+var_10]
0x180050813  jmp     loc_1800508A6
0x180050818  mov     rdi, [rbp+var_10]
0x18005081c  cmp     dword ptr [rdi], 0
0x18005081f  jbe     short loc_180050864
0x180050821  mov     r14d, [r15]
0x180050824  xor     ebx, ebx
0x180050826  mov     eax, ebx
0x180050828  imul    rsi, rax, 274h
0x18005082f  cmp     [rsi+rdi+208h], r14d
0x180050837  jnz     short loc_180050857
0x180050839  lea     rcx, [rdi+20Ch]
0x180050840  mov     r8, r14; Size
0x180050843  add     rcx, rsi; Buf1
0x180050846  lea     rdx, [r15+4]; Buf2
0x18005084a  call    memcmp_0
0x18005084f  test    eax, eax
0x180050851  jz      loc_18005090A
0x180050857  inc     ebx
0x180050859  cmp     ebx, [rdi]
0x18005085b  jb      short loc_180050826
0x18005085d  lea     r14, WPP_GLOBAL_Control
0x180050864  mov     r10, cs:WPP_GLOBAL_Control
0x18005086b  cmp     r10, r14
0x18005086e  jz      short loc_1800508A1
0x180050870  cmp     byte ptr [r10+19h], 3
0x180050875  jb      short loc_1800508A1
0x180050877  xor     ecx, ecx; int
0x180050879  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18005087e  mov     rcx, [r10+10h]
0x180050882  lea     r8, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x180050889  mov     edx, 33h ; '3'
0x18005088e  mov     r9, rax
0x180050891  call    WPP_SF_s
0x180050896  mov     r10, cs:WPP_GLOBAL_Control
0x18005089d  mov     rdi, [rbp+var_10]
0x1800508a1  mov     ebx, 80070490h
0x1800508a6  test    rdi, rdi
0x1800508a9  jz      short loc_1800508BB
0x1800508ab  mov     rcx, rdi; pMemory
0x1800508ae  call    cs:__imp_WlanFreeMemory
0x1800508b4  mov     r10, cs:WPP_GLOBAL_Control
0x1800508bb  cmp     r10, r14
0x1800508be  jz      short loc_1800508EF
0x1800508c0  test    ebx, ebx
0x1800508c2  js      short loc_1800508CB
0x1800508c4  cmp     byte ptr [r10+19h], 6
0x1800508c9  jb      short loc_1800508EF
0x1800508cb  or      ecx, 0FFFFFFFFh; int
0x1800508ce  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800508d3  mov     rcx, [r10+10h]
0x1800508d7  lea     r8, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x1800508de  mov     edx, 34h ; '4'
0x1800508e3  mov     dword ptr [rsp+40h+ppAvailableNetworkList], ebx
0x1800508e7  mov     r9, rax
0x1800508ea  call    WPP_SF_sd
0x1800508ef  mov     eax, ebx
0x1800508f1  lea     r11, [rsp+40h+var_s0]
0x1800508f6  mov     rbx, [r11+38h]
0x1800508fa  mov     rsi, [r11+40h]
0x1800508fe  mov     rsp, r11
0x180050901  pop     r15
0x180050903  pop     r14
0x180050905  pop     r12
0x180050907  pop     rdi
0x180050908  pop     rbp
0x180050909  retn
0x18005090a  xor     ebx, ebx
0x18005090c  lea     r14, WPP_GLOBAL_Control
0x180050913  cmp     [rsi+rdi+268h], ebx
0x18005091a  setnz   al
0x18005091d  mov     [r12], al
0x180050921  mov     r10, cs:WPP_GLOBAL_Control
0x180050928  jmp     loc_1800508A6
```
