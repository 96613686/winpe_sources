# MSXU_FieldOfView2Get(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140056ef0`
- end: `0x14005714c`
- name: `?MSXU_FieldOfView2Get@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `604`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14001d0cc`
- `0x140056ef0`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_FieldOfView2Get(struct _IRP *a1, struct KSIDENTIFIER *a2, _DWORD *a3)
{
  NTSTATUS v6; // ebx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v11; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  unsigned __int8 v13[8]; // [rsp+50h] [rbp-20h] BYREF
  struct _HW_DEVICE_EXTENSION *v14; // [rsp+58h] [rbp-18h] BYREF
  struct _TOPOLOGY_NODE_INFO *v15; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 v16; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int8 v17; // [rsp+B8h] [rbp+48h] BYREF

  v17 = 0;
  v16 = 0;
  v15 = 0;
  v14 = 0;
  *(_DWORD *)v13 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 271, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  if ( !a1 || !a2 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_33;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 272, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1, a2);
    goto LABEL_30;
  }
  v6 = MSXUGetInfo(a1, 0, &v17, &v16, &v15, &v14);
  if ( v6 >= 0 )
  {
    v6 = ValidateExtendedPropertyDataBufferLength(a1, a3, 40);
    if ( v6 >= 0 )
    {
      if ( *a3 != 1 || a3[2] < 0x28u || a3[1] != -1 )
      {
        v6 = -1073741811;
        goto LABEL_30;
      }
      LODWORD(Size) = 4;
      LOBYTE(v11) = v16;
      v6 = SubmitControlRequest(0xA1u, 0x81u, 0x1000u, v17, v11, v13, Size, (__int64)v15, (__int64)v14);
      if ( v6 >= 0 )
      {
        v9 = *(unsigned int *)v13;
        a3[8] = *(_DWORD *)v13;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 276, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v9);
        a1->IoStatus.Information = 40;
        goto LABEL_30;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_33;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_30;
      v8 = 275;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_33;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_30;
      v8 = 274;
    }
    WPP_SF_(v7->AttachedDevice, v8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_33;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 273, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  }
LABEL_30:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 277, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v6);
LABEL_33:
  a1->IoStatus.Status = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140056ef0  mov     [rsp-28h+arg_8], rbx
