# CWcnPageCFEPin::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x18001297c`
- end: `0x180012c12`
- name: `?OnInitDialog@CWcnPageCFEPin@@QEAA_JI_K_JAEAH@Z`
- size: `662`
- prototype: `__int64 __fastcall(CWcnPageCFEPin *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b860`

## callees

- `0x18000d630`
- `0x18001297c`
- `0x1800132b8`
- `0x18002dc94`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `USER32!LoadImageW` at `0x180012a7c`
- `USER32!LoadImageW` at `0x180012a7c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012a05`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012b13`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012b45`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012bb8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012a05`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012b13`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012b45`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180012bb8`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180012ab8`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180012ad2`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180012ac2`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x180012ac2`
- `DUI70!StrToID` at `0x1800129f9`
- `DUI70!StrToID` at `0x180012b07`
- `DUI70!StrToID` at `0x180012b39`
- `DUI70!StrToID` at `0x180012bac`
- `DUI70!StrToID` at `0x1800129f9`
- `DUI70!StrToID` at `0x180012b07`
- `DUI70!StrToID` at `0x180012b39`
- `DUI70!StrToID` at `0x180012bac`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180012adc`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x180012adc`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x180012a92`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x180012a92`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x180012a1a`
- `api-ms-win-shcore-scaling-l1-1-0!GetScaleFactorForDevice` at `0x180012a1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWcnPageCFEPin::OnInitDialog(
        CWcnPageCFEPin *this,
        __int64 a2,
        __int64 a3,
        struct DirectUI::Value *a4)
{
  const char *Indent; // rax
  __int64 v6; // r10
  char *v7; // rsi
  DirectUI::Element *v8; // rbx
  unsigned __int16 v9; // ax
  DirectUI::Element *Descendent; // rbp
  int ScaleFactorForDevice; // eax
  int v12; // ebx
  int cy; // edi
  bool v14; // al
  HICON ImageW; // rax
  struct DirectUI::Value *Graphic; // rbx
  DirectUI::Element *v17; // rbx
  unsigned __int16 v18; // ax
  DirectUI::Element *v19; // rbx
  unsigned __int16 v20; // ax
  struct DirectUI::Element *v21; // rax
  const char *v22; // rax
  __int64 v23; // r10
  DirectUI::Element *v24; // rbx
  unsigned __int16 v25; // ax
  const char *v26; // rax
  __int64 v27; // r10
  struct DirectUI::Value *v29; // [rsp+78h] [rbp+20h] BYREF

  v29 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 14, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids, Indent);
  }
  v7 = (char *)this + 344;
  v8 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 43) + 48LL))((char *)this + 344);
  v9 = StrToID(L"PagePasswordPin_PinIcon");
  Descendent = DirectUI::Element::FindDescendent(v8, v9);
  if ( Descendent )
  {
    ScaleFactorForDevice = GetScaleFactorForDevice(1);
    v12 = 100;
    if ( ScaleFactorForDevice != 100 )
    {
      if ( ScaleFactorForDevice == 140 )
      {
        v12 = 140;
        cy = 84;
        goto LABEL_11;
      }
      if ( ScaleFactorForDevice == 180 )
      {
        v12 = 180;
        cy = 108;
        goto LABEL_11;
      }
    }
    cy = 60;
LABEL_11:
    v14 = IsStandardIconContrastRatioAcceptable();
    ImageW = (HICON)LoadImageW(
                      hModule,
                      (LPCWSTR)((-(__int64)v14 & 0xFFFFFFFFFFFFFFF2uLL) + 10817),
                      1u,
                      v12,
                      cy,
                      0x8000u);
    if ( ImageW )
    {
      Graphic = DirectUI::Value::CreateGraphic(ImageW, 0, 0, 0);
      v29 = 0;
      CValuePtr::Release((CValuePtr *)&v29);
      v29 = Graphic;
      if ( Graphic
        && (int)DirectUI::Element::RemoveLocalValue(
                  Descendent,
                  (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp) >= 0 )
      {
        DirectUI::Element::SetValue(
          Descendent,
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
          1,
          Graphic);
      }
      CValuePtr::Release((CValuePtr *)&v29);
    }
  }
  v17 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v7 + 48LL))((char *)this + 344);
  v18 = StrToID(L"PagePasswordPin_EditPinBox");
  *((_QWORD *)this + 49) = DirectUI::Element::FindDescendent(v17, v18);
  v19 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v7 + 48LL))((char *)this + 344);
  v20 = StrToID(L"PagePasswordPin_Help");
  v21 = DirectUI::Element::FindDescendent(v19, v20);
  *((_QWORD *)this + 50) = v21;
  if ( (!*((_QWORD *)this + 49) || !v21)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = GetIndent(0);
    WPP_SF_s(*(_QWORD *)(v23 + 16), 15, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids, v22);
  }
  v24 = (DirectUI::Element *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v7 + 48LL))((char *)this + 344);
  v25 = StrToID(L"PagePasswordPin_ProfileMismatchWarning");
  *((_QWORD *)this + 51) = DirectUI::Element::FindDescendent(v24, v25);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v26 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v27 + 16), 16, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids, v26);
  }
  return 1;
}

