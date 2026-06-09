# MSXU_EVCompensationGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140055f40`
- end: `0x140056300`
- name: `?MSXU_EVCompensationGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `960`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b70c`
- `0x140040a30`
- `0x140055f40`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_EVCompensationGet(struct _IRP *a1, struct KSIDENTIFIER *a2, char *a3)
{
  NTSTATUS v5; // ebx
  int v6; // r8d
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r15
  char v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r14
  int v15; // eax
  char v16; // dl
  int v17; // r9d
  char v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r10
  int v25; // [rsp+20h] [rbp-59h]
  size_t Size; // [rsp+30h] [rbp-49h]
  __int64 v27; // [rsp+40h] [rbp-39h]
  unsigned __int8 v28; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int8 v29[7]; // [rsp+51h] [rbp-28h] BYREF
  struct _TOPOLOGY_NODE_INFO *v30; // [rsp+58h] [rbp-21h] BYREF
  __int128 v31; // [rsp+80h] [rbp+7h]
  __int64 v32; // [rsp+90h] [rbp+17h]
  _BYTE v33[11]; // [rsp+98h] [rbp+1Fh] BYREF

  v29[0] = 0;
  v28 = 0;
  v30 = 0;
  *(_QWORD *)v33 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 137, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, 0, v29, &v28, &v30, (struct _HW_DEVICE_EXTENSION **)v33);
  if ( v5 < 0 )
    goto LABEL_50;
  v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 56);
  if ( v5 >= 0 )
  {
    v9 = *(_QWORD *)(*(_QWORD *)v33 + 976LL);
    v10 = *(_BYTE *)(v9 + 33);
    v11 = v10 & 1 | 2LL;
    if ( (v10 & 2) == 0 )
      v11 = *(_BYTE *)(v9 + 33) & 1;
    v12 = v11 | 4;
    if ( (v10 & 4) == 0 )
      v12 = v11;
    v13 = v12 | 8;
    if ( (v10 & 8) == 0 )
      v13 = v12;
    v14 = v13 | 0x10;
    if ( (v10 & 0x10) == 0 )
      v14 = v13;
    if ( v14 )
    {
      if ( *(_DWORD *)a3 == 1 && *((_DWORD *)a3 + 2) >= 0x38u && *((_DWORD *)a3 + 1) == -1 )
      {
        v15 = *(_DWORD *)(v9 + 29);
        v27 = *(_QWORD *)v33;
        *(_QWORD *)v33 = *(_QWORD *)(v9 + 22);
        *(_DWORD *)&v33[7] = v15;
        LODWORD(Size) = 11;
        LOBYTE(v25) = v28;
        v5 = SubmitControlRequest(0xA1u, 0x81u, 0x300u, v29[0], v25, v33, Size, (__int64)v30, v27);
        if ( v5 >= 0 )
        {
          v16 = v33[0];
          if ( (v33[0] & 0x1F) != v33[0] )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 140, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v33[0]);
              v16 = v33[0];
            }
            v5 = -1073741436;
          }
          if ( v5 >= 0 )
          {
            v17 = *(_DWORD *)&v33[7];
            v18 = v16;
            *((_QWORD *)a3 + 4) = 0;
            v19 = v16 & 1;
            *(_DWORD *)a3 = 1;
            *((_DWORD *)a3 + 1) = -1;
            v20 = v19 | 2;
            *((_QWORD *)a3 + 1) = 56;
            v31 = 0;
            if ( (v18 & 2) == 0 )
              v20 = v19;
            v21 = v20 | 4;
            if ( (v18 & 4) == 0 )
              v21 = v20;
            v22 = v21 | 8;
            if ( (v18 & 8) == 0 )
              v22 = v21;
            v23 = v22 | 0x10;
            if ( (v18 & 0x10) == 0 )
              v23 = v22;
            *((_QWORD *)a3 + 2) = v23;
            v32 = 0;
            *(_OWORD *)(a3 + 40) = *((unsigned __int64 *)&v31 + 1);
            *((_DWORD *)a3 + 11) = v17;
            *((_QWORD *)a3 + 3) = v14 | 0x8000000000000000uLL;
            *((_DWORD *)a3 + 9) = *(_DWORD *)(v9 + 7);
            *((_DWORD *)a3 + 10) = *(_DWORD *)(v9 + 18);
            *((_DWORD *)a3 + 8) = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_diidd(WPP_GLOBAL_Control->AttachedDevice);
            a1->IoStatus.Information = 56;
            goto LABEL_50;
          }
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_53;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_50;
        v8 = 142;
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        v5 = -1073741811;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_53;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_50;
        v8 = 143;
      }
    }
    else
    {
      v5 = -1073741275;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_53;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_50;
      v8 = 139;
    }
    goto LABEL_9;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_53;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v8 = (unsigned int)(v6 + 82);
