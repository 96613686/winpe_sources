# WcnwizWlanMatchNetworkSignature(_GUID const *,_GUID *,_DOT11_SSID *,uint *)

- ea: `0x180027fa0`
- end: `0x18002817e`
- name: `?WcnwizWlanMatchNetworkSignature@@YAJPEBU_GUID@@PEAU1@PEAU_DOT11_SSID@@PEAI@Z`
- size: `478`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _GUID *, struct _DOT11_SSID *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180019dc8`

## callees

- `0x180002294`
- `0x18000e0a0`
- `0x180025fc0`
- `0x180027fa0`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x180028153`
- `wlanapi!WlanCloseHandle` at `0x180028153`
- `wlanapi!WlanOpenHandle` at `0x180027ff5`
- `wlanapi!WlanOpenHandle` at `0x180027ff5`
- `wlanapi!WlanEnumInterfaces` at `0x180028062`
- `wlanapi!WlanEnumInterfaces` at `0x180028062`
- `wlanapi!WlanFreeMemory` at `0x180028141`
- `wlanapi!WlanFreeMemory` at `0x180028141`

## pseudocode

```c
__int64 __fastcall WcnwizWlanMatchNetworkSignature(
        const struct _GUID *a1,
        struct _GUID *a2,
        struct _DOT11_SSID *a3,
        unsigned int *a4)
{
  char v7; // r15
  signed int v8; // eax
  unsigned int v9; // ebx
  signed int MatchingNetworkForSignature; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // ebx
  DWORD i; // edi
  char *v15; // r12
  __int128 v16; // xmm1
  int v17; // eax
  __int128 v18; // xmm0
  void *phClientHandle; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+38h] [rbp-C8h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[512]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+250h] [rbp+150h]
  __int128 v25; // [rsp+260h] [rbp+160h]
  int v26; // [rsp+270h] [rbp+170h]
  unsigned int v27; // [rsp+2B4h] [rbp+1B4h]

  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  ppInterfaceList = 0;
  v7 = 0;
  v8 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    else
      v9 = v8;
    MatchingNetworkForSignature = v9 | 0x80000000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 17;
LABEL_8:
      WPP_SF_Dd(
        v11[2],
        v12,
        WPP_b21d8b9d621e39ee23229db12d609292_Traceguids,
        (unsigned int)v8,
        MatchingNetworkForSignature);
    }
  }
  else
  {
    v8 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
    if ( v8 )
    {
      if ( v8 > 0 )
        v13 = (unsigned __int16)v8 | 0x80070000;
      else
        v13 = v8;
      MatchingNetworkForSignature = v13 | 0x80000000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 18;
        goto LABEL_8;
      }
    }
    else
    {
      MatchingNetworkForSignature = 0;
      for ( i = 0; i < ppInterfaceList->dwNumberOfItems; ++i )
      {
        v15 = (char *)ppInterfaceList + 532 * i;
        memset_0(v23, 0, 0x274u);
        MatchingNetworkForSignature = GetMatchingNetworkForSignature(phClientHandle, (GUID *)(v15 + 8));
        if ( MatchingNetworkForSignature >= 0 )
        {
          v16 = v24;
          v17 = v26;
          *a2 = *(struct _GUID *)(v15 + 8);
          v18 = v25;
          *(_OWORD *)&a3->uSSIDLength = v16;
          *(_OWORD *)&a3->ucSSID[12] = v18;
          *(_DWORD *)&a3->ucSSID[28] = v17;
          if ( a4 )
            *a4 = v27;
          v7 = 1;
          break;
        }
      }
    }
  }
  if ( ppInterfaceList )
    WlanFreeMemory(ppInterfaceList);
  if ( phClientHandle )
    WlanCloseHandle(phClientHandle, 0);
  if ( MatchingNetworkForSignature >= 0 && !v7 )
    return (unsigned int)-2147023728;
  return (unsigned int)MatchingNetworkForSignature;
}

```

## disassembly

