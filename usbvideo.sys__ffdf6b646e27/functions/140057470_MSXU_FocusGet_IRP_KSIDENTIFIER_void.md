# MSXU_FocusGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140057470`
- end: `0x140057768`
- name: `?MSXU_FocusGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `760`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14000ef88`
- `0x14001b118`
- `0x14001b15c`
- `0x14003badc`
- `0x140040a30`
- `0x140057470`
- `0x14005bc78`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_FocusGet(struct _IRP *a1, struct KSIDENTIFIER *a2, char *a3)
{
  NTSTATUS v5; // ebx
  int v6; // r9d
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r14
  unsigned int v10; // ecx
  unsigned __int64 ExtPropFlags; // rax
  unsigned __int64 v12; // r15
  __int128 v13; // xmm0
  int v14; // r10d
  __int64 v15; // r11
  __int64 v16; // r8
  unsigned __int64 v17; // r10
  __int64 v18; // rdx
  __int64 v19; // rax
  int v21; // [rsp+20h] [rbp-79h]
  size_t Size; // [rsp+30h] [rbp-69h]
  struct _HW_DEVICE_EXTENSION *v23; // [rsp+40h] [rbp-59h]
  unsigned __int8 v24; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int8 v25[7]; // [rsp+51h] [rbp-48h] BYREF
  struct _TOPOLOGY_NODE_INFO *v26[9]; // [rsp+58h] [rbp-41h] BYREF
  struct _HW_DEVICE_EXTENSION *v27; // [rsp+A0h] [rbp+7h] BYREF
  int v28; // [rsp+A8h] [rbp+Fh]

  v25[0] = 0;
  v24 = 0;
  v26[0] = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, 0, v25, &v24, v26, &v27);
  if ( v5 < 0 )
    goto LABEL_29;
  v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 64);
  if ( v5 >= 0 )
  {
    if ( CExtendedVidProcSetting::isValid((CExtendedVidProcSetting *)a3) && *((_DWORD *)a3 + 1) == -1 )
    {
      v23 = v27;
      v9 = *((_QWORD *)v27 + 120);
      v27 = *(struct _HW_DEVICE_EXTENSION **)(v9 + 24);
      v28 = *(_DWORD *)(v9 + 32);
      LODWORD(Size) = 12;
      LOBYTE(v21) = v24;
      v5 = SubmitControlRequest(
             0xA1u,
             0x81u,
             0x100u,
             v25[0],
             v21,
             (unsigned __int8 *)&v27,
             Size,
             (__int64)v26[0],
             (__int64)v23);
      if ( v5 >= 0 )
      {
        v10 = *(_DWORD *)((char *)&v27 + 1);
        if ( (*(_DWORD *)((_BYTE *)&v27 + 1) & 0x1F0107) != *(_DWORD *)((char *)&v27 + 1) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              95,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              *(unsigned int *)((char *)&v27 + 1));
            v10 = *(_DWORD *)((char *)&v27 + 1);
          }
          v5 = -1073741436;
        }
        if ( v5 >= 0 )
        {
          ExtPropFlags = GetExtPropFlags(v10);
          *((_QWORD *)a3 + 2) = ExtPropFlags;
          memset(&v26[5], 0, 32);
          v12 = ExtPropFlags;
          LODWORD(ExtPropFlags) = v28;
          v13 = *(_OWORD *)&v26[6];
          *(_DWORD *)a3 = 1;
          *((_QWORD *)a3 + 4) = 0;
          *(_OWORD *)(a3 + 40) = v13;
          *((_DWORD *)a3 + 1) = -1;
          *((_QWORD *)a3 + 7) = *(_OWORD *)&_mm_unpackhi_pd((__m128d)0LL, (__m128d)0LL);
          *((_DWORD *)a3 + 12) = ExtPropFlags;
          *((_DWORD *)a3 + 2) = 64;
          *((_DWORD *)a3 + 3) = v14;
          *((_QWORD *)a3 + 3) = v15;
          v17 = GetExtPropFlags(*(_DWORD *)(v9 + 13)) | 0xC000000000000000uLL;
          *((_QWORD *)a3 + 3) = v17;
          v18 = *(int *)(v9 + 8);
          *((_DWORD *)a3 + 9) = v18;
          v19 = *(int *)(v9 + 20);
          *((_DWORD *)a3 + 10) = v19;
          *((_DWORD *)a3 + 11) = *(_DWORD *)(v9 + 44);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_iiiii(WPP_GLOBAL_Control->AttachedDevice, v18, v16, *((_QWORD *)a3 + 6), v12, v17, v18, v19);
          a1->IoStatus.Information = 64;
          goto LABEL_29;
        }
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_32;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_29;
      v8 = 97;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      v5 = -1073741811;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_32;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_29;
      v8 = 98;
    }
    goto LABEL_28;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_32;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v8 = (unsigned int)(v6 + 94);
