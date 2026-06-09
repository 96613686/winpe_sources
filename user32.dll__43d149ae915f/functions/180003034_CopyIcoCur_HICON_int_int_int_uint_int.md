# CopyIcoCur(HICON__ *,int,int,int,uint,int)

- ea: `0x180003034`
- end: `0x1800034bb`
- name: `?CopyIcoCur@@YAPEAUHICON__@@PEAU1@HHHIH@Z`
- size: `1159`
- prototype: `HICON __fastcall(HICON, int, int, int, unsigned int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180002f70`
- `0x180008324`

## callees

- `0x180001ffc`
- `0x180002080`
- `0x180003034`
- `0x180003b18`
- `0x180004c04`
- `0x180005d94`
- `0x180005f7c`
- `0x180005fd0`
- `0x180008190`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserGetIconInfo` at `0x180003126`
- `win32u!NtUserGetIconInfo` at `0x180003126`
- `win32u!NtUserGetIconSize` at `0x1800030c2`
- `win32u!NtUserGetIconSize` at `0x1800030c2`
- `win32u!NtUserDestroyCursor` at `0x180003362`
- `win32u!NtUserDestroyCursor` at `0x1800033e6`
- `win32u!NtUserDestroyCursor` at `0x180003362`
- `win32u!NtUserDestroyCursor` at `0x1800033e6`
- `win32u!NtUserCreateEmptyCursorObject` at `0x1800032a6`
- `win32u!NtUserCreateEmptyCursorObject` at `0x1800032a6`
- `ntdll!RtlFreeHeap` at `0x1800034b0`
- `ntdll!RtlFreeHeap` at `0x1800034b0`
- `GDI32!GdiTrackHCreate` at `0x180003139`
- `GDI32!GdiTrackHCreate` at `0x180003144`
- `GDI32!GdiTrackHCreate` at `0x180003139`
- `GDI32!GdiTrackHCreate` at `0x180003144`
- `GDI32!DeleteObject` at `0x180003257`
- `GDI32!DeleteObject` at `0x180003271`
- `GDI32!DeleteObject` at `0x180003397`
- `GDI32!DeleteObject` at `0x1800033a7`
- `GDI32!DeleteObject` at `0x180003468`
- `GDI32!DeleteObject` at `0x180003257`
- `GDI32!DeleteObject` at `0x180003271`
- `GDI32!DeleteObject` at `0x180003397`
- `GDI32!DeleteObject` at `0x1800033a7`
- `GDI32!DeleteObject` at `0x180003468`

## pseudocode

```c
HICON __fastcall CopyIcoCur(HICON a1, int a2, unsigned int a3, unsigned int a4, unsigned int a5, int a6)
{
  unsigned int v6; // ebx
  HICON EmptyCursorObject; // rdi
  unsigned int IcoCurWidth; // r13d
  unsigned int IcoCurHeight; // eax
  unsigned int v14; // r12d
  struct tagBITMAPINFOHEADER *v15; // r14
  unsigned int IcoCurBpp; // eax
  HBITMAP v17; // rax
  HDC v18; // rdx
  HBITMAP v19; // rsi
  HBITMAP v20; // rcx
  HBITMAP v21; // r15
  PCWSTR v22; // rax
  int ThreadDefCursorSize; // eax
  unsigned int v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v27; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h] BYREF
  HGDIOBJ ho[2]; // [rsp+50h] [rbp-B0h]
  __int128 v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v31; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR v32[2]; // [rsp+78h] [rbp-88h] BYREF
  HICON v33; // [rsp+88h] [rbp-78h]
  HICON v34; // [rsp+90h] [rbp-70h] BYREF
  int v35; // [rsp+98h] [rbp-68h]
  unsigned int v36; // [rsp+9Ch] [rbp-64h]
  unsigned int v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+A4h] [rbp-5Ch]
  _QWORD v39[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C8h] [rbp-38h]
  __int16 v42; // [rsp+CCh] [rbp-34h]
  __int16 v43; // [rsp+CEh] [rbp-32h]
  HGDIOBJ v44; // [rsp+D0h] [rbp-30h]
  HGDIOBJ v45; // [rsp+D8h] [rbp-28h]
  int v46; // [rsp+100h] [rbp+0h]
  unsigned int v47; // [rsp+104h] [rbp+4h]
  int v48; // [rsp+108h] [rbp+8h]
  char v49; // [rsp+140h] [rbp+40h] BYREF
  char v50; // [rsp+350h] [rbp+250h] BYREF

  v6 = a5;
  EmptyCursorObject = 0;
  v33 = a1;
  v27 = 0;
  v25 = 0;
  v26 = 0;
  v28 = 0;
  *(_OWORD *)ho = 0;
  memset_0(v39, 0, 0x88u);
  v30 = 0;
  *(_OWORD *)v32 = 0;
  if ( !(unsigned int)NtUserGetIconSize(a1, 0, &v27, &v25) )
    return 0;
  v25 = (int)v25 >> 1;
  if ( (a5 & 0x2000) != 0 )
    v6 = a5 & 0xFFFFD7FF | 0x800;
  *((_QWORD *)&v30 + 1) = &v49;
  LODWORD(v30) = 17039360;
  v32[1] = (PCWSTR)&v50;
  LODWORD(v32[0]) = 17039360;
  if ( !(unsigned int)NtUserGetIconInfo(a1, &v28, &v30, v32, &v26, 1) )
    return 0;
  GdiTrackHCreate(ho[0]);
  GdiTrackHCreate(ho[1]);
  IcoCurWidth = GetIcoCurWidth(a3, a2, v6, v27);
  IcoCurHeight = GetIcoCurHeight(a4, a2, v6, v25);
  v14 = IcoCurHeight;
  if ( (v6 & 0x4000) != 0 )
  {
    v37 = IcoCurHeight;
    v38 = v26;
    v34 = a1;
    v35 = a2 != 0 ? 3 : 1;
    v36 = IcoCurWidth;
    v15 = 0;
    EmptyCursorObject = CopyImageFromRes(
                          (PCWSTR)(*((_QWORD *)&v30 + 1) & -(__int64)((_WORD)v30 != 0)),
                          v32[1],
                          (struct tagCURSORFIND *)&v34,
                          v6);
    if ( EmptyCursorObject )
      goto LABEL_34;
  }
  else
  {
    v15 = 0;
  }
  IcoCurBpp = GetIcoCurBpp(v6);
  if ( IcoCurWidth == v27 && v14 == v25 && (v26 == 1 || !IcoCurBpp || IcoCurBpp == v26) )
  {
    if ( (v6 & 4) == 0 )
      goto LABEL_19;
    EmptyCursorObject = a1;
LABEL_34:
    DeleteObject(ho[0]);
    if ( ho[1] )
      DeleteObject(ho[1]);
    goto LABEL_36;
  }
  v17 = CopyBmp((HBITMAP)ho[0], IcoCurWidth, 2 * v14, 1u, 0);
  v19 = v17;
  if ( !v17 )
    goto LABEL_34;
  v20 = (HBITMAP)ho[1];
  if ( ho[1] )
  {
    if ( a6 )
    {
      v31 = 0;
      v15 = (struct tagBITMAPINFOHEADER *)DIBFromBitmap(v17, v18, &v31);
      if ( !v15 )
      {
LABEL_49:
        DeleteObject(v19);
        goto LABEL_34;
      }
      v20 = (HBITMAP)ho[1];
    }
    v21 = CopyBmp(v20, IcoCurWidth, v14, v6, v15);
    if ( v15 )
      RtlFreeHeap(pUserHeap, 0, v15);
    if ( v21 )
      goto LABEL_14;
    goto LABEL_49;
  }
  v21 = 0;
