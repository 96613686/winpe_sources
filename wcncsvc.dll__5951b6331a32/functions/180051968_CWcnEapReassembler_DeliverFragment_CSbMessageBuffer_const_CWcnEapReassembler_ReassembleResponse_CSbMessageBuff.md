# CWcnEapReassembler::DeliverFragment(CSbMessageBuffer const *,CWcnEapReassembler::ReassembleResponse *,CSbMessageBuffer *)

- ea: `0x180051968`
- end: `0x180052113`
- name: `?DeliverFragment@CWcnEapReassembler@@QEAAJPEBVCSbMessageBuffer@@PEAW4ReassembleResponse@1@PEAV2@@Z`
- size: `1963`
- prototype: `__int64 __fastcall(UUID *this, const struct CSbMessageBuffer *, enum CWcnEapReassembler::ReassembleResponse *, UUID *)`
- caller_count: `4`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800471a0`
- `0x180049f10`
- `0x18004be80`
- `0x18004f150`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x180005088`
- `0x18000862c`
- `0x18000a74c`
- `0x18000a994`
- `0x180051968`
- `0x18005211c`
- `0x1800521e8`
- `0x180053004`
- `0x180056e30`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180051fac`
- `RPCRT4!UuidCreate` at `0x180051fac`

## string_xrefs

- `0x180051a0e`: `pIncomingFragment`

## pseudocode

```c
__int64 __fastcall CWcnEapReassembler::DeliverFragment(
        UUID *this,
        const struct CSbMessageBuffer *a2,
        enum CWcnEapReassembler::ReassembleResponse *a3,
        UUID *a4)
{
  _BYTE *v7; // r10
  const char *Indent; // rax
  __int64 v9; // r10
  __int64 v10; // rdx
  const char *v11; // r9
  _QWORD *v13; // rcx
  _QWORD *v14; // r11
  __int64 *v15; // r14
  int v16; // ecx
  char v17; // r9
  unsigned __int32 v18; // r15d
  __int64 v19; // r8
  unsigned int v20; // ebx
  _QWORD *v21; // r10
  const char *v22; // rax
  __int64 v23; // r10
  unsigned int v24; // eax
  _BYTE *v25; // r11
  __int64 v26; // r10
  __int64 v27; // xmm6_8
  int v28; // r14d
  unsigned __int16 v29; // ax
  char v30; // r15
  unsigned int v31; // eax
  char v32; // r11
  _QWORD *v33; // rax
  __int64 v34; // rcx
  int v35; // eax
  __int64 v36; // rdx
  UUID v37; // xmm0
  unsigned int v38; // r12d
  unsigned int v39; // eax
  __int64 v40; // r10
  int v41; // r11d
  __int64 v42; // r15
  unsigned __int8 *Data4; // r14
  unsigned int v44; // eax
  __int64 v45; // r10
  int v46; // edx
  int v47; // r8d
  char v48; // r11
  unsigned int v49; // eax
  char v50; // r11
  _QWORD *v51; // rcx
  const char *v52; // rax
  __int64 v53; // r10
  unsigned int v54; // eax
  __int64 v55; // r10
  unsigned int v56; // eax
  __int64 v57; // r10
  int v58; // edx
  int v59; // r8d
  unsigned int v60; // eax
  __int64 v61; // r10
  char v62; // r11
  unsigned int v63; // eax
  __int64 v64; // r10
  __int64 v65; // [rsp+50h] [rbp-41h]
  char v66; // [rsp+60h] [rbp-31h]
  enum CWcnEapReassembler::ReassembleResponse *v67; // [rsp+68h] [rbp-29h]
  unsigned __int8 v68[4]; // [rsp+70h] [rbp-21h] BYREF
  int v69; // [rsp+74h] [rbp-1Dh]
  unsigned __int8 v70[8]; // [rsp+78h] [rbp-19h] BYREF
  int v71; // [rsp+80h] [rbp-11h]

  v67 = a3;
  *(_QWORD *)v70 = 0;
  v71 = 0;
  *(_DWORD *)v68 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v9 + 16), 10, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids, Indent);
    v7 = WPP_GLOBAL_Control;
    a3 = v67;
  }
  if ( !a2 )
  {
    if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || v7[25] < 2u )
      return 2147500035LL;
    v10 = 11;
    v11 = "pIncomingFragment";
