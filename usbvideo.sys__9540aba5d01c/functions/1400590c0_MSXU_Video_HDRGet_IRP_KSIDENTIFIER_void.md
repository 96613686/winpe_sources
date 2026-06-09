# MSXU_Video_HDRGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x1400590c0`
- end: `0x14005936c`
- name: `?MSXU_Video_HDRGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `684`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b85c`
- `0x1400590c0`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_Video_HDRGet(struct _IRP *a1, struct KSIDENTIFIER *a2, _DWORD *a3)
{
  NTSTATUS v5; // ebx
  unsigned int v6; // r8d
  int v7; // r9d
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r14
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v16; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  struct _HW_DEVICE_EXTENSION *v18; // [rsp+40h] [rbp-30h]
  struct _HW_DEVICE_EXTENSION *v19; // [rsp+50h] [rbp-20h] BYREF
  struct _TOPOLOGY_NODE_INFO *v20; // [rsp+58h] [rbp-18h] BYREF
  struct _KSFILTER *v21; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int8 v22; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int8 v23; // [rsp+B8h] [rbp+48h] BYREF

  v23 = 0;
  v22 = 0;
  v20 = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 221, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, &v21, &v23, &v22, &v20, &v19);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 222, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
    goto LABEL_33;
  }
  v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 40);
  if ( v5 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      goto LABEL_33;
    v9 = 223;
LABEL_12:
    WPP_SF_(v8->AttachedDevice, v9, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
LABEL_33:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        228,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        (unsigned int)v5);
    goto LABEL_36;
  }
  v5 = -1073741811;
  if ( *a3 != 1 || a3[2] < v6 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        227,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        (unsigned int)a3[2],
        a3[1]);
    goto LABEL_33;
  }
  v10 = *((_QWORD *)v19 + 132);
  if ( !v10 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_33;
    v9 = 224;
    goto LABEL_12;
  }
  v18 = v19;
  LODWORD(Size) = 4;
  LODWORD(v19) = v7;
  LOBYTE(v16) = v22;
  v11 = SubmitControlRequest(0xA1u, 0x81u, 0xD00u, v23, v16, (unsigned __int8 *)&v19, Size, (__int64)v20, (__int64)v18);
  v5 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_36;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        226,
        WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
        (unsigned int)v11);
    goto LABEL_33;
  }
  v12 = *(_DWORD *)(v10 + 4) & 1 | 2LL;
  if ( (*(_BYTE *)(v10 + 4) & 2) == 0 )
    v12 = *(_DWORD *)(v10 + 4) & 1;
  v13 = (unsigned __int8)v19 & 1;
  *((_QWORD *)a3 + 3) = v12;
  v14 = (unsigned int)v13 | 2LL;
  if ( ((unsigned __int8)v19 & 2) == 0 )
    v14 = v13;
  *((_QWORD *)a3 + 2) = v12 & v14;
  a1->IoStatus.Information = 40;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 225);
    goto LABEL_33;
  }
