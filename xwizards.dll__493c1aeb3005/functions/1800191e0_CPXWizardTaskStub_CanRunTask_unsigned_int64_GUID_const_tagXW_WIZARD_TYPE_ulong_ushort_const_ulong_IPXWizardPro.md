# CPXWizardTaskStub::CanRunTask(unsigned __int64,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IPXWizardPropertyBagStub *,IPXWizardTransactionStub *,IPXWizardNavigateStub *,IPXWizardTaskReportStub *,ushort)

- ea: `0x1800191e0`
- end: `0x180019437`
- name: `?CanRunTask@CPXWizardTaskStub@@UEAAJ_KQEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIPXWizardPropertyBagStub@@PEAUIPXWizardTransactionStub@@PEAUIPXWizardNavigateStub@@PEAUIPXWizardTaskReportStub@@G@Z`
- size: `599`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002556`
- `0x18000ae04`
- `0x18000ae44`
- `0x1800191e0`
- `0x180019bf0`
- `0x18001af64`
- `0x18001b6e4`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193f4`

## pseudocode

```c
__int64 __fastcall CPXWizardTaskStub::CanRunTask(
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
        struct IPXWizardTaskReportStub *a11,
        unsigned __int16 a12)
{
  struct IXWizardSource **v12; // rsi
  int Instance; // eax
  unsigned int v18; // r14d
  __int64 v20; // r10
  _WORD *v21; // rcx
  struct IXWizardSource *v22; // rdx
  __int64 v23; // rax
  unsigned int v24; // ebx
  unsigned int v25; // r14d
  int v26; // eax
  void *v27; // r15
  _OWORD *v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  void *Src; // [rsp+50h] [rbp-18h] BYREF
  void *v32; // [rsp+58h] [rbp-10h] BYREF
  size_t Size; // [rsp+B0h] [rbp+48h] BYREF

  v12 = (struct IXWizardSource **)(a1 + 88);
  if ( !*(_QWORD *)(a1 + 88) )
  {
    Instance = CXWizardSourceStub::HrCreateInstance(a8, a9, a10, a11, 0, v12);
    v18 = Instance;
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_0ee650487c993580f623fc88d5d02f33_Traceguids,
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
  if ( !v24 && Src )
  {
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
        goto LABEL_29;
      v30 = 18;
      goto LABEL_28;
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
      }
      v24 = 0;
      goto LABEL_29;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v30 = 17;
LABEL_28:
      WPP_SF_DD(v29[2], v30, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids, v25, v26);
    }
  }
LABEL_29:
  CoTaskMemFree(Src);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids, v24);
  return v24;
}

```

## disassembly