```asm
0x180027fa0  mov     [rsp-8+arg_0], rcx
0x180027fa5  push    rbp
0x180027fa6  push    rbx
0x180027fa7  push    rsi
0x180027fa8  push    rdi
0x180027fa9  push    r12
0x180027fab  push    r13
0x180027fad  push    r14
0x180027faf  push    r15
0x180027fb1  lea     rbp, [rsp-1D8h]
0x180027fb9  sub     rsp, 2D8h
0x180027fc0  mov     r13, rdx
0x180027fc3  mov     [rsp+310h+phClientHandle], 0
0x180027fcc  xor     edx, edx; pReserved
0x180027fce  mov     [rsp+310h+pdwNegotiatedVersion], 0
0x180027fd6  mov     r14, r9
0x180027fd9  mov     [rsp+310h+ppInterfaceList], 0
0x180027fe2  mov     rsi, r8
0x180027fe5  lea     r9, [rsp+310h+phClientHandle]; phClientHandle
0x180027fea  lea     r8, [rsp+310h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180027fef  xor     r15b, r15b
0x180027ff2  lea     ecx, [rdx+2]; dwClientVersion
0x180027ff5  call    cs:__imp_WlanOpenHandle
0x180027ffb  test    eax, eax
0x180027ffd  jz      short loc_180028056
0x180027fff  jg      short loc_180028005
0x180028001  mov     ebx, eax
0x180028003  jmp     short loc_18002800E
0x180028005  movzx   ebx, ax
0x180028008  or      ebx, 80070000h
0x18002800e  or      ebx, 80000000h
0x180028014  mov     rcx, cs:WPP_GLOBAL_Control
0x18002801b  lea     rdx, WPP_GLOBAL_Control
0x180028022  cmp     rcx, rdx
0x180028025  jz      loc_180028134
0x18002802b  cmp     byte ptr [rcx+19h], 2
0x18002802f  jb      loc_180028134
0x180028035  mov     edx, 11h
0x18002803a  mov     rcx, [rcx+10h]
0x18002803e  lea     r8, WPP_b21d8b9d621e39ee23229db12d609292_Traceguids
0x180028045  mov     r9d, eax
0x180028048  mov     [rsp+310h+var_2F0], ebx
0x18002804c  call    WPP_SF_Dd
0x180028051  jmp     loc_180028134
0x180028056  mov     rcx, [rsp+310h+phClientHandle]; hClientHandle
0x18002805b  lea     r8, [rsp+310h+ppInterfaceList]; ppInterfaceList
0x180028060  xor     edx, edx; pReserved
0x180028062  call    cs:__imp_WlanEnumInterfaces
0x180028068  test    eax, eax
0x18002806a  jz      short loc_1800280A9
0x18002806c  jg      short loc_180028072
0x18002806e  mov     ebx, eax
0x180028070  jmp     short loc_18002807B
0x180028072  movzx   ebx, ax
0x180028075  or      ebx, 80070000h
0x18002807b  or      ebx, 80000000h
0x180028081  mov     rcx, cs:WPP_GLOBAL_Control
0x180028088  lea     rdx, WPP_GLOBAL_Control
0x18002808f  cmp     rcx, rdx
0x180028092  jz      loc_180028134
0x180028098  cmp     byte ptr [rcx+19h], 2
0x18002809c  jb      loc_180028134
0x1800280a2  mov     edx, 12h
0x1800280a7  jmp     short loc_18002803A
0x1800280a9  xor     ebx, ebx
0x1800280ab  xor     edi, edi
0x1800280ad  mov     rdx, [rsp+310h+ppInterfaceList]
0x1800280b2  cmp     edi, [rdx]
0x1800280b4  jnb     short loc_180028134
0x1800280b6  mov     eax, edi
0x1800280b8  lea     rcx, [rsp+310h+var_2C0]; void *
0x1800280bd  imul    r12, rax, 214h
0x1800280c4  mov     r8d, 274h; Size
0x1800280ca  add     r12, rdx
0x1800280cd  xor     edx, edx; Val
0x1800280cf  call    memset_0
0x1800280d4  mov     r8, [rbp+210h+arg_0]
0x1800280db  lea     r9, [rsp+310h+var_2C0]
0x1800280e0  mov     rcx, [rsp+310h+phClientHandle]; hClientHandle
0x1800280e5  lea     rdx, [r12+8]; pInterfaceGuid
0x1800280ea  call    GetMatchingNetworkForSignature
0x1800280ef  mov     ebx, eax
0x1800280f1  test    eax, eax
0x1800280f3  jns     short loc_1800280F9
0x1800280f5  inc     edi
0x1800280f7  jmp     short loc_1800280AD
0x1800280f9  movaps  xmm1, [rbp+210h+var_C0]
0x180028100  mov     eax, [rbp+210h+var_A0]
0x180028106  movups  xmm0, xmmword ptr [r12+8]
0x18002810c  movdqu  xmmword ptr [r13+0], xmm0
0x180028112  movaps  xmm0, [rbp+210h+var_B0]
0x180028119  movups  xmmword ptr [rsi], xmm1
0x18002811c  movups  xmmword ptr [rsi+10h], xmm0
0x180028120  mov     [rsi+20h], eax
0x180028123  test    r14, r14
0x180028126  jz      short loc_180028131
0x180028128  mov     eax, [rbp+210h+var_5C]
0x18002812e  mov     [r14], eax
0x180028131  mov     r15b, 1
0x180028134  mov     rdx, [rsp+310h+ppInterfaceList]
0x180028139  test    rdx, rdx
0x18002813c  jz      short loc_180028147
0x18002813e  mov     rcx, rdx; pMemory
0x180028141  call    cs:__imp_WlanFreeMemory
0x180028147  mov     rcx, [rsp+310h+phClientHandle]; hClientHandle
0x18002814c  test    rcx, rcx
0x18002814f  jz      short loc_180028159
0x180028151  xor     edx, edx; pReserved
0x180028153  call    cs:__imp_WlanCloseHandle
0x180028159  test    ebx, ebx
0x18002815b  js      short loc_180028168
0x18002815d  test    r15b, r15b
0x180028160  mov     eax, 80070490h
0x180028165  cmovz   ebx, eax
0x180028168  mov     eax, ebx
0x18002816a  add     rsp, 2D8h
0x180028171  pop     r15
0x180028173  pop     r14
0x180028175  pop     r13
0x180028177  pop     r12
0x180028179  pop     rdi
0x18002817a  pop     rsi
0x18002817b  pop     rbx
0x18002817c  pop     rbp
0x18002817d  retn
```
