# CH264FormatPlugin::GetDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,int,_USBVIDEO_DATARANGE * *)

- ea: `0x14003ecd0`
- end: `0x14003f4fa`
- name: `?GetDataRangeFromDescriptor@CH264FormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KHPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `2090`
- prototype: `__int64 __fastcall(CH264FormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140019cd4`
- `0x14001b118`
- `0x14001b3e4`
- `0x14003ecd0`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003edf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f1bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003edf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f1bc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003ed9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f15a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003ed9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f15a`
- `ks!KsAddItemToObjectBag` at `0x14003edda`
- `ks!KsAddItemToObjectBag` at `0x14003f1a1`
- `ks!KsAddItemToObjectBag` at `0x14003edda`
- `ks!KsAddItemToObjectBag` at `0x14003f1a1`

## pseudocode

```c
__int64 __fastcall CH264FormatPlugin::GetDataRangeFromDescriptor(
        KSOBJECT_BAG *this,
        struct VIDEO_SPECIFIC *a2,
        struct VIDEO_SPECIFIC *a3,
        unsigned int a4,
        int a5,
        GUID **a6)
{
  unsigned int FrameIndex; // r10d
  char v7; // bp
  bool v10; // cf
  unsigned int v11; // r8d
  unsigned int v12; // ecx
  unsigned __int8 *i; // rdi
  GUID *PoolWithTag; // rax
  GUID *v15; // rbx
  NTSTATUS v16; // r14d
  __int16 v18; // dx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  size_t v27; // r14
  unsigned int v28; // r13d
  PVOID v29; // rax
  void *v30; // rbp
  NTSTATUS v31; // r15d
  __int64 v32; // rcx
  __int64 v33; // rax
  __int16 v34; // ax
  __int16 v35; // cx
  unsigned __int16 v36; // ax
  unsigned __int16 v37; // cx
  __int64 v38; // [rsp+88h] [rbp+10h]

  FrameIndex = *((unsigned __int8 *)a2 + 5);
  v7 = a4;
  if ( *((_BYTE *)a2 + 7) )
  {
    LOBYTE(a3) = 1;
    FrameIndex = GetFrameIndex(*((unsigned __int8 *)a2 + 5), a4, a3);
  }
  else if ( a4 )
  {
    v10 = a4 < FrameIndex;
    FrameIndex = a4;
    if ( !v10 )
      FrameIndex = a4 + 1;
  }
  v11 = *((unsigned __int8 *)a2 + 4);
  if ( FrameIndex > v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_cb3bf0f71c183cb151c0892f7a1c1990_Traceguids,
        FrameIndex,
        v11);
    return 3221225485LL;
  }
  v12 = 1;
  for ( i = (unsigned __int8 *)a2 + *(unsigned __int8 *)a2; v12 < FrameIndex; i += *i )
    ++v12;
  PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x188u, 0x56425355u);
  v15 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  if ( !ExPoolZeroingNativelySupported )
    memset(PoolWithTag, 0, 0x188u);
  v16 = KsAddItemToObjectBag(this[2], v15, FreeMem);
  if ( v16 < 0 )
  {
    ExFreePoolWithTag(v15, 0x56425355u);
    return (unsigned int)v16;
  }
  memset(v15, 0, 0x188u);
  v15[6].Data1 = 296;
  v15[7] = GUID_73646976_0000_0010_8000_00aa00389b71;
  if ( *((_BYTE *)a2 + 10) )
  {
    v15[8].Data1 = -565772622;
    *(_DWORD *)&v15[8].Data2 = 1198738537;
    *(_DWORD *)v15[8].Data4 = -391937610;
    *(_DWORD *)&v15[8].Data4[4] = 1730468556;
  }
  else
  {
    v18 = *((_WORD *)i + 6);
    switch ( v18 )
    {
      case 0x5304:
      case 0x5604:
        v15[8].Data1 = 1321326275;
        *(_DWORD *)&v15[8].Data2 = 1161458909;
        *(_DWORD *)v15[8].Data4 = -1899956817;
        *(_DWORD *)&v15[8].Data4[4] = 1110166751;
        break;
      case 0x7600:
      case 0x8000:
        v15[8].Data1 = 273958170;
        *(_DWORD *)&v15[8].Data2 = 1296739040;
        *(_DWORD *)v15[8].Data4 = 1936717205;
        *(_DWORD *)&v15[8].Data4[4] = -1805135753;
        break;
      case 0x4240:
      case 0x4200:
      case 0x4D00:
      case 0x4F00:
      case 0x6400:
      case 0x640C:
      case 0x7A00:
      case 0x6E00:
      case 0x5800:
        if ( !*((_BYTE *)a2 + 7) || (v7 & 1) != 0 )
        {
          v15[8] = MEDIASUBTYPE_H264;
        }
        else
        {
          v15[8].Data1 = 1061221616;
          *(_DWORD *)&v15[8].Data2 = 1341675042;
          *(_DWORD *)v15[8].Data4 = 2057427126;
          *(_DWORD *)&v15[8].Data4[4] = 1592675160;
        }
        break;
      default:
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225485LL;
        v20 = *((unsigned __int16 *)i + 6);
        v21 = 11;
LABEL_82:
        WPP_SF_d(v19->AttachedDevice, v21, WPP_cb3bf0f71c183cb151c0892f7a1c1990_Traceguids, v20);
        return 3221225485LL;
    }
  }
  v22 = i[14];
  if ( (unsigned __int8)v22 > 0x33u || (v23 = 0xC0701C0703C00LL, !_bittest64(&v23, v22)) )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225485LL;
    v20 = i[14];
    v21 = 12;
    goto LABEL_82;
  }
  *(_DWORD *)&v15[10].Data2 = 1;
  v15[9] = GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c;
  v15[11] = GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c;
  *(_DWORD *)&v15[12].Data2 = *((unsigned __int16 *)i + 2);
  *(_DWORD *)v15[12].Data4 = *((unsigned __int16 *)i + 3);
  *(_DWORD *)&v15[12].Data4[4] = *((unsigned __int16 *)i + 2);
  v15[13].Data1 = *((unsigned __int16 *)i + 3);
  *(_DWORD *)&v15[13].Data2 = *((unsigned __int16 *)i + 2);
  *(_DWORD *)v15[13].Data4 = *((unsigned __int16 *)i + 3);
  *(_DWORD *)&v15[13].Data4[4] = 1;
  v15[14].Data1 = 1;
  *(_DWORD *)&v15[14].Data2 = 1;
  *(_DWORD *)v15[14].Data4 = 1;
  *(_DWORD *)&v15[14].Data4[4] = *((unsigned __int16 *)i + 2);
  v15[15].Data1 = *((unsigned __int16 *)i + 3);
  *(_DWORD *)&v15[15].Data2 = *((unsigned __int16 *)i + 2);
  *(_DWORD *)v15[15].Data4 = *((unsigned __int16 *)i + 3);
  *(_DWORD *)&v15[15].Data4[4] = 1;
  v15[16].Data1 = 1;
  *(_DWORD *)v15[18].Data4 = *(_DWORD *)(i + 31);
  *(_DWORD *)&v15[18].Data4[4] = *(_DWORD *)(i + 35);
  v24 = i[43];
  if ( !(_BYTE)v24 )
  {
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 3221225485LL;
    v26 = 13;
    goto LABEL_78;
  }
  v27 = 4 * v24;
  if ( 4 * v24 + 44 != *i )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_cb3bf0f71c183cb151c0892f7a1c1990_Traceguids);
    return 3221225485LL;
  }
  v28 = i[43];
  *(_QWORD *)v15[17].Data4 = *((unsigned int *)i + 11);
  v38 = (unsigned int)(v24 - 1);
  *(_QWORD *)&v15[18].Data1 = *(unsigned int *)&i[4 * v38 + 44];
  v29 = ExAllocatePoolWithTag((POOL_TYPE)1536, 4 * v24, 0x56425355u);
  v30 = v29;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( v29 )
    {
LABEL_55:
      v31 = KsAddItemToObjectBag(this[2], v30, FreeMem);
      if ( v31 < 0 )
      {
        ExFreePoolWithTag(v30, 0x56425355u);
        return (unsigned int)v31;
      }
      memmove(v30, i + 44, v27);
      *(_QWORD *)v15[2].Data4 = v30;
      v15[3].Data1 = v28;
      *(_DWORD *)&v15[3].Data2 = *(_DWORD *)&i[4 * v38 + 44];
      v32 = *(_QWORD *)&v15[18].Data1;
      v33 = *(_QWORD *)v15[17].Data4;
      if ( v33 <= v32 )
      {
        if ( v33 && v32 && *(_DWORD *)(i + 39) )
        {
          LOBYTE(v15[21].Data2) = *((_BYTE *)a2 + 6);
          HIBYTE(v15[21].Data2) = *((_BYTE *)a2 + 7);
          LOBYTE(v15[21].Data3) = *((_BYTE *)a2 + 8);
          HIBYTE(v15[21].Data3) = *((_BYTE *)a2 + 9);
          v15[21].Data4[0] = *((_BYTE *)a2 + 10);
          v15[21].Data4[1] = *((_BYTE *)a2 + 11);
          *(_WORD *)&v15[21].Data4[2] = *((_WORD *)a2 + 6);
          *(_WORD *)&v15[21].Data4[4] = *((_WORD *)a2 + 7);
          *(_WORD *)&v15[21].Data4[6] = *((_WORD *)a2 + 8);
          LOWORD(v15[22].Data1) = *((_WORD *)a2 + 9);
          HIWORD(v15[22].Data1) = *((_WORD *)a2 + 10);
          v15[22].Data2 = *((_WORD *)a2 + 11);
          v15[22].Data3 = *((_WORD *)a2 + 12);
          *(_WORD *)v15[22].Data4 = *((_WORD *)a2 + 13);
          *(_WORD *)&v15[22].Data4[2] = *((_WORD *)a2 + 14);
          *(_WORD *)&v15[22].Data4[4] = *((_WORD *)a2 + 15);
          *(_WORD *)&v15[22].Data4[6] = *((_WORD *)a2 + 16);
          LOWORD(v15[23].Data1) = *((_WORD *)a2 + 17);
          HIWORD(v15[23].Data1) = *((_WORD *)a2 + 18);
          v15[23].Data2 = *((_WORD *)a2 + 19);
          v15[23].Data3 = *((_WORD *)a2 + 20);
          *(_WORD *)v15[23].Data4 = *((_WORD *)a2 + 21);
          *(_WORD *)&v15[23].Data4[2] = *((_WORD *)a2 + 22);
          *(_WORD *)&v15[23].Data4[4] = *((_WORD *)a2 + 23);
          *(_WORD *)&v15[23].Data4[6] = *((_WORD *)a2 + 24);
          LOWORD(v15[24].Data1) = *((_WORD *)a2 + 25);
          v34 = *((_WORD *)i + 2);
          LOWORD(v15[19].Data1) = v34;
          v35 = *((_WORD *)i + 3);
          HIWORD(v15[19].Data1) = v35;
          if ( v34 && v35 )
          {
            v36 = *((_WORD *)i + 4);
            v15[19].Data2 = v36;
            v37 = *((_WORD *)i + 5);
            v15[19].Data3 = v37;
            if ( v36 && v37 )
            {
              *(_WORD *)v15[19].Data4 = *((_WORD *)i + 6);
              v15[19].Data4[2] = i[14];
              *(_WORD *)&v15[19].Data4[4] = *(_WORD *)(i + 15);
              v15[20].Data1 = *(_DWORD *)(i + 17);
              v15[20].Data2 = *(_WORD *)(i + 21);
              *(_DWORD *)v15[20].Data4 = *(_DWORD *)(i + 23);
              *(_DWORD *)&v15[20].Data4[4] = *(_DWORD *)(i + 27);
              v15[21].Data1 = *(_DWORD *)(i + 39);
              v15[4].Data4[4] = *((_BYTE *)a2 + 3);
              v15[4].Data4[5] = i[3];
              *(_DWORD *)v15[3].Data4 = 1;
              *(_QWORD *)&v15[4].Data1 = 0;
              *(_DWORD *)v15[4].Data4 = 0;
              *(_WORD *)&v15[4].Data4[6] = 256;
              BYTE1(v15[5].Data1) = 0;
              *a6 = v15;
              return 0;
            }
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              return 3221225485LL;
            v26 = 18;
          }
          else
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              return 3221225485LL;
            v26 = 17;
          }
        }
        else
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            return 3221225485LL;
          v26 = 16;
        }
      }
      else
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225485LL;
        v26 = 15;
      }
LABEL_78:
      WPP_SF_(v25->AttachedDevice, v26, WPP_cb3bf0f71c183cb151c0892f7a1c1990_Traceguids);
      return 3221225485LL;
    }
  }
  else if ( v29 )
  {
    memset(v29, 0, v27);
    goto LABEL_55;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14003ecd0  push    rbx
0x14003ecd2  push    rbp
0x14003ecd3  push    rsi
0x14003ecd4  push    rdi
0x14003ecd5  push    r12
0x14003ecd7  push    r13
0x14003ecd9  push    r14
0x14003ecdb  push    r15
0x14003ecdd  sub     rsp, 38h
0x14003ece1  movzx   r10d, byte ptr [rdx+5]
0x14003ece6  xor     r12d, r12d
0x14003ece9  mov     ebp, r9d
0x14003ecec  mov     rsi, rdx
0x14003ecef  mov     r15, rcx
0x14003ecf2  mov     r13d, 1
0x14003ecf8  cmp     [rdx+7], r12b
0x14003ecfc  jz      short loc_14003ED11
0x14003ecfe  mov     r8b, r13b
0x14003ed01  mov     edx, r9d
0x14003ed04  mov     ecx, r10d
0x14003ed07  call    GetFrameIndex
0x14003ed0c  mov     r10d, eax
0x14003ed0f  jmp     short loc_14003ED21
0x14003ed11  test    ebp, ebp
0x14003ed13  jz      short loc_14003ED21
0x14003ed15  cmp     ebp, r10d
0x14003ed18  mov     r10d, ebp
0x14003ed1b  jb      short loc_14003ED21
0x14003ed1d  lea     r10d, [r9+1]
0x14003ed21  movzx   r8d, byte ptr [rsi+4]
0x14003ed26  cmp     r10d, r8d
0x14003ed29  jbe     short loc_14003ED6E
0x14003ed2b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ed32  lea     rax, WPP_GLOBAL_Control
0x14003ed39  cmp     rcx, rax
0x14003ed3c  jz      loc_14003F4DC
0x14003ed42  cmp     byte ptr [rcx+29h], 2
0x14003ed46  jb      loc_14003F4DC
0x14003ed4c  mov     rcx, [rcx+18h]
0x14003ed50  mov     edx, 0Ah
0x14003ed55  mov     [rsp+78h+var_58], r8d
0x14003ed5a  mov     r9d, r10d
0x14003ed5d  lea     r8, WPP_cb3bf0f71c183cb151c0892f7a1c1990_Traceguids
0x14003ed64  call    WPP_SF_dd
0x14003ed69  jmp     loc_14003F4DC
0x14003ed6e  movzx   edi, byte ptr [rsi]
0x14003ed71  mov     ecx, r13d
0x14003ed74  add     rdi, rsi
0x14003ed77  cmp     r10d, r13d
0x14003ed7a  jbe     short loc_14003ED8A
0x14003ed7c  movzx   eax, byte ptr [rdi]
0x14003ed7f  add     ecx, r13d
0x14003ed82  add     rdi, rax
0x14003ed85  cmp     ecx, r10d
0x14003ed88  jb      short loc_14003ED7C
0x14003ed8a  mov     r14d, 188h
0x14003ed90  mov     r8d, 56425355h; Tag
0x14003ed96  mov     edx, r14d; NumberOfBytes
0x14003ed99  mov     ecx, 600h; PoolType
0x14003ed9e  call    cs:__imp_ExAllocatePoolWithTag
0x14003eda5  nop     dword ptr [rax+rax+00h]
0x14003edaa  mov     rbx, rax
0x14003edad  test    rax, rax
0x14003edb0  jz      loc_14003F4E3
0x14003edb6  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x14003edbd  jnz     short loc_14003EDCC
0x14003edbf  mov     r8d, r14d; Size
0x14003edc2  xor     edx, edx; Val
0x14003edc4  mov     rcx, rax; void *
0x14003edc7  call    memset
0x14003edcc  mov     rcx, [r15+10h]; ObjectBag
0x14003edd0  lea     r8, FreeMem; Free
0x14003edd7  mov     rdx, rbx; Item
0x14003edda  call    cs:__imp_KsAddItemToObjectBag
0x14003ede1  nop     dword ptr [rax+rax+00h]
0x14003ede6  mov     r14d, eax
0x14003ede9  mov     rcx, rbx; void *
0x14003edec  test    eax, eax
0x14003edee  jns     short loc_14003EE09
0x14003edf0  mov     edx, 56425355h; Tag
0x14003edf5  call    cs:__imp_ExFreePoolWithTag
0x14003edfc  nop     dword ptr [rax+rax+00h]
0x14003ee01  mov     eax, r14d
0x14003ee04  jmp     loc_14003F4E8
0x14003ee09  xor     edx, edx; Val
0x14003ee0b  mov     r8d, 188h; Size
0x14003ee11  call    memset
0x14003ee16  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14003ee1d  mov     dword ptr [rbx+60h], 128h
0x14003ee24  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003ee29  cmp     [rsi+0Ah], r12b
0x14003ee2d  jz      short loc_14003EE5C
0x14003ee2f  mov     dword ptr [rbx+80h], 0DE46FEB2h
0x14003ee39  mov     dword ptr [rbx+84h], 47734C69h
0x14003ee43  mov     dword ptr [rbx+88h], 0E8A381B6h
0x14003ee4d  mov     dword ptr [rbx+8Ch], 6724DACCh
0x14003ee57  jmp     loc_14003EFB8
0x14003ee5c  movzx   edx, word ptr [rdi+0Ch]
0x14003ee60  mov     eax, 5304h
0x14003ee65  cmp     dx, ax
0x14003ee68  jz      loc_14003EF90
0x14003ee6e  mov     eax, 5604h
0x14003ee73  cmp     dx, ax
0x14003ee76  jz      loc_14003EF90
0x14003ee7c  mov     eax, 7600h
0x14003ee81  cmp     dx, ax
0x14003ee84  jz      loc_14003EF66
0x14003ee8a  mov     eax, 8000h
0x14003ee8f  cmp     dx, ax
0x14003ee92  jz      loc_14003EF66
0x14003ee98  mov     eax, 4240h
0x14003ee9d  cmp     dx, ax
0x14003eea0  jz      short loc_14003EF20
0x14003eea2  mov     eax, 4200h
0x14003eea7  cmp     dx, ax
0x14003eeaa  jz      short loc_14003EF20
0x14003eeac  mov     eax, 4D00h
0x14003eeb1  cmp     dx, ax
0x14003eeb4  jz      short loc_14003EF20
0x14003eeb6  mov     eax, 4F00h
0x14003eebb  cmp     dx, ax
0x14003eebe  jz      short loc_14003EF20
0x14003eec0  mov     eax, 6400h
0x14003eec5  cmp     dx, ax
0x14003eec8  jz      short loc_14003EF20
0x14003eeca  mov     eax, 640Ch
0x14003eecf  cmp     dx, ax
0x14003eed2  jz      short loc_14003EF20
0x14003eed4  mov     eax, 7A00h
0x14003eed9  cmp     dx, ax
0x14003eedc  jz      short loc_14003EF20
0x14003eede  mov     eax, 6E00h
0x14003eee3  cmp     dx, ax
0x14003eee6  jz      short loc_14003EF20
0x14003eee8  mov     eax, 5800h
0x14003eeed  cmp     dx, ax
0x14003eef0  jz      short loc_14003EF20
0x14003eef2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003eef9  lea     rax, WPP_GLOBAL_Control
0x14003ef00  cmp     rcx, rax
0x14003ef03  jz      loc_14003F4DC
0x14003ef09  cmp     byte ptr [rcx+29h], 2
0x14003ef0d  jb      loc_14003F4DC
0x14003ef13  mov     r9d, edx
0x14003ef16  mov     edx, 0Bh
0x14003ef1b  jmp     loc_14003F4CC
0x14003ef20  cmp     [rsi+7], r12b
0x14003ef24  jz      short loc_14003EF55
0x14003ef26  test    r13b, bpl
0x14003ef29  jnz     short loc_14003EF55
0x14003ef2b  mov     dword ptr [rbx+80h], 3F40F4F0h
0x14003ef35  mov     dword ptr [rbx+84h], 4FF85622h
0x14003ef3f  mov     dword ptr [rbx+88h], 7AA1D8B6h
0x14003ef49  mov     dword ptr [rbx+8Ch], 5EEE4B58h
0x14003ef53  jmp     short loc_14003EFB8
0x14003ef55  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_H264.Data1
0x14003ef5c  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003ef64  jmp     short loc_14003EFB8
0x14003ef66  mov     dword ptr [rbx+80h], 1054451Ah
0x14003ef70  mov     dword ptr [rbx+84h], 4D4AAAE0h
0x14003ef7a  mov     dword ptr [rbx+88h], 736FF595h
0x14003ef84  mov     dword ptr [rbx+8Ch], 9467D077h
0x14003ef8e  jmp     short loc_14003EFB8
0x14003ef90  mov     dword ptr [rbx+80h], 4EC1D6C3h
0x14003ef9a  mov     dword ptr [rbx+84h], 453A74DDh
0x14003efa4  mov     dword ptr [rbx+88h], 8EC0F5AFh
0x14003efae  mov     dword ptr [rbx+8Ch], 422BCCDFh
0x14003efb8  movzx   edx, byte ptr [rdi+0Eh]
0x14003efbc  cmp     dl, 33h ; '3'
0x14003efbf  ja      loc_14003F4AB
0x14003efc5  mov     rcx, 0C0701C0703C00h
0x14003efcf  bt      rcx, rdx
0x14003efd3  jnb     loc_14003F4AB
0x14003efd9  movups  xmm0, xmmword ptr cs:_GUID_2017be05_6629_4248_aaed_7e1a47bc9b9c.Data1
0x14003efe0  mov     [rbx+0A4h], r13d
0x14003efe7  movdqu  xmmword ptr [rbx+90h], xmm0
0x14003efef  movdqu  xmmword ptr [rbx+0B0h], xmm0
0x14003eff7  movzx   eax, word ptr [rdi+4]
0x14003effb  mov     [rbx+0C4h], eax
0x14003f001  movzx   eax, word ptr [rdi+6]
0x14003f005  mov     [rbx+0C8h], eax
0x14003f00b  movzx   eax, word ptr [rdi+4]
0x14003f00f  mov     [rbx+0CCh], eax
0x14003f015  movzx   eax, word ptr [rdi+6]
0x14003f019  mov     [rbx+0D0h], eax
0x14003f01f  movzx   eax, word ptr [rdi+4]
0x14003f023  mov     [rbx+0D4h], eax
0x14003f029  movzx   eax, word ptr [rdi+6]
0x14003f02d  mov     [rbx+0D8h], eax
0x14003f033  mov     [rbx+0DCh], r13d
0x14003f03a  mov     [rbx+0E0h], r13d
0x14003f041  mov     [rbx+0E4h], r13d
0x14003f048  mov     [rbx+0E8h], r13d
0x14003f04f  movzx   eax, word ptr [rdi+4]
0x14003f053  mov     [rbx+0ECh], eax
0x14003f059  movzx   eax, word ptr [rdi+6]
0x14003f05d  mov     [rbx+0F0h], eax
0x14003f063  movzx   eax, word ptr [rdi+4]
0x14003f067  mov     [rbx+0F4h], eax
0x14003f06d  movzx   eax, word ptr [rdi+6]
0x14003f071  mov     [rbx+0F8h], eax
0x14003f077  mov     [rbx+0FCh], r13d
0x14003f07e  mov     [rbx+100h], r13d
0x14003f085  mov     eax, [rdi+1Fh]
0x14003f088  mov     [rbx+128h], eax
0x14003f08e  mov     eax, [rdi+23h]
0x14003f091  mov     [rbx+12Ch], eax
0x14003f097  movzx   edx, byte ptr [rdi+2Bh]
0x14003f09b  test    dl, dl
0x14003f09d  jnz     short loc_14003F0CA
0x14003f09f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f0a6  lea     rax, WPP_GLOBAL_Control
0x14003f0ad  cmp     rcx, rax
0x14003f0b0  jz      loc_14003F4DC
0x14003f0b6  cmp     byte ptr [rcx+29h], 2
0x14003f0ba  jb      loc_14003F4DC
0x14003f0c0  mov     edx, 0Dh
0x14003f0c5  jmp     loc_14003F499
0x14003f0ca  movzx   r9d, byte ptr [rdi]
0x14003f0ce  lea     r14, ds:0[rdx*4]
0x14003f0d6  lea     r8, [r14+2Ch]
0x14003f0da  cmp     r8, r9
0x14003f0dd  jz      short loc_14003F129
0x14003f0df  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f0e6  lea     rax, WPP_GLOBAL_Control
0x14003f0ed  cmp     rcx, rax
0x14003f0f0  jz      loc_14003F4DC
0x14003f0f6  cmp     byte ptr [rcx+29h], 2
0x14003f0fa  jb      loc_14003F4DC
0x14003f100  mov     rcx, [rcx+18h]
0x14003f104  mov     eax, r9d
0x14003f107  mov     [rsp+78h+var_50], r8d
0x14003f10c  mov     r9d, edx
0x14003f10f  mov     edx, 0Eh
0x14003f114  mov     [rsp+78h+var_58], eax
0x14003f118  lea     r8, WPP_cb3bf0f71c183cb151c0892f7a1c1990_Traceguids
0x14003f11f  call    WPP_SF_ddD
0x14003f124  jmp     loc_14003F4DC
0x14003f129  mov     eax, [rdi+2Ch]
0x14003f12c  mov     r13d, edx
0x14003f12f  mov     [rbx+118h], rax
0x14003f136  mov     r8d, 56425355h; Tag
0x14003f13c  lea     eax, [rdx-1]
0x14003f13f  mov     ecx, 600h; PoolType
0x14003f144  mov     [rsp+78h+arg_8], rax
0x14003f14c  mov     rdx, r14; NumberOfBytes
0x14003f14f  mov     eax, [rdi+rax*4+2Ch]
0x14003f153  mov     [rbx+120h], rax
0x14003f15a  call    cs:__imp_ExAllocatePoolWithTag
0x14003f161  nop     dword ptr [rax+rax+00h]
0x14003f166  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x14003f16d  mov     rbp, rax
0x14003f170  jnz     short loc_14003F18A
0x14003f172  test    rax, rax
0x14003f175  jz      loc_14003F4E3
0x14003f17b  mov     r8, r14; Size
0x14003f17e  xor     edx, edx; Val
0x14003f180  mov     rcx, rax; void *
0x14003f183  call    memset
0x14003f188  jmp     short loc_14003F193
0x14003f18a  test    rbp, rbp
0x14003f18d  jz      loc_14003F4E3
0x14003f193  mov     rcx, [r15+10h]; ObjectBag
0x14003f197  lea     r8, FreeMem; Free
0x14003f19e  mov     rdx, rbp; Item
0x14003f1a1  call    cs:__imp_KsAddItemToObjectBag
0x14003f1a8  nop     dword ptr [rax+rax+00h]
0x14003f1ad  mov     r15d, eax
0x14003f1b0  mov     rcx, rbp; void *
0x14003f1b3  test    eax, eax
0x14003f1b5  jns     short loc_14003F1D0
0x14003f1b7  mov     edx, 56425355h; Tag
0x14003f1bc  call    cs:__imp_ExFreePoolWithTag
0x14003f1c3  nop     dword ptr [rax+rax+00h]
0x14003f1c8  mov     eax, r15d
0x14003f1cb  jmp     loc_14003F4E8
0x14003f1d0  mov     r8, r14; Size
0x14003f1d3  lea     rdx, [rdi+2Ch]; Src
0x14003f1d7  call    memmove
0x14003f1dc  mov     rax, [rsp+78h+arg_8]
0x14003f1e4  mov     [rbx+28h], rbp
0x14003f1e8  mov     [rbx+30h], r13d
0x14003f1ec  mov     eax, [rdi+rax*4+2Ch]
0x14003f1f0  mov     [rbx+34h], eax
0x14003f1f3  mov     rcx, [rbx+120h]
0x14003f1fa  mov     rax, [rbx+118h]
0x14003f201  cmp     rax, rcx
0x14003f204  jle     short loc_14003F231
0x14003f206  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f20d  lea     rax, WPP_GLOBAL_Control
0x14003f214  cmp     rcx, rax
0x14003f217  jz      loc_14003F4DC
0x14003f21d  cmp     byte ptr [rcx+29h], 2
0x14003f221  jb      loc_14003F4DC
0x14003f227  mov     edx, 0Fh
0x14003f22c  jmp     loc_14003F499
0x14003f231  xor     edx, edx
0x14003f233  test    rax, rax
0x14003f236  jz      loc_14003F47B
0x14003f23c  test    rcx, rcx
  ... truncated ...
```