```asm
0x1800191e0  push    rbp
0x1800191e2  push    rbx
0x1800191e3  push    rsi
0x1800191e4  push    rdi
0x1800191e5  push    r12
0x1800191e7  push    r13
0x1800191e9  push    r14
0x1800191eb  push    r15
0x1800191ed  mov     rbp, rsp
0x1800191f0  sub     rsp, 68h
0x1800191f4  lea     rsi, [rcx+58h]
0x1800191f8  xor     r13d, r13d
0x1800191fb  mov     r12d, r9d
0x1800191fe  mov     rbx, r8
0x180019201  mov     r15, rdx
0x180019204  mov     rdi, rcx
0x180019207  cmp     [rsi], r13
0x18001920a  jnz     short loc_180019276
0x18001920c  mov     r9, [rbp+arg_50]; struct IPXWizardTaskReportStub *
0x180019213  mov     r8, [rbp+arg_48]; struct IPXWizardNavigateStub *
0x18001921a  mov     rdx, [rbp+arg_40]; struct IPXWizardTransactionStub *
0x180019221  mov     rcx, [rbp+arg_38]; struct IPXWizardPropertyBagStub *
0x180019228  mov     [rsp+68h+var_40], rsi; struct IXWizardSource **
0x18001922d  mov     [rsp+68h+var_48], r13; struct IPXWizardPageReportStub *
0x180019232  call    ?HrCreateInstance@CXWizardSourceStub@@SAJPEAUIPXWizardPropertyBagStub@@PEAUIPXWizardTransactionStub@@PEAUIPXWizardNavigateStub@@PEAUIPXWizardTaskReportStub@@PEAUIPXWizardPageReportStub@@PEAPEAUIXWizardSource@@@Z; CXWizardSourceStub::HrCreateInstance(IPXWizardPropertyBagStub *,IPXWizardTransactionStub *,IPXWizardNavigateStub *,IPXWizardTaskReportStub *,IPXWizardPageReportStub *,IXWizardSource * *)
0x180019237  mov     r14d, eax
0x18001923a  test    eax, eax
0x18001923c  jns     short loc_180019276
0x18001923e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019245  lea     rsi, WPP_GLOBAL_Control
0x18001924c  cmp     rcx, rsi
0x18001924f  jz      short loc_18001926E
0x180019251  test    byte ptr [rcx+1Ch], 4
0x180019255  jz      short loc_18001926E
0x180019257  mov     rcx, [rcx+10h]
0x18001925b  lea     edx, [r13+10h]
0x18001925f  mov     r9d, eax
0x180019262  lea     r8, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids
0x180019269  call    WPP_SF_d
0x18001926e  mov     eax, r14d
0x180019271  jmp     loc_180019426
0x180019276  mov     r10, [rdi+50h]
0x18001927a  mov     rcx, [rbp+arg_28]
0x18001927e  mov     rdx, [rsi]
0x180019281  mov     [rbp+Src], r13
0x180019285  mov     rax, [r10]
0x180019288  mov     r11, [rax+38h]
0x18001928c  test    rcx, rcx
0x18001928f  jz      short loc_18001929A
0x180019291  cmp     [rcx], r13w
0x180019295  jnz     short loc_18001929A
0x180019297  mov     rcx, r13
0x18001929a  test    rbx, rbx
0x18001929d  jz      short loc_1800192BE
0x18001929f  mov     rax, [rbx]
0x1800192a2  sub     rax, qword ptr cs:GUID_NULL.Data1
0x1800192a9  jnz     short loc_1800192B6
0x1800192ab  mov     rax, [rbx+8]
0x1800192af  sub     rax, qword ptr cs:GUID_NULL.Data4
0x1800192b6  test    rax, rax
0x1800192b9  jnz     short loc_1800192BE
0x1800192bb  mov     rbx, r13
0x1800192be  lea     rax, [rbp+Src]
0x1800192c2  mov     r9d, r12d
0x1800192c5  mov     [rsp+68h+var_28], rax
0x1800192ca  mov     r8, rbx
0x1800192cd  mov     [rsp+68h+var_30], rdx
0x1800192d2  mov     rax, r11
0x1800192d5  mov     edx, [rbp+arg_30]
0x1800192d8  mov     [rsp+68h+var_38], edx
0x1800192dc  mov     edx, [rbp+arg_20]
0x1800192df  mov     [rsp+68h+var_40], rcx
0x1800192e4  mov     rcx, r10
0x1800192e7  mov     dword ptr [rsp+68h+var_48], edx
0x1800192eb  mov     rdx, r15
0x1800192ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192f3  lea     rsi, WPP_GLOBAL_Control
0x1800192fa  mov     ebx, eax
0x1800192fc  test    eax, eax
0x1800192fe  jnz     loc_1800193F0
0x180019304  cmp     [rbp+Src], r13
0x180019308  jz      loc_1800193F0
0x18001930e  movzx   r14d, [rbp+arg_58]
0x180019316  lea     r8, [rbp+Size]; unsigned int *
0x18001931a  movzx   ecx, r14w; unsigned __int16
0x18001931e  mov     [rbp+var_10], r13
0x180019322  lea     rdx, [rbp+var_10]; void **
0x180019326  mov     dword ptr [rbp+Size], r13d
0x18001932a  call    ?HrMapMarshalID@@YAJGPEAPEAXPEAK@Z; HrMapMarshalID(ushort,void * *,ulong *)
0x18001932f  mov     r15, [rbp+var_10]
0x180019333  mov     ebx, eax
0x180019335  test    r15, r15
0x180019338  jz      loc_1800193C2
0x18001933e  mov     r8d, dword ptr [rbp+Size]; Size
0x180019342  mov     rcx, r15; void *
0x180019345  mov     rdx, [rbp+Src]; Src
0x180019349  call    memcpy_0
0x18001934e  mov     rcx, r15; void *
0x180019351  call    ?HrUnmapMarshalID@@YAJPEAX@Z; HrUnmapMarshalID(void *)
0x180019356  mov     ebx, eax
0x180019358  test    eax, eax
0x18001935a  js      short loc_1800193A9
0x18001935c  test    r12d, 623h
0x180019363  jz      short loc_1800193A4
0x180019365  mov     rax, [rbp+Src]
0x180019369  movups  xmm0, xmmword ptr [rax]
0x18001936c  movups  xmmword ptr [rdi+60h], xmm0
0x180019370  movups  xmm1, xmmword ptr [rax+10h]
0x180019374  movups  xmmword ptr [rdi+70h], xmm1
0x180019378  movups  xmm0, xmmword ptr [rax+20h]
0x18001937c  movups  xmmword ptr [rdi+80h], xmm0
0x180019383  movups  xmm1, xmmword ptr [rax+30h]
0x180019387  movups  xmmword ptr [rdi+90h], xmm1
0x18001938e  movups  xmm0, xmmword ptr [rax+40h]
0x180019392  movups  xmmword ptr [rdi+0A0h], xmm0
0x180019399  movups  xmm1, xmmword ptr [rax+50h]
0x18001939d  movups  xmmword ptr [rdi+0B0h], xmm1
0x1800193a4  mov     ebx, r13d
0x1800193a7  jmp     short loc_1800193F0
0x1800193a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193b0  cmp     rcx, rsi
0x1800193b3  jz      short loc_1800193F0
0x1800193b5  test    byte ptr [rcx+1Ch], 4
0x1800193b9  jz      short loc_1800193F0
0x1800193bb  mov     edx, 11h
0x1800193c0  jmp     short loc_1800193D9
0x1800193c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193c9  cmp     rcx, rsi
0x1800193cc  jz      short loc_1800193F0
0x1800193ce  test    byte ptr [rcx+1Ch], 4
0x1800193d2  jz      short loc_1800193F0
0x1800193d4  mov     edx, 12h
0x1800193d9  mov     rcx, [rcx+10h]
0x1800193dd  lea     r8, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids
0x1800193e4  mov     r9d, r14d
0x1800193e7  mov     dword ptr [rsp+68h+var_48], eax
0x1800193eb  call    WPP_SF_DD
0x1800193f0  mov     rcx, [rbp+Src]; pv
0x1800193f4  call    cs:__imp_CoTaskMemFree
0x1800193fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180019401  cmp     rcx, rsi
0x180019404  jz      short loc_180019424
0x180019406  test    byte ptr [rcx+1Ch], 10h
0x18001940a  jz      short loc_180019424
0x18001940c  mov     rcx, [rcx+10h]
0x180019410  lea     r8, WPP_0ee650487c993580f623fc88d5d02f33_Traceguids
0x180019417  mov     edx, 13h
0x18001941c  mov     r9d, ebx
0x18001941f  call    WPP_SF_d
0x180019424  mov     eax, ebx
0x180019426  add     rsp, 68h
0x18001942a  pop     r15
0x18001942c  pop     r14
0x18001942e  pop     r13
0x180019430  pop     r12
0x180019432  pop     rdi
0x180019433  pop     rsi
0x180019434  pop     rbx
0x180019435  pop     rbp
0x180019436  retn
```
