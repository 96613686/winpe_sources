# MSXU_Video_HDRSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140059380`
- end: `0x14005987e`
- name: `?MSXU_Video_HDRSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `1278`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b364`
- `0x14003b85c`
- `0x14003b8b8`
- `0x140055348`
- `0x140059380`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_Video_HDRSet(struct _IRP *a1, struct KSIDENTIFIER *a2, _QWORD *a3)
{
  NTSTATUS PinInfo; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  struct _IRP *v8; // rcx
  __int64 v9; // r8
  _DWORD *v10; // r9
  struct _KSFILTER *v11; // r12
  ULONG v12; // edx
  __int64 ClientState; // r9
  struct _HW_DEVICE_EXTENSION *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // r9
  __int64 v18; // r14
  unsigned int v19; // ebx
  unsigned __int8 v20; // r9
  unsigned __int8 v21; // al
  int v22; // eax
  int v24; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  struct _TOPOLOGY_NODE_INFO *v26; // [rsp+38h] [rbp-38h]
  struct _KSFILTER *v27; // [rsp+50h] [rbp-20h] BYREF
  struct _KSPIN *v28; // [rsp+58h] [rbp-18h] BYREF
  struct _HW_DEVICE_EXTENSION *v29; // [rsp+60h] [rbp-10h] BYREF
  struct _TOPOLOGY_NODE_INFO *v30; // [rsp+68h] [rbp-8h] BYREF
  unsigned __int8 v31; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int8 v32; // [rsp+B8h] [rbp+48h] BYREF

  v32 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 229, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  PinInfo = MSXUGetInfo(a1, &v27, &v32, &v31, &v30, &v29);
  if ( PinInfo >= 0 )
  {
    PinInfo = ValidateExtendedPropertyDataBufferLength(a1, a3, 40);
    if ( PinInfo < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_65;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_62;
      v7 = 231;
      goto LABEL_8;
    }
    v10 = a3 + 1;
    if ( *(_DWORD *)a3 == 1
      && *v10 >= (unsigned int)v9
      && (v11 = v27, v12 = *((_DWORD *)a3 + 1), v12 < v27->Descriptor->PinDescriptorsCount) )
    {
      PinInfo = GetPinInfo(v8, v12, &v28);
      if ( PinInfo < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 232, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
LABEL_20:
        PinInfo = -1073741436;
        goto LABEL_62;
      }
      if ( v28 )
      {
        ClientState = (unsigned int)v28->ClientState;
        if ( (_DWORD)ClientState )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              235,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              ClientState);
          goto LABEL_20;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            234,
            WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
            ClientState);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 233, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, 0);
      }
      v14 = v29;
      v15 = 136LL * *((unsigned int *)a3 + 1);
      v16 = *((_QWORD *)v29 + 93);
      if ( *(_DWORD *)(v15 + v16 + 120) || !*(_QWORD *)(v15 + v16 + 128) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_65;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 239, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      }
      else
      {
        v17 = a3[2];
        v18 = *(_DWORD *)(*((_QWORD *)v29 + 132) + 4LL) & 1 | 2LL;
        if ( (*(_DWORD *)(*((_QWORD *)v29 + 132) + 4LL) & 2) == 0 )
          v18 = *(_DWORD *)(*((_QWORD *)v29 + 132) + 4LL) & 1;
        if ( (v17 & v18) != v17 )
          goto LABEL_56;
        if ( v17 > 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 55, v9, v17);
LABEL_56:
          PinInfo = -1073741811;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_65;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 238);
          goto LABEL_59;
        }
        if ( (v17 & 3) != 0 )
        {
          if ( (a3[2] & 3LL) == 1 )
          {
            v19 = 1;
          }
          else if ( (a3[2] & 3LL) == 2 )
          {
            v19 = 2;
          }
          else
          {
            v19 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 14, v9, v17);
          }
        }
        else
        {
          v19 = 0;
        }
        LODWORD(v27) = v19;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 236, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v19);
        v20 = v32;
        v26 = v30;
        LODWORD(Size) = 4;
        v21 = v31;
        *((_QWORD *)v14 + 149) = v11;
        LOBYTE(v24) = v21;
        *((_DWORD *)v14 + 332) = 1;
        v22 = SubmitControlRequest(
                0x21u,
                1u,
                0xD00u,
                v20,
                v24,
                (unsigned __int8 *)&v27,
                Size,
                (__int64)v26,
                (__int64)v14);
        PinInfo = v22;
        if ( v22 >= 0 )
        {
          a1->IoStatus.Information = 40;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              237,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              (unsigned int)v22);
          *((_QWORD *)v14 + 149) = 0;
        }
      }
    }
    else
    {
      PinInfo = -1073741811;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_65;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          240,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          (unsigned int)*v10,
          *((_DWORD *)a3 + 1));
    }
