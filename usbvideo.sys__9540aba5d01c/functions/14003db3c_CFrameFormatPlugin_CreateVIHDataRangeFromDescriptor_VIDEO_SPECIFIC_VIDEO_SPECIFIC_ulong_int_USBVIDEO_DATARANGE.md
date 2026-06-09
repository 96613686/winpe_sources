# CFrameFormatPlugin::CreateVIHDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,int,_USBVIDEO_DATARANGE * *)

- ea: `0x14003db3c`
- end: `0x14003e393`
- name: `?CreateVIHDataRangeFromDescriptor@CFrameFormatPlugin@@QEAAJPEAUVIDEO_SPECIFIC@@0KHPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `2135`
- prototype: `__int64 __fastcall(CFrameFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14003e3c0`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x14001b3e4`
- `0x14003c810`
- `0x14003db3c`
- `0x140040b40`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003dc8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ded8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dfc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dc8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ded8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003dfc6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003dc03`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003dc2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003de6b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003df5e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003dc03`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003dc2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003de6b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003df5e`
- `ks!KsAddItemToObjectBag` at `0x14003dc77`
- `ks!KsAddItemToObjectBag` at `0x14003debf`
- `ks!KsAddItemToObjectBag` at `0x14003dfad`
- `ks!KsAddItemToObjectBag` at `0x14003dc77`
- `ks!KsAddItemToObjectBag` at `0x14003debf`
- `ks!KsAddItemToObjectBag` at `0x14003dfad`

## pseudocode

```c
__int64 __fastcall CFrameFormatPlugin::CreateVIHDataRangeFromDescriptor(
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
  unsigned __int8 *v11; // rsi
  unsigned int i; // ecx
  GUID *PoolWithTag; // rax
  GUID *v14; // rbx
  size_t v15; // r8
  NTSTATUS v16; // edi
  size_t v17; // r8
  int v18; // eax
  int v19; // ecx
  __int64 v20; // rcx
  unsigned int v21; // r8d
  int v22; // eax
  int v23; // ecx
  unsigned int v24; // r15d
  PVOID v25; // rax
  void *v26; // rdi
  NTSTATUS v27; // r13d
  __int64 v29; // rdx
  unsigned int v30; // r8d
  KSOBJECT_BAG *v31; // r13
  int v32; // eax
  size_t v33; // r15
  PVOID v34; // rax
  void *v35; // rdi
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
  int v52; // r8d
  char v53; // al
  char v54; // al
  unsigned int v55; // ecx
  int v56; // eax
  unsigned int v57; // eax
  int v58; // ecx
  unsigned int v59; // eax
  int v60; // ecx
  __int64 v61; // [rsp+30h] [rbp-58h]
  __int64 Size; // [rsp+98h] [rbp+10h]
  struct VIDEO_SPECIFIC *v64; // [rsp+A0h] [rbp+18h]
  unsigned int v65; // [rsp+A8h] [rbp+20h] BYREF

  v64 = a3;
  LOBYTE(a3) = 1;
  v8 = a4;
  FrameIndex = GetFrameIndex(*((unsigned __int8 *)a2 + 22), a4, a3);
  if ( FrameIndex > *((unsigned __int8 *)a2 + 4) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_f984283f434f3c712851591db66f6a90_Traceguids,
        FrameIndex,
        *((unsigned __int8 *)a2 + 4));
    return (unsigned int)-1073741811;
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
    v17 = 416;
    if ( !v10 )
      v17 = 392;
    memset(v14, 0, v17);
    LOBYTE(v14[5].Data1) = *((_BYTE *)a2 + 27) == 0;
    v14[10].Data1 = *((_BYTE *)a2 + 27) == 0;
    v18 = *(unsigned __int16 *)(v11 + 5) * *(unsigned __int16 *)(v11 + 7);
    v19 = *((unsigned __int8 *)a2 + 21);
    v14[7] = GUID_73646976_0000_0010_8000_00aa00389b71;
    *(_DWORD *)v14[6].Data4 = v19 * v18 / 8;
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
    v20 = v11[21];
    *(_QWORD *)v14[17].Data4 = *(unsigned int *)(v11 + 26);
    if ( (_BYTE)v20 )
    {
      v65 = v20;
      v61 = (unsigned int)(v20 - 1);
      v33 = 4 * v20;
      Size = 4 * v20;
      *(_QWORD *)&v14[18].Data1 = *(unsigned int *)&v11[4 * v61 + 26];
      v34 = ExAllocatePoolWithTag((POOL_TYPE)1536, 4 * v20, 0x56425355u);
      v35 = v34;
      if ( ExPoolZeroingNativelySupported )
      {
        if ( !v34 )
          return (unsigned int)-1073741670;
      }
      else
      {
        if ( !v34 )
          return (unsigned int)-1073741670;
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
      v14[3].Data1 = v65;
      *(_QWORD *)v14[2].Data4 = v35;
      v32 = *(_DWORD *)&v11[4 * v61 + 26];
    }
    else
    {
      *(_QWORD *)&v14[18].Data1 = *(unsigned int *)(v11 + 30);
      v21 = *(_DWORD *)(v11 + 34);
      v22 = *(_DWORD *)(v11 + 30);
      v23 = *(_DWORD *)(v11 + 26);
      v65 = v21;
      if ( v21 )
      {
        v24 = (v22 - v23) / v21 + 1;
      }
      else
      {
        if ( v22 != v23 )
          return (unsigned int)-1073741823;
        v24 = 1;
      }
      v25 = ExAllocatePoolWithTag((POOL_TYPE)1536, 4LL * v24, 0x56425355u);
      v26 = v25;
      if ( ExPoolZeroingNativelySupported )
      {
        if ( !v25 )
          return (unsigned int)-1073741670;
      }
      else
      {
        if ( !v25 )
          return (unsigned int)-1073741670;
        memset(v25, 0, 4LL * v24);
      }
      v27 = KsAddItemToObjectBag(this[2], v26, FreeMem);
      if ( v27 < 0 )
      {
        ExFreePoolWithTag(v26, 0x56425355u);
        return (unsigned int)v27;
      }
      v29 = 0;
      if ( v24 )
      {
        v30 = v65;
        do
        {
          *((_DWORD *)v26 + v29) = *(_DWORD *)(v11 + 26) + v29 * v30;
          v29 = (unsigned int)(v29 + 1);
        }
        while ( (unsigned int)v29 < v24 );
      }
      v31 = this;
      *(_QWORD *)v14[2].Data4 = v26;
      v14[3].Data1 = v24;
      v32 = *(_DWORD *)(v11 + 30);
    }
    *(_DWORD *)&v14[3].Data2 = v32;
    v37 = *(_QWORD *)&v14[18].Data1;
    v38 = *(_QWORD *)v14[17].Data4;
    if ( v38 > v37 )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return (unsigned int)-1073741811;
      v40 = 11;
LABEL_102:
      WPP_SF_(v39->AttachedDevice, v40, WPP_f984283f434f3c712851591db66f6a90_Traceguids);
      return (unsigned int)-1073741811;
    }
    if ( !v38 || !v37 || (v41 = *(_DWORD *)(v11 + 17)) == 0 )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return (unsigned int)-1073741811;
      v40 = 12;
      goto LABEL_102;
    }
    v14[21].Data1 = *(unsigned __int16 *)(v11 + 5)
                  * *((unsigned __int8 *)a2 + 21)
                  * *(unsigned __int16 *)(v11 + 7)
                  * (0x989680
                   / v41);
    *(_QWORD *)v14[21].Data4 = *(unsigned int *)(v11 + 17);
    if ( !v10 )
    {
      v14[22].Data1 = 40;
      v59 = *((unsigned __int8 *)a2 + 21);
      v60 = *(unsigned __int16 *)(v11 + 5);
      if ( (v59 & 7) != 0 )
        v60 *= v59 >> 3;
      *(_DWORD *)&v14[22].Data2 = v60;
      *(_DWORD *)v14[22].Data4 = *(unsigned __int16 *)(v11 + 7);
      *(_WORD *)&v14[22].Data4[4] = 1;
      *(_WORD *)&v14[22].Data4[6] = *((unsigned __int8 *)a2 + 21);
      v14[23].Data1 = *(_DWORD *)((char *)a2 + 5);
      *(_DWORD *)&v14[23].Data2 = *(unsigned __int16 *)(v11 + 5)
                                * *(unsigned __int16 *)(v11 + 7)
                                * *((unsigned __int8 *)a2 + 21)
                                / 8;
      goto LABEL_98;
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
      v65 = 0;
      a5 = 0;
      ReduceToLowestTerms(v45, v44, &v65, &a5);
      v46 = v65;
      *(_DWORD *)&v14[22].Data4[4] = a5;
      *(_DWORD *)v14[22].Data4 = v46;
    }
    v47 = 2;
    *(_DWORD *)&v14[22].Data2 = *((_BYTE *)a2 + 26) == 1;
    if ( (*((_BYTE *)a2 + 25) & 1) == 0 )
      goto LABEL_77;
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
LABEL_71:
          v50 = *((_BYTE *)a2 + 25) & 0xC0;
          switch ( v50 )
          {
            case 0:
LABEL_76:
              v14[22].Data1 = Data1;
              break;
            case 0x40:
              Data1 |= 0x40u;
              goto LABEL_76;
            case 0x80:
              Data1 |= 0x80u;
              goto LABEL_76;
          }
LABEL_77:
          v51 = 2;
          v52 = *(_DWORD *)((char *)a2 + 5);
          if ( v64 )
          {
            v53 = *((_BYTE *)v64 + 3);
            switch ( v53 )
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
            v54 = *((_BYTE *)v64 + 5);
            if ( v54 == 1 )
            {
              v51 = 1;
            }
            else if ( v54 == 5 )
            {
              v51 = 3;
            }
          }
          LOBYTE(v14[23].Data1) = -127;
          v55 = ((v47 << 7) | v51 & 0xFFFFF01F) << 15;
          v56 = 4096;
          if ( v52 != 1196444237 )
            v56 = 0x2000;
          v14[23].Data1 = v14[23].Data1 & 0xF80C06FF | v56 & 0xF80C7FFF | v55 | 0xC0600;
          v57 = *((unsigned __int8 *)a2 + 21);
          v58 = *(unsigned __int16 *)(v11 + 5);
          if ( (v57 & 7) != 0 )
            v58 *= v57 >> 3;
          *(_DWORD *)&v14[23].Data4[4] = v58;
          v14[24].Data1 = *(unsigned __int16 *)(v11 + 7);
          v14[24].Data2 = 1;
          v14[24].Data3 = *((unsigned __int8 *)a2 + 21);
          *(_DWORD *)v14[24].Data4 = *(_DWORD *)((char *)a2 + 5);
          *(_DWORD *)&v14[24].Data4[4] = *(unsigned __int16 *)(v11 + 5)
                                       * *(unsigned __int16 *)(v11 + 7)
                                       * *((unsigned __int8 *)a2 + 21)
                                       / 8;
LABEL_98:
          v14[4].Data4[4] = *((_BYTE *)a2 + 3);
          v14[4].Data4[5] = v11[3];
          *(_DWORD *)v14[3].Data4 = 1;
          *(_QWORD *)&v14[4].Data1 = 0;
          *(_DWORD *)v14[4].Data4 = 0;
          v14[4].Data4[7] = 1;
          v14[4].Data4[6] = ((_DWORD)v31[3] & 0x20) != 0;
          v16 = 0;
          *a6 = v14;
          return (unsigned int)v16;
      }
    }
    v14[22].Data1 = Data1;
    goto LABEL_71;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x14003db3c  mov     [rsp+arg_10], r8
