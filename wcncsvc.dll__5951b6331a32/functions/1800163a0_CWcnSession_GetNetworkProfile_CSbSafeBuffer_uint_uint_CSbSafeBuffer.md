# CWcnSession::GetNetworkProfile(CSbSafeBuffer *,uint *,uint *,CSbSafeBuffer *)

- ea: `0x1800163a0`
- end: `0x180016851`
- name: `?GetNetworkProfile@CWcnSession@@QEAAJPEAVCSbSafeBuffer@@PEAI10@Z`
- size: `1201`
- prototype: `__int64 __fastcall(CWcnSession *this, struct CSbSafeBuffer *, unsigned int *, unsigned int *, struct CSbSafeBuffer *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180036c40`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x1800163a0`
- `0x18001a974`
- `0x18001ab1c`
- `0x18001d050`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800164c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800164c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800167f5`

## string_xrefs

- `0x18001643b`: `pSsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CWcnSession::GetNetworkProfile(
        CWcnSession *this,
        struct CSbSafeBuffer *a2,
        unsigned int *a3,
        unsigned int *a4,
        struct CSbSafeBuffer *a5)
{
  _BYTE *v9; // r10
  const char *Indent; // rax
  __int64 v11; // r10
  __int64 v12; // r11
  __int64 v13; // rdx
  const char *v14; // r9
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  int Attribute; // eax
  int v18; // ebx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  const char *v21; // rax
  __int64 v22; // r10
  __int64 v23; // rdx
  unsigned int v24; // eax
  __int64 v25; // r10
  struct CWcnAttribute *v26; // [rsp+30h] [rbp-20h] BYREF
  struct CWcnAttribute *v27; // [rsp+38h] [rbp-18h] BYREF
  struct CWcnAttribute *v28; // [rsp+40h] [rbp-10h] BYREF
  struct CWcnAttribute *v29; // [rsp+48h] [rbp-8h] BYREF
  __int64 v30; // [rsp+88h] [rbp+38h] BYREF

  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v11 + 16), 80, v12, Indent);
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 81;
    v14 = "pSsid";
LABEL_20:
    WPP_SF_s(*((_QWORD *)v9 + 2), v13, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v14);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 82;
    v14 = "pWcnAuthType";
    goto LABEL_20;
  }
  if ( !a4 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 83;
    v14 = "pWcnCipherType";
    goto LABEL_20;
  }
  if ( !a5 )
  {
    if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 2u )
      return 2147500035LL;
    v13 = 84;
    v14 = "pNetworkKey";
    goto LABEL_20;
  }
  v16 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 4) + 16LL);
  v30 = 60;
  EnterCriticalSection(v16);
  Attribute = CWcnAttributeDatabase::FindAttribute(
                (CWcnSession *)((char *)this + 160),
                (const struct CWcnAttributeDatabase::AttributeSearchPattern *)&v30,
                &v26);
  v18 = Attribute;
  if ( Attribute < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v20 = 85;
    goto LABEL_26;
  }
  if ( Attribute == 1 )
  {
    v18 = -2147023728;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v21 = GetIndent(0);
    v23 = 86;
    goto LABEL_31;
  }
  Attribute = CWcnAttribute::GetValueAsBlob(v26, a2);
  v18 = Attribute;
  if ( Attribute < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v20 = 87;
    goto LABEL_26;
  }
  LODWORD(v30) = 2;
  Attribute = CWcnAttributeDatabase::FindAttribute(
                (CWcnSession *)((char *)this + 160),
                (const struct CWcnAttributeDatabase::AttributeSearchPattern *)&v30,
                &v27);
  v18 = Attribute;
  if ( Attribute < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v20 = 88;
    goto LABEL_26;
  }
  if ( Attribute == 1 )
  {
    v18 = -2147023728;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v21 = GetIndent(0);
    v23 = 89;
    goto LABEL_31;
  }
  Attribute = CWcnAttribute::GetValueAsInteger(v27, a3);
  v18 = Attribute;
  if ( Attribute < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v20 = 90;
    goto LABEL_26;
  }
  LODWORD(v30) = 19;
  Attribute = CWcnAttributeDatabase::FindAttribute(
                (CWcnSession *)((char *)this + 160),
                (const struct CWcnAttributeDatabase::AttributeSearchPattern *)&v30,
                &v28);
  v18 = Attribute;
  if ( Attribute < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v20 = 91;
    goto LABEL_26;
  }
  if ( Attribute == 1 )
  {
    v18 = -2147023728;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v21 = GetIndent(0);
    v23 = 92;
    goto LABEL_31;
  }
  Attribute = CWcnAttribute::GetValueAsInteger(v28, a4);
  v18 = Attribute;
  if ( Attribute < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v20 = 93;
    goto LABEL_26;
  }
  LODWORD(v30) = 33;
  Attribute = CWcnAttributeDatabase::FindAttribute(
                (CWcnSession *)((char *)this + 160),
                (const struct CWcnAttributeDatabase::AttributeSearchPattern *)&v30,
                &v29);
  v18 = Attribute;
  if ( Attribute < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v20 = 94;
    goto LABEL_26;
  }
  if ( Attribute != 1 )
  {
    Attribute = CWcnAttribute::GetValueAsBlob(v29, a5);
    v18 = Attribute;
    if ( Attribute >= 0 )
      goto LABEL_72;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_72;
    v20 = 96;
LABEL_26:
    WPP_SF_d(v19[2], v20, WPP_a137d119f5dc35a130051116e3170526_Traceguids, (unsigned int)Attribute);
    goto LABEL_72;
  }
  v18 = -2147023728;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    goto LABEL_72;
  v21 = GetIndent(0);
  v23 = 95;
LABEL_31:
  WPP_SF_s(*(_QWORD *)(v22 + 16), v23, WPP_a137d119f5dc35a130051116e3170526_Traceguids, v21);
LABEL_72:
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 4) + 16LL));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v18 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v24 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v25 + 16), 97, (unsigned int)WPP_a137d119f5dc35a130051116e3170526_Traceguids, v24, v18);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800163a0  mov     [rsp-28h+arg_0], rbx
0x1800163a5  mov     [rsp-28h+arg_10], rsi
0x1800163aa  push    rbp
0x1800163ab  push    rdi
0x1800163ac  push    r12
0x1800163ae  push    r13
0x1800163b0  push    r15
0x1800163b2  mov     rbp, rsp
0x1800163b5  sub     rsp, 50h
0x1800163b9  xor     ebx, ebx
0x1800163bb  mov     r12, r9
0x1800163be  mov     [rbp+var_20], rbx
0x1800163c2  mov     r15, r8
0x1800163c5  mov     [rbp+var_18], rbx
0x1800163c9  mov     rsi, rdx
0x1800163cc  mov     [rbp+var_10], rbx
0x1800163d0  mov     r13, rcx
0x1800163d3  mov     [rbp+var_8], rbx
0x1800163d7  mov     r10, cs:WPP_GLOBAL_Control
0x1800163de  lea     rax, WPP_GLOBAL_Control
0x1800163e5  lea     r11, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x1800163ec  cmp     r10, rax
0x1800163ef  jz      short loc_180016427
0x1800163f1  cmp     byte ptr [r10+19h], 6
0x1800163f6  jb      short loc_180016427
0x1800163f8  lea     ecx, [rbx+1]; int
0x1800163fb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016400  mov     rcx, [r10+10h]
0x180016404  lea     edx, [rbx+50h]
0x180016407  mov     r9, rax
0x18001640a  mov     r8, r11
0x18001640d  call    WPP_SF_s
0x180016412  mov     r10, cs:WPP_GLOBAL_Control
0x180016419  lea     rax, WPP_GLOBAL_Control
0x180016420  lea     r11, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180016427  test    rsi, rsi
0x18001642a  jnz     short loc_180016444
0x18001642c  cmp     r10, rax
0x18001642f  jz      short loc_1800164AB
0x180016431  cmp     byte ptr [r10+19h], 2
0x180016436  jb      short loc_1800164AB
0x180016438  lea     edx, [rsi+51h]
0x18001643b  lea     r9, aPssid; "pSsid"
0x180016442  jmp     short loc_18001649F
0x180016444  test    r15, r15
0x180016447  jnz     short loc_180016462
0x180016449  cmp     r10, rax
0x18001644c  jz      short loc_1800164AB
0x18001644e  cmp     byte ptr [r10+19h], 2
0x180016453  jb      short loc_1800164AB
0x180016455  lea     edx, [r15+52h]
0x180016459  lea     r9, aPwcnauthtype; "pWcnAuthType"
0x180016460  jmp     short loc_18001649F
0x180016462  test    r12, r12
0x180016465  jnz     short loc_180016481
0x180016467  cmp     r10, rax
0x18001646a  jz      short loc_1800164AB
0x18001646c  cmp     byte ptr [r10+19h], 2
0x180016471  jb      short loc_1800164AB
0x180016473  lea     edx, [r12+53h]
0x180016478  lea     r9, aPwcnciphertype; "pWcnCipherType"
0x18001647f  jmp     short loc_18001649F
0x180016481  cmp     [rbp+arg_20], rbx
0x180016485  jnz     short loc_1800164B5
0x180016487  cmp     r10, rax
0x18001648a  jz      short loc_1800164AB
0x18001648c  cmp     byte ptr [r10+19h], 2
0x180016491  jb      short loc_1800164AB
0x180016493  mov     edx, 54h ; 'T'
0x180016498  lea     r9, aPnetworkkey; "pNetworkKey"
0x18001649f  mov     rcx, [r10+10h]
0x1800164a3  mov     r8, r11
0x1800164a6  call    WPP_SF_s
0x1800164ab  mov     eax, 80004003h
0x1800164b0  jmp     loc_180016838
0x1800164b5  mov     rcx, [r13+20h]
0x1800164b9  add     rcx, 10h; lpCriticalSection
0x1800164bd  mov     [rbp+arg_8], 3Ch ; '<'
0x1800164c5  call    cs:__imp_EnterCriticalSection
0x1800164cb  lea     rdi, [r13+0A0h]
0x1800164d2  mov     rcx, rdi; this
0x1800164d5  lea     r8, [rbp+var_20]; struct CWcnAttribute **
0x1800164d9  lea     rdx, [rbp+arg_8]; struct CWcnAttributeDatabase::AttributeSearchPattern *
0x1800164dd  call    ?FindAttribute@CWcnAttributeDatabase@@QEBAJPEBUAttributeSearchPattern@1@PEAPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::FindAttribute(CWcnAttributeDatabase::AttributeSearchPattern const *,CWcnAttribute const * *)
0x1800164e2  mov     ebx, eax
0x1800164e4  test    eax, eax
0x1800164e6  jns     short loc_180016526
0x1800164e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800164ef  lea     rdi, WPP_GLOBAL_Control
0x1800164f6  cmp     rcx, rdi
0x1800164f9  jz      loc_1800167ED
0x1800164ff  cmp     byte ptr [rcx+19h], 2
0x180016503  jb      loc_1800167ED
0x180016509  mov     edx, 55h ; 'U'
0x18001650e  mov     rcx, [rcx+10h]
0x180016512  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180016519  mov     r9d, eax
0x18001651c  call    WPP_SF_d
0x180016521  jmp     loc_1800167ED
0x180016526  cmp     eax, 1
0x180016529  jnz     short loc_180016576
0x18001652b  mov     ebx, 80070490h
0x180016530  mov     r10, cs:WPP_GLOBAL_Control
0x180016537  lea     rdi, WPP_GLOBAL_Control
0x18001653e  cmp     r10, rdi
0x180016541  jz      loc_1800167ED
0x180016547  cmp     byte ptr [r10+19h], 2
0x18001654c  jb      loc_1800167ED
0x180016552  xor     ecx, ecx; int
0x180016554  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016559  mov     edx, 56h ; 'V'
0x18001655e  mov     rcx, [r10+10h]
0x180016562  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180016569  mov     r9, rax
0x18001656c  call    WPP_SF_s
0x180016571  jmp     loc_1800167ED
0x180016576  mov     rcx, [rbp+var_20]; this
0x18001657a  mov     rdx, rsi; struct CSbSafeBuffer *
0x18001657d  call    ?GetValueAsBlob@CWcnAttribute@@QEBAJPEAVCSbSafeBuffer@@@Z; CWcnAttribute::GetValueAsBlob(CSbSafeBuffer *)
0x180016582  mov     ebx, eax
0x180016584  test    eax, eax
0x180016586  jns     short loc_1800165B3
0x180016588  mov     rcx, cs:WPP_GLOBAL_Control
0x18001658f  lea     rdi, WPP_GLOBAL_Control
0x180016596  cmp     rcx, rdi
0x180016599  jz      loc_1800167ED
0x18001659f  cmp     byte ptr [rcx+19h], 2
0x1800165a3  jb      loc_1800167ED
0x1800165a9  mov     edx, 57h ; 'W'
0x1800165ae  jmp     loc_18001650E
0x1800165b3  lea     r8, [rbp+var_18]; struct CWcnAttribute **
0x1800165b7  mov     dword ptr [rbp+arg_8], 2
0x1800165be  lea     rdx, [rbp+arg_8]; struct CWcnAttributeDatabase::AttributeSearchPattern *
0x1800165c2  mov     rcx, rdi; this
0x1800165c5  call    ?FindAttribute@CWcnAttributeDatabase@@QEBAJPEBUAttributeSearchPattern@1@PEAPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::FindAttribute(CWcnAttributeDatabase::AttributeSearchPattern const *,CWcnAttribute const * *)
0x1800165ca  mov     ebx, eax
0x1800165cc  test    eax, eax
0x1800165ce  jns     short loc_1800165FB
0x1800165d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165d7  lea     rdi, WPP_GLOBAL_Control
0x1800165de  cmp     rcx, rdi
0x1800165e1  jz      loc_1800167ED
0x1800165e7  cmp     byte ptr [rcx+19h], 2
0x1800165eb  jb      loc_1800167ED
0x1800165f1  mov     edx, 58h ; 'X'
0x1800165f6  jmp     loc_18001650E
0x1800165fb  cmp     eax, 1
0x1800165fe  jnz     short loc_180016638
0x180016600  mov     ebx, 80070490h
0x180016605  mov     r10, cs:WPP_GLOBAL_Control
0x18001660c  lea     rdi, WPP_GLOBAL_Control
0x180016613  cmp     r10, rdi
0x180016616  jz      loc_1800167ED
0x18001661c  cmp     byte ptr [r10+19h], 2
0x180016621  jb      loc_1800167ED
0x180016627  xor     ecx, ecx; int
0x180016629  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001662e  mov     edx, 59h ; 'Y'
0x180016633  jmp     loc_18001655E
0x180016638  mov     rcx, [rbp+var_18]; this
0x18001663c  mov     rdx, r15; unsigned int *
0x18001663f  call    ?GetValueAsInteger@CWcnAttribute@@QEBAJPEAI@Z; CWcnAttribute::GetValueAsInteger(uint *)
0x180016644  mov     ebx, eax
0x180016646  test    eax, eax
0x180016648  jns     short loc_180016675
0x18001664a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016651  lea     rdi, WPP_GLOBAL_Control
0x180016658  cmp     rcx, rdi
0x18001665b  jz      loc_1800167ED
0x180016661  cmp     byte ptr [rcx+19h], 2
0x180016665  jb      loc_1800167ED
0x18001666b  mov     edx, 5Ah ; 'Z'
0x180016670  jmp     loc_18001650E
0x180016675  lea     r8, [rbp+var_10]; struct CWcnAttribute **
0x180016679  mov     dword ptr [rbp+arg_8], 13h
0x180016680  lea     rdx, [rbp+arg_8]; struct CWcnAttributeDatabase::AttributeSearchPattern *
0x180016684  mov     rcx, rdi; this
0x180016687  call    ?FindAttribute@CWcnAttributeDatabase@@QEBAJPEBUAttributeSearchPattern@1@PEAPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::FindAttribute(CWcnAttributeDatabase::AttributeSearchPattern const *,CWcnAttribute const * *)
0x18001668c  mov     ebx, eax
0x18001668e  test    eax, eax
0x180016690  jns     short loc_1800166BD
0x180016692  mov     rcx, cs:WPP_GLOBAL_Control
0x180016699  lea     rdi, WPP_GLOBAL_Control
0x1800166a0  cmp     rcx, rdi
0x1800166a3  jz      loc_1800167ED
0x1800166a9  cmp     byte ptr [rcx+19h], 2
0x1800166ad  jb      loc_1800167ED
0x1800166b3  mov     edx, 5Bh ; '['
0x1800166b8  jmp     loc_18001650E
0x1800166bd  cmp     eax, 1
0x1800166c0  jnz     short loc_1800166FA
0x1800166c2  mov     ebx, 80070490h
0x1800166c7  mov     r10, cs:WPP_GLOBAL_Control
0x1800166ce  lea     rdi, WPP_GLOBAL_Control
0x1800166d5  cmp     r10, rdi
0x1800166d8  jz      loc_1800167ED
0x1800166de  cmp     byte ptr [r10+19h], 2
0x1800166e3  jb      loc_1800167ED
0x1800166e9  xor     ecx, ecx; int
0x1800166eb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800166f0  mov     edx, 5Ch ; '\'
0x1800166f5  jmp     loc_18001655E
0x1800166fa  mov     rcx, [rbp+var_10]; this
0x1800166fe  mov     rdx, r12; unsigned int *
0x180016701  call    ?GetValueAsInteger@CWcnAttribute@@QEBAJPEAI@Z; CWcnAttribute::GetValueAsInteger(uint *)
0x180016706  mov     ebx, eax
0x180016708  test    eax, eax
0x18001670a  jns     short loc_180016737
0x18001670c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016713  lea     rdi, WPP_GLOBAL_Control
0x18001671a  cmp     rcx, rdi
0x18001671d  jz      loc_1800167ED
0x180016723  cmp     byte ptr [rcx+19h], 2
0x180016727  jb      loc_1800167ED
0x18001672d  mov     edx, 5Dh ; ']'
0x180016732  jmp     loc_18001650E
0x180016737  lea     r8, [rbp+var_8]; struct CWcnAttribute **
0x18001673b  mov     dword ptr [rbp+arg_8], 21h ; '!'
0x180016742  lea     rdx, [rbp+arg_8]; struct CWcnAttributeDatabase::AttributeSearchPattern *
0x180016746  mov     rcx, rdi; this
0x180016749  call    ?FindAttribute@CWcnAttributeDatabase@@QEBAJPEBUAttributeSearchPattern@1@PEAPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::FindAttribute(CWcnAttributeDatabase::AttributeSearchPattern const *,CWcnAttribute const * *)
0x18001674e  mov     ebx, eax
0x180016750  test    eax, eax
0x180016752  jns     short loc_18001677B
0x180016754  mov     rcx, cs:WPP_GLOBAL_Control
0x18001675b  lea     rdi, WPP_GLOBAL_Control
0x180016762  cmp     rcx, rdi
0x180016765  jz      loc_1800167ED
0x18001676b  cmp     byte ptr [rcx+19h], 2
0x18001676f  jb      short loc_1800167ED
0x180016771  mov     edx, 5Eh ; '^'
0x180016776  jmp     loc_18001650E
0x18001677b  cmp     eax, 1
0x18001677e  jnz     short loc_1800167B0
0x180016780  mov     ebx, 80070490h
0x180016785  mov     r10, cs:WPP_GLOBAL_Control
0x18001678c  lea     rdi, WPP_GLOBAL_Control
0x180016793  cmp     r10, rdi
0x180016796  jz      short loc_1800167ED
0x180016798  cmp     byte ptr [r10+19h], 2
0x18001679d  jb      short loc_1800167ED
0x18001679f  xor     ecx, ecx; int
0x1800167a1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800167a6  mov     edx, 5Fh ; '_'
0x1800167ab  jmp     loc_18001655E
0x1800167b0  mov     rdx, [rbp+arg_20]; struct CSbSafeBuffer *
0x1800167b4  mov     rcx, [rbp+var_8]; this
0x1800167b8  call    ?GetValueAsBlob@CWcnAttribute@@QEBAJPEAVCSbSafeBuffer@@@Z; CWcnAttribute::GetValueAsBlob(CSbSafeBuffer *)
0x1800167bd  mov     ebx, eax
0x1800167bf  test    eax, eax
0x1800167c1  jns     short loc_1800167E6
0x1800167c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167ca  lea     rdi, WPP_GLOBAL_Control
0x1800167d1  cmp     rcx, rdi
0x1800167d4  jz      short loc_1800167ED
0x1800167d6  cmp     byte ptr [rcx+19h], 2
0x1800167da  jb      short loc_1800167ED
0x1800167dc  mov     edx, 60h ; '`'
0x1800167e1  jmp     loc_18001650E
0x1800167e6  lea     rdi, WPP_GLOBAL_Control
0x1800167ed  mov     rcx, [r13+20h]
0x1800167f1  add     rcx, 10h; lpCriticalSection
0x1800167f5  call    cs:__imp_LeaveCriticalSection
0x1800167fb  mov     r10, cs:WPP_GLOBAL_Control
0x180016802  cmp     r10, rdi
0x180016805  jz      short loc_180016836
0x180016807  test    ebx, ebx
0x180016809  js      short loc_180016812
0x18001680b  cmp     byte ptr [r10+19h], 6
0x180016810  jb      short loc_180016836
0x180016812  or      ecx, 0FFFFFFFFh; int
0x180016815  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001681a  mov     rcx, [r10+10h]
0x18001681e  lea     r8, WPP_a137d119f5dc35a130051116e3170526_Traceguids
0x180016825  mov     edx, 61h ; 'a'
0x18001682a  mov     [rsp+50h+var_30], ebx
0x18001682e  mov     r9, rax
0x180016831  call    WPP_SF_sd
0x180016836  mov     eax, ebx
0x180016838  lea     r11, [rsp+50h+var_s0]
0x18001683d  mov     rbx, [r11+30h]
0x180016841  mov     rsi, [r11+40h]
0x180016845  mov     rsp, r11
0x180016848  pop     r15
0x18001684a  pop     r13
0x18001684c  pop     r12
0x18001684e  pop     rdi
0x18001684f  pop     rbp
0x180016850  retn
```