LABEL_16:
    WPP_SF_s(*((_QWORD *)v7 + 2), v10, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids, v11);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || v7[25] < 2u )
      return 2147500035LL;
    v10 = 12;
    v11 = "pResponseAction";
    goto LABEL_16;
  }
  if ( !a4 )
  {
    if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || v7[25] < 2u )
      return 2147500035LL;
    v10 = 13;
    v11 = "pResponseBuffer";
    goto LABEL_16;
  }
  *(_DWORD *)a3 = 0;
  v13 = (_QWORD *)*((_QWORD *)a2 + 3);
  v14 = v13 + 1;
  if ( !v13 || *v14 - *v13 < 0xAu )
  {
    v20 = -2147176439;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v20;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_100;
    v60 = (unsigned int)GetIndent(0);
    WPP_SF_sPP(*(_QWORD *)(v61 + 16), 14, (unsigned int)WPP_92c646ccb9143535ae7e38580a538a95_Traceguids, v60, v62, 10);
    goto LABEL_99;
  }
  v15 = (__int64 *)*v13;
  v16 = *(unsigned __int8 *)(*v13 + 1LL);
  v17 = *((_BYTE *)v15 + 9);
  BYTE2(v65) = *((_BYTE *)v15 + 2);
  BYTE1(v65) = v16;
  BYTE3(v65) = *((_BYTE *)v15 + 3);
  HIDWORD(v65) = *((_DWORD *)v15 + 1);
  LOBYTE(v65) = *(_BYTE *)v15;
  v66 = *((_BYTE *)v15 + 8);
  v69 = (v16 << 16) + (BYTE2(v65) << 8) + BYTE3(v65);
  v18 = _byteswap_ulong(HIDWORD(v65));
  if ( (_BYTE)v65 != 0xFE || v18 != 1 || (v16 << 16) + (BYTE2(v65) << 8) + BYTE3(v65) != 14122 )
  {
    v20 = -2147176438;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v20;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_100;
    v56 = (unsigned int)GetIndent(0);
    WPP_SF_sDDDD(*(_QWORD *)(v57 + 16), v58, v59, v56, v18, v69);
    goto LABEL_99;
  }
  v19 = 10;
  if ( (v17 & 2) == 0 )
  {
    v27 = v65;
    v30 = v17;
LABEL_40:
    v33 = (_QWORD *)*((_QWORD *)a2 + 3);
    if ( v33 )
      v34 = v33[1] - *v33;
    else
      v34 = 0;
    v35 = CSbSafeBuffer::PushToBack((CSbSafeBuffer *)&this[2], (const unsigned __int8 *)(v19 + *v33), v34 - v19);
    v20 = v35;
    if ( v35 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v20;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_100;
      v36 = 19;
      goto LABEL_47;
    }
    v37 = (UUID)*((_OWORD *)a2 + 2);
    v38 = ++this[1].Data1;
    this[4] = v37;
    if ( v38 > 0x14 )
    {
      v20 = -2147023604;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_100;
        v39 = (unsigned int)GetIndent(0);
        WPP_SF_sld(
          *(_QWORD *)(v40 + 16),
          v41,
          (unsigned int)WPP_92c646ccb9143535ae7e38580a538a95_Traceguids,
          v39,
          v38,
          v41);
        goto LABEL_28;
      }
      return v20;
    }
    if ( (v30 & 1) != 0 )
    {
      *(_QWORD *)v70 = v27;
      v71 = 6;
      v35 = CSbSafeBuffer::PushToBack((CSbSafeBuffer *)a4, v68, 4u);
      v20 = v35;
      if ( v35 >= 0 )
      {
        v35 = CSbSafeBuffer::PushToBack((CSbSafeBuffer *)a4, v70, 0xAu);
        v20 = v35;
        if ( v35 >= 0 )
        {
          UuidCreate(a4 + 2);
          *(_DWORD *)v67 = 1;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
              goto LABEL_100;
            v54 = (unsigned int)GetIndent(0);
            WPP_SF_sd(
              *(_QWORD *)(v55 + 16),
              24,
              (unsigned int)WPP_92c646ccb9143535ae7e38580a538a95_Traceguids,
              v54,
              this[1].Data1);
            goto LABEL_28;
          }
          return v20;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v20;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_100;
        v36 = 23;
      }
      else
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v20;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_100;
        v36 = 22;
      }