LABEL_14:
  DeleteObject(ho[0]);
  ho[0] = v19;
  if ( ho[1] && ho[1] != v21 )
  {
    DeleteObject(ho[1]);
    ho[1] = v21;
  }
  if ( IcoCurWidth != v27 && v27 )
    DWORD1(v28) = (int)(DWORD1(v28) * IcoCurWidth + (int)v27 / 2) / (int)v27;
  if ( v14 != v25 && v25 )
    DWORD2(v28) = (int)(DWORD2(v28) * v14 + (int)v25 / 2) / (int)v25;
LABEL_19:
  EmptyCursorObject = (HICON)NtUserCreateEmptyCursorObject(0);
  if ( !EmptyCursorObject )
    goto LABEL_34;
  memset_0(v39, 0, 0x88u);
  v22 = (PCWSTR)v39[0];
  if ( LOWORD(v32[0]) )
    v22 = v32[1];
  v39[0] = v22;
  v39[1] = *((_QWORD *)&v30 + 1) & -(__int64)((_WORD)v30 != 0);
  if ( (_DWORD)v28 )
    v40 = 3;
  else
    v40 = 1;
  v46 = v26;
  v48 = 2 * v14;
  v42 = WORD2(v28);
  v43 = WORD4(v28);
  v44 = ho[0];
  v45 = ho[1];
  v47 = IcoCurWidth;
  if ( (v6 & 0x40000) != 0 )
    v41 |= 0x1000u;
  ThreadDefCursorSize = GetThreadDefCursorSize();
  if ( !(unsigned int)_SetCursorIconData(EmptyCursorObject, (struct tagCURSORDATA *)v39, ThreadDefCursorSize) )
  {
    NtUserDestroyCursor(EmptyCursorObject, 0);
    return 0;
  }