LABEL_28:
    WPP_SF_(v7->AttachedDevice, v8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_29:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v5);
LABEL_32:
  a1->IoStatus.Status = v5;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140057470  mov     [rsp-8+arg_8], rbx
0x140057475  push    rbp
0x140057476  push    rsi
0x140057477  push    rdi
0x140057478  push    r12
0x14005747a  push    r13
0x14005747c  push    r14
0x14005747e  push    r15
0x140057480  lea     rbp, [rsp-27h]
0x140057485  sub     rsp, 0C0h
0x14005748c  mov     rax, cs:__security_cookie
0x140057493  xor     rax, rsp
0x140057496  mov     [rbp+57h+var_40], rax
0x14005749a  xor     r15d, r15d
0x14005749d  mov     rdi, r8
0x1400574a0  mov     [rbp+57h+var_9F], r15b
0x1400574a4  mov     rsi, rcx
0x1400574a7  mov     [rbp+57h+var_A0], r15b
0x1400574ab  mov     [rbp+57h+var_98], r15
0x1400574af  mov     [rbp+57h+var_50], r15
0x1400574b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400574ba  lea     r12, WPP_GLOBAL_Control
0x1400574c1  lea     r13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400574c8  mov     r14b, 2
0x1400574cb  cmp     rcx, r12
0x1400574ce  jz      short loc_1400574E9
0x1400574d0  cmp     [rcx+29h], r14b
0x1400574d4  jb      short loc_1400574E9
0x1400574d6  mov     rcx, [rcx+18h]
0x1400574da  lea     edx, [r15+5Dh]
0x1400574de  mov     r9, rsi
0x1400574e1  mov     r8, r13
0x1400574e4  call    WPP_SF_q
0x1400574e9  lea     rax, [rbp+57h+var_50]
0x1400574ed  xor     edx, edx; struct _KSFILTER **
0x1400574ef  mov     [rsp+0F0h+var_C8], rax; struct _HW_DEVICE_EXTENSION **
0x1400574f4  lea     r9, [rbp+57h+var_A0]; unsigned __int8 *
0x1400574f8  lea     rax, [rbp+57h+var_98]
0x1400574fc  mov     rcx, rsi; struct _IRP *
0x1400574ff  lea     r8, [rbp+57h+var_9F]; unsigned __int8 *
0x140057503  mov     [rsp+0F0h+var_D0], rax; struct _TOPOLOGY_NODE_INFO **
0x140057508  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x14005750d  mov     ebx, eax
0x14005750f  test    eax, eax
0x140057511  js      loc_140057715
0x140057517  xor     r9d, r9d
0x14005751a  mov     rdx, rdi
0x14005751d  mov     rcx, rsi
0x140057520  lea     r8d, [r9+40h]
0x140057524  call    ValidateExtendedPropertyDataBufferLength
0x140057529  mov     ebx, eax
0x14005752b  test    eax, eax
0x14005752d  jns     short loc_140057552
0x14005752f  mov     rcx, cs:WPP_GLOBAL_Control
0x140057536  cmp     rcx, r12
0x140057539  jz      loc_14005773B
0x14005753f  cmp     [rcx+29h], r14b
0x140057543  jb      loc_140057715
0x140057549  lea     edx, [r9+5Eh]
0x14005754d  jmp     loc_140057709
0x140057552  mov     rcx, rdi; this
0x140057555  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ; CExtendedVidProcSetting::isValid(void)
0x14005755a  test    al, al
0x14005755c  jz      loc_1400576ED
0x140057562  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x140057566  jnz     loc_1400576ED
0x14005756c  mov     rcx, [rbp+57h+var_50]
0x140057570  mov     r8d, 100h; int
0x140057576  mov     r9b, [rbp+57h+var_9F]; int
0x14005757a  mov     dl, 81h; int
0x14005757c  mov     [rsp+0F0h+var_B0], rcx; __int64
0x140057581  mov     r14, [rcx+3C0h]
0x140057588  mov     cl, 0A1h; int
0x14005758a  movsd   xmm0, qword ptr [r14+18h]
0x140057590  movsd   [rbp+57h+var_50], xmm0
0x140057595  mov     eax, [r14+20h]
0x140057599  mov     [rbp+57h+var_48], eax
0x14005759c  mov     rax, [rbp+57h+var_98]
0x1400575a0  mov     [rsp+0F0h+var_B8], rax; __int64
0x1400575a5  lea     rax, [rbp+57h+var_50]
0x1400575a9  mov     dword ptr [rsp+0F0h+Size], 0Ch; Size
0x1400575b1  mov     [rsp+0F0h+var_C8], rax; void *
0x1400575b6  mov     al, [rbp+57h+var_A0]
0x1400575b9  mov     byte ptr [rsp+0F0h+var_D0], al; int
0x1400575bd  call    SubmitControlRequest
0x1400575c2  mov     ebx, eax
0x1400575c4  test    eax, eax
0x1400575c6  js      loc_1400576D4
0x1400575cc  mov     ecx, dword ptr [rbp+57h+var_50+1]
0x1400575cf  mov     eax, ecx
0x1400575d1  and     eax, 1F0107h
0x1400575d6  cmp     eax, ecx
0x1400575d8  jz      short loc_140057608
0x1400575da  mov     rax, cs:WPP_GLOBAL_Control
0x1400575e1  cmp     rax, r12
0x1400575e4  jz      short loc_140057603
0x1400575e6  cmp     byte ptr [rax+29h], 2
0x1400575ea  jb      short loc_140057603
0x1400575ec  mov     r9d, ecx
0x1400575ef  mov     edx, 5Fh ; '_'
0x1400575f4  mov     rcx, [rax+18h]
0x1400575f8  mov     r8, r13
0x1400575fb  call    WPP_SF_d
0x140057600  mov     ecx, dword ptr [rbp+57h+var_50+1]; unsigned int
0x140057603  mov     ebx, 0C0000184h
0x140057608  test    ebx, ebx
0x14005760a  js      loc_1400576D4
0x140057610  mov     r10d, r15d
0x140057613  mov     r11, r15
0x140057616  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x14005761b  xorps   xmm1, xmm1
0x14005761e  mov     [rdi+10h], rax
0x140057622  movaps  [rbp+57h+var_70], xmm1
0x140057626  mov     r15, rax
0x140057629  mov     eax, [rbp+57h+var_48]
0x14005762c  movaps  [rbp+57h+var_60], xmm1
0x140057630  movups  xmm0, [rbp+57h+var_70+8]
0x140057634  mov     dword ptr [rdi], 1
0x14005763a  movsd   qword ptr [rdi+20h], xmm1
0x14005763f  movups  xmmword ptr [rdi+28h], xmm0
0x140057643  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x14005764a  unpckhpd xmm1, xmm1
0x14005764e  movsd   qword ptr [rdi+38h], xmm1
0x140057653  mov     [rdi+30h], eax
0x140057656  mov     dword ptr [rdi+8], 40h ; '@'
0x14005765d  mov     [rdi+0Ch], r10d
0x140057661  mov     [rdi+18h], r11
0x140057665  mov     ecx, [r14+0Dh]; unsigned int
0x140057669  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x14005766e  mov     r10, rax
0x140057671  mov     rax, 0C000000000000000h
0x14005767b  or      r10, rax
0x14005767e  mov     [rdi+18h], r10
0x140057682  movsxd  rdx, dword ptr [r14+8]
0x140057686  mov     [rdi+24h], edx
0x140057689  movsxd  rax, dword ptr [r14+14h]
0x14005768d  mov     [rdi+28h], eax
0x140057690  mov     ecx, [r14+2Ch]
0x140057694  mov     [rdi+2Ch], ecx
0x140057697  mov     rcx, cs:WPP_GLOBAL_Control
0x14005769e  cmp     rcx, r12
0x1400576a1  jz      short loc_1400576CA
0x1400576a3  cmp     byte ptr [rcx+29h], 4
0x1400576a7  jb      short loc_1400576CA
0x1400576a9  mov     r9, [rdi+30h]
0x1400576ad  mov     rcx, [rcx+18h]
0x1400576b1  mov     [rsp+0F0h+var_B8], rax
0x1400576b6  mov     [rsp+0F0h+Size], rdx
0x1400576bb  mov     [rsp+0F0h+var_C8], r10
0x1400576c0  mov     [rsp+0F0h+var_D0], r15
0x1400576c5  call    WPP_SF_iiiii
0x1400576ca  mov     qword ptr [rsi+38h], 40h ; '@'
0x1400576d2  jmp     short loc_140057715
0x1400576d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400576db  cmp     rcx, r12
0x1400576de  jz      short loc_14005773B
0x1400576e0  cmp     byte ptr [rcx+29h], 2
0x1400576e4  jb      short loc_140057715
0x1400576e6  mov     edx, 61h ; 'a'
0x1400576eb  jmp     short loc_140057709
0x1400576ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400576f4  mov     ebx, 0C000000Dh
0x1400576f9  cmp     rcx, r12
0x1400576fc  jz      short loc_14005773B
0x1400576fe  cmp     [rcx+29h], r14b
0x140057702  jb      short loc_140057715
0x140057704  mov     edx, 62h ; 'b'
0x140057709  mov     rcx, [rcx+18h]
0x14005770d  mov     r8, r13
0x140057710  call    WPP_SF_
0x140057715  mov     rcx, cs:WPP_GLOBAL_Control
0x14005771c  cmp     rcx, r12
0x14005771f  jz      short loc_14005773B
0x140057721  cmp     byte ptr [rcx+29h], 4
0x140057725  jb      short loc_14005773B
0x140057727  mov     rcx, [rcx+18h]
0x14005772b  mov     edx, 63h ; 'c'
0x140057730  mov     r9d, ebx
0x140057733  mov     r8, r13
0x140057736  call    WPP_SF_d
0x14005773b  mov     [rsi+30h], ebx
0x14005773e  mov     eax, ebx
0x140057740  mov     rcx, [rbp+57h+var_40]
0x140057744  xor     rcx, rsp; StackCookie
0x140057747  call    __security_check_cookie
0x14005774c  mov     rbx, [rsp+0F0h+arg_8]
0x140057754  add     rsp, 0C0h
0x14005775b  pop     r15
0x14005775d  pop     r14
0x14005775f  pop     r13
0x140057761  pop     r12
0x140057763  pop     rdi
0x140057764  pop     rsi
0x140057765  pop     rbp
0x140057766  retn
```
