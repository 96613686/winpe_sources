# MSMSecLogOneXRestart(ushort *,_GUID *,uchar (*)[6],_DOT11_SSID *,_DOT11_BSS_TYPE,uchar (*)[6],_EAP_METHOD_TYPE *,_ONEX_AUTH_RESTART_REASON,void *)

- ea: `0x180026afc`
- end: `0x180026e63`
- name: `?MSMSecLogOneXRestart@@YAKPEAGPEAU_GUID@@PEAY05EPEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@2PEAU_EAP_METHOD_TYPE@@W4_ONEX_AUTH_RESTART_REASON@@PEAX@Z`
- size: `871`
- prototype: `unsigned int(unsigned __int16 *, struct _GUID *, unsigned __int8 (*)[6], struct _DOT11_SSID *, enum _DOT11_BSS_TYPE, unsigned __int8 (*)[6], struct _EAP_METHOD_TYPE *, enum _ONEX_AUTH_RESTART_REASON, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18002a040`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180026afc`
- `0x180027b50`
- `0x180027b8c`
- `0x180043a30`
- `0x18004456c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180026d8e`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180026d8e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180026db7`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180026db7`
- `OneX!OneXRestartReasonCodeToString` at `0x180026c31`
- `OneX!OneXRestartReasonCodeToString` at `0x180026c31`

## pseudocode

```c
__int64 __fastcall MSMSecLogOneXRestart(
        unsigned __int16 *a1,
        struct _GUID *a2,
        unsigned __int8 (*a3)[6],
        struct _DOT11_SSID *a4,
        enum _DOT11_BSS_TYPE a5,
        unsigned __int8 (*a6)[6],
        struct _EAP_METHOD_TYPE *a7,
        enum _ONEX_AUTH_RESTART_REASON a8,
        void *a9)
{
  __int64 v13; // r14
  unsigned int CmnEventFieldsNoPeerMac; // eax
  ULONG v15; // ebx
  PVOID *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v25; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID *v28; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v30; // [rsp+50h] [rbp-B0h]
  int v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+5Ch] [rbp-A4h]
  unsigned __int16 *v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  int v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+7Ch] [rbp-84h]
  __int64 *v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h]
  char *v41; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+98h] [rbp-68h]
  __int64 *v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  char *v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  _WORD *v47; // [rsp+C0h] [rbp-40h]
  int v48; // [rsp+C8h] [rbp-38h]
  int v49; // [rsp+CCh] [rbp-34h]
  void **v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v52[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v53; // [rsp+F0h] [rbp-10h]
  int v54; // [rsp+100h] [rbp+0h]
  unsigned __int16 v55[40]; // [rsp+110h] [rbp+10h] BYREF
  _WORD v56[256]; // [rsp+160h] [rbp+60h] BYREF

  UserData.Ptr = 0;
  memset_0(&UserData.Size, 0, 0xA8u);
  v54 = 0;
  *(_OWORD *)v52 = 0;
  v53 = 0;
  memset_0(v55, 0, 0x42u);
  memset_0(v56, 0, sizeof(v56));
  v13 = Dot11BssTypeStr((unsigned int)a5);
  v25 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids);
  CmnEventFieldsNoPeerMac = MSMSecCreateCmnEventFieldsNoPeerMac(a3, v52, a4, v55);
  v15 = CmnEventFieldsNoPeerMac;
  if ( !CmnEventFieldsNoPeerMac )
  {
    if ( (unsigned int)OneXRestartReasonCodeToString((unsigned int)a8, 256, v56, 0, v25, v26, UserData.Ptr) )
      v56[0] = 0;
    v19 = -1;
    UserData.Ptr = (ULONGLONG)a1;
    v20 = -1;
    do
      ++v20;
    while ( a1[v20] );
    UserData.Reserved = 0;
    UserData.Size = 2 * v20 + 2;
    v28 = a2;
    v30 = v52;
    v21 = -1;
    v29 = 16;
    do
      ++v21;
    while ( v52[v21] );
    v32 = 0;
    v31 = 2 * v21 + 2;
    v33 = v55;
    v22 = -1;
    do
      ++v22;
    while ( v55[v22] );
    v35 = 0;
    v34 = 2 * v22 + 2;
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v13 + 2 * v23) );
    v37 = 2 * v23 + 2;
    v36 = v13;
    v38 = 0;
    LODWORD(v25) = a7->eapType.type;
    HIDWORD(v25) = a7->eapType.dwVendorId;
    v39 = &v25;
    v41 = (char *)&v25 + 4;
    v43 = &v26;
    v45 = (char *)&v26 + 4;
    v47 = v56;
    v40 = 4;
    v42 = 4;
    v44 = 4;
    v46 = 4;
    do
      ++v19;
    while ( v56[v19] );
    v48 = 2 * v19 + 2;
    v49 = 0;
    v50 = &a9;
    v51 = 8;
    if ( EventEnabled(WLANSVC_EVT_GUID_Context, &WlansecOneXRestartEvtDesc) )
    {
      v15 = EventWrite(WLANSVC_EVT_GUID_Context, &WlansecOneXRestartEvtDesc, 0xBu, &UserData);
      if ( !v15 )
        goto LABEL_28;
    }
    else
    {
      v15 = 5023;
    }
    v18 = v15;
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_29;
    v17 = 23;
