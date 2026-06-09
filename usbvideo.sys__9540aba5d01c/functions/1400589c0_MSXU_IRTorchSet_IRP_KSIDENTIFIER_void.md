# MSXU_IRTorchSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x1400589c0`
- end: `0x140058d1a`
- name: `?MSXU_IRTorchSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `858`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140008640`
- `0x14000de14`
- `0x14000ef88`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b85c`
- `0x1400589c0`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_IRTorchSet(struct _IRP *a1, struct KSIDENTIFIER *a2, CExtendedVidProcSetting *a3)
{
  NTSTATUS v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // r8d
  struct _HW_DEVICE_EXTENSION *v9; // r14
  __int64 v10; // rax
  int v11; // r8d
  __int64 v12; // rdx
  __int64 v13; // r9
  bool v14; // zf
  __int64 v15; // r8
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  int v18; // r10d
  unsigned __int64 v19; // r9
  unsigned int v20; // eax
  unsigned __int8 v21; // r9
  int v22; // eax
  int v24; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  struct _TOPOLOGY_NODE_INFO *v26; // [rsp+38h] [rbp-38h]
  struct _HW_DEVICE_EXTENSION *v27; // [rsp+50h] [rbp-20h] BYREF
  struct _KSFILTER *v28; // [rsp+58h] [rbp-18h] BYREF
  struct _TOPOLOGY_NODE_INFO *v29; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 v30; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int8 v31; // [rsp+B8h] [rbp+48h] BYREF

  v31 = 0;
  v30 = 0;
  v29 = 0;
  v27 = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 186, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, &v28, &v31, &v30, &v29, &v27);
  if ( v5 >= 0 )
  {
    v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 64);
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_50;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_47;
      v7 = (unsigned int)(v8 + 124);
      goto LABEL_8;
    }
    v5 = -1073741811;
    if ( !CExtendedVidProcSetting::isValid(a3) || *((_DWORD *)a3 + 1) != -1 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_50;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          193,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          *((unsigned int *)a3 + 2),
          *((_DWORD *)a3 + 1));
      goto LABEL_47;
    }
    v9 = v27;
    v10 = *((_QWORD *)v27 + 129);
    v11 = *(_DWORD *)(v10 + 8);
    v12 = v11 & 1 | 2LL;
    if ( (v11 & 2) == 0 )
      v12 = *(_DWORD *)(v10 + 8) & 1LL;
    v13 = v12 | 4;
    v14 = (v11 & 4) == 0;
    v15 = *((_QWORD *)a3 + 2);
    if ( v14 )
      v13 = v12;
    if ( v15 == (v15 & v13) )
    {
      if ( v15 == 1 || v15 == 2 || v15 == 4 )
      {
        v18 = *((_DWORD *)a3 + 12);
        v19 = (*((_QWORD *)a3 + 2) & 1LL) != 0;
        v20 = v15 & 1 | 2;
        v27 = (struct _HW_DEVICE_EXTENSION *)v19;
        if ( (v15 & 2) != 0 )
        {
          v19 = v20;
          LODWORD(v27) = v15 & 1 | 2;
        }
        else
        {
          v20 = v15 & 1;
        }
        if ( (v15 & 4) != 0 )
        {
          v19 = v20 | 4;
          LODWORD(v27) = v20 | 4;
        }
        HIDWORD(v27) = v18;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            189,
            WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
            v19,
            HIDWORD(v27));
        v21 = v31;
        *((_QWORD *)v9 + 146) = v28;
        v26 = v29;
        LODWORD(Size) = 8;
        LOBYTE(v24) = v30;
        *((_DWORD *)v9 + 329) = 1;
        v22 = SubmitControlRequest(
                0x21u,
                1u,
                0xA00u,
                v21,
                v24,
                (unsigned __int8 *)&v27,
                Size,
                (__int64)v26,
                (__int64)v9);
        v5 = v22;
        if ( v22 >= 0 )
        {
          a1->IoStatus.Information = 64;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              190,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              (unsigned int)v22);
          *((_QWORD *)v9 + 146) = 0;
        }
        goto LABEL_47;
      }
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_50;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_47;
      v17 = 191;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_50;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_47;
      v17 = 192;
    }
    WPP_SF_ii(v16->AttachedDevice, v17);
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_50;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v7 = 187;
LABEL_8:
      WPP_SF_(v6->AttachedDevice, v7, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
    }
  }
LABEL_47:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 194, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v5);
LABEL_50:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400589c0  mov     [rsp-28h+arg_8], rbx
0x1400589c5  mov     [rsp-28h+arg_10], rsi
0x1400589ca  push    rbp
0x1400589cb  push    rdi
0x1400589cc  push    r12
0x1400589ce  push    r13
0x1400589d0  push    r14
0x1400589d2  mov     rbp, rsp
0x1400589d5  sub     rsp, 70h
0x1400589d9  mov     rdi, r8
0x1400589dc  mov     [rbp+arg_18], 0
0x1400589e0  mov     rsi, rcx
0x1400589e3  mov     [rbp+arg_0], 0
0x1400589e7  mov     [rbp+var_10], 0
0x1400589ef  mov     [rbp+var_20], 0
0x1400589f7  mov     [rbp+var_18], 0
0x1400589ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140058a06  lea     r12, WPP_GLOBAL_Control
0x140058a0d  lea     r13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140058a14  cmp     rcx, r12
0x140058a17  jz      short loc_140058A33
0x140058a19  cmp     byte ptr [rcx+29h], 4
0x140058a1d  jb      short loc_140058A33
0x140058a1f  mov     rcx, [rcx+18h]
0x140058a23  mov     edx, 0BAh
0x140058a28  mov     r9, rsi
0x140058a2b  mov     r8, r13
0x140058a2e  call    WPP_SF_q
0x140058a33  lea     rax, [rbp+var_20]
0x140058a37  mov     rcx, rsi; struct _IRP *
0x140058a3a  mov     [rsp+70h+var_48], rax; struct _HW_DEVICE_EXTENSION **
0x140058a3f  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x140058a43  lea     rax, [rbp+var_10]
0x140058a47  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x140058a4b  mov     [rsp+70h+var_50], rax; struct _TOPOLOGY_NODE_INFO **
0x140058a50  lea     rdx, [rbp+var_18]; struct _KSFILTER **
0x140058a54  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140058a59  mov     ebx, eax
0x140058a5b  test    eax, eax
0x140058a5d  jns     short loc_140058A8F
0x140058a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140058a66  cmp     rcx, r12
0x140058a69  jz      loc_140058CFB
0x140058a6f  cmp     byte ptr [rcx+29h], 2
0x140058a73  jb      loc_140058CD5
0x140058a79  mov     edx, 0BBh
0x140058a7e  mov     rcx, [rcx+18h]
0x140058a82  mov     r8, r13
0x140058a85  call    WPP_SF_
0x140058a8a  jmp     loc_140058CD5
0x140058a8f  xor     r9d, r9d
0x140058a92  mov     rdx, rdi
0x140058a95  mov     rcx, rsi
0x140058a98  lea     r8d, [r9+40h]
0x140058a9c  call    ValidateExtendedPropertyDataBufferLength
0x140058aa1  mov     ebx, eax
0x140058aa3  test    eax, eax
0x140058aa5  jns     short loc_140058AC7
0x140058aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x140058aae  cmp     rcx, r12
0x140058ab1  jz      loc_140058CFB
0x140058ab7  cmp     byte ptr [rcx+29h], 2
0x140058abb  jb      loc_140058CD5
0x140058ac1  lea     edx, [r8+7Ch]
0x140058ac5  jmp     short loc_140058A7E
0x140058ac7  mov     rcx, rdi; this
0x140058aca  mov     ebx, 0C000000Dh
0x140058acf  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ; CExtendedVidProcSetting::isValid(void)
0x140058ad4  test    al, al
0x140058ad6  jz      loc_140058CA7
0x140058adc  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x140058ae0  jnz     loc_140058CA7
0x140058ae6  mov     r14, [rbp+var_20]
0x140058aea  mov     r11d, 1
0x140058af0  mov     rax, [r14+408h]
0x140058af7  mov     r8d, [rax+8]
0x140058afb  mov     ecx, r8d
0x140058afe  and     rcx, r11
0x140058b01  mov     rdx, rcx
0x140058b04  or      rdx, 2
0x140058b08  test    r8b, 2
0x140058b0c  cmovz   rdx, rcx
0x140058b10  mov     r9, rdx
0x140058b13  or      r9, 4
0x140058b17  test    r8b, 4
0x140058b1b  mov     r8, [rdi+10h]
0x140058b1f  cmovz   r9, rdx
0x140058b23  mov     rax, r9
0x140058b26  and     rax, r8
0x140058b29  cmp     r8, rax
0x140058b2c  jnz     loc_140058C7D
0x140058b32  mov     rax, r8
0x140058b35  sub     rax, r11
0x140058b38  jz      short loc_140058B69
0x140058b3a  sub     rax, r11
0x140058b3d  jz      short loc_140058B69
0x140058b3f  cmp     rax, 2
0x140058b43  jz      short loc_140058B69
0x140058b45  mov     rcx, cs:WPP_GLOBAL_Control
0x140058b4c  cmp     rcx, r12
0x140058b4f  jz      loc_140058CFB
0x140058b55  cmp     byte ptr [rcx+29h], 2
0x140058b59  jb      loc_140058CD5
0x140058b5f  mov     edx, 0BFh
0x140058b64  jmp     loc_140058C94
0x140058b69  mov     r10d, [rdi+30h]
0x140058b6d  mov     rdx, r8
0x140058b70  mov     [rbp+var_20], 0
0x140058b78  mov     rcx, r8
0x140058b7b  mov     r9d, dword ptr [rbp+var_20]
0x140058b7f  and     rcx, r11
0x140058b82  mov     eax, ecx
0x140058b84  cmovnz  r9d, r11d
0x140058b88  and     edx, 2
0x140058b8b  or      eax, 2
0x140058b8e  mov     dword ptr [rbp+var_20], r9d
0x140058b92  test    rdx, rdx
0x140058b95  jz      short loc_140058B9D
0x140058b97  mov     r9d, eax
0x140058b9a  mov     dword ptr [rbp+var_20], eax
0x140058b9d  cmovz   eax, ecx
0x140058ba0  test    r8b, 4
0x140058ba4  jz      short loc_140058BB1
0x140058ba6  mov     r9d, eax
0x140058ba9  or      r9d, 4
0x140058bad  mov     dword ptr [rbp+var_20], r9d
0x140058bb1  mov     dword ptr [rbp+var_20+4], r10d
0x140058bb5  mov     rax, [rbp+var_20]
0x140058bb9  mov     [rbp+var_20], rax
0x140058bbd  mov     rcx, cs:WPP_GLOBAL_Control
0x140058bc4  cmp     rcx, r12
0x140058bc7  jz      short loc_140058BEE
0x140058bc9  cmp     byte ptr [rcx+29h], 4
0x140058bcd  jb      short loc_140058BEE
0x140058bcf  mov     rcx, [rcx+18h]
0x140058bd3  mov     edx, 0BDh
0x140058bd8  shr     rax, 20h
0x140058bdc  mov     r8, r13
0x140058bdf  mov     dword ptr [rsp+70h+var_50], eax
0x140058be3  call    WPP_SF_dd
0x140058be8  mov     r11d, 1
0x140058bee  mov     rax, [rbp+var_18]
0x140058bf2  mov     r8d, 0A00h; int
0x140058bf8  mov     r9b, [rbp+arg_18]; int
0x140058bfc  mov     dl, r11b; int
0x140058bff  mov     [r14+490h], rax
0x140058c06  mov     cl, 21h ; '!'; int
0x140058c08  mov     rax, [rbp+var_10]
0x140058c0c  mov     [rsp+70h+var_30], r14; __int64
0x140058c11  mov     [rsp+70h+var_38], rax; __int64
0x140058c16  lea     rax, [rbp+var_20]
0x140058c1a  mov     dword ptr [rsp+70h+Size], 8; Size
0x140058c22  mov     [rsp+70h+var_48], rax; void *
0x140058c27  mov     al, [rbp+arg_0]
0x140058c2a  mov     byte ptr [rsp+70h+var_50], al; int
0x140058c2e  mov     [r14+524h], r11d
0x140058c35  call    SubmitControlRequest
0x140058c3a  mov     ebx, eax
0x140058c3c  test    eax, eax
0x140058c3e  jns     short loc_140058C73
0x140058c40  mov     rcx, cs:WPP_GLOBAL_Control
0x140058c47  cmp     rcx, r12
0x140058c4a  jz      short loc_140058C66
0x140058c4c  cmp     byte ptr [rcx+29h], 2
0x140058c50  jb      short loc_140058C66
0x140058c52  mov     rcx, [rcx+18h]
0x140058c56  mov     edx, 0BEh
0x140058c5b  mov     r9d, eax
0x140058c5e  mov     r8, r13
0x140058c61  call    WPP_SF_d
0x140058c66  mov     qword ptr [r14+490h], 0
0x140058c71  jmp     short loc_140058CD5
0x140058c73  mov     qword ptr [rsi+38h], 40h ; '@'
0x140058c7b  jmp     short loc_140058CD5
0x140058c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140058c84  cmp     rcx, r12
0x140058c87  jz      short loc_140058CFB
0x140058c89  cmp     byte ptr [rcx+29h], 2
0x140058c8d  jb      short loc_140058CD5
0x140058c8f  mov     edx, 0C0h
0x140058c94  mov     rcx, [rcx+18h]
0x140058c98  mov     [rsp+70h+var_50], r9
0x140058c9d  mov     r9, r8
0x140058ca0  call    WPP_SF_ii
0x140058ca5  jmp     short loc_140058CD5
0x140058ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140058cae  cmp     rcx, r12
0x140058cb1  jz      short loc_140058CFB
0x140058cb3  cmp     byte ptr [rcx+29h], 2
0x140058cb7  jb      short loc_140058CD5
0x140058cb9  mov     eax, [rdi+4]
0x140058cbc  mov     edx, 0C1h
0x140058cc1  mov     r9d, [rdi+8]
0x140058cc5  mov     r8, r13
0x140058cc8  mov     rcx, [rcx+18h]
0x140058ccc  mov     dword ptr [rsp+70h+var_50], eax
0x140058cd0  call    WPP_SF_dd
0x140058cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140058cdc  cmp     rcx, r12
0x140058cdf  jz      short loc_140058CFB
0x140058ce1  cmp     byte ptr [rcx+29h], 4
0x140058ce5  jb      short loc_140058CFB
0x140058ce7  mov     rcx, [rcx+18h]
0x140058ceb  mov     edx, 0C2h
0x140058cf0  mov     r9d, ebx
0x140058cf3  mov     r8, r13
0x140058cf6  call    WPP_SF_d
0x140058cfb  lea     r11, [rsp+70h+var_s0]
0x140058d00  mov     [rsi+30h], ebx
0x140058d03  mov     rsi, [r11+40h]
0x140058d07  mov     eax, ebx
0x140058d09  mov     rbx, [r11+38h]
0x140058d0d  mov     rsp, r11
0x140058d10  pop     r14
0x140058d12  pop     r13
0x140058d14  pop     r12
0x140058d16  pop     rdi
0x140058d17  pop     rbp
0x140058d18  retn
```
