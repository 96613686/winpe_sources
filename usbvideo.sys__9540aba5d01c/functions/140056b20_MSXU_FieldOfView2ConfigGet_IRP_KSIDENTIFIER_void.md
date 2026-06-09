# MSXU_FieldOfView2ConfigGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140056b20`
- end: `0x140056edf`
- name: `?MSXU_FieldOfView2ConfigGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `959`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x140004bac`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14001d0cc`
- `0x14003b308`
- `0x14003b438`
- `0x140056b20`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_FieldOfView2ConfigGet(struct _IRP *a1, struct KSIDENTIFIER *a2, _WORD *a3)
{
  NTSTATUS v6; // ebx
  __int64 v7; // r8
  unsigned int v8; // r11d
  __int64 v9; // rdx
  int v10; // eax
  unsigned int v11; // esi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  _WORD *v14; // r12
  __int64 v15; // rdx
  _OWORD *v16; // rax
  _OWORD *v17; // rcx
  __int64 v18; // r8
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int64 v32; // rax
  unsigned int i; // r14d
  __int64 v34; // rdx
  int v36; // [rsp+20h] [rbp-E0h]
  struct _HW_DEVICE_EXTENSION *v37; // [rsp+30h] [rbp-D0h] BYREF
  struct _TOPOLOGY_NODE_INFO *v38; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v39[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h]
  __int64 v41; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v44; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int8 v45; // [rsp+398h] [rbp+298h] BYREF

  v45 = 0;
  v44 = 0;
  v38 = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 262, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  if ( !a1 || !a2 )
  {
    v6 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_48;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 263, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1, a2);
    goto LABEL_45;
  }
  v6 = MSXUGetInfo(a1, 0, &v45, &v44, &v38, &v37);
  if ( v6 >= 0 )
  {
    v6 = ValidateExtendedPropertyDataBufferLength(a1, a3, 760);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_48;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 265, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      goto LABEL_45;
    }
    v9 = *((_QWORD *)v37 + 134);
    if ( v9 && (v10 = *((unsigned __int16 *)v37 + 627), *((_WORD *)v37 + 627)) )
    {
      v11 = (unsigned int)(v10 - 4) >> 2;
      if ( v11 <= 0x168 )
      {
        v14 = (_WORD *)(v9 + (unsigned int)(2 * v10));
        if ( v14 )
        {
          if ( *(_DWORD *)a3 == 1 && *((_DWORD *)a3 + 2) >= v8 && *((_DWORD *)a3 + 1) == -1 )
          {
            v15 = 5;
            v39[1] = -1;
            v40 = v7;
            v16 = v39;
            v39[0] = 1;
            v17 = a3;
            v42 = 0;
            v18 = 128;
            v41 = 0;
            v43 = 0;
            do
            {
              v19 = v16[1];
              *v17 = *v16;
              v20 = v16[2];
              v17[1] = v19;
              v21 = v16[3];
              v17[2] = v20;
              v22 = v16[4];
              v17[3] = v21;
              v23 = v16[5];
              v17[4] = v22;
              v24 = v16[6];
              v17[5] = v23;
              v25 = v16[7];
              v16 += 8;
              v17[6] = v24;
              v17[7] = v25;
              v17 += 8;
              --v15;
            }
            while ( v15 );
            v26 = v16[1];
            *v17 = *v16;
            v27 = v16[2];
            v17[1] = v26;
            v28 = v16[3];
            v17[2] = v27;
            v29 = v16[4];
            v17[3] = v28;
            v30 = v16[5];
            v17[4] = v29;
            v31 = v16[6];
            v32 = *((_QWORD *)v16 + 14);
            v17[5] = v30;
            v17[6] = v31;
            *((_QWORD *)v17 + 14) = v32;
            a3[16] = *v14;
            a3[17] = v11;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_HH(WPP_GLOBAL_Control->AttachedDevice, 0, 128);
            for ( i = 0; i < v11; ++i )
            {
              v34 = (unsigned __int16)v14[2 * i + 2];
              a3[i + 18] = v34;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                LOWORD(v36) = v34;
                WPP_SF_LH(WPP_GLOBAL_Control->AttachedDevice, v34, v18, i, v36);
              }
            }
            a1->IoStatus.Information = 760;
          }
          else
          {
            v6 = -1073741811;
          }
        }
        else
        {
          v6 = -1073741670;
        }
        goto LABEL_45;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_41;
      v13 = 267;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_41;
      v13 = 266;
    }
    WPP_SF_(v12->AttachedDevice, v13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
LABEL_41:
    v6 = -1073741436;
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_48;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 264, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
LABEL_45:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 270, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v6);
LABEL_48:
  a1->IoStatus.Status = v6;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140056b20  mov     [rsp-8+arg_8], rbx
0x140056b25  push    rbp
0x140056b26  push    rsi
0x140056b27  push    rdi
0x140056b28  push    r12
0x140056b2a  push    r13
0x140056b2c  push    r14
0x140056b2e  push    r15
0x140056b30  lea     rbp, [rsp-240h]
0x140056b38  sub     rsp, 340h
0x140056b3f  xor     r13d, r13d
0x140056b42  mov     r15, r8
0x140056b45  mov     [rbp+270h+arg_18], r13b
0x140056b4c  mov     rsi, rdx
0x140056b4f  mov     [rbp+270h+arg_0], r13b
0x140056b56  mov     rdi, rcx
0x140056b59  mov     [rsp+370h+var_338], r13
0x140056b5e  mov     [rsp+370h+var_340], r13
0x140056b63  mov     rcx, cs:WPP_GLOBAL_Control
0x140056b6a  lea     r14, WPP_GLOBAL_Control
0x140056b71  cmp     rcx, r14
0x140056b74  jz      short loc_140056B94
0x140056b76  cmp     byte ptr [rcx+29h], 4
0x140056b7a  jb      short loc_140056B94
0x140056b7c  mov     rcx, [rcx+18h]
0x140056b80  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140056b87  mov     edx, 106h
0x140056b8c  mov     r9, rdi
0x140056b8f  call    WPP_SF_q
0x140056b94  test    rdi, rdi
0x140056b97  jz      loc_140056E60
0x140056b9d  test    rsi, rsi
0x140056ba0  jz      loc_140056E60
0x140056ba6  lea     rax, [rsp+370h+var_340]
0x140056bab  xor     edx, edx; struct _KSFILTER **
0x140056bad  mov     [rsp+370h+var_348], rax; struct _HW_DEVICE_EXTENSION **
0x140056bb2  lea     r9, [rbp+270h+arg_0]; unsigned __int8 *
0x140056bb9  lea     rax, [rsp+370h+var_338]
0x140056bbe  mov     rcx, rdi; struct _IRP *
0x140056bc1  lea     r8, [rbp+270h+arg_18]; unsigned __int8 *
0x140056bc8  mov     [rsp+370h+var_350], rax; struct _TOPOLOGY_NODE_INFO **
0x140056bcd  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140056bd2  mov     ebx, eax
0x140056bd4  test    eax, eax
0x140056bd6  jns     short loc_140056C0F
0x140056bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140056bdf  cmp     rcx, r14
0x140056be2  jz      loc_140056EBE
0x140056be8  cmp     byte ptr [rcx+29h], 2
0x140056bec  jb      loc_140056E94
0x140056bf2  mov     rcx, [rcx+18h]
0x140056bf6  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140056bfd  mov     edx, 108h
0x140056c02  mov     r9, rdi
0x140056c05  call    WPP_SF_q
0x140056c0a  jmp     loc_140056E94
0x140056c0f  mov     r11d, 2F8h
0x140056c15  xor     r9d, r9d
0x140056c18  mov     r8d, r11d
0x140056c1b  mov     rdx, r15
0x140056c1e  mov     rcx, rdi
0x140056c21  call    ValidateExtendedPropertyDataBufferLength
0x140056c26  mov     ebx, eax
0x140056c28  test    eax, eax
0x140056c2a  jns     short loc_140056C60
0x140056c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056c33  cmp     rcx, r14
0x140056c36  jz      loc_140056EBE
0x140056c3c  cmp     byte ptr [rcx+29h], 2
0x140056c40  jb      loc_140056E94
0x140056c46  mov     rcx, [rcx+18h]
0x140056c4a  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140056c51  mov     edx, 109h
0x140056c56  call    WPP_SF_
0x140056c5b  jmp     loc_140056E94
0x140056c60  mov     rax, [rsp+370h+var_340]
0x140056c65  mov     rdx, [rax+430h]
0x140056c6c  test    rdx, rdx
0x140056c6f  jz      loc_140056E32
0x140056c75  movzx   eax, word ptr [rax+4E6h]
0x140056c7c  test    eax, eax
0x140056c7e  jz      loc_140056E32
0x140056c84  lea     esi, [rax-4]
0x140056c87  shr     esi, 2
0x140056c8a  cmp     esi, 168h
0x140056c90  jbe     short loc_140056CB6
0x140056c92  mov     rcx, cs:WPP_GLOBAL_Control
0x140056c99  cmp     rcx, r14
0x140056c9c  jz      loc_140056E59
0x140056ca2  cmp     byte ptr [rcx+29h], 2
0x140056ca6  jb      loc_140056E59
0x140056cac  mov     edx, 10Bh
0x140056cb1  jmp     loc_140056E49
0x140056cb6  lea     r12d, [rax+rax]
0x140056cba  add     r12, rdx
0x140056cbd  jnz     short loc_140056CC9
0x140056cbf  mov     ebx, 0C000009Ah
0x140056cc4  jmp     loc_140056E94
0x140056cc9  cmp     dword ptr [r15], 1
0x140056ccd  jnz     loc_140056E2B
0x140056cd3  cmp     [r15+8], r11d
0x140056cd7  jb      loc_140056E2B
0x140056cdd  or      eax, 0FFFFFFFFh
0x140056ce0  cmp     [r15+4], eax
0x140056ce4  jnz     loc_140056E2B
0x140056cea  mov     edx, 5
0x140056cef  mov     [rsp+370h+var_32C], eax
0x140056cf3  mov     [rsp+370h+var_328], r8
0x140056cf8  lea     rax, [rsp+370h+var_330]
0x140056cfd  mov     [rsp+370h+var_330], 1
0x140056d05  mov     rcx, r15
0x140056d08  mov     [rsp+370h+var_318], r13
0x140056d0d  lea     r8d, [rdx+7Bh]
0x140056d11  mov     [rsp+370h+var_320], r13
0x140056d16  mov     [rsp+370h+var_310], r13d
0x140056d1b  movups  xmm0, xmmword ptr [rax]
0x140056d1e  movups  xmm1, xmmword ptr [rax+10h]
0x140056d22  movups  xmmword ptr [rcx], xmm0
0x140056d25  movups  xmm0, xmmword ptr [rax+20h]
0x140056d29  movups  xmmword ptr [rcx+10h], xmm1
0x140056d2d  movups  xmm1, xmmword ptr [rax+30h]
0x140056d31  movups  xmmword ptr [rcx+20h], xmm0
0x140056d35  movups  xmm0, xmmword ptr [rax+40h]
0x140056d39  movups  xmmword ptr [rcx+30h], xmm1
0x140056d3d  movups  xmm1, xmmword ptr [rax+50h]
0x140056d41  movups  xmmword ptr [rcx+40h], xmm0
0x140056d45  movups  xmm0, xmmword ptr [rax+60h]
0x140056d49  movups  xmmword ptr [rcx+50h], xmm1
0x140056d4d  movups  xmm1, xmmword ptr [rax+70h]
0x140056d51  add     rax, r8
0x140056d54  movups  xmmword ptr [rcx+60h], xmm0
0x140056d58  movups  xmmword ptr [rcx+70h], xmm1
0x140056d5c  add     rcx, r8
0x140056d5f  sub     rdx, 1
0x140056d63  jnz     short loc_140056D1B
0x140056d65  movups  xmm0, xmmword ptr [rax]
0x140056d68  movups  xmm1, xmmword ptr [rax+10h]
0x140056d6c  movups  xmmword ptr [rcx], xmm0
0x140056d6f  movups  xmm0, xmmword ptr [rax+20h]
0x140056d73  movups  xmmword ptr [rcx+10h], xmm1
0x140056d77  movups  xmm1, xmmword ptr [rax+30h]
0x140056d7b  movups  xmmword ptr [rcx+20h], xmm0
0x140056d7f  movups  xmm0, xmmword ptr [rax+40h]
0x140056d83  movups  xmmword ptr [rcx+30h], xmm1
0x140056d87  movups  xmm1, xmmword ptr [rax+50h]
0x140056d8b  movups  xmmword ptr [rcx+40h], xmm0
0x140056d8f  movups  xmm0, xmmword ptr [rax+60h]
0x140056d93  mov     rax, [rax+70h]
0x140056d97  movups  xmmword ptr [rcx+50h], xmm1
0x140056d9b  movups  xmmword ptr [rcx+60h], xmm0
0x140056d9f  mov     [rcx+70h], rax
0x140056da3  movzx   r9d, word ptr [r12]
0x140056da8  mov     [r15+20h], r9w
0x140056dad  mov     [r15+22h], si
0x140056db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140056db9  cmp     rcx, r14
0x140056dbc  jz      short loc_140056DD2
0x140056dbe  cmp     byte ptr [rcx+29h], 4
0x140056dc2  jb      short loc_140056DD2
0x140056dc4  mov     rcx, [rcx+18h]
0x140056dc8  mov     word ptr [rsp+370h+var_350], si
0x140056dcd  call    WPP_SF_HH
0x140056dd2  mov     r14d, r13d
0x140056dd5  test    esi, esi
0x140056dd7  jz      short loc_140056E1A
0x140056dd9  lea     r13, WPP_GLOBAL_Control
0x140056de0  mov     eax, r14d
0x140056de3  movzx   edx, word ptr [r12+rax*4+4]
0x140056de9  mov     [r15+rax*2+24h], dx
0x140056def  mov     rcx, cs:WPP_GLOBAL_Control
0x140056df6  cmp     rcx, r13
0x140056df9  jz      short loc_140056E12
0x140056dfb  cmp     byte ptr [rcx+29h], 4
0x140056dff  jb      short loc_140056E12
0x140056e01  mov     rcx, [rcx+18h]
0x140056e05  mov     r9d, r14d
0x140056e08  mov     word ptr [rsp+370h+var_350], dx
0x140056e0d  call    WPP_SF_LH
0x140056e12  inc     r14d
0x140056e15  cmp     r14d, esi
0x140056e18  jb      short loc_140056DE0
0x140056e1a  mov     qword ptr [rdi+38h], 2F8h
0x140056e22  lea     r14, WPP_GLOBAL_Control
0x140056e29  jmp     short loc_140056E94
0x140056e2b  mov     ebx, 0C000000Dh
0x140056e30  jmp     short loc_140056E94
0x140056e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140056e39  cmp     rcx, r14
0x140056e3c  jz      short loc_140056E59
0x140056e3e  cmp     byte ptr [rcx+29h], 2
0x140056e42  jb      short loc_140056E59
0x140056e44  mov     edx, 10Ah
0x140056e49  mov     rcx, [rcx+18h]
0x140056e4d  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140056e54  call    WPP_SF_
0x140056e59  mov     ebx, 0C0000184h
0x140056e5e  jmp     short loc_140056E94
0x140056e60  mov     rcx, cs:WPP_GLOBAL_Control
0x140056e67  mov     ebx, 0C000000Dh
0x140056e6c  cmp     rcx, r14
0x140056e6f  jz      short loc_140056EBE
0x140056e71  cmp     byte ptr [rcx+29h], 2
0x140056e75  jb      short loc_140056E94
0x140056e77  mov     rcx, [rcx+18h]
0x140056e7b  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140056e82  mov     edx, 107h
0x140056e87  mov     [rsp+370h+var_350], rsi
0x140056e8c  mov     r9, rdi
0x140056e8f  call    WPP_SF_qq
0x140056e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140056e9b  cmp     rcx, r14
0x140056e9e  jz      short loc_140056EBE
0x140056ea0  cmp     byte ptr [rcx+29h], 4
0x140056ea4  jb      short loc_140056EBE
0x140056ea6  mov     rcx, [rcx+18h]
0x140056eaa  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140056eb1  mov     edx, 10Eh
0x140056eb6  mov     r9d, ebx
0x140056eb9  call    WPP_SF_d
0x140056ebe  mov     [rdi+30h], ebx
0x140056ec1  mov     eax, ebx
0x140056ec3  mov     rbx, [rsp+370h+arg_8]
0x140056ecb  add     rsp, 340h
0x140056ed2  pop     r15
0x140056ed4  pop     r14
0x140056ed6  pop     r13
0x140056ed8  pop     r12
0x140056eda  pop     rdi
0x140056edb  pop     rsi
0x140056edc  pop     rbp
0x140056edd  retn
```
