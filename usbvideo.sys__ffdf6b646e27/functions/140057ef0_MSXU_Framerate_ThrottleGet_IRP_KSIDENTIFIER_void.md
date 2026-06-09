# MSXU_Framerate_ThrottleGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140057ef0`
- end: `0x1400581f6`
- name: `?MSXU_Framerate_ThrottleGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `774`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14000ef88`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b1ec`
- `0x140040a30`
- `0x140057ef0`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_Framerate_ThrottleGet(struct _IRP *a1, struct KSIDENTIFIER *a2, _QWORD *a3)
{
  NTSTATUS v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // r11d
  unsigned int v10; // ecx
  int v11; // r10d
  int v12; // r8d
  int v14; // [rsp+20h] [rbp-39h]
  size_t Size; // [rsp+30h] [rbp-29h]
  unsigned __int8 v16; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int8 v17[7]; // [rsp+51h] [rbp-8h] BYREF
  struct _HW_DEVICE_EXTENSION *v18; // [rsp+58h] [rbp-1h] BYREF
  struct _TOPOLOGY_NODE_INFO *v19; // [rsp+60h] [rbp+7h] BYREF
  __int128 v20; // [rsp+68h] [rbp+Fh] BYREF
  unsigned int v21; // [rsp+78h] [rbp+1Fh]

  v17[0] = 0;
  v16 = 0;
  v19 = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 243, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, 0, v17, &v16, &v19, &v18);
  if ( v5 < 0 )
    goto LABEL_34;
  v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 64);
  if ( v5 >= 0 )
  {
    if ( CExtendedVidProcSetting::isValid((CExtendedVidProcSetting *)a3) && *((_DWORD *)a3 + 1) == -1 )
    {
      v21 = 0;
      LODWORD(Size) = 20;
      LOBYTE(v14) = v16;
      v20 = 0;
      v8 = SubmitControlRequest(
             0xA1u,
             0x81u,
             0xE00u,
             v17[0],
             v14,
             (unsigned __int8 *)&v20,
             Size,
             (__int64)v19,
             (__int64)v18);
      v5 = v8;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_37;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            247,
            WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
            (unsigned int)v8);
      }
      else
      {
        v9 = v21;
        v10 = v20 & 1;
        v11 = DWORD2(v20);
        v12 = DWORD1(v20);
        if ( v10 != (_DWORD)v20
          || HIDWORD(v20) != 100
          || (unsigned int)(DWORD2(v20) - 1) > 0x62
          || DWORD2(v20) % v21
          || 0x64 % v21
          || DWORD1(v20) > 0x64
          || DWORD1(v20) < DWORD2(v20)
          || DWORD1(v20) % v21 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_LLLLL(WPP_GLOBAL_Control->AttachedDevice, 245);
          v5 = -1073741811;
        }
        else
        {
          a3[3] = 1;
          a3[2] = v10;
          *((_DWORD *)a3 + 9) = v11;
          *((_DWORD *)a3 + 10) = 100;
          *((_DWORD *)a3 + 11) = v9;
          *((_DWORD *)a3 + 12) = v12;
          a1->IoStatus.Information = 64;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_37;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_LLLLL(WPP_GLOBAL_Control->AttachedDevice, 246);
        }
      }
      goto LABEL_34;
    }
    v6 = WPP_GLOBAL_Control;
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v7 = 248;
      goto LABEL_33;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v7 = 244;
LABEL_33:
      WPP_SF_(v6->AttachedDevice, v7, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
    }
  }
LABEL_34:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 249, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v5);
LABEL_37:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140057ef0  mov     [rsp-8+arg_8], rbx
0x140057ef5  push    rbp
0x140057ef6  push    rsi
0x140057ef7  push    rdi
0x140057ef8  push    r12
0x140057efa  push    r14
0x140057efc  lea     rbp, [rsp-37h]
0x140057f01  sub     rsp, 90h
0x140057f08  mov     rax, cs:__security_cookie
0x140057f0f  xor     rax, rsp
0x140057f12  mov     [rbp+57h+var_30], rax
0x140057f16  mov     rdi, r8
0x140057f19  mov     [rbp+57h+var_5F], 0
0x140057f1d  mov     rsi, rcx
0x140057f20  mov     [rbp+57h+var_60], 0
0x140057f24  mov     [rbp+57h+var_50], 0
0x140057f2c  mov     [rbp+57h+var_58], 0
0x140057f34  mov     rcx, cs:WPP_GLOBAL_Control
0x140057f3b  lea     r12, WPP_GLOBAL_Control
0x140057f42  cmp     rcx, r12
0x140057f45  jz      short loc_140057F65
0x140057f47  cmp     byte ptr [rcx+29h], 2
0x140057f4b  jb      short loc_140057F65
0x140057f4d  mov     rcx, [rcx+18h]
0x140057f51  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140057f58  mov     edx, 0F3h
0x140057f5d  mov     r9, rsi
0x140057f60  call    WPP_SF_q
0x140057f65  lea     rax, [rbp+57h+var_58]
0x140057f69  xor     edx, edx; struct _KSFILTER **
0x140057f6b  mov     [rsp+0B0h+var_88], rax; struct _HW_DEVICE_EXTENSION **
0x140057f70  lea     r9, [rbp+57h+var_60]; unsigned __int8 *
0x140057f74  lea     rax, [rbp+57h+var_50]
0x140057f78  mov     rcx, rsi; struct _IRP *
0x140057f7b  lea     r8, [rbp+57h+var_5F]; unsigned __int8 *
0x140057f7f  mov     [rsp+0B0h+var_90], rax; struct _TOPOLOGY_NODE_INFO **
0x140057f84  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140057f89  mov     ebx, eax
0x140057f8b  test    eax, eax
0x140057f8d  js      loc_1400581A3
0x140057f93  xor     r9d, r9d
0x140057f96  mov     rdx, rdi
0x140057f99  mov     rcx, rsi
0x140057f9c  lea     r8d, [r9+40h]
0x140057fa0  call    ValidateExtendedPropertyDataBufferLength
0x140057fa5  mov     ebx, eax
0x140057fa7  test    eax, eax
0x140057fa9  jns     short loc_140057FCF
0x140057fab  mov     rcx, cs:WPP_GLOBAL_Control
0x140057fb2  cmp     rcx, r12
0x140057fb5  jz      loc_1400581CD
0x140057fbb  cmp     byte ptr [rcx+29h], 2
0x140057fbf  jb      loc_1400581A3
0x140057fc5  mov     edx, 0F4h
0x140057fca  jmp     loc_140058193
0x140057fcf  mov     rcx, rdi; this
0x140057fd2  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ; CExtendedVidProcSetting::isValid(void)
0x140057fd7  test    al, al
0x140057fd9  jz      loc_140058177
0x140057fdf  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x140057fe3  jnz     loc_140058177
0x140057fe9  mov     r9b, [rbp+57h+var_5F]; int
0x140057fed  xor     eax, eax
0x140057fef  mov     [rbp+57h+var_38], eax
0x140057ff2  xorps   xmm0, xmm0
0x140057ff5  mov     rax, [rbp+57h+var_58]
0x140057ff9  mov     r8d, 0E00h; int
0x140057fff  mov     [rsp+0B0h+var_70], rax; __int64
0x140058004  mov     dl, 81h; int
0x140058006  mov     rax, [rbp+57h+var_50]
0x14005800a  mov     cl, 0A1h; int
0x14005800c  mov     [rsp+0B0h+var_78], rax; __int64
0x140058011  lea     rax, [rbp+57h+var_48]
0x140058015  mov     dword ptr [rsp+0B0h+Size], 14h; Size
0x14005801d  mov     [rsp+0B0h+var_88], rax; void *
0x140058022  mov     al, [rbp+57h+var_60]
0x140058025  mov     byte ptr [rsp+0B0h+var_90], al; int
0x140058029  movups  [rbp+57h+var_48], xmm0
0x14005802d  call    SubmitControlRequest
0x140058032  mov     ebx, eax
0x140058034  test    eax, eax
0x140058036  js      loc_14005814B
0x14005803c  mov     r9d, dword ptr [rbp+57h+var_48]
0x140058040  mov     ecx, r9d
0x140058043  mov     r11d, [rbp+57h+var_38]
0x140058047  and     ecx, 1
0x14005804a  mov     r14d, dword ptr [rbp+57h+var_48+0Ch]
0x14005804e  mov     r10d, dword ptr [rbp+57h+var_48+8]
0x140058052  mov     r8d, dword ptr [rbp+57h+var_48+4]
0x140058056  cmp     ecx, r9d
0x140058059  jnz     loc_140058110
0x14005805f  cmp     r14d, 64h ; 'd'
0x140058063  jnz     loc_140058110
0x140058069  lea     eax, [r10-1]
0x14005806d  cmp     eax, 62h ; 'b'
0x140058070  ja      loc_140058110
0x140058076  xor     edx, edx
0x140058078  mov     eax, r10d
0x14005807b  div     r11d
0x14005807e  test    edx, edx
0x140058080  jnz     loc_140058110
0x140058086  xor     edx, edx
0x140058088  mov     eax, r14d
0x14005808b  div     r11d
0x14005808e  test    edx, edx
0x140058090  jnz     short loc_140058110
0x140058092  cmp     r8d, r14d
0x140058095  ja      short loc_140058110
0x140058097  cmp     r8d, r10d
0x14005809a  jb      short loc_140058110
0x14005809c  xor     edx, edx
0x14005809e  mov     eax, r8d
0x1400580a1  div     r11d
0x1400580a4  test    edx, edx
0x1400580a6  jnz     short loc_140058110
0x1400580a8  mov     qword ptr [rdi+18h], 1
0x1400580b0  mov     eax, ecx
0x1400580b2  mov     [rdi+10h], rax
0x1400580b6  mov     eax, r14d
0x1400580b9  mov     [rdi+24h], r10d
0x1400580bd  mov     [rdi+28h], eax
0x1400580c0  mov     [rdi+2Ch], r11d
0x1400580c4  mov     [rdi+30h], r8d
0x1400580c8  mov     qword ptr [rsi+38h], 40h ; '@'
0x1400580d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400580d7  cmp     rcx, r12
0x1400580da  jz      loc_1400581CD
0x1400580e0  cmp     byte ptr [rcx+29h], 4
0x1400580e4  jb      loc_1400581A3
0x1400580ea  mov     rcx, [rcx+18h]
0x1400580ee  mov     edx, 0F6h
0x1400580f3  mov     dword ptr [rsp+0B0h+var_78], r11d
0x1400580f8  mov     dword ptr [rsp+0B0h+Size], eax
0x1400580fc  mov     dword ptr [rsp+0B0h+var_88], r10d
0x140058101  mov     dword ptr [rsp+0B0h+var_90], r8d
0x140058106  call    WPP_SF_LLLLL
0x14005810b  jmp     loc_1400581A3
0x140058110  mov     rcx, cs:WPP_GLOBAL_Control
0x140058117  cmp     rcx, r12
0x14005811a  jz      short loc_140058144
0x14005811c  cmp     byte ptr [rcx+29h], 2
0x140058120  jb      short loc_140058144
0x140058122  mov     rcx, [rcx+18h]
0x140058126  mov     edx, 0F5h
0x14005812b  mov     dword ptr [rsp+0B0h+var_78], r11d
0x140058130  mov     dword ptr [rsp+0B0h+Size], r14d
0x140058135  mov     dword ptr [rsp+0B0h+var_88], r10d
0x14005813a  mov     dword ptr [rsp+0B0h+var_90], r8d
0x14005813f  call    WPP_SF_LLLLL
0x140058144  mov     ebx, 0C000000Dh
0x140058149  jmp     short loc_1400581A3
0x14005814b  mov     rcx, cs:WPP_GLOBAL_Control
0x140058152  cmp     rcx, r12
0x140058155  jz      short loc_1400581CD
0x140058157  cmp     byte ptr [rcx+29h], 2
0x14005815b  jb      short loc_1400581A3
0x14005815d  mov     rcx, [rcx+18h]
0x140058161  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140058168  mov     edx, 0F7h
0x14005816d  mov     r9d, eax
0x140058170  call    WPP_SF_d
0x140058175  jmp     short loc_1400581A3
0x140058177  mov     rcx, cs:WPP_GLOBAL_Control
0x14005817e  mov     ebx, 0C000000Dh
0x140058183  cmp     rcx, r12
0x140058186  jz      short loc_1400581CD
0x140058188  cmp     byte ptr [rcx+29h], 2
0x14005818c  jb      short loc_1400581A3
0x14005818e  mov     edx, 0F8h
0x140058193  mov     rcx, [rcx+18h]
0x140058197  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005819e  call    WPP_SF_
0x1400581a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400581aa  cmp     rcx, r12
0x1400581ad  jz      short loc_1400581CD
0x1400581af  cmp     byte ptr [rcx+29h], 4
0x1400581b3  jb      short loc_1400581CD
0x1400581b5  mov     rcx, [rcx+18h]
0x1400581b9  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400581c0  mov     edx, 0F9h
0x1400581c5  mov     r9d, ebx
0x1400581c8  call    WPP_SF_d
0x1400581cd  mov     [rsi+30h], ebx
0x1400581d0  mov     eax, ebx
0x1400581d2  mov     rcx, [rbp+57h+var_30]
0x1400581d6  xor     rcx, rsp; StackCookie
0x1400581d9  call    __security_check_cookie
0x1400581de  mov     rbx, [rsp+0B0h+arg_8]
0x1400581e6  add     rsp, 90h
0x1400581ed  pop     r14
0x1400581ef  pop     r12
0x1400581f1  pop     rdi
0x1400581f2  pop     rsi
0x1400581f3  pop     rbp
0x1400581f4  retn
```