LABEL_27:
    WPP_SF_d(v16[7], v17, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids, v18);
LABEL_28:
    v16 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_29;
  }
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v17 = 22;
    v18 = CmnEventFieldsNoPeerMac;
    goto LABEL_27;
  }
LABEL_29:
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 17) & 0x100) != 0 )
    WPP_SF_d(v16[7], 24, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180026afc  mov     [rsp-8+arg_0], rbx
0x180026b01  mov     [rsp-8+arg_8], rsi
0x180026b06  push    rbp
0x180026b07  push    rdi
0x180026b08  push    r12
0x180026b0a  push    r14
0x180026b0c  push    r15
0x180026b0e  lea     rbp, [rsp-270h]
0x180026b16  sub     rsp, 370h
0x180026b1d  mov     rax, cs:__security_cookie
0x180026b24  xor     rax, rsp
0x180026b27  mov     [rbp+290h+var_30], rax
0x180026b2e  mov     rbx, r8
0x180026b31  mov     r15, rdx
0x180026b34  mov     rdi, rcx
0x180026b37  xor     r12d, r12d
0x180026b3a  xor     edx, edx; Val
0x180026b3c  mov     [rsp+390h+UserData.Ptr], r12
0x180026b41  mov     r8d, 0A8h; Size
0x180026b47  lea     rcx, [rsp+390h+UserData.Size]; void *
0x180026b4c  mov     rsi, r9
0x180026b4f  call    memset_0
0x180026b54  xorps   xmm0, xmm0
0x180026b57  lea     r8d, [r12+42h]; Size
0x180026b5c  xor     eax, eax
0x180026b5e  lea     rcx, [rbp+290h+var_280]; void *
0x180026b62  xor     edx, edx; Val
0x180026b64  mov     [rbp+290h+var_290], eax
0x180026b67  movups  xmmword ptr [rbp+290h+var_2B0], xmm0
0x180026b6b  movups  [rbp+290h+var_2A0], xmm0
0x180026b6f  call    memset_0
0x180026b74  xor     edx, edx; Val
0x180026b76  lea     rcx, [rbp+290h+var_230]; void *
0x180026b7a  mov     r8d, 200h; Size
0x180026b80  call    memset_0
0x180026b85  mov     ecx, [rbp+290h+arg_20]
0x180026b8b  call    Dot11BssTypeStr
0x180026b90  mov     r14, rax
0x180026b93  mov     [rsp+390h+var_370], r12d
0x180026b98  mov     [rsp+390h+var_36C], r12d
0x180026b9d  mov     [rsp+390h+var_368], r12d
0x180026ba2  mov     [rsp+390h+var_364], r12d
0x180026ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bae  lea     rax, WPP_GLOBAL_Control
0x180026bb5  cmp     rcx, rax
0x180026bb8  jz      short loc_180026BD8
0x180026bba  test    dword ptr [rcx+44h], 100h
0x180026bc1  jz      short loc_180026BD8
0x180026bc3  mov     rcx, [rcx+38h]
0x180026bc7  lea     edx, [r12+15h]
0x180026bcc  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x180026bd3  call    WPP_SF_
0x180026bd8  lea     r9, [rbp+290h+var_280]; unsigned __int16 *
0x180026bdc  mov     r8, rsi; struct _DOT11_SSID *
0x180026bdf  lea     rdx, [rbp+290h+var_2B0]; unsigned __int16 *
0x180026be3  mov     rcx, rbx; unsigned __int8 (*)[6]
0x180026be6  call    ?MSMSecCreateCmnEventFieldsNoPeerMac@@YAKPEAY05EPEAGPEAU_DOT11_SSID@@1@Z; MSMSecCreateCmnEventFieldsNoPeerMac(uchar (*)[6],ushort *,_DOT11_SSID *,ushort *)
0x180026beb  mov     ebx, eax
0x180026bed  test    eax, eax
0x180026bef  jz      short loc_180026C1F
0x180026bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bf8  lea     rdi, WPP_GLOBAL_Control
0x180026bff  cmp     rcx, rdi
0x180026c02  jz      loc_180026E35
0x180026c08  test    byte ptr [rcx+44h], 1
0x180026c0c  jz      loc_180026E0F
0x180026c12  mov     edx, 16h
0x180026c17  mov     r9d, eax
0x180026c1a  jmp     loc_180026DF8
0x180026c1f  mov     ecx, [rbp+290h+arg_38]
0x180026c25  lea     r8, [rbp+290h+var_230]
0x180026c29  xor     r9d, r9d
0x180026c2c  mov     edx, 100h
0x180026c31  call    cs:__imp_OneXRestartReasonCodeToString
0x180026c38  nop     dword ptr [rax+rax+00h]
0x180026c3d  test    eax, eax
0x180026c3f  jz      short loc_180026C46
0x180026c41  mov     [rbp+290h+var_230], r12w
0x180026c46  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180026c4a  mov     [rsp+390h+UserData.Ptr], rdi
0x180026c4f  mov     rax, rdx
0x180026c52  inc     rax
0x180026c55  cmp     [rdi+rax*2], r12w
0x180026c5a  jnz     short loc_180026C52
0x180026c5c  lea     eax, ds:2[rax*2]
0x180026c63  mov     dword ptr [rsp+390h+UserData.0Ch], r12d
0x180026c68  mov     [rsp+390h+UserData.Size], eax
0x180026c6c  lea     rcx, [rbp+290h+var_2B0]
0x180026c70  lea     rax, [rbp+290h+var_2B0]
0x180026c74  mov     [rsp+390h+var_350], r15
0x180026c79  mov     [rsp+390h+var_340], rax
0x180026c7e  mov     rax, rdx
0x180026c81  mov     [rsp+390h+var_348], 10h
0x180026c8a  inc     rax
0x180026c8d  cmp     [rcx+rax*2], r12w
0x180026c92  jnz     short loc_180026C8A
0x180026c94  lea     eax, ds:2[rax*2]
0x180026c9b  mov     [rsp+390h+var_334], r12d
0x180026ca0  mov     [rsp+390h+var_338], eax
0x180026ca4  lea     rcx, [rbp+290h+var_280]
0x180026ca8  lea     rax, [rbp+290h+var_280]
0x180026cac  mov     [rsp+390h+var_330], rax
0x180026cb1  mov     rax, rdx
0x180026cb4  inc     rax
0x180026cb7  cmp     [rcx+rax*2], r12w
0x180026cbc  jnz     short loc_180026CB4
0x180026cbe  lea     eax, ds:2[rax*2]
0x180026cc5  mov     [rsp+390h+var_324], r12d
0x180026cca  mov     [rsp+390h+var_328], eax
0x180026cce  mov     rax, rdx
0x180026cd1  inc     rax
0x180026cd4  cmp     [r14+rax*2], r12w
0x180026cd9  jnz     short loc_180026CD1
0x180026cdb  mov     rcx, [rbp+290h+arg_30]
0x180026ce2  lea     eax, ds:2[rax*2]
0x180026ce9  mov     [rsp+390h+var_318], eax
0x180026ced  mov     [rsp+390h+var_320], r14
0x180026cf2  mov     [rsp+390h+var_314], r12d
0x180026cf7  movzx   eax, byte ptr [rcx]
0x180026cfa  mov     [rsp+390h+var_370], eax
0x180026cfe  mov     eax, [rcx+4]
0x180026d01  mov     [rsp+390h+var_36C], eax
0x180026d05  lea     rax, [rsp+390h+var_370]
0x180026d0a  mov     [rbp+290h+var_310], rax
0x180026d0e  lea     rax, [rsp+390h+var_36C]
0x180026d13  mov     [rbp+290h+var_300], rax
0x180026d17  lea     rax, [rsp+390h+var_368]
0x180026d1c  mov     [rbp+290h+var_2F0], rax
0x180026d20  lea     rax, [rsp+390h+var_364]
0x180026d25  mov     [rbp+290h+var_2E0], rax
0x180026d29  lea     rax, [rbp+290h+var_230]
0x180026d2d  mov     [rbp+290h+var_2D0], rax
0x180026d31  lea     rax, [rbp+290h+var_230]
0x180026d35  mov     [rbp+290h+var_308], 4
0x180026d3d  mov     [rbp+290h+var_2F8], 4
0x180026d45  mov     [rbp+290h+var_2E8], 4
0x180026d4d  mov     [rbp+290h+var_2D8], 4
0x180026d55  inc     rdx
0x180026d58  cmp     [rax+rdx*2], r12w
0x180026d5d  jnz     short loc_180026D55
0x180026d5f  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x180026d66  lea     eax, ds:2[rdx*2]
0x180026d6d  mov     [rbp+290h+var_2C8], eax
0x180026d70  lea     rdx, WlansecOneXRestartEvtDesc; EventDescriptor
0x180026d77  lea     rax, [rbp+290h+arg_40]
0x180026d7e  mov     [rbp+290h+var_2C4], r12d
0x180026d82  mov     [rbp+290h+var_2C0], rax
0x180026d86  mov     [rbp+290h+var_2B8], 8
0x180026d8e  call    cs:__imp_EventEnabled
0x180026d95  nop     dword ptr [rax+rax+00h]
0x180026d9a  test    al, al
0x180026d9c  jz      short loc_180026DD2
0x180026d9e  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x180026da5  lea     r9, [rsp+390h+UserData]; UserData
0x180026daa  mov     r8d, 0Bh; UserDataCount
0x180026db0  lea     rdx, WlansecOneXRestartEvtDesc; EventDescriptor
0x180026db7  call    cs:__imp_EventWrite
0x180026dbe  nop     dword ptr [rax+rax+00h]
0x180026dc3  mov     ebx, eax
0x180026dc5  test    eax, eax
0x180026dc7  jnz     short loc_180026DD7
0x180026dc9  lea     rdi, WPP_GLOBAL_Control
0x180026dd0  jmp     short loc_180026E08
0x180026dd2  mov     ebx, 139Fh
0x180026dd7  mov     r9d, ebx
0x180026dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180026de1  lea     rdi, WPP_GLOBAL_Control
0x180026de8  cmp     rcx, rdi
0x180026deb  jz      short loc_180026E35
0x180026ded  test    byte ptr [rcx+44h], 1
0x180026df1  jz      short loc_180026E0F
0x180026df3  mov     edx, 17h
0x180026df8  mov     rcx, [rcx+38h]
0x180026dfc  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x180026e03  call    WPP_SF_d
0x180026e08  mov     rcx, cs:WPP_GLOBAL_Control
0x180026e0f  cmp     rcx, rdi
0x180026e12  jz      short loc_180026E35
0x180026e14  test    dword ptr [rcx+44h], 100h
0x180026e1b  jz      short loc_180026E35
0x180026e1d  mov     rcx, [rcx+38h]
0x180026e21  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x180026e28  mov     edx, 18h
0x180026e2d  mov     r9d, ebx
0x180026e30  call    WPP_SF_d
0x180026e35  mov     eax, ebx
0x180026e37  mov     rcx, [rbp+290h+var_30]
0x180026e3e  xor     rcx, rsp; StackCookie
0x180026e41  call    __security_check_cookie
0x180026e46  lea     r11, [rsp+390h+var_20]
0x180026e4e  mov     rbx, [r11+30h]
0x180026e52  mov     rsi, [r11+38h]
0x180026e56  mov     rsp, r11
0x180026e59  pop     r15
0x180026e5b  pop     r14
0x180026e5d  pop     r12
0x180026e5f  pop     rdi
0x180026e60  pop     rbp
0x180026e61  retn
```
