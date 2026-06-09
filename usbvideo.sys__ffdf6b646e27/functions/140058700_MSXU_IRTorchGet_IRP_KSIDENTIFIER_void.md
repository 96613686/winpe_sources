# MSXU_IRTorchGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140058700`
- end: `0x1400589b2`
- name: `?MSXU_IRTorchGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `690`
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
- `0x14003b9b0`
- `0x140058700`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_IRTorchGet(struct _IRP *a1, struct KSIDENTIFIER *a2, CExtendedVidProcSetting *a3)
{
  NTSTATUS v5; // edi
  int v6; // r8d
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  struct _HW_DEVICE_EXTENSION *v9; // r9
  _DWORD *v10; // r14
  int v11; // r8d
  char v12; // al
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rcx
  int v18; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  struct _HW_DEVICE_EXTENSION *v20; // [rsp+40h] [rbp-30h]
  struct _HW_DEVICE_EXTENSION *v21; // [rsp+50h] [rbp-20h] BYREF
  struct _TOPOLOGY_NODE_INFO *v22; // [rsp+58h] [rbp-18h] BYREF
  struct _KSFILTER *v23; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 v24; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int8 v25; // [rsp+B8h] [rbp+48h] BYREF

  v25 = 0;
  v24 = 0;
  v22 = 0;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 180, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, &v23, &v25, &v24, &v22, &v21);
  if ( v5 < 0 )
    goto LABEL_30;
  v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 64);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_33;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      goto LABEL_30;
    v8 = (unsigned int)(v6 + 117);
LABEL_9:
    WPP_SF_(v7->AttachedDevice, v8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
LABEL_30:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        185,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        (unsigned int)v5);
    goto LABEL_33;
  }
  if ( !CExtendedVidProcSetting::isValid(a3) || *((_DWORD *)a3 + 1) != -1 )
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_33;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        184,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        *((unsigned int *)a3 + 2),
        *((_DWORD *)a3 + 1));
    goto LABEL_30;
  }
  v20 = v21;
  v10 = (_DWORD *)*((_QWORD *)v21 + 129);
  LODWORD(Size) = 8;
  v21 = v9;
  LOBYTE(v18) = v24;
  v5 = SubmitControlRequest(0xA1u, 0x81u, 0xA00u, v25, v18, (unsigned __int8 *)&v21, Size, (__int64)v22, (__int64)v20);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_33;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_30;
    v8 = 183;
    goto LABEL_9;
  }
  v11 = v10[2];
  v12 = (char)v21;
  v13 = v11 & 1 | 2LL;
  if ( (v11 & 2) == 0 )
    v13 = v10[2] & 1;
  v14 = v13 | 4;
  if ( (v11 & 4) == 0 )
    v14 = v13;
  *((_QWORD *)a3 + 3) = v14;
  v15 = v12 & 1 | 2LL;
  if ( (v12 & 2) == 0 )
    v15 = v12 & 1;
  v16 = v15 | 4;
  if ( ((unsigned __int8)v21 & 4) == 0 )
    v16 = v15;
  *((_QWORD *)a3 + 2) = v14 & v16;
  *((_DWORD *)a3 + 9) = v10[1];
  *((_DWORD *)a3 + 10) = v10[3];
  *((_DWORD *)a3 + 11) = v10[7];
  *((_DWORD *)a3 + 12) = HIDWORD(v21);
  *((_DWORD *)a3 + 8) = 0;
  a1->IoStatus.Information = 64;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_iidddd(
        WPP_GLOBAL_Control->AttachedDevice,
        v12 & 1,
        v15,
        *((_QWORD *)a3 + 2),
        *((_QWORD *)a3 + 3),
        *((_DWORD *)a3 + 9),
        *((_DWORD *)a3 + 10),
        *((_DWORD *)a3 + 11),
        *((_DWORD *)a3 + 12));
    goto LABEL_30;
  }
LABEL_33:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140058700  mov     [rsp-28h+arg_8], rbx
0x140058705  mov     [rsp-28h+arg_10], rsi
0x14005870a  push    rbp
0x14005870b  push    rdi
0x14005870c  push    r12
0x14005870e  push    r13
0x140058710  push    r14
0x140058712  mov     rbp, rsp
0x140058715  sub     rsp, 70h
0x140058719  mov     rbx, r8
0x14005871c  mov     [rbp+arg_18], 0
0x140058720  mov     rsi, rcx
0x140058723  mov     [rbp+arg_0], 0
0x140058727  mov     [rbp+var_18], 0
0x14005872f  mov     [rbp+var_20], 0
0x140058737  mov     rcx, cs:WPP_GLOBAL_Control
0x14005873e  lea     r12, WPP_GLOBAL_Control
0x140058745  lea     r13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005874c  cmp     rcx, r12
0x14005874f  jz      short loc_14005876B
0x140058751  cmp     byte ptr [rcx+29h], 2
0x140058755  jb      short loc_14005876B
0x140058757  mov     rcx, [rcx+18h]
0x14005875b  mov     edx, 0B4h
0x140058760  mov     r9, rsi
0x140058763  mov     r8, r13
0x140058766  call    WPP_SF_q
0x14005876b  lea     rax, [rbp+var_20]
0x14005876f  mov     rcx, rsi; struct _IRP *
0x140058772  mov     [rsp+70h+var_48], rax; struct _HW_DEVICE_EXTENSION **
0x140058777  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x14005877b  lea     rax, [rbp+var_18]
0x14005877f  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x140058783  mov     [rsp+70h+var_50], rax; struct _TOPOLOGY_NODE_INFO **
0x140058788  lea     rdx, [rbp+var_10]; struct _KSFILTER **
0x14005878c  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140058791  mov     edi, eax
0x140058793  test    eax, eax
0x140058795  js      loc_14005896D
0x14005879b  xor     r9d, r9d
0x14005879e  mov     rdx, rbx
0x1400587a1  mov     rcx, rsi
0x1400587a4  lea     r8d, [r9+40h]
0x1400587a8  call    ValidateExtendedPropertyDataBufferLength
0x1400587ad  mov     edi, eax
0x1400587af  test    eax, eax
0x1400587b1  jns     short loc_1400587E2
0x1400587b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400587ba  cmp     rcx, r12
0x1400587bd  jz      loc_140058993
0x1400587c3  cmp     byte ptr [rcx+29h], 4
0x1400587c7  jb      loc_14005896D
0x1400587cd  lea     edx, [r8+75h]
0x1400587d1  mov     rcx, [rcx+18h]
0x1400587d5  mov     r8, r13
0x1400587d8  call    WPP_SF_
0x1400587dd  jmp     loc_14005896D
0x1400587e2  mov     rcx, rbx; this
0x1400587e5  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ; CExtendedVidProcSetting::isValid(void)
0x1400587ea  test    al, al
0x1400587ec  jz      loc_14005893A
0x1400587f2  cmp     dword ptr [rbx+4], 0FFFFFFFFh
0x1400587f6  jnz     loc_14005893A
0x1400587fc  mov     rax, [rbp+var_20]
0x140058800  mov     r8d, 0A00h; int
0x140058806  mov     [rsp+70h+var_30], rax; __int64
0x14005880b  mov     dl, 81h; int
0x14005880d  mov     cl, 0A1h; int
0x14005880f  mov     r14, [rax+408h]
0x140058816  mov     rax, [rbp+var_18]
0x14005881a  mov     [rsp+70h+var_38], rax; __int64
0x14005881f  lea     rax, [rbp+var_20]
0x140058823  mov     dword ptr [rsp+70h+Size], 8; Size
0x14005882b  mov     [rsp+70h+var_48], rax; void *
0x140058830  mov     al, [rbp+arg_0]
0x140058833  mov     [rbp+var_20], r9
0x140058837  mov     r9b, [rbp+arg_18]; int
0x14005883b  mov     byte ptr [rsp+70h+var_50], al; int
0x14005883f  call    SubmitControlRequest
0x140058844  mov     edi, eax
0x140058846  test    eax, eax
0x140058848  js      loc_14005891E
0x14005884e  mov     r8d, [r14+8]
0x140058852  mov     ecx, r8d
0x140058855  mov     rax, [rbp+var_20]
0x140058859  and     ecx, 1
0x14005885c  mov     edx, ecx
0x14005885e  or      rdx, 2
0x140058862  test    r8b, 2
0x140058866  cmovz   rdx, rcx
0x14005886a  mov     r9, rdx
0x14005886d  or      r9, 4
0x140058871  test    r8b, 4
0x140058875  cmovz   r9, rdx
0x140058879  mov     rdx, rax
0x14005887c  mov     [rbx+18h], r9
0x140058880  and     edx, 1
0x140058883  mov     r8d, edx
0x140058886  or      r8, 2
0x14005888a  test    al, 2
0x14005888c  cmovz   r8, rdx
0x140058890  mov     rcx, r8
0x140058893  or      rcx, 4
0x140058897  test    byte ptr [rbp+var_20], 4
0x14005889b  cmovz   rcx, r8
0x14005889f  and     rcx, r9
0x1400588a2  mov     [rbx+10h], rcx
0x1400588a6  mov     eax, [r14+4]
0x1400588aa  mov     [rbx+24h], eax
0x1400588ad  mov     eax, [r14+0Ch]
0x1400588b1  mov     [rbx+28h], eax
0x1400588b4  mov     eax, [r14+1Ch]
0x1400588b8  mov     [rbx+2Ch], eax
0x1400588bb  mov     eax, dword ptr [rbp+var_20+4]
0x1400588be  mov     [rbx+30h], eax
0x1400588c1  mov     dword ptr [rbx+20h], 0
0x1400588c8  mov     qword ptr [rsi+38h], 40h ; '@'
0x1400588d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400588d7  cmp     rcx, r12
0x1400588da  jz      loc_140058993
0x1400588e0  cmp     byte ptr [rcx+29h], 4
0x1400588e4  jb      loc_14005896D
0x1400588ea  mov     eax, [rbx+30h]
0x1400588ed  mov     r9, [rbx+10h]
0x1400588f1  mov     rcx, [rcx+18h]
0x1400588f5  mov     dword ptr [rsp+70h+var_30], eax
0x1400588f9  mov     eax, [rbx+2Ch]
0x1400588fc  mov     dword ptr [rsp+70h+var_38], eax
0x140058900  mov     eax, [rbx+28h]
0x140058903  mov     dword ptr [rsp+70h+Size], eax
0x140058907  mov     eax, [rbx+24h]
0x14005890a  mov     dword ptr [rsp+70h+var_48], eax
0x14005890e  mov     rax, [rbx+18h]
0x140058912  mov     [rsp+70h+var_50], rax
0x140058917  call    WPP_SF_iidddd
0x14005891c  jmp     short loc_14005896D
0x14005891e  mov     rcx, cs:WPP_GLOBAL_Control
0x140058925  cmp     rcx, r12
0x140058928  jz      short loc_140058993
0x14005892a  cmp     byte ptr [rcx+29h], 2
0x14005892e  jb      short loc_14005896D
0x140058930  mov     edx, 0B7h
0x140058935  jmp     loc_1400587D1
0x14005893a  mov     rcx, cs:WPP_GLOBAL_Control
0x140058941  mov     edi, 0C000000Dh
0x140058946  cmp     rcx, r12
0x140058949  jz      short loc_140058993
0x14005894b  cmp     byte ptr [rcx+29h], 2
0x14005894f  jb      short loc_14005896D
0x140058951  mov     eax, [rbx+4]
0x140058954  mov     edx, 0B8h
0x140058959  mov     r9d, [rbx+8]
0x14005895d  mov     r8, r13
0x140058960  mov     rcx, [rcx+18h]
0x140058964  mov     dword ptr [rsp+70h+var_50], eax
0x140058968  call    WPP_SF_dd
0x14005896d  mov     rcx, cs:WPP_GLOBAL_Control
0x140058974  cmp     rcx, r12
0x140058977  jz      short loc_140058993
0x140058979  cmp     byte ptr [rcx+29h], 4
0x14005897d  jb      short loc_140058993
0x14005897f  mov     rcx, [rcx+18h]
0x140058983  mov     edx, 0B9h
0x140058988  mov     r9d, edi
0x14005898b  mov     r8, r13
0x14005898e  call    WPP_SF_d
0x140058993  lea     r11, [rsp+70h+var_s0]
0x140058998  mov     [rsi+30h], edi
0x14005899b  mov     rbx, [r11+38h]
0x14005899f  mov     eax, edi
0x1400589a1  mov     rsi, [r11+40h]
0x1400589a5  mov     rsp, r11
0x1400589a8  pop     r14
0x1400589aa  pop     r13
0x1400589ac  pop     r12
0x1400589ae  pop     rdi
0x1400589af  pop     rbp
0x1400589b0  retn
```