LABEL_59:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_65;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_iiD(WPP_GLOBAL_Control->AttachedDevice, 241, v9, a3[2], a3[3], PinInfo);
    goto LABEL_62;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_65;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v7 = 230;
LABEL_8:
    WPP_SF_(v6->AttachedDevice, v7, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_62:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      242,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      (unsigned int)PinInfo);
LABEL_65:
  a1->IoStatus.Status = PinInfo;
  return (unsigned int)PinInfo;
}

```

## disassembly

```asm
0x140059380  mov     [rsp-28h+arg_8], rbx
0x140059385  mov     [rsp-28h+arg_10], rsi
0x14005938a  push    rbp
0x14005938b  push    rdi
0x14005938c  push    r12
0x14005938e  push    r14
0x140059390  push    r15
0x140059392  mov     rbp, rsp
0x140059395  sub     rsp, 70h
0x140059399  mov     rdi, r8
0x14005939c  mov     [rbp+arg_18], 0
0x1400593a0  mov     r15, rcx
0x1400593a3  mov     [rbp+arg_0], 0
0x1400593a7  mov     [rbp+var_8], 0
0x1400593af  mov     [rbp+var_10], 0
0x1400593b7  mov     [rbp+var_18], 0
0x1400593bf  mov     [rbp+var_20], 0
0x1400593c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400593ce  lea     r14, WPP_GLOBAL_Control
0x1400593d5  cmp     rcx, r14
0x1400593d8  jz      short loc_1400593F8
0x1400593da  cmp     byte ptr [rcx+29h], 4
0x1400593de  jb      short loc_1400593F8
0x1400593e0  mov     rcx, [rcx+18h]
0x1400593e4  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400593eb  mov     edx, 0E5h
0x1400593f0  mov     r9, r15
0x1400593f3  call    WPP_SF_q
0x1400593f8  lea     rax, [rbp+var_10]
0x1400593fc  mov     rcx, r15; struct _IRP *
0x1400593ff  mov     [rsp+70h+var_48], rax; struct _HW_DEVICE_EXTENSION **
0x140059404  lea     r9, [rbp+arg_0]; unsigned __int8 *
0x140059408  lea     rax, [rbp+var_8]
0x14005940c  lea     r8, [rbp+arg_18]; unsigned __int8 *
0x140059410  mov     [rsp+70h+var_50], rax; struct _TOPOLOGY_NODE_INFO **
0x140059415  lea     rdx, [rbp+var_20]; struct _KSFILTER **
0x140059419  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x14005941e  mov     ebx, eax
0x140059420  test    eax, eax
0x140059422  jns     short loc_140059458
0x140059424  mov     rcx, cs:WPP_GLOBAL_Control
0x14005942b  cmp     rcx, r14
0x14005942e  jz      loc_1400597B7
0x140059434  cmp     byte ptr [rcx+29h], 2
0x140059438  jb      loc_14005978D
0x14005943e  mov     edx, 0E6h
0x140059443  mov     rcx, [rcx+18h]
0x140059447  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005944e  call    WPP_SF_
0x140059453  jmp     loc_14005978D
0x140059458  xor     r9d, r9d
0x14005945b  mov     rdx, rdi
0x14005945e  mov     rcx, r15
0x140059461  lea     r8d, [r9+28h]
0x140059465  call    ValidateExtendedPropertyDataBufferLength
0x14005946a  mov     ebx, eax
0x14005946c  test    eax, eax
0x14005946e  jns     short loc_140059491
0x140059470  mov     rcx, cs:WPP_GLOBAL_Control
0x140059477  cmp     rcx, r14
0x14005947a  jz      loc_1400597B7
0x140059480  cmp     byte ptr [rcx+29h], 2
0x140059484  jb      loc_14005978D
0x14005948a  mov     edx, 0E7h
0x14005948f  jmp     short loc_140059443
0x140059491  cmp     dword ptr [rdi], 1
0x140059494  lea     r9, [rdi+8]
0x140059498  jnz     loc_14005983B
0x14005949e  cmp     [r9], r8d
0x1400594a1  jb      loc_14005983B
0x1400594a7  mov     r12, [rbp+var_20]
0x1400594ab  mov     edx, [rdi+4]; unsigned int
0x1400594ae  mov     rax, [r12]
0x1400594b2  cmp     edx, [rax+20h]
0x1400594b5  jnb     loc_14005983B
0x1400594bb  lea     r8, [rbp+var_18]; struct _KSPIN **
0x1400594bf  call    ?GetPinInfo@@YAJPEAU_IRP@@KPEAPEAU_KSPIN@@@Z; GetPinInfo(_IRP *,ulong,_KSPIN * *)
0x1400594c4  mov     ebx, eax
0x1400594c6  test    eax, eax
0x1400594c8  jns     short loc_1400594FB
0x1400594ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400594d1  cmp     rcx, r14
0x1400594d4  jz      short loc_1400594F1
0x1400594d6  cmp     byte ptr [rcx+29h], 2
0x1400594da  jb      short loc_1400594F1
0x1400594dc  mov     rcx, [rcx+18h]
0x1400594e0  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400594e7  mov     edx, 0E8h
0x1400594ec  call    WPP_SF_
0x1400594f1  mov     ebx, 0C0000184h
0x1400594f6  jmp     loc_14005978D
0x1400594fb  mov     rax, [rbp+var_18]
0x1400594ff  test    rax, rax
0x140059502  jnz     short loc_140059530
0x140059504  mov     rcx, cs:WPP_GLOBAL_Control
0x14005950b  cmp     rcx, r14
0x14005950e  jz      short loc_140059567
0x140059510  cmp     byte ptr [rcx+29h], 4
0x140059514  jb      short loc_140059567
0x140059516  mov     rcx, [rcx+18h]
0x14005951a  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059521  mov     edx, 0E9h
0x140059526  xor     r9d, r9d
0x140059529  call    WPP_SF_q
0x14005952e  jmp     short loc_140059567
0x140059530  mov     r9d, [rax+80h]
0x140059537  test    r9d, r9d
0x14005953a  jnz     loc_140059807
0x140059540  mov     rcx, cs:WPP_GLOBAL_Control
0x140059547  cmp     rcx, r14
0x14005954a  jz      short loc_140059567
0x14005954c  cmp     byte ptr [rcx+29h], 4
0x140059550  jb      short loc_140059567
0x140059552  mov     rcx, [rcx+18h]
0x140059556  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005955d  mov     edx, 0EAh
0x140059562  call    WPP_SF_d
0x140059567  mov     eax, [rdi+4]
0x14005956a  mov     rsi, [rbp+var_10]
0x14005956e  imul    rcx, rax, 88h
0x140059575  mov     rax, [rsi+2E8h]
0x14005957c  cmp     dword ptr [rcx+rax+78h], 0
0x140059581  jnz     loc_1400597D7
0x140059587  cmp     qword ptr [rcx+rax+80h], 0
0x140059590  jz      loc_1400597D7
0x140059596  mov     rax, [rsi+420h]
0x14005959d  mov     r9, [rdi+10h]
0x1400595a1  mov     ecx, [rax+4]
0x1400595a4  mov     eax, ecx
0x1400595a6  and     eax, 1
0x1400595a9  mov     r14d, eax
0x1400595ac  or      r14, 2
0x1400595b0  test    cl, 2
0x1400595b3  cmovz   r14, rax
0x1400595b7  mov     rax, r14
0x1400595ba  and     rax, r9
0x1400595bd  cmp     rax, r9
0x1400595c0  jnz     loc_140059720
0x1400595c6  mov     rax, r9
0x1400595c9  test    r9, r9
0x1400595cc  jz      short loc_14005960E
0x1400595ce  sub     rax, 1
0x1400595d2  jz      short loc_14005960E
0x1400595d4  cmp     rax, 1
0x1400595d8  jz      short loc_14005960E
0x1400595da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400595e1  lea     rsi, WPP_GLOBAL_Control
0x1400595e8  cmp     rcx, rsi
0x1400595eb  jz      loc_140059727
0x1400595f1  cmp     byte ptr [rcx+29h], 2
0x1400595f5  jb      loc_140059727
0x1400595fb  mov     rcx, [rcx+18h]
0x1400595ff  mov     edx, 37h ; '7'
0x140059604  call    WPP_SF_i
0x140059609  jmp     loc_140059727
0x14005960e  mov     rax, r9
0x140059611  and     eax, 3
0x140059614  jz      short loc_140059659
0x140059616  sub     rax, 1
0x14005961a  jz      short loc_140059652
0x14005961c  cmp     rax, 1
0x140059620  jz      short loc_14005964B
0x140059622  mov     rcx, cs:WPP_GLOBAL_Control
0x140059629  lea     r14, WPP_GLOBAL_Control
0x140059630  xor     ebx, ebx
0x140059632  cmp     rcx, r14
0x140059635  jz      short loc_140059662
0x140059637  cmp     byte ptr [rcx+29h], 2
0x14005963b  jb      short loc_140059662
0x14005963d  mov     rcx, [rcx+18h]
0x140059641  lea     edx, [rbx+0Eh]
0x140059644  call    WPP_SF_i
0x140059649  jmp     short loc_140059662
0x14005964b  mov     ebx, 2
0x140059650  jmp     short loc_14005965B
0x140059652  mov     ebx, 1
0x140059657  jmp     short loc_14005965B
0x140059659  xor     ebx, ebx
0x14005965b  lea     r14, WPP_GLOBAL_Control
0x140059662  mov     dword ptr [rbp+var_20], ebx
0x140059665  mov     rcx, cs:WPP_GLOBAL_Control
0x14005966c  cmp     rcx, r14
0x14005966f  jz      short loc_14005968F
0x140059671  cmp     byte ptr [rcx+29h], 4
0x140059675  jb      short loc_14005968F
0x140059677  mov     rcx, [rcx+18h]
0x14005967b  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059682  mov     edx, 0ECh
0x140059687  mov     r9d, ebx
0x14005968a  call    WPP_SF_d
0x14005968f  mov     rax, [rbp+var_8]
0x140059693  mov     r8d, 0D00h; int
0x140059699  mov     r9b, [rbp+arg_18]; int
0x14005969d  mov     dl, 1; int
0x14005969f  mov     [rsp+70h+var_30], rsi; __int64
0x1400596a4  mov     cl, 21h ; '!'; int
0x1400596a6  mov     [rsp+70h+var_38], rax; __int64
0x1400596ab  lea     rax, [rbp+var_20]
0x1400596af  mov     dword ptr [rsp+70h+Size], 4; Size
0x1400596b7  mov     [rsp+70h+var_48], rax; void *
0x1400596bc  mov     al, [rbp+arg_0]
0x1400596bf  mov     [rsi+4A8h], r12
0x1400596c6  mov     byte ptr [rsp+70h+var_50], al; int
0x1400596ca  mov     dword ptr [rsi+530h], 1
0x1400596d4  call    SubmitControlRequest
0x1400596d9  mov     ebx, eax
0x1400596db  test    eax, eax
0x1400596dd  jns     short loc_140059716
0x1400596df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400596e6  cmp     rcx, r14
0x1400596e9  jz      short loc_140059709
0x1400596eb  cmp     byte ptr [rcx+29h], 2
0x1400596ef  jb      short loc_140059709
0x1400596f1  mov     rcx, [rcx+18h]
0x1400596f5  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400596fc  mov     edx, 0EDh
0x140059701  mov     r9d, eax
0x140059704  call    WPP_SF_d
0x140059709  mov     qword ptr [rsi+4A8h], 0
0x140059714  jmp     short loc_14005975C
0x140059716  mov     qword ptr [r15+38h], 28h ; '('
0x14005971e  jmp     short loc_14005975C
0x140059720  lea     rsi, WPP_GLOBAL_Control
0x140059727  mov     rcx, cs:WPP_GLOBAL_Control
0x14005972e  mov     ebx, 0C000000Dh
0x140059733  cmp     rcx, rsi
0x140059736  jz      short loc_1400597B7
0x140059738  cmp     byte ptr [rcx+29h], 2
0x14005973c  jb      short loc_140059755
0x14005973e  mov     r9, [rdi+10h]
0x140059742  mov     edx, 0EEh
0x140059747  mov     rcx, [rcx+18h]
0x14005974b  mov     [rsp+70h+var_50], r14
0x140059750  call    WPP_SF_ii
0x140059755  lea     r14, WPP_GLOBAL_Control
0x14005975c  mov     rcx, cs:WPP_GLOBAL_Control
0x140059763  cmp     rcx, r14
0x140059766  jz      short loc_1400597B7
0x140059768  cmp     byte ptr [rcx+29h], 4
0x14005976c  jb      short loc_14005978D
0x14005976e  mov     rax, [rdi+18h]
0x140059772  mov     edx, 0F1h
0x140059777  mov     r9, [rdi+10h]
0x14005977b  mov     rcx, [rcx+18h]
0x14005977f  mov     dword ptr [rsp+70h+var_48], ebx
0x140059783  mov     [rsp+70h+var_50], rax
0x140059788  call    WPP_SF_iiD
0x14005978d  mov     rcx, cs:WPP_GLOBAL_Control
0x140059794  cmp     rcx, r14
0x140059797  jz      short loc_1400597B7
0x140059799  cmp     byte ptr [rcx+29h], 4
0x14005979d  jb      short loc_1400597B7
0x14005979f  mov     rcx, [rcx+18h]
0x1400597a3  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400597aa  mov     edx, 0F2h
0x1400597af  mov     r9d, ebx
0x1400597b2  call    WPP_SF_d
0x1400597b7  lea     r11, [rsp+70h+var_s0]
0x1400597bc  mov     [r15+30h], ebx
0x1400597c0  mov     rsi, [r11+40h]
0x1400597c4  mov     eax, ebx
0x1400597c6  mov     rbx, [r11+38h]
0x1400597ca  mov     rsp, r11
0x1400597cd  pop     r15
0x1400597cf  pop     r14
0x1400597d1  pop     r12
0x1400597d3  pop     rdi
0x1400597d4  pop     rbp
0x1400597d5  retn
0x1400597d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400597de  cmp     rcx, r14
0x1400597e1  jz      short loc_1400597B7
0x1400597e3  cmp     byte ptr [rcx+29h], 2
0x1400597e7  jb      loc_14005975C
0x1400597ed  mov     rcx, [rcx+18h]
0x1400597f1  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400597f8  mov     edx, 0EFh
0x1400597fd  call    WPP_SF_
0x140059802  jmp     loc_14005975C
0x140059807  mov     rcx, cs:WPP_GLOBAL_Control
0x14005980e  cmp     rcx, r14
0x140059811  jz      loc_1400594F1
0x140059817  cmp     byte ptr [rcx+29h], 4
0x14005981b  jb      loc_1400594F1
0x140059821  mov     rcx, [rcx+18h]
0x140059825  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005982c  mov     edx, 0EBh
0x140059831  call    WPP_SF_d
0x140059836  jmp     loc_1400594F1
0x14005983b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059842  mov     ebx, 0C000000Dh
0x140059847  cmp     rcx, r14
0x14005984a  jz      loc_1400597B7
0x140059850  cmp     byte ptr [rcx+29h], 2
0x140059854  jb      loc_14005975C
0x14005985a  mov     eax, [rdi+4]
0x14005985d  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140059864  mov     r9d, [r9]
0x140059867  mov     edx, 0F0h
0x14005986c  mov     rcx, [rcx+18h]
  ... truncated ...
```
