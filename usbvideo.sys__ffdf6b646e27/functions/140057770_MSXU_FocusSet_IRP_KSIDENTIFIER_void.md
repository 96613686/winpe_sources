# MSXU_FocusSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140057770`
- end: `0x140057ee3`
- name: `?MSXU_FocusSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `1907`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140008640`
- `0x14000de14`
- `0x14000ef88`
- `0x14001b118`
- `0x14001b15c`
- `0x140040a30`
- `0x140057770`
- `0x14005a094`
- `0x14005bc78`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_FocusSet(struct _IRP *a1, struct KSIDENTIFIER *a2, CExtendedVidProcSetting *a3)
{
  NTSTATUS v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // r9d
  struct _HW_DEVICE_EXTENSION *v9; // r15
  unsigned __int64 ExtPropFlags; // rax
  __int64 v11; // r10
  __int64 v12; // r14
  __int16 v13; // di
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  bool v23; // zf
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  int v27; // eax
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // r9
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // rcx
  unsigned __int64 v39; // rcx
  PDEVICE_OBJECT v40; // rcx
  __int64 v41; // rdx
  __int64 PayloadFocus; // rax
  __int64 v43; // r9
  unsigned __int8 v44; // r9
  int v45; // eax
  int v47; // [rsp+20h] [rbp-49h]
  size_t Size; // [rsp+30h] [rbp-39h]
  struct _TOPOLOGY_NODE_INFO *v49; // [rsp+38h] [rbp-31h]
  unsigned __int8 v50; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int8 v51[7]; // [rsp+51h] [rbp-18h] BYREF
  struct _TOPOLOGY_NODE_INFO *v52; // [rsp+58h] [rbp-11h] BYREF
  char v53[16]; // [rsp+60h] [rbp-9h] BYREF
  struct _HW_DEVICE_EXTENSION *v54; // [rsp+70h] [rbp+7h] BYREF
  int v55; // [rsp+78h] [rbp+Fh]
  struct _KSFILTER *v56; // [rsp+80h] [rbp+17h] BYREF
  int v57; // [rsp+88h] [rbp+1Fh]

  v51 = 0;
  v50 = 0;
  v52 = 0;
  v54 = 0;
  v56 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, &v56, &v51, &v50, &v52, &v54);
  if ( v5 >= 0 )
  {
    v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 64);
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_122;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_119;
      v7 = (unsigned int)(v8 + 102);
      goto LABEL_118;
    }
    v5 = -1073741811;
    if ( !CExtendedVidProcSetting::isValid(a3) )
      goto LABEL_115;
    if ( *((_DWORD *)a3 + 1) != -1 )
      goto LABEL_115;
    v9 = v54;
    ExtPropFlags = GetExtPropFlags(*(_DWORD *)(*((_QWORD *)v54 + 120) + 13LL));
    v12 = *((_QWORD *)a3 + 2);
    v13 = ExtPropFlags;
    if ( ((ExtPropFlags | 0x8000000000000000uLL) & v12) != v12 )
      goto LABEL_115;
    v5 = 0;
    v14 = v12 & 0x1F07;
    if ( v14 > 0x900 )
    {
      v32 = v14 - 2816;
      if ( !v32 )
        goto LABEL_39;
      v33 = v32 - 1281;
      if ( !v33 )
        goto LABEL_39;
      v34 = v33 - 4;
      if ( !v34 )
        goto LABEL_39;
      v35 = v34 - 251;
      if ( !v35 )
        goto LABEL_39;
      v36 = v35 - 512;
      if ( !v36 )
        goto LABEL_39;
      v37 = v36 - 1281;
      if ( !v37 )
        goto LABEL_39;
      v38 = v37 - 4;
      if ( !v38 )
        goto LABEL_39;
      v39 = v38 - 251;
      if ( !v39 )
        goto LABEL_39;
      v23 = v39 == 512;
    }
    else
    {
      if ( v14 == 2304 )
        goto LABEL_39;
      v15 = v14 - 1;
      if ( !v15 )
        goto LABEL_39;
      v16 = v15 - 1;
      if ( !v16 )
      {
        v31 = *((unsigned int *)a3 + 12);
        if ( (int)v31 > *(_DWORD *)(v11 + 20) || (int)v31 < *(_DWORD *)(v11 + 8) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v31);
          goto LABEL_103;
        }
        goto LABEL_39;
      }
      v17 = v16 - 2;
      if ( !v17 )
      {
        v54 = 0;
        v55 = 0;
        LODWORD(Size) = 12;
        LOBYTE(v47) = v50;
        v5 = SubmitControlRequest(
               0xA1u,
               0x81u,
               0x100u,
               v51,
               v47,
               (unsigned __int8 *)&v54,
               Size,
               (__int64)v52,
               (__int64)v9);
        if ( v5 >= 0 )
        {
          if ( (*(_DWORD *)((_BYTE *)&v54 + 1) & 0x1F0107) == *(_DWORD *)((char *)&v54 + 1) )
          {
            if ( (*(_WORD *)((_BYTE *)&v54 + 1) & 0x101) != 0 )
            {
              if ( (v13 & 0x101) == 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
                v5 = -1073741811;
              }
              if ( v5 < 0 )
                goto LABEL_115;
            }
            else
            {
              if ( (BYTE1(v54) & 2) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
                v5 = -1073741794;
                goto LABEL_115;
              }
              v5 = 0;
            }
            goto LABEL_39;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              104,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              *(unsigned int *)((char *)&v54 + 1));
          v5 = -1073741436;
        }
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_119;
        v29 = 105;
        v30 = (unsigned int)v5;
        goto LABEL_76;
      }
      v18 = v17 - 1;
      if ( !v18 )
        goto LABEL_39;
      v19 = v18 - 251;
      if ( !v19 )
        goto LABEL_39;
      v20 = v19 - 512;
      if ( !v20 )
        goto LABEL_39;
      v21 = v20 - 256;
      if ( !v21 )
        goto LABEL_39;
      v22 = v21 - 1025;
      if ( !v22 )
        goto LABEL_39;
      v23 = v22 == 4;
    }
    if ( !v23 )
    {
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_103;
      v41 = 108;
LABEL_102:
      WPP_SF_(v40->AttachedDevice, v41, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
LABEL_103:
      v5 = -1073741811;
      goto LABEL_115;
    }
LABEL_39:
    v24 = v12 & 0x1F0000;
    if ( (v12 & 0x1F0000) != 0 )
    {
      if ( (v12 & 0x101) == 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_103;
        v41 = 110;
        goto LABEL_102;
      }
      if ( v24 != 0x10000 && v24 != 0x20000 && v24 != 0x40000 && v24 != 0x80000 && v24 != 0x100000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
        v5 = -1073741811;
      }
    }
    if ( v5 >= 0 )
    {
      v25 = v12 & 0x7000000;
      if ( (v12 & 2) != 0 )
      {
        if ( (v12 & 0x7000000) != 0 && v25 != 0x1000000 && v25 != 0x2000000 && v25 != 0x4000000 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
          v5 = -1073741811;
        }
        if ( v5 < 0 )
          goto LABEL_115;
      }
      else if ( (v12 & 0x7000000) != 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_103;
        v41 = 112;
        goto LABEL_102;
      }
      v26 = *((_QWORD *)a3 + 2);
      if ( v26 >= 0 )
      {
        PayloadFocus = MakePayloadFocus(&v53, v26, *((unsigned int *)a3 + 12));
        v54 = *(struct _HW_DEVICE_EXTENSION **)PayloadFocus;
        v43 = *(unsigned int *)(PayloadFocus + 8);
        v55 = *(_DWORD *)(PayloadFocus + 8);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            115,
            WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
            v43,
            (unsigned __int64)v54 >> 8);
        v44 = v51;
        *((_QWORD *)v9 + 137) = v56;
        v49 = v52;
        LODWORD(Size) = 12;
        LOBYTE(v47) = v50;
        *((_DWORD *)v9 + 320) = 1;
        v45 = SubmitControlRequest(
                0x21u,
                1u,
                0x100u,
                v44,
                v47,
                (unsigned __int8 *)&v54,
                Size,
                (__int64)v49,
                (__int64)v9);
        v5 = v45;
        if ( v45 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              116,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              (unsigned int)v45);
          *((_QWORD *)v9 + 137) = 0;
        }
        goto LABEL_119;
      }
      v56 = (struct _KSFILTER *)1;
      v57 = 0;
      LODWORD(Size) = 12;
      LOBYTE(v47) = v50;
      v27 = SubmitControlRequest(0x21u, 1u, 0x100u, v51, v47, (unsigned __int8 *)&v56, Size, (__int64)v52, (__int64)v9);
      v5 = v27;
      if ( v27 >= 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_122;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          goto LABEL_119;
        v7 = 114;
        goto LABEL_118;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_122;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_119;
      v29 = 113;
      v30 = (unsigned int)v27;
LABEL_76:
      WPP_SF_d(v28->AttachedDevice, v29, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v30);
      goto LABEL_119;
    }
