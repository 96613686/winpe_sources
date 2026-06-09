# CPXWizardPageStub::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IPXWizardPropertyBagStub *,IPXWizardTransactionStub *,IPXWizardNavigateStub *,IPXWizardPageReportStub *,ushort)

- ea: `0x180018660`
- end: `0x18001891b`
- name: `?CanRunPage@CPXWizardPageStub@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIPXWizardPropertyBagStub@@PEAUIPXWizardTransactionStub@@PEAUIPXWizardNavigateStub@@PEAUIPXWizardPageReportStub@@G@Z`
- size: `699`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002556`
- `0x18000ae04`
- `0x18000ae44`
- `0x180018660`
- `0x180019bf0`
- `0x18001af64`
- `0x18001b434`
- `0x18001b6e4`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800188dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800188dc`

## pseudocode

```c
__int64 __fastcall CPXWizardPageStub::CanRunPage(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        unsigned int a4,
        int a5,
        _WORD *a6,
        int a7,
        struct IPXWizardPropertyBagStub *a8,
        struct IPXWizardTransactionStub *a9,
        struct IPXWizardNavigateStub *a10,
        struct IPXWizardPageReportStub *a11,
        unsigned __int16 a12)
{
  struct IXWizardSource **v12; // rsi
  int Instance; // eax
  unsigned int v18; // r15d
  __int64 v20; // r10
  _WORD *v21; // rcx
  struct IXWizardSource *v22; // rdx
  __int64 v23; // rax
  unsigned int v24; // ebx
  unsigned int v25; // r15d
  int v26; // eax
  void *v27; // r12
  _OWORD *v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  void *Src; // [rsp+50h] [rbp-18h] BYREF
  void *v32; // [rsp+58h] [rbp-10h] BYREF
  size_t Size; // [rsp+B0h] [rbp+48h] BYREF

  v12 = (struct IXWizardSource **)(a1 + 88);
  if ( !*(_QWORD *)(a1 + 88) )
  {
    Instance = CXWizardSourceStub::HrCreateInstance(a8, a9, a10, 0, a11, v12);
    v18 = Instance;
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids,
          (unsigned int)Instance);
      return v18;
    }
  }
  v20 = *(_QWORD *)(a1 + 80);
  v21 = a6;
  v22 = *v12;
  Src = 0;
  if ( a6 && !*a6 )
    v21 = 0;
  if ( a3 )
  {
    v23 = *a3 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *a3 == *(_QWORD *)&GUID_NULL.Data1 )
      v23 = a3[1] - *(_QWORD *)GUID_NULL.Data4;
    if ( !v23 )
      a3 = 0;
  }
  v24 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, _QWORD, int, _WORD *, int, struct IXWizardSource *, void **))(*(_QWORD *)v20 + 56LL))(
          v20,
          a2,
          a3,
          a4,
          a5,
          v21,
          a7,
          v22,
          &Src);
  if ( !v24 )
  {
    if ( Src )
    {
      if ( ((unsigned __int8)Src & 1) != 0 )
      {
        v24 = -2147467263;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids,
            2147500033LL);
        Src = (void *)((unsigned __int64)Src ^ 1);
        goto LABEL_35;
      }
      v25 = a12;
      v32 = 0;
      LODWORD(Size) = 0;
      v26 = HrMapMarshalID(a12, &v32, (unsigned int *)&Size);
      v27 = v32;
      v24 = v26;
      if ( !v32 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_35;
        v30 = 15;
        goto LABEL_26;
      }
      memcpy_0(v32, Src, (unsigned int)Size);
      v26 = HrUnmapMarshalID(v27);
      v24 = v26;
      if ( v26 >= 0 )
      {
        if ( (a4 & 0x623) != 0 )
        {
          v28 = Src;
          *(_OWORD *)(a1 + 96) = *(_OWORD *)Src;
          *(_OWORD *)(a1 + 112) = v28[1];
          *(_OWORD *)(a1 + 128) = v28[2];
          *(_OWORD *)(a1 + 144) = v28[3];
          *(_OWORD *)(a1 + 160) = v28[4];
          *(_OWORD *)(a1 + 176) = v28[5];
          *(_QWORD *)(a1 + 192) = *((_QWORD *)v28 + 12);
        }
        v24 = 0;
        goto LABEL_35;
      }
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v30 = 14;
LABEL_26:
        WPP_SF_DD(v29[2], v30, WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids, v25, v26);
      }
    }
    else
    {
      v24 = HrResizeMarshalID(a12, 0);
    }
  }
LABEL_35:
  CoTaskMemFree(Src);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids, v24);
  return v24;
}

```

## disassembly

