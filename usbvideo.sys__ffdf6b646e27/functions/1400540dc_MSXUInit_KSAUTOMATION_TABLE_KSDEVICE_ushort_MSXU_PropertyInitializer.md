# MSXUInit(KSAUTOMATION_TABLE_ * *,_KSDEVICE *,ushort,MSXU_PropertyInitializer *)

- ea: `0x1400540dc`
- end: `0x1400547f6`
- name: `?MSXUInit@@YAJPEAPEAUKSAUTOMATION_TABLE_@@PEAU_KSDEVICE@@GPEAUMSXU_PropertyInitializer@@@Z`
- size: `1818`
- prototype: `__int64 __fastcall(struct KSAUTOMATION_TABLE_ **, struct _KSDEVICE *, unsigned __int16, struct MSXU_PropertyInitializer *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1400547fc`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140008640`
- `0x140010d84`
- `0x140019d34`
- `0x14001ab4c`
- `0x14001b118`
- `0x14003b0fc`
- `0x14003bcf8`
- `0x140040a70`
- `0x140040e40`
- `0x1400540dc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140054413`
- `ntoskrnl!ExFreePoolWithTag` at `0x140054413`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054364`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054364`
- `ks!KsAddItemToObjectBag` at `0x1400543f1`
- `ks!KsAddItemToObjectBag` at `0x1400543f1`
- `ks!KsRemoveItemFromObjectBag` at `0x1400547c7`
- `ks!KsRemoveItemFromObjectBag` at `0x1400547c7`

## pseudocode

```c
__int64 __fastcall MSXUInit(
        struct KSAUTOMATION_TABLE_ **a1,
        struct _KSDEVICE *a2,
        unsigned __int16 a3,
        struct MSXU_PropertyInitializer *a4)
{
  int v4; // ebx
  struct MSXU_PropertyInitializer *v5; // rsi
  struct _KSDEVICE *v6; // rbp
  __int64 v8; // r13
  unsigned __int16 v9; // r15
  __int64 v10; // r12
  __int64 v11; // rax
  unsigned __int8 v12; // r14
  int v13; // eax
  int appended; // edi
  __int64 v15; // rbx
  __int64 v16; // rbp
  int v17; // eax
  unsigned int v18; // edi
  PVOID PoolWithTag; // rax
  void *v20; // rbx
  NTSTATUS v21; // eax
  __int64 v22; // r14
  int i; // ebx
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v27; // eax
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r13
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // r13
  __int64 v35; // rcx
  __int64 v36; // r9
  __int64 v37; // rbx
  int v39; // [rsp+20h] [rbp-E8h]
  int v40; // [rsp+20h] [rbp-E8h]
  int v41; // [rsp+20h] [rbp-E8h]
  size_t Size; // [rsp+30h] [rbp-D8h]
  size_t Sizea; // [rsp+30h] [rbp-D8h]
  size_t Sizeb; // [rsp+30h] [rbp-D8h]
  char v45; // [rsp+80h] [rbp-88h]
  unsigned __int16 v46; // [rsp+84h] [rbp-84h] BYREF
  int v47; // [rsp+88h] [rbp-80h]
  __int64 v48; // [rsp+90h] [rbp-78h]
  PDEVICE_OBJECT v49; // [rsp+98h] [rbp-70h]
  __int64 v50; // [rsp+A0h] [rbp-68h]
  _QWORD *Context; // [rsp+A8h] [rbp-60h]
  __int64 v52; // [rsp+B0h] [rbp-58h]
  struct KSAUTOMATION_TABLE_ **v53; // [rsp+110h] [rbp+8h] BYREF
  struct _KSDEVICE *v54; // [rsp+118h] [rbp+10h]
  unsigned __int16 v55; // [rsp+120h] [rbp+18h]
  struct MSXU_PropertyInitializer *v56; // [rsp+128h] [rbp+20h]

  v56 = a4;
  v55 = a3;
  v54 = a2;
  v53 = a1;
  v4 = *((unsigned __int16 *)a4 + 5);
  v5 = a4;
  LOBYTE(v53) = 0;
  v6 = a2;
  v46 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 304, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a2, a3);
  v9 = a3 << 8;
  Context = v6->Context;
  v8 = (__int64)Context;
  v10 = Context[110];
  LODWORD(Size) = 2;
  v11 = *(_QWORD *)(v10 + 32);
  v52 = v10;
  v45 = *(_BYTE *)(v10 + 40);
  LOBYTE(v39) = v45;
  LOBYTE(v47) = *(_BYTE *)(v11 + 3);
  v12 = v47;
  v13 = SubmitControlRequest(0xA1u, 0x85u, a3 << 8, v47, v39, (unsigned __int8 *)&v46, Size, v10, (__int64)Context);
  appended = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          305,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          (unsigned int)v13);
      goto LABEL_67;
    }
