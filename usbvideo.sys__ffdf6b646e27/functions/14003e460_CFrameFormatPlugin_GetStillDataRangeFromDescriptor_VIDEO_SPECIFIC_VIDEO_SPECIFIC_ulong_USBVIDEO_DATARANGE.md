# CFrameFormatPlugin::GetStillDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,_USBVIDEO_DATARANGE * *)

- ea: `0x14003e460`
- end: `0x14003e71d`
- name: `?GetStillDataRangeFromDescriptor@CFrameFormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `701`
- prototype: `__int64 __fastcall(CFrameFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x14001b3e4`
- `0x14003e460`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003e514`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003e514`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e4bf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e4bf`
- `ks!KsAddItemToObjectBag` at `0x14003e4fa`
- `ks!KsAddItemToObjectBag` at `0x14003e4fa`

## pseudocode

```c
__int64 __fastcall CFrameFormatPlugin::GetStillDataRangeFromDescriptor(
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_f984283f434f3c712851591db66f6a90_Traceguids);
  return 3221225473LL;
}

```

## disassembly

```asm
0x14003e460  push    rbx
0x14003e462  push    rbp
0x14003e463  push    rsi
0x14003e464  push    rdi
0x14003e465  push    r12
0x14003e467  push    r14
0x14003e469  push    r15
0x14003e46b  sub     rsp, 20h
0x14003e46f  mov     rdi, rcx
0x14003e472  mov     r15, r8
0x14003e475  xor     r8d, r8d
0x14003e478  mov     r10, rdx
0x14003e47b  mov     edx, r9d
0x14003e47e  lea     ecx, [r8+1]
0x14003e482  call    GetFrameIndex
0x14003e487  xor     r12d, r12d
0x14003e48a  mov     ebp, eax
0x14003e48c  lea     r9d, [rax-1]
0x14003e490  movzx   r14d, word ptr [r10+r9*4+5]
0x14003e496  test    r14w, r14w
0x14003e49a  jz      loc_14003E6DA
0x14003e4a0  movzx   esi, word ptr [r10+r9*4+7]
0x14003e4a6  test    si, si
0x14003e4a9  jz      loc_14003E6DA
0x14003e4af  mov     edx, 188h; NumberOfBytes
0x14003e4b4  mov     ecx, 600h; PoolType
0x14003e4b9  mov     r8d, 56425355h; Tag
0x14003e4bf  call    cs:__imp_ExAllocatePoolWithTag
0x14003e4c6  nop     dword ptr [rax+rax+00h]
0x14003e4cb  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x14003e4d2  mov     rbx, rax
0x14003e4d5  jnz     short loc_14003E527
0x14003e4d7  test    rax, rax
0x14003e4da  jz      short loc_14003E52C
0x14003e4dc  xor     edx, edx; Val
0x14003e4de  mov     r8d, 188h; Size
0x14003e4e4  mov     rcx, rax; void *
0x14003e4e7  call    memset
0x14003e4ec  mov     rcx, [rdi+10h]; ObjectBag
0x14003e4f0  lea     r8, FreeMem; Free
0x14003e4f7  mov     rdx, rbx; Item
0x14003e4fa  call    cs:__imp_KsAddItemToObjectBag
0x14003e501  nop     dword ptr [rax+rax+00h]
0x14003e506  mov     edi, eax
0x14003e508  mov     rcx, rbx; void *
0x14003e50b  test    eax, eax
0x14003e50d  jns     short loc_14003E536
0x14003e50f  mov     edx, 56425355h; Tag
0x14003e514  call    cs:__imp_ExFreePoolWithTag
0x14003e51b  nop     dword ptr [rax+rax+00h]
0x14003e520  mov     eax, edi
0x14003e522  jmp     loc_14003E70D
0x14003e527  test    rbx, rbx
0x14003e52a  jnz     short loc_14003E4EC
0x14003e52c  mov     eax, 0C000009Ah
0x14003e531  jmp     loc_14003E70D
0x14003e536  xor     edx, edx; Val
0x14003e538  mov     r8d, 188h; Size
0x14003e53e  call    memset
0x14003e543  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14003e54a  mov     dword ptr [rbx+60h], 128h
0x14003e551  mov     r10d, 1
0x14003e557  mov     [rbx+0A0h], r10d
0x14003e55e  mov     ecx, esi
0x14003e560  movzx   eax, byte ptr [r15+15h]
0x14003e565  imul    eax, esi
0x14003e568  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003e56d  lea     r9d, [r10+7]
0x14003e571  imul    eax, r14d
0x14003e575  cdq
0x14003e576  idiv    r9d
0x14003e579  mov     edx, 989680h
0x14003e57e  mov     [rbx+68h], eax
0x14003e581  movups  xmm0, xmmword ptr [r15+5]
0x14003e586  movdqu  xmmword ptr [rbx+80h], xmm0
0x14003e58e  movups  xmm1, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003e595  movdqu  xmmword ptr [rbx+90h], xmm1
0x14003e59d  movups  xmm0, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003e5a4  mov     [rbx+0C0h], r12d
0x14003e5ab  mov     [rbx+0C4h], r14d
0x14003e5b2  movdqu  xmmword ptr [rbx+0B0h], xmm0
0x14003e5ba  mov     [rbx+0C8h], ecx
0x14003e5c0  mov     [rbx+0CCh], r14d
0x14003e5c7  mov     [rbx+0D0h], ecx
0x14003e5cd  mov     [rbx+0D4h], r14d
0x14003e5d4  mov     [rbx+0D8h], ecx
0x14003e5da  mov     [rbx+0DCh], r10d
0x14003e5e1  mov     [rbx+0E0h], r10d
0x14003e5e8  mov     [rbx+0E4h], r10d
0x14003e5ef  mov     [rbx+0E8h], r10d
0x14003e5f6  mov     [rbx+0ECh], r14d
0x14003e5fd  mov     [rbx+0F0h], ecx
0x14003e603  mov     [rbx+0F4h], r14d
0x14003e60a  mov     [rbx+0F8h], ecx
0x14003e610  mov     [rbx+0FCh], r10d
0x14003e617  mov     [rbx+100h], r10d
0x14003e61e  movzx   eax, byte ptr [r15+15h]
0x14003e623  imul    eax, esi
0x14003e626  imul    eax, r14d
0x14003e62a  mov     [rbx+128h], eax
0x14003e630  movzx   eax, byte ptr [r15+15h]
0x14003e635  imul    eax, esi
0x14003e638  mov     [rbx+118h], rdx
0x14003e63f  mov     [rbx+120h], rdx
0x14003e646  imul    eax, r14d
0x14003e64a  mov     [rbx+12Ch], eax
0x14003e650  movzx   eax, byte ptr [r15+15h]
0x14003e655  mov     [rbx+158h], rdx
0x14003e65c  imul    eax, esi
0x14003e65f  mov     dword ptr [rbx+160h], 28h ; '('
0x14003e669  mov     [rbx+164h], r14d
0x14003e670  mov     [rbx+168h], ecx
0x14003e676  mov     [rbx+16Ch], r10w
0x14003e67e  imul    eax, r14d
0x14003e682  mov     [rbx+150h], eax
0x14003e688  movzx   eax, byte ptr [r15+15h]
0x14003e68d  mov     [rbx+16Eh], ax
0x14003e694  mov     eax, [r15+5]
0x14003e698  mov     [rbx+170h], eax
0x14003e69e  movzx   eax, byte ptr [r15+15h]
0x14003e6a3  imul    eax, esi
0x14003e6a6  imul    eax, r14d
0x14003e6aa  cdq
0x14003e6ab  idiv    r9d
0x14003e6ae  mov     [rbx+174h], eax
0x14003e6b4  mov     al, [r15+3]
0x14003e6b8  mov     [rbx+4Ch], al
0x14003e6bb  mov     rax, [rsp+58h+arg_20]
0x14003e6c3  mov     [rbx+4Dh], bpl
0x14003e6c7  mov     [rbx+38h], r10d
0x14003e6cb  mov     [rbx+40h], r12
0x14003e6cf  mov     [rbx+48h], r12d
0x14003e6d3  mov     [rax], rbx
0x14003e6d6  xor     eax, eax
0x14003e6d8  jmp     short loc_14003E70D
0x14003e6da  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e6e1  lea     rax, WPP_GLOBAL_Control
0x14003e6e8  cmp     rcx, rax
0x14003e6eb  jz      short loc_14003E708
0x14003e6ed  cmp     byte ptr [rcx+29h], 2
0x14003e6f1  jb      short loc_14003E708
0x14003e6f3  mov     rcx, [rcx+18h]
0x14003e6f7  lea     r8, WPP_f984283f434f3c712851591db66f6a90_Traceguids
0x14003e6fe  mov     edx, 0Dh
0x14003e703  call    WPP_SF_
0x14003e708  mov     eax, 0C0000001h
0x14003e70d  add     rsp, 20h
0x14003e711  pop     r15
0x14003e713  pop     r14
0x14003e715  pop     r12
0x14003e717  pop     rdi
0x14003e718  pop     rsi
0x14003e719  pop     rbp
0x14003e71a  pop     rbx
0x14003e71b  retn
```
