# MSMSecLogOneXStart(ushort *,_GUID *,uchar (*)[6],_DOT11_SSID *,_DOT11_BSS_TYPE,uchar (*)[6],_EAP_METHOD_TYPE *,void *)

- ea: `0x180027830`
- end: `0x180027b4a`
- name: `?MSMSecLogOneXStart@@YAKPEAGPEAU_GUID@@PEAY05EPEAU_DOT11_SSID@@W4_DOT11_BSS_TYPE@@2PEAU_EAP_METHOD_TYPE@@PEAX@Z`
- size: `794`
- prototype: `unsigned int(unsigned __int16 *, struct _GUID *, unsigned __int8 (*)[6], struct _DOT11_SSID *, enum _DOT11_BSS_TYPE, unsigned __int8 (*)[6], struct _EAP_METHOD_TYPE *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180026e70`

## callees

- `0x18000892c`
- `0x180008998`
- `0x180027830`
- `0x180027b50`
- `0x180027b8c`
- `0x180043a30`
- `0x18004456c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180027a19`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180027a19`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180027a42`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180027a42`

## pseudocode

```c
__int64 __fastcall MSMSecLogOneXStart(
        unsigned __int16 *a1,
        struct _GUID *a2,
        unsigned __int8 (*a3)[6],
        struct _DOT11_SSID *a4,
        enum _DOT11_BSS_TYPE a5,
        unsigned __int8 (*a6)[6],
        struct _EAP_METHOD_TYPE *a7,
        void *a8)
{
  __int64 v12; // r14
  unsigned int CmnEventFieldsNoPeerMac; // eax
  ULONG v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  PVOID *v19; // rcx
  __int64 v21; // r9
  __int64 v22; // rdx
  int type; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwVendorId; // [rsp+24h] [rbp-DCh] BYREF
  int v25; // [rsp+28h] [rbp-D8h] BYREF
  int v26; // [rsp+2Ch] [rbp-D4h] BYREF
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
  int *p_type; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h]
  DWORD *p_dwVendorId; // [rsp+90h] [rbp-70h]
  __int64 v42; // [rsp+98h] [rbp-68h]
  int *v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  int *v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  void **v47; // [rsp+C0h] [rbp-40h]
  __int64 v48; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v49[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v52[40]; // [rsp+100h] [rbp+0h] BYREF

  UserData.Ptr = 0;
  memset_0(&UserData.Size, 0, 0x98u);
  v51 = 0;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  memset_0(v52, 0, 0x42u);
  v12 = Dot11BssTypeStr((unsigned int)a5);
  type = 0;
  dwVendorId = 0;
  v25 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids);
  CmnEventFieldsNoPeerMac = MSMSecCreateCmnEventFieldsNoPeerMac(a3, v49, a4, v52);
  v14 = CmnEventFieldsNoPeerMac;
  if ( CmnEventFieldsNoPeerMac )
  {
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v14;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_14;
    v22 = 18;
    v21 = CmnEventFieldsNoPeerMac;
    goto LABEL_20;
  }
  v15 = -1;
  UserData.Ptr = (ULONGLONG)a1;
  v16 = -1;
  do
    ++v16;
  while ( a1[v16] );
  UserData.Reserved = 0;
  UserData.Size = 2 * v16 + 2;
  v28 = a2;
  v30 = v49;
  v17 = -1;
  v29 = 16;
  do
    ++v17;
  while ( v49[v17] );
  v32 = 0;
  v31 = 2 * v17 + 2;
  v33 = v52;
  v18 = -1;
  do
    ++v18;
  while ( v52[v18] );
  v35 = 0;
  v34 = 2 * v18 + 2;
  do
    ++v15;
  while ( *(_WORD *)(v12 + 2 * v15) );
  v36 = v12;
  v37 = 2 * v15 + 2;
  v38 = 0;
  v40 = 4;
  type = a7->eapType.type;
  dwVendorId = a7->eapType.dwVendorId;
  p_type = &type;
  p_dwVendorId = &dwVendorId;
  v43 = &v25;
  v45 = &v26;
  v47 = &a8;
  v42 = 4;
  v44 = 4;
  v46 = 4;
  v48 = 8;
  if ( EventEnabled(WLANSVC_EVT_GUID_Context, &WlansecOneXStartEvtDesc) )
  {
    v14 = EventWrite(WLANSVC_EVT_GUID_Context, &WlansecOneXStartEvtDesc, 0xAu, &UserData);
    if ( !v14 )
    {
LABEL_13:
      v19 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_14;
    }
  }
  else
  {
    v14 = 5023;
  }
  v21 = v14;
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v22 = 19;
LABEL_20:
    WPP_SF_d(v19[7], v22, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids, v21);
    goto LABEL_13;
  }
