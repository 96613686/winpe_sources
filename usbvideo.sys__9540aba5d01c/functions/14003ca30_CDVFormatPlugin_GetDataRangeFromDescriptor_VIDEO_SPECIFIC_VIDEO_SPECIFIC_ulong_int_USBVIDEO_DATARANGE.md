# CDVFormatPlugin::GetDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,int,_USBVIDEO_DATARANGE * *)

- ea: `0x14003ca30`
- end: `0x14003d26f`
- name: `?GetDataRangeFromDescriptor@CDVFormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KHPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `2111`
- prototype: `__int64 __fastcall(CDVFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x14003ca30`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003cacc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cb5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cacc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cb5a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003ca75`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003cafe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003ca75`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003cafe`
- `ks!KsAddItemToObjectBag` at `0x14003cab1`
- `ks!KsAddItemToObjectBag` at `0x14003cb3f`
- `ks!KsAddItemToObjectBag` at `0x14003cab1`
- `ks!KsAddItemToObjectBag` at `0x14003cb3f`

## pseudocode

```c
__int64 __fastcall CDVFormatPlugin::GetDataRangeFromDescriptor(
        CDVFormatPlugin *this,
        struct VIDEO_SPECIFIC *a2,
        struct VIDEO_SPECIFIC *a3,
        int a4,
        int a5,
        GUID **a6)
{
  int v7; // ebp
  SIZE_T v10; // rdi
  GUID *PoolWithTag; // rax
  GUID *v12; // rbx
  NTSTATUS v13; // r15d
  _DWORD *v15; // rax
  void *v16; // rdi
  NTSTATUS v17; // r14d
  _DWORD *v18; // rcx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  _DWORD *v21; // rcx
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  GUID v24; // xmm0
  unsigned int v25; // ecx
  int v26; // r8d
  unsigned int v27; // edx

  v7 = *((_DWORD *)this + 6) & 1;
  if ( !a5 || (v10 = 392, a4 != v7) )
    v10 = 192;
  PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, v10, 0x56425355u);
  v12 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  if ( !ExPoolZeroingNativelySupported )
    memset(PoolWithTag, 0, v10);
  v13 = KsAddItemToObjectBag(*((KSOBJECT_BAG *)this + 2), v12, FreeMem);
  if ( v13 < 0 )
  {
    ExFreePoolWithTag(v12, 0x56425355u);
    return (unsigned int)v13;
  }
  memset(v12, 0, v10);
  BYTE1(v12[5].Data1) = 1;
  v15 = ExAllocatePoolWithTag((POOL_TYPE)1536, 4u, 0x56425355u);
  v16 = v15;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( v15 )
    {
      *v15 = 0;
      goto LABEL_13;
    }
    return 3221225626LL;
  }
  if ( !v15 )
    return 3221225626LL;
LABEL_13:
  v17 = KsAddItemToObjectBag(*((KSOBJECT_BAG *)this + 2), v15, FreeMem);
  if ( v17 < 0 )
  {
    ExFreePoolWithTag(v16, 0x56425355u);
    return (unsigned int)v17;
  }
  *(_QWORD *)v12[2].Data4 = v16;
  v12[3].Data1 = 1;
  if ( !a5 || a4 != v7 )
  {
    v12[6].Data1 = 96;
    v12[7] = GUID_73766169_0000_0010_8000_00aa00389b71;
    v12[9] = GUID_05589f84_c356_11ce_bf01_00aa0055595a;
    v21 = *(_DWORD **)v12[2].Data4;
    if ( *((char *)a2 + 8) >= 0 )
    {
      *(_DWORD *)&v12[3].Data2 = 400000;
      *v21 = 400000;
      if ( *((_BYTE *)a2 + 8) )
      {
        if ( *((_BYTE *)a2 + 8) != 1 )
        {
          if ( *((_BYTE *)a2 + 8) == 2 )
          {
            *(_DWORD *)v12[6].Data4 = 288000;
            v12[8] = GUID_64687664_0000_0010_8000_00aa00389b71;
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_69;
            v23 = 16;
          }
          else
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_69;
            v23 = 17;
          }
LABEL_61:
          WPP_SF_(v22->AttachedDevice, v23, WPP_69f6b6c0d15b31777b53c7f4677022b8_Traceguids);
LABEL_69:
          v12[4].Data4[4] = *((_BYTE *)a2 + 3);
          v12[4].Data4[5] = 0;
          goto LABEL_70;
        }
        v24 = GUID_6c737664_0000_0010_8000_00aa00389b71;
        *(_DWORD *)v12[6].Data4 = 72000;
        v12[10].Data1 = -773771057;
        *(_QWORD *)v12[10].Data4 = 0;
        v12[11].Data1 = -14548993;
        *(_DWORD *)&v12[11].Data2 = -145345;
LABEL_68:
        *(_DWORD *)&v12[10].Data2 = -6238401;
        v12[8] = v24;
        goto LABEL_69;
      }
      *(_DWORD *)v12[6].Data4 = 144000;
      v12[10].Data1 = -773836593;
      *(_DWORD *)v12[10].Data4 = -773832753;
      v12[11].Data1 = -14614529;
      *(_DWORD *)&v12[11].Data2 = -145345;
    }
    else
    {
      *(_DWORD *)&v12[3].Data2 = 333667;
      *v21 = 333667;
      if ( (*((_BYTE *)a2 + 8) & 0x7F) != 0 )
      {
        if ( (*((_BYTE *)a2 + 8) & 0x7F) != 1 )
        {
          if ( (*((_BYTE *)a2 + 8) & 0x7F) == 2 )
          {
            *(_DWORD *)v12[6].Data4 = 240000;
            v12[8] = GUID_64687664_0000_0010_8000_00aa00389b71;
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_69;
            v23 = 14;
          }
          else
          {
            v22 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              goto LABEL_69;
            v23 = 15;
          }
          goto LABEL_61;
        }
        v24 = GUID_6c737664_0000_0010_8000_00aa00389b71;
        *(_DWORD *)v12[6].Data4 = 60000;
        v12[10].Data1 = -775868209;
        *(_QWORD *)v12[10].Data4 = 0;
        v12[11].Data1 = -16646145;
        *(_DWORD *)&v12[11].Data2 = -210881;
        goto LABEL_68;
      }
      *(_DWORD *)v12[6].Data4 = 120000;
      v12[10].Data1 = -775933745;
      *(_DWORD *)v12[10].Data4 = -775929905;
      v12[11].Data1 = -16711681;
      *(_DWORD *)&v12[11].Data2 = -210881;
    }
    v24 = GUID_64737664_0000_0010_8000_00aa00389b71;
    *(_DWORD *)&v12[10].Data4[4] = -6238401;
    goto LABEL_68;
  }
  *(_QWORD *)&v12[10].Data1 = 1;
  v12[6].Data1 = 296;
  v12[7] = GUID_73646976_0000_0010_8000_00aa00389b71;
  v12[9] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
  *(_DWORD *)&v12[13].Data4[4] = 1;
  v12[14].Data1 = 1;
  v12[11] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
  *(_DWORD *)&v12[14].Data2 = 1;
  *(_DWORD *)v12[14].Data4 = 1;
  *(_DWORD *)&v12[15].Data4[4] = 1;
  v12[16].Data1 = 1;
  v12[22].Data1 = 40;
  *(_DWORD *)&v12[22].Data4[4] = 1572865;
  v18 = *(_DWORD **)v12[2].Data4;
  v12[4].Data4[4] = *((_BYTE *)a2 + 3);
  v12[4].Data4[5] = 0;
  *(_DWORD *)v12[3].Data4 = 1;
  if ( *((char *)a2 + 8) >= 0 )
  {
    *(_DWORD *)&v12[3].Data2 = 400000;
    *v18 = 400000;
    *(_DWORD *)&v12[12].Data2 = 720;
    *(_DWORD *)&v12[12].Data4[4] = 720;
    *(_DWORD *)&v12[13].Data2 = 720;
    *(_DWORD *)&v12[14].Data4[4] = 720;
    *(_DWORD *)&v12[15].Data2 = 720;
    *(_DWORD *)&v12[22].Data2 = 720;
    v12[12].Data1 = 16;
    *(_DWORD *)v12[12].Data4 = 480;
    v12[13].Data1 = 576;
    *(_DWORD *)v12[13].Data4 = 576;
    v12[15].Data1 = 576;
    *(_DWORD *)v12[15].Data4 = 576;
    *(_QWORD *)v12[17].Data4 = 400000;
    *(_QWORD *)&v12[18].Data1 = 400000;
    *(_QWORD *)v12[21].Data4 = 400000;
    *(_DWORD *)v12[22].Data4 = 576;
    switch ( *((_BYTE *)a2 + 8) )
    {
      case 0:
        *(_DWORD *)v12[6].Data4 = 144000;
        *(_DWORD *)v12[18].Data4 = 28800000;
        v12[8] = GUID_64737664_0000_0010_8000_00aa00389b71;
        *(_DWORD *)&v12[18].Data4[4] = 28800000;
        v12[21].Data1 = 28800000;
        v12[23].Data1 = 1685288548;
        *(_DWORD *)&v12[23].Data2 = 144000;
        goto LABEL_70;
      case 1:
        *(_DWORD *)v12[6].Data4 = 72000;
        *(_DWORD *)v12[18].Data4 = 14400000;
        v12[8] = GUID_6c737664_0000_0010_8000_00aa00389b71;
        *(_DWORD *)&v12[18].Data4[4] = 14400000;
        v12[21].Data1 = 28800000;
        v12[23].Data1 = 1819506276;
        *(_DWORD *)&v12[23].Data2 = 72000;
        goto LABEL_70;
      case 2:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_69f6b6c0d15b31777b53c7f4677022b8_Traceguids);
        *(_DWORD *)v12[6].Data4 = 288000;
        *(_DWORD *)v12[18].Data4 = 57600000;
        v12[8] = GUID_64687664_0000_0010_8000_00aa00389b71;
        *(_DWORD *)&v12[18].Data4[4] = 57600000;
        v12[21].Data1 = 28800000;
        v12[23].Data1 = 1684567652;
        *(_DWORD *)&v12[23].Data2 = 288000;
        goto LABEL_70;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v20 = 13;
      goto LABEL_36;
    }
  }
  else
  {
    *(_DWORD *)&v12[3].Data2 = 333667;
    *v18 = 333667;
    *(_DWORD *)&v12[12].Data2 = 720;
    *(_DWORD *)&v12[12].Data4[4] = 720;
    *(_DWORD *)&v12[13].Data2 = 720;
    *(_DWORD *)&v12[14].Data4[4] = 720;
    *(_DWORD *)&v12[15].Data2 = 720;
    *(_DWORD *)&v12[22].Data2 = 720;
    v12[12].Data1 = 1;
    *(_DWORD *)v12[12].Data4 = 480;
    v12[13].Data1 = 480;
    *(_DWORD *)v12[13].Data4 = 480;
    v12[15].Data1 = 480;
    *(_DWORD *)v12[15].Data4 = 480;
    *(_QWORD *)v12[17].Data4 = 333667;
    *(_QWORD *)&v12[18].Data1 = 333667;
    *(_QWORD *)v12[21].Data4 = 333667;
    *(_DWORD *)v12[22].Data4 = 480;
    if ( (*((_BYTE *)a2 + 8) & 0x7F) != 0 )
    {
      if ( (*((_BYTE *)a2 + 8) & 0x7F) == 1 )
      {
        *(_DWORD *)v12[6].Data4 = 60000;
        *(_DWORD *)v12[18].Data4 = 14400000;
        v12[8] = GUID_6c737664_0000_0010_8000_00aa00389b71;
        *(_DWORD *)&v12[18].Data4[4] = 14400000;
        v12[21].Data1 = 14400000;
        v12[23].Data1 = 1819506276;
        *(_DWORD *)&v12[23].Data2 = 60000;
      }
      else
      {
        if ( (*((_BYTE *)a2 + 8) & 0x7F) == 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_69f6b6c0d15b31777b53c7f4677022b8_Traceguids);
          *(_DWORD *)v12[6].Data4 = 240000;
          *(_DWORD *)v12[18].Data4 = 57600000;
          v12[8] = GUID_64687664_0000_0010_8000_00aa00389b71;
          *(_DWORD *)&v12[18].Data4[4] = 57600000;
          v12[21].Data1 = 57600000;
          v12[23].Data1 = 1684567652;
          *(_DWORD *)&v12[23].Data2 = 240000;
          goto LABEL_70;
        }
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v20 = 11;
LABEL_36:
          WPP_SF_(v19->AttachedDevice, v20, WPP_69f6b6c0d15b31777b53c7f4677022b8_Traceguids);
        }
      }
    }
    else
    {
      *(_DWORD *)v12[6].Data4 = 120000;
      *(_DWORD *)v12[18].Data4 = 28800000;
      v12[8] = GUID_64737664_0000_0010_8000_00aa00389b71;
      *(_DWORD *)&v12[18].Data4[4] = 28800000;
      v12[21].Data1 = 28800000;
      v12[23].Data1 = 1685288548;
      *(_DWORD *)&v12[23].Data2 = 120000;
    }
  }
LABEL_70:
  v25 = *(_DWORD *)v12[6].Data4;
  *(_DWORD *)&v12[3].Data4[4] = v25;
  v26 = *((char *)a2 + 8);
  if ( *((char *)a2 + 8) >= 0 )
    v27 = v25 / 0x12C;
  else
    v27 = v25 / 0xFA;
  v12[4].Data1 = v27;
  *(_DWORD *)&v12[4].Data2 = ((v26 >> 31) & 0xFFFFFFCE) + 300;
  *(_DWORD *)v12[4].Data4 = 13500000;
  *(_WORD *)&v12[4].Data4[6] = 257;
  *a6 = v12;
  return 0;
}

```

## disassembly

```asm
0x14003ca30  push    rbx
0x14003ca32  push    rbp
0x14003ca33  push    rsi
0x14003ca34  push    rdi
0x14003ca35  push    r12
0x14003ca37  push    r14
0x14003ca39  push    r15
0x14003ca3b  sub     rsp, 20h
0x14003ca3f  mov     ebp, [rcx+18h]
0x14003ca42  mov     r12d, r9d
0x14003ca45  and     ebp, 1
0x14003ca48  mov     rsi, rdx
0x14003ca4b  cmp     [rsp+58h+arg_20], 0
0x14003ca53  mov     r14, rcx
0x14003ca56  jz      short loc_14003CA62
0x14003ca58  mov     edi, 188h
0x14003ca5d  cmp     r9d, ebp
0x14003ca60  jz      short loc_14003CA67
0x14003ca62  mov     edi, 0C0h
0x14003ca67  mov     r8d, 56425355h; Tag
0x14003ca6d  mov     rdx, rdi; NumberOfBytes
0x14003ca70  mov     ecx, 600h; PoolType
0x14003ca75  call    cs:__imp_ExAllocatePoolWithTag
0x14003ca7c  nop     dword ptr [rax+rax+00h]
0x14003ca81  mov     rbx, rax
0x14003ca84  test    rax, rax
0x14003ca87  jz      loc_14003D25A
0x14003ca8d  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14003ca94  jnz     short loc_14003CAA3
0x14003ca96  mov     r8, rdi; Size
0x14003ca99  xor     edx, edx; Val
0x14003ca9b  mov     rcx, rax; void *
0x14003ca9e  call    memset
0x14003caa3  mov     rcx, [r14+10h]; ObjectBag
0x14003caa7  lea     r8, FreeMem; Free
0x14003caae  mov     rdx, rbx; Item
0x14003cab1  call    cs:__imp_KsAddItemToObjectBag
0x14003cab8  nop     dword ptr [rax+rax+00h]
0x14003cabd  mov     r15d, eax
0x14003cac0  mov     rcx, rbx; void *
0x14003cac3  test    eax, eax
0x14003cac5  jns     short loc_14003CAE0
0x14003cac7  mov     edx, 56425355h; Tag
0x14003cacc  call    cs:__imp_ExFreePoolWithTag
0x14003cad3  nop     dword ptr [rax+rax+00h]
0x14003cad8  mov     eax, r15d
0x14003cadb  jmp     loc_14003D25F
0x14003cae0  mov     r8, rdi; Size
0x14003cae3  xor     edx, edx; Val
0x14003cae5  call    memset
0x14003caea  mov     edx, 4; NumberOfBytes
0x14003caef  mov     byte ptr [rbx+51h], 1
0x14003caf3  mov     ecx, 600h; PoolType
0x14003caf8  mov     r8d, 56425355h; Tag
0x14003cafe  call    cs:__imp_ExAllocatePoolWithTag
0x14003cb05  nop     dword ptr [rax+rax+00h]
0x14003cb0a  xor     r15d, r15d
0x14003cb0d  mov     rdi, rax
0x14003cb10  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x14003cb17  jnz     short loc_14003CB28
0x14003cb19  test    rax, rax
0x14003cb1c  jz      loc_14003D25A
0x14003cb22  xor     eax, eax
0x14003cb24  mov     [rdi], eax
0x14003cb26  jmp     short loc_14003CB31
0x14003cb28  test    rdi, rdi
0x14003cb2b  jz      loc_14003D25A
0x14003cb31  mov     rcx, [r14+10h]; ObjectBag
0x14003cb35  lea     r8, FreeMem; Free
0x14003cb3c  mov     rdx, rdi; Item
0x14003cb3f  call    cs:__imp_KsAddItemToObjectBag
0x14003cb46  nop     dword ptr [rax+rax+00h]
0x14003cb4b  mov     r14d, eax
0x14003cb4e  test    eax, eax
0x14003cb50  jns     short loc_14003CB6E
0x14003cb52  mov     edx, 56425355h; Tag
0x14003cb57  mov     rcx, rdi; P
0x14003cb5a  call    cs:__imp_ExFreePoolWithTag
0x14003cb61  nop     dword ptr [rax+rax+00h]
0x14003cb66  mov     eax, r14d
0x14003cb69  jmp     loc_14003D25F
0x14003cb6e  mov     [rbx+28h], rdi
0x14003cb72  mov     edi, 1
0x14003cb77  mov     [rbx+30h], edi
0x14003cb7a  cmp     [rsp+58h+arg_20], r15d
0x14003cb82  jz      loc_14003CFB2
0x14003cb88  cmp     r12d, ebp
0x14003cb8b  jnz     loc_14003CFB2
0x14003cb91  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14003cb98  mov     [rbx+0A0h], rdi
0x14003cb9f  mov     dword ptr [rbx+60h], 128h
0x14003cba6  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003cbab  movups  xmm1, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003cbb2  movdqu  xmmword ptr [rbx+90h], xmm1
0x14003cbba  movups  xmm0, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003cbc1  mov     [rbx+0DCh], edi
0x14003cbc7  mov     [rbx+0E0h], edi
0x14003cbcd  movdqu  xmmword ptr [rbx+0B0h], xmm0
0x14003cbd5  mov     [rbx+0E4h], edi
0x14003cbdb  mov     [rbx+0E8h], edi
0x14003cbe1  mov     [rbx+0FCh], edi
0x14003cbe7  mov     [rbx+100h], edi
0x14003cbed  mov     dword ptr [rbx+160h], 28h ; '('
0x14003cbf7  mov     dword ptr [rbx+16Ch], 180001h
0x14003cc01  mov     al, [rsi+3]
0x14003cc04  mov     rcx, [rbx+28h]
0x14003cc08  mov     [rbx+4Ch], al
0x14003cc0b  mov     [rbx+4Dh], r15b
0x14003cc0f  mov     [rbx+38h], edi
0x14003cc12  cmp     [rsi+8], r15b
0x14003cc16  jge     loc_14003CDD8
0x14003cc1c  mov     edx, 1E0h
0x14003cc21  mov     eax, 51763h
0x14003cc26  mov     [rbx+34h], eax
0x14003cc29  mov     [rcx], eax
0x14003cc2b  mov     ecx, 2D0h
0x14003cc30  mov     [rbx+0C4h], ecx
0x14003cc36  mov     [rbx+0CCh], ecx
0x14003cc3c  mov     [rbx+0D4h], ecx
0x14003cc42  mov     [rbx+0ECh], ecx
0x14003cc48  mov     [rbx+0F4h], ecx
0x14003cc4e  mov     [rbx+164h], ecx
0x14003cc54  mov     [rbx+0C0h], edi
0x14003cc5a  mov     [rbx+0C8h], edx
0x14003cc60  mov     [rbx+0D0h], edx
0x14003cc66  mov     [rbx+0D8h], edx
0x14003cc6c  mov     [rbx+0F0h], edx
0x14003cc72  mov     [rbx+0F8h], edx
0x14003cc78  mov     [rbx+118h], rax
0x14003cc7f  mov     [rbx+120h], rax
0x14003cc86  mov     [rbx+158h], rax
0x14003cc8d  mov     [rbx+168h], edx
0x14003cc93  movzx   ecx, byte ptr [rsi+8]
0x14003cc97  and     ecx, 0FFFFFF7Fh
0x14003cc9d  jz      loc_14003CD92
0x14003cca3  sub     ecx, edi
0x14003cca5  jz      loc_14003CD4C
0x14003ccab  cmp     ecx, edi
0x14003ccad  jz      short loc_14003CCD8
0x14003ccaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ccb6  lea     rax, WPP_GLOBAL_Control
0x14003ccbd  cmp     rcx, rax
0x14003ccc0  jz      loc_14003D204
0x14003ccc6  cmp     byte ptr [rcx+29h], 2
0x14003ccca  jb      loc_14003D204
0x14003ccd0  lea     edx, [rdi+0Ah]
0x14003ccd3  jmp     loc_14003CE95
0x14003ccd8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ccdf  lea     rax, WPP_GLOBAL_Control
0x14003cce6  cmp     rcx, rax
0x14003cce9  jz      short loc_14003CD06
0x14003cceb  cmp     byte ptr [rcx+29h], 2
0x14003ccef  jb      short loc_14003CD06
0x14003ccf1  mov     rcx, [rcx+18h]
0x14003ccf5  lea     r8, WPP_69f6b6c0d15b31777b53c7f4677022b8_Traceguids
0x14003ccfc  mov     edx, 0Ah
0x14003cd01  call    WPP_SF_
0x14003cd06  movups  xmm0, xmmword ptr cs:_GUID_64687664_0000_0010_8000_00aa00389b71.Data1
0x14003cd0d  mov     eax, 36EE800h
0x14003cd12  mov     dword ptr [rbx+68h], 3A980h
0x14003cd19  mov     [rbx+128h], eax
0x14003cd1f  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003cd27  mov     [rbx+12Ch], eax
0x14003cd2d  mov     [rbx+150h], eax
0x14003cd33  mov     dword ptr [rbx+170h], 64687664h
0x14003cd3d  mov     dword ptr [rbx+174h], 3A980h
0x14003cd47  jmp     loc_14003D204
0x14003cd4c  movups  xmm0, xmmword ptr cs:_GUID_6c737664_0000_0010_8000_00aa00389b71.Data1
0x14003cd53  mov     eax, 0DBBA00h
0x14003cd58  mov     dword ptr [rbx+68h], 0EA60h
0x14003cd5f  mov     [rbx+128h], eax
0x14003cd65  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003cd6d  mov     [rbx+12Ch], eax
0x14003cd73  mov     [rbx+150h], eax
0x14003cd79  mov     dword ptr [rbx+170h], 6C737664h
0x14003cd83  mov     dword ptr [rbx+174h], 0EA60h
0x14003cd8d  jmp     loc_14003D204
0x14003cd92  movups  xmm0, xmmword ptr cs:_GUID_64737664_0000_0010_8000_00aa00389b71.Data1
0x14003cd99  mov     eax, 1B77400h
0x14003cd9e  mov     dword ptr [rbx+68h], 1D4C0h
0x14003cda5  mov     [rbx+128h], eax
0x14003cdab  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003cdb3  mov     [rbx+12Ch], eax
0x14003cdb9  mov     [rbx+150h], eax
0x14003cdbf  mov     dword ptr [rbx+170h], 64737664h
0x14003cdc9  mov     dword ptr [rbx+174h], 1D4C0h
0x14003cdd3  jmp     loc_14003D204
0x14003cdd8  mov     eax, 61A80h
0x14003cddd  mov     edx, 240h
0x14003cde2  mov     [rbx+34h], eax
0x14003cde5  mov     [rcx], eax
0x14003cde7  mov     ecx, 2D0h
0x14003cdec  mov     [rbx+0C4h], ecx
0x14003cdf2  mov     [rbx+0CCh], ecx
0x14003cdf8  mov     [rbx+0D4h], ecx
0x14003cdfe  mov     [rbx+0ECh], ecx
0x14003ce04  mov     [rbx+0F4h], ecx
0x14003ce0a  mov     [rbx+164h], ecx
0x14003ce10  mov     dword ptr [rbx+0C0h], 10h
0x14003ce1a  mov     dword ptr [rbx+0C8h], 1E0h
0x14003ce24  mov     [rbx+0D0h], edx
0x14003ce2a  mov     [rbx+0D8h], edx
0x14003ce30  mov     [rbx+0F0h], edx
0x14003ce36  mov     [rbx+0F8h], edx
0x14003ce3c  mov     [rbx+118h], rax
0x14003ce43  mov     [rbx+120h], rax
0x14003ce4a  mov     [rbx+158h], rax
0x14003ce51  mov     [rbx+168h], edx
0x14003ce57  movzx   ecx, byte ptr [rsi+8]
0x14003ce5b  test    ecx, ecx
0x14003ce5d  jz      loc_14003CF6C
0x14003ce63  sub     ecx, edi
0x14003ce65  jz      loc_14003CF22
0x14003ce6b  cmp     ecx, edi
0x14003ce6d  jz      short loc_14003CEAA
0x14003ce6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ce76  lea     rax, WPP_GLOBAL_Control
0x14003ce7d  cmp     rcx, rax
0x14003ce80  jz      loc_14003D204
0x14003ce86  cmp     byte ptr [rcx+29h], 2
0x14003ce8a  jb      loc_14003D204
0x14003ce90  mov     edx, 0Dh
0x14003ce95  mov     rcx, [rcx+18h]
0x14003ce99  lea     r8, WPP_69f6b6c0d15b31777b53c7f4677022b8_Traceguids
0x14003cea0  call    WPP_SF_
0x14003cea5  jmp     loc_14003D204
0x14003ceaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ceb1  lea     rax, WPP_GLOBAL_Control
0x14003ceb8  cmp     rcx, rax
0x14003cebb  jz      short loc_14003CED8
0x14003cebd  cmp     byte ptr [rcx+29h], 2
0x14003cec1  jb      short loc_14003CED8
0x14003cec3  mov     rcx, [rcx+18h]
0x14003cec7  lea     r8, WPP_69f6b6c0d15b31777b53c7f4677022b8_Traceguids
0x14003cece  mov     edx, 0Ch
0x14003ced3  call    WPP_SF_
0x14003ced8  movups  xmm0, xmmword ptr cs:_GUID_64687664_0000_0010_8000_00aa00389b71.Data1
0x14003cedf  mov     eax, 36EE800h
0x14003cee4  mov     dword ptr [rbx+68h], 46500h
0x14003ceeb  mov     [rbx+128h], eax
0x14003cef1  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003cef9  mov     [rbx+12Ch], eax
0x14003ceff  mov     dword ptr [rbx+150h], 1B77400h
0x14003cf09  mov     dword ptr [rbx+170h], 64687664h
0x14003cf13  mov     dword ptr [rbx+174h], 46500h
0x14003cf1d  jmp     loc_14003D204
0x14003cf22  movups  xmm0, xmmword ptr cs:_GUID_6c737664_0000_0010_8000_00aa00389b71.Data1
0x14003cf29  mov     eax, 0DBBA00h
0x14003cf2e  mov     dword ptr [rbx+68h], 11940h
0x14003cf35  mov     [rbx+128h], eax
0x14003cf3b  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003cf43  mov     [rbx+12Ch], eax
0x14003cf49  mov     dword ptr [rbx+150h], 1B77400h
0x14003cf53  mov     dword ptr [rbx+170h], 6C737664h
0x14003cf5d  mov     dword ptr [rbx+174h], 11940h
0x14003cf67  jmp     loc_14003D204
0x14003cf6c  movups  xmm0, xmmword ptr cs:_GUID_64737664_0000_0010_8000_00aa00389b71.Data1
0x14003cf73  mov     eax, 1B77400h
0x14003cf78  mov     dword ptr [rbx+68h], 23280h
0x14003cf7f  mov     [rbx+128h], eax
0x14003cf85  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003cf8d  mov     [rbx+12Ch], eax
0x14003cf93  mov     [rbx+150h], eax
0x14003cf99  mov     dword ptr [rbx+170h], 64737664h
0x14003cfa3  mov     dword ptr [rbx+174h], 23280h
0x14003cfad  jmp     loc_14003D204
0x14003cfb2  movups  xmm0, xmmword ptr cs:_GUID_73766169_0000_0010_8000_00aa00389b71.Data1
0x14003cfb9  mov     dword ptr [rbx+60h], 60h ; '`'
0x14003cfc0  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003cfc5  movups  xmm1, xmmword ptr cs:_GUID_05589f84_c356_11ce_bf01_00aa0055595a.Data1
0x14003cfcc  movdqu  xmmword ptr [rbx+90h], xmm1
0x14003cfd4  mov     rcx, [rbx+28h]
0x14003cfd8  cmp     [rsi+8], r15b
0x14003cfdc  jge     loc_14003D0DC
0x14003cfe2  mov     eax, 51763h
0x14003cfe7  mov     [rbx+34h], eax
0x14003cfea  mov     [rcx], eax
0x14003cfec  movzx   ecx, byte ptr [rsi+8]
0x14003cff0  and     ecx, 0FFFFFF7Fh
0x14003cff6  jz      loc_14003D0A8
0x14003cffc  sub     ecx, edi
0x14003cffe  jz      short loc_14003D070
0x14003d000  cmp     ecx, edi
0x14003d002  jz      short loc_14003D02F
0x14003d004  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d00b  lea     rax, WPP_GLOBAL_Control
0x14003d012  cmp     rcx, rax
0x14003d015  jz      loc_14003D1FA
0x14003d01b  cmp     byte ptr [rcx+29h], 2
0x14003d01f  jb      loc_14003D1FA
0x14003d025  mov     edx, 0Fh
0x14003d02a  jmp     loc_14003D120
0x14003d02f  movups  xmm0, xmmword ptr cs:_GUID_64687664_0000_0010_8000_00aa00389b71.Data1
0x14003d036  mov     dword ptr [rbx+68h], 3A980h
0x14003d03d  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003d045  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d04c  lea     rax, WPP_GLOBAL_Control
0x14003d053  cmp     rcx, rax
0x14003d056  jz      loc_14003D1FA
0x14003d05c  cmp     byte ptr [rcx+29h], 2
  ... truncated ...
```