LABEL_9:
    WPP_SF_(v7->AttachedDevice, v8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_50:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v5);
LABEL_53:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140055f40  mov     [rsp-8+arg_8], rbx
0x140055f45  push    rbp
0x140055f46  push    rsi
0x140055f47  push    rdi
0x140055f48  push    r14
0x140055f4a  push    r15
0x140055f4c  lea     rbp, [rsp-37h]
0x140055f51  sub     rsp, 0B0h
0x140055f58  mov     rax, cs:__security_cookie
0x140055f5f  xor     rax, rsp
0x140055f62  mov     [rbp+57h+var_28], rax
0x140055f66  mov     rsi, r8
0x140055f69  mov     [rbp+57h+var_7F], 0
0x140055f6d  mov     rdi, rcx
0x140055f70  mov     [rbp+57h+var_80], 0
0x140055f74  mov     [rbp+57h+var_78], 0
0x140055f7c  mov     [rbp+57h+var_38], 0
0x140055f84  mov     rcx, cs:WPP_GLOBAL_Control
0x140055f8b  lea     rax, WPP_GLOBAL_Control
0x140055f92  cmp     rcx, rax
0x140055f95  jz      short loc_140055FB5
0x140055f97  cmp     byte ptr [rcx+29h], 2
0x140055f9b  jb      short loc_140055FB5
0x140055f9d  mov     rcx, [rcx+18h]
0x140055fa1  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140055fa8  mov     edx, 89h
0x140055fad  mov     r9, rdi
0x140055fb0  call    WPP_SF_q
0x140055fb5  lea     rax, [rbp+57h+var_38]
0x140055fb9  xor     edx, edx; struct _KSFILTER **
0x140055fbb  mov     [rsp+0D0h+var_A8], rax; struct _HW_DEVICE_EXTENSION **
0x140055fc0  lea     r9, [rbp+57h+var_80]; unsigned __int8 *
0x140055fc4  lea     rax, [rbp+57h+var_78]
0x140055fc8  mov     rcx, rdi; struct _IRP *
0x140055fcb  lea     r8, [rbp+57h+var_7F]; unsigned __int8 *
0x140055fcf  mov     [rsp+0D0h+var_B0], rax; struct _TOPOLOGY_NODE_INFO **
0x140055fd4  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x140055fd9  mov     ebx, eax
0x140055fdb  test    eax, eax
0x140055fdd  js      loc_1400562A6
0x140055fe3  xor     r9d, r9d
0x140055fe6  mov     rdx, rsi
0x140055fe9  mov     rcx, rdi
0x140055fec  lea     r8d, [r9+38h]
0x140055ff0  call    ValidateExtendedPropertyDataBufferLength
0x140055ff5  mov     ebx, eax
0x140055ff7  test    eax, eax
0x140055ff9  jns     short loc_140056035
0x140055ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x140056002  lea     rsi, WPP_GLOBAL_Control
0x140056009  cmp     rcx, rsi
0x14005600c  jz      loc_1400562D7
0x140056012  cmp     byte ptr [rcx+29h], 2
0x140056016  jb      loc_1400562AD
0x14005601c  lea     edx, [r8+52h]
0x140056020  mov     rcx, [rcx+18h]
0x140056024  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005602b  call    WPP_SF_
0x140056030  jmp     loc_1400562AD
0x140056035  mov     r9, [rbp+57h+var_38]
0x140056039  mov     r15, [r9+3D0h]
0x140056040  movzx   r8d, byte ptr [r15+21h]
0x140056045  mov     ecx, r8d
0x140056048  and     ecx, 1
0x14005604b  mov     edx, ecx
0x14005604d  or      rdx, 2
0x140056051  test    r8b, 2
0x140056055  cmovz   rdx, rcx
0x140056059  mov     rcx, rdx
0x14005605c  or      rcx, 4
0x140056060  test    r8b, 4
0x140056064  cmovz   rcx, rdx
0x140056068  mov     rdx, rcx
0x14005606b  or      rdx, 8
0x14005606f  test    r8b, 8
0x140056073  cmovz   rdx, rcx
0x140056077  mov     r14, rdx
0x14005607a  or      r14, 10h
0x14005607e  test    r8b, 10h
0x140056082  cmovz   r14, rdx
0x140056086  test    r14, r14
0x140056089  jnz     short loc_1400560BB
0x14005608b  mov     ebx, 0C0000225h
0x140056090  mov     rcx, cs:WPP_GLOBAL_Control
0x140056097  lea     rsi, WPP_GLOBAL_Control
0x14005609e  cmp     rcx, rsi
0x1400560a1  jz      loc_1400562D7
0x1400560a7  cmp     byte ptr [rcx+29h], 2
0x1400560ab  jb      loc_1400562AD
0x1400560b1  mov     edx, 8Bh
0x1400560b6  jmp     loc_140056020
0x1400560bb  cmp     dword ptr [rsi], 1
0x1400560be  jnz     loc_14005627E
0x1400560c4  cmp     dword ptr [rsi+8], 38h ; '8'
0x1400560c8  jb      loc_14005627E
0x1400560ce  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x1400560d2  jnz     loc_14005627E
0x1400560d8  mov     eax, [r15+1Dh]
0x1400560dc  mov     r8d, 300h; int
0x1400560e2  movsd   xmm0, qword ptr [r15+16h]
0x1400560e8  mov     dl, 81h; int
0x1400560ea  mov     [rsp+0D0h+var_90], r9; __int64
0x1400560ef  mov     cl, 0A1h; int
0x1400560f1  mov     r9b, [rbp+57h+var_7F]; int
0x1400560f5  movsd   [rbp+57h+var_38], xmm0
0x1400560fa  mov     dword ptr [rbp+57h+var_38+7], eax
0x1400560fd  mov     rax, [rbp+57h+var_78]
0x140056101  mov     [rsp+0D0h+var_98], rax; __int64
0x140056106  lea     rax, [rbp+57h+var_38]
0x14005610a  mov     dword ptr [rsp+0D0h+Size], 0Bh; Size
0x140056112  mov     [rsp+0D0h+var_A8], rax; void *
0x140056117  mov     al, [rbp+57h+var_80]
0x14005611a  mov     byte ptr [rsp+0D0h+var_B0], al; int
0x14005611e  call    SubmitControlRequest
0x140056123  mov     ebx, eax
0x140056125  test    eax, eax
0x140056127  js      loc_14005625B
0x14005612d  movzx   edx, byte ptr [rbp+57h+var_38]
0x140056131  mov     al, dl
0x140056133  and     al, 1Fh
0x140056135  cmp     al, dl
0x140056137  jz      short loc_140056172
0x140056139  mov     rcx, cs:WPP_GLOBAL_Control
0x140056140  lea     rax, WPP_GLOBAL_Control
0x140056147  cmp     rcx, rax
0x14005614a  jz      short loc_14005616D
0x14005614c  cmp     byte ptr [rcx+29h], 2
0x140056150  jb      short loc_14005616D
0x140056152  mov     rcx, [rcx+18h]
0x140056156  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005615d  mov     r9d, edx
0x140056160  mov     edx, 8Ch
0x140056165  call    WPP_SF_d
0x14005616a  mov     dl, byte ptr [rbp+57h+var_38]
0x14005616d  mov     ebx, 0C0000184h
0x140056172  test    ebx, ebx
0x140056174  js      loc_14005625B
0x14005617a  mov     r9d, dword ptr [rbp+57h+var_38+7]
0x14005617e  xorps   xmm0, xmm0
0x140056181  movzx   r8d, dl
0x140056185  mov     rax, 8000000000000000h
0x14005618f  movsd   qword ptr [rsi+20h], xmm0
0x140056194  mov     ecx, r8d
0x140056197  and     ecx, 1
0x14005619a  mov     dword ptr [rsi], 1
0x1400561a0  mov     edx, ecx
0x1400561a2  mov     dword ptr [rsi+4], 0FFFFFFFFh
0x1400561a9  or      rdx, 2
0x1400561ad  mov     qword ptr [rsi+8], 38h ; '8'
0x1400561b5  test    r8b, 2
0x1400561b9  movups  [rbp+57h+var_50], xmm0
0x1400561bd  cmovz   rdx, rcx
0x1400561c1  mov     rcx, rdx
0x1400561c4  or      rcx, 4
0x1400561c8  test    r8b, 4
0x1400561cc  cmovz   rcx, rdx
0x1400561d0  mov     rdx, rcx
0x1400561d3  or      rdx, 8
0x1400561d7  test    r8b, 8
0x1400561db  cmovz   rdx, rcx
0x1400561df  mov     r10, rdx
0x1400561e2  or      r10, 10h
0x1400561e6  test    r8b, 10h
0x1400561ea  cmovz   r10, rdx
0x1400561ee  xor     ecx, ecx
0x1400561f0  mov     [rsi+10h], r10
0x1400561f4  or      r14, rax
0x1400561f7  mov     [rbp+57h+var_40], rcx
0x1400561fb  movups  xmm0, [rbp+57h+var_50+8]
0x1400561ff  movdqu  xmmword ptr [rsi+28h], xmm0
0x140056204  mov     [rsi+2Ch], r9d
0x140056208  mov     [rsi+18h], r14
0x14005620c  mov     eax, [r15+7]
0x140056210  mov     [rsi+24h], eax
0x140056213  mov     edx, [r15+12h]
0x140056217  mov     [rsi+28h], edx
0x14005621a  mov     [rsi+20h], ecx
0x14005621d  mov     rcx, cs:WPP_GLOBAL_Control
0x140056224  lea     rsi, WPP_GLOBAL_Control
0x14005622b  cmp     rcx, rsi
0x14005622e  jz      short loc_140056251
0x140056230  cmp     byte ptr [rcx+29h], 4
0x140056234  jb      short loc_140056251
0x140056236  mov     rcx, [rcx+18h]
0x14005623a  mov     dword ptr [rsp+0D0h+var_98], edx
0x14005623e  mov     dword ptr [rsp+0D0h+Size], eax
0x140056242  mov     [rsp+0D0h+var_A8], r14
0x140056247  mov     [rsp+0D0h+var_B0], r10
0x14005624c  call    WPP_SF_diidd
0x140056251  mov     qword ptr [rdi+38h], 38h ; '8'
0x140056259  jmp     short loc_1400562AD
0x14005625b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056262  lea     rsi, WPP_GLOBAL_Control
0x140056269  cmp     rcx, rsi
0x14005626c  jz      short loc_1400562D7
0x14005626e  cmp     byte ptr [rcx+29h], 2
0x140056272  jb      short loc_1400562AD
0x140056274  mov     edx, 8Eh
0x140056279  jmp     loc_140056020
0x14005627e  mov     rcx, cs:WPP_GLOBAL_Control
0x140056285  lea     rsi, WPP_GLOBAL_Control
0x14005628c  mov     ebx, 0C000000Dh
0x140056291  cmp     rcx, rsi
0x140056294  jz      short loc_1400562D7
0x140056296  cmp     byte ptr [rcx+29h], 2
0x14005629a  jb      short loc_1400562AD
0x14005629c  mov     edx, 8Fh
0x1400562a1  jmp     loc_140056020
0x1400562a6  lea     rsi, WPP_GLOBAL_Control
0x1400562ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400562b4  cmp     rcx, rsi
0x1400562b7  jz      short loc_1400562D7
0x1400562b9  cmp     byte ptr [rcx+29h], 4
0x1400562bd  jb      short loc_1400562D7
0x1400562bf  mov     rcx, [rcx+18h]
0x1400562c3  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400562ca  mov     edx, 90h
0x1400562cf  mov     r9d, ebx
0x1400562d2  call    WPP_SF_d
0x1400562d7  mov     [rdi+30h], ebx
0x1400562da  mov     eax, ebx
0x1400562dc  mov     rcx, [rbp+57h+var_28]
0x1400562e0  xor     rcx, rsp; StackCookie
0x1400562e3  call    __security_check_cookie
0x1400562e8  mov     rbx, [rsp+0D0h+arg_8]
0x1400562f0  add     rsp, 0B0h
0x1400562f7  pop     r15
0x1400562f9  pop     r14
0x1400562fb  pop     rdi
0x1400562fc  pop     rsi
0x1400562fd  pop     rbp
0x1400562fe  retn
```