0x14003db41  mov     [rsp+arg_0], rcx
0x14003db46  push    rbx
0x14003db47  push    rbp
0x14003db48  push    rsi
0x14003db49  push    rdi
0x14003db4a  push    r12
0x14003db4c  push    r13
0x14003db4e  push    r14
0x14003db50  push    r15
0x14003db52  sub     rsp, 48h
0x14003db56  mov     rdi, rcx
0x14003db59  mov     r14d, 1
0x14003db5f  movzx   ecx, byte ptr [rdx+16h]
0x14003db63  mov     rbp, rdx
0x14003db66  mov     r8b, r14b
0x14003db69  mov     edx, r9d
0x14003db6c  mov     r12d, r9d
0x14003db6f  call    GetFrameIndex
0x14003db74  mov     r10d, eax
0x14003db77  movzx   eax, byte ptr [rbp+4]
0x14003db7b  cmp     r10d, eax
0x14003db7e  jbe     short loc_14003DBC4
0x14003db80  mov     rcx, cs:WPP_GLOBAL_Control
0x14003db87  lea     rdx, WPP_GLOBAL_Control
0x14003db8e  cmp     rcx, rdx
0x14003db91  jz      loc_14003E37A
0x14003db97  lea     edx, [r14+1]
0x14003db9b  cmp     [rcx+29h], dl
0x14003db9e  jb      loc_14003E37A
0x14003dba4  mov     rcx, [rcx+18h]
0x14003dba8  lea     edx, [r14+9]
0x14003dbac  mov     r9d, r10d
0x14003dbaf  mov     [rsp+88h+var_68], eax
0x14003dbb3  lea     r8, WPP_f984283f434f3c712851591db66f6a90_Traceguids
0x14003dbba  call    WPP_SF_dd
0x14003dbbf  jmp     loc_14003E37A
0x14003dbc4  movzx   esi, byte ptr [rbp+0]
0x14003dbc8  and     r12b, r14b
0x14003dbcb  add     rsi, rbp
0x14003dbce  mov     ecx, r14d
0x14003dbd1  cmp     r10d, r14d
0x14003dbd4  jbe     short loc_14003DBE4
0x14003dbd6  movzx   eax, byte ptr [rsi]
0x14003dbd9  add     ecx, r14d
0x14003dbdc  add     rsi, rax
0x14003dbdf  cmp     ecx, r10d
0x14003dbe2  jb      short loc_14003DBD6
0x14003dbe4  xor     r15d, r15d
0x14003dbe7  mov     r14d, 56425355h
0x14003dbed  mov     r13d, 600h
0x14003dbf3  mov     r8d, r14d; Tag
0x14003dbf6  mov     ecx, r13d; PoolType
0x14003dbf9  test    r12b, r12b
0x14003dbfc  jz      short loc_14003DC28
0x14003dbfe  mov     edx, 1A0h; NumberOfBytes
0x14003dc03  call    cs:__imp_ExAllocatePoolWithTag
0x14003dc0a  nop     dword ptr [rax+rax+00h]
0x14003dc0f  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x14003dc16  mov     rbx, rax
0x14003dc19  jnz     short loc_14003DC5A
0x14003dc1b  test    rax, rax
0x14003dc1e  jz      short loc_14003DC5A
0x14003dc20  mov     r8d, 1A0h
0x14003dc26  jmp     short loc_14003DC50
0x14003dc28  mov     edx, 188h; NumberOfBytes
0x14003dc2d  call    cs:__imp_ExAllocatePoolWithTag
0x14003dc34  nop     dword ptr [rax+rax+00h]
0x14003dc39  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x14003dc40  mov     rbx, rax
0x14003dc43  jnz     short loc_14003DC5A
0x14003dc45  test    rax, rax
0x14003dc48  jz      short loc_14003DC5A
0x14003dc4a  mov     r8d, 188h; Size
0x14003dc50  xor     edx, edx; Val
0x14003dc52  mov     rcx, rax; void *
0x14003dc55  call    memset
0x14003dc5a  test    rbx, rbx
0x14003dc5d  jnz     short loc_14003DC69
0x14003dc5f  mov     edi, 0C000009Ah
0x14003dc64  jmp     loc_14003E37F
0x14003dc69  mov     rcx, [rdi+10h]; ObjectBag
0x14003dc6d  lea     r8, FreeMem; Free
0x14003dc74  mov     rdx, rbx; Item
0x14003dc77  call    cs:__imp_KsAddItemToObjectBag
0x14003dc7e  nop     dword ptr [rax+rax+00h]
0x14003dc83  mov     edi, eax
0x14003dc85  mov     rcx, rbx; void *
0x14003dc88  test    eax, eax
0x14003dc8a  jns     short loc_14003DCA0
0x14003dc8c  mov     edx, r14d; Tag
0x14003dc8f  call    cs:__imp_ExFreePoolWithTag
0x14003dc96  nop     dword ptr [rax+rax+00h]
0x14003dc9b  jmp     loc_14003E37F
0x14003dca0  xor     edx, edx; Val
0x14003dca2  mov     r8d, 1A0h
0x14003dca8  test    r12b, r12b
0x14003dcab  jnz     short loc_14003DCB3
0x14003dcad  mov     r8d, 188h; Size
0x14003dcb3  call    memset
0x14003dcb8  cmp     [rbp+1Bh], r15b
0x14003dcbc  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14003dcc3  setz    al
0x14003dcc6  mov     [rbx+50h], al
0x14003dcc9  mov     eax, r15d
0x14003dccc  cmp     [rbp+1Bh], r15b
0x14003dcd0  setz    al
0x14003dcd3  mov     [rbx+0A0h], eax
0x14003dcd9  movzx   ecx, word ptr [rsi+5]
0x14003dcdd  movzx   eax, word ptr [rsi+7]
0x14003dce1  imul    eax, ecx
0x14003dce4  movzx   ecx, byte ptr [rbp+15h]
0x14003dce8  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003dced  imul    eax, ecx
0x14003dcf0  mov     ecx, 8
0x14003dcf5  cdq
0x14003dcf6  idiv    ecx
0x14003dcf8  mov     [rbx+68h], eax
0x14003dcfb  movups  xmm0, xmmword ptr [rbp+5]
0x14003dcff  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003dd07  test    r12b, r12b
0x14003dd0a  jz      short loc_14003DD2C
0x14003dd0c  movups  xmm0, xmmword ptr cs:_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1
0x14003dd13  mov     dword ptr [rbx+60h], 140h
0x14003dd1a  movdqu  xmmword ptr [rbx+90h], xmm0
0x14003dd22  movdqu  xmmword ptr [rbx+0B0h], xmm0
0x14003dd2a  jmp     short loc_14003DD51
0x14003dd2c  mov     dword ptr [rbx+60h], 128h
0x14003dd33  movups  xmm0, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003dd3a  movdqu  xmmword ptr [rbx+90h], xmm0
0x14003dd42  movups  xmm1, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003dd49  movdqu  xmmword ptr [rbx+0B0h], xmm1
0x14003dd51  mov     [rbx+0C0h], r15d
0x14003dd58  mov     r9d, 1
0x14003dd5e  movzx   eax, word ptr [rsi+5]
0x14003dd62  mov     [rbx+0C4h], eax
0x14003dd68  movzx   eax, word ptr [rsi+7]
0x14003dd6c  mov     [rbx+0C8h], eax
0x14003dd72  movzx   eax, word ptr [rsi+5]
0x14003dd76  mov     [rbx+0CCh], eax
0x14003dd7c  movzx   eax, word ptr [rsi+7]
0x14003dd80  mov     [rbx+0D0h], eax
0x14003dd86  movzx   eax, word ptr [rsi+5]
0x14003dd8a  mov     [rbx+0D4h], eax
0x14003dd90  movzx   eax, word ptr [rsi+7]
0x14003dd94  mov     [rbx+0D8h], eax
0x14003dd9a  mov     [rbx+0DCh], r9d
0x14003dda1  mov     [rbx+0E0h], r9d
0x14003dda8  mov     [rbx+0E4h], r9d
0x14003ddaf  mov     [rbx+0E8h], r9d
0x14003ddb6  movzx   eax, word ptr [rsi+5]
0x14003ddba  mov     [rbx+0ECh], eax
0x14003ddc0  movzx   eax, word ptr [rsi+7]
0x14003ddc4  mov     [rbx+0F0h], eax
0x14003ddca  movzx   eax, word ptr [rsi+5]
0x14003ddce  mov     [rbx+0F4h], eax
0x14003ddd4  movzx   eax, word ptr [rsi+7]
0x14003ddd8  mov     [rbx+0F8h], eax
0x14003ddde  mov     [rbx+0FCh], r9d
0x14003dde5  mov     [rbx+100h], r9d
0x14003ddec  mov     eax, [rsi+9]
0x14003ddef  mov     [rbx+128h], eax
0x14003ddf5  mov     eax, [rsi+0Dh]
0x14003ddf8  mov     [rbx+12Ch], eax
0x14003ddfe  movzx   ecx, byte ptr [rsi+15h]
0x14003de02  mov     eax, [rsi+1Ah]
0x14003de05  mov     [rbx+118h], rax
0x14003de0c  test    cl, cl
0x14003de0e  jnz     loc_14003DF2B
0x14003de14  mov     eax, [rsi+1Eh]
0x14003de17  mov     [rbx+120h], rax
0x14003de1e  mov     r8d, [rsi+22h]
0x14003de22  mov     eax, [rsi+1Eh]
0x14003de25  mov     ecx, [rsi+1Ah]
0x14003de28  mov     [rsp+88h+arg_18], r8d
0x14003de30  test    r8d, r8d
0x14003de33  jnz     short loc_14003DE48
0x14003de35  cmp     eax, ecx
0x14003de37  jz      short loc_14003DE43
0x14003de39  mov     edi, 0C0000001h
0x14003de3e  jmp     loc_14003E37F
0x14003de43  mov     r15d, r9d
0x14003de46  jmp     short loc_14003DE53
0x14003de48  sub     eax, ecx
0x14003de4a  xor     edx, edx
0x14003de4c  div     r8d
0x14003de4f  lea     r15d, [r9+rax]
0x14003de53  mov     eax, r15d
0x14003de56  mov     r8d, r14d; Tag
0x14003de59  shl     rax, 2
0x14003de5d  mov     ecx, r13d; PoolType
0x14003de60  mov     rdx, rax; NumberOfBytes
0x14003de63  mov     [rsp+88h+Size], rax
0x14003de6b  call    cs:__imp_ExAllocatePoolWithTag
0x14003de72  nop     dword ptr [rax+rax+00h]
0x14003de77  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14003de7e  mov     rdi, rax
0x14003de81  jnz     short loc_14003DEA0
0x14003de83  test    rax, rax
0x14003de86  jz      loc_14003DC5F
0x14003de8c  mov     r8, [rsp+88h+Size]; Size
0x14003de94  xor     edx, edx; Val
0x14003de96  mov     rcx, rax; void *
0x14003de99  call    memset
0x14003de9e  jmp     short loc_14003DEA9
0x14003dea0  test    rdi, rdi
0x14003dea3  jz      loc_14003DC5F
0x14003dea9  mov     rcx, [rsp+88h+arg_0]
0x14003deb1  lea     r8, FreeMem; Free
0x14003deb8  mov     rdx, rdi; Item
0x14003debb  mov     rcx, [rcx+10h]; ObjectBag
0x14003debf  call    cs:__imp_KsAddItemToObjectBag
0x14003dec6  nop     dword ptr [rax+rax+00h]
0x14003decb  mov     r13d, eax
0x14003dece  test    eax, eax
0x14003ded0  jns     short loc_14003DEEC
0x14003ded2  mov     edx, r14d; Tag
0x14003ded5  mov     rcx, rdi; P
0x14003ded8  call    cs:__imp_ExFreePoolWithTag
0x14003dedf  nop     dword ptr [rax+rax+00h]
0x14003dee4  mov     eax, r13d
0x14003dee7  jmp     loc_14003E381
0x14003deec  xor     edx, edx
0x14003deee  lea     r14d, [rdx+1]
0x14003def2  test    r15d, r15d
0x14003def5  jz      short loc_14003DF13
0x14003def7  mov     r8d, [rsp+88h+arg_18]
0x14003deff  mov     ecx, r8d
0x14003df02  imul    ecx, edx
0x14003df05  add     ecx, [rsi+1Ah]
0x14003df08  mov     [rdi+rdx*4], ecx
0x14003df0b  add     edx, r14d
0x14003df0e  cmp     edx, r15d
0x14003df11  jb      short loc_14003DEFF
0x14003df13  mov     r13, [rsp+88h+arg_0]
0x14003df1b  mov     [rbx+28h], rdi
0x14003df1f  mov     [rbx+30h], r15d
0x14003df23  mov     eax, [rsi+1Eh]
0x14003df26  jmp     loc_14003E008
0x14003df2b  mov     eax, ecx
0x14003df2d  mov     [rsp+88h+arg_18], ecx
0x14003df34  dec     eax
0x14003df36  mov     r15, rcx
0x14003df39  mov     [rsp+88h+var_58], rax
0x14003df3e  mov     r8d, r14d; Tag
0x14003df41  shl     r15, 2
0x14003df45  mov     ecx, r13d; PoolType
0x14003df48  mov     rdx, r15; NumberOfBytes
0x14003df4b  mov     [rsp+88h+Size], r15
0x14003df53  mov     eax, [rsi+rax*4+1Ah]
0x14003df57  mov     [rbx+120h], rax
0x14003df5e  call    cs:__imp_ExAllocatePoolWithTag
0x14003df65  nop     dword ptr [rax+rax+00h]
0x14003df6a  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14003df71  mov     rdi, rax
0x14003df74  jnz     short loc_14003DF8E
0x14003df76  test    rax, rax
0x14003df79  jz      loc_14003DC5F
0x14003df7f  mov     r8, r15; Size
0x14003df82  xor     edx, edx; Val
0x14003df84  mov     rcx, rax; void *
0x14003df87  call    memset
0x14003df8c  jmp     short loc_14003DF97
0x14003df8e  test    rdi, rdi
0x14003df91  jz      loc_14003DC5F
0x14003df97  mov     r13, [rsp+88h+arg_0]
0x14003df9f  lea     r8, FreeMem; Free
0x14003dfa6  mov     rdx, rdi; Item
0x14003dfa9  mov     rcx, [r13+10h]; ObjectBag
0x14003dfad  call    cs:__imp_KsAddItemToObjectBag
0x14003dfb4  nop     dword ptr [rax+rax+00h]
0x14003dfb9  mov     r15d, eax
0x14003dfbc  mov     rcx, rdi; void *
0x14003dfbf  test    eax, eax
0x14003dfc1  jns     short loc_14003DFDA
0x14003dfc3  mov     edx, r14d; Tag
0x14003dfc6  call    cs:__imp_ExFreePoolWithTag
0x14003dfcd  nop     dword ptr [rax+rax+00h]
0x14003dfd2  mov     eax, r15d
0x14003dfd5  jmp     loc_14003E381
0x14003dfda  mov     r8, [rsp+88h+Size]; Size
0x14003dfe2  lea     rdx, [rsi+1Ah]; Src
0x14003dfe6  call    memmove
0x14003dfeb  mov     eax, [rsp+88h+arg_18]
0x14003dff2  mov     r14d, 1
0x14003dff8  mov     [rbx+30h], eax
0x14003dffb  mov     rax, [rsp+88h+var_58]
0x14003e000  mov     [rbx+28h], rdi
0x14003e004  mov     eax, [rsi+rax*4+1Ah]
0x14003e008  mov     [rbx+34h], eax
0x14003e00b  mov     rcx, [rbx+120h]
0x14003e012  mov     rax, [rbx+118h]
0x14003e019  cmp     rax, rcx
0x14003e01c  jle     short loc_14003E04D
0x14003e01e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e025  lea     rdx, WPP_GLOBAL_Control
0x14003e02c  cmp     rcx, rdx
0x14003e02f  jz      loc_14003E37A
0x14003e035  mov     edx, 2
0x14003e03a  cmp     [rcx+29h], dl
  ... truncated ...
```
