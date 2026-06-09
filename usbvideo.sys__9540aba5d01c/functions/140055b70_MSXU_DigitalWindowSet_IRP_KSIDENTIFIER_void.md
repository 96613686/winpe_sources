# MSXU_DigitalWindowSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140055b70`
- end: `0x140055f2c`
- name: `?MSXU_DigitalWindowSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `956`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x1400053fc`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14001d120`
- `0x14003b85c`
- `0x140040a30`
- `0x140055b70`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_DigitalWindowSet(struct _IRP *a1, struct KSIDENTIFIER *a2, _DWORD *a3)
{
  NTSTATUS v6; // edi
  unsigned int v7; // r8d
  _DWORD *v8; // rax
  __int64 v9; // r9
  struct _HW_DEVICE_EXTENSION *v10; // r14
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // eax
  __int64 v15; // r9
  int v16; // r8d
  int v17; // r10d
  unsigned __int8 v18; // r9
  int v19; // eax
  int v21; // [rsp+20h] [rbp-60h]
  size_t Size; // [rsp+30h] [rbp-50h]
  struct _TOPOLOGY_NODE_INFO *v23; // [rsp+38h] [rbp-48h]
  unsigned __int8 v24; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int8 v25[7]; // [rsp+51h] [rbp-2Fh] BYREF
  struct _KSFILTER *v26; // [rsp+58h] [rbp-28h] BYREF
  struct _TOPOLOGY_NODE_INFO *v27; // [rsp+60h] [rbp-20h] BYREF
  struct _HW_DEVICE_EXTENSION *v28; // [rsp+68h] [rbp-18h] BYREF
  int v29; // [rsp+70h] [rbp-10h]
  int v30; // [rsp+74h] [rbp-Ch]

  v25[0] = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 203, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  if ( !a1 || !a2 || !a3 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_50;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 204, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1, a2, a3);
    goto LABEL_47;
  }
  v6 = MSXUGetInfo(a1, &v26, v25, &v24, &v27, &v28);
  if ( v6 >= 0 )
  {
    v6 = ValidateExtendedPropertyDataBufferLength(a1, a3, 48);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_50;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 206, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      goto LABEL_47;
    }
    v8 = a3 + 1;
    v6 = -1073741811;
    if ( *a3 != 1 || *v8 != -1 || a3[2] < v7 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_50;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          212,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          (unsigned int)a3[2],
          *v8);
      goto LABEL_47;
    }
    v9 = *((_QWORD *)a3 + 2);
    v10 = v28;
    if ( v9 == (v9 & *(_DWORD *)(*((_QWORD *)v28 + 130) + 16LL) & 1) )
    {
      if ( v9 )
      {
        if ( v9 != 1 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_50;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            goto LABEL_47;
          v12 = 210;
LABEL_24:
          WPP_SF_ii(v11->AttachedDevice, v12);
          goto LABEL_47;
        }
      }
      else
      {
        v13 = a3[10];
        if ( v13 <= 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_50;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              207,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              (unsigned int)v13);
          goto LABEL_47;
        }
      }
      v14 = a3[8];
      v15 = *((_QWORD *)a3 + 2) & 1LL;
      v16 = a3[9];
      v17 = a3[10];
      v28 = (struct _HW_DEVICE_EXTENSION *)__PAIR64__(v14, v15);
      v29 = v16;
      v30 = v17;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_DDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          208,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          v15,
          v14,
          v16,
          v17);
      v18 = v25[0];
      *((_QWORD *)v10 + 147) = v26;
      v23 = v27;
      LODWORD(Size) = 16;
      LOBYTE(v21) = v24;
      *((_DWORD *)v10 + 330) = 1;
      v19 = SubmitControlRequest(0x21u, 1u, 0xB00u, v18, v21, (unsigned __int8 *)&v28, Size, (__int64)v23, (__int64)v10);
      v6 = v19;
      if ( v19 >= 0 )
      {
        a1->IoStatus.Information = 48;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            209,
            WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
            (unsigned int)v19);
        *((_QWORD *)v10 + 147) = 0;
      }
      goto LABEL_47;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_50;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_47;
    v12 = 211;
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_50;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 205, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
LABEL_47:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 213, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v6);
LABEL_50:
  a1->IoStatus.Status = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140055b70  push    rbp
0x140055b72  push    rbx
0x140055b73  push    rsi
0x140055b74  push    rdi
0x140055b75  push    r12
0x140055b77  push    r13
0x140055b79  push    r14
0x140055b7b  mov     rbp, rsp
0x140055b7e  sub     rsp, 80h
0x140055b85  mov     rax, cs:__security_cookie
0x140055b8c  xor     rax, rsp
0x140055b8f  mov     [rbp+var_8], rax
0x140055b93  mov     rbx, r8
0x140055b96  mov     [rbp+var_2F], 0
0x140055b9a  mov     r14, rdx
0x140055b9d  mov     [rbp+var_30], 0
0x140055ba1  mov     rsi, rcx
0x140055ba4  mov     [rbp+var_20], 0
0x140055bac  mov     [rbp+var_18], 0
0x140055bb4  mov     [rbp+var_28], 0
0x140055bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140055bc3  lea     r12, WPP_GLOBAL_Control
0x140055bca  lea     r13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140055bd1  cmp     rcx, r12
0x140055bd4  jz      short loc_140055BF0
0x140055bd6  cmp     byte ptr [rcx+29h], 4
0x140055bda  jb      short loc_140055BF0
0x140055bdc  mov     rcx, [rcx+18h]
0x140055be0  mov     edx, 0CBh
0x140055be5  mov     r9, rsi
0x140055be8  mov     r8, r13
0x140055beb  call    WPP_SF_q
0x140055bf0  test    rsi, rsi
0x140055bf3  jz      loc_140055EAD
0x140055bf9  test    r14, r14
0x140055bfc  jz      loc_140055EAD
0x140055c02  test    rbx, rbx
0x140055c05  jz      loc_140055EAD
0x140055c0b  lea     rax, [rbp+var_18]
0x140055c0f  mov     rcx, rsi; struct _IRP *
0x140055c12  mov     [rsp+80h+var_58], rax; struct _HW_DEVICE_EXTENSION **
0x140055c17  lea     r9, [rbp+var_30]; unsigned __int8 *
0x140055c1b  lea     rax, [rbp+var_20]
0x140055c1f  lea     r8, [rbp+var_2F]; unsigned __int8 *
0x140055c23  mov     [rsp+80h+var_60], rax; struct _TOPOLOGY_NODE_INFO **
0x140055c28  lea     rdx, [rbp+var_28]; struct _KSFILTER **
0x140055c2c  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140055c31  mov     edi, eax
0x140055c33  test    eax, eax
0x140055c35  jns     short loc_140055C6A
0x140055c37  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c3e  cmp     rcx, r12
0x140055c41  jz      loc_140055F08
0x140055c47  cmp     byte ptr [rcx+29h], 2
0x140055c4b  jb      loc_140055EE2
0x140055c51  mov     rcx, [rcx+18h]
0x140055c55  mov     edx, 0CDh
0x140055c5a  mov     r9, rsi
0x140055c5d  mov     r8, r13
0x140055c60  call    WPP_SF_q
0x140055c65  jmp     loc_140055EE2
0x140055c6a  xor     r9d, r9d
0x140055c6d  mov     rdx, rbx
0x140055c70  mov     rcx, rsi
0x140055c73  lea     r8d, [r9+30h]
0x140055c77  call    ValidateExtendedPropertyDataBufferLength
0x140055c7c  mov     edi, eax
0x140055c7e  test    eax, eax
0x140055c80  jns     short loc_140055CB2
0x140055c82  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c89  cmp     rcx, r12
0x140055c8c  jz      loc_140055F08
0x140055c92  cmp     byte ptr [rcx+29h], 2
0x140055c96  jb      loc_140055EE2
0x140055c9c  mov     rcx, [rcx+18h]
0x140055ca0  mov     edx, 0CEh
0x140055ca5  mov     r8, r13
0x140055ca8  call    WPP_SF_
0x140055cad  jmp     loc_140055EE2
0x140055cb2  cmp     dword ptr [rbx], 1
0x140055cb5  lea     rax, [rbx+4]
0x140055cb9  mov     edi, 0C000000Dh
0x140055cbe  jnz     loc_140055E7E
0x140055cc4  cmp     dword ptr [rax], 0FFFFFFFFh
0x140055cc7  jnz     loc_140055E7E
0x140055ccd  cmp     [rbx+8], r8d
0x140055cd1  jb      loc_140055E7E
0x140055cd7  mov     r9, [rbx+10h]
0x140055cdb  mov     r14, [rbp+var_18]
0x140055cdf  mov     rax, [r14+410h]
0x140055ce6  mov     r8d, [rax+10h]
0x140055cea  and     r8d, 1
0x140055cee  mov     eax, r8d
0x140055cf1  and     rax, r9
0x140055cf4  cmp     r9, rax
0x140055cf7  jnz     loc_140055E5E
0x140055cfd  mov     rax, r9
0x140055d00  test    r9, r9
0x140055d03  jz      short loc_140055D3D
0x140055d05  cmp     rax, 1
0x140055d09  jz      short loc_140055D77
0x140055d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d12  cmp     rcx, r12
0x140055d15  jz      loc_140055F08
0x140055d1b  cmp     byte ptr [rcx+29h], 2
0x140055d1f  jb      loc_140055EE2
0x140055d25  mov     edx, 0D2h
0x140055d2a  mov     rcx, [rcx+18h]
0x140055d2e  mov     [rsp+80h+var_60], r8
0x140055d33  call    WPP_SF_ii
0x140055d38  jmp     loc_140055EE2
0x140055d3d  mov     eax, [rbx+28h]
0x140055d40  test    eax, eax
0x140055d42  jg      short loc_140055D77
0x140055d44  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d4b  cmp     rcx, r12
0x140055d4e  jz      loc_140055F08
0x140055d54  cmp     byte ptr [rcx+29h], 2
0x140055d58  jb      loc_140055EE2
0x140055d5e  mov     rcx, [rcx+18h]
0x140055d62  mov     edx, 0CFh
0x140055d67  mov     r9d, eax
0x140055d6a  mov     r8, r13
0x140055d6d  call    WPP_SF_d
0x140055d72  jmp     loc_140055EE2
0x140055d77  mov     eax, [rbx+20h]
0x140055d7a  and     r9d, 1
0x140055d7e  mov     r8d, [rbx+24h]
0x140055d82  mov     r10d, [rbx+28h]
0x140055d86  mov     dword ptr [rbp+var_18], r9d
0x140055d8a  mov     dword ptr [rbp+var_18+4], eax
0x140055d8d  mov     [rbp+var_10], r8d
0x140055d91  mov     [rbp+var_C], r10d
0x140055d95  mov     rcx, cs:WPP_GLOBAL_Control
0x140055d9c  cmp     rcx, r12
0x140055d9f  jz      short loc_140055DC6
0x140055da1  cmp     byte ptr [rcx+29h], 4
0x140055da5  jb      short loc_140055DC6
0x140055da7  mov     rcx, [rcx+18h]
0x140055dab  mov     edx, 0D0h
0x140055db0  mov     dword ptr [rsp+80h+Size], r10d
0x140055db5  mov     dword ptr [rsp+80h+var_58], r8d
0x140055dba  mov     r8, r13
0x140055dbd  mov     dword ptr [rsp+80h+var_60], eax
0x140055dc1  call    WPP_SF_DDDD
0x140055dc6  mov     rax, [rbp+var_28]
0x140055dca  mov     r8d, 0B00h; int
0x140055dd0  mov     r9b, [rbp+var_2F]; int
0x140055dd4  mov     dl, 1; int
0x140055dd6  mov     [r14+498h], rax
0x140055ddd  mov     cl, 21h ; '!'; int
0x140055ddf  mov     rax, [rbp+var_20]
0x140055de3  mov     [rsp+80h+var_40], r14; __int64
0x140055de8  mov     [rsp+80h+var_48], rax; __int64
0x140055ded  lea     rax, [rbp+var_18]
0x140055df1  mov     dword ptr [rsp+80h+Size], 10h; Size
0x140055df9  mov     [rsp+80h+var_58], rax; void *
0x140055dfe  mov     al, [rbp+var_30]
0x140055e01  mov     byte ptr [rsp+80h+var_60], al; int
0x140055e05  mov     dword ptr [r14+528h], 1
0x140055e10  call    SubmitControlRequest
0x140055e15  mov     edi, eax
0x140055e17  test    eax, eax
0x140055e19  jns     short loc_140055E51
0x140055e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e22  cmp     rcx, r12
0x140055e25  jz      short loc_140055E41
0x140055e27  cmp     byte ptr [rcx+29h], 2
0x140055e2b  jb      short loc_140055E41
0x140055e2d  mov     rcx, [rcx+18h]
0x140055e31  mov     edx, 0D1h
0x140055e36  mov     r9d, eax
0x140055e39  mov     r8, r13
0x140055e3c  call    WPP_SF_d
0x140055e41  mov     qword ptr [r14+498h], 0
0x140055e4c  jmp     loc_140055EE2
0x140055e51  mov     qword ptr [rsi+38h], 30h ; '0'
0x140055e59  jmp     loc_140055EE2
0x140055e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e65  cmp     rcx, r12
0x140055e68  jz      loc_140055F08
0x140055e6e  cmp     byte ptr [rcx+29h], 2
0x140055e72  jb      short loc_140055EE2
0x140055e74  mov     edx, 0D3h
0x140055e79  jmp     loc_140055D2A
0x140055e7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055e85  cmp     rcx, r12
0x140055e88  jz      short loc_140055F08
0x140055e8a  cmp     byte ptr [rcx+29h], 2
0x140055e8e  jb      short loc_140055EE2
0x140055e90  mov     eax, [rax]
0x140055e92  mov     edx, 0D4h
0x140055e97  mov     r9d, [rbx+8]
0x140055e9b  mov     r8, r13
0x140055e9e  mov     rcx, [rcx+18h]
0x140055ea2  mov     dword ptr [rsp+80h+var_60], eax
0x140055ea6  call    WPP_SF_dd
0x140055eab  jmp     short loc_140055EE2
0x140055ead  mov     rcx, cs:WPP_GLOBAL_Control
0x140055eb4  mov     edi, 0C000000Dh
0x140055eb9  cmp     rcx, r12
0x140055ebc  jz      short loc_140055F08
0x140055ebe  cmp     byte ptr [rcx+29h], 2
0x140055ec2  jb      short loc_140055EE2
0x140055ec4  mov     rcx, [rcx+18h]
0x140055ec8  mov     edx, 0CCh
0x140055ecd  mov     [rsp+80h+var_58], rbx
0x140055ed2  mov     r9, rsi
0x140055ed5  mov     r8, r13
0x140055ed8  mov     [rsp+80h+var_60], r14
0x140055edd  call    WPP_SF_qqq
0x140055ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x140055ee9  cmp     rcx, r12
0x140055eec  jz      short loc_140055F08
0x140055eee  cmp     byte ptr [rcx+29h], 4
0x140055ef2  jb      short loc_140055F08
0x140055ef4  mov     rcx, [rcx+18h]
0x140055ef8  mov     edx, 0D5h
0x140055efd  mov     r9d, edi
0x140055f00  mov     r8, r13
0x140055f03  call    WPP_SF_d
0x140055f08  mov     [rsi+30h], edi
0x140055f0b  mov     eax, edi
0x140055f0d  mov     rcx, [rbp+var_8]
0x140055f11  xor     rcx, rsp; StackCookie
0x140055f14  call    __security_check_cookie
0x140055f19  add     rsp, 80h
0x140055f20  pop     r14
0x140055f22  pop     r13
0x140055f24  pop     r12
0x140055f26  pop     rdi
0x140055f27  pop     rsi
0x140055f28  pop     rbx
0x140055f29  pop     rbp
0x140055f2a  retn
```
