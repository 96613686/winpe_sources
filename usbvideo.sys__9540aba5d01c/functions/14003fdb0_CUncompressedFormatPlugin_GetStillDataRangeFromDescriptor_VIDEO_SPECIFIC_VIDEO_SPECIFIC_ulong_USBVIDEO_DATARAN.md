# CUncompressedFormatPlugin::GetStillDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,_USBVIDEO_DATARANGE * *)

- ea: `0x14003fdb0`
- end: `0x14004006d`
- name: `?GetStillDataRangeFromDescriptor@CUncompressedFormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `701`
- prototype: `__int64 __fastcall(CUncompressedFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004bac`
- `0x14001b3e4`
- `0x14003fdb0`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe64`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe64`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003fe0f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003fe0f`
- `ks!KsAddItemToObjectBag` at `0x14003fe4a`
- `ks!KsAddItemToObjectBag` at `0x14003fe4a`

## pseudocode

```c
__int64 __fastcall CUncompressedFormatPlugin::GetStillDataRangeFromDescriptor(
        KSOBJECT_BAG *this,
        struct VIDEO_SPECIFIC *a2,
        struct VIDEO_SPECIFIC *a3,
        unsigned int a4,
        GUID **a5)
{
  int FrameIndex; // eax
  __int64 v8; // r10
  unsigned __int8 v9; // bp
  __int64 v10; // r9
  int v11; // r14d
  unsigned int v12; // esi
  GUID *PoolWithTag; // rax
  GUID *v14; // rbx
  NTSTATUS v15; // edi
  int v17; // eax
  int v18; // eax
  int v19; // eax

  FrameIndex = GetFrameIndex(1, a4, 0);
  v9 = FrameIndex;
  v10 = (unsigned int)(FrameIndex - 1);
  v11 = *(unsigned __int16 *)(v8 + 4 * v10 + 5);
  if ( (_WORD)v11 )
  {
    v12 = *(unsigned __int16 *)(v8 + 4 * v10 + 7);
    if ( (_WORD)v12 )
    {
      PoolWithTag = (GUID *)ExAllocatePoolWithTag((POOL_TYPE)1536, 0x188u, 0x56425355u);
      v14 = PoolWithTag;
      if ( ExPoolZeroingNativelySupported )
      {
        if ( PoolWithTag )
        {
LABEL_6:
          v15 = KsAddItemToObjectBag(this[2], v14, FreeMem);
          if ( v15 >= 0 )
          {
            memset(v14, 0, 0x188u);
            v14[6].Data1 = 296;
            v14[10].Data1 = 1;
            v17 = v12 * *((unsigned __int8 *)a3 + 21);
            v14[7] = GUID_73646976_0000_0010_8000_00aa00389b71;
            *(_DWORD *)v14[6].Data4 = v11 * v17 / 8;
            v14[8] = *(GUID *)((char *)a3 + 5);
            v14[9] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
            v14[12].Data1 = 0;
            *(_DWORD *)&v14[12].Data2 = v11;
            v14[11] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
            *(_DWORD *)v14[12].Data4 = v12;
            *(_DWORD *)&v14[12].Data4[4] = v11;
            v14[13].Data1 = v12;
            *(_DWORD *)&v14[13].Data2 = v11;
            *(_DWORD *)v14[13].Data4 = v12;
            *(_DWORD *)&v14[13].Data4[4] = 1;
            v14[14].Data1 = 1;
            *(_DWORD *)&v14[14].Data2 = 1;
            *(_DWORD *)v14[14].Data4 = 1;
            *(_DWORD *)&v14[14].Data4[4] = v11;
            v14[15].Data1 = v12;
            *(_DWORD *)&v14[15].Data2 = v11;
            *(_DWORD *)v14[15].Data4 = v12;
            *(_DWORD *)&v14[15].Data4[4] = 1;
            v14[16].Data1 = 1;
            *(_DWORD *)v14[18].Data4 = v11 * v12 * *((unsigned __int8 *)a3 + 21);
            v18 = v12 * *((unsigned __int8 *)a3 + 21);
            *(_QWORD *)v14[17].Data4 = 10000000;
            *(_QWORD *)&v14[18].Data1 = 10000000;
            *(_DWORD *)&v14[18].Data4[4] = v11 * v18;
            v19 = *((unsigned __int8 *)a3 + 21);
            *(_QWORD *)v14[21].Data4 = 10000000;
            v14[22].Data1 = 40;
            *(_DWORD *)&v14[22].Data2 = v11;
            *(_DWORD *)v14[22].Data4 = v12;
            *(_WORD *)&v14[22].Data4[4] = 1;
            v14[21].Data1 = v11 * v12 * v19;
            *(_WORD *)&v14[22].Data4[6] = *((unsigned __int8 *)a3 + 21);
            v14[23].Data1 = *(_DWORD *)((char *)a3 + 5);
            *(_DWORD *)&v14[23].Data2 = (int)(v11 * v12 * *((unsigned __int8 *)a3 + 21)) / 8;
            v14[4].Data4[4] = *((_BYTE *)a3 + 3);
            v14[4].Data4[5] = v9;
            *(_DWORD *)v14[3].Data4 = 1;
            *(_QWORD *)&v14[4].Data1 = 0;
            *(_DWORD *)v14[4].Data4 = 0;
            *a5 = v14;
            return 0;
          }
          else
          {
            ExFreePoolWithTag(v14, 0x56425355u);
            return (unsigned int)v15;
          }
        }
      }
      else if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, 0x188u);
        goto LABEL_6;
      }
      return 3221225626LL;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_5c1996b9c3ee3482b8470e48b3ef8bf2_Traceguids);
  return 3221225473LL;
}

```

## disassembly

```asm
0x14003fdb0  push    rbx
0x14003fdb2  push    rbp
0x14003fdb3  push    rsi
0x14003fdb4  push    rdi
0x14003fdb5  push    r12
0x14003fdb7  push    r14
0x14003fdb9  push    r15
0x14003fdbb  sub     rsp, 20h
0x14003fdbf  mov     rdi, rcx
0x14003fdc2  mov     r15, r8
0x14003fdc5  xor     r8d, r8d
0x14003fdc8  mov     r10, rdx
0x14003fdcb  mov     edx, r9d
0x14003fdce  lea     ecx, [r8+1]
0x14003fdd2  call    GetFrameIndex
0x14003fdd7  xor     r12d, r12d
0x14003fdda  mov     ebp, eax
0x14003fddc  lea     r9d, [rax-1]
0x14003fde0  movzx   r14d, word ptr [r10+r9*4+5]
0x14003fde6  test    r14w, r14w
0x14003fdea  jz      loc_14004002A
0x14003fdf0  movzx   esi, word ptr [r10+r9*4+7]
0x14003fdf6  test    si, si
0x14003fdf9  jz      loc_14004002A
0x14003fdff  mov     edx, 188h; NumberOfBytes
0x14003fe04  mov     ecx, 600h; PoolType
0x14003fe09  mov     r8d, 56425355h; Tag
0x14003fe0f  call    cs:__imp_ExAllocatePoolWithTag
0x14003fe16  nop     dword ptr [rax+rax+00h]
0x14003fe1b  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x14003fe22  mov     rbx, rax
0x14003fe25  jnz     short loc_14003FE77
0x14003fe27  test    rax, rax
0x14003fe2a  jz      short loc_14003FE7C
0x14003fe2c  xor     edx, edx; Val
0x14003fe2e  mov     r8d, 188h; Size
0x14003fe34  mov     rcx, rax; void *
0x14003fe37  call    memset
0x14003fe3c  mov     rcx, [rdi+10h]; ObjectBag
0x14003fe40  lea     r8, FreeMem; Free
0x14003fe47  mov     rdx, rbx; Item
0x14003fe4a  call    cs:__imp_KsAddItemToObjectBag
0x14003fe51  nop     dword ptr [rax+rax+00h]
0x14003fe56  mov     edi, eax
0x14003fe58  mov     rcx, rbx; void *
0x14003fe5b  test    eax, eax
0x14003fe5d  jns     short loc_14003FE86
0x14003fe5f  mov     edx, 56425355h; Tag
0x14003fe64  call    cs:__imp_ExFreePoolWithTag
0x14003fe6b  nop     dword ptr [rax+rax+00h]
0x14003fe70  mov     eax, edi
0x14003fe72  jmp     loc_14004005D
0x14003fe77  test    rbx, rbx
0x14003fe7a  jnz     short loc_14003FE3C
0x14003fe7c  mov     eax, 0C000009Ah
0x14003fe81  jmp     loc_14004005D
0x14003fe86  xor     edx, edx; Val
0x14003fe88  mov     r8d, 188h; Size
0x14003fe8e  call    memset
0x14003fe93  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14003fe9a  mov     dword ptr [rbx+60h], 128h
0x14003fea1  mov     r10d, 1
0x14003fea7  mov     [rbx+0A0h], r10d
0x14003feae  mov     ecx, esi
0x14003feb0  movzx   eax, byte ptr [r15+15h]
0x14003feb5  imul    eax, esi
0x14003feb8  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003febd  lea     r9d, [r10+7]
0x14003fec1  imul    eax, r14d
0x14003fec5  cdq
0x14003fec6  idiv    r9d
0x14003fec9  mov     edx, 989680h
0x14003fece  mov     [rbx+68h], eax
0x14003fed1  movups  xmm0, xmmword ptr [r15+5]
0x14003fed6  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003fede  movups  xmm1, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003fee5  movdqu  xmmword ptr [rbx+90h], xmm1
0x14003feed  movups  xmm0, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003fef4  mov     [rbx+0C0h], r12d
0x14003fefb  mov     [rbx+0C4h], r14d
0x14003ff02  movdqu  xmmword ptr [rbx+0B0h], xmm0
0x14003ff0a  mov     [rbx+0C8h], ecx
0x14003ff10  mov     [rbx+0CCh], r14d
0x14003ff17  mov     [rbx+0D0h], ecx
0x14003ff1d  mov     [rbx+0D4h], r14d
0x14003ff24  mov     [rbx+0D8h], ecx
0x14003ff2a  mov     [rbx+0DCh], r10d
0x14003ff31  mov     [rbx+0E0h], r10d
0x14003ff38  mov     [rbx+0E4h], r10d
0x14003ff3f  mov     [rbx+0E8h], r10d
0x14003ff46  mov     [rbx+0ECh], r14d
0x14003ff4d  mov     [rbx+0F0h], ecx
0x14003ff53  mov     [rbx+0F4h], r14d
0x14003ff5a  mov     [rbx+0F8h], ecx
0x14003ff60  mov     [rbx+0FCh], r10d
0x14003ff67  mov     [rbx+100h], r10d
0x14003ff6e  movzx   eax, byte ptr [r15+15h]
0x14003ff73  imul    eax, esi
0x14003ff76  imul    eax, r14d
0x14003ff7a  mov     [rbx+128h], eax
0x14003ff80  movzx   eax, byte ptr [r15+15h]
0x14003ff85  imul    eax, esi
0x14003ff88  mov     [rbx+118h], rdx
0x14003ff8f  mov     [rbx+120h], rdx
0x14003ff96  imul    eax, r14d
0x14003ff9a  mov     [rbx+12Ch], eax
0x14003ffa0  movzx   eax, byte ptr [r15+15h]
0x14003ffa5  mov     [rbx+158h], rdx
0x14003ffac  imul    eax, esi
0x14003ffaf  mov     dword ptr [rbx+160h], 28h ; '('
0x14003ffb9  mov     [rbx+164h], r14d
0x14003ffc0  mov     [rbx+168h], ecx
0x14003ffc6  mov     [rbx+16Ch], r10w
0x14003ffce  imul    eax, r14d
0x14003ffd2  mov     [rbx+150h], eax
0x14003ffd8  movzx   eax, byte ptr [r15+15h]
0x14003ffdd  mov     [rbx+16Eh], ax
0x14003ffe4  mov     eax, [r15+5]
0x14003ffe8  mov     [rbx+170h], eax
0x14003ffee  movzx   eax, byte ptr [r15+15h]
0x14003fff3  imul    eax, esi
0x14003fff6  imul    eax, r14d
0x14003fffa  cdq
0x14003fffb  idiv    r9d
0x14003fffe  mov     [rbx+174h], eax
0x140040004  mov     al, [r15+3]
0x140040008  mov     [rbx+4Ch], al
0x14004000b  mov     rax, [rsp+58h+arg_20]
0x140040013  mov     [rbx+4Dh], bpl
0x140040017  mov     [rbx+38h], r10d
0x14004001b  mov     [rbx+40h], r12
0x14004001f  mov     [rbx+48h], r12d
0x140040023  mov     [rax], rbx
0x140040026  xor     eax, eax
0x140040028  jmp     short loc_14004005D
0x14004002a  mov     rcx, cs:WPP_GLOBAL_Control
0x140040031  lea     rax, WPP_GLOBAL_Control
0x140040038  cmp     rcx, rax
0x14004003b  jz      short loc_140040058
0x14004003d  cmp     byte ptr [rcx+29h], 2
0x140040041  jb      short loc_140040058
0x140040043  mov     rcx, [rcx+18h]
0x140040047  lea     r8, WPP_5c1996b9c3ee3482b8470e48b3ef8bf2_Traceguids
0x14004004e  mov     edx, 0Dh
0x140040053  call    WPP_SF_
0x140040058  mov     eax, 0C0000001h
0x14004005d  add     rsp, 20h
0x140040061  pop     r15
0x140040063  pop     r14
0x140040065  pop     r12
0x140040067  pop     rdi
0x140040068  pop     rsi
0x140040069  pop     rbp
0x14004006a  pop     rbx
0x14004006b  retn
```
