# MSXU_DigitalWindowGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140055880`
- end: `0x140055b64`
- name: `?MSXU_DigitalWindowGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `740`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14001d0cc`
- `0x14003b924`
- `0x140040a30`
- `0x140055880`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_DigitalWindowGet(struct _IRP *a1, struct KSIDENTIFIER *a2, _DWORD *a3)
{
  NTSTATUS v6; // ebx
  unsigned int v7; // r8d
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  _DWORD *v10; // rax
  __int64 v11; // r14
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  int v18; // [rsp+20h] [rbp-60h]
  size_t Size; // [rsp+30h] [rbp-50h]
  unsigned __int8 v20; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int8 v21[7]; // [rsp+51h] [rbp-2Fh] BYREF
  struct _HW_DEVICE_EXTENSION *v22; // [rsp+58h] [rbp-28h] BYREF
  struct _TOPOLOGY_NODE_INFO *v23; // [rsp+60h] [rbp-20h] BYREF
  struct _KSFILTER *v24[2]; // [rsp+68h] [rbp-18h] BYREF

  v21[0] = 0;
  v20 = 0;
  v23 = 0;
  v22 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 195, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  if ( !a1 || !a2 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 196, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1, a2);
    goto LABEL_31;
  }
  v6 = MSXUGetInfo(a1, v24, v21, &v20, &v23, &v22);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 197, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
    goto LABEL_31;
  }
  v6 = ValidateExtendedPropertyDataBufferLength(a1, a3, 48);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      goto LABEL_31;
    v9 = 198;
    goto LABEL_14;
  }
  v10 = a3 + 1;
  if ( *a3 != 1 || *v10 != -1 || a3[2] < v7 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        201,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        (unsigned int)a3[2],
        *v10);
    goto LABEL_31;
  }
  v11 = *((_QWORD *)v22 + 130);
  LODWORD(Size) = 16;
  LOBYTE(v18) = v20;
  *(_OWORD *)v24 = 0;
  v6 = SubmitControlRequest(0xA1u, 0x81u, 0xB00u, v21[0], v18, (unsigned __int8 *)v24, Size, (__int64)v23, (__int64)v22);
  if ( v6 >= 0 )
  {
    v12 = HIDWORD(v24[0]);
    v13 = *(_DWORD *)(v11 + 16) & 1;
    v14 = LODWORD(v24[1]);
    v15 = HIDWORD(v24[1]);
    *((_QWORD *)a3 + 3) = v13;
    v16 = (__int64)v24[0] & (unsigned __int8)v13 & 1;
    a3[8] = v12;
    *((_QWORD *)a3 + 2) = v16;
    a3[9] = v14;
    a3[10] = v15;
    a1->IoStatus.Information = 48;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_iiDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        v15,
        *((_QWORD *)a3 + 2),
        *((_QWORD *)a3 + 3),
        v12,
        v14,
        v15);
    goto LABEL_31;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_34;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v9 = 200;
LABEL_14:
    WPP_SF_(v8->AttachedDevice, v9, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_31:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 202, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v6);
LABEL_34:
  a1->IoStatus.Status = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140055880  push    rbp