LABEL_72:
    v37 = v55;
    KsRemoveItemFromObjectBag(v54->Bag, *(PVOID *)(v8 + 8LL * v55 + 952), 1u);
    *(_QWORD *)(v8 + 8 * v37 + 952) = 0;
    return (unsigned int)appended;
  }
  if ( (_WORD)v4 != 0xFFFF && (_WORD)v4 != v46 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 306, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v46, v4);
    appended = -1073741823;
    goto LABEL_67;
  }
  v15 = v55;
  LODWORD(Sizea) = 1;
  v16 = v55;
  *(_WORD *)(v8 + 2LL * v55 + 1224) = v46;
  LOBYTE(v40) = v45;
  v17 = SubmitControlRequest(0xA1u, 0x86u, v9, v12, v40, (unsigned __int8 *)&v53, Sizea, v10, v8);
  appended = v17;
  if ( v17 >= 0 )
  {
    if ( ((unsigned __int8)v53 & *((_BYTE *)v5 + 8)) != *((_BYTE *)v5 + 9) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          308,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          (unsigned __int8)v53);
      appended = -1073741823;
      goto LABEL_18;
    }
    *(_BYTE *)(v8 + v15 + 1258) = (_BYTE)v53;
    v18 = 4 * v46;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1536, v18, 0x56425355u);
    v20 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v18);
    *(_QWORD *)(v8 + 8 * v16 + 952) = v20;
    if ( !v20 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 309, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
      appended = -1073741670;
      goto LABEL_32;
    }
    v21 = KsAddItemToObjectBag(v54->Bag, v20, FreeMem);
    v22 = *(_QWORD *)(v8 + 8 * v16 + 952);
    appended = v21;
    if ( v21 < 0 )
    {
      ExFreePoolWithTag(*(PVOID *)(v8 + 8 * v16 + 952), 0x56425355u);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 310, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
        goto LABEL_32;
      }
      goto LABEL_72;
    }
    for ( i = 0; i < 4; ++i )
    {
      LODWORD(Sizeb) = v46;
      v48 = i;
      LOBYTE(v41) = v45;
      v24 = SubmitControlRequest(
              0xA1u,
              *((_BYTE *)&qword_1400480B0 + i),
              v9,
              v47,
              v41,
              (unsigned __int8 *)(v22 + i * v46),
              Sizeb,
              v10,
              v8);
      appended = v24;
      if ( v24 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_72;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_sD(WPP_GLOBAL_Control->AttachedDevice, v25, v26, (unsigned int)off_140045B18[v48], v24);
        goto LABEL_32;
      }
    }
    v27 = (*((__int64 (__fastcall **)(__int64, __int64, _QWORD))v5 + 2))(v8, v22, v46);
    appended = v27;
    if ( v27 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_72;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_32:
        v6 = v54;
LABEL_67:
        LOWORD(v15) = v55;
        goto LABEL_68;
      }
      v29 = 312;
      goto LABEL_48;
    }
    if ( ((unsigned __int8)v53 & 2) != 0 )
    {
      LODWORD(Sizeb) = v46;
      LOBYTE(v41) = v45;
      v27 = SubmitControlRequest(
              0x21u,
              1u,
              v9,
              v47,
              v41,
              (unsigned __int8 *)(v22 + 2 * (unsigned int)v46),
              Sizeb,
              v10,
              v8);
      appended = v27;
      if ( v27 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_72;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_32;
        v29 = 313;
LABEL_48:
        WPP_SF_d(v28->AttachedDevice, v29, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v27);
        goto LABEL_32;
      }
      *(_DWORD *)(v8 + 4 * v16 + 1276) = 0;
    }
    v30 = *(_QWORD *)v5;
    if ( **(_DWORD **)v5 )
    {
      v31 = 0;
      LODWORD(v48) = 0;
      do
      {
        v32 = *(_QWORD *)(v30 + 8);
        v33 = 5 * v31;
        v50 = 5 * v31;
        if ( *(_DWORD *)(v32 + 40 * v31 + 8) )
        {
          v34 = 0;
          do
          {
            v49 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              v35 = *(_QWORD *)(v30 + 8);
              v36 = *(_QWORD *)(v35 + 8 * v33);
              WPP_SF_DDDDDDDDDDDd(
                v49->AttachedDevice,
                9 * v34,
                *(unsigned __int8 *)(v36 + 15),
                *(_DWORD *)v36,
                *(_WORD *)(v36 + 4),
                *(_WORD *)(v36 + 6),
                *(_BYTE *)(v36 + 8),
                *(_BYTE *)(v36 + 9),
                *(_BYTE *)(v36 + 10),
                *(_BYTE *)(v36 + 11),
                *(_BYTE *)(v36 + 12),
                *(_BYTE *)(v36 + 13),
                *(_BYTE *)(v36 + 14),
                *(_BYTE *)(v36 + 15),
                *(_DWORD *)(*(_QWORD *)(v35 + 8 * v33 + 16) + 72 * v34));
              v33 = v50;
              v5 = v56;
            }
            v30 = *(_QWORD *)v5;
            v34 = (unsigned int)(v34 + 1);
          }
          while ( (unsigned int)v34 < *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 8LL) + 8 * v33 + 8) );
          LODWORD(v31) = v48;
        }
        v31 = (unsigned int)(v31 + 1);
        LODWORD(v48) = v31;
      }
      while ( (unsigned int)v31 < *(_DWORD *)v30 );
      v8 = (__int64)Context;
      v10 = v52;
    }
    v6 = v54;
    appended = AppendAutomationTable(v10 + 24, v30, v54->Bag);
    goto LABEL_67;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_72;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      307,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      (unsigned int)v17);
