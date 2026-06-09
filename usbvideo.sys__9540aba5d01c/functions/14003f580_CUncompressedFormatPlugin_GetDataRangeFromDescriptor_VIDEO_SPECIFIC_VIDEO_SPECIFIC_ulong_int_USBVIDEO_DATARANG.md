# CUncompressedFormatPlugin::GetDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,int,_USBVIDEO_DATARANGE * *)

- ea: `0x14003f580`
- end: `0x14003fd91`
- name: `?GetDataRangeFromDescriptor@CUncompressedFormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KHPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `2065`
- prototype: `__int64 __fastcall(CUncompressedFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x14001b3e4`
- `0x14003c810`
- `0x14003f580`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003f6c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f8f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f9e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f6c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f8f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f9e2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f640`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f66a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f895`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f97b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f640`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f66a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f895`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f97b`
- `ks!KsAddItemToObjectBag` at `0x14003f6ae`
- `ks!KsAddItemToObjectBag` at `0x14003f8de`
- `ks!KsAddItemToObjectBag` at `0x14003f9ca`
- `ks!KsAddItemToObjectBag` at `0x14003f6ae`
- `ks!KsAddItemToObjectBag` at `0x14003f8de`
- `ks!KsAddItemToObjectBag` at `0x14003f9ca`

## pseudocode

```c
__int64 __fastcall CUncompressedFormatPlugin::GetDataRangeFromDescriptor(
        KSOBJECT_BAG *this,
        struct VIDEO_SPECIFIC *a2,
        struct VIDEO_SPECIFIC *a3,
        unsigned int a4,
        int a5,
        GUID **a6)
{
  char v8; // r12
  unsigned int FrameIndex; // r10d
  char v10; // r12
  unsigned __int8 *v11; // rdi
  unsigned int i; // ecx
  GUID *PoolWithTag; // rax
  GUID *v14; // rbx
  size_t v15; // r8
  NTSTATUS v16; // r14d
  size_t v18; // r8
  int v19; // eax
  int v20; // ecx
  __int64 v21; // rcx
  unsigned int v22; // r8d
  int v23; // eax
  int v24; // ecx
  unsigned int v25; // r15d
  PVOID v26; // rax
  void *v27; // r14
  NTSTATUS v28; // r13d
  __int64 v29; // rdx
  unsigned int v30; // r8d
  KSOBJECT_BAG *v31; // r13
  int v32; // eax
  size_t v33; // r15
  PVOID v34; // rax
  void *v35; // r14
  NTSTATUS v36; // r15d
  __int64 v37; // rcx
  __int64 v38; // rax
  PDEVICE_OBJECT v39; // rcx
  __int64 v40; // rdx
  unsigned int v41; // ecx
  int v42; // eax
  int v43; // ecx
  __int64 v44; // rdx
  __int64 v45; // rcx
  unsigned int v46; // r8d
  int v47; // edx
  unsigned int Data1; // ecx
  char v49; // al
  char v50; // al
  int v51; // ecx
  char v52; // al
  char v53; // al
  unsigned int v54; // eax
  int v55; // ecx
  unsigned int v56; // eax
  int v57; // ecx
  __int64 v58; // [rsp+30h] [rbp-58h]
  size_t Size; // [rsp+98h] [rbp+10h] BYREF
  struct VIDEO_SPECIFIC *v61; // [rsp+A0h] [rbp+18h]
  unsigned int v62; // [rsp+A8h] [rbp+20h] BYREF

  v61 = a3;
  LOBYTE(a3) = 1;
  v8 = a4;
  FrameIndex = GetFrameIndex(*((unsigned __int8 *)a2 + 22), a4, a3);
  if ( FrameIndex > *((unsigned __int8 *)a2 + 4) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_5c1996b9c3ee3482b8470e48b3ef8bf2_Traceguids,
        FrameIndex,
        *((unsigned __int8 *)a2 + 4));
    return 3221225485LL;
  }
  v10 = v8 & 1;
  v11 = (unsigned __int8 *)a2 + *(unsigned __int8 *)a2;
  for ( i = 1; i < FrameIndex; v11 += *v11 )
    ++i;
  if ( v10 )
  {
    PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x1A0u, 0x56425355u);
    v14 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    {
      v15 = 416;
LABEL_14:
      memset(PoolWithTag, 0, v15);
    }
  }
  else
  {
    PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x188u, 0x56425355u);
    v14 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    {
      v15 = 392;
      goto LABEL_14;
    }
  }
  if ( v14 )
  {
    v16 = KsAddItemToObjectBag(this[2], v14, FreeMem);
    if ( v16 < 0 )
    {
      ExFreePoolWithTag(v14, 0x56425355u);
      return (unsigned int)v16;
    }
    v18 = 416;
    if ( !v10 )
      v18 = 392;
    memset(v14, 0, v18);
    BYTE1(v14[5].Data1) = 1;
    v14[10].Data1 = 1;
    v19 = *(unsigned __int16 *)(v11 + 5) * *(unsigned __int16 *)(v11 + 7);
    v20 = *((unsigned __int8 *)a2 + 21);
    v14[7] = GUID_73646976_0000_0010_8000_00aa00389b71;
    *(_DWORD *)v14[6].Data4 = v20 * v19 / 8;
    v14[8] = *(GUID *)((char *)a2 + 5);
    if ( v10 )
    {
      v14[6].Data1 = 320;
      v14[9] = GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba;
      v14[11] = GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba;
    }
    else
    {
      v14[6].Data1 = 296;
      v14[9] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
      v14[11] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
    }
    v14[12].Data1 = 0;
    *(_DWORD *)&v14[12].Data2 = *(unsigned __int16 *)(v11 + 5);
    *(_DWORD *)v14[12].Data4 = *(unsigned __int16 *)(v11 + 7);
    *(_DWORD *)&v14[12].Data4[4] = *(unsigned __int16 *)(v11 + 5);
    v14[13].Data1 = *(unsigned __int16 *)(v11 + 7);
    *(_DWORD *)&v14[13].Data2 = *(unsigned __int16 *)(v11 + 5);
    *(_DWORD *)v14[13].Data4 = *(unsigned __int16 *)(v11 + 7);
    *(_DWORD *)&v14[13].Data4[4] = 1;
    v14[14].Data1 = 1;
    *(_DWORD *)&v14[14].Data2 = 1;
    *(_DWORD *)v14[14].Data4 = 1;
    *(_DWORD *)&v14[14].Data4[4] = *(unsigned __int16 *)(v11 + 5);
    v14[15].Data1 = *(unsigned __int16 *)(v11 + 7);
    *(_DWORD *)&v14[15].Data2 = *(unsigned __int16 *)(v11 + 5);
    *(_DWORD *)v14[15].Data4 = *(unsigned __int16 *)(v11 + 7);
    *(_DWORD *)&v14[15].Data4[4] = 1;
    v14[16].Data1 = 1;
    *(_DWORD *)v14[18].Data4 = *(_DWORD *)(v11 + 9);
    *(_DWORD *)&v14[18].Data4[4] = *(_DWORD *)(v11 + 13);
    v21 = v11[25];
    *(_QWORD *)v14[17].Data4 = *(unsigned int *)(v11 + 26);
    if ( (_BYTE)v21 )
    {
      v62 = v21;
      v58 = (unsigned int)(v21 - 1);
      v33 = 4 * v21;
      Size = 4 * v21;
      *(_QWORD *)&v14[18].Data1 = *(unsigned int *)&v11[4 * v58 + 26];
      v34 = ExAllocatePoolWithTag((POOL_TYPE)1536, 4 * v21, 0x56425355u);
      v35 = v34;
      if ( ExPoolZeroingNativelySupported )
      {
        if ( !v34 )
          return 3221225626LL;
      }
      else
      {
        if ( !v34 )
          return 3221225626LL;
        memset(v34, 0, v33);
      }
      v31 = this;
      v36 = KsAddItemToObjectBag(this[2], v35, FreeMem);
      if ( v36 < 0 )
      {
        ExFreePoolWithTag(v35, 0x56425355u);
        return (unsigned int)v36;
      }
      memmove(v35, v11 + 26, Size);
      v14[3].Data1 = v62;
      *(_QWORD *)v14[2].Data4 = v35;
      v32 = *(_DWORD *)&v11[4 * v58 + 26];
LABEL_45:
      *(_DWORD *)&v14[3].Data2 = v32;
      v37 = *(_QWORD *)&v14[18].Data1;
      v38 = *(_QWORD *)v14[17].Data4;
      if ( v38 > v37 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225485LL;
        v40 = 11;
LABEL_98:
        WPP_SF_(v39->AttachedDevice, v40, WPP_5c1996b9c3ee3482b8470e48b3ef8bf2_Traceguids);
        return 3221225485LL;
      }
      if ( !v38 || !v37 || (v41 = *(_DWORD *)(v11 + 21)) == 0 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return 3221225485LL;
        v40 = 12;
        goto LABEL_98;
      }
      v14[21].Data1 = *(unsigned __int16 *)(v11 + 7)
                    * *((unsigned __int8 *)a2 + 21)
                    * *(unsigned __int16 *)(v11 + 5)
                    * (0x989680
                     / v41);
      *(_QWORD *)v14[21].Data4 = *(unsigned int *)(v11 + 21);
      if ( !v10 )
      {
        v14[22].Data1 = 40;
        v56 = *((unsigned __int8 *)a2 + 21);
        v57 = *(unsigned __int16 *)(v11 + 5);
        if ( (v56 & 7) != 0 )
          v57 *= v56 >> 3;
        *(_DWORD *)&v14[22].Data2 = v57;
        *(_DWORD *)v14[22].Data4 = *(unsigned __int16 *)(v11 + 7);
        *(_WORD *)&v14[22].Data4[4] = 1;
        *(_WORD *)&v14[22].Data4[6] = *((unsigned __int8 *)a2 + 21);
        v14[23].Data1 = *(_DWORD *)((char *)a2 + 5);
        *(_DWORD *)&v14[23].Data2 = *(unsigned __int16 *)(v11 + 5)
                                  * *(unsigned __int16 *)(v11 + 7)
                                  * *((unsigned __int8 *)a2 + 21)
                                  / 8;
        goto LABEL_94;
      }
      *(_DWORD *)v14[23].Data4 = 40;
      v42 = *((unsigned __int8 *)a2 + 23);
      *(_DWORD *)v14[22].Data4 = v42;
      v43 = *((unsigned __int8 *)a2 + 24);
      *(_DWORD *)&v14[22].Data4[4] = v43;
      if ( !(_BYTE)v42 || !v43 )
      {
        v44 = *(unsigned __int16 *)(v11 + 7);
        v45 = *(unsigned __int16 *)(v11 + 5);
        v62 = 0;
        LODWORD(Size) = 0;
        ReduceToLowestTerms(v45, v44, &v62, &Size);
        v46 = v62;
        *(_DWORD *)&v14[22].Data4[4] = Size;
        *(_DWORD *)v14[22].Data4 = v46;
      }
      v47 = 2;
      *(_DWORD *)&v14[22].Data2 = *((_BYTE *)a2 + 26) == 1;
      if ( (*((_BYTE *)a2 + 25) & 1) == 0 )
        goto LABEL_75;
      v14[22].Data1 |= 1u;
      Data1 = v14[22].Data1;
      if ( (*((_BYTE *)a2 + 25) & 2) != 0 )
      {
        Data1 |= 2u;
        v14[22].Data1 = Data1;
      }
      if ( (*((_BYTE *)a2 + 25) & 4) != 0 )
      {
        Data1 |= 4u;
        v14[22].Data1 = Data1;
      }
      v49 = *((_BYTE *)a2 + 25) & 0x30;
      if ( v49 )
      {
        switch ( v49 )
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
LABEL_69:
            v50 = *((_BYTE *)a2 + 25) & 0xC0;
            switch ( v50 )
            {
              case 0:
LABEL_74:
                v14[22].Data1 = Data1;
                break;
              case 0x40:
                Data1 |= 0x40u;
                goto LABEL_74;
              case 0x80:
                Data1 |= 0x80u;
                goto LABEL_74;
            }
LABEL_75:
            v51 = 2;
            if ( v61 )
            {
              v52 = *((_BYTE *)v61 + 3);
              switch ( v52 )
              {
                case 5:
                  v47 = 6;
                  break;
                case 4:
                  v47 = 5;
                  break;
                case 2:
                  v47 = 3;
                  break;
                case 3:
                  v47 = 4;
                  break;
              }
              v53 = *((_BYTE *)v61 + 5);
              if ( v53 == 1 )
              {
                v51 = 1;
              }
              else if ( v53 == 5 )
              {
                v51 = 3;
              }
            }
            LOBYTE(v14[23].Data1) = -127;
            v14[23].Data1 = v14[23].Data1 & 0xF80C26FF | (((v47 << 7) | v51 & 0xFFFFF01F) << 15) | 0xC2600;
            v54 = *((unsigned __int8 *)a2 + 21);
            v55 = *(unsigned __int16 *)(v11 + 5);
            if ( (v54 & 7) != 0 )
              v55 *= v54 >> 3;
            *(_DWORD *)&v14[23].Data4[4] = v55;
            v14[24].Data1 = *(unsigned __int16 *)(v11 + 7);
            v14[24].Data2 = 1;
            v14[24].Data3 = *((unsigned __int8 *)a2 + 21);
            *(_DWORD *)v14[24].Data4 = *(_DWORD *)((char *)a2 + 5);
            *(_DWORD *)&v14[24].Data4[4] = *(unsigned __int16 *)(v11 + 5)
                                         * *(unsigned __int16 *)(v11 + 7)
                                         * *((unsigned __int8 *)a2 + 21)
                                         / 8;
LABEL_94:
            v14[4].Data4[4] = *((_BYTE *)a2 + 3);
            v14[4].Data4[5] = v11[3];
            *(_DWORD *)v14[3].Data4 = 1;
            *(_QWORD *)&v14[4].Data1 = 0;
            *(_DWORD *)v14[4].Data4 = 0;
            v14[4].Data4[7] = 1;
            v14[4].Data4[6] = ((_DWORD)v31[3] & 0x10) == 0;
            *a6 = v14;
            return 0;
        }
      }
      v14[22].Data1 = Data1;
      goto LABEL_69;
    }
    *(_QWORD *)&v14[18].Data1 = *(unsigned int *)(v11 + 30);
    v22 = *(_DWORD *)(v11 + 34);
    v23 = *(_DWORD *)(v11 + 30);
    v24 = *(_DWORD *)(v11 + 26);
    v62 = v22;
    if ( v22 )
    {
      v25 = (v23 - v24) / v22 + 1;
    }
    else
    {
      if ( v23 != v24 )
        return 3221225473LL;
      v25 = 1;
    }
    Size = 4LL * v25;
    v26 = ExAllocatePoolWithTag((POOL_TYPE)1536, Size, 0x56425355u);
    v27 = v26;
    if ( v26 )
    {
      if ( !ExPoolZeroingNativelySupported )
        memset(v26, 0, Size);
      v28 = KsAddItemToObjectBag(this[2], v27, FreeMem);
      if ( v28 < 0 )
      {
        ExFreePoolWithTag(v27, 0x56425355u);
        return (unsigned int)v28;
      }
      v29 = 0;
      if ( v25 )
      {
        v30 = v62;
        do
        {
          *((_DWORD *)v27 + v29) = *(_DWORD *)(v11 + 26) + v29 * v30;
          v29 = (unsigned int)(v29 + 1);
        }
        while ( (unsigned int)v29 < v25 );
      }
      v31 = this;
      *(_QWORD *)v14[2].Data4 = v27;
      v14[3].Data1 = v25;
      v32 = *(_DWORD *)(v11 + 30);
      goto LABEL_45;
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14003f580  mov     [rsp+arg_10], r8
0x14003f585  mov     [rsp+arg_0], rcx
0x14003f58a  push    rbx
0x14003f58b  push    rbp
0x14003f58c  push    rsi
0x14003f58d  push    rdi
0x14003f58e  push    r12
0x14003f590  push    r13
0x14003f592  push    r14
0x14003f594  push    r15
0x14003f596  sub     rsp, 48h
0x14003f59a  mov     r14, rcx
0x14003f59d  mov     ebp, 1
0x14003f5a2  movzx   ecx, byte ptr [rdx+16h]
0x14003f5a6  mov     rsi, rdx
0x14003f5a9  mov     r8b, bpl
0x14003f5ac  mov     edx, r9d
0x14003f5af  mov     r12d, r9d
0x14003f5b2  call    GetFrameIndex
0x14003f5b7  mov     r10d, eax
0x14003f5ba  movzx   eax, byte ptr [rsi+4]
0x14003f5be  cmp     r10d, eax
0x14003f5c1  jbe     short loc_14003F605
0x14003f5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f5ca  lea     rdx, WPP_GLOBAL_Control
0x14003f5d1  cmp     rcx, rdx
0x14003f5d4  jz      loc_14003FD73
0x14003f5da  lea     edx, [rbp+1]
0x14003f5dd  cmp     [rcx+29h], dl
0x14003f5e0  jb      loc_14003FD73
0x14003f5e6  mov     rcx, [rcx+18h]
0x14003f5ea  lea     edx, [rbp+9]
0x14003f5ed  mov     r9d, r10d
0x14003f5f0  mov     [rsp+88h+var_68], eax
0x14003f5f4  lea     r8, WPP_5c1996b9c3ee3482b8470e48b3ef8bf2_Traceguids
0x14003f5fb  call    WPP_SF_dd
0x14003f600  jmp     loc_14003FD73
0x14003f605  movzx   edi, byte ptr [rsi]
0x14003f608  and     r12b, bpl
0x14003f60b  add     rdi, rsi
0x14003f60e  mov     ecx, ebp
0x14003f610  cmp     r10d, ebp
0x14003f613  jbe     short loc_14003F622
0x14003f615  movzx   eax, byte ptr [rdi]
0x14003f618  add     ecx, ebp
0x14003f61a  add     rdi, rax
0x14003f61d  cmp     ecx, r10d
0x14003f620  jb      short loc_14003F615
0x14003f622  xor     r15d, r15d
0x14003f625  mov     ebp, 56425355h
0x14003f62a  mov     r13d, 600h
0x14003f630  mov     r8d, ebp; Tag
0x14003f633  mov     ecx, r13d; PoolType
0x14003f636  test    r12b, r12b
0x14003f639  jz      short loc_14003F665
0x14003f63b  mov     edx, 1A0h; NumberOfBytes
0x14003f640  call    cs:__imp_ExAllocatePoolWithTag
0x14003f647  nop     dword ptr [rax+rax+00h]
0x14003f64c  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x14003f653  mov     rbx, rax
0x14003f656  jnz     short loc_14003F697
0x14003f658  test    rax, rax
0x14003f65b  jz      short loc_14003F697
0x14003f65d  mov     r8d, 1A0h
0x14003f663  jmp     short loc_14003F68D
0x14003f665  mov     edx, 188h; NumberOfBytes
0x14003f66a  call    cs:__imp_ExAllocatePoolWithTag
0x14003f671  nop     dword ptr [rax+rax+00h]
0x14003f676  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x14003f67d  mov     rbx, rax
0x14003f680  jnz     short loc_14003F697
0x14003f682  test    rax, rax
0x14003f685  jz      short loc_14003F697
0x14003f687  mov     r8d, 188h; Size
0x14003f68d  xor     edx, edx; Val
0x14003f68f  mov     rcx, rax; void *
0x14003f692  call    memset
0x14003f697  test    rbx, rbx
0x14003f69a  jz      loc_14003FD7A
0x14003f6a0  mov     rcx, [r14+10h]; ObjectBag
0x14003f6a4  lea     r8, FreeMem; Free
0x14003f6ab  mov     rdx, rbx; Item
0x14003f6ae  call    cs:__imp_KsAddItemToObjectBag
0x14003f6b5  nop     dword ptr [rax+rax+00h]
0x14003f6ba  mov     r14d, eax
0x14003f6bd  mov     rcx, rbx; void *
0x14003f6c0  test    eax, eax
0x14003f6c2  jns     short loc_14003F6DA
0x14003f6c4  mov     edx, ebp; Tag
0x14003f6c6  call    cs:__imp_ExFreePoolWithTag
0x14003f6cd  nop     dword ptr [rax+rax+00h]
0x14003f6d2  mov     eax, r14d
0x14003f6d5  jmp     loc_14003FD7F
0x14003f6da  xor     edx, edx; Val
0x14003f6dc  mov     r8d, 1A0h
0x14003f6e2  test    r12b, r12b
0x14003f6e5  jnz     short loc_14003F6ED
0x14003f6e7  mov     r8d, 188h; Size
0x14003f6ed  call    memset
0x14003f6f2  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14003f6f9  mov     r9d, 1
0x14003f6ff  mov     [rbx+51h], r9b
0x14003f703  mov     [rbx+0A0h], r9d
0x14003f70a  movzx   ecx, word ptr [rdi+5]
0x14003f70e  movzx   eax, word ptr [rdi+7]
0x14003f712  imul    eax, ecx
0x14003f715  movzx   ecx, byte ptr [rsi+15h]
0x14003f719  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003f71e  imul    eax, ecx
0x14003f721  lea     ecx, [r9+7]
0x14003f725  cdq
0x14003f726  idiv    ecx
0x14003f728  mov     [rbx+68h], eax
0x14003f72b  movups  xmm0, xmmword ptr [rsi+5]
0x14003f72f  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003f737  test    r12b, r12b
0x14003f73a  jz      short loc_14003F75C
0x14003f73c  movups  xmm0, xmmword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1
0x14003f743  mov     dword ptr [rbx+60h], 140h
0x14003f74a  movdqu  xmmword ptr [rbx+90h], xmm0
0x14003f752  movdqu  xmmword ptr [rbx+0B0h], xmm0
0x14003f75a  jmp     short loc_14003F781
0x14003f75c  mov     dword ptr [rbx+60h], 128h
0x14003f763  movups  xmm0, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003f76a  movdqu  xmmword ptr [rbx+90h], xmm0
0x14003f772  movups  xmm1, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003f779  movdqu  xmmword ptr [rbx+0B0h], xmm1
0x14003f781  mov     [rbx+0C0h], r15d
0x14003f788  movzx   eax, word ptr [rdi+5]
0x14003f78c  mov     [rbx+0C4h], eax
0x14003f792  movzx   eax, word ptr [rdi+7]
0x14003f796  mov     [rbx+0C8h], eax
0x14003f79c  movzx   eax, word ptr [rdi+5]
0x14003f7a0  mov     [rbx+0CCh], eax
0x14003f7a6  movzx   eax, word ptr [rdi+7]
0x14003f7aa  mov     [rbx+0D0h], eax
0x14003f7b0  movzx   eax, word ptr [rdi+5]
0x14003f7b4  mov     [rbx+0D4h], eax
0x14003f7ba  movzx   eax, word ptr [rdi+7]
0x14003f7be  mov     [rbx+0D8h], eax
0x14003f7c4  mov     [rbx+0DCh], r9d
0x14003f7cb  mov     [rbx+0E0h], r9d
0x14003f7d2  mov     [rbx+0E4h], r9d
0x14003f7d9  mov     [rbx+0E8h], r9d
0x14003f7e0  movzx   eax, word ptr [rdi+5]
0x14003f7e4  mov     [rbx+0ECh], eax
0x14003f7ea  movzx   eax, word ptr [rdi+7]
0x14003f7ee  mov     [rbx+0F0h], eax
0x14003f7f4  movzx   eax, word ptr [rdi+5]
0x14003f7f8  mov     [rbx+0F4h], eax
0x14003f7fe  movzx   eax, word ptr [rdi+7]
0x14003f802  mov     [rbx+0F8h], eax
0x14003f808  mov     [rbx+0FCh], r9d
0x14003f80f  mov     [rbx+100h], r9d
0x14003f816  mov     eax, [rdi+9]
0x14003f819  mov     [rbx+128h], eax
0x14003f81f  mov     eax, [rdi+0Dh]
0x14003f822  mov     [rbx+12Ch], eax
0x14003f828  movzx   ecx, byte ptr [rdi+19h]
0x14003f82c  mov     eax, [rdi+1Ah]
0x14003f82f  mov     [rbx+118h], rax
0x14003f836  test    cl, cl
0x14003f838  jnz     loc_14003F948
0x14003f83e  mov     eax, [rdi+1Eh]
0x14003f841  mov     [rbx+120h], rax
0x14003f848  mov     r8d, [rdi+22h]
0x14003f84c  mov     eax, [rdi+1Eh]
0x14003f84f  mov     ecx, [rdi+1Ah]
0x14003f852  mov     [rsp+88h+arg_18], r8d
0x14003f85a  test    r8d, r8d
0x14003f85d  jnz     short loc_14003F872
0x14003f85f  cmp     eax, ecx
0x14003f861  jz      short loc_14003F86D
0x14003f863  mov     eax, 0C0000001h
0x14003f868  jmp     loc_14003FD7F
0x14003f86d  mov     r15d, r9d
0x14003f870  jmp     short loc_14003F87D
0x14003f872  sub     eax, ecx
0x14003f874  xor     edx, edx
0x14003f876  div     r8d
0x14003f879  lea     r15d, [r9+rax]
0x14003f87d  mov     eax, r15d
0x14003f880  mov     r8d, ebp; Tag
0x14003f883  shl     rax, 2
0x14003f887  mov     ecx, r13d; PoolType
0x14003f88a  mov     rdx, rax; NumberOfBytes
0x14003f88d  mov     [rsp+88h+Size], rax
0x14003f895  call    cs:__imp_ExAllocatePoolWithTag
0x14003f89c  nop     dword ptr [rax+rax+00h]
0x14003f8a1  mov     r14, rax
0x14003f8a4  test    rax, rax
0x14003f8a7  jz      loc_14003FD7A
0x14003f8ad  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14003f8b4  jnz     short loc_14003F8C8
0x14003f8b6  mov     r8, [rsp+88h+Size]; Size
0x14003f8be  xor     edx, edx; Val
0x14003f8c0  mov     rcx, rax; void *
0x14003f8c3  call    memset
0x14003f8c8  mov     rcx, [rsp+88h+arg_0]
0x14003f8d0  lea     r8, FreeMem; Free
0x14003f8d7  mov     rdx, r14; Item
0x14003f8da  mov     rcx, [rcx+10h]; ObjectBag
0x14003f8de  call    cs:__imp_KsAddItemToObjectBag
0x14003f8e5  nop     dword ptr [rax+rax+00h]
0x14003f8ea  mov     r13d, eax
0x14003f8ed  test    eax, eax
0x14003f8ef  jns     short loc_14003F90A
0x14003f8f1  mov     edx, ebp; Tag
0x14003f8f3  mov     rcx, r14; P
0x14003f8f6  call    cs:__imp_ExFreePoolWithTag
0x14003f8fd  nop     dword ptr [rax+rax+00h]
0x14003f902  mov     eax, r13d
0x14003f905  jmp     loc_14003FD7F
0x14003f90a  xor     edx, edx
0x14003f90c  lea     ebp, [rdx+1]
0x14003f90f  test    r15d, r15d
0x14003f912  jz      short loc_14003F930
0x14003f914  mov     r8d, [rsp+88h+arg_18]
0x14003f91c  mov     ecx, r8d
0x14003f91f  imul    ecx, edx
0x14003f922  add     ecx, [rdi+1Ah]
0x14003f925  mov     [r14+rdx*4], ecx
0x14003f929  add     edx, ebp
0x14003f92b  cmp     edx, r15d
0x14003f92e  jb      short loc_14003F91C
0x14003f930  mov     r13, [rsp+88h+arg_0]
0x14003f938  mov     [rbx+28h], r14
0x14003f93c  mov     [rbx+30h], r15d
0x14003f940  mov     eax, [rdi+1Eh]
0x14003f943  jmp     loc_14003FA23
0x14003f948  mov     eax, ecx
0x14003f94a  mov     [rsp+88h+arg_18], ecx
0x14003f951  dec     eax
0x14003f953  mov     r15, rcx
0x14003f956  mov     [rsp+88h+var_58], rax
0x14003f95b  mov     r8d, ebp; Tag
0x14003f95e  shl     r15, 2
0x14003f962  mov     ecx, r13d; PoolType
0x14003f965  mov     rdx, r15; NumberOfBytes
0x14003f968  mov     [rsp+88h+Size], r15
0x14003f970  mov     eax, [rdi+rax*4+1Ah]
0x14003f974  mov     [rbx+120h], rax
0x14003f97b  call    cs:__imp_ExAllocatePoolWithTag
0x14003f982  nop     dword ptr [rax+rax+00h]
0x14003f987  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14003f98e  mov     r14, rax
0x14003f991  jnz     short loc_14003F9AB
0x14003f993  test    rax, rax
0x14003f996  jz      loc_14003FD7A
0x14003f99c  mov     r8, r15; Size
0x14003f99f  xor     edx, edx; Val
0x14003f9a1  mov     rcx, rax; void *
0x14003f9a4  call    memset
0x14003f9a9  jmp     short loc_14003F9B4
0x14003f9ab  test    r14, r14
0x14003f9ae  jz      loc_14003FD7A
0x14003f9b4  mov     r13, [rsp+88h+arg_0]
0x14003f9bc  lea     r8, FreeMem; Free
0x14003f9c3  mov     rdx, r14; Item
0x14003f9c6  mov     rcx, [r13+10h]; ObjectBag
0x14003f9ca  call    cs:__imp_KsAddItemToObjectBag
0x14003f9d1  nop     dword ptr [rax+rax+00h]
0x14003f9d6  mov     r15d, eax
0x14003f9d9  mov     rcx, r14; void *
0x14003f9dc  test    eax, eax
0x14003f9de  jns     short loc_14003F9F6
0x14003f9e0  mov     edx, ebp; Tag
0x14003f9e2  call    cs:__imp_ExFreePoolWithTag
0x14003f9e9  nop     dword ptr [rax+rax+00h]
0x14003f9ee  mov     eax, r15d
0x14003f9f1  jmp     loc_14003FD7F
0x14003f9f6  mov     r8, [rsp+88h+Size]; Size
0x14003f9fe  lea     rdx, [rdi+1Ah]; Src
0x14003fa02  call    memmove
0x14003fa07  mov     eax, [rsp+88h+arg_18]
0x14003fa0e  mov     ebp, 1
0x14003fa13  mov     [rbx+30h], eax
0x14003fa16  mov     rax, [rsp+88h+var_58]
0x14003fa1b  mov     [rbx+28h], r14
0x14003fa1f  mov     eax, [rdi+rax*4+1Ah]
0x14003fa23  mov     [rbx+34h], eax
0x14003fa26  mov     rcx, [rbx+120h]
0x14003fa2d  mov     rax, [rbx+118h]
0x14003fa34  cmp     rax, rcx
0x14003fa37  jle     short loc_14003FA68
0x14003fa39  mov     rcx, cs:WPP_GLOBAL_Control
0x14003fa40  lea     rdx, WPP_GLOBAL_Control
0x14003fa47  cmp     rcx, rdx
0x14003fa4a  jz      loc_14003FD73
0x14003fa50  mov     edx, 2
0x14003fa55  cmp     [rcx+29h], dl
0x14003fa58  jb      loc_14003FD73
0x14003fa5e  mov     edx, 0Bh
0x14003fa63  jmp     loc_14003FD63
0x14003fa68  test    rax, rax
0x14003fa6b  jz      loc_14003FD41
0x14003fa71  test    rcx, rcx
0x14003fa74  jz      loc_14003FD41
0x14003fa7a  mov     ecx, [rdi+15h]
0x14003fa7d  test    ecx, ecx
  ... truncated ...
```
