# MSXU_WhiteBalanceGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140059890`
- end: `0x140059bfd`
- name: `?MSXU_WhiteBalanceGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `877`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14000ef88`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b270`
- `0x140040a30`
- `0x1400552b8`
- `0x140059890`
- `0x14005bc78`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_WhiteBalanceGet(struct _IRP *a1, struct KSIDENTIFIER *a2, char *a3)
{
  NTSTATUS v5; // edi
  int v6; // r9d
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r14
  __int64 v10; // xmm0_8
  unsigned __int8 v11; // dl
  __int64 v12; // r11
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  unsigned int v16; // ecx
  unsigned __int64 v17; // r10
  __int64 v18; // rdx
  __int64 v19; // r8
  int v21; // [rsp+20h] [rbp-69h]
  size_t Size; // [rsp+30h] [rbp-59h]
  __int64 v23; // [rsp+40h] [rbp-49h]
  unsigned __int8 v24; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int8 v25[7]; // [rsp+51h] [rbp-38h] BYREF
  struct _TOPOLOGY_NODE_INFO *v26[9]; // [rsp+58h] [rbp-31h] BYREF
  _BYTE v27[15]; // [rsp+A0h] [rbp+17h] BYREF

  v25[0] = 0;
  v24 = 0;
  v26[0] = 0;
  *(_QWORD *)v27 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, 0, v25, &v24, v26, (struct _HW_DEVICE_EXTENSION **)v27);
  if ( v5 < 0 )
    goto LABEL_40;
  v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 64);
  if ( v5 >= 0 )
  {
    if ( !CExtendedVidProcSetting::isValid((CExtendedVidProcSetting *)a3) || *((_DWORD *)a3 + 1) != -1 )
    {
      v7 = WPP_GLOBAL_Control;
      v5 = -1073741811;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_43;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_40;
      v8 = 125;
      goto LABEL_39;
    }
    v23 = *(_QWORD *)v27;
    v9 = *(_QWORD *)(*(_QWORD *)v27 + 984LL);
    v10 = *(_QWORD *)(v9 + 30);
    *(_DWORD *)&v27[8] = *(_DWORD *)(v9 + 38);
    *(_WORD *)&v27[12] = *(_WORD *)(v9 + 42);
    v27[14] = *(_BYTE *)(v9 + 44);
    LODWORD(Size) = 15;
    LOBYTE(v21) = v24;
    *(_QWORD *)v27 = v10;
    v5 = SubmitControlRequest(0xA1u, 0x81u, 0x400u, v25[0], v21, v27, Size, (__int64)v26[0], v23);
    if ( v5 < 0 )
      goto LABEL_33;
    v11 = v27[0];
    if ( (v27[0] & 7) != v27[0] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v27[0]);
        v11 = v27[0];
      }
      v5 = -1073741436;
    }
    if ( v5 < 0 )
    {
LABEL_33:
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_43;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_40;
      v8 = 124;
      goto LABEL_39;
    }
    *((_QWORD *)a3 + 2) = GetExtPropFlags(v11);
    v13 = *(_DWORD *)&v27[7];
    v14 = v12 + 1;
    memset(&v26[5], 0, 32);
    *((_QWORD *)a3 + 4) = 0;
    *(_DWORD *)a3 = v12 + 1;
    *((_DWORD *)a3 + 1) = -1;
    *((_QWORD *)a3 + 1) = 64;
    *((_QWORD *)a3 + 3) = v12;
    *(_OWORD *)(a3 + 40) = *(_OWORD *)&v26[6];
    *((_QWORD *)a3 + 7) = *(_OWORD *)&_mm_unpackhi_pd((__m128d)0LL, (__m128d)0LL);
    if ( v13 )
    {
      v15 = v13 - v14;
      if ( v15 )
      {
        if ( v15 != v14 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(
              WPP_GLOBAL_Control->AttachedDevice,
              (unsigned int)(v12 + 122),
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
          v5 = -1073741436;
          goto LABEL_40;
        }
        v16 = *(_DWORD *)&v27[11];
        *((_DWORD *)a3 + 8) = 2;
        *((_QWORD *)a3 + 6) = ConvertWhiteBalancePresets(v16);
LABEL_29:
        v17 = GetExtPropFlags(*(unsigned __int8 *)(v9 + 15)) | 0x8000000000000000uLL;
        *((_QWORD *)a3 + 3) = v17;
        v18 = *(unsigned int *)(v9 + 11);
        *((_DWORD *)a3 + 9) = v18;
        v19 = *(unsigned int *)(v9 + 26);
        *((_DWORD *)a3 + 10) = v19;
        *((_DWORD *)a3 + 11) = *(_DWORD *)(v9 + 56);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_DiiDDD(
            WPP_GLOBAL_Control->AttachedDevice,
            v18,
            v19,
            *((unsigned int *)a3 + 12),
            *((_QWORD *)a3 + 2),
            v17,
            v18,
            v19,
            *((_DWORD *)a3 + 8));
        a1->IoStatus.Information = 64;
        goto LABEL_40;
      }
      *((_DWORD *)a3 + 8) = v14;
    }
    else
    {
      *((_DWORD *)a3 + 8) = v12;
    }
    *((_DWORD *)a3 + 12) = *(_DWORD *)&v27[11];
    goto LABEL_29;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_43;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v8 = (unsigned int)(v6 + 120);
LABEL_39:
    WPP_SF_(v7->AttachedDevice, v8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_40:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 126, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v5);
LABEL_43:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140059890  mov     [rsp-8+arg_8], rbx
0x140059895  push    rbp
0x140059896  push    rsi
0x140059897  push    rdi
0x140059898  push    r12
0x14005989a  push    r14
0x14005989c  lea     rbp, [rsp-37h]
0x1400598a1  sub     rsp, 0C0h
0x1400598a8  mov     rax, cs:__security_cookie
0x1400598af  xor     rax, rsp
0x1400598b2  mov     [rbp+57h+var_30], rax
0x1400598b6  mov     rbx, r8
0x1400598b9  mov     [rbp+57h+var_8F], 0
0x1400598bd  mov     rsi, rcx
0x1400598c0  mov     [rbp+57h+var_90], 0
0x1400598c4  mov     [rbp+57h+var_88], 0
0x1400598cc  mov     [rbp+57h+var_40], 0
0x1400598d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400598db  lea     r12, WPP_GLOBAL_Control
0x1400598e2  cmp     rcx, r12
0x1400598e5  jz      short loc_140059905
0x1400598e7  cmp     byte ptr [rcx+29h], 2
0x1400598eb  jb      short loc_140059905
0x1400598ed  mov     rcx, [rcx+18h]
0x1400598f1  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400598f8  mov     edx, 77h ; 'w'
0x1400598fd  mov     r9, rsi
0x140059900  call    WPP_SF_q
0x140059905  lea     rax, [rbp+57h+var_40]
0x140059909  xor     edx, edx; struct _KSFILTER **
0x14005990b  mov     [rsp+0E0h+var_B8], rax; struct _HW_DEVICE_EXTENSION **
0x140059910  lea     r9, [rbp+57h+var_90]; unsigned __int8 *
0x140059914  lea     rax, [rbp+57h+var_88]
0x140059918  mov     rcx, rsi; struct _IRP *
0x14005991b  lea     r8, [rbp+57h+var_8F]; unsigned __int8 *
0x14005991f  mov     [rsp+0E0h+var_C0], rax; struct _TOPOLOGY_NODE_INFO **
0x140059924  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140059929  mov     edi, eax
0x14005992b  test    eax, eax
0x14005992d  js      loc_140059BAA
0x140059933  xor     r9d, r9d
0x140059936  mov     rdx, rbx
0x140059939  mov     rcx, rsi
0x14005993c  lea     r8d, [r9+40h]
0x140059940  call    ValidateExtendedPropertyDataBufferLength
0x140059945  mov     edi, eax
0x140059947  test    eax, eax
0x140059949  jns     short loc_14005996E
0x14005994b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059952  cmp     rcx, r12
0x140059955  jz      loc_140059BD4
0x14005995b  cmp     byte ptr [rcx+29h], 2
0x14005995f  jb      loc_140059BAA
0x140059965  lea     edx, [r9+78h]
0x140059969  jmp     loc_140059B9A
0x14005996e  mov     rcx, rbx; this
0x140059971  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ; CExtendedVidProcSetting::isValid(void)
0x140059976  test    al, al
0x140059978  jz      loc_140059B7E
0x14005997e  cmp     dword ptr [rbx+4], 0FFFFFFFFh
0x140059982  jnz     loc_140059B7E
0x140059988  mov     rcx, [rbp+57h+var_40]
0x14005998c  mov     r8d, 400h; int
0x140059992  mov     r9b, [rbp+57h+var_8F]; int
0x140059996  mov     dl, 81h; int
0x140059998  mov     [rsp+0E0h+var_A0], rcx; __int64
0x14005999d  mov     r14, [rcx+3D8h]
0x1400599a4  mov     cl, 0A1h; int
0x1400599a6  mov     eax, [r14+26h]
0x1400599aa  movsd   xmm0, qword ptr [r14+1Eh]
0x1400599b0  mov     [rbp+57h+var_38], eax
0x1400599b3  movzx   eax, word ptr [r14+2Ah]
0x1400599b8  mov     [rbp+57h+var_34], ax
0x1400599bc  mov     al, [r14+2Ch]
0x1400599c0  mov     [rbp+57h+var_32], al
0x1400599c3  mov     rax, [rbp+57h+var_88]
0x1400599c7  mov     [rsp+0E0h+var_A8], rax; __int64
0x1400599cc  lea     rax, [rbp+57h+var_40]
0x1400599d0  mov     dword ptr [rsp+0E0h+Size], 0Fh; Size
0x1400599d8  mov     [rsp+0E0h+var_B8], rax; void *
0x1400599dd  mov     al, [rbp+57h+var_90]
0x1400599e0  mov     byte ptr [rsp+0E0h+var_C0], al; int
0x1400599e4  movsd   [rbp+57h+var_40], xmm0
0x1400599e9  call    SubmitControlRequest
0x1400599ee  mov     edi, eax
0x1400599f0  test    eax, eax
0x1400599f2  js      loc_140059B65
0x1400599f8  movzx   edx, byte ptr [rbp+57h+var_40]
0x1400599fc  mov     al, dl
0x1400599fe  and     al, 7
0x140059a00  cmp     al, dl
0x140059a02  jz      short loc_140059A36
0x140059a04  mov     rcx, cs:WPP_GLOBAL_Control
0x140059a0b  cmp     rcx, r12
0x140059a0e  jz      short loc_140059A31
0x140059a10  cmp     byte ptr [rcx+29h], 2
0x140059a14  jb      short loc_140059A31
0x140059a16  mov     rcx, [rcx+18h]
0x140059a1a  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059a21  mov     r9d, edx
0x140059a24  mov     edx, 79h ; 'y'
0x140059a29  call    WPP_SF_d
0x140059a2e  mov     dl, byte ptr [rbp+57h+var_40]
0x140059a31  mov     edi, 0C0000184h
0x140059a36  test    edi, edi
0x140059a38  js      loc_140059B65
0x140059a3e  movzx   ecx, dl; unsigned int
0x140059a41  xor     r11d, r11d
0x140059a44  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x140059a49  xorps   xmm1, xmm1
0x140059a4c  mov     [rbx+10h], rax
0x140059a50  mov     eax, dword ptr [rbp+57h+var_40+7]
0x140059a53  lea     ecx, [r11+1]
0x140059a57  movaps  [rbp+57h+var_60], xmm1
0x140059a5b  movaps  [rbp+57h+var_50], xmm1
0x140059a5f  movsd   qword ptr [rbx+20h], xmm1
0x140059a64  unpckhpd xmm1, xmm1
0x140059a68  mov     [rbx], ecx
0x140059a6a  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x140059a71  mov     qword ptr [rbx+8], 40h ; '@'
0x140059a79  mov     [rbx+18h], r11
0x140059a7d  movups  xmm0, [rbp+57h+var_60+8]
0x140059a81  movups  xmmword ptr [rbx+28h], xmm0
0x140059a85  movsd   qword ptr [rbx+38h], xmm1
0x140059a8a  test    eax, eax
0x140059a8c  jz      short loc_140059AE0
0x140059a8e  sub     eax, ecx
0x140059a90  jz      short loc_140059ADB
0x140059a92  cmp     eax, ecx
0x140059a94  jz      short loc_140059AC6
0x140059a96  mov     rcx, cs:WPP_GLOBAL_Control
0x140059a9d  cmp     rcx, r12
0x140059aa0  jz      short loc_140059ABC
0x140059aa2  cmp     byte ptr [rcx+29h], 2
0x140059aa6  jb      short loc_140059ABC
0x140059aa8  mov     rcx, [rcx+18h]
0x140059aac  lea     edx, [r11+7Ah]
0x140059ab0  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059ab7  call    WPP_SF_
0x140059abc  mov     edi, 0C0000184h
0x140059ac1  jmp     loc_140059BAA
0x140059ac6  mov     ecx, [rbp+57h+var_38+3]; unsigned int
0x140059ac9  mov     dword ptr [rbx+20h], 2
0x140059ad0  call    ?ConvertWhiteBalancePresets@@YA_KK@Z; ConvertWhiteBalancePresets(ulong)
0x140059ad5  mov     [rbx+30h], rax
0x140059ad9  jmp     short loc_140059AEA
0x140059adb  mov     [rbx+20h], ecx
0x140059ade  jmp     short loc_140059AE4
0x140059ae0  mov     [rbx+20h], r11d
0x140059ae4  mov     eax, [rbp+57h+var_38+3]
0x140059ae7  mov     [rbx+30h], eax
0x140059aea  movzx   ecx, byte ptr [r14+0Fh]; unsigned int
0x140059aef  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x140059af4  mov     r10, rax
0x140059af7  mov     rax, 8000000000000000h
0x140059b01  or      r10, rax
0x140059b04  mov     [rbx+18h], r10
0x140059b08  mov     edx, [r14+0Bh]
0x140059b0c  mov     [rbx+24h], edx
0x140059b0f  mov     r8d, [r14+1Ah]
0x140059b13  mov     [rbx+28h], r8d
0x140059b17  mov     ecx, [r14+38h]
0x140059b1b  mov     [rbx+2Ch], ecx
0x140059b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059b25  cmp     rcx, r12
0x140059b28  jz      short loc_140059B5B
0x140059b2a  cmp     byte ptr [rcx+29h], 4
0x140059b2e  jb      short loc_140059B5B
0x140059b30  mov     eax, [rbx+20h]
0x140059b33  mov     r9d, [rbx+30h]
0x140059b37  mov     rcx, [rcx+18h]
0x140059b3b  mov     dword ptr [rsp+0E0h+var_A0], eax
0x140059b3f  mov     rax, [rbx+10h]
0x140059b43  mov     dword ptr [rsp+0E0h+var_A8], r8d
0x140059b48  mov     dword ptr [rsp+0E0h+Size], edx
0x140059b4c  mov     [rsp+0E0h+var_B8], r10
0x140059b51  mov     [rsp+0E0h+var_C0], rax
0x140059b56  call    WPP_SF_DiiDDD
0x140059b5b  mov     qword ptr [rsi+38h], 40h ; '@'
0x140059b63  jmp     short loc_140059BAA
0x140059b65  mov     rcx, cs:WPP_GLOBAL_Control
0x140059b6c  cmp     rcx, r12
0x140059b6f  jz      short loc_140059BD4
0x140059b71  cmp     byte ptr [rcx+29h], 2
0x140059b75  jb      short loc_140059BAA
0x140059b77  mov     edx, 7Ch ; '|'
0x140059b7c  jmp     short loc_140059B9A
0x140059b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140059b85  mov     edi, 0C000000Dh
0x140059b8a  cmp     rcx, r12
0x140059b8d  jz      short loc_140059BD4
0x140059b8f  cmp     byte ptr [rcx+29h], 2
0x140059b93  jb      short loc_140059BAA
0x140059b95  mov     edx, 7Dh ; '}'
0x140059b9a  mov     rcx, [rcx+18h]
0x140059b9e  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059ba5  call    WPP_SF_
0x140059baa  mov     rcx, cs:WPP_GLOBAL_Control
0x140059bb1  cmp     rcx, r12
0x140059bb4  jz      short loc_140059BD4
0x140059bb6  cmp     byte ptr [rcx+29h], 4
0x140059bba  jb      short loc_140059BD4
0x140059bbc  mov     rcx, [rcx+18h]
0x140059bc0  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059bc7  mov     edx, 7Eh ; '~'
0x140059bcc  mov     r9d, edi
0x140059bcf  call    WPP_SF_d
0x140059bd4  mov     [rsi+30h], edi
0x140059bd7  mov     eax, edi
0x140059bd9  mov     rcx, [rbp+57h+var_30]
0x140059bdd  xor     rcx, rsp; StackCookie
0x140059be0  call    __security_check_cookie
0x140059be5  mov     rbx, [rsp+0E0h+arg_8]
0x140059bed  add     rsp, 0C0h
0x140059bf4  pop     r14
0x140059bf6  pop     r12
0x140059bf8  pop     rdi
0x140059bf9  pop     rsi
0x140059bfa  pop     rbp
0x140059bfb  retn
```
