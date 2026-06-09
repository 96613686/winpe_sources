# CMJPEGFormatPlugin::GetDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,int,_USBVIDEO_DATARANGE * *)

- ea: `0x14000de60`
- end: `0x14000e61b`
- name: `?GetDataRangeFromDescriptor@CMJPEGFormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KHPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `1979`
- prototype: `__int64 __fastcall(CMJPEGFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x14000de60`
- `0x14003c810`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000dfb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e1c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dfb3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e1c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2a6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000df2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000df57`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e16a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e23e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000df2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000df57`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e16a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000e23e`
- `ks!KsAddItemToObjectBag` at `0x14000df9b`
- `ks!KsAddItemToObjectBag` at `0x14000e1ae`
- `ks!KsAddItemToObjectBag` at `0x14000e28d`
- `ks!KsAddItemToObjectBag` at `0x14000df9b`
- `ks!KsAddItemToObjectBag` at `0x14000e1ae`
- `ks!KsAddItemToObjectBag` at `0x14000e28d`

## pseudocode

```c
__int64 __fastcall CMJPEGFormatPlugin::GetDataRangeFromDescriptor(
        KSOBJECT_BAG *this,
        struct VIDEO_SPECIFIC *a2,
        struct VIDEO_SPECIFIC *a3,
        unsigned int a4,
        int a5,
        GUID **a6)
{
  __int64 v8; // r9
  unsigned int v9; // eax
  bool v11; // cf
  unsigned int v12; // r8d
  unsigned __int8 *v13; // rdi
  char v14; // r12
  unsigned int i; // ecx
  GUID *PoolWithTag; // rax
  GUID *v17; // rbx
  size_t v18; // r8
  NTSTATUS v19; // ebp
  size_t v21; // r8
  int v22; // ecx
  __int64 v23; // rcx
  unsigned int v24; // r8d
  int v25; // eax
  int v26; // ecx
  unsigned int v27; // ebp
  PVOID v28; // rax
  void *v29; // r15
  NTSTATUS v30; // r13d
  __int64 v31; // rdx
  unsigned int v32; // r8d
  int v33; // eax
  size_t v34; // r13
  PVOID v35; // rax
  void *v36; // rbp
  NTSTATUS v37; // r15d
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  PDEVICE_OBJECT v41; // rcx
  __int64 v42; // rdx
  unsigned int v43; // ecx
  int v44; // eax
  int v45; // ecx
  __int64 v46; // rdx
  __int64 v47; // rcx
  unsigned int v48; // r8d
  int v49; // edx
  unsigned int Data1; // ecx
  char v51; // al
  char v52; // al
  int v53; // ecx
  char v54; // al
  char v55; // al
  unsigned int v56; // eax
  __int64 v58; // [rsp+88h] [rbp+10h] BYREF
  struct VIDEO_SPECIFIC *v59; // [rsp+90h] [rbp+18h]
  unsigned int v60; // [rsp+98h] [rbp+20h] BYREF

  v59 = a3;
  v8 = *((unsigned __int8 *)a2 + 6);
  v9 = a4 >> 1;
  if ( a4 >> 1 )
  {
    v11 = v9 < (unsigned int)v8;
    v8 = v9;
    if ( !v11 )
      v8 = v9 + 1;
  }
  v12 = *((unsigned __int8 *)a2 + 4);
  if ( (unsigned int)v8 > v12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_427f7f479e5f364e8bc738df4327e74b_Traceguids, v8, v12);
    return 3221225485LL;
  }
  v13 = (unsigned __int8 *)a2 + *(unsigned __int8 *)a2;
  v14 = a4 & 1;
  for ( i = 1; i < (unsigned int)v8; v13 += *v13 )
    ++i;
  if ( v14 )
  {
    PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x1A0u, 0x56425355u);
    v17 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    {
      v18 = 416;
LABEL_17:
      memset(PoolWithTag, 0, v18);
    }
  }
  else
  {
    PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x188u, 0x56425355u);
    v17 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    {
      v18 = 392;
      goto LABEL_17;
    }
  }
  if ( v17 )
  {
    v19 = KsAddItemToObjectBag(this[2], v17, FreeMem);
    if ( v19 < 0 )
    {
      ExFreePoolWithTag(v17, 0x56425355u);
      return (unsigned int)v19;
    }
    v21 = 416;
    if ( !v14 )
      v21 = 392;
    memset(v17, 0, v21);
    BYTE1(v17[5].Data1) = 1;
    v22 = *(unsigned __int16 *)(v13 + 5) * *(unsigned __int16 *)(v13 + 7);
    v17[7] = GUID_73646976_0000_0010_8000_00aa00389b71;
    v17[8] = MEDIASUBTYPE_MJPG;
    *(_DWORD *)v17[6].Data4 = 3 * v22;
    if ( v14 )
    {
      v17[6].Data1 = 320;
      v17[9] = GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba;
      v17[11] = GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba;
    }
    else
    {
      v17[6].Data1 = 296;
      v17[9] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
      v17[11] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
    }
    v17[12].Data1 = 0;
    *(_DWORD *)&v17[12].Data2 = *(unsigned __int16 *)(v13 + 5);
    *(_DWORD *)v17[12].Data4 = *(unsigned __int16 *)(v13 + 7);
    *(_DWORD *)&v17[12].Data4[4] = *(unsigned __int16 *)(v13 + 5);
    v17[13].Data1 = *(unsigned __int16 *)(v13 + 7);
    *(_DWORD *)&v17[13].Data2 = *(unsigned __int16 *)(v13 + 5);
    *(_DWORD *)v17[13].Data4 = *(unsigned __int16 *)(v13 + 7);
    *(_DWORD *)&v17[13].Data4[4] = 1;
    v17[14].Data1 = 1;
    *(_DWORD *)&v17[14].Data2 = 1;
    *(_DWORD *)v17[14].Data4 = 1;
    *(_DWORD *)&v17[14].Data4[4] = *(unsigned __int16 *)(v13 + 5);
    v17[15].Data1 = *(unsigned __int16 *)(v13 + 7);
    *(_DWORD *)&v17[15].Data2 = *(unsigned __int16 *)(v13 + 5);
    *(_DWORD *)v17[15].Data4 = *(unsigned __int16 *)(v13 + 7);
    *(_DWORD *)&v17[15].Data4[4] = 1;
    v17[16].Data1 = 1;
    *(_DWORD *)v17[18].Data4 = *(_DWORD *)(v13 + 9);
    *(_DWORD *)&v17[18].Data4[4] = *(_DWORD *)(v13 + 13);
    v23 = v13[25];
    *(_QWORD *)v17[17].Data4 = *(unsigned int *)(v13 + 26);
    if ( (_BYTE)v23 )
    {
      v60 = v23;
      v58 = (unsigned int)(v23 - 1);
      v34 = 4 * v23;
      *(_QWORD *)&v17[18].Data1 = *(unsigned int *)&v13[4 * v58 + 26];
      v35 = ExAllocatePoolWithTag((POOL_TYPE)1536, 4 * v23, 0x56425355u);
      v36 = v35;
      if ( ExPoolZeroingNativelySupported )
      {
        if ( !v35 )
          return 3221225626LL;
      }
      else
      {
        if ( !v35 )
          return 3221225626LL;
        memset(v35, 0, v34);
      }
      v37 = KsAddItemToObjectBag(this[2], v36, FreeMem);
      if ( v37 < 0 )
      {
        ExFreePoolWithTag(v36, 0x56425355u);
        return (unsigned int)v37;
      }
      memmove(v36, v13 + 26, v34);
      v17[3].Data1 = v60;
      v38 = v58;
      *(_QWORD *)v17[2].Data4 = v36;
      v33 = *(_DWORD *)&v13[4 * v38 + 26];
LABEL_48:
      *(_DWORD *)&v17[3].Data2 = v33;
      v39 = *(_QWORD *)&v17[18].Data1;
      v40 = *(_QWORD *)v17[17].Data4;
      if ( v40 > v39 )
      {
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225485LL;
        v42 = 11;
LABEL_97:
        WPP_SF_(v41->AttachedDevice, v42, WPP_427f7f479e5f364e8bc738df4327e74b_Traceguids);
        return 3221225485LL;
      }
      if ( !v40 || !v39 || (v43 = *(_DWORD *)(v13 + 21)) == 0 )
      {
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225485LL;
        v42 = 12;
        goto LABEL_97;
      }
      v17[21].Data1 = 24 * *(unsigned __int16 *)(v13 + 7) * *(unsigned __int16 *)(v13 + 5) * (0x989680 / v43);
      *(_QWORD *)v17[21].Data4 = *(unsigned int *)(v13 + 21);
      if ( !v14 )
      {
        v17[22].Data1 = 40;
        *(_DWORD *)&v17[22].Data2 = *(unsigned __int16 *)(v13 + 5);
        *(_DWORD *)v17[22].Data4 = *(unsigned __int16 *)(v13 + 7);
        *(_DWORD *)&v17[22].Data4[4] = 1572865;
        v17[23].Data1 = 1196444237;
        *(_DWORD *)&v17[23].Data2 = 3 * *(unsigned __int16 *)(v13 + 7) * *(unsigned __int16 *)(v13 + 5);
LABEL_93:
        v17[4].Data4[4] = *((_BYTE *)a2 + 3);
        v17[4].Data4[5] = v13[3];
        *(_DWORD *)v17[3].Data4 = 1;
        *(_QWORD *)&v17[4].Data1 = 0;
        *(_DWORD *)v17[4].Data4 = 0;
        v17[4].Data4[7] = 1;
        v17[4].Data4[6] = ((_DWORD)this[3] & 0x10) == 0;
        *a6 = v17;
        return 0;
      }
      v44 = *((unsigned __int8 *)a2 + 7);
      *(_DWORD *)v17[22].Data4 = v44;
      v45 = *((unsigned __int8 *)a2 + 8);
      *(_DWORD *)&v17[22].Data4[4] = v45;
      if ( !(_BYTE)v44 || !(_BYTE)v45 )
      {
        v46 = *(unsigned __int16 *)(v13 + 7);
        v47 = *(unsigned __int16 *)(v13 + 5);
        v60 = 0;
        LODWORD(v58) = 0;
        ReduceToLowestTerms(v47, v46, &v60, &v58);
        v48 = v60;
        *(_DWORD *)&v17[22].Data4[4] = v58;
        *(_DWORD *)v17[22].Data4 = v48;
      }
      v49 = 2;
      *(_DWORD *)&v17[22].Data2 = *((_BYTE *)a2 + 10) == 1;
      if ( (*((_BYTE *)a2 + 9) & 1) == 0 )
        goto LABEL_78;
      v17[22].Data1 |= 1u;
      Data1 = v17[22].Data1;
      if ( (*((_BYTE *)a2 + 9) & 2) != 0 )
      {
        Data1 |= 2u;
        v17[22].Data1 = Data1;
      }
      if ( (*((_BYTE *)a2 + 9) & 4) != 0 )
      {
        Data1 |= 4u;
        v17[22].Data1 = Data1;
      }
      v51 = *((_BYTE *)a2 + 9) & 0x30;
      if ( v51 )
      {
        switch ( v51 )
        {
          case 16:
            Data1 |= 0x10u;
            break;
          case 32:
            Data1 |= 0x20u;
            break;
          case 48:
            Data1 |= 0x30u;
            break;
          default:
LABEL_72:
            v52 = *((_BYTE *)a2 + 9) & 0xC0;
            switch ( v52 )
            {
              case 0:
LABEL_77:
                v17[22].Data1 = Data1;
                break;
              case 0x40:
                Data1 |= 0x40u;
                goto LABEL_77;
              case 0x80:
                Data1 |= 0x80u;
                goto LABEL_77;
            }
LABEL_78:
            v53 = 2;
            if ( v59 )
            {
              v54 = *((_BYTE *)v59 + 3);
              switch ( v54 )
              {
                case 5:
                  v49 = 6;
                  break;
                case 4:
                  v49 = 5;
                  break;
                case 2:
                  v49 = 3;
                  break;
                case 3:
                  v49 = 4;
                  break;
              }
              v55 = *((_BYTE *)v59 + 5);
              if ( v55 == 1 )
              {
                v53 = 1;
              }
              else if ( v55 == 5 )
              {
                v53 = 3;
              }
            }
            LOBYTE(v17[23].Data1) = -127;
            v56 = v17[23].Data1 & 0xF80C11FF;
            *(_DWORD *)v17[23].Data4 = 40;
            v17[23].Data1 = v56 | (((v49 << 7) | v53 & 0xFFFFF01F) << 15) | 0xC1100;
            *(_DWORD *)&v17[23].Data4[4] = *(unsigned __int16 *)(v13 + 5);
            v17[24].Data1 = *(unsigned __int16 *)(v13 + 7);
            *(_DWORD *)&v17[24].Data2 = 1572865;
            *(_DWORD *)v17[24].Data4 = 1196444237;
            *(_DWORD *)&v17[24].Data4[4] = 3 * *(unsigned __int16 *)(v13 + 7) * *(unsigned __int16 *)(v13 + 5);
            goto LABEL_93;
        }
      }
      v17[22].Data1 = Data1;
      goto LABEL_72;
    }
    *(_QWORD *)&v17[18].Data1 = *(unsigned int *)(v13 + 30);
    v24 = *(_DWORD *)(v13 + 34);
    v25 = *(_DWORD *)(v13 + 30);
    v26 = *(_DWORD *)(v13 + 26);
    v60 = v24;
    if ( v24 )
    {
      v27 = (v25 - v26) / v24 + 1;
    }
    else
    {
      if ( v25 != v26 )
        return 3221225473LL;
      v27 = 1;
    }
    v28 = ExAllocatePoolWithTag((POOL_TYPE)1536, 4LL * v27, 0x56425355u);
    v29 = v28;
    if ( v28 )
    {
      if ( !ExPoolZeroingNativelySupported )
        memset(v28, 0, 4LL * v27);
      v30 = KsAddItemToObjectBag(this[2], v29, FreeMem);
      if ( v30 < 0 )
      {
        ExFreePoolWithTag(v29, 0x56425355u);
        return (unsigned int)v30;
      }
      v31 = 0;
      if ( v27 )
      {
        v32 = v60;
        do
        {
          *((_DWORD *)v29 + v31) = *(_DWORD *)(v13 + 26) + v31 * v32;
          v31 = (unsigned int)(v31 + 1);
        }
        while ( (unsigned int)v31 < v27 );
      }
      *(_QWORD *)v17[2].Data4 = v29;
      v17[3].Data1 = v27;
      v33 = *(_DWORD *)(v13 + 30);
      goto LABEL_48;
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14000de60  mov     [rsp+arg_10], r8
0x14000de65  mov     [rsp+arg_0], rcx
0x14000de6a  push    rbx
0x14000de6b  push    rbp
0x14000de6c  push    rsi
0x14000de6d  push    rdi
0x14000de6e  push    r12
0x14000de70  push    r13
0x14000de72  push    r14
0x14000de74  push    r15
0x14000de76  sub     rsp, 38h
0x14000de7a  mov     r12d, r9d
0x14000de7d  mov     rsi, rdx
0x14000de80  movzx   r9d, byte ptr [rdx+6]
0x14000de85  mov     eax, r12d
0x14000de88  shr     eax, 1
0x14000de8a  mov     rbp, rcx
0x14000de8d  jz      short loc_14000DE9B
0x14000de8f  cmp     eax, r9d
0x14000de92  mov     r9d, eax
0x14000de95  jb      short loc_14000DE9B
0x14000de97  lea     r9d, [rax+1]
0x14000de9b  movzx   r8d, byte ptr [rdx+4]
0x14000dea0  cmp     r9d, r8d
0x14000dea3  jbe     short loc_14000DEE9
0x14000dea5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000deac  lea     rax, WPP_GLOBAL_Control
0x14000deb3  cmp     rcx, rax
0x14000deb6  jz      loc_14000E5FD
0x14000debc  mov     edx, 2
0x14000dec1  cmp     [rcx+29h], dl
0x14000dec4  jb      loc_14000E5FD
0x14000deca  mov     rcx, [rcx+18h]
0x14000dece  mov     edx, 0Ah
0x14000ded3  mov     [rsp+78h+var_58], r8d
0x14000ded8  lea     r8, WPP_427f7f479e5f364e8bc738df4327e74b_Traceguids
0x14000dedf  call    WPP_SF_dd
0x14000dee4  jmp     loc_14000E5FD
0x14000dee9  movzx   edi, byte ptr [rdx]
0x14000deec  mov     r14d, 1
0x14000def2  add     rdi, rsi
0x14000def5  and     r12b, r14b
0x14000def8  mov     ecx, r14d
0x14000defb  cmp     r9d, r14d
0x14000defe  jbe     short loc_14000DF0E
0x14000df00  movzx   eax, byte ptr [rdi]
0x14000df03  add     ecx, r14d
0x14000df06  add     rdi, rax
0x14000df09  cmp     ecx, r9d
0x14000df0c  jb      short loc_14000DF00
0x14000df0e  xor     r13d, r13d
0x14000df11  mov     r14d, 56425355h
0x14000df17  mov     r15d, 600h
0x14000df1d  mov     r8d, r14d; Tag
0x14000df20  mov     ecx, r15d; PoolType
0x14000df23  test    r12b, r12b
0x14000df26  jz      short loc_14000DF52
0x14000df28  mov     edx, 1A0h; NumberOfBytes
0x14000df2d  call    cs:__imp_ExAllocatePoolWithTag
0x14000df34  nop     dword ptr [rax+rax+00h]
0x14000df39  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x14000df40  mov     rbx, rax
0x14000df43  jnz     short loc_14000DF84
0x14000df45  test    rax, rax
0x14000df48  jz      short loc_14000DF84
0x14000df4a  mov     r8d, 1A0h
0x14000df50  jmp     short loc_14000DF7A
0x14000df52  mov     edx, 188h; NumberOfBytes
0x14000df57  call    cs:__imp_ExAllocatePoolWithTag
0x14000df5e  nop     dword ptr [rax+rax+00h]
0x14000df63  cmp     cs:ExPoolZeroingNativelySupported, r13b
0x14000df6a  mov     rbx, rax
0x14000df6d  jnz     short loc_14000DF84
0x14000df6f  test    rax, rax
0x14000df72  jz      short loc_14000DF84
0x14000df74  mov     r8d, 188h; Size
0x14000df7a  xor     edx, edx; Val
0x14000df7c  mov     rcx, rax; void *
0x14000df7f  call    memset
0x14000df84  test    rbx, rbx
0x14000df87  jz      loc_14000E604
0x14000df8d  mov     rcx, [rbp+10h]; ObjectBag
0x14000df91  lea     r8, FreeMem; Free
0x14000df98  mov     rdx, rbx; Item
0x14000df9b  call    cs:__imp_KsAddItemToObjectBag
0x14000dfa2  nop     dword ptr [rax+rax+00h]
0x14000dfa7  mov     ebp, eax
0x14000dfa9  mov     rcx, rbx; void *
0x14000dfac  test    eax, eax
0x14000dfae  jns     short loc_14000DFC6
0x14000dfb0  mov     edx, r14d; Tag
0x14000dfb3  call    cs:__imp_ExFreePoolWithTag
0x14000dfba  nop     dword ptr [rax+rax+00h]
0x14000dfbf  mov     eax, ebp
0x14000dfc1  jmp     loc_14000E609
0x14000dfc6  xor     edx, edx; Val
0x14000dfc8  mov     r8d, 1A0h
0x14000dfce  test    r12b, r12b
0x14000dfd1  jnz     short loc_14000DFD9
0x14000dfd3  mov     r8d, 188h; Size
0x14000dfd9  call    memset
0x14000dfde  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14000dfe5  mov     r9d, 1
0x14000dfeb  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_MJPG.Data1
0x14000dff2  mov     [rbx+51h], r9b
0x14000dff6  movzx   eax, word ptr [rdi+5]
0x14000dffa  movzx   ecx, word ptr [rdi+7]
0x14000dffe  imul    ecx, eax
0x14000e001  movdqu  xmmword ptr [rbx+70h], xmm0
0x14000e006  movdqu  xmmword ptr [rbx+80h], xmm1
0x14000e00e  lea     eax, [rcx+rcx*2]
0x14000e011  mov     [rbx+68h], eax
0x14000e014  test    r12b, r12b
0x14000e017  jz      short loc_14000E039
0x14000e019  movups  xmm0, xmmword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1
0x14000e020  mov     dword ptr [rbx+60h], 140h
0x14000e027  movdqu  xmmword ptr [rbx+90h], xmm0
0x14000e02f  movdqu  xmmword ptr [rbx+0B0h], xmm0
0x14000e037  jmp     short loc_14000E05E
0x14000e039  mov     dword ptr [rbx+60h], 128h
0x14000e040  movups  xmm0, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14000e047  movdqu  xmmword ptr [rbx+90h], xmm0
0x14000e04f  movups  xmm1, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14000e056  movdqu  xmmword ptr [rbx+0B0h], xmm1
0x14000e05e  mov     [rbx+0C0h], r13d
0x14000e065  movzx   eax, word ptr [rdi+5]
0x14000e069  mov     [rbx+0C4h], eax
0x14000e06f  movzx   eax, word ptr [rdi+7]
0x14000e073  mov     [rbx+0C8h], eax
0x14000e079  movzx   eax, word ptr [rdi+5]
0x14000e07d  mov     [rbx+0CCh], eax
0x14000e083  movzx   eax, word ptr [rdi+7]
0x14000e087  mov     [rbx+0D0h], eax
0x14000e08d  movzx   eax, word ptr [rdi+5]
0x14000e091  mov     [rbx+0D4h], eax
0x14000e097  movzx   eax, word ptr [rdi+7]
0x14000e09b  mov     [rbx+0D8h], eax
0x14000e0a1  mov     [rbx+0DCh], r9d
0x14000e0a8  mov     [rbx+0E0h], r9d
0x14000e0af  mov     [rbx+0E4h], r9d
0x14000e0b6  mov     [rbx+0E8h], r9d
0x14000e0bd  movzx   eax, word ptr [rdi+5]
0x14000e0c1  mov     [rbx+0ECh], eax
0x14000e0c7  movzx   eax, word ptr [rdi+7]
0x14000e0cb  mov     [rbx+0F0h], eax
0x14000e0d1  movzx   eax, word ptr [rdi+5]
0x14000e0d5  mov     [rbx+0F4h], eax
0x14000e0db  movzx   eax, word ptr [rdi+7]
0x14000e0df  mov     [rbx+0F8h], eax
0x14000e0e5  mov     [rbx+0FCh], r9d
0x14000e0ec  mov     [rbx+100h], r9d
0x14000e0f3  mov     eax, [rdi+9]
0x14000e0f6  mov     [rbx+128h], eax
0x14000e0fc  mov     eax, [rdi+0Dh]
0x14000e0ff  mov     [rbx+12Ch], eax
0x14000e105  movzx   ecx, byte ptr [rdi+19h]
0x14000e109  mov     eax, [rdi+1Ah]
0x14000e10c  mov     [rbx+118h], rax
0x14000e113  test    cl, cl
0x14000e115  jnz     loc_14000E210
0x14000e11b  mov     eax, [rdi+1Eh]
0x14000e11e  mov     [rbx+120h], rax
0x14000e125  mov     r8d, [rdi+22h]
0x14000e129  mov     eax, [rdi+1Eh]
0x14000e12c  mov     ecx, [rdi+1Ah]
0x14000e12f  mov     [rsp+78h+arg_18], r8d
0x14000e137  test    r8d, r8d
0x14000e13a  jnz     short loc_14000E14F
0x14000e13c  cmp     eax, ecx
0x14000e13e  jz      short loc_14000E14A
0x14000e140  mov     eax, 0C0000001h
0x14000e145  jmp     loc_14000E609
0x14000e14a  mov     ebp, r9d
0x14000e14d  jmp     short loc_14000E15A
0x14000e14f  sub     eax, ecx
0x14000e151  xor     edx, edx
0x14000e153  div     r8d
0x14000e156  lea     ebp, [r9+rax]
0x14000e15a  mov     r13d, ebp
0x14000e15d  mov     r8d, r14d; Tag
0x14000e160  shl     r13, 2
0x14000e164  mov     ecx, r15d; PoolType
0x14000e167  mov     rdx, r13; NumberOfBytes
0x14000e16a  call    cs:__imp_ExAllocatePoolWithTag
0x14000e171  nop     dword ptr [rax+rax+00h]
0x14000e176  mov     r15, rax
0x14000e179  test    rax, rax
0x14000e17c  jz      loc_14000E604
0x14000e182  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000e189  jnz     short loc_14000E198
0x14000e18b  mov     r8, r13; Size
0x14000e18e  xor     edx, edx; Val
0x14000e190  mov     rcx, rax; void *
0x14000e193  call    memset
0x14000e198  mov     rcx, [rsp+78h+arg_0]
0x14000e1a0  lea     r8, FreeMem; Free
0x14000e1a7  mov     rdx, r15; Item
0x14000e1aa  mov     rcx, [rcx+10h]; ObjectBag
0x14000e1ae  call    cs:__imp_KsAddItemToObjectBag
0x14000e1b5  nop     dword ptr [rax+rax+00h]
0x14000e1ba  mov     r13d, eax
0x14000e1bd  test    eax, eax
0x14000e1bf  jns     short loc_14000E1DB
0x14000e1c1  mov     edx, r14d; Tag
0x14000e1c4  mov     rcx, r15; P
0x14000e1c7  call    cs:__imp_ExFreePoolWithTag
0x14000e1ce  nop     dword ptr [rax+rax+00h]
0x14000e1d3  mov     eax, r13d
0x14000e1d6  jmp     loc_14000E609
0x14000e1db  xor     edx, edx
0x14000e1dd  lea     r14d, [rdx+1]
0x14000e1e1  test    ebp, ebp
0x14000e1e3  jz      short loc_14000E201
0x14000e1e5  mov     r8d, [rsp+78h+arg_18]
0x14000e1ed  mov     ecx, r8d
0x14000e1f0  imul    ecx, edx
0x14000e1f3  add     ecx, [rdi+1Ah]
0x14000e1f6  mov     [r15+rdx*4], ecx
0x14000e1fa  add     edx, r14d
0x14000e1fd  cmp     edx, ebp
0x14000e1ff  jb      short loc_14000E1ED
0x14000e201  mov     [rbx+28h], r15
0x14000e205  mov     [rbx+30h], ebp
0x14000e208  mov     eax, [rdi+1Eh]
0x14000e20b  jmp     loc_14000E2E6
0x14000e210  mov     eax, ecx
0x14000e212  mov     [rsp+78h+arg_18], ecx
0x14000e219  dec     eax
0x14000e21b  mov     r13, rcx
0x14000e21e  mov     [rsp+78h+arg_8], rax
0x14000e226  mov     r8d, r14d; Tag
0x14000e229  shl     r13, 2
0x14000e22d  mov     ecx, r15d; PoolType
0x14000e230  mov     rdx, r13; NumberOfBytes
0x14000e233  mov     eax, [rdi+rax*4+1Ah]
0x14000e237  mov     [rbx+120h], rax
0x14000e23e  call    cs:__imp_ExAllocatePoolWithTag
0x14000e245  nop     dword ptr [rax+rax+00h]
0x14000e24a  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14000e251  mov     rbp, rax
0x14000e254  jnz     short loc_14000E26E
0x14000e256  test    rax, rax
0x14000e259  jz      loc_14000E604
0x14000e25f  mov     r8, r13; Size
0x14000e262  xor     edx, edx; Val
0x14000e264  mov     rcx, rax; void *
0x14000e267  call    memset
0x14000e26c  jmp     short loc_14000E277
0x14000e26e  test    rbp, rbp
0x14000e271  jz      loc_14000E604
0x14000e277  mov     rcx, [rsp+78h+arg_0]
0x14000e27f  lea     r8, FreeMem; Free
0x14000e286  mov     rdx, rbp; Item
0x14000e289  mov     rcx, [rcx+10h]; ObjectBag
0x14000e28d  call    cs:__imp_KsAddItemToObjectBag
0x14000e294  nop     dword ptr [rax+rax+00h]
0x14000e299  mov     r15d, eax
0x14000e29c  mov     rcx, rbp; void *
0x14000e29f  test    eax, eax
0x14000e2a1  jns     short loc_14000E2BA
0x14000e2a3  mov     edx, r14d; Tag
0x14000e2a6  call    cs:__imp_ExFreePoolWithTag
0x14000e2ad  nop     dword ptr [rax+rax+00h]
0x14000e2b2  mov     eax, r15d
0x14000e2b5  jmp     loc_14000E609
0x14000e2ba  mov     r8, r13; Size
0x14000e2bd  lea     rdx, [rdi+1Ah]; Src
0x14000e2c1  call    memmove
0x14000e2c6  mov     eax, [rsp+78h+arg_18]
0x14000e2cd  mov     r14d, 1
0x14000e2d3  mov     [rbx+30h], eax
0x14000e2d6  mov     rax, [rsp+78h+arg_8]
0x14000e2de  mov     [rbx+28h], rbp
0x14000e2e2  mov     eax, [rdi+rax*4+1Ah]
0x14000e2e6  mov     [rbx+34h], eax
0x14000e2e9  mov     rcx, [rbx+120h]
0x14000e2f0  mov     rax, [rbx+118h]
0x14000e2f7  cmp     rax, rcx
0x14000e2fa  jle     short loc_14000E32B
0x14000e2fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e303  lea     rax, WPP_GLOBAL_Control
0x14000e30a  cmp     rcx, rax
0x14000e30d  jz      loc_14000E5FD
0x14000e313  mov     edx, 2
0x14000e318  cmp     [rcx+29h], dl
0x14000e31b  jb      loc_14000E5FD
0x14000e321  mov     edx, 0Bh
0x14000e326  jmp     loc_14000E5ED
0x14000e32b  test    rax, rax
0x14000e32e  jz      loc_14000E5CB
0x14000e334  test    rcx, rcx
0x14000e337  jz      loc_14000E5CB
0x14000e33d  mov     ecx, [rdi+15h]
0x14000e340  test    ecx, ecx
0x14000e342  jz      loc_14000E5CB
0x14000e348  xor     edx, edx
0x14000e34a  mov     eax, 989680h
0x14000e34f  div     ecx
0x14000e351  movzx   ecx, word ptr [rdi+5]
0x14000e355  imul    eax, ecx
  ... truncated ...
```
