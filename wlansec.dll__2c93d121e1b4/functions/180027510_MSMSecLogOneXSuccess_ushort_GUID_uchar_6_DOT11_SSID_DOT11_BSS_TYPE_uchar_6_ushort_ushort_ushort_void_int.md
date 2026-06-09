# MSMSecLogOneXSuccess(ushort *,_GUID *,uchar (*)[6],_DOT11_SSID *,_DOT11_BSS_TYPE,uchar (*)[6],ushort *,ushort *,ushort *,void *,int)

- ea: `0x180027510`
- end: `0x18002782a`
- name: `?MSMSecLogOneXSuccess@@YAKPEAGPEAU_GUID@@PEAY05EPEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@2000PEAXH@Z`
- size: `794`
- prototype: `unsigned int(unsigned __int16 *, struct _GUID *, unsigned __int8 (*)[6], struct _DOT11_SSID *, enum _DOT11_BSS_TYPE, unsigned __int8 (*)[6], unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, void *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180029660`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180027510`
- `0x180027b50`
- `0x180027b8c`
- `0x180043a30`
- `0x18004456c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180027758`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180027758`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180027781`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180027781`

## pseudocode

```c
__int64 __fastcall MSMSecLogOneXSuccess(
        unsigned __int16 *a1,
        struct _GUID *a2,
        unsigned __int8 (*a3)[6],
        struct _DOT11_SSID *a4,
        enum _DOT11_BSS_TYPE a5,
        unsigned __int8 (*a6)[6],
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        void *a10,
        int a11)
{
  __int64 v15; // rsi
  unsigned int CmnEventFieldsNoPeerMac; // eax
  ULONG v17; // ebx
  PVOID *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-E0h] BYREF
  struct _GUID *v30; // [rsp+30h] [rbp-D0h]
  __int64 v31; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v32; // [rsp+40h] [rbp-C0h]
  int v33; // [rsp+48h] [rbp-B8h]
  int v34; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 *v35; // [rsp+50h] [rbp-B0h]
  int v36; // [rsp+58h] [rbp-A8h]
  int v37; // [rsp+5Ch] [rbp-A4h]
  __int64 v38; // [rsp+60h] [rbp-A0h]
  int v39; // [rsp+68h] [rbp-98h]
  int v40; // [rsp+6Ch] [rbp-94h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-90h]
  int v42; // [rsp+78h] [rbp-88h]
  int v43; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 *v44; // [rsp+80h] [rbp-80h]
  int v45; // [rsp+88h] [rbp-78h]
  int v46; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 *v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+98h] [rbp-68h]
  int v49; // [rsp+9Ch] [rbp-64h]
  void **v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+A8h] [rbp-58h]
  int *v52; // [rsp+B0h] [rbp-50h]
  __int64 v53; // [rsp+B8h] [rbp-48h]
  unsigned __int16 v54[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v55; // [rsp+D0h] [rbp-30h]
  int v56; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v57[40]; // [rsp+F0h] [rbp-10h] BYREF

  UserData.Ptr = 0;
  memset_0(&UserData.Size, 0, 0x98u);
  v56 = 0;
  *(_OWORD *)v54 = 0;
  v55 = 0;
  memset_0(v57, 0, 0x42u);
  v15 = Dot11BssTypeStr((unsigned int)a5);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids);
  CmnEventFieldsNoPeerMac = MSMSecCreateCmnEventFieldsNoPeerMac(a3, v54, a4, v57);
  v17 = CmnEventFieldsNoPeerMac;
  if ( !CmnEventFieldsNoPeerMac )
  {
    v21 = -1;
    UserData.Ptr = (ULONGLONG)a1;
    v22 = -1;
    do
      ++v22;
    while ( a1[v22] );
    UserData.Reserved = 0;
    UserData.Size = 2 * v22 + 2;
    v30 = a2;
    v32 = v54;
    v23 = -1;
    v31 = 16;
    do
      ++v23;
    while ( v54[v23] );
    v34 = 0;
    v33 = 2 * v23 + 2;
    v35 = v57;
    v24 = -1;
    do
      ++v24;
    while ( v57[v24] );
    v37 = 0;
    v36 = 2 * v24 + 2;
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)(v15 + 2 * v25) );
    v39 = 2 * v25 + 2;
    v26 = -1;
    v38 = v15;
    v40 = 0;
    v41 = a7;
    do
      ++v26;
    while ( a7[v26] );
    v42 = 2 * v26 + 2;
    v27 = -1;
    v43 = 0;
    v44 = a8;
    do
      ++v27;
    while ( a8[v27] );
    v46 = 0;
    v45 = 2 * v27 + 2;
    v47 = a9;
    do
      ++v21;
    while ( a9[v21] );
    v49 = 0;
    v48 = 2 * v21 + 2;
    v50 = &a10;
    v52 = &a11;
    v51 = 8;
    v53 = 4;
    if ( EventEnabled(WLANSVC_EVT_GUID_Context, &WlansecOneXSuccessEvtDesc) )
    {
      v17 = EventWrite(WLANSVC_EVT_GUID_Context, &WlansecOneXSuccessEvtDesc, 0xAu, &UserData);
      if ( !v17 )
        goto LABEL_30;
    }
    else
    {
      v17 = 5023;
    }
    v20 = v17;
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v17;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_31;
    v19 = 27;
LABEL_29:
    WPP_SF_d(v18[7], v19, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids, v20);
LABEL_30:
    v18 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v17;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v19 = 26;
    v20 = CmnEventFieldsNoPeerMac;
    goto LABEL_29;
  }
LABEL_31:
  if ( v18 != &WPP_GLOBAL_Control && (*((_DWORD *)v18 + 17) & 0x100) != 0 )
    WPP_SF_d(v18[7], 28, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids, v17);
  return v17;
}

```

