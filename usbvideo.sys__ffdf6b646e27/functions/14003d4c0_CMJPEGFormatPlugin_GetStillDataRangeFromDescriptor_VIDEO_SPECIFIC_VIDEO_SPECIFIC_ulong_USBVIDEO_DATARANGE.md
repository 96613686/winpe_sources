# CMJPEGFormatPlugin::GetStillDataRangeFromDescriptor(VIDEO_SPECIFIC *,VIDEO_SPECIFIC *,ulong,_USBVIDEO_DATARANGE * *)

- ea: `0x14003d4c0`
- end: `0x14003d735`
- name: `?GetStillDataRangeFromDescriptor@CMJPEGFormatPlugin@@UEAAJPEAUVIDEO_SPECIFIC@@0KPEAPEAU_USBVIDEO_DATARANGE@@@Z`
- size: `629`
- prototype: `__int64 __fastcall(CMJPEGFormatPlugin *__hidden this, struct VIDEO_SPECIFIC *, struct VIDEO_SPECIFIC *, unsigned int, struct _USBVIDEO_DATARANGE **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x14001b3e4`
- `0x14003d4c0`
- `0x140040e40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003d574`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d574`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d51f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003d51f`
- `ks!KsAddItemToObjectBag` at `0x14003d55a`
- `ks!KsAddItemToObjectBag` at `0x14003d55a`

## pseudocode

```c
__int64 __fastcall CMJPEGFormatPlugin::GetStillDataRangeFromDescriptor(
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
  int v17; // ecx

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
            v14[7] = GUID_73646976_0000_0010_8000_00aa00389b71;
            v14[8] = MEDIASUBTYPE_MJPG;
            v17 = 24 * v11 * v12;
            *(_DWORD *)v14[6].Data4 = v17 / 8;
            v14[9] = GUID_05589f80_c356_11ce_bf01_00aa0055595a;
            *(_DWORD *)&v14[23].Data2 = v17 / 8;
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
            *(_DWORD *)v14[18].Data4 = v17;
            *(_DWORD *)&v14[18].Data4[4] = v17;
            *(_QWORD *)v14[17].Data4 = 10000000;
            *(_QWORD *)&v14[18].Data1 = 10000000;
            v14[21].Data1 = v17;
            *(_QWORD *)v14[21].Data4 = 10000000;
            v14[22].Data1 = 40;
            *(_DWORD *)&v14[22].Data2 = v11;
            *(_DWORD *)v14[22].Data4 = v12;
            *(_DWORD *)&v14[22].Data4[4] = 1572865;
            v14[23].Data1 = 1196444237;
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_427f7f479e5f364e8bc738df4327e74b_Traceguids);
  return 3221225473LL;
}

```

## disassembly