0x140056ef5  mov     [rsp-28h+arg_10], rsi
0x140056efa  push    rbp
0x140056efb  push    rdi
0x140056efc  push    r12
0x140056efe  push    r13
0x140056f00  push    r14
0x140056f02  mov     rbp, rsp
0x140056f05  sub     rsp, 70h
0x140056f09  mov     rsi, r8
0x140056f0c  mov     [rbp+arg_18], 0
0x140056f10  mov     r14, rdx
0x140056f13  mov     [rbp+arg_0], 0
0x140056f17  mov     rdi, rcx
0x140056f1a  mov     [rbp+var_10], 0
0x140056f22  mov     [rbp+var_18], 0
0x140056f2a  mov     dword ptr [rbp+var_20], 0
0x140056f31  mov     rcx, cs:WPP_GLOBAL_Control
0x140056f38  lea     r12, WPP_GLOBAL_Control
0x140056f3f  lea     r13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140056f46  cmp     rcx, r12
0x140056f49  jz      short loc_140056F65
0x140056f4b  cmp     byte ptr [rcx+29h], 2
0x140056f4f  jb      short loc_140056F65
0x140056f51  mov     rcx, [rcx+18h]
0x140056f55  mov     edx, 10Fh
0x140056f5a  mov     r9, rdi
0x140056f5d  mov     r8, r13
0x140056f60  call    WPP_SF_q
0x140056f65  test    rdi, rdi
0x140056f68  jz      loc_1400570D7
0x140056f6e  test    r14, r14
0x140056f71  jz      loc_1400570D7
0x140056f77  lea     rax, [rbp+var_18]
0x140056f7b  xor     edx, edx; struct _KSFILTER **
0x140056f7d  mov     [rsp+70h+var_48], rax; struct _HW_DEVICE_EXTENSION **
0x140056f82  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x140056f86  lea     rax, [rbp+var_10]
0x140056f8a  mov     rcx, rdi; struct _IRP *
0x140056f8d  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x140056f91  mov     [rsp+70h+var_50], rax; struct _TOPOLOGY_NODE_INFO **
0x140056f96  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140056f9b  mov     ebx, eax
0x140056f9d  test    eax, eax
0x140056f9f  jns     short loc_140056FD4
0x140056fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140056fa8  cmp     rcx, r12
0x140056fab  jz      loc_14005712D
0x140056fb1  cmp     byte ptr [rcx+29h], 2
0x140056fb5  jb      loc_140057107
0x140056fbb  mov     rcx, [rcx+18h]
0x140056fbf  mov     edx, 111h
0x140056fc4  mov     r9, rdi
0x140056fc7  mov     r8, r13
0x140056fca  call    WPP_SF_q
0x140056fcf  jmp     loc_140057107
0x140056fd4  xor     r9d, r9d
0x140056fd7  mov     rdx, rsi
0x140056fda  mov     rcx, rdi
0x140056fdd  lea     r14d, [r9+28h]
0x140056fe1  mov     r8d, r14d
0x140056fe4  call    ValidateExtendedPropertyDataBufferLength
0x140056fe9  mov     ebx, eax
0x140056feb  test    eax, eax
0x140056fed  jns     short loc_14005701F
0x140056fef  mov     rcx, cs:WPP_GLOBAL_Control
0x140056ff6  cmp     rcx, r12
0x140056ff9  jz      loc_14005712D
0x140056fff  cmp     byte ptr [rcx+29h], 2
0x140057003  jb      loc_140057107
0x140057009  mov     edx, 112h
0x14005700e  mov     rcx, [rcx+18h]
0x140057012  mov     r8, r13
0x140057015  call    WPP_SF_
0x14005701a  jmp     loc_140057107
0x14005701f  cmp     dword ptr [rsi], 1
0x140057022  jnz     loc_1400570D0
0x140057028  cmp     [rsi+8], r14d
0x14005702c  jb      loc_1400570D0
0x140057032  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x140057036  jnz     loc_1400570D0
0x14005703c  mov     rax, [rbp+var_18]
0x140057040  mov     r8d, 1000h; int
0x140057046  mov     r9b, [rbp+arg_18]; int
0x14005704a  mov     dl, 81h; int
0x14005704c  mov     [rsp+70h+var_30], rax; __int64
0x140057051  mov     cl, 0A1h; int
0x140057053  mov     rax, [rbp+var_10]
0x140057057  mov     [rsp+70h+var_38], rax; __int64
0x14005705c  lea     rax, [rbp+var_20]
0x140057060  mov     dword ptr [rsp+70h+Size], 4; Size
0x140057068  mov     [rsp+70h+var_48], rax; void *
0x14005706d  mov     al, [rbp+arg_0]
0x140057070  mov     byte ptr [rsp+70h+var_50], al; int
0x140057074  call    SubmitControlRequest
0x140057079  mov     ebx, eax
0x14005707b  test    eax, eax
0x14005707d  jns     short loc_14005709F
0x14005707f  mov     rcx, cs:WPP_GLOBAL_Control
0x140057086  cmp     rcx, r12
0x140057089  jz      loc_14005712D
0x14005708f  cmp     byte ptr [rcx+29h], 2
0x140057093  jb      short loc_140057107
0x140057095  mov     edx, 113h
0x14005709a  jmp     loc_14005700E
0x14005709f  mov     r9d, dword ptr [rbp+var_20]
0x1400570a3  mov     [rsi+20h], r9d
0x1400570a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400570ae  cmp     rcx, r12
0x1400570b1  jz      short loc_1400570CA
0x1400570b3  cmp     byte ptr [rcx+29h], 4
0x1400570b7  jb      short loc_1400570CA
0x1400570b9  mov     rcx, [rcx+18h]
0x1400570bd  mov     edx, 114h
0x1400570c2  mov     r8, r13
0x1400570c5  call    WPP_SF_d
0x1400570ca  mov     [rdi+38h], r14
0x1400570ce  jmp     short loc_140057107
0x1400570d0  mov     ebx, 0C000000Dh
0x1400570d5  jmp     short loc_140057107
0x1400570d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400570de  mov     ebx, 0C000000Dh
0x1400570e3  cmp     rcx, r12
0x1400570e6  jz      short loc_14005712D
0x1400570e8  cmp     byte ptr [rcx+29h], 2
0x1400570ec  jb      short loc_140057107
0x1400570ee  mov     rcx, [rcx+18h]
0x1400570f2  mov     edx, 110h
0x1400570f7  mov     r9, rdi
0x1400570fa  mov     [rsp+70h+var_50], r14
0x1400570ff  mov     r8, r13
0x140057102  call    WPP_SF_qq
0x140057107  mov     rcx, cs:WPP_GLOBAL_Control
0x14005710e  cmp     rcx, r12
0x140057111  jz      short loc_14005712D
0x140057113  cmp     byte ptr [rcx+29h], 4
0x140057117  jb      short loc_14005712D
0x140057119  mov     rcx, [rcx+18h]
0x14005711d  mov     edx, 115h
0x140057122  mov     r9d, ebx
0x140057125  mov     r8, r13
0x140057128  call    WPP_SF_d
0x14005712d  lea     r11, [rsp+70h+var_s0]
0x140057132  mov     [rdi+30h], ebx
0x140057135  mov     rsi, [r11+40h]
0x140057139  mov     eax, ebx
0x14005713b  mov     rbx, [r11+38h]
0x14005713f  mov     rsp, r11
0x140057142  pop     r14
0x140057144  pop     r13
0x140057146  pop     r12
0x140057148  pop     rdi
0x140057149  pop     rbp
0x14005714a  retn
```