## disassembly

```asm
0x180027510  mov     [rsp-8+arg_0], rbx
0x180027515  mov     [rsp-8+arg_8], rsi
0x18002751a  push    rbp
0x18002751b  push    rdi
0x18002751c  push    r12
0x18002751e  push    r14
0x180027520  push    r15
0x180027522  lea     rbp, [rsp-50h]
0x180027527  sub     rsp, 150h
0x18002752e  mov     rax, cs:__security_cookie
0x180027535  xor     rax, rsp
0x180027538  mov     [rbp+70h+var_30], rax
0x18002753c  mov     rbx, r8
0x18002753f  mov     r15, rdx
0x180027542  mov     rdi, rcx
0x180027545  xor     r12d, r12d
0x180027548  xor     edx, edx; Val
0x18002754a  mov     [rsp+170h+UserData.Ptr], r12
0x18002754f  mov     r8d, 98h; Size
0x180027555  lea     rcx, [rsp+170h+UserData.Size]; void *
0x18002755a  mov     r14, r9
0x18002755d  call    memset_0
0x180027562  xorps   xmm0, xmm0
0x180027565  lea     r8d, [r12+42h]; Size
0x18002756a  xor     eax, eax
0x18002756c  lea     rcx, [rbp+70h+var_80]; void *
0x180027570  xor     edx, edx; Val
0x180027572  mov     [rbp+70h+var_90], eax
0x180027575  movups  xmmword ptr [rbp+70h+var_B0], xmm0
0x180027579  movups  [rbp+70h+var_A0], xmm0
0x18002757d  call    memset_0
0x180027582  mov     ecx, [rbp+70h+arg_20]
0x180027588  call    Dot11BssTypeStr
0x18002758d  mov     rsi, rax
0x180027590  mov     rcx, cs:WPP_GLOBAL_Control
0x180027597  lea     rax, WPP_GLOBAL_Control
0x18002759e  cmp     rcx, rax
0x1800275a1  jz      short loc_1800275C1
0x1800275a3  test    dword ptr [rcx+44h], 100h
0x1800275aa  jz      short loc_1800275C1
0x1800275ac  mov     rcx, [rcx+38h]
0x1800275b0  lea     edx, [r12+19h]
0x1800275b5  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x1800275bc  call    WPP_SF_
0x1800275c1  lea     r9, [rbp+70h+var_80]; unsigned __int16 *
0x1800275c5  mov     r8, r14; struct _DOT11_SSID *
0x1800275c8  lea     rdx, [rbp+70h+var_B0]; unsigned __int16 *
0x1800275cc  mov     rcx, rbx; unsigned __int8 (*)[6]
0x1800275cf  call    ?MSMSecCreateCmnEventFieldsNoPeerMac@@YAKPEAY05EPEAGPEAU_DOT11_SSID@@1@Z; MSMSecCreateCmnEventFieldsNoPeerMac(uchar (*)[6],ushort *,_DOT11_SSID *,ushort *)
0x1800275d4  mov     ebx, eax
0x1800275d6  test    eax, eax
0x1800275d8  jz      short loc_180027608
0x1800275da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275e1  lea     rdi, WPP_GLOBAL_Control
0x1800275e8  cmp     rcx, rdi
0x1800275eb  jz      loc_1800277FF
0x1800275f1  test    byte ptr [rcx+44h], 1
0x1800275f5  jz      loc_1800277D9
0x1800275fb  mov     edx, 1Ah
0x180027600  mov     r9d, eax
0x180027603  jmp     loc_1800277C2
0x180027608  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002760c  mov     [rsp+170h+UserData.Ptr], rdi
0x180027611  mov     rax, rcx
0x180027614  inc     rax
0x180027617  cmp     [rdi+rax*2], r12w
0x18002761c  jnz     short loc_180027614
0x18002761e  lea     eax, ds:2[rax*2]
0x180027625  mov     dword ptr [rsp+170h+UserData.0Ch], r12d
0x18002762a  mov     [rsp+170h+UserData.Size], eax
0x18002762e  lea     rdx, [rbp+70h+var_B0]
0x180027632  lea     rax, [rbp+70h+var_B0]
0x180027636  mov     [rsp+170h+var_140], r15
0x18002763b  mov     [rsp+170h+var_130], rax
0x180027640  mov     rax, rcx
0x180027643  mov     [rsp+170h+var_138], 10h
0x18002764c  inc     rax
0x18002764f  cmp     [rdx+rax*2], r12w
0x180027654  jnz     short loc_18002764C
0x180027656  lea     eax, ds:2[rax*2]
0x18002765d  mov     [rsp+170h+var_124], r12d
0x180027662  mov     [rsp+170h+var_128], eax
0x180027666  lea     rdx, [rbp+70h+var_80]
0x18002766a  lea     rax, [rbp+70h+var_80]
0x18002766e  mov     [rsp+170h+var_120], rax
0x180027673  mov     rax, rcx
0x180027676  inc     rax
0x180027679  cmp     [rdx+rax*2], r12w
0x18002767e  jnz     short loc_180027676
0x180027680  lea     eax, ds:2[rax*2]
0x180027687  mov     [rsp+170h+var_114], r12d
0x18002768c  mov     [rsp+170h+var_118], eax
0x180027690  mov     rax, rcx
0x180027693  inc     rax
0x180027696  cmp     [rsi+rax*2], r12w
0x18002769b  jnz     short loc_180027693
0x18002769d  mov     rdx, [rbp+70h+arg_30]
0x1800276a4  lea     eax, ds:2[rax*2]
0x1800276ab  mov     [rsp+170h+var_108], eax
0x1800276af  mov     rax, rcx
0x1800276b2  mov     [rsp+170h+var_110], rsi
0x1800276b7  mov     [rsp+170h+var_104], r12d
0x1800276bc  mov     [rsp+170h+var_100], rdx
0x1800276c1  inc     rax
0x1800276c4  cmp     [rdx+rax*2], r12w
0x1800276c9  jnz     short loc_1800276C1
0x1800276cb  mov     rdx, [rbp+70h+arg_38]
0x1800276d2  lea     eax, ds:2[rax*2]
0x1800276d9  mov     [rsp+170h+var_F8], eax
0x1800276dd  mov     rax, rcx
0x1800276e0  mov     [rsp+170h+var_F4], r12d
0x1800276e5  mov     [rbp+70h+var_F0], rdx
0x1800276e9  inc     rax
0x1800276ec  cmp     [rdx+rax*2], r12w
0x1800276f1  jnz     short loc_1800276E9
0x1800276f3  lea     eax, ds:2[rax*2]
0x1800276fa  mov     [rbp+70h+var_E4], r12d
0x1800276fe  mov     [rbp+70h+var_E8], eax
0x180027701  mov     rax, [rbp+70h+arg_40]
0x180027708  mov     [rbp+70h+var_E0], rax
0x18002770c  inc     rcx
0x18002770f  cmp     [rax+rcx*2], r12w
0x180027714  jnz     short loc_18002770C
0x180027716  lea     eax, ds:2[rcx*2]
0x18002771d  mov     [rbp+70h+var_D4], r12d
0x180027721  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x180027728  lea     rdx, WlansecOneXSuccessEvtDesc; EventDescriptor
0x18002772f  mov     [rbp+70h+var_D8], eax
0x180027732  lea     rax, [rbp+70h+arg_48]
0x180027739  mov     [rbp+70h+var_D0], rax
0x18002773d  lea     rax, [rbp+70h+arg_50]
0x180027744  mov     [rbp+70h+var_C0], rax
0x180027748  mov     [rbp+70h+var_C8], 8
0x180027750  mov     [rbp+70h+var_B8], 4
0x180027758  call    cs:__imp_EventEnabled
0x18002775f  nop     dword ptr [rax+rax+00h]
0x180027764  test    al, al
0x180027766  jz      short loc_18002779C
0x180027768  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x18002776f  lea     r9, [rsp+170h+UserData]; UserData
0x180027774  mov     r8d, 0Ah; UserDataCount
0x18002777a  lea     rdx, WlansecOneXSuccessEvtDesc; EventDescriptor
0x180027781  call    cs:__imp_EventWrite
0x180027788  nop     dword ptr [rax+rax+00h]
0x18002778d  mov     ebx, eax
0x18002778f  test    eax, eax
0x180027791  jnz     short loc_1800277A1
0x180027793  lea     rdi, WPP_GLOBAL_Control
0x18002779a  jmp     short loc_1800277D2
0x18002779c  mov     ebx, 139Fh
0x1800277a1  mov     r9d, ebx
0x1800277a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277ab  lea     rdi, WPP_GLOBAL_Control
0x1800277b2  cmp     rcx, rdi
0x1800277b5  jz      short loc_1800277FF
0x1800277b7  test    byte ptr [rcx+44h], 1
0x1800277bb  jz      short loc_1800277D9
0x1800277bd  mov     edx, 1Bh
0x1800277c2  mov     rcx, [rcx+38h]
0x1800277c6  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x1800277cd  call    WPP_SF_d
0x1800277d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277d9  cmp     rcx, rdi
0x1800277dc  jz      short loc_1800277FF
0x1800277de  test    dword ptr [rcx+44h], 100h
0x1800277e5  jz      short loc_1800277FF
0x1800277e7  mov     rcx, [rcx+38h]
0x1800277eb  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x1800277f2  mov     edx, 1Ch
0x1800277f7  mov     r9d, ebx
0x1800277fa  call    WPP_SF_d
0x1800277ff  mov     eax, ebx
0x180027801  mov     rcx, [rbp+70h+var_30]
0x180027805  xor     rcx, rsp; StackCookie
0x180027808  call    __security_check_cookie
0x18002780d  lea     r11, [rsp+170h+var_20]
0x180027815  mov     rbx, [r11+30h]
0x180027819  mov     rsi, [r11+38h]
0x18002781d  mov     rsp, r11
0x180027820  pop     r15
0x180027822  pop     r14
0x180027824  pop     r12
0x180027826  pop     rdi
0x180027827  pop     rbp
0x180027828  retn
```