LABEL_47:
      WPP_SF_d(v21[2], v36, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids, (unsigned int)v35);
      goto LABEL_28;
    }
    v42 = *(_QWORD *)this[1].Data4;
    Data4 = this[3].Data4;
    if ( v42 && (!*(_QWORD *)Data4 || *(_QWORD *)(*(_QWORD *)Data4 + 8LL) - **(_QWORD **)Data4 != v42) )
    {
      v20 = -2147176440;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_100;
        v44 = (unsigned int)GetIndent(0);
        WPP_SF_sPPD(*(_QWORD *)(v45 + 16), v46, v47, v44, v48, v42, v38);
        goto LABEL_28;
      }
      return v20;
    }
    switch ( v66 )
    {
      case 1:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v52 = GetIndent(0);
          WPP_SF_s(*(_QWORD *)(v53 + 16), 25, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids, v52);
        }
        *(_DWORD *)v67 = 3;
        *(_QWORD *)this[1].Data4 = 0;
        this[1].Data1 = 0;
        if ( *(_QWORD *)Data4 )
          *(_QWORD *)(*(_QWORD *)Data4 + 8LL) = **(_QWORD **)Data4;
        LOBYTE(this[3].Data1) = 1;
        goto LABEL_28;
      case 2:
      case 3:
      case 4:
      case 5:
        a4[2] = this[4];
        v35 = CSbSafeBuffer::CopyFromBuffer((CSbSafeBuffer *)a4, (const struct CSbSafeBuffer *)&this[2]);
        v20 = v35;
        if ( v35 < 0 )
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
            return v20;
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_100;
          v36 = 26;
          goto LABEL_47;
        }
        *(_QWORD *)this[1].Data4 = 0;
        this[1].Data1 = 0;
        v51 = *(_QWORD **)this[3].Data4;
        if ( v51 )
          v51[1] = *v51;
        LOBYTE(this[3].Data1) = 1;
        *(_DWORD *)v67 = 4;
        break;
      case 6:
        v20 = -2147467263;
        break;
      default:
        v20 = -2147176438;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_100;
          v49 = (unsigned int)GetIndent(0);
          WPP_SF_sd(*(_QWORD *)(v55 + 16), 27, (unsigned int)WPP_92c646ccb9143535ae7e38580a538a95_Traceguids, v49, v50);
          goto LABEL_28;
        }
        return v20;
    }
LABEL_99:
    v21 = WPP_GLOBAL_Control;
    goto LABEL_100;
  }
  if ( !this[1].Data1 )
  {
    if ( *v14 - (_QWORD)v15 < 0xDu )
    {
      v20 = -2147176439;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_100;
        v24 = (unsigned int)GetIndent(0);
        WPP_SF_sPP(
          *(_QWORD *)(v26 + 16),
          17,
          (unsigned int)WPP_92c646ccb9143535ae7e38580a538a95_Traceguids,
          v24,
          *v25 - (_BYTE)v15,
          12);
        goto LABEL_28;
      }
      return v20;
    }
    v27 = *v15;
    v28 = *((_DWORD *)v15 + 2);
    v29 = __ROR2__(HIWORD(v28), 8);
    *(_QWORD *)this[1].Data4 = v29;
    if ( v29 > 0x2800uLL || (v19 = 12, !v29) )
    {
      v20 = -2147023604;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_100;
        v31 = (unsigned int)GetIndent(0);
        WPP_SF_sPP(
          *(_QWORD *)(v26 + 16),
          18,
          (unsigned int)WPP_92c646ccb9143535ae7e38580a538a95_Traceguids,
          v31,
          v32,
          0);
        goto LABEL_28;
      }
      return v20;
    }
    v30 = BYTE1(v28);
    v66 = v28;
    goto LABEL_40;
  }
  v20 = -2147176438;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_100:
      if ( v21 != &WPP_GLOBAL_Control && ((v20 & 0x80000000) != 0 || *((_BYTE *)v21 + 25) >= 6u) )
      {
        v63 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v64 + 16), 28, (unsigned int)WPP_92c646ccb9143535ae7e38580a538a95_Traceguids, v63, v20);
      }
      return v20;
    }
    v22 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v23 + 16), 16, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids, v22);