```asm
0x180018660  push    rbp
0x180018662  push    rbx
0x180018663  push    rsi
0x180018664  push    rdi
0x180018665  push    r12
0x180018667  push    r13
0x180018669  push    r14
0x18001866b  push    r15
0x18001866d  mov     rbp, rsp
0x180018670  sub     rsp, 68h
0x180018674  lea     rsi, [rcx+58h]
0x180018678  xor     r12d, r12d
0x18001867b  mov     r13d, r9d
0x18001867e  mov     rbx, r8
0x180018681  mov     r14, rdx
0x180018684  mov     rdi, rcx
0x180018687  cmp     [rsi], r12
0x18001868a  jnz     short loc_1800186FA
0x18001868c  mov     rax, [rbp+arg_50]
0x180018693  xor     r9d, r9d; struct IPXWizardTaskReportStub *
0x180018696  mov     r8, [rbp+arg_48]; struct IPXWizardNavigateStub *
0x18001869d  mov     rdx, [rbp+arg_40]; struct IPXWizardTransactionStub *
0x1800186a4  mov     rcx, [rbp+arg_38]; struct IPXWizardPropertyBagStub *
0x1800186ab  mov     [rsp+68h+var_40], rsi; struct IXWizardSource **
0x1800186b0  mov     [rsp+68h+var_48], rax; struct IPXWizardPageReportStub *
0x1800186b5  call    ?HrCreateInstance@CXWizardSourceStub@@SAJPEAUIPXWizardPropertyBagStub@@PEAUIPXWizardTransactionStub@@PEAUIPXWizardNavigateStub@@PEAUIPXWizardTaskReportStub@@PEAUIPXWizardPageReportStub@@PEAPEAUIXWizardSource@@@Z; CXWizardSourceStub::HrCreateInstance(IPXWizardPropertyBagStub *,IPXWizardTransactionStub *,IPXWizardNavigateStub *,IPXWizardTaskReportStub *,IPXWizardPageReportStub *,IXWizardSource * *)
0x1800186ba  mov     r15d, eax
0x1800186bd  test    eax, eax
0x1800186bf  jns     short loc_1800186FA
0x1800186c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186c8  lea     rsi, WPP_GLOBAL_Control
0x1800186cf  cmp     rcx, rsi
0x1800186d2  jz      short loc_1800186F2
0x1800186d4  test    byte ptr [rcx+1Ch], 4
0x1800186d8  jz      short loc_1800186F2
0x1800186da  mov     rcx, [rcx+10h]
0x1800186de  lea     edx, [r12+0Dh]
0x1800186e3  mov     r9d, eax
0x1800186e6  lea     r8, WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids
0x1800186ed  call    WPP_SF_d
0x1800186f2  mov     eax, r15d
0x1800186f5  jmp     loc_18001890A
0x1800186fa  mov     r10, [rdi+50h]
0x1800186fe  mov     rcx, [rbp+arg_28]
0x180018702  mov     rdx, [rsi]
0x180018705  mov     [rbp+Src], r12
0x180018709  mov     rax, [r10]
0x18001870c  mov     r11, [rax+38h]
0x180018710  test    rcx, rcx
0x180018713  jz      short loc_18001871E
0x180018715  cmp     [rcx], r12w
0x180018719  jnz     short loc_18001871E
0x18001871b  mov     rcx, r12
0x18001871e  test    rbx, rbx
0x180018721  jz      short loc_180018742
0x180018723  mov     rax, [rbx]
0x180018726  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18001872d  jnz     short loc_18001873A
0x18001872f  mov     rax, [rbx+8]
0x180018733  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18001873a  test    rax, rax
0x18001873d  jnz     short loc_180018742
0x18001873f  mov     rbx, r12
0x180018742  lea     rax, [rbp+Src]
0x180018746  mov     r9d, r13d
0x180018749  mov     [rsp+68h+var_28], rax
0x18001874e  mov     r8, rbx
0x180018751  mov     [rsp+68h+var_30], rdx
0x180018756  mov     rax, r11
0x180018759  mov     edx, [rbp+arg_30]
0x18001875c  mov     [rsp+68h+var_38], edx
0x180018760  mov     edx, [rbp+arg_20]
0x180018763  mov     [rsp+68h+var_40], rcx
0x180018768  mov     rcx, r10
0x18001876b  mov     dword ptr [rsp+68h+var_48], edx
0x18001876f  mov     rdx, r14
0x180018772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018777  lea     rsi, WPP_GLOBAL_Control
0x18001877e  mov     ebx, eax
0x180018780  lea     r14, WPP_cf12daad0a4e3cade8be3fb4e2dbd0df_Traceguids
0x180018787  test    eax, eax
0x180018789  jnz     loc_1800188D8
0x18001878f  mov     rax, [rbp+Src]
0x180018793  test    rax, rax
0x180018796  jz      loc_1800188C8
0x18001879c  test    al, 1
0x18001879e  jnz     loc_180018893
0x1800187a4  movzx   r15d, [rbp+arg_58]
0x1800187ac  lea     r8, [rbp+Size]; unsigned int *
0x1800187b0  movzx   ecx, r15w; unsigned __int16
0x1800187b4  mov     [rbp+var_10], r12
0x1800187b8  lea     rdx, [rbp+var_10]; void **
0x1800187bc  mov     dword ptr [rbp+Size], r12d
0x1800187c0  call    ?HrMapMarshalID@@YAJGPEAPEAXPEAK@Z; HrMapMarshalID(ushort,void * *,ulong *)
0x1800187c5  mov     r12, [rbp+var_10]
0x1800187c9  mov     ebx, eax
0x1800187cb  test    r12, r12
0x1800187ce  jz      loc_18001887A
0x1800187d4  mov     r8d, dword ptr [rbp+Size]; Size
0x1800187d8  mov     rcx, r12; void *
0x1800187db  mov     rdx, [rbp+Src]; Src
0x1800187df  call    memcpy_0
0x1800187e4  mov     rcx, r12; void *
0x1800187e7  call    ?HrUnmapMarshalID@@YAJPEAX@Z; HrUnmapMarshalID(void *)
0x1800187ec  mov     ebx, eax
0x1800187ee  test    eax, eax
0x1800187f0  js      short loc_18001884E
0x1800187f2  test    r13d, 623h
0x1800187f9  jz      short loc_180018847
0x1800187fb  mov     rax, [rbp+Src]
0x1800187ff  movups  xmm0, xmmword ptr [rax]
0x180018802  movups  xmmword ptr [rdi+60h], xmm0
0x180018806  movups  xmm1, xmmword ptr [rax+10h]
0x18001880a  movups  xmmword ptr [rdi+70h], xmm1
0x18001880e  movups  xmm0, xmmword ptr [rax+20h]
0x180018812  movups  xmmword ptr [rdi+80h], xmm0
0x180018819  movups  xmm1, xmmword ptr [rax+30h]
0x18001881d  movups  xmmword ptr [rdi+90h], xmm1
0x180018824  movups  xmm0, xmmword ptr [rax+40h]
0x180018828  movups  xmmword ptr [rdi+0A0h], xmm0
0x18001882f  movups  xmm1, xmmword ptr [rax+50h]
0x180018833  movups  xmmword ptr [rdi+0B0h], xmm1
0x18001883a  movsd   xmm0, qword ptr [rax+60h]
0x18001883f  movsd   qword ptr [rdi+0C0h], xmm0
0x180018847  xor     ebx, ebx
0x180018849  jmp     loc_1800188D8
0x18001884e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018855  cmp     rcx, rsi
0x180018858  jz      short loc_1800188D8
0x18001885a  test    byte ptr [rcx+1Ch], 4
0x18001885e  jz      short loc_1800188D8
0x180018860  mov     edx, 0Eh
0x180018865  mov     rcx, [rcx+10h]
0x180018869  mov     r9d, r15d
0x18001886c  mov     r8, r14
0x18001886f  mov     dword ptr [rsp+68h+var_48], eax
0x180018873  call    WPP_SF_DD
0x180018878  jmp     short loc_1800188D8
0x18001887a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018881  cmp     rcx, rsi
0x180018884  jz      short loc_1800188D8
0x180018886  test    byte ptr [rcx+1Ch], 4
0x18001888a  jz      short loc_1800188D8
0x18001888c  mov     edx, 0Fh
0x180018891  jmp     short loc_180018865
0x180018893  mov     ebx, 80004001h
0x180018898  mov     rcx, cs:WPP_GLOBAL_Control
0x18001889f  cmp     rcx, rsi
0x1800188a2  jz      short loc_1800188C1
0x1800188a4  test    byte ptr [rcx+1Ch], 8
0x1800188a8  jz      short loc_1800188C1
0x1800188aa  mov     rcx, [rcx+10h]
0x1800188ae  mov     edx, 10h
0x1800188b3  mov     r9d, 80004001h
0x1800188b9  mov     r8, r14
0x1800188bc  call    WPP_SF_d
0x1800188c1  xor     [rbp+Src], 1
0x1800188c6  jmp     short loc_1800188D8
0x1800188c8  movzx   ecx, [rbp+arg_58]; unsigned __int16
0x1800188cf  xor     edx, edx; unsigned int
0x1800188d1  call    ?HrResizeMarshalID@@YAJGK@Z; HrResizeMarshalID(ushort,ulong)
0x1800188d6  mov     ebx, eax
0x1800188d8  mov     rcx, [rbp+Src]; pv
0x1800188dc  call    cs:__imp_CoTaskMemFree
0x1800188e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800188e9  cmp     rcx, rsi
0x1800188ec  jz      short loc_180018908
0x1800188ee  test    byte ptr [rcx+1Ch], 10h
0x1800188f2  jz      short loc_180018908
0x1800188f4  mov     rcx, [rcx+10h]
0x1800188f8  mov     edx, 11h
0x1800188fd  mov     r9d, ebx
0x180018900  mov     r8, r14
0x180018903  call    WPP_SF_d
0x180018908  mov     eax, ebx
0x18001890a  add     rsp, 68h
0x18001890e  pop     r15
0x180018910  pop     r14
0x180018912  pop     r13
0x180018914  pop     r12
0x180018916  pop     rdi
0x180018917  pop     rsi
0x180018918  pop     rbx
0x180018919  pop     rbp
0x18001891a  retn
```