LABEL_18:
  v6 = v54;
LABEL_68:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      315,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      v6,
      (unsigned __int16)v15,
      appended);
  if ( appended < 0 )
    goto LABEL_72;
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400540dc  mov     rax, rsp
0x1400540df  mov     [rax+20h], r9
0x1400540e3  mov     [rax+18h], r8w
0x1400540e8  mov     [rax+10h], rdx
0x1400540ec  mov     [rax+8], rcx
0x1400540f0  push    rbx
0x1400540f1  push    rbp
0x1400540f2  push    rsi
0x1400540f3  push    rdi
0x1400540f4  push    r12
0x1400540f6  push    r13
0x1400540f8  push    r14
0x1400540fa  push    r15
0x1400540fc  sub     rsp, 0C8h
0x140054103  movzx   ebx, word ptr [r9+0Ah]
0x140054108  mov     rsi, r9
0x14005410b  mov     byte ptr [rax+8], 0
0x14005410f  mov     rbp, rdx
0x140054112  xor     eax, eax
0x140054114  movzx   edi, r8w
0x140054118  mov     [rsp+108h+var_84], ax
0x140054120  mov     rcx, cs:WPP_GLOBAL_Control
0x140054127  lea     rax, WPP_GLOBAL_Control
0x14005412e  cmp     rcx, rax
0x140054131  jz      short loc_140054155
0x140054133  cmp     byte ptr [rcx+29h], 4
0x140054137  jb      short loc_140054155
0x140054139  mov     rcx, [rcx+18h]
0x14005413d  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140054144  mov     edx, 130h
0x140054149  mov     [rsp+108h+var_E8], edi
0x14005414d  mov     r9, rbp
0x140054150  call    WPP_SF_qD
0x140054155  mov     r13, [rbp+10h]
0x140054159  lea     rcx, [rsp+108h+var_84]
0x140054161  mov     [rsp+108h+var_C8], r13; __int64
0x140054166  movzx   r15d, di
0x14005416a  shl     r15w, 8
0x14005416f  mov     dl, 85h; int
0x140054171  movzx   r8d, r15w; int
0x140054175  mov     [rsp+108h+var_60], r13
0x14005417d  mov     r12, [r13+370h]
0x140054184  mov     [rsp+108h+var_D0], r12; __int64
0x140054189  mov     dword ptr [rsp+108h+Size], 2; Size
0x140054191  mov     [rsp+108h+var_E0], rcx; void *
0x140054196  mov     cl, 0A1h; int
0x140054198  mov     rax, [r12+20h]
0x14005419d  mov     [rsp+108h+var_58], r12
0x1400541a5  mov     r14b, [rax+3]
0x1400541a9  mov     al, [r12+28h]
0x1400541ae  mov     r9b, r14b; int
0x1400541b1  mov     byte ptr [rsp+108h+var_88], al
0x1400541b8  mov     byte ptr [rsp+108h+var_E8], al; int
0x1400541bc  mov     byte ptr [rsp+108h+var_80], r14b
0x1400541c4  call    SubmitControlRequest
0x1400541c9  mov     edi, eax
0x1400541cb  test    eax, eax
0x1400541cd  jns     short loc_14005420D
0x1400541cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400541d6  lea     rsi, WPP_GLOBAL_Control
0x1400541dd  cmp     rcx, rsi
0x1400541e0  jz      loc_1400547A8
0x1400541e6  cmp     byte ptr [rcx+29h], 2
0x1400541ea  jb      loc_140054767
0x1400541f0  mov     rcx, [rcx+18h]
0x1400541f4  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400541fb  mov     edx, 131h
0x140054200  mov     r9d, eax
0x140054203  call    WPP_SF_d
0x140054208  jmp     loc_140054767
0x14005420d  movzx   edx, [rsp+108h+var_84]
0x140054215  mov     eax, 0FFFFh
0x14005421a  cmp     bx, ax
0x14005421d  jz      short loc_140054263
0x14005421f  cmp     bx, dx
0x140054222  jz      short loc_140054263
0x140054224  mov     rcx, cs:WPP_GLOBAL_Control
0x14005422b  lea     rsi, WPP_GLOBAL_Control
0x140054232  cmp     rcx, rsi
0x140054235  jz      short loc_140054259
0x140054237  cmp     byte ptr [rcx+29h], 2
0x14005423b  jb      short loc_140054259
0x14005423d  mov     rcx, [rcx+18h]
0x140054241  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140054248  mov     r9d, edx
0x14005424b  mov     [rsp+108h+var_E8], ebx
0x14005424f  mov     edx, 132h
0x140054254  call    WPP_SF_dd
0x140054259  mov     edi, 0C0000001h
0x14005425e  jmp     loc_140054767
0x140054263  movzx   ebx, [rsp+108h+arg_10]
0x14005426b  lea     rax, [rsp+108h+arg_0]
0x140054273  mov     [rsp+108h+var_C8], r13; __int64
0x140054278  mov     r9b, r14b; int
0x14005427b  mov     [rsp+108h+var_D0], r12; __int64
0x140054280  movzx   r8d, r15w; int
0x140054284  mov     dword ptr [rsp+108h+Size], 1; Size
0x14005428c  mov     cl, 0A1h; int
0x14005428e  mov     [rsp+108h+var_E0], rax; void *
0x140054293  mov     ebp, ebx
0x140054295  mov     al, byte ptr [rsp+108h+var_88]
0x14005429c  mov     [r13+rbx*2+4C8h], dx
0x1400542a5  mov     dl, 86h; int
0x1400542a7  mov     byte ptr [rsp+108h+var_E8], al; int
0x1400542ab  call    SubmitControlRequest
0x1400542b0  mov     edi, eax
0x1400542b2  test    eax, eax
0x1400542b4  jns     short loc_1400542F8
0x1400542b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400542bd  lea     rsi, WPP_GLOBAL_Control
0x1400542c4  cmp     rcx, rsi
0x1400542c7  jz      loc_1400547A8
0x1400542cd  cmp     byte ptr [rcx+29h], 2
0x1400542d1  jb      short loc_1400542EB
0x1400542d3  mov     rcx, [rcx+18h]
0x1400542d7  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400542de  mov     edx, 133h
0x1400542e3  mov     r9d, eax
0x1400542e6  call    WPP_SF_d
0x1400542eb  mov     rbp, [rsp+108h+arg_8]
0x1400542f3  jmp     loc_14005476F
0x1400542f8  mov     al, [rsi+8]
0x1400542fb  movzx   edx, byte ptr [rsp+108h+arg_0]
0x140054303  and     al, dl
0x140054305  cmp     al, [rsi+9]
0x140054308  jz      short loc_140054342
0x14005430a  mov     rcx, cs:WPP_GLOBAL_Control
0x140054311  lea     rsi, WPP_GLOBAL_Control
0x140054318  cmp     rcx, rsi
0x14005431b  jz      short loc_14005433B
0x14005431d  cmp     byte ptr [rcx+29h], 2
0x140054321  jb      short loc_14005433B
0x140054323  mov     rcx, [rcx+18h]
0x140054327  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005432e  mov     r9d, edx
0x140054331  mov     edx, 134h
0x140054336  call    WPP_SF_d
0x14005433b  mov     edi, 0C0000001h
0x140054340  jmp     short loc_1400542EB
0x140054342  mov     [r13+rbx+4EAh], dl
0x14005434a  mov     r8d, 56425355h; Tag
0x140054350  movzx   eax, [rsp+108h+var_84]
0x140054358  mov     ecx, 600h; PoolType
0x14005435d  shl     eax, 2
0x140054360  mov     edx, eax; NumberOfBytes
0x140054362  mov     edi, eax
0x140054364  call    cs:__imp_ExAllocatePoolWithTag
0x14005436b  nop     dword ptr [rax+rax+00h]
0x140054370  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140054377  mov     rbx, rax
0x14005437a  jnz     short loc_14005438E
0x14005437c  test    rax, rax
0x14005437f  jz      short loc_14005438E
0x140054381  mov     r8d, edi; Size
0x140054384  xor     edx, edx; Val
0x140054386  mov     rcx, rax; void *
0x140054389  call    memset
0x14005438e  mov     [r13+rbp*8+3B8h], rbx
0x140054396  test    rbx, rbx
0x140054399  jnz     short loc_1400543DB
0x14005439b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400543a2  lea     rsi, WPP_GLOBAL_Control
0x1400543a9  cmp     rcx, rsi
0x1400543ac  jz      short loc_1400543C9
0x1400543ae  cmp     byte ptr [rcx+29h], 2
0x1400543b2  jb      short loc_1400543C9
0x1400543b4  mov     rcx, [rcx+18h]
0x1400543b8  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x1400543bf  mov     edx, 135h
0x1400543c4  call    WPP_SF_
0x1400543c9  mov     edi, 0C000009Ah
0x1400543ce  mov     rbp, [rsp+108h+arg_8]
0x1400543d6  jmp     loc_140054767
0x1400543db  mov     rcx, [rsp+108h+arg_8]
0x1400543e3  lea     r8, FreeMem; Free
0x1400543ea  mov     rdx, rbx; Item
0x1400543ed  mov     rcx, [rcx+8]; ObjectBag
0x1400543f1  call    cs:__imp_KsAddItemToObjectBag
0x1400543f8  nop     dword ptr [rax+rax+00h]
0x1400543fd  mov     r14, [r13+rbp*8+3B8h]
0x140054405  mov     edi, eax
0x140054407  test    eax, eax
0x140054409  jns     short loc_140054456
0x14005440b  mov     edx, 56425355h; Tag
0x140054410  mov     rcx, r14; P
0x140054413  call    cs:__imp_ExFreePoolWithTag
0x14005441a  nop     dword ptr [rax+rax+00h]
0x14005441f  mov     rcx, cs:WPP_GLOBAL_Control
0x140054426  lea     rsi, WPP_GLOBAL_Control
0x14005442d  cmp     rcx, rsi
0x140054430  jz      loc_1400547A8
0x140054436  cmp     byte ptr [rcx+29h], 2
0x14005443a  jb      short loc_1400543CE
0x14005443c  mov     rcx, [rcx+18h]
0x140054440  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140054447  mov     edx, 136h
0x14005444c  call    WPP_SF_
0x140054451  jmp     loc_1400543CE
0x140054456  xor     ebx, ebx
0x140054458  lea     r11, cs:140000000h
0x14005445f  cmp     ebx, 4
0x140054462  jge     loc_140054513
0x140054468  movzx   edx, [rsp+108h+var_84]
0x140054470  movzx   r8d, r15w; int
0x140054474  mov     r9b, byte ptr [rsp+108h+var_80]; int
0x14005447c  mov     eax, edx
0x14005447e  mov     [rsp+108h+var_C8], r13; __int64
0x140054483  imul    eax, ebx
0x140054486  movsxd  r10, ebx
0x140054489  mov     [rsp+108h+var_D0], r12; __int64
0x14005448e  mov     dword ptr [rsp+108h+Size], edx; Size
0x140054492  mov     [rsp+108h+var_78], r10
0x14005449a  mov     dl, [r10+r11+480B0h]; int
0x1400544a2  movsxd  rcx, eax
0x1400544a5  mov     al, byte ptr [rsp+108h+var_88]
0x1400544ac  add     rcx, r14
0x1400544af  mov     [rsp+108h+var_E0], rcx; void *
0x1400544b4  mov     cl, 0A1h; int
0x1400544b6  mov     byte ptr [rsp+108h+var_E8], al; int
0x1400544ba  call    SubmitControlRequest
0x1400544bf  mov     edi, eax
0x1400544c1  test    eax, eax
0x1400544c3  js      short loc_1400544C9
0x1400544c5  inc     ebx
0x1400544c7  jmp     short loc_140054458
0x1400544c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400544d0  lea     rsi, WPP_GLOBAL_Control
0x1400544d7  cmp     rcx, rsi
0x1400544da  jz      loc_1400547A8
0x1400544e0  cmp     byte ptr [rcx+29h], 2
0x1400544e4  jb      loc_1400543CE
0x1400544ea  mov     r9, [rsp+108h+var_78]
0x1400544f2  mov     rcx, [rcx+18h]
0x1400544f6  mov     [rsp+108h+var_E8], eax
0x1400544fa  lea     rax, cs:140000000h
0x140054501  mov     r9, ds:rva off_140045B18[rax+r9*8]; "GET_MIN" ...
0x140054509  call    WPP_SF_sD
0x14005450e  jmp     loc_1400543CE
0x140054513  mov     rax, [rsi+10h]
0x140054517  mov     rdx, r14
0x14005451a  movzx   r8d, [rsp+108h+var_84]
0x140054523  mov     rcx, r13
0x140054526  call    _guard_dispatch_icall
0x14005452b  mov     edi, eax
0x14005452d  test    eax, eax
0x14005452f  jns     short loc_14005456F
0x140054531  mov     rcx, cs:WPP_GLOBAL_Control
0x140054538  lea     rsi, WPP_GLOBAL_Control
0x14005453f  cmp     rcx, rsi
0x140054542  jz      loc_1400547A8
0x140054548  cmp     byte ptr [rcx+29h], 2
0x14005454c  jb      loc_1400543CE
0x140054552  mov     edx, 138h
0x140054557  mov     rcx, [rcx+18h]
0x14005455b  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140054562  mov     r9d, eax
0x140054565  call    WPP_SF_d
0x14005456a  jmp     loc_1400543CE
0x14005456f  test    byte ptr [rsp+108h+arg_0], 2
0x140054577  jz      short loc_1400545F7
0x140054579  movzx   edx, [rsp+108h+var_84]
0x140054581  movzx   r8d, r15w; int
0x140054585  mov     al, byte ptr [rsp+108h+var_88]
0x14005458c  mov     r9b, byte ptr [rsp+108h+var_80]; int
0x140054594  mov     [rsp+108h+var_C8], r13; __int64
0x140054599  lea     ecx, [rdx+rdx]
0x14005459c  mov     [rsp+108h+var_D0], r12; __int64
0x1400545a1  mov     dword ptr [rsp+108h+Size], edx; Size
0x1400545a5  add     rcx, r14
0x1400545a8  mov     [rsp+108h+var_E0], rcx; void *
0x1400545ad  mov     dl, 1; int
0x1400545af  mov     cl, 21h ; '!'; int
0x1400545b1  mov     byte ptr [rsp+108h+var_E8], al; int
0x1400545b5  call    SubmitControlRequest
0x1400545ba  mov     edi, eax
0x1400545bc  test    eax, eax
0x1400545be  jns     short loc_1400545EB
0x1400545c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400545c7  lea     rsi, WPP_GLOBAL_Control
0x1400545ce  cmp     rcx, rsi
0x1400545d1  jz      loc_1400547A8
0x1400545d7  cmp     byte ptr [rcx+29h], 2
0x1400545db  jb      loc_1400543CE
0x1400545e1  mov     edx, 139h
0x1400545e6  jmp     loc_140054557
0x1400545eb  mov     dword ptr [r13+rbp*4+4FCh], 0
0x1400545f7  mov     rdx, [rsi]
0x1400545fa  cmp     dword ptr [rdx], 0
0x1400545fd  jbe     loc_140054748
0x140054603  xor     r13d, r13d
0x140054606  mov     dword ptr [rsp+108h+var_78], r13d
0x14005460e  mov     rax, [rdx+8]
0x140054612  lea     r8, ds:0[r13*4]
0x14005461a  add     r8, r13
0x14005461d  mov     [rsp+108h+var_68], r8
0x140054625  cmp     dword ptr [rax+r8*8+8], 0
0x14005462b  jbe     loc_140054724
0x140054631  xor     r13d, r13d
0x140054634  lea     rcx, WPP_GLOBAL_Control
0x14005463b  mov     rax, cs:WPP_GLOBAL_Control
  ... truncated ...
```