LABEL_36:
  if ( EmptyCursorObject != v33 && (v6 & 8) != 0 )
    NtUserDestroyCursor(v33, 1);
  return EmptyCursorObject;
}

```

## disassembly

```asm
0x180003034  push    rbp
0x180003036  push    rbx
0x180003037  push    rsi
0x180003038  push    rdi
0x180003039  push    r12
0x18000303b  push    r13
0x18000303d  push    r14
0x18000303f  push    r15
0x180003041  lea     rbp, [rsp-478h]
0x180003049  sub     rsp, 578h
0x180003050  mov     rax, cs:__security_cookie
0x180003057  xor     rax, rsp
0x18000305a  mov     [rbp+4B0h+var_50], rax
0x180003061  mov     ebx, [rbp+4B0h+arg_20]
0x180003067  xor     edi, edi
0x180003069  xorps   xmm0, xmm0
0x18000306c  mov     [rbp+4B0h+var_528], rcx
0x180003070  mov     r15d, r8d
0x180003073  mov     [rsp+5B0h+var_578], edi
0x180003077  mov     r14d, edx
0x18000307a  mov     [rsp+5B0h+var_580], edi
0x18000307e  mov     rsi, rcx
0x180003081  mov     [rsp+5B0h+var_57C], edi
0x180003085  xor     edx, edx; Val
0x180003087  lea     rcx, [rbp+4B0h+var_500]; void *
0x18000308b  mov     r8d, 88h; Size
0x180003091  mov     r12d, r9d
0x180003094  movups  [rsp+5B0h+var_570], xmm0
0x180003099  movups  xmmword ptr [rsp+5B0h+ho], xmm0
0x18000309e  call    memset_0
0x1800030a3  xorps   xmm0, xmm0
0x1800030a6  lea     r9, [rsp+5B0h+var_580]
0x1800030ab  xorps   xmm1, xmm1
0x1800030ae  lea     r8, [rsp+5B0h+var_578]
0x1800030b3  xor     edx, edx
0x1800030b5  mov     rcx, rsi
0x1800030b8  movups  [rsp+5B0h+var_550], xmm0
0x1800030bd  movups  xmmword ptr [rsp+5B0h+var_538], xmm1
0x1800030c2  call    cs:__imp_NtUserGetIconSize
0x1800030c8  test    eax, eax
0x1800030ca  jz      loc_180003368
0x1800030d0  sar     [rsp+5B0h+var_580], 1
0x1800030d4  bt      ebx, 0Dh
0x1800030d8  jb      loc_180003497
0x1800030de  lea     rax, [rbp+4B0h+var_470]
0x1800030e2  mov     [rsp+5B0h+var_588], 1
0x1800030ea  mov     qword ptr [rsp+5B0h+var_550+8], rax
0x1800030ef  lea     r9, [rsp+5B0h+var_538]
0x1800030f4  lea     rax, [rbp+4B0h+var_260]
0x1800030fb  mov     dword ptr [rsp+5B0h+var_550], 1040000h
0x180003103  mov     [rbp+4B0h+var_538+8], rax
0x180003107  lea     r8, [rsp+5B0h+var_550]
0x18000310c  lea     rax, [rsp+5B0h+var_57C]
0x180003111  mov     dword ptr [rsp+5B0h+var_538], 1040000h
0x180003119  lea     rdx, [rsp+5B0h+var_570]
0x18000311e  mov     [rsp+5B0h+var_590], rax
0x180003123  mov     rcx, rsi
0x180003126  call    cs:__imp_NtUserGetIconInfo
0x18000312c  test    eax, eax
0x18000312e  jz      loc_180003368
0x180003134  mov     rcx, [rsp+5B0h+ho]
0x180003139  call    cs:__imp_GdiTrackHCreate
0x18000313f  mov     rcx, [rsp+5B0h+ho+8]
0x180003144  call    cs:__imp_GdiTrackHCreate
0x18000314a  mov     r9d, [rsp+5B0h+var_578]; unsigned int
0x18000314f  mov     r8d, ebx; unsigned int
0x180003152  mov     edx, r14d; int
0x180003155  mov     ecx, r15d; unsigned int
0x180003158  call    ?GetIcoCurWidth@@YAKKHIK@Z; GetIcoCurWidth(ulong,int,uint,ulong)
0x18000315d  mov     r9d, [rsp+5B0h+var_580]; unsigned int
0x180003162  mov     r8d, ebx; unsigned int
0x180003165  mov     edx, r14d; int
0x180003168  mov     ecx, r12d; unsigned int
0x18000316b  mov     r13d, eax
0x18000316e  call    ?GetIcoCurHeight@@YAKKHIK@Z; GetIcoCurHeight(ulong,int,uint,ulong)
0x180003173  mov     r12d, eax
0x180003176  mov     r15d, 1
0x18000317c  bt      ebx, 0Eh
0x180003180  jnb     loc_1800033EE
0x180003186  mov     rdx, [rbp+4B0h+var_538+8]; PCWSTR
0x18000318a  lea     r8, [rbp+4B0h+var_520]; struct tagCURSORFIND *
0x18000318e  mov     [rbp+4B0h+var_510], eax
0x180003191  neg     r14d
0x180003194  mov     eax, [rsp+5B0h+var_57C]
0x180003198  mov     r9d, ebx; unsigned int
0x18000319b  sbb     ecx, ecx
0x18000319d  mov     [rbp+4B0h+var_50C], eax
0x1800031a0  movzx   eax, word ptr [rsp+5B0h+var_550]
0x1800031a5  and     ecx, 2
0x1800031a8  add     ecx, r15d
0x1800031ab  mov     [rbp+4B0h+var_520], rsi
0x1800031af  mov     [rbp+4B0h+var_518], ecx
0x1800031b2  neg     ax
0x1800031b5  mov     [rbp+4B0h+var_514], r13d
0x1800031b9  sbb     rcx, rcx
0x1800031bc  and     rcx, qword ptr [rsp+5B0h+var_550+8]; SourceString
0x1800031c1  call    ?CopyImageFromRes@@YAPEAUHICON__@@PEAG0PEAUtagCURSORFIND@@I@Z; CopyImageFromRes(ushort *,ushort *,tagCURSORFIND *,uint)
0x1800031c6  xor     r14d, r14d
0x1800031c9  mov     rdi, rax
0x1800031cc  test    rax, rax
0x1800031cf  jnz     loc_180003392
0x1800031d5  mov     ecx, ebx; unsigned int
0x1800031d7  call    ?GetIcoCurBpp@@YAKI@Z; GetIcoCurBpp(uint)
0x1800031dc  cmp     r13d, [rsp+5B0h+var_578]
0x1800031e1  jz      loc_18000336C
0x1800031e7  mov     rcx, [rsp+5B0h+ho]; hbm
0x1800031ec  lea     r8d, [r12+r12]; unsigned int
0x1800031f0  mov     r9d, r15d; unsigned int
0x1800031f3  mov     [rsp+5B0h+var_590], r14; struct tagBITMAPINFOHEADER *
0x1800031f8  mov     edx, r13d; unsigned int
0x1800031fb  call    ?CopyBmp@@YAPEAUHBITMAP__@@PEAU1@HHIPEAUtagBITMAPINFOHEADER@@@Z; CopyBmp(HBITMAP__ *,int,int,uint,tagBITMAPINFOHEADER *)
0x180003200  mov     rsi, rax
0x180003203  test    rax, rax
0x180003206  jz      loc_180003392
0x18000320c  mov     rcx, [rsp+5B0h+ho+8]; hbm
0x180003211  test    rcx, rcx
0x180003214  jz      loc_180003444
0x18000321a  cmp     [rbp+4B0h+arg_28], r14d
0x180003221  jnz     loc_180003473
0x180003227  mov     r9d, ebx; unsigned int
0x18000322a  mov     [rsp+5B0h+var_590], r14; struct tagBITMAPINFOHEADER *
0x18000322f  mov     r8d, r12d; unsigned int
0x180003232  mov     edx, r13d; unsigned int
0x180003235  call    ?CopyBmp@@YAPEAUHBITMAP__@@PEAU1@HHIPEAUtagBITMAPINFOHEADER@@@Z; CopyBmp(HBITMAP__ *,int,int,uint,tagBITMAPINFOHEADER *)
0x18000323a  mov     r15, rax
0x18000323d  test    r14, r14
0x180003240  jnz     loc_1800034A4
0x180003246  xor     r14d, r14d
0x180003249  test    r15, r15
0x18000324c  jz      loc_180003465
0x180003252  mov     rcx, [rsp+5B0h+ho]; ho
0x180003257  call    cs:__imp_DeleteObject
0x18000325d  mov     rcx, [rsp+5B0h+ho+8]; ho
0x180003262  mov     [rsp+5B0h+ho], rsi
0x180003267  test    rcx, rcx
0x18000326a  jz      short loc_18000327C
0x18000326c  cmp     rcx, r15
0x18000326f  jz      short loc_18000327C
0x180003271  call    cs:__imp_DeleteObject
0x180003277  mov     [rsp+5B0h+ho+8], r15
0x18000327c  mov     r8d, [rsp+5B0h+var_578]
0x180003281  mov     r10d, 2
0x180003287  cmp     r13d, r8d
0x18000328a  jnz     loc_1800033F6
0x180003290  mov     r9d, [rsp+5B0h+var_580]
0x180003295  mov     r15d, 1
0x18000329b  cmp     r12d, r9d
0x18000329e  jnz     loc_18000341D
0x1800032a4  xor     ecx, ecx
0x1800032a6  call    cs:__imp_NtUserCreateEmptyCursorObject
0x1800032ac  mov     rdi, rax
0x1800032af  test    rax, rax
0x1800032b2  jz      loc_180003392
0x1800032b8  xor     edx, edx; Val
0x1800032ba  lea     rcx, [rbp+4B0h+var_500]; void *
0x1800032be  mov     r8d, 88h; Size
0x1800032c4  call    memset_0
0x1800032c9  cmp     word ptr [rsp+5B0h+var_538], r14w
0x1800032cf  mov     rax, [rbp+4B0h+var_500]
0x1800032d3  cmovnz  rax, [rbp+4B0h+var_538+8]
0x1800032d8  mov     [rbp+4B0h+var_500], rax
0x1800032dc  movzx   eax, word ptr [rsp+5B0h+var_550]
0x1800032e1  neg     ax
0x1800032e4  sbb     rcx, rcx
0x1800032e7  and     rcx, qword ptr [rsp+5B0h+var_550+8]
0x1800032ec  mov     [rbp+4B0h+var_4F8], rcx
0x1800032f0  cmp     dword ptr [rsp+5B0h+var_570], r14d
0x1800032f5  jz      loc_18000345B
0x1800032fb  mov     eax, 3
0x180003300  mov     [rbp+4B0h+var_4F0], ax
0x180003304  mov     eax, [rsp+5B0h+var_57C]
0x180003308  mov     [rbp+4B0h+var_4B0], eax
0x18000330b  lea     eax, [r12+r12]
0x18000330f  mov     [rbp+4B0h+var_4A8], eax
0x180003312  movzx   eax, word ptr [rsp+5B0h+var_570+4]
0x180003317  mov     [rbp+4B0h+var_4E4], ax
0x18000331b  movzx   eax, word ptr [rsp+5B0h+var_570+8]
0x180003320  mov     [rbp+4B0h+var_4E2], ax
0x180003324  mov     rax, [rsp+5B0h+ho]
0x180003329  mov     [rbp+4B0h+var_4E0], rax
0x18000332d  mov     rax, [rsp+5B0h+ho+8]
0x180003332  mov     [rbp+4B0h+var_4D8], rax
0x180003336  mov     [rbp+4B0h+var_4AC], r13d
0x18000333a  bt      ebx, 12h
0x18000333e  jnb     short loc_180003345
0x180003340  bts     [rbp+4B0h+var_4E8], 0Ch
0x180003345  call    ?GetThreadDefCursorSize@@YAHXZ; GetThreadDefCursorSize(void)
0x18000334a  mov     r8d, eax; int
0x18000334d  lea     rdx, [rbp+4B0h+var_500]; struct tagCURSORDATA *
0x180003351  mov     rcx, rdi; HICON
0x180003354  call    ?_SetCursorIconData@@YAHPEAUHICON__@@PEAUtagCURSORDATA@@H@Z; _SetCursorIconData(HICON__ *,tagCURSORDATA *,int)
0x180003359  test    eax, eax
0x18000335b  jnz     short loc_1800033AD
0x18000335d  xor     edx, edx
0x18000335f  mov     rcx, rdi
0x180003362  call    cs:__imp_NtUserDestroyCursor
0x180003368  xor     eax, eax
0x18000336a  jmp     short loc_1800033B9
0x18000336c  cmp     r12d, [rsp+5B0h+var_580]
0x180003371  jnz     loc_1800031E7
0x180003377  cmp     [rsp+5B0h+var_57C], r15d
0x18000337c  jz      short loc_180003386
0x18000337e  test    eax, eax
0x180003380  jnz     loc_18000344C
0x180003386  test    bl, 4
0x180003389  jz      loc_1800032A4
0x18000338f  mov     rdi, rsi
0x180003392  mov     rcx, [rsp+5B0h+ho]; ho
0x180003397  call    cs:__imp_DeleteObject
0x18000339d  mov     rcx, [rsp+5B0h+ho+8]; ho
0x1800033a2  test    rcx, rcx
0x1800033a5  jz      short loc_1800033AD
0x1800033a7  call    cs:__imp_DeleteObject
0x1800033ad  mov     rcx, [rbp+4B0h+var_528]
0x1800033b1  cmp     rdi, rcx
0x1800033b4  jnz     short loc_1800033DC
0x1800033b6  mov     rax, rdi
0x1800033b9  mov     rcx, [rbp+4B0h+var_50]
0x1800033c0  xor     rcx, rsp; StackCookie
0x1800033c3  call    __security_check_cookie
0x1800033c8  add     rsp, 578h
0x1800033cf  pop     r15
0x1800033d1  pop     r14
0x1800033d3  pop     r13
0x1800033d5  pop     r12
0x1800033d7  pop     rdi
0x1800033d8  pop     rsi
0x1800033d9  pop     rbx
0x1800033da  pop     rbp
0x1800033db  retn
0x1800033dc  test    bl, 8
0x1800033df  jz      short loc_1800033B6
0x1800033e1  mov     edx, 1
0x1800033e6  call    cs:__imp_NtUserDestroyCursor
0x1800033ec  jmp     short loc_1800033B6
0x1800033ee  xor     r14d, r14d
0x1800033f1  jmp     loc_1800031D5
0x1800033f6  test    r8d, r8d
0x1800033f9  jz      loc_180003290
0x1800033ff  mov     eax, r8d
0x180003402  mov     ecx, r13d
0x180003405  imul    ecx, dword ptr [rsp+5B0h+var_570+4]
0x18000340a  cdq
0x18000340b  idiv    r10d
0x18000340e  add     eax, ecx
0x180003410  cdq
0x180003411  idiv    r8d
0x180003414  mov     dword ptr [rsp+5B0h+var_570+4], eax
0x180003418  jmp     loc_180003290
0x18000341d  test    r9d, r9d
0x180003420  jz      loc_1800032A4
0x180003426  mov     eax, r9d
0x180003429  mov     ecx, r12d
0x18000342c  imul    ecx, dword ptr [rsp+5B0h+var_570+8]
0x180003431  cdq
0x180003432  idiv    r10d
0x180003435  add     eax, ecx
0x180003437  cdq
0x180003438  idiv    r9d
0x18000343b  mov     dword ptr [rsp+5B0h+var_570+8], eax
0x18000343f  jmp     loc_1800032A4
0x180003444  mov     r15, r14
0x180003447  jmp     loc_180003252
0x18000344c  cmp     eax, [rsp+5B0h+var_57C]
0x180003450  jz      loc_180003386
0x180003456  jmp     loc_1800031E7
0x18000345b  mov     [rbp+4B0h+var_4F0], r15w
0x180003460  jmp     loc_180003304
0x180003465  mov     rcx, rsi; ho
0x180003468  call    cs:__imp_DeleteObject
0x18000346e  jmp     loc_180003392
0x180003473  lea     r8, [rsp+5B0h+var_540]; unsigned int *
0x180003478  mov     [rsp+5B0h+var_540], r14d
0x18000347d  mov     rcx, rsi; hbm
0x180003480  call    ?DIBFromBitmap@@YAPEAXPEAUHBITMAP__@@PEAUHDC__@@PEAK@Z; DIBFromBitmap(HBITMAP__ *,HDC__ *,ulong *)
0x180003485  mov     r14, rax
0x180003488  test    rax, rax
0x18000348b  jz      short loc_180003465
0x18000348d  mov     rcx, [rsp+5B0h+ho+8]
0x180003492  jmp     loc_180003227
0x180003497  btr     ebx, 0Dh
0x18000349b  bts     ebx, 0Bh
0x18000349f  jmp     loc_1800030DE
0x1800034a4  mov     rcx, cs:pUserHeap; HeapHandle
0x1800034ab  mov     r8, r14; P
0x1800034ae  xor     edx, edx; Flags
0x1800034b0  call    cs:__imp_RtlFreeHeap
0x1800034b6  jmp     loc_180003246
```