0x140055882  push    rbx
0x140055883  push    rsi
0x140055884  push    rdi
0x140055885  push    r12
0x140055887  push    r13
0x140055889  push    r14
0x14005588b  mov     rbp, rsp
0x14005588e  sub     rsp, 80h
0x140055895  mov     rax, cs:__security_cookie
0x14005589c  xor     rax, rsp
0x14005589f  mov     [rbp+var_8], rax
0x1400558a3  mov     rdi, r8
0x1400558a6  mov     [rbp+var_2F], 0
0x1400558aa  mov     r14, rdx
0x1400558ad  mov     [rbp+var_30], 0
0x1400558b1  mov     rsi, rcx
0x1400558b4  mov     [rbp+var_20], 0
0x1400558bc  mov     [rbp+var_28], 0
0x1400558c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400558cb  lea     r12, WPP_GLOBAL_Control
0x1400558d2  lea     r13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400558d9  cmp     rcx, r12
0x1400558dc  jz      short loc_1400558F8
0x1400558de  cmp     byte ptr [rcx+29h], 2
0x1400558e2  jb      short loc_1400558F8
0x1400558e4  mov     rcx, [rcx+18h]
0x1400558e8  mov     edx, 0C3h
0x1400558ed  mov     r9, rsi
0x1400558f0  mov     r8, r13
0x1400558f3  call    WPP_SF_q
0x1400558f8  test    rsi, rsi
0x1400558fb  jz      loc_140055AEA
0x140055901  test    r14, r14
0x140055904  jz      loc_140055AEA
0x14005590a  lea     rax, [rbp+var_28]
0x14005590e  mov     rcx, rsi; struct _IRP *
0x140055911  mov     [rsp+80h+var_58], rax; struct _HW_DEVICE_EXTENSION **
0x140055916  lea     r9, [rbp+var_30]; unsigned __int8 *
0x14005591a  lea     rax, [rbp+var_20]
0x14005591e  lea     r8, [rbp+var_2F]; unsigned __int8 *
0x140055922  mov     [rsp+80h+var_60], rax; struct _TOPOLOGY_NODE_INFO **
0x140055927  lea     rdx, [rbp+var_18]; struct _KSFILTER **
0x14005592b  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140055930  mov     ebx, eax
0x140055932  test    eax, eax
0x140055934  jns     short loc_140055969
0x140055936  mov     rcx, cs:WPP_GLOBAL_Control
0x14005593d  cmp     rcx, r12
0x140055940  jz      loc_140055B40
0x140055946  cmp     byte ptr [rcx+29h], 2
0x14005594a  jb      loc_140055B1A
0x140055950  mov     rcx, [rcx+18h]
0x140055954  mov     edx, 0C5h
0x140055959  mov     r9, rsi
0x14005595c  mov     r8, r13
0x14005595f  call    WPP_SF_q
0x140055964  jmp     loc_140055B1A
0x140055969  xor     r9d, r9d
0x14005596c  mov     rdx, rdi
0x14005596f  mov     rcx, rsi
0x140055972  lea     r8d, [r9+30h]
0x140055976  call    ValidateExtendedPropertyDataBufferLength
0x14005597b  mov     ebx, eax
0x14005597d  test    eax, eax
0x14005597f  jns     short loc_1400559B1
0x140055981  mov     rcx, cs:WPP_GLOBAL_Control
0x140055988  cmp     rcx, r12
0x14005598b  jz      loc_140055B40
0x140055991  cmp     byte ptr [rcx+29h], 4
0x140055995  jb      loc_140055B1A
0x14005599b  mov     edx, 0C6h
0x1400559a0  mov     rcx, [rcx+18h]
0x1400559a4  mov     r8, r13
0x1400559a7  call    WPP_SF_
0x1400559ac  jmp     loc_140055B1A
0x1400559b1  cmp     dword ptr [rdi], 1
0x1400559b4  lea     rax, [rdi+4]
0x1400559b8  jnz     loc_140055AB6
0x1400559be  cmp     dword ptr [rax], 0FFFFFFFFh
0x1400559c1  jnz     loc_140055AB6
0x1400559c7  cmp     [rdi+8], r8d
0x1400559cb  jb      loc_140055AB6
0x1400559d1  mov     rax, [rbp+var_28]
0x1400559d5  xorps   xmm0, xmm0
0x1400559d8  mov     r9b, [rbp+var_2F]; int
0x1400559dc  mov     r8d, 0B00h; int
0x1400559e2  mov     [rsp+80h+var_40], rax; __int64
0x1400559e7  mov     dl, 81h; int
0x1400559e9  mov     cl, 0A1h; int
0x1400559eb  mov     r14, [rax+410h]
0x1400559f2  mov     rax, [rbp+var_20]
0x1400559f6  mov     [rsp+80h+var_48], rax; __int64
0x1400559fb  lea     rax, [rbp+var_18]
0x1400559ff  mov     dword ptr [rsp+80h+Size], 10h; Size
0x140055a07  mov     [rsp+80h+var_58], rax; void *
0x140055a0c  mov     al, [rbp+var_30]
0x140055a0f  mov     byte ptr [rsp+80h+var_60], al; int
0x140055a13  movups  xmmword ptr [rbp+var_18], xmm0
0x140055a17  call    SubmitControlRequest
0x140055a1c  mov     ebx, eax
0x140055a1e  test    eax, eax
0x140055a20  js      short loc_140055A96
0x140055a22  mov     ecx, [r14+10h]
0x140055a26  mov     eax, dword ptr [rbp+var_18+4]
0x140055a29  and     ecx, 1
0x140055a2c  mov     edx, dword ptr [rbp+var_18+8]
0x140055a2f  mov     r8d, dword ptr [rbp+var_18+0Ch]
0x140055a33  mov     [rdi+18h], rcx
0x140055a37  and     rcx, [rbp+var_18]
0x140055a3b  and     ecx, 1
0x140055a3e  mov     [rdi+20h], eax
0x140055a41  mov     [rdi+10h], rcx
0x140055a45  mov     [rdi+24h], edx
0x140055a48  mov     [rdi+28h], r8d
0x140055a4c  mov     qword ptr [rsi+38h], 30h ; '0'
0x140055a54  mov     rcx, cs:WPP_GLOBAL_Control
0x140055a5b  cmp     rcx, r12
0x140055a5e  jz      loc_140055B40
0x140055a64  cmp     byte ptr [rcx+29h], 4
0x140055a68  jb      loc_140055B1A
0x140055a6e  mov     r9, [rdi+10h]
0x140055a72  mov     rcx, [rcx+18h]
0x140055a76  mov     dword ptr [rsp+80h+var_48], r8d
0x140055a7b  mov     dword ptr [rsp+80h+Size], edx
0x140055a7f  mov     dword ptr [rsp+80h+var_58], eax
0x140055a83  mov     rax, [rdi+18h]
0x140055a87  mov     [rsp+80h+var_60], rax
0x140055a8c  call    WPP_SF_iiDDD
0x140055a91  jmp     loc_140055B1A
0x140055a96  mov     rcx, cs:WPP_GLOBAL_Control
0x140055a9d  cmp     rcx, r12
0x140055aa0  jz      loc_140055B40
0x140055aa6  cmp     byte ptr [rcx+29h], 2
0x140055aaa  jb      short loc_140055B1A
0x140055aac  mov     edx, 0C8h
0x140055ab1  jmp     loc_1400559A0
0x140055ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140055abd  mov     ebx, 0C000000Dh
0x140055ac2  cmp     rcx, r12
0x140055ac5  jz      short loc_140055B40
0x140055ac7  cmp     byte ptr [rcx+29h], 2
0x140055acb  jb      short loc_140055B1A
0x140055acd  mov     eax, [rax]
0x140055acf  mov     edx, 0C9h
0x140055ad4  mov     r9d, [rdi+8]
0x140055ad8  mov     r8, r13
0x140055adb  mov     rcx, [rcx+18h]
0x140055adf  mov     dword ptr [rsp+80h+var_60], eax
0x140055ae3  call    WPP_SF_dd
0x140055ae8  jmp     short loc_140055B1A
0x140055aea  mov     rcx, cs:WPP_GLOBAL_Control
0x140055af1  mov     ebx, 0C000000Dh
0x140055af6  cmp     rcx, r12
0x140055af9  jz      short loc_140055B40
0x140055afb  cmp     byte ptr [rcx+29h], 2
0x140055aff  jb      short loc_140055B1A
0x140055b01  mov     rcx, [rcx+18h]
0x140055b05  mov     edx, 0C4h
0x140055b0a  mov     r9, rsi
0x140055b0d  mov     [rsp+80h+var_60], r14
0x140055b12  mov     r8, r13
0x140055b15  call    WPP_SF_qq
0x140055b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140055b21  cmp     rcx, r12
0x140055b24  jz      short loc_140055B40
0x140055b26  cmp     byte ptr [rcx+29h], 4
0x140055b2a  jb      short loc_140055B40
0x140055b2c  mov     rcx, [rcx+18h]
0x140055b30  mov     edx, 0CAh
0x140055b35  mov     r9d, ebx
0x140055b38  mov     r8, r13
0x140055b3b  call    WPP_SF_d
0x140055b40  mov     [rsi+30h], ebx
0x140055b43  mov     eax, ebx
0x140055b45  mov     rcx, [rbp+var_8]
0x140055b49  xor     rcx, rsp; StackCookie
0x140055b4c  call    __security_check_cookie
0x140055b51  add     rsp, 80h
0x140055b58  pop     r14
0x140055b5a  pop     r13
0x140055b5c  pop     r12
0x140055b5e  pop     rdi
0x140055b5f  pop     rsi
0x140055b60  pop     rbx
0x140055b61  pop     rbp
0x140055b62  retn
```
