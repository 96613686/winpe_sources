# MSXU_WhiteBalanceSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140059c10`
- end: `0x14005a08d`
- name: `?MSXU_WhiteBalanceSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `1149`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14000ef88`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b0c8`
- `0x14003b674`
- `0x14003b7f4`
- `0x14003b85c`
- `0x140040a30`
- `0x140055228`
- `0x140059c10`
- `0x14005bc78`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_WhiteBalanceSet(struct _IRP *a1, struct KSIDENTIFIER *a2, _QWORD *a3)
{
  NTSTATUS v5; // edi
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // r8d
  __int64 v9; // rdx
  __int64 v10; // r8
  struct _HW_DEVICE_EXTENSION *v11; // r14
  unsigned __int64 ExtPropFlags; // rax
  unsigned int *v13; // r10
  __int64 v14; // r9
  __int64 v15; // r11
  __int64 v16; // r9
  __int64 v17; // r9
  __int64 v18; // rcx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // r9d
  unsigned __int8 v23; // r10
  char v24; // al
  __int64 v25; // r8
  __int64 v26; // rcx
  unsigned __int8 v27; // si
  int v28; // edi
  unsigned int v29; // eax
  unsigned __int8 v30; // r9
  int v31; // eax
  int v33; // [rsp+20h] [rbp-39h]
  size_t Size; // [rsp+30h] [rbp-29h]
  struct _TOPOLOGY_NODE_INFO *v35; // [rsp+38h] [rbp-21h]
  unsigned __int8 v36; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 v37[7]; // [rsp+51h] [rbp-8h] BYREF
  struct _HW_DEVICE_EXTENSION *v38[2]; // [rsp+58h] [rbp-1h] BYREF
  struct _KSFILTER *v39; // [rsp+68h] [rbp+Fh] BYREF
  struct _TOPOLOGY_NODE_INFO *v40; // [rsp+70h] [rbp+17h] BYREF
  struct _HW_DEVICE_EXTENSION *v41; // [rsp+78h] [rbp+1Fh] BYREF
  int v42; // [rsp+80h] [rbp+27h]
  __int16 v43; // [rsp+84h] [rbp+2Bh]
  char v44; // [rsp+86h] [rbp+2Dh]

  v37[0] = 0;
  v36 = 0;
  v40 = 0;
  v38[0] = 0;
  v39 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, &v39, v37, &v36, &v40, v38);
  if ( v5 >= 0 )
  {
    v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 64);
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_66;
      v7 = (unsigned int)(v8 + 65);
      goto LABEL_8;
    }
    v5 = -1073741811;
    if ( CExtendedVidProcSetting::isValid((CExtendedVidProcSetting *)a3) && *((_DWORD *)a3 + 1) == -1 )
    {
      v11 = v38[0];
      ExtPropFlags = GetExtPropFlags(*(unsigned __int8 *)(*((_QWORD *)v38[0] + 123) + 15LL));
      v14 = a3[2];
      if ( (v14 & (ExtPropFlags | 0x8000000000000000uLL)) != v14 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_69;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 133);
        goto LABEL_63;
      }
      v15 = 1;
      v16 = v14 - 1;
      if ( !v16 )
      {
        v18 = 1;
        goto LABEL_33;
      }
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( (unsigned __int64)(v17 - 2) <= 1 )
        {
          v18 = 5;
          a3[2] = 5;
LABEL_33:
          v21 = a3[6];
          v22 = *((_DWORD *)a3 + 8);
          memset(v38, 0, 15);
          v23 = v15 & v18;
          v24 = 0;
          if ( (v15 & v18) != 0 )
            v24 = v15;
          LOBYTE(v38[0]) = v24;
          if ( (v18 & 2) != 0 )
            LOBYTE(v38[0]) = v23 | 2;
          v25 = v23 | 2u;
          if ( (v18 & 2) == 0 )
            v25 = v23;
          v26 = v18 & 4;
          if ( v26 )
            LOBYTE(v38[0]) = v25 | 4;
          v27 = v25 | 4;
          if ( !v26 )
            v27 = v25;
          if ( v22 == 1 )
          {
            v28 = 1;
            *(_DWORD *)((char *)v38 + 7) = 1;
            *(_DWORD *)((char *)&v38[1] + 3) = v21;
          }
          else if ( v22 == 2 )
          {
            *(_DWORD *)((char *)v38 + 7) = 2;
            v28 = 2;
            v29 = ConvertWhiteBalancePresets(v21);
            v21 = v29;
            *(_DWORD *)((char *)&v38[1] + 3) = v29;
          }
          else
          {
            v21 = *(unsigned int *)((char *)&v38[1] + 3);
            v28 = *(_DWORD *)((char *)v38 + 7);
          }
          v42 = (int)v38[1];
          v43 = WORD2(v38[1]);
          v44 = BYTE6(v38[1]);
          v41 = v38[0];
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_iDD(WPP_GLOBAL_Control->AttachedDevice, v21, v25, (unsigned int)v21, v27, v28);
          v30 = v37[0];
          *((_QWORD *)v11 + 140) = v39;
          v35 = v40;
          LODWORD(Size) = 15;
          LOBYTE(v33) = v36;
          *((_DWORD *)v11 + 323) = 1;
          v31 = SubmitControlRequest(
                  0x21u,
                  1u,
                  0x400u,
                  v30,
                  v33,
                  (unsigned __int8 *)&v41,
                  Size,
                  (__int64)v35,
                  (__int64)v11);
          v5 = v31;
          if ( v31 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                131,
                WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
                (unsigned int)v31);
            *((_QWORD *)v11 + 140) = 0;
          }
          goto LABEL_63;
        }
      }
      else if ( *((_DWORD *)a3 + 8) == 1 )
      {
        v5 = BoundsCheck<unsigned long>(
               *((unsigned int *)a3 + 12),
               *(unsigned int *)((char *)v13 + 11),
               *(unsigned int *)((char *)v13 + 26),
               v13[14]);
        v18 = 2;
        if ( v5 >= 0 )
          goto LABEL_33;
      }
      else if ( *((_DWORD *)a3 + 8) == 2
             && (a3[6] == 1 || a3[6] == 2 || a3[6] == 3 || a3[6] == 4 || (unsigned __int64)(a3[6] - 5LL) <= 1) )
      {
        v18 = 2;
        goto LABEL_33;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_63;
      v20 = 132;
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_69;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_63;
      v20 = 134;
    }
    WPP_SF_(v19->AttachedDevice, v20, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
LABEL_63:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_69;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_diiDiD(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        *((unsigned int *)a3 + 1),
        a3[2],
        a3[3],
        *((_DWORD *)a3 + 8),
        a3[6],
        v5);
    goto LABEL_66;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_69;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v7 = 128;
LABEL_8:
    WPP_SF_(v6->AttachedDevice, v7, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_66:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v5);
LABEL_69:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140059c10  mov     [rsp-8+arg_8], rbx
0x140059c15  mov     [rsp-8+arg_18], rsi
0x140059c1a  push    rbp
0x140059c1b  push    rdi
0x140059c1c  push    r13
0x140059c1e  push    r14
0x140059c20  push    r15
0x140059c22  lea     rbp, [rsp-37h]
0x140059c27  sub     rsp, 90h
0x140059c2e  mov     rax, cs:__security_cookie
0x140059c35  xor     rax, rsp
0x140059c38  mov     [rbp+57h+var_28], rax
0x140059c3c  mov     rbx, r8
0x140059c3f  mov     [rbp+57h+var_5F], 0
0x140059c43  mov     r15, rcx
0x140059c46  mov     [rbp+57h+var_60], 0
0x140059c4a  mov     [rbp+57h+var_40], 0
0x140059c52  mov     [rbp+57h+var_58], 0
0x140059c5a  mov     [rbp+57h+var_48], 0
0x140059c62  mov     rcx, cs:WPP_GLOBAL_Control
0x140059c69  lea     r13, WPP_GLOBAL_Control
0x140059c70  cmp     rcx, r13
0x140059c73  jz      short loc_140059C93
0x140059c75  cmp     byte ptr [rcx+29h], 4
0x140059c79  jb      short loc_140059C93
0x140059c7b  mov     rcx, [rcx+18h]
0x140059c7f  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059c86  mov     edx, 7Fh
0x140059c8b  mov     r9, r15
0x140059c8e  call    WPP_SF_q
0x140059c93  lea     rax, [rbp+57h+var_58]
0x140059c97  mov     rcx, r15; struct _IRP *
0x140059c9a  mov     [rsp+0B0h+var_88], rax; struct _HW_DEVICE_EXTENSION **
0x140059c9f  lea     r9, [rbp+57h+var_60]; unsigned __int8 *
0x140059ca3  lea     rax, [rbp+57h+var_40]
0x140059ca7  lea     r8, [rbp+57h+var_5F]; unsigned __int8 *
0x140059cab  mov     [rsp+0B0h+var_90], rax; struct _TOPOLOGY_NODE_INFO **
0x140059cb0  lea     rdx, [rbp+57h+var_48]; struct _KSFILTER **
0x140059cb4  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140059cb9  mov     edi, eax
0x140059cbb  test    eax, eax
0x140059cbd  jns     short loc_140059CF3
0x140059cbf  mov     rcx, cs:WPP_GLOBAL_Control
0x140059cc6  cmp     rcx, r13
0x140059cc9  jz      loc_14005A05E
0x140059ccf  cmp     byte ptr [rcx+29h], 2
0x140059cd3  jb      loc_14005A034
0x140059cd9  mov     edx, 80h
0x140059cde  mov     rcx, [rcx+18h]
0x140059ce2  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059ce9  call    WPP_SF_
0x140059cee  jmp     loc_14005A034
0x140059cf3  xor     r9d, r9d
0x140059cf6  mov     rdx, rbx
0x140059cf9  mov     rcx, r15
0x140059cfc  lea     r8d, [r9+40h]
0x140059d00  call    ValidateExtendedPropertyDataBufferLength
0x140059d05  mov     edi, eax
0x140059d07  test    eax, eax
0x140059d09  jns     short loc_140059D2B
0x140059d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059d12  cmp     rcx, r13
0x140059d15  jz      loc_14005A05E
0x140059d1b  cmp     byte ptr [rcx+29h], 2
0x140059d1f  jb      loc_14005A034
0x140059d25  lea     edx, [r8+41h]
0x140059d29  jmp     short loc_140059CDE
0x140059d2b  mov     rcx, rbx; this
0x140059d2e  mov     edi, 0C000000Dh
0x140059d33  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ; CExtendedVidProcSetting::isValid(void)
0x140059d38  test    al, al
0x140059d3a  jz      loc_140059FC4
0x140059d40  cmp     dword ptr [rbx+4], 0FFFFFFFFh
0x140059d44  jnz     loc_140059FC4
0x140059d4a  mov     r14, [rbp+57h+var_58]
0x140059d4e  mov     r10, [r14+3D8h]
0x140059d55  movzx   ecx, byte ptr [r10+0Fh]; unsigned int
0x140059d5a  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x140059d5f  mov     r9, [rbx+10h]
0x140059d63  mov     rcx, 8000000000000000h
0x140059d6d  or      rax, rcx
0x140059d70  mov     rcx, rax
0x140059d73  and     rcx, r9
0x140059d76  cmp     rcx, r9
0x140059d79  jnz     loc_140059F99
0x140059d7f  mov     r11d, 1
0x140059d85  sub     r9, r11
0x140059d88  jz      loc_140059E22
0x140059d8e  sub     r9, r11
0x140059d91  jz      short loc_140059DA9
0x140059d93  sub     r9, 2
0x140059d97  jz      short loc_140059D9E
0x140059d99  cmp     r9, r11
0x140059d9c  jnz     short loc_140059DFE
0x140059d9e  mov     ecx, 5
0x140059da3  mov     [rbx+10h], rcx
0x140059da7  jmp     short loc_140059E25
0x140059da9  mov     ecx, [rbx+20h]
0x140059dac  sub     ecx, r11d
0x140059daf  jz      short loc_140059DDF
0x140059db1  cmp     ecx, r11d
0x140059db4  jnz     short loc_140059DFE
0x140059db6  mov     rax, [rbx+30h]
0x140059dba  sub     rax, r11
0x140059dbd  jz      short loc_140059DD8
0x140059dbf  sub     rax, r11
0x140059dc2  jz      short loc_140059DD8
0x140059dc4  sub     rax, r11
0x140059dc7  jz      short loc_140059DD8
0x140059dc9  sub     rax, r11
0x140059dcc  jz      short loc_140059DD8
0x140059dce  sub     rax, r11
0x140059dd1  jz      short loc_140059DD8
0x140059dd3  cmp     rax, r11
0x140059dd6  jnz     short loc_140059DFE
0x140059dd8  mov     ecx, 2
0x140059ddd  jmp     short loc_140059E25
0x140059ddf  mov     edx, [r10+0Bh]
0x140059de3  mov     r9d, [r10+38h]
0x140059de7  mov     r8d, [r10+1Ah]
0x140059deb  mov     ecx, [rbx+30h]
0x140059dee  call    ??$BoundsCheck@K@@YAJKKKK@Z; BoundsCheck<ulong>(ulong,ulong,ulong,ulong)
0x140059df3  mov     edi, eax
0x140059df5  mov     ecx, 2
0x140059dfa  test    eax, eax
0x140059dfc  jns     short loc_140059E25
0x140059dfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140059e05  cmp     rcx, r13
0x140059e08  jz      loc_14005A05E
0x140059e0e  cmp     byte ptr [rcx+29h], 2
0x140059e12  jb      loc_140059FEF
0x140059e18  mov     edx, 84h
0x140059e1d  jmp     loc_140059FDF
0x140059e22  mov     rcx, r11
0x140059e25  mov     rdx, [rbx+30h]
0x140059e29  xor     eax, eax
0x140059e2b  mov     r9d, [rbx+20h]
0x140059e2f  mov     r10, rcx
0x140059e32  mov     [rbp+57h+var_58], rax
0x140059e36  and     r10, r11
0x140059e39  mov     [rbp+57h+var_50], eax
0x140059e3c  mov     [rbp+57h+var_4C], ax
0x140059e40  mov     [rbp+57h+var_4A], al
0x140059e43  movzx   eax, al
0x140059e46  cmovnz  eax, r11d
0x140059e4a  mov     r11, rcx
0x140059e4d  mov     byte ptr [rbp+57h+var_58], al
0x140059e50  and     r11d, 2
0x140059e54  mov     al, r10b
0x140059e57  or      al, 2
0x140059e59  test    r11, r11
0x140059e5c  jz      short loc_140059E61
0x140059e5e  mov     byte ptr [rbp+57h+var_58], al
0x140059e61  movzx   r8d, al
0x140059e65  test    r11, r11
0x140059e68  movzx   eax, r10b
0x140059e6c  cmovz   r8d, eax
0x140059e70  and     ecx, 4
0x140059e73  mov     al, r8b
0x140059e76  or      al, 4
0x140059e78  test    rcx, rcx
0x140059e7b  jz      short loc_140059E80
0x140059e7d  mov     byte ptr [rbp+57h+var_58], al
0x140059e80  movzx   esi, al
0x140059e83  test    rcx, rcx
0x140059e86  movzx   eax, r8b
0x140059e8a  cmovz   esi, eax
0x140059e8d  cmp     r9d, 1
0x140059e91  jnz     short loc_140059E9F
0x140059e93  mov     edi, r9d
0x140059e96  mov     dword ptr [rbp+57h+var_58+7], r9d
0x140059e9a  mov     [rbp+57h+var_50+3], edx
0x140059e9d  jmp     short loc_140059EC1
0x140059e9f  cmp     r9d, 2
0x140059ea3  jnz     short loc_140059EBB
0x140059ea5  mov     rcx, rdx; __int64
0x140059ea8  mov     dword ptr [rbp+57h+var_58+7], r9d
0x140059eac  mov     edi, r9d
0x140059eaf  call    ?ConvertWhiteBalancePresets@@YAK_J@Z; ConvertWhiteBalancePresets(__int64)
0x140059eb4  mov     edx, eax
0x140059eb6  mov     [rbp+57h+var_50+3], eax
0x140059eb9  jmp     short loc_140059EC1
0x140059ebb  mov     edx, [rbp+57h+var_50+3]
0x140059ebe  mov     edi, dword ptr [rbp+57h+var_58+7]
0x140059ec1  mov     eax, [rbp+57h+var_50]
0x140059ec4  movsd   xmm0, [rbp+57h+var_58]
0x140059ec9  mov     [rbp+57h+var_30], eax
0x140059ecc  movzx   eax, [rbp+57h+var_4C]
0x140059ed0  mov     [rbp+57h+var_2C], ax
0x140059ed4  mov     al, [rbp+57h+var_4A]
0x140059ed7  mov     [rbp+57h+var_2A], al
0x140059eda  movsd   [rbp+57h+var_38], xmm0
0x140059edf  mov     rcx, cs:WPP_GLOBAL_Control
0x140059ee6  cmp     rcx, r13
0x140059ee9  jz      short loc_140059F09
0x140059eeb  cmp     byte ptr [rcx+29h], 4
0x140059eef  jb      short loc_140059F09
0x140059ef1  mov     rcx, [rcx+18h]
0x140059ef5  movzx   eax, sil
0x140059ef9  mov     r9d, edx
0x140059efc  mov     dword ptr [rsp+0B0h+var_88], edi
0x140059f00  mov     dword ptr [rsp+0B0h+var_90], eax
0x140059f04  call    WPP_SF_iDD
0x140059f09  mov     rax, [rbp+57h+var_48]
0x140059f0d  mov     r8d, 400h; int
0x140059f13  mov     r9b, [rbp+57h+var_5F]; int
0x140059f17  mov     dl, 1; int
0x140059f19  mov     [r14+460h], rax
0x140059f20  mov     cl, 21h ; '!'; int
0x140059f22  mov     rax, [rbp+57h+var_40]
0x140059f26  mov     [rsp+0B0h+var_70], r14; __int64
0x140059f2b  mov     [rsp+0B0h+var_78], rax; __int64
0x140059f30  lea     rax, [rbp+57h+var_38]
0x140059f34  mov     dword ptr [rsp+0B0h+Size], 0Fh; Size
0x140059f3c  mov     [rsp+0B0h+var_88], rax; void *
0x140059f41  mov     al, [rbp+57h+var_60]
0x140059f44  mov     byte ptr [rsp+0B0h+var_90], al; int
0x140059f48  mov     dword ptr [r14+50Ch], 1
0x140059f53  call    SubmitControlRequest
0x140059f58  mov     edi, eax
0x140059f5a  test    eax, eax
0x140059f5c  jns     loc_140059FEF
0x140059f62  mov     rcx, cs:WPP_GLOBAL_Control
0x140059f69  cmp     rcx, r13
0x140059f6c  jz      short loc_140059F8C
0x140059f6e  cmp     byte ptr [rcx+29h], 2
0x140059f72  jb      short loc_140059F8C
0x140059f74  mov     rcx, [rcx+18h]
0x140059f78  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059f7f  mov     edx, 83h
0x140059f84  mov     r9d, eax
0x140059f87  call    WPP_SF_d
0x140059f8c  mov     qword ptr [r14+460h], 0
0x140059f97  jmp     short loc_140059FEF
0x140059f99  mov     rcx, cs:WPP_GLOBAL_Control
0x140059fa0  cmp     rcx, r13
0x140059fa3  jz      loc_14005A05E
0x140059fa9  cmp     byte ptr [rcx+29h], 2
0x140059fad  jb      short loc_140059FEF
0x140059faf  mov     rcx, [rcx+18h]
0x140059fb3  mov     edx, 85h
0x140059fb8  mov     [rsp+0B0h+var_90], rax
0x140059fbd  call    WPP_SF_ii
0x140059fc2  jmp     short loc_140059FEF
0x140059fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140059fcb  cmp     rcx, r13
0x140059fce  jz      loc_14005A05E
0x140059fd4  cmp     byte ptr [rcx+29h], 2
0x140059fd8  jb      short loc_140059FEF
0x140059fda  mov     edx, 86h
0x140059fdf  mov     rcx, [rcx+18h]
0x140059fe3  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059fea  call    WPP_SF_
0x140059fef  mov     rcx, cs:WPP_GLOBAL_Control
0x140059ff6  cmp     rcx, r13
0x140059ff9  jz      short loc_14005A05E
0x140059ffb  cmp     byte ptr [rcx+29h], 4
0x140059fff  jb      short loc_14005A034
0x14005a001  mov     rax, [rbx+30h]
0x14005a005  mov     r9d, [rbx+4]
0x14005a009  mov     rcx, [rcx+18h]
0x14005a00d  mov     dword ptr [rsp+0B0h+var_70], edi
0x14005a011  mov     [rsp+0B0h+var_78], rax
0x14005a016  mov     eax, [rbx+20h]
0x14005a019  mov     dword ptr [rsp+0B0h+Size], eax
0x14005a01d  mov     rax, [rbx+18h]
0x14005a021  mov     [rsp+0B0h+var_88], rax
0x14005a026  mov     rax, [rbx+10h]
0x14005a02a  mov     [rsp+0B0h+var_90], rax
0x14005a02f  call    WPP_SF_diiDiD
0x14005a034  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a03b  cmp     rcx, r13
0x14005a03e  jz      short loc_14005A05E
0x14005a040  cmp     byte ptr [rcx+29h], 4
0x14005a044  jb      short loc_14005A05E
0x14005a046  mov     rcx, [rcx+18h]
0x14005a04a  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005a051  mov     edx, 88h
0x14005a056  mov     r9d, edi
0x14005a059  call    WPP_SF_d
0x14005a05e  mov     [r15+30h], edi
0x14005a062  mov     eax, edi
0x14005a064  mov     rcx, [rbp+57h+var_28]
0x14005a068  xor     rcx, rsp; StackCookie
0x14005a06b  call    __security_check_cookie
0x14005a070  lea     r11, [rsp+0B0h+var_20]
0x14005a078  mov     rbx, [r11+38h]
0x14005a07c  mov     rsi, [r11+48h]
0x14005a080  mov     rsp, r11
0x14005a083  pop     r15
0x14005a085  pop     r14
0x14005a087  pop     r13
0x14005a089  pop     rdi
0x14005a08a  pop     rbp
0x14005a08b  retn
```