```asm
0x14003d4c0  push    rbx
0x14003d4c2  push    rbp
0x14003d4c3  push    rsi
0x14003d4c4  push    rdi
0x14003d4c5  push    r12
0x14003d4c7  push    r14
0x14003d4c9  push    r15
0x14003d4cb  sub     rsp, 20h
0x14003d4cf  mov     rdi, rcx
0x14003d4d2  mov     r15, r8
0x14003d4d5  xor     r8d, r8d
0x14003d4d8  mov     r10, rdx
0x14003d4db  mov     edx, r9d
0x14003d4de  lea     ecx, [r8+1]
0x14003d4e2  call    GetFrameIndex
0x14003d4e7  xor     r12d, r12d
0x14003d4ea  mov     ebp, eax
0x14003d4ec  lea     r9d, [rax-1]
0x14003d4f0  movzx   r14d, word ptr [r10+r9*4+5]
0x14003d4f6  test    r14w, r14w
0x14003d4fa  jz      loc_14003D6F2
0x14003d500  movzx   esi, word ptr [r10+r9*4+7]
0x14003d506  test    si, si
0x14003d509  jz      loc_14003D6F2
0x14003d50f  mov     edx, 188h; NumberOfBytes
0x14003d514  mov     ecx, 600h; PoolType
0x14003d519  mov     r8d, 56425355h; Tag
0x14003d51f  call    cs:__imp_ExAllocatePoolWithTag
0x14003d526  nop     dword ptr [rax+rax+00h]
0x14003d52b  cmp     cs:ExPoolZeroingNativelySupported, r12b
0x14003d532  mov     rbx, rax
0x14003d535  jnz     short loc_14003D587
0x14003d537  test    rax, rax
0x14003d53a  jz      short loc_14003D58C
0x14003d53c  xor     edx, edx; Val
0x14003d53e  mov     r8d, 188h; Size
0x14003d544  mov     rcx, rax; void *
0x14003d547  call    memset
0x14003d54c  mov     rcx, [rdi+10h]; ObjectBag
0x14003d550  lea     r8, FreeMem; Free
0x14003d557  mov     rdx, rbx; Item
0x14003d55a  call    cs:__imp_KsAddItemToObjectBag
0x14003d561  nop     dword ptr [rax+rax+00h]
0x14003d566  mov     edi, eax
0x14003d568  mov     rcx, rbx; void *
0x14003d56b  test    eax, eax
0x14003d56d  jns     short loc_14003D596
0x14003d56f  mov     edx, 56425355h; Tag
0x14003d574  call    cs:__imp_ExFreePoolWithTag
0x14003d57b  nop     dword ptr [rax+rax+00h]
0x14003d580  mov     eax, edi
0x14003d582  jmp     loc_14003D725
0x14003d587  test    rbx, rbx
0x14003d58a  jnz     short loc_14003D54C
0x14003d58c  mov     eax, 0C000009Ah
0x14003d591  jmp     loc_14003D725
0x14003d596  xor     edx, edx; Val
0x14003d598  mov     r8d, 188h; Size
0x14003d59e  call    memset
0x14003d5a3  movups  xmm0, xmmword ptr cs:_GUID_73646976_0000_0010_8000_00aa00389b71.Data1
0x14003d5aa  mov     dword ptr [rbx+60h], 128h
0x14003d5b1  mov     eax, esi
0x14003d5b3  movups  xmm1, xmmword ptr cs:MEDIASUBTYPE_MJPG.Data1
0x14003d5ba  mov     r10d, 8
0x14003d5c0  imul    eax, r14d
0x14003d5c4  movdqu  xmmword ptr [rbx+70h], xmm0
0x14003d5c9  movdqu  xmmword ptr [rbx+80h], xmm1
0x14003d5d1  lea     ecx, [rax+rax*2]
0x14003d5d4  shl     ecx, 3
0x14003d5d7  mov     eax, ecx
0x14003d5d9  cdq
0x14003d5da  idiv    r10d
0x14003d5dd  mov     r10d, 1
0x14003d5e3  mov     edx, 989680h
0x14003d5e8  mov     [rbx+68h], eax
0x14003d5eb  movups  xmm0, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003d5f2  movdqu  xmmword ptr [rbx+90h], xmm0
0x14003d5fa  movups  xmm1, xmmword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x14003d601  mov     [rbx+174h], eax
0x14003d607  mov     [rbx+0C4h], r14d
0x14003d60e  movdqu  xmmword ptr [rbx+0B0h], xmm1
0x14003d616  mov     [rbx+0C8h], esi
0x14003d61c  mov     [rbx+0CCh], r14d
0x14003d623  mov     [rbx+0D0h], esi
0x14003d629  mov     [rbx+0D4h], r14d
0x14003d630  mov     [rbx+0D8h], esi
0x14003d636  mov     [rbx+0DCh], r10d
0x14003d63d  mov     [rbx+0E0h], r10d
0x14003d644  mov     [rbx+0E4h], r10d
0x14003d64b  mov     [rbx+0E8h], r10d
0x14003d652  mov     [rbx+0ECh], r14d
0x14003d659  mov     [rbx+0F0h], esi
0x14003d65f  mov     [rbx+0F4h], r14d
0x14003d666  mov     [rbx+0F8h], esi
0x14003d66c  mov     [rbx+0FCh], r10d
0x14003d673  mov     [rbx+100h], r10d
0x14003d67a  mov     [rbx+128h], ecx
0x14003d680  mov     [rbx+12Ch], ecx
0x14003d686  mov     [rbx+118h], rdx
0x14003d68d  mov     [rbx+120h], rdx
0x14003d694  mov     [rbx+150h], ecx
0x14003d69a  mov     [rbx+158h], rdx
0x14003d6a1  mov     dword ptr [rbx+160h], 28h ; '('
0x14003d6ab  mov     [rbx+164h], r14d
0x14003d6b2  mov     [rbx+168h], esi
0x14003d6b8  mov     dword ptr [rbx+16Ch], 180001h
0x14003d6c2  mov     dword ptr [rbx+170h], 47504A4Dh
0x14003d6cc  mov     al, [r15+3]
0x14003d6d0  mov     [rbx+4Ch], al
0x14003d6d3  mov     rax, [rsp+58h+arg_20]
0x14003d6db  mov     [rbx+4Dh], bpl
0x14003d6df  mov     [rbx+38h], r10d
0x14003d6e3  mov     [rbx+40h], r12
0x14003d6e7  mov     [rbx+48h], r12d
0x14003d6eb  mov     [rax], rbx
0x14003d6ee  xor     eax, eax
0x14003d6f0  jmp     short loc_14003D725
0x14003d6f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d6f9  lea     rax, WPP_GLOBAL_Control
0x14003d700  cmp     rcx, rax
0x14003d703  jz      short loc_14003D720
0x14003d705  cmp     byte ptr [rcx+29h], 2
0x14003d709  jb      short loc_14003D720
0x14003d70b  mov     rcx, [rcx+18h]
0x14003d70f  lea     r8, WPP_427f7f479e5f364e8bc738df4327e74b_Traceguids
0x14003d716  mov     edx, 0Dh
0x14003d71b  call    WPP_SF_
0x14003d720  mov     eax, 0C0000001h
0x14003d725  add     rsp, 20h
0x14003d729  pop     r15
0x14003d72b  pop     r14
0x14003d72d  pop     r12
0x14003d72f  pop     rdi
0x14003d730  pop     rsi
0x14003d731  pop     rbp
0x14003d732  pop     rbx
0x14003d733  retn
```