LABEL_28:
    v21 = WPP_GLOBAL_Control;
    goto LABEL_100;
  }
  return v20;
}

```

## disassembly

```asm
0x180051968  mov     rax, rsp
0x18005196b  push    rbp
0x18005196c  push    rbx
0x18005196d  push    rsi
0x18005196e  push    rdi
0x18005196f  push    r12
0x180051971  push    r13
0x180051973  push    r14
0x180051975  push    r15
0x180051977  lea     rbp, [rax-5Fh]
0x18005197b  sub     rsp, 0A8h
0x180051982  movaps  xmmword ptr [rax-58h], xmm6
0x180051986  mov     rax, cs:__security_cookie
0x18005198d  xor     rax, rsp
0x180051990  mov     [rbp+57h+var_60], rax
0x180051994  xor     eax, eax
0x180051996  mov     [rbp+57h+var_80], r8
0x18005199a  mov     word ptr [rbp+57h+var_90+2], ax
0x18005199e  mov     r13, r9
0x1800519a1  mov     qword ptr [rbp+57h+var_70], rax
0x1800519a5  mov     r12, rdx
0x1800519a8  mov     [rbp+57h+var_68], eax
0x1800519ab  mov     rsi, rcx
0x1800519ae  mov     dword ptr [rbp+57h+var_78], eax
0x1800519b1  mov     r10, cs:WPP_GLOBAL_Control
0x1800519b8  lea     rdi, WPP_GLOBAL_Control
0x1800519bf  lea     ebx, [rax+0Ah]
0x1800519c2  cmp     r10, rdi
0x1800519c5  jz      short loc_1800519F6
0x1800519c7  cmp     byte ptr [r10+19h], 6
0x1800519cc  jb      short loc_1800519F6
0x1800519ce  lea     ecx, [rax+1]; int
0x1800519d1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800519d6  mov     rcx, [r10+10h]
0x1800519da  lea     r8, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids
0x1800519e1  mov     edx, ebx
0x1800519e3  mov     r9, rax
0x1800519e6  call    WPP_SF_s
0x1800519eb  mov     r10, cs:WPP_GLOBAL_Control
0x1800519f2  mov     r8, [rbp+57h+var_80]
0x1800519f6  test    r12, r12
0x1800519f9  jnz     short loc_180051A17
0x1800519fb  cmp     r10, rdi
0x1800519fe  jz      short loc_180051A65
0x180051a00  mov     dil, 2
0x180051a03  cmp     [r10+19h], dil
0x180051a07  jb      short loc_180051A65
0x180051a09  lea     edx, [r12+0Bh]
0x180051a0e  lea     r9, aPincomingfragm; "pIncomingFragment"
0x180051a15  jmp     short loc_180051A55
0x180051a17  test    r8, r8
0x180051a1a  jnz     short loc_180051A37
0x180051a1c  cmp     r10, rdi
0x180051a1f  jz      short loc_180051A65
0x180051a21  mov     dil, 2
0x180051a24  cmp     [r10+19h], dil
0x180051a28  jb      short loc_180051A65
0x180051a2a  lea     edx, [r8+0Ch]
0x180051a2e  lea     r9, aPresponseactio; "pResponseAction"
0x180051a35  jmp     short loc_180051A55
0x180051a37  test    r13, r13
0x180051a3a  jnz     short loc_180051A6F
0x180051a3c  cmp     r10, rdi
0x180051a3f  jz      short loc_180051A65
0x180051a41  mov     dil, 2
0x180051a44  cmp     [r10+19h], dil
0x180051a48  jb      short loc_180051A65
0x180051a4a  lea     edx, [r13+0Dh]
0x180051a4e  lea     r9, aPresponsebuffe; "pResponseBuffer"
0x180051a55  mov     rcx, [r10+10h]
0x180051a59  lea     r8, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids
0x180051a60  call    WPP_SF_s
0x180051a65  mov     eax, 80004003h
0x180051a6a  jmp     loc_1800520EB
0x180051a6f  mov     dword ptr [r8], 0
0x180051a76  mov     rcx, [r12+18h]
0x180051a7b  lea     r11, [rcx+8]
0x180051a7f  test    rcx, rcx
0x180051a82  jz      loc_18005204C
0x180051a88  mov     rax, [r11]
0x180051a8b  sub     rax, [rcx]
0x180051a8e  cmp     rax, rbx
0x180051a91  jb      loc_18005204C
0x180051a97  mov     r14, [rcx]
0x180051a9a  movzx   ecx, byte ptr [r14+1]
0x180051a9f  movzx   edx, byte ptr [r14+2]
0x180051aa4  movzx   eax, byte ptr [r14+3]
0x180051aa9  mov     r8b, [r14]
0x180051aac  mov     r15d, [r14+4]
0x180051ab0  mov     r10b, [r14+8]
0x180051ab4  mov     r9b, [r14+9]
0x180051ab8  mov     byte ptr [rbp+57h+var_98+2], dl
0x180051abb  shl     edx, 8
0x180051abe  mov     byte ptr [rbp+57h+var_98+1], cl
0x180051ac1  shl     ecx, 10h
0x180051ac4  add     edx, ecx
0x180051ac6  mov     byte ptr [rbp+57h+var_98+3], al
0x180051ac9  add     eax, edx
0x180051acb  mov     dword ptr [rbp+57h+var_98+4], r15d
0x180051acf  mov     byte ptr [rbp+57h+var_98], r8b
0x180051ad3  mov     dword ptr [rbp+57h+var_88], r10d
0x180051ad7  mov     byte ptr [rbp+57h+var_90], r10b
0x180051adb  mov     [rbp+57h+var_A0], r9b
0x180051adf  mov     byte ptr [rbp+57h+var_90+1], r9b
0x180051ae3  mov     [rbp+57h+var_74], eax
0x180051ae6  bswap   r15d
0x180051ae9  cmp     r8b, 0FEh
0x180051aed  jnz     loc_180052009
0x180051af3  cmp     r15d, 1
0x180051af7  jnz     loc_180052009
0x180051afd  cmp     eax, 372Ah
0x180051b02  jnz     loc_180052009
0x180051b08  mov     dil, 2
0x180051b0b  mov     r8, rbx
0x180051b0e  test    dil, r9b
0x180051b11  jz      loc_180051C54
0x180051b17  cmp     dword ptr [rsi+10h], 0
0x180051b1b  jbe     short loc_180051B6D
0x180051b1d  mov     ebx, 8004B00Ah
0x180051b22  mov     r10, cs:WPP_GLOBAL_Control
0x180051b29  lea     r13, WPP_GLOBAL_Control
0x180051b30  cmp     r10, r13
0x180051b33  jz      loc_1800520E9
0x180051b39  cmp     [r10+19h], dil
0x180051b3d  jb      loc_1800520B5
0x180051b43  xor     ecx, ecx; int
0x180051b45  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180051b4a  mov     rcx, [r10+10h]
0x180051b4e  lea     edx, [r15+0Fh]
0x180051b52  mov     r9, rax
0x180051b55  lea     r8, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids
0x180051b5c  call    WPP_SF_s
0x180051b61  mov     r10, cs:WPP_GLOBAL_Control
0x180051b68  jmp     loc_1800520B5
0x180051b6d  mov     rax, [r11]
0x180051b70  sub     rax, r14
0x180051b73  cmp     rax, 0Dh
0x180051b77  jnb     short loc_180051BD4
0x180051b79  mov     ebx, 8004B009h
0x180051b7e  mov     r10, cs:WPP_GLOBAL_Control
0x180051b85  lea     r13, WPP_GLOBAL_Control
0x180051b8c  cmp     r10, r13
0x180051b8f  jz      loc_1800520E9
0x180051b95  cmp     [r10+19h], dil
0x180051b99  jb      loc_1800520B5
0x180051b9f  xor     ecx, ecx; int
0x180051ba1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180051ba6  mov     rcx, [r11]
0x180051ba9  mov     edx, 11h
0x180051bae  sub     rcx, r14
0x180051bb1  lea     r8d, [rdx-5]
0x180051bb5  mov     qword ptr [rsp+0E0h+var_B8], r8
0x180051bba  mov     [rsp+0E0h+var_C0], rcx
0x180051bbf  mov     rcx, [r10+10h]
0x180051bc3  lea     r8, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids
0x180051bca  mov     r9, rax
0x180051bcd  call    WPP_SF_sPP
0x180051bd2  jmp     short loc_180051B61
0x180051bd4  movsd   xmm6, qword ptr [r14]
0x180051bd9  mov     r15d, 2800h
0x180051bdf  mov     r14d, [r14+8]
0x180051be3  mov     eax, r14d
0x180051be6  shr     eax, 10h
0x180051be9  ror     ax, 8
0x180051bed  movzx   r11d, ax
0x180051bf1  mov     [rbp+57h+var_90], r14d
0x180051bf5  mov     [rsi+18h], r11
0x180051bf9  cmp     r11, r15
0x180051bfc  ja      short loc_180051C13
0x180051bfe  mov     r8d, 0Ch
0x180051c04  test    r11, r11
0x180051c07  jz      short loc_180051C13
0x180051c09  mov     r15b, byte ptr [rbp+57h+var_90+1]
0x180051c0d  mov     dword ptr [rbp+57h+var_88], r14d
0x180051c11  jmp     short loc_180051C5D
0x180051c13  mov     ebx, 8007050Ch
0x180051c18  mov     r10, cs:WPP_GLOBAL_Control
0x180051c1f  lea     r13, WPP_GLOBAL_Control
0x180051c26  cmp     r10, r13
0x180051c29  jz      loc_1800520E9
0x180051c2f  cmp     [r10+19h], dil
0x180051c33  jb      loc_1800520B5
0x180051c39  xor     ecx, ecx; int
0x180051c3b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180051c40  mov     qword ptr [rsp+0E0h+var_B8], r15
0x180051c45  mov     edx, 12h
0x180051c4a  mov     [rsp+0E0h+var_C0], r11
0x180051c4f  jmp     loc_180051BBF
0x180051c54  movsd   xmm6, [rbp+57h+var_98]
0x180051c59  mov     r15b, [rbp+57h+var_A0]
0x180051c5d  mov     rax, [r12+18h]
0x180051c62  test    rax, rax
0x180051c65  jz      short loc_180051C70
0x180051c67  mov     rcx, [rax+8]
0x180051c6b  sub     rcx, [rax]
0x180051c6e  jmp     short loc_180051C72
0x180051c70  xor     ecx, ecx
0x180051c72  mov     rdx, [rax]
0x180051c75  sub     rcx, r8
0x180051c78  add     rdx, r8; unsigned __int8 *
0x180051c7b  mov     r8, rcx; unsigned __int64
0x180051c7e  lea     rcx, [rsi+20h]; this
0x180051c82  call    ?PushToBack@CSbSafeBuffer@@QEAAJPEBE_K@Z; CSbSafeBuffer::PushToBack(uchar const *,unsigned __int64)
0x180051c87  mov     ebx, eax
0x180051c89  test    eax, eax
0x180051c8b  jns     short loc_180051CCB
0x180051c8d  mov     r10, cs:WPP_GLOBAL_Control
0x180051c94  lea     r13, WPP_GLOBAL_Control
0x180051c9b  cmp     r10, r13
0x180051c9e  jz      loc_1800520E9
0x180051ca4  cmp     [r10+19h], dil
0x180051ca8  jb      loc_1800520B5
0x180051cae  mov     edx, 13h
0x180051cb3  mov     rcx, [r10+10h]
0x180051cb7  lea     r8, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids
0x180051cbe  mov     r9d, eax
0x180051cc1  call    WPP_SF_d
0x180051cc6  jmp     loc_180051B61
0x180051ccb  movups  xmm0, xmmword ptr [r12+20h]
0x180051cd1  inc     dword ptr [rsi+10h]
0x180051cd4  mov     r11d, 14h
0x180051cda  mov     r12d, [rsi+10h]
0x180051cde  movdqu  xmmword ptr [rsi+40h], xmm0
0x180051ce3  cmp     r12d, r11d
0x180051ce6  jbe     short loc_180051D3A
0x180051ce8  mov     ebx, 8007050Ch
0x180051ced  mov     r10, cs:WPP_GLOBAL_Control
0x180051cf4  lea     r13, WPP_GLOBAL_Control
0x180051cfb  cmp     r10, r13
0x180051cfe  jz      loc_1800520E9
0x180051d04  cmp     [r10+19h], dil
0x180051d08  jb      loc_1800520B5
0x180051d0e  xor     ecx, ecx; int
0x180051d10  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180051d15  mov     rcx, [r10+10h]
0x180051d19  lea     r8, WPP_92c646ccb9143535ae7e38580a538a95_Traceguids
0x180051d20  mov     [rsp+0E0h+var_B8], r11d
0x180051d25  mov     edx, r11d
0x180051d28  mov     r9, rax
0x180051d2b  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x180051d30  call    WPP_SF_sld
0x180051d35  jmp     loc_180051B61
0x180051d3a  test    r15b, 1
0x180051d3e  jnz     loc_180051F16
0x180051d44  mov     r15, [rsi+18h]
0x180051d48  lea     r14, [rsi+38h]
0x180051d4c  test    r15, r15
0x180051d4f  jz      short loc_180051DC3
0x180051d51  mov     rcx, [r14]
0x180051d54  test    rcx, rcx
0x180051d57  jz      short loc_180051D65
0x180051d59  mov     rax, [rcx+8]
0x180051d5d  sub     rax, [rcx]
0x180051d60  cmp     rax, r15
0x180051d63  jz      short loc_180051DC3
0x180051d65  mov     ebx, 8004B008h
0x180051d6a  mov     r10, cs:WPP_GLOBAL_Control
0x180051d71  lea     r13, WPP_GLOBAL_Control
0x180051d78  cmp     r10, r13
0x180051d7b  jz      loc_1800520E9
0x180051d81  cmp     [r10+19h], dil
0x180051d85  jb      loc_1800520B5
0x180051d8b  test    rcx, rcx
0x180051d8e  jz      short loc_180051D99
0x180051d90  mov     r11, [rcx+8]
0x180051d94  sub     r11, [rcx]
0x180051d97  jmp     short loc_180051D9C
0x180051d99  xor     r11d, r11d
0x180051d9c  xor     ecx, ecx; int
0x180051d9e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180051da3  mov     rcx, [r10+10h]
0x180051da7  mov     r9, rax
0x180051daa  mov     [rsp+30h], r12d
0x180051daf  mov     qword ptr [rsp+0E0h+var_B8], r15
0x180051db4  mov     [rsp+0E0h+var_C0], r11
0x180051db9  call    WPP_SF_sPPD
0x180051dbe  jmp     loc_180051B61
0x180051dc3  movzx   r11d, [rbp+57h+var_88]
0x180051dc8  mov     ecx, r11d
0x180051dcb  sub     ecx, 1
0x180051dce  jz      loc_180051EAC
0x180051dd4  sub     ecx, 1
0x180051dd7  jz      short loc_180051E33
0x180051dd9  sub     ecx, 1
0x180051ddc  jz      short loc_180051E33
0x180051dde  sub     ecx, 1
0x180051de1  jz      short loc_180051E33
0x180051de3  sub     ecx, 1
0x180051de6  jz      short loc_180051E33
0x180051de8  cmp     ecx, 1
0x180051deb  jz      short loc_180051E29
0x180051ded  mov     ebx, 8004B00Ah
0x180051df2  mov     r10, cs:WPP_GLOBAL_Control
0x180051df9  lea     r13, WPP_GLOBAL_Control
0x180051e00  cmp     r10, r13
0x180051e03  jz      loc_1800520E9
0x180051e09  cmp     [r10+19h], dil
0x180051e0d  jb      loc_1800520B5
0x180051e13  xor     ecx, ecx; int
0x180051e15  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
  ... truncated ...
```