LABEL_36:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400590c0  mov     [rsp-28h+arg_8], rbx
0x1400590c5  mov     [rsp-28h+arg_10], rsi
0x1400590ca  push    rbp
0x1400590cb  push    rdi
0x1400590cc  push    r12
0x1400590ce  push    r13
0x1400590d0  push    r14
0x1400590d2  mov     rbp, rsp
0x1400590d5  sub     rsp, 70h
0x1400590d9  mov     rdi, r8
0x1400590dc  mov     [rbp+arg_18], 0
0x1400590e0  mov     rsi, rcx
0x1400590e3  mov     [rbp+arg_0], 0
0x1400590e7  mov     [rbp+var_18], 0
0x1400590ef  mov     [rbp+var_20], 0
0x1400590f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400590fe  lea     r12, WPP_GLOBAL_Control
0x140059105  lea     r13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005910c  cmp     rcx, r12
0x14005910f  jz      short loc_14005912B
0x140059111  cmp     byte ptr [rcx+29h], 2
0x140059115  jb      short loc_14005912B
0x140059117  mov     rcx, [rcx+18h]
0x14005911b  mov     edx, 0DDh
0x140059120  mov     r9, rsi
0x140059123  mov     r8, r13
0x140059126  call    WPP_SF_q
0x14005912b  lea     rax, [rbp+var_20]
0x14005912f  mov     rcx, rsi; struct _IRP *
0x140059132  mov     [rsp+70h+var_48], rax; struct _HW_DEVICE_EXTENSION **
0x140059137  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x14005913b  lea     rax, [rbp+var_18]
0x14005913f  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x140059143  mov     [rsp+70h+var_50], rax; struct _TOPOLOGY_NODE_INFO **
0x140059148  lea     rdx, [rbp+var_10]; struct _KSFILTER **
0x14005914c  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140059151  mov     ebx, eax
0x140059153  test    eax, eax
0x140059155  jns     short loc_14005918A
0x140059157  mov     rcx, cs:WPP_GLOBAL_Control
0x14005915e  cmp     rcx, r12
0x140059161  jz      loc_14005934D
0x140059167  cmp     byte ptr [rcx+29h], 2
0x14005916b  jb      loc_140059327
0x140059171  mov     rcx, [rcx+18h]
0x140059175  mov     edx, 0DEh
0x14005917a  mov     r9, rsi
0x14005917d  mov     r8, r13
0x140059180  call    WPP_SF_q
0x140059185  jmp     loc_140059327
0x14005918a  xor     r9d, r9d
0x14005918d  mov     rdx, rdi
0x140059190  mov     rcx, rsi
0x140059193  lea     r8d, [r9+28h]
0x140059197  call    ValidateExtendedPropertyDataBufferLength
0x14005919c  mov     ebx, eax
0x14005919e  test    eax, eax
0x1400591a0  jns     short loc_1400591D2
0x1400591a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591a9  cmp     rcx, r12
0x1400591ac  jz      loc_14005934D
0x1400591b2  cmp     byte ptr [rcx+29h], 4
0x1400591b6  jb      loc_140059327
0x1400591bc  mov     edx, 0DFh
0x1400591c1  mov     rcx, [rcx+18h]
0x1400591c5  mov     r8, r13
0x1400591c8  call    WPP_SF_
0x1400591cd  jmp     loc_140059327
0x1400591d2  cmp     dword ptr [rdi], 1
0x1400591d5  mov     ebx, 0C000000Dh
0x1400591da  jnz     short loc_1400591E2
0x1400591dc  cmp     [rdi+8], r8d
0x1400591e0  jnb     short loc_14005921D
0x1400591e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400591e9  cmp     rcx, r12
0x1400591ec  jz      loc_14005934D
0x1400591f2  cmp     byte ptr [rcx+29h], 2
0x1400591f6  jb      loc_140059327
0x1400591fc  mov     eax, [rdi+4]
0x1400591ff  mov     edx, 0E3h
0x140059204  mov     r9d, [rdi+8]
0x140059208  mov     r8, r13
0x14005920b  mov     rcx, [rcx+18h]
0x14005920f  mov     dword ptr [rsp+70h+var_50], eax
0x140059213  call    WPP_SF_dd
0x140059218  jmp     loc_140059327
0x14005921d  mov     rax, [rbp+var_20]
0x140059221  mov     r14, [rax+420h]
0x140059228  test    r14, r14
0x14005922b  jnz     short loc_140059251
0x14005922d  mov     rcx, cs:WPP_GLOBAL_Control
0x140059234  cmp     rcx, r12
0x140059237  jz      loc_14005934D
0x14005923d  cmp     byte ptr [rcx+29h], 2
0x140059241  jb      loc_140059327
0x140059247  mov     edx, 0E0h
0x14005924c  jmp     loc_1400591C1
0x140059251  mov     [rsp+70h+var_30], rax; __int64
0x140059256  mov     r8d, 0D00h; int
0x14005925c  mov     rax, [rbp+var_18]
0x140059260  mov     dl, 81h; int
0x140059262  mov     [rsp+70h+var_38], rax; __int64
0x140059267  mov     cl, 0A1h; int
0x140059269  lea     rax, [rbp+var_20]
0x14005926d  mov     dword ptr [rsp+70h+Size], 4; Size
0x140059275  mov     [rsp+70h+var_48], rax; void *
0x14005927a  mov     al, [rbp+arg_0]
0x14005927d  mov     dword ptr [rbp+var_20], r9d
0x140059281  mov     r9b, [rbp+arg_18]; int
0x140059285  mov     byte ptr [rsp+70h+var_50], al; int
0x140059289  call    SubmitControlRequest
0x14005928e  mov     ebx, eax
0x140059290  test    eax, eax
0x140059292  js      short loc_140059301
0x140059294  mov     ecx, [r14+4]
0x140059298  mov     edx, dword ptr [rbp+var_20]
0x14005929b  and     ecx, 1
0x14005929e  mov     r8d, ecx
0x1400592a1  or      r8, 2
0x1400592a5  test    byte ptr [r14+4], 2
0x1400592aa  cmovz   r8, rcx
0x1400592ae  and     edx, 1
0x1400592b1  mov     ecx, edx
0x1400592b3  mov     [rdi+18h], r8
0x1400592b7  or      rcx, 2
0x1400592bb  test    byte ptr [rbp+var_20], 2
0x1400592bf  cmovz   rcx, rdx
0x1400592c3  and     rcx, r8
0x1400592c6  mov     [rdi+10h], rcx
0x1400592ca  mov     qword ptr [rsi+38h], 28h ; '('
0x1400592d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400592d9  cmp     rcx, r12
0x1400592dc  jz      short loc_14005934D
0x1400592de  cmp     byte ptr [rcx+29h], 4
0x1400592e2  jb      short loc_140059327
0x1400592e4  mov     rax, [rdi+18h]
0x1400592e8  mov     edx, 0E1h
0x1400592ed  mov     r9, [rdi+10h]
0x1400592f1  mov     rcx, [rcx+18h]
0x1400592f5  mov     [rsp+70h+var_50], rax
0x1400592fa  call    WPP_SF_ii
0x1400592ff  jmp     short loc_140059327
0x140059301  mov     rcx, cs:WPP_GLOBAL_Control
0x140059308  cmp     rcx, r12
0x14005930b  jz      short loc_14005934D
0x14005930d  cmp     byte ptr [rcx+29h], 2
0x140059311  jb      short loc_140059327
0x140059313  mov     rcx, [rcx+18h]
0x140059317  mov     edx, 0E2h
0x14005931c  mov     r9d, eax
0x14005931f  mov     r8, r13
0x140059322  call    WPP_SF_d
0x140059327  mov     rcx, cs:WPP_GLOBAL_Control
0x14005932e  cmp     rcx, r12
0x140059331  jz      short loc_14005934D
0x140059333  cmp     byte ptr [rcx+29h], 4
0x140059337  jb      short loc_14005934D
0x140059339  mov     rcx, [rcx+18h]
0x14005933d  mov     edx, 0E4h
0x140059342  mov     r9d, ebx
0x140059345  mov     r8, r13
0x140059348  call    WPP_SF_d
0x14005934d  lea     r11, [rsp+70h+var_s0]
0x140059352  mov     [rsi+30h], ebx
0x140059355  mov     rsi, [r11+40h]
0x140059359  mov     eax, ebx
0x14005935b  mov     rbx, [r11+38h]
0x14005935f  mov     rsp, r11
0x140059362  pop     r14
0x140059364  pop     r13
0x140059366  pop     r12
0x140059368  pop     rdi
0x140059369  pop     rbp
0x14005936a  retn
```