```

## disassembly

```asm
0x18001297c  mov     [rsp+arg_0], rbx
0x180012981  mov     [rsp+arg_8], rbp
0x180012986  mov     [rsp+arg_18], r9
0x18001298b  push    rsi
0x18001298c  push    rdi
0x18001298d  push    r13
0x18001298f  push    r14
0x180012991  push    r15
0x180012993  sub     rsp, 30h
0x180012997  mov     r14, rcx
0x18001299a  lea     r13, WPP_GLOBAL_Control
0x1800129a1  mov     r15d, 1
0x1800129a7  mov     r10, cs:WPP_GLOBAL_Control
0x1800129ae  cmp     r10, r13
0x1800129b1  jz      short loc_1800129D9
0x1800129b3  cmp     byte ptr [r10+19h], 6
0x1800129b8  jb      short loc_1800129D9
0x1800129ba  mov     ecx, r15d; int
0x1800129bd  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800129c2  lea     edx, [r15+0Dh]
0x1800129c6  mov     r9, rax
0x1800129c9  lea     r8, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids
0x1800129d0  mov     rcx, [r10+10h]
0x1800129d4  call    WPP_SF_s
0x1800129d9  lea     rsi, [r14+158h]
0x1800129e0  mov     rax, [rsi]
0x1800129e3  mov     rcx, rsi
0x1800129e6  mov     rax, [rax+30h]
0x1800129ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129ef  mov     rbx, rax
0x1800129f2  lea     rcx, aPagepasswordpi_1; "PagePasswordPin_PinIcon"
0x1800129f9  call    cs:__imp_StrToID
0x1800129ff  movzx   edx, ax
0x180012a02  mov     rcx, rbx
0x180012a05  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012a0b  mov     rbp, rax
0x180012a0e  test    rax, rax
0x180012a11  jz      loc_180012AEE
0x180012a17  mov     ecx, r15d
0x180012a1a  call    cs:__imp_GetScaleFactorForDevice
0x180012a20  mov     ecx, eax
0x180012a22  mov     ebx, 64h ; 'd'
0x180012a27  sub     ecx, ebx
0x180012a29  jz      short loc_180012A49
0x180012a2b  sub     ecx, 28h ; '('
0x180012a2e  jz      short loc_180012A3F
0x180012a30  cmp     ecx, 28h ; '('
0x180012a33  jnz     short loc_180012A49
0x180012a35  mov     ebx, 0B4h
0x180012a3a  lea     edi, [rcx+44h]
0x180012a3d  jmp     short loc_180012A4E
0x180012a3f  mov     ebx, 8Ch
0x180012a44  lea     edi, [rbx-38h]
0x180012a47  jmp     short loc_180012A4E
0x180012a49  mov     edi, 3Ch ; '<'
0x180012a4e  call    ?IsStandardIconContrastRatioAcceptable@@YA_NXZ; IsStandardIconContrastRatioAcceptable(void)
0x180012a53  neg     al
0x180012a55  sbb     rdx, rdx
0x180012a58  and     rdx, 0FFFFFFFFFFFFFFF2h
0x180012a5c  add     rdx, 2A41h; name
0x180012a63  mov     [rsp+58h+fuLoad], 8000h; fuLoad
0x180012a6b  mov     [rsp+58h+cy], edi; cy
0x180012a6f  mov     r9d, ebx; cx
0x180012a72  mov     r8d, r15d; type
0x180012a75  mov     rcx, cs:hModule; hInst
0x180012a7c  call    cs:__imp_LoadImageW
0x180012a82  test    rax, rax
0x180012a85  jz      short loc_180012AEE
0x180012a87  xor     r9d, r9d
0x180012a8a  xor     r8d, r8d
0x180012a8d  xor     edx, edx
0x180012a8f  mov     rcx, rax
0x180012a92  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x180012a98  mov     rbx, rax
0x180012a9b  mov     [rsp+58h+arg_18], 0
0x180012aa4  lea     rcx, [rsp+58h+arg_18]; this
0x180012aa9  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180012aae  mov     [rsp+58h+arg_18], rbx
0x180012ab3  test    rbx, rbx
0x180012ab6  jz      short loc_180012AE3
0x180012ab8  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180012abf  mov     rcx, rbp
0x180012ac2  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x180012ac8  test    eax, eax
0x180012aca  js      short loc_180012AE3
0x180012acc  mov     r9, rbx
0x180012acf  mov     r8d, r15d
0x180012ad2  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x180012ad9  mov     rcx, rbp
0x180012adc  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x180012ae2  nop
0x180012ae3  lea     rcx, [rsp+58h+arg_18]; this
0x180012ae8  call    ?Release@CValuePtr@@QEAAXXZ; CValuePtr::Release(void)
0x180012aed  nop
0x180012aee  mov     rax, [rsi]
0x180012af1  mov     rcx, rsi
0x180012af4  mov     rax, [rax+30h]
0x180012af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012afd  mov     rbx, rax
0x180012b00  lea     rcx, aPagepasswordpi_2; "PagePasswordPin_EditPinBox"
0x180012b07  call    cs:__imp_StrToID
0x180012b0d  movzx   edx, ax
0x180012b10  mov     rcx, rbx
0x180012b13  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012b19  mov     [r14+188h], rax
0x180012b20  mov     rax, [rsi]
0x180012b23  mov     rcx, rsi
0x180012b26  mov     rax, [rax+30h]
0x180012b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b2f  mov     rbx, rax
0x180012b32  lea     rcx, aPagepasswordpi_0; "PagePasswordPin_Help"
0x180012b39  call    cs:__imp_StrToID
0x180012b3f  movzx   edx, ax
0x180012b42  mov     rcx, rbx
0x180012b45  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012b4b  mov     [r14+190h], rax
0x180012b52  cmp     qword ptr [r14+188h], 0
0x180012b5a  jz      short loc_180012B61
0x180012b5c  test    rax, rax
0x180012b5f  jnz     short loc_180012B93
0x180012b61  mov     r10, cs:WPP_GLOBAL_Control
0x180012b68  cmp     r10, r13
0x180012b6b  jz      short loc_180012B93
0x180012b6d  cmp     byte ptr [r10+19h], 2
0x180012b72  jb      short loc_180012B93
0x180012b74  xor     ecx, ecx; int
0x180012b76  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180012b7b  mov     edx, 0Fh
0x180012b80  mov     r9, rax
0x180012b83  lea     r8, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids
0x180012b8a  mov     rcx, [r10+10h]
0x180012b8e  call    WPP_SF_s
0x180012b93  mov     rax, [rsi]
0x180012b96  mov     rcx, rsi
0x180012b99  mov     rax, [rax+30h]
0x180012b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ba2  mov     rbx, rax
0x180012ba5  lea     rcx, aPagepasswordpi; "PagePasswordPin_ProfileMismatchWarning"
0x180012bac  call    cs:__imp_StrToID
0x180012bb2  movzx   edx, ax
0x180012bb5  mov     rcx, rbx
0x180012bb8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180012bbe  mov     [r14+198h], rax
0x180012bc5  mov     r10, cs:WPP_GLOBAL_Control
0x180012bcc  cmp     r10, r13
0x180012bcf  jz      short loc_180012BF8
0x180012bd1  cmp     byte ptr [r10+19h], 6
0x180012bd6  jb      short loc_180012BF8
0x180012bd8  or      ecx, 0FFFFFFFFh; int
0x180012bdb  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180012be0  mov     edx, 10h
0x180012be5  mov     r9, rax
0x180012be8  lea     r8, WPP_ec3d56dcd870365e094116459b5f4c14_Traceguids
0x180012bef  mov     rcx, [r10+10h]
0x180012bf3  call    WPP_SF_s
0x180012bf8  mov     rax, r15
0x180012bfb  mov     rbx, [rsp+58h+arg_0]
0x180012c00  mov     rbp, [rsp+58h+arg_8]
0x180012c05  add     rsp, 30h
0x180012c09  pop     r15
0x180012c0b  pop     r14
0x180012c0d  pop     r13
0x180012c0f  pop     rdi
0x180012c10  pop     rsi
0x180012c11  retn
```