LABEL_115:
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_122;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_119;
    v7 = 117;
    goto LABEL_118;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_122;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v7 = 101;
LABEL_118:
    WPP_SF_(v6->AttachedDevice, v7, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_119:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v5);
LABEL_122:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140057770  mov     [rsp-8+arg_8], rbx
0x140057775  mov     [rsp-8+arg_18], rsi
0x14005777a  push    rbp
0x14005777b  push    rdi
0x14005777c  push    r13
0x14005777e  push    r14
0x140057780  push    r15
0x140057782  lea     rbp, [rsp-37h]
0x140057787  sub     rsp, 0A0h
0x14005778e  mov     rax, cs:__security_cookie
0x140057795  xor     rax, rsp
0x140057798  mov     [rbp+57h+var_30], rax
0x14005779c  mov     rsi, r8
0x14005779f  mov     [rbp+57h+var_6F], 0
0x1400577a3  mov     r13, rcx
0x1400577a6  mov     [rbp+57h+var_70], 0
0x1400577aa  mov     [rbp+57h+var_68], 0
0x1400577b2  mov     [rbp+57h+var_50], 0
0x1400577ba  mov     [rbp+57h+var_40], 0
0x1400577c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400577c9  lea     rax, WPP_GLOBAL_Control
0x1400577d0  cmp     rcx, rax
0x1400577d3  jz      short loc_1400577F3
0x1400577d5  cmp     byte ptr [rcx+29h], 4
0x1400577d9  jb      short loc_1400577F3
0x1400577db  mov     rcx, [rcx+18h]
0x1400577df  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400577e6  mov     edx, 64h ; 'd'
0x1400577eb  mov     r9, r13
0x1400577ee  call    WPP_SF_q
0x1400577f3  lea     rax, [rbp+57h+var_50]
0x1400577f7  mov     rcx, r13; struct _IRP *
0x1400577fa  mov     [rsp+0C0h+var_98], rax; struct _HW_DEVICE_EXTENSION **
0x1400577ff  lea     r9, [rbp+57h+var_70]; unsigned __int8 *
0x140057803  lea     rax, [rbp+57h+var_68]
0x140057807  lea     r8, [rbp+57h+var_6F]; unsigned __int8 *
0x14005780b  mov     [rsp+0C0h+var_A0], rax; struct _TOPOLOGY_NODE_INFO **
0x140057810  lea     rdx, [rbp+57h+var_40]; struct _KSFILTER **
0x140057814  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140057819  mov     ebx, eax
0x14005781b  test    eax, eax
0x14005781d  jns     short loc_14005784A
0x14005781f  mov     rcx, cs:WPP_GLOBAL_Control
0x140057826  lea     rdi, WPP_GLOBAL_Control
0x14005782d  cmp     rcx, rdi
0x140057830  jz      loc_140057EB4
0x140057836  cmp     byte ptr [rcx+29h], 2
0x14005783a  jb      loc_140057E8A
0x140057840  mov     edx, 65h ; 'e'
0x140057845  jmp     loc_140057E7A
0x14005784a  xor     r9d, r9d
0x14005784d  mov     rdx, rsi
0x140057850  mov     rcx, r13
0x140057853  lea     r8d, [r9+40h]
0x140057857  call    ValidateExtendedPropertyDataBufferLength
0x14005785c  mov     ebx, eax
0x14005785e  test    eax, eax
0x140057860  jns     short loc_14005788C
0x140057862  mov     rcx, cs:WPP_GLOBAL_Control
0x140057869  lea     rdi, WPP_GLOBAL_Control
0x140057870  cmp     rcx, rdi
0x140057873  jz      loc_140057EB4
0x140057879  cmp     byte ptr [rcx+29h], 2
0x14005787d  jb      loc_140057E8A
0x140057883  lea     edx, [r9+66h]
0x140057887  jmp     loc_140057E7A
0x14005788c  mov     rcx, rsi; this
0x14005788f  mov     ebx, 0C000000Dh
0x140057894  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ; CExtendedVidProcSetting::isValid(void)
0x140057899  test    al, al
0x14005789b  jz      loc_140057E5C
0x1400578a1  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x1400578a5  jnz     loc_140057E5C
0x1400578ab  mov     r15, [rbp+57h+var_50]
0x1400578af  mov     r10, [r15+3C0h]
0x1400578b6  mov     ecx, [r10+0Dh]; unsigned int
0x1400578ba  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x1400578bf  mov     r14, [rsi+10h]
0x1400578c3  mov     rdi, rax
0x1400578c6  mov     rax, 8000000000000000h
0x1400578d0  mov     rcx, r14
0x1400578d3  or      rdi, rax
0x1400578d6  and     rcx, rdi
0x1400578d9  cmp     rcx, r14
0x1400578dc  jnz     loc_140057E5C
0x1400578e2  mov     rcx, r14
0x1400578e5  xor     ebx, ebx
0x1400578e7  and     ecx, 1F07h
0x1400578ed  mov     eax, 900h
0x1400578f2  mov     r8d, 100h; int
0x1400578f8  cmp     rcx, rax
0x1400578fb  ja      loc_140057C81
0x140057901  jz      loc_140057A44
0x140057907  sub     rcx, 1
0x14005790b  jz      loc_140057A44
0x140057911  sub     rcx, 1
0x140057915  jz      loc_140057C32
0x14005791b  sub     rcx, 2
0x14005791f  jz      short loc_140057965
0x140057921  sub     rcx, 1
0x140057925  jz      loc_140057A44
0x14005792b  sub     rcx, 0FBh
0x140057932  jz      loc_140057A44
0x140057938  mov     eax, 200h
0x14005793d  sub     rcx, rax
0x140057940  jz      loc_140057A44
0x140057946  sub     rcx, r8
0x140057949  jz      loc_140057A44
0x14005794f  sub     rcx, 401h
0x140057956  jz      loc_140057A44
0x14005795c  cmp     rcx, 4
0x140057960  jmp     loc_140057CE2
0x140057965  mov     r9b, [rbp+57h+var_6F]; int
0x140057969  xor     eax, eax
0x14005796b  mov     [rbp+57h+var_50], rax
0x14005796f  mov     dl, 81h; int
0x140057971  mov     [rbp+57h+var_48], eax
0x140057974  mov     cl, 0A1h; int
0x140057976  mov     rax, [rbp+57h+var_68]
0x14005797a  mov     [rsp+0C0h+var_80], r15; __int64
0x14005797f  mov     [rsp+0C0h+var_88], rax; __int64
0x140057984  lea     rax, [rbp+57h+var_50]
0x140057988  mov     dword ptr [rsp+0C0h+Size], 0Ch; Size
0x140057990  mov     [rsp+0C0h+var_98], rax; void *
0x140057995  mov     al, [rbp+57h+var_70]
0x140057998  mov     byte ptr [rsp+0C0h+var_A0], al; int
0x14005799c  call    SubmitControlRequest
0x1400579a1  mov     ebx, eax
0x1400579a3  test    eax, eax
0x1400579a5  js      loc_140057BF4
0x1400579ab  mov     r8d, dword ptr [rbp+57h+var_50+1]
0x1400579af  mov     eax, r8d
0x1400579b2  and     eax, 1F0107h
0x1400579b7  cmp     eax, r8d
0x1400579ba  jz      short loc_1400579F7
0x1400579bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400579c3  lea     rdi, WPP_GLOBAL_Control
0x1400579ca  cmp     rcx, rdi
0x1400579cd  jz      short loc_1400579ED
0x1400579cf  cmp     byte ptr [rcx+29h], 2
0x1400579d3  jb      short loc_1400579ED
0x1400579d5  mov     rcx, [rcx+18h]
0x1400579d9  mov     r9d, r8d
0x1400579dc  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400579e3  mov     edx, 68h ; 'h'
0x1400579e8  call    WPP_SF_d
0x1400579ed  mov     ebx, 0C0000184h
0x1400579f2  jmp     loc_140057BFB
0x1400579f7  test    r8d, 101h
0x1400579fe  jnz     loc_140057BA2
0x140057a04  test    byte ptr [rbp+57h+var_50+1], 2
0x140057a08  jz      short loc_140057A42
0x140057a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140057a11  lea     rdi, WPP_GLOBAL_Control
0x140057a18  cmp     rcx, rdi
0x140057a1b  jz      short loc_140057A38
0x140057a1d  cmp     byte ptr [rcx+29h], 2
0x140057a21  jb      short loc_140057A38
0x140057a23  mov     rcx, [rcx+18h]
0x140057a27  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057a2e  mov     edx, 6Ah ; 'j'
0x140057a33  call    WPP_SF_
0x140057a38  mov     ebx, 0C000001Eh
0x140057a3d  jmp     loc_140057E63
0x140057a42  xor     ebx, ebx
0x140057a44  lea     rdi, WPP_GLOBAL_Control
0x140057a4b  mov     rax, r14
0x140057a4e  and     eax, 1F0000h
0x140057a53  jz      short loc_140057AB6
0x140057a55  test    r14, 101h
0x140057a5c  jz      loc_140057D08
0x140057a62  cmp     rax, 10000h
0x140057a68  jz      short loc_140057AB6
0x140057a6a  cmp     rax, 20000h
0x140057a70  jz      short loc_140057AB6
0x140057a72  cmp     rax, 40000h
0x140057a78  jz      short loc_140057AB6
0x140057a7a  cmp     rax, 80000h
0x140057a80  jz      short loc_140057AB6
0x140057a82  cmp     rax, 100000h
0x140057a88  jz      short loc_140057AB6
0x140057a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140057a91  cmp     rcx, rdi
0x140057a94  jz      short loc_140057AB1
0x140057a96  cmp     byte ptr [rcx+29h], 2
0x140057a9a  jb      short loc_140057AB1
0x140057a9c  mov     rcx, [rcx+18h]
0x140057aa0  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057aa7  mov     edx, 6Dh ; 'm'
0x140057aac  call    WPP_SF_
0x140057ab1  mov     ebx, 0C000000Dh
0x140057ab6  test    ebx, ebx
0x140057ab8  js      loc_140057E63
0x140057abe  mov     rax, r14
0x140057ac1  and     eax, 7000000h
0x140057ac6  test    r14b, 2
0x140057aca  jz      loc_140057D21
0x140057ad0  test    rax, rax
0x140057ad3  jz      short loc_140057B19
0x140057ad5  cmp     rax, 1000000h
0x140057adb  jz      short loc_140057B19
0x140057add  cmp     rax, 2000000h
0x140057ae3  jz      short loc_140057B19
0x140057ae5  cmp     rax, 4000000h
0x140057aeb  jz      short loc_140057B19
0x140057aed  mov     rcx, cs:WPP_GLOBAL_Control
0x140057af4  cmp     rcx, rdi
0x140057af7  jz      short loc_140057B14
0x140057af9  cmp     byte ptr [rcx+29h], 2
0x140057afd  jb      short loc_140057B14
0x140057aff  mov     rcx, [rcx+18h]
0x140057b03  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057b0a  mov     edx, 6Fh ; 'o'
0x140057b0f  call    WPP_SF_
0x140057b14  mov     ebx, 0C000000Dh
0x140057b19  test    ebx, ebx
0x140057b1b  js      loc_140057E63
0x140057b21  mov     rdx, [rsi+10h]
0x140057b25  test    rdx, rdx
0x140057b28  jns     loc_140057D7F
0x140057b2e  mov     r9b, [rbp+57h+var_6F]; int
0x140057b32  xor     eax, eax
0x140057b34  mov     [rbp+57h+var_40], rax
0x140057b38  mov     r8d, 100h; int
0x140057b3e  mov     [rbp+57h+var_38], eax
0x140057b41  mov     dl, 1; int
0x140057b43  mov     rax, [rbp+57h+var_68]
0x140057b47  mov     cl, 21h ; '!'; int
0x140057b49  mov     [rsp+0C0h+var_80], r15; __int64
0x140057b4e  mov     [rsp+0C0h+var_88], rax; __int64
0x140057b53  lea     rax, [rbp+57h+var_40]
0x140057b57  mov     dword ptr [rsp+0C0h+Size], 0Ch; Size
0x140057b5f  mov     [rsp+0C0h+var_98], rax; void *
0x140057b64  mov     al, [rbp+57h+var_70]
0x140057b67  mov     byte ptr [rsp+0C0h+var_A0], al; int
0x140057b6b  mov     byte ptr [rbp+57h+var_40], 1
0x140057b6f  call    SubmitControlRequest
0x140057b74  mov     ebx, eax
0x140057b76  test    eax, eax
0x140057b78  jns     loc_140057D5B
0x140057b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140057b85  cmp     rcx, rdi
0x140057b88  jz      loc_140057EB4
0x140057b8e  cmp     byte ptr [rcx+29h], 2
0x140057b92  jb      loc_140057E8A
0x140057b98  mov     edx, 71h ; 'q'
0x140057b9d  mov     r9d, eax
0x140057ba0  jmp     short loc_140057C1D
0x140057ba2  test    rdi, 101h
0x140057ba9  jnz     short loc_140057BE0
0x140057bab  mov     rcx, cs:WPP_GLOBAL_Control
0x140057bb2  lea     rdi, WPP_GLOBAL_Control
0x140057bb9  cmp     rcx, rdi
0x140057bbc  jz      short loc_140057BD9
0x140057bbe  cmp     byte ptr [rcx+29h], 2
0x140057bc2  jb      short loc_140057BD9
0x140057bc4  mov     rcx, [rcx+18h]
0x140057bc8  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057bcf  mov     edx, 6Bh ; 'k'
0x140057bd4  call    WPP_SF_
0x140057bd9  mov     ebx, 0C000000Dh
0x140057bde  jmp     short loc_140057BE7
0x140057be0  lea     rdi, WPP_GLOBAL_Control
0x140057be7  test    ebx, ebx
0x140057be9  js      loc_140057E63
0x140057bef  jmp     loc_140057A4B
0x140057bf4  lea     rdi, WPP_GLOBAL_Control
0x140057bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c02  cmp     rcx, rdi
0x140057c05  jz      loc_140057EB4
0x140057c0b  cmp     byte ptr [rcx+29h], 2
0x140057c0f  jb      loc_140057E8A
0x140057c15  mov     edx, 69h ; 'i'
0x140057c1a  mov     r9d, ebx
0x140057c1d  mov     rcx, [rcx+18h]
0x140057c21  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057c28  call    WPP_SF_d
0x140057c2d  jmp     loc_140057E8A
0x140057c32  mov     r9d, [rsi+30h]
0x140057c36  cmp     r9d, [r10+14h]
0x140057c3a  jg      short loc_140057C46
0x140057c3c  cmp     r9d, [r10+8]
0x140057c40  jge     loc_140057A44
0x140057c46  mov     rcx, cs:WPP_GLOBAL_Control
0x140057c4d  lea     rdi, WPP_GLOBAL_Control
0x140057c54  cmp     rcx, rdi
0x140057c57  jz      loc_140057D51
0x140057c5d  cmp     byte ptr [rcx+29h], 2
0x140057c61  jb      loc_140057D51
0x140057c67  mov     rcx, [rcx+18h]
0x140057c6b  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057c72  mov     edx, 67h ; 'g'
0x140057c77  call    WPP_SF_d
0x140057c7c  jmp     loc_140057D51
0x140057c81  sub     rcx, 0B00h
0x140057c88  jz      loc_140057A44
0x140057c8e  mov     r8d, 501h
0x140057c94  sub     rcx, r8
0x140057c97  jz      loc_140057A44
0x140057c9d  sub     rcx, 4
  ... truncated ...
```