LABEL_14:
  if ( v19 != &WPP_GLOBAL_Control && (*((_DWORD *)v19 + 17) & 0x100) != 0 )
    WPP_SF_d(v19[7], 20, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180027830  mov     [rsp-8+arg_0], rbx
0x180027835  mov     [rsp-8+arg_8], rsi
0x18002783a  push    rbp
0x18002783b  push    rdi
0x18002783c  push    r12
0x18002783e  push    r14
0x180027840  push    r15
0x180027842  lea     rbp, [rsp-60h]
0x180027847  sub     rsp, 160h
0x18002784e  mov     rax, cs:__security_cookie
0x180027855  xor     rax, rsp
0x180027858  mov     [rbp+80h+var_30], rax
0x18002785c  mov     rbx, r8
0x18002785f  mov     r15, rdx
0x180027862  mov     rdi, rcx
0x180027865  xor     r12d, r12d
0x180027868  xor     edx, edx; Val
0x18002786a  mov     [rsp+180h+UserData.Ptr], r12
0x18002786f  mov     r8d, 98h; Size
0x180027875  lea     rcx, [rsp+180h+UserData.Size]; void *
0x18002787a  mov     rsi, r9
0x18002787d  call    memset_0
0x180027882  xorps   xmm0, xmm0
0x180027885  lea     r8d, [r12+42h]; Size
0x18002788a  xor     eax, eax
0x18002788c  lea     rcx, [rbp+80h+var_80]; void *
0x180027890  xor     edx, edx; Val
0x180027892  mov     [rbp+80h+var_90], eax
0x180027895  movups  xmmword ptr [rbp+80h+var_B0], xmm0
0x180027899  movups  [rbp+80h+var_A0], xmm0
0x18002789d  call    memset_0
0x1800278a2  mov     ecx, [rbp+80h+arg_20]
0x1800278a8  call    Dot11BssTypeStr
0x1800278ad  mov     r14, rax
0x1800278b0  mov     [rsp+180h+var_160], r12d
0x1800278b5  mov     [rsp+180h+var_15C], r12d
0x1800278ba  mov     [rsp+180h+var_158], r12d
0x1800278bf  mov     [rsp+180h+var_154], r12d
0x1800278c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278cb  lea     rax, WPP_GLOBAL_Control
0x1800278d2  cmp     rcx, rax
0x1800278d5  jnz     loc_180027ACE
0x1800278db  lea     r9, [rbp+80h+var_80]; unsigned __int16 *
0x1800278df  mov     r8, rsi; struct _DOT11_SSID *
0x1800278e2  lea     rdx, [rbp+80h+var_B0]; unsigned __int16 *
0x1800278e6  mov     rcx, rbx; unsigned __int8 (*)[6]
0x1800278e9  call    ?MSMSecCreateCmnEventFieldsNoPeerMac@@YAKPEAY05EPEAGPEAU_DOT11_SSID@@1@Z; MSMSecCreateCmnEventFieldsNoPeerMac(uchar (*)[6],ushort *,_DOT11_SSID *,ushort *)
0x1800278ee  mov     ebx, eax
0x1800278f0  test    eax, eax
0x1800278f2  jnz     loc_180027AF5
0x1800278f8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800278fc  mov     [rsp+180h+UserData.Ptr], rdi
0x180027901  mov     rax, rcx
0x180027904  inc     rax
0x180027907  cmp     [rdi+rax*2], r12w
0x18002790c  jnz     short loc_180027904
0x18002790e  lea     eax, ds:2[rax*2]
0x180027915  mov     dword ptr [rsp+180h+UserData.0Ch], r12d
0x18002791a  mov     [rsp+180h+UserData.Size], eax
0x18002791e  lea     rdx, [rbp+80h+var_B0]
0x180027922  lea     rax, [rbp+80h+var_B0]
0x180027926  mov     [rsp+180h+var_140], r15
0x18002792b  mov     [rsp+180h+var_130], rax
0x180027930  mov     rax, rcx
0x180027933  mov     [rsp+180h+var_138], 10h
0x18002793c  inc     rax
0x18002793f  cmp     [rdx+rax*2], r12w
0x180027944  jnz     short loc_18002793C
0x180027946  lea     eax, ds:2[rax*2]
0x18002794d  mov     [rsp+180h+var_124], r12d
0x180027952  mov     [rsp+180h+var_128], eax
0x180027956  lea     rdx, [rbp+80h+var_80]
0x18002795a  lea     rax, [rbp+80h+var_80]
0x18002795e  mov     [rsp+180h+var_120], rax
0x180027963  mov     rax, rcx
0x180027966  inc     rax
0x180027969  cmp     [rdx+rax*2], r12w
0x18002796e  jnz     short loc_180027966
0x180027970  lea     eax, ds:2[rax*2]
0x180027977  mov     [rsp+180h+var_114], r12d
0x18002797c  mov     [rsp+180h+var_118], eax
0x180027980  inc     rcx
0x180027983  cmp     [r14+rcx*2], r12w
0x180027988  jnz     short loc_180027980
0x18002798a  lea     eax, ds:2[rcx*2]
0x180027991  mov     [rsp+180h+var_110], r14
0x180027996  mov     rcx, [rbp+80h+arg_30]
0x18002799d  lea     rdx, WlansecOneXStartEvtDesc; EventDescriptor
0x1800279a4  mov     [rsp+180h+var_108], eax
0x1800279a8  mov     [rsp+180h+var_104], r12d
0x1800279ad  mov     [rbp+80h+var_F8], 4
0x1800279b5  movzx   eax, byte ptr [rcx]
0x1800279b8  mov     [rsp+180h+var_160], eax
0x1800279bc  mov     eax, [rcx+4]
0x1800279bf  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x1800279c6  mov     [rsp+180h+var_15C], eax
0x1800279ca  lea     rax, [rsp+180h+var_160]
0x1800279cf  mov     [rbp+80h+var_100], rax
0x1800279d3  lea     rax, [rsp+180h+var_15C]
0x1800279d8  mov     [rbp+80h+var_F0], rax
0x1800279dc  lea     rax, [rsp+180h+var_158]
0x1800279e1  mov     [rbp+80h+var_E0], rax
0x1800279e5  lea     rax, [rsp+180h+var_154]
0x1800279ea  mov     [rbp+80h+var_D0], rax
0x1800279ee  lea     rax, [rbp+80h+arg_38]
0x1800279f5  mov     [rbp+80h+var_C0], rax
0x1800279f9  mov     [rbp+80h+var_E8], 4
0x180027a01  mov     [rbp+80h+var_D8], 4
0x180027a09  mov     [rbp+80h+var_C8], 4
0x180027a11  mov     [rbp+80h+var_B8], 8
0x180027a19  call    cs:__imp_EventEnabled
0x180027a20  nop     dword ptr [rax+rax+00h]
0x180027a25  test    al, al
0x180027a27  jz      short loc_180027A96
0x180027a29  mov     rcx, cs:WLANSVC_EVT_GUID_Context; RegHandle
0x180027a30  lea     r9, [rsp+180h+UserData]; UserData
0x180027a35  mov     r8d, 0Ah; UserDataCount
0x180027a3b  lea     rdx, WlansecOneXStartEvtDesc; EventDescriptor
0x180027a42  call    cs:__imp_EventWrite
0x180027a49  nop     dword ptr [rax+rax+00h]
0x180027a4e  mov     ebx, eax
0x180027a50  test    eax, eax
0x180027a52  jnz     short loc_180027A9B
0x180027a54  lea     rdi, WPP_GLOBAL_Control
0x180027a5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a62  cmp     rcx, rdi
0x180027a65  jnz     loc_180027B20
0x180027a6b  mov     eax, ebx
0x180027a6d  mov     rcx, [rbp+80h+var_30]
0x180027a71  xor     rcx, rsp; StackCookie
0x180027a74  call    __security_check_cookie
0x180027a79  lea     r11, [rsp+180h+var_20]
0x180027a81  mov     rbx, [r11+30h]
0x180027a85  mov     rsi, [r11+38h]
0x180027a89  mov     rsp, r11
0x180027a8c  pop     r15
0x180027a8e  pop     r14
0x180027a90  pop     r12
0x180027a92  pop     rdi
0x180027a93  pop     rbp
0x180027a94  retn
0x180027a96  mov     ebx, 139Fh
0x180027a9b  mov     r9d, ebx
0x180027a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027aa5  lea     rdi, WPP_GLOBAL_Control
0x180027aac  cmp     rcx, rdi
0x180027aaf  jz      short loc_180027A6B
0x180027ab1  test    byte ptr [rcx+44h], 1
0x180027ab5  jz      short loc_180027A62
0x180027ab7  mov     edx, 13h
0x180027abc  mov     rcx, [rcx+38h]
0x180027ac0  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x180027ac7  call    WPP_SF_d
0x180027acc  jmp     short loc_180027A5B
0x180027ace  test    dword ptr [rcx+44h], 100h
0x180027ad5  jz      loc_1800278DB
0x180027adb  mov     rcx, [rcx+38h]
0x180027adf  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x180027ae6  mov     edx, 11h
0x180027aeb  call    WPP_SF_
0x180027af0  jmp     loc_1800278DB
0x180027af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180027afc  lea     rdi, WPP_GLOBAL_Control
0x180027b03  cmp     rcx, rdi
0x180027b06  jz      loc_180027A6B
0x180027b0c  test    byte ptr [rcx+44h], 1
0x180027b10  jz      loc_180027A62
0x180027b16  mov     edx, 12h
0x180027b1b  mov     r9d, eax
0x180027b1e  jmp     short loc_180027ABC
0x180027b20  test    dword ptr [rcx+44h], 100h
0x180027b27  jz      loc_180027A6B
0x180027b2d  mov     rcx, [rcx+38h]
0x180027b31  lea     r8, WPP_9fb5e4a96850369dcc444dddefb9c61b_Traceguids
0x180027b38  mov     edx, 14h
0x180027b3d  mov     r9d, ebx
0x180027b40  call    WPP_SF_d
0x180027b45  jmp     loc_180027A6B
```
