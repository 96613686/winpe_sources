# MSXU_Framerate_ThrottleSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140058200`
- end: `0x1400586eb`
- name: `?MSXU_Framerate_ThrottleSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `1259`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14000ef88`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b1ec`
- `0x14003b3b0`
- `0x14003b5d0`
- `0x14003b85c`
- `0x140040a30`
- `0x140058200`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_Framerate_ThrottleSet(struct _IRP *a1, struct KSIDENTIFIER *a2, CExtendedVidProcSetting *a3)
{
  struct _IRP *v4; // rsi
  int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // r11d
  __int64 v11; // rcx
  __int64 v12; // rax
  _DWORD *v13; // r12
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int v17; // r15d
  int v18; // r14d
  unsigned int v19; // esi
  unsigned int v20; // r13d
  int v21; // r9d
  struct _HW_DEVICE_EXTENSION *v22; // rsi
  unsigned __int8 v23; // r9
  int v25; // [rsp+20h] [rbp-59h]
  size_t Size; // [rsp+30h] [rbp-49h]
  struct _TOPOLOGY_NODE_INFO *v27; // [rsp+38h] [rbp-41h]
  struct _HW_DEVICE_EXTENSION *v28; // [rsp+40h] [rbp-39h]
  unsigned __int8 v29; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int8 v30[7]; // [rsp+51h] [rbp-28h] BYREF
  struct _IRP *v31; // [rsp+58h] [rbp-21h]
  struct _HW_DEVICE_EXTENSION *v32; // [rsp+60h] [rbp-19h] BYREF
  struct _KSFILTER *v33; // [rsp+68h] [rbp-11h] BYREF
  struct _TOPOLOGY_NODE_INFO *v34; // [rsp+70h] [rbp-9h] BYREF
  _DWORD v35[6]; // [rsp+78h] [rbp-1h] BYREF

  v31 = a1;
  v30[0] = 0;
  v29 = 0;
  v4 = a1;
  v34 = 0;
  v32 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 250, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(v4, &v33, v30, &v29, &v34, &v32);
  if ( v5 >= 0 )
  {
    v5 = ValidateExtendedPropertyDataBufferLength(v4, a3, 64);
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_70;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_9;
      v7 = 252;
      goto LABEL_8;
    }
    v5 = -1073741811;
    if ( !CExtendedVidProcSetting::isValid(a3) || *((_DWORD *)a3 + 1) != -1 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_70;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 259, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      goto LABEL_67;
    }
    v11 = *((_QWORD *)v32 + 133);
    if ( !v11 || (v12 = *((unsigned __int16 *)v32 + 626), !(_WORD)v12) )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_25;
      v15 = 253;
      goto LABEL_24;
    }
    v13 = (_DWORD *)(v11 + 2 * v12);
    if ( !v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_25;
      v15 = 254;
LABEL_24:
      WPP_SF_(v14->AttachedDevice, v15, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
LABEL_25:
      v5 = -1073741436;
      goto LABEL_9;
    }
    v16 = *((_QWORD *)a3 + 2);
    v9 = 1;
    if ( (v16 & 1) != v16 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_70;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 258);
      goto LABEL_67;
    }
    v17 = *((_DWORD *)a3 + 11);
    v18 = *((_DWORD *)a3 + 10);
    v19 = *((_DWORD *)a3 + 9);
    v20 = *((_DWORD *)a3 + 12);
    if ( v16 )
    {
      if ( v16 == 1 )
      {
        v21 = 1;
LABEL_33:
        v35[0] = v21;
        v35[1] = v20;
        v35[2] = v19;
        v35[3] = v18;
        v35[4] = v17;
        if ( v18 != v13[3]
          || v19 != v13[2]
          || v17 != v13[4]
          || v18 != 100
          || !v19
          || v19 >= 0x64
          || v19 % v17
          || 0x64 % v17
          || v20 > 0x64
          || v20 < v19
          || v20 % v17 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_LLLLL(WPP_GLOBAL_Control->AttachedDevice, 255);
          v4 = v31;
          goto LABEL_9;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v25 = v20;
          WPP_SF_LLLLL(WPP_GLOBAL_Control->AttachedDevice, 256);
        }
        v22 = v32;
        v23 = v30[0];
        v28 = v32;
        *((_QWORD *)v32 + 150) = v33;
        v27 = v34;
        LODWORD(Size) = 20;
        LOBYTE(v25) = v29;
        *((_DWORD *)v22 + 333) = 1;
        v5 = SubmitControlRequest(0x21u, 1u, 0xE00u, v23, v25, (unsigned __int8 *)v35, Size, (__int64)v27, (__int64)v28);
        if ( v5 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              257,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              (unsigned int)v5);
          *((_QWORD *)v22 + 150) = 0;
          v4 = v31;
        }
        else
        {
          v4 = v31;
          v31->IoStatus.Information = 64;
        }
LABEL_67:
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_70;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_diLLLLD(
            WPP_GLOBAL_Control->AttachedDevice,
            v8,
            v9,
            *((unsigned int *)a3 + 1),
            *((_QWORD *)a3 + 2),
            *((_DWORD *)a3 + 12),
            *((_DWORD *)a3 + 9),
            *((_DWORD *)a3 + 10),
            *((_DWORD *)a3 + 11),
            v5);
        goto LABEL_9;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v25 = *((_DWORD *)a3 + 12);
        WPP_SF_ILLLL(WPP_GLOBAL_Control->AttachedDevice);
        v10 = 0;
      }
    }
    v21 = v10;
    goto LABEL_33;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_70;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v7 = 251;
LABEL_8:
    WPP_SF_(v6->AttachedDevice, v7, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_9:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 261, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v5);
LABEL_70:
  v4->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140058200  mov     [rsp-8+arg_8], rbx
0x140058205  push    rbp
0x140058206  push    rsi
0x140058207  push    rdi
0x140058208  push    r12
0x14005820a  push    r13
0x14005820c  push    r14
0x14005820e  push    r15
0x140058210  lea     rbp, [rsp-27h]
0x140058215  sub     rsp, 0A0h
0x14005821c  mov     rax, cs:__security_cookie
0x140058223  xor     rax, rsp
0x140058226  mov     [rbp+57h+var_40], rax
0x14005822a  xor     r14d, r14d
0x14005822d  mov     [rbp+57h+var_78], rcx
0x140058231  mov     [rbp+57h+var_7F], r14b
0x140058235  mov     rdi, r8
0x140058238  mov     [rbp+57h+var_80], r14b
0x14005823c  mov     rsi, rcx
0x14005823f  mov     [rbp+57h+var_60], r14
0x140058243  mov     [rbp+57h+var_70], r14
0x140058247  mov     [rbp+57h+var_68], r14
0x14005824b  mov     rcx, cs:WPP_GLOBAL_Control
0x140058252  lea     r14, WPP_GLOBAL_Control
0x140058259  lea     r15, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140058260  cmp     rcx, r14
0x140058263  jz      short loc_14005827F
0x140058265  cmp     byte ptr [rcx+29h], 4
0x140058269  jb      short loc_14005827F
0x14005826b  mov     rcx, [rcx+18h]
0x14005826f  mov     edx, 0FAh
0x140058274  mov     r9, rsi
0x140058277  mov     r8, r15
0x14005827a  call    WPP_SF_q
0x14005827f  lea     rax, [rbp+57h+var_70]
0x140058283  mov     rcx, rsi; struct _IRP *
0x140058286  mov     [rsp+0D0h+var_A8], rax; struct _HW_DEVICE_EXTENSION **
0x14005828b  lea     r9, [rbp+57h+var_80]; unsigned __int8 *
0x14005828f  lea     rax, [rbp+57h+var_60]
0x140058293  lea     r8, [rbp+57h+var_7F]; unsigned __int8 *
0x140058297  mov     [rsp+0D0h+var_B0], rax; struct _TOPOLOGY_NODE_INFO **
0x14005829c  lea     rdx, [rbp+57h+var_68]; struct _KSFILTER **
0x1400582a0  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z
0x1400582a5  xor     r11d, r11d
0x1400582a8  mov     ebx, eax
0x1400582aa  test    eax, eax
0x1400582ac  jns     short loc_14005830C
0x1400582ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400582b5  cmp     rcx, r14
0x1400582b8  jz      loc_1400586BE
0x1400582be  cmp     byte ptr [rcx+29h], 2
0x1400582c2  jb      short loc_1400582D5
0x1400582c4  mov     edx, 0FBh
0x1400582c9  mov     rcx, [rcx+18h]
0x1400582cd  mov     r8, r15
0x1400582d0  call    WPP_SF_
0x1400582d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400582dc  cmp     rcx, r14
0x1400582df  jz      loc_1400586BE
0x1400582e5  cmp     byte ptr [rcx+29h], 4
0x1400582e9  jb      loc_1400586BE
0x1400582ef  mov     rcx, [rcx+18h]
0x1400582f3  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400582fa  mov     edx, 105h
0x1400582ff  mov     r9d, ebx
0x140058302  call    WPP_SF_d
0x140058307  jmp     loc_1400586BE
0x14005830c  xor     r9d, r9d
0x14005830f  mov     rdx, rdi
0x140058312  mov     rcx, rsi
0x140058315  lea     r8d, [r9+40h]
0x140058319  call    ValidateExtendedPropertyDataBufferLength
0x14005831e  mov     ebx, eax
0x140058320  test    eax, eax
0x140058322  jns     short loc_140058341
0x140058324  mov     rcx, cs:WPP_GLOBAL_Control
0x14005832b  cmp     rcx, r14
0x14005832e  jz      loc_1400586BE
0x140058334  cmp     byte ptr [rcx+29h], 2
0x140058338  jb      short loc_1400582D5
0x14005833a  mov     edx, 0FCh
0x14005833f  jmp     short loc_1400582C9
0x140058341  mov     rcx, rdi; this
0x140058344  mov     ebx, 0C000000Dh
0x140058349  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ
0x14005834e  test    al, al
0x140058350  jz      loc_14005864A
0x140058356  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x14005835a  jnz     loc_14005864A
0x140058360  mov     rax, [rbp+57h+var_70]
0x140058364  mov     rcx, [rax+428h]
0x14005836b  test    rcx, rcx
0x14005836e  jz      loc_140058626
0x140058374  movzx   eax, word ptr [rax+4E4h]
0x14005837b  test    ax, ax
0x14005837e  jz      loc_140058626
0x140058384  lea     r12, [rcx+rax*2]
0x140058388  test    r12, r12
0x14005838b  jnz     short loc_1400583BA
0x14005838d  mov     rcx, cs:WPP_GLOBAL_Control
0x140058394  cmp     rcx, r14
0x140058397  jz      short loc_1400583B0
0x140058399  cmp     byte ptr [rcx+29h], 2
0x14005839d  jb      short loc_1400583B0
0x14005839f  mov     edx, 0FEh
0x1400583a4  mov     rcx, [rcx+18h]
0x1400583a8  mov     r8, r15
0x1400583ab  call    WPP_SF_
0x1400583b0  mov     ebx, 0C0000184h
0x1400583b5  jmp     loc_1400582D5
0x1400583ba  mov     r9, [rdi+10h]
0x1400583be  mov     r8d, 1
0x1400583c4  mov     rax, r9
0x1400583c7  and     rax, r8
0x1400583ca  cmp     rax, r9
0x1400583cd  jnz     loc_1400585FB
0x1400583d3  mov     r15d, [rdi+2Ch]
0x1400583d7  mov     rax, r9
0x1400583da  mov     r14d, [rdi+28h]
0x1400583de  mov     esi, [rdi+24h]
0x1400583e1  mov     r13d, [rdi+30h]
0x1400583e5  test    r9, r9
0x1400583e8  jz      short loc_14005842B
0x1400583ea  cmp     rax, r8
0x1400583ed  jz      loc_14005856B
0x1400583f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400583fa  lea     r8, WPP_GLOBAL_Control
0x140058401  cmp     rcx, r8
0x140058404  jz      short loc_140058432
0x140058406  cmp     byte ptr [rcx+29h], 2
0x14005840a  jb      short loc_140058432
0x14005840c  mov     rcx, [rcx+18h]
0x140058410  mov     dword ptr [rsp+0D0h+var_98], r15d
0x140058415  mov     dword ptr [rsp+0D0h+Size], r14d
0x14005841a  mov     dword ptr [rsp+0D0h+var_A8], esi
0x14005841e  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x140058423  call    WPP_SF_ILLLL
0x140058428  xor     r11d, r11d
0x14005842b  lea     r8, WPP_GLOBAL_Control
0x140058432  mov     r9d, r11d
0x140058435  mov     [rbp+57h+var_58], r9d
0x140058439  mov     [rbp+57h+var_54], r13d
0x14005843d  mov     [rbp+57h+var_50], esi
0x140058440  mov     [rbp+57h+var_4C], r14d
0x140058444  mov     [rbp+57h+var_48], r15d
0x140058448  cmp     r14d, [r12+0Ch]
0x14005844d  jnz     loc_1400585B8
0x140058453  cmp     esi, [r12+8]
0x140058458  jnz     loc_1400585B8
0x14005845e  cmp     r15d, [r12+10h]
0x140058463  jnz     loc_1400585B8
0x140058469  cmp     r14d, 64h ; 'd'
0x14005846d  jnz     loc_1400585B8
0x140058473  test    esi, esi
0x140058475  jz      loc_1400585B8
0x14005847b  cmp     esi, r14d
0x14005847e  jnb     loc_1400585B8
0x140058484  xor     edx, edx
0x140058486  mov     eax, esi
0x140058488  div     r15d
0x14005848b  test    edx, edx
0x14005848d  jnz     loc_1400585B8
0x140058493  xor     edx, edx
0x140058495  mov     eax, r14d
0x140058498  div     r15d
0x14005849b  test    edx, edx
0x14005849d  jnz     loc_1400585B8
0x1400584a3  cmp     r13d, r14d
0x1400584a6  ja      loc_1400585B8
0x1400584ac  cmp     r13d, esi
0x1400584af  jb      loc_1400585B8
0x1400584b5  xor     edx, edx
0x1400584b7  mov     eax, r13d
0x1400584ba  div     r15d
0x1400584bd  test    edx, edx
0x1400584bf  jnz     loc_1400585B8
0x1400584c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400584cc  cmp     rcx, r8
0x1400584cf  jz      short loc_1400584F8
0x1400584d1  cmp     byte ptr [rcx+29h], 4
0x1400584d5  jb      short loc_1400584F8
0x1400584d7  mov     rcx, [rcx+18h]
0x1400584db  mov     edx, 100h
0x1400584e0  mov     dword ptr [rsp+0D0h+var_98], r15d
0x1400584e5  mov     dword ptr [rsp+0D0h+Size], r14d
0x1400584ea  mov     dword ptr [rsp+0D0h+var_A8], esi
0x1400584ee  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x1400584f3  call    WPP_SF_LLLLL
0x1400584f8  mov     rsi, [rbp+57h+var_70]
0x1400584fc  mov     r8d, 0E00h; int
0x140058502  mov     rax, [rbp+57h+var_68]
0x140058506  mov     dl, 1; int
0x140058508  mov     r9b, [rbp+57h+var_7F]; int
0x14005850c  mov     cl, 21h ; '!'; int
0x14005850e  mov     [rsp+0D0h+var_90], rsi; __int64
0x140058513  mov     [rsi+4B0h], rax
0x14005851a  mov     rax, [rbp+57h+var_60]
0x14005851e  mov     [rsp+0D0h+var_98], rax; __int64
0x140058523  lea     rax, [rbp+57h+var_58]
0x140058527  mov     dword ptr [rsp+0D0h+Size], 14h; Size
0x14005852f  mov     [rsp+0D0h+var_A8], rax; void *
0x140058534  mov     al, [rbp+57h+var_80]
0x140058537  mov     byte ptr [rsp+0D0h+var_B0], al; int
0x14005853b  mov     dword ptr [rsi+534h], 1
0x140058545  call    SubmitControlRequest
0x14005854a  xor     r14d, r14d
0x14005854d  mov     ebx, eax
0x14005854f  test    eax, eax
0x140058551  js      short loc_14005857A
0x140058553  mov     rsi, [rbp+57h+var_78]
0x140058557  mov     qword ptr [rsi+38h], 40h ; '@'
0x14005855f  lea     r14, WPP_GLOBAL_Control
0x140058566  jmp     loc_14005866D
0x14005856b  mov     r9d, r8d
0x14005856e  lea     r8, WPP_GLOBAL_Control
0x140058575  jmp     loc_140058435
0x14005857a  mov     rcx, cs:WPP_GLOBAL_Control
0x140058581  lea     rax, WPP_GLOBAL_Control
0x140058588  cmp     rcx, rax
0x14005858b  jz      short loc_1400585AB
0x14005858d  cmp     byte ptr [rcx+29h], 2
0x140058591  jb      short loc_1400585AB
0x140058593  mov     rcx, [rcx+18h]
0x140058597  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005859e  mov     edx, 101h
0x1400585a3  mov     r9d, ebx
0x1400585a6  call    WPP_SF_d
0x1400585ab  mov     [rsi+4B0h], r14
0x1400585b2  mov     rsi, [rbp+57h+var_78]
0x1400585b6  jmp     short loc_14005855F
0x1400585b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400585bf  cmp     rcx, r8
0x1400585c2  jz      short loc_1400585EB
0x1400585c4  cmp     byte ptr [rcx+29h], 2
0x1400585c8  jb      short loc_1400585EB
0x1400585ca  mov     rcx, [rcx+18h]
0x1400585ce  mov     edx, 0FFh
0x1400585d3  mov     dword ptr [rsp+0D0h+var_98], r15d
0x1400585d8  mov     dword ptr [rsp+0D0h+Size], r14d
0x1400585dd  mov     dword ptr [rsp+0D0h+var_A8], esi
0x1400585e1  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x1400585e6  call    WPP_SF_LLLLL
0x1400585eb  mov     rsi, [rbp+57h+var_78]
0x1400585ef  lea     r14, WPP_GLOBAL_Control
0x1400585f6  jmp     loc_1400582D5
0x1400585fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140058602  cmp     rcx, r14
0x140058605  jz      loc_1400586BE
0x14005860b  cmp     byte ptr [rcx+29h], 2
0x14005860f  jb      short loc_14005866D
0x140058611  mov     rcx, [rcx+18h]
0x140058615  mov     edx, 102h
0x14005861a  mov     [rsp+0D0h+var_B0], r8
0x14005861f  call    WPP_SF_ii
0x140058624  jmp     short loc_14005866D
0x140058626  mov     rcx, cs:WPP_GLOBAL_Control
0x14005862d  cmp     rcx, r14
0x140058630  jz      loc_1400583B0
0x140058636  cmp     byte ptr [rcx+29h], 2
0x14005863a  jb      loc_1400583B0
0x140058640  mov     edx, 0FDh
0x140058645  jmp     loc_1400583A4
0x14005864a  mov     rcx, cs:WPP_GLOBAL_Control
0x140058651  cmp     rcx, r14
0x140058654  jz      short loc_1400586BE
0x140058656  cmp     byte ptr [rcx+29h], 2
0x14005865a  jb      short loc_14005866D
0x14005865c  mov     rcx, [rcx+18h]
0x140058660  mov     edx, 103h
0x140058665  mov     r8, r15
0x140058668  call    WPP_SF_
0x14005866d  mov     rcx, cs:WPP_GLOBAL_Control
0x140058674  cmp     rcx, r14
0x140058677  jz      short loc_1400586BE
0x140058679  cmp     byte ptr [rcx+29h], 4
0x14005867d  jb      loc_1400582D5
0x140058683  mov     eax, [rdi+2Ch]
0x140058686  mov     r9d, [rdi+4]
0x14005868a  mov     rcx, [rcx+18h]
0x14005868e  mov     [rsp+0D0h+var_88], ebx
0x140058692  mov     dword ptr [rsp+0D0h+var_90], eax
0x140058696  mov     eax, [rdi+28h]
0x140058699  mov     dword ptr [rsp+0D0h+var_98], eax
0x14005869d  mov     eax, [rdi+24h]
0x1400586a0  mov     dword ptr [rsp+0D0h+Size], eax
0x1400586a4  mov     eax, [rdi+30h]
0x1400586a7  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1400586ab  mov     rax, [rdi+10h]
0x1400586af  mov     [rsp+0D0h+var_B0], rax
0x1400586b4  call    WPP_SF_diLLLLD
0x1400586b9  jmp     loc_1400582D5
0x1400586be  mov     [rsi+30h], ebx
0x1400586c1  mov     eax, ebx
0x1400586c3  mov     rcx, [rbp+57h+var_40]
0x1400586c7  xor     rcx, rsp; StackCookie
0x1400586ca  call    __security_check_cookie
0x1400586cf  mov     rbx, [rsp+0D0h+arg_8]
0x1400586d7  add     rsp, 0A0h
0x1400586de  pop     r15
0x1400586e0  pop     r14
  ... truncated ...
```
