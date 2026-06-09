# CPXWizardPageProxy::HrCreateInstance(HWND__ *,_GUID *,IMultiObjectElevationFactory * *,IPXWizardTypeEvent *,IXWizardPageEvent * *)

- ea: `0x18002ea84`
- end: `0x18002ed37`
- name: `?HrCreateInstance@CPXWizardPageProxy@@SAJPEAUHWND__@@PEAU_GUID@@PEAPEAUIMultiObjectElevationFactory@@PEAUIPXWizardTypeEvent@@PEAPEAUIXWizardPageEvent@@@Z`
- size: `691`
- prototype: `__int64 __usercall@<rax>(HWND@<rcx>, struct _GUID *@<rdx>, struct IMultiObjectElevationFactory **@<r8>, struct IPXWizardTypeEvent *@<r9>, struct IXWizardPageEvent **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021634`

## callees

- `0x180001200`
- `0x18000ae04`
- `0x18000f024`
- `0x18002dee4`
- `0x18002ea84`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ec75`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ec75`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPXWizardPageProxy::HrCreateInstance(
        HWND a1,
        struct _GUID *a2,
        LPVOID *a3,
        struct IPXWizardTypeEvent *a4,
        struct IXWizardPageEvent **a5)
{
  LPVOID *v5; // r15
  struct _GUID *v6; // r12
  HWND v7; // r13
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int v11; // esi
  struct IXWizardPageEvent **v12; // r14
  CPXWizardPageProxy *v13; // rax
  CPXWizardPageProxy *v14; // rbx
  unsigned int v15; // eax
  unsigned int ElevatedInstance; // eax
  CPXWizardPageProxy *v17; // [rsp+38h] [rbp-50h]
  int v21; // [rsp+A8h] [rbp+20h] BYREF

  v5 = a3;
  v6 = a2;
  v7 = a1;
  v21 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IPXWizardTypeEvent *, int *))(*(_QWORD *)a4 + 72LL))(a4, &v21);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids,
        (unsigned int)v8);
    return v9;
  }
  try
  {
    v11 = -2147024882;
    v12 = a5;
    *a5 = 0;
    v13 = (CPXWizardPageProxy *)operator new(0x70u);
    v14 = v13;
    if ( v13 )
    {
      CPXWizardPageProxy::CPXWizardPageProxy(v13);
      *(_QWORD *)v14 = &ATL::CComObject<CPXWizardPageProxy>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v17 = v14;
  }
  catch ( ... )
  {
    v12 = a5;
    v5 = a3;
    v6 = a2;
    v7 = a1;
    v14 = v17;
    v11 = -2147024882;
  }
  if ( v14 )
  {
    v15 = (**(__int64 (__fastcall ***)(CPXWizardPageProxy *, GUID *, struct IXWizardPageEvent **))v14)(
            v14,
            &IID_IXWizardPageEvent,
            v12);
    v11 = v15;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids, v15);
    }
    else
    {
      if ( v5 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids, v6->Data1);
        *((_DWORD *)v14 + 16) = 4096;
        ElevatedInstance = CoCreateElevatedInstance(
                             v7,
                             v5,
                             &CLSID_CPXWizardPageStub,
                             &IID_IPXWizardPageEventStub,
                             (void **)v14 + 9);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids, v6->Data1);
        *((_DWORD *)v14 + 16) = 256;
        ElevatedInstance = CoCreateInstance(
                             &CLSID_CPXWizardPageStub,
                             0,
                             0x404u,
                             &IID_IPXWizardPageEventStub,
                             (LPVOID *)v14 + 9);
      }
      v11 = ElevatedInstance;
      if ( !ElevatedInstance )
      {
        *((_DWORD *)v14 + 17) = v21;
        v11 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)v14 + 9) + 56LL))(
                *((_QWORD *)v14 + 9),
                v6);
        if ( !v11 )
          goto LABEL_27;
      }
    }
    (*(void (__fastcall **)(CPXWizardPageProxy *, __int64))(*(_QWORD *)v14 + 96LL))(v14, 1);
    *v12 = 0;
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18002ea84  mov     r11, rsp
0x18002ea87  mov     [r11+18h], r8
0x18002ea8b  mov     [r11+10h], rdx
0x18002ea8f  mov     [r11+8], rcx
0x18002ea93  push    rbx
0x18002ea94  push    rsi
0x18002ea95  push    rdi
0x18002ea96  push    r12
0x18002ea98  push    r13
0x18002ea9a  push    r14
0x18002ea9c  push    r15
0x18002ea9e  sub     rsp, 50h
0x18002eaa2  mov     r15, r8
0x18002eaa5  mov     r12, rdx
0x18002eaa8  mov     r13, rcx
0x18002eaab  mov     dword ptr [r11+20h], 0
0x18002eab3  mov     rax, [r9]
0x18002eab6  lea     rdx, [r11+20h]
0x18002eaba  mov     rcx, r9
0x18002eabd  mov     rax, [rax+48h]
0x18002eac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eac6  mov     ebx, eax
0x18002eac8  test    eax, eax
0x18002eaca  jns     short loc_18002EB04
0x18002eacc  lea     rdi, WPP_GLOBAL_Control
0x18002ead3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eada  cmp     rcx, rdi
0x18002eadd  jz      short loc_18002EAFD
0x18002eadf  test    byte ptr [rcx+1Ch], 4
0x18002eae3  jz      short loc_18002EAFD
0x18002eae5  mov     edx, 2Ah ; '*'
0x18002eaea  mov     r9d, eax
0x18002eaed  lea     r8, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids
0x18002eaf4  mov     rcx, [rcx+10h]
0x18002eaf8  call    WPP_SF_d
0x18002eafd  mov     eax, ebx
0x18002eaff  jmp     loc_18002ED27
0x18002eb04  mov     [rsp+88h+var_50], 0
0x18002eb0d  mov     esi, 8007000Eh
0x18002eb12  mov     [rsp+88h+var_58], esi
0x18002eb16  mov     r14, [rsp+88h+arg_20]
0x18002eb1e  mov     qword ptr [r14], 0
0x18002eb25  mov     ecx, 70h ; 'p'; Size
0x18002eb2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002eb2f  mov     rbx, rax
0x18002eb32  mov     [rsp+88h+var_48], rax
0x18002eb37  test    rbx, rbx
0x18002eb3a  jz      short loc_18002EB62
0x18002eb3c  mov     rcx, rax; this
0x18002eb3f  call    ??0CPXWizardPageProxy@@QEAA@XZ; CPXWizardPageProxy::CPXWizardPageProxy(void)
0x18002eb44  lea     rax, ??_7?$CComObject@VCPXWizardPageProxy@@@ATL@@6B@; const ATL::CComObject<CPXWizardPageProxy>::`vftable'
0x18002eb4b  mov     [rbx], rax
0x18002eb4e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002eb55  mov     rax, [rcx]
0x18002eb58  mov     rax, [rax+8]
0x18002eb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb61  nop
0x18002eb62  mov     [rsp+88h+var_50], rbx
0x18002eb67  jmp     short loc_18002EB92
0x18002eb69  mov     r14, [rsp+88h+arg_20]
0x18002eb71  mov     r15, [rsp+88h+arg_10]
0x18002eb79  mov     r12, [rsp+88h+arg_8]
0x18002eb81  mov     r13, [rsp+88h+arg_0]
0x18002eb89  mov     rbx, [rsp+88h+var_50]
0x18002eb8e  mov     esi, [rsp+88h+var_58]
0x18002eb92  test    rbx, rbx
0x18002eb95  jz      loc_18002ECF4
0x18002eb9b  mov     rax, [rbx]
0x18002eb9e  mov     r8, r14
0x18002eba1  lea     rdx, IID_IXWizardPageEvent
0x18002eba8  mov     rcx, rbx
0x18002ebab  mov     rax, [rax]
0x18002ebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebb3  mov     esi, eax
0x18002ebb5  test    eax, eax
0x18002ebb7  jnz     loc_18002ECA6
0x18002ebbd  test    r15, r15
0x18002ebc0  jz      short loc_18002EC1D
0x18002ebc2  lea     rdi, WPP_GLOBAL_Control
0x18002ebc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebd0  cmp     rcx, rdi
0x18002ebd3  jz      short loc_18002EBF2
0x18002ebd5  test    byte ptr [rcx+1Ch], 8
0x18002ebd9  jz      short loc_18002EBF2
0x18002ebdb  lea     edx, [rax+2Bh]
0x18002ebde  mov     r9d, [r12]
0x18002ebe2  lea     r8, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids
0x18002ebe9  mov     rcx, [rcx+10h]
0x18002ebed  call    WPP_SF_d
0x18002ebf2  mov     dword ptr [rbx+40h], 1000h
0x18002ebf9  lea     rax, [rbx+48h]
0x18002ebfd  mov     [rsp+88h+ppv], rax; void **
0x18002ec02  lea     r9, IID_IPXWizardPageEventStub; struct _GUID *
0x18002ec09  lea     r8, CLSID_CPXWizardPageStub; struct _GUID *
0x18002ec10  mov     rdx, r15; struct IMultiObjectElevationFactory **
0x18002ec13  mov     rcx, r13; HWND
0x18002ec16  call    ?CoCreateElevatedInstance@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@AEBU_GUID@@2PEAPEAX@Z; CoCreateElevatedInstance(HWND__ *,IMultiObjectElevationFactory * *,_GUID const &,_GUID const &,void * *)
0x18002ec1b  jmp     short loc_18002EC7B
0x18002ec1d  lea     rdi, WPP_GLOBAL_Control
0x18002ec24  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec2b  cmp     rcx, rdi
0x18002ec2e  jz      short loc_18002EC4F
0x18002ec30  test    byte ptr [rcx+1Ch], 8
0x18002ec34  jz      short loc_18002EC4F
0x18002ec36  mov     edx, 2Ch ; ','
0x18002ec3b  mov     r9d, [r12]
0x18002ec3f  lea     r8, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids
0x18002ec46  mov     rcx, [rcx+10h]
0x18002ec4a  call    WPP_SF_d
0x18002ec4f  mov     dword ptr [rbx+40h], 100h
0x18002ec56  lea     rax, [rbx+48h]
0x18002ec5a  mov     [rsp+88h+ppv], rax; ppv
0x18002ec5f  lea     r9, IID_IPXWizardPageEventStub; riid
0x18002ec66  xor     edx, edx; pUnkOuter
0x18002ec68  mov     r8d, 404h; dwClsContext
0x18002ec6e  lea     rcx, CLSID_CPXWizardPageStub; rclsid
0x18002ec75  call    cs:__imp_CoCreateInstance
0x18002ec7b  mov     esi, eax
0x18002ec7d  test    eax, eax
0x18002ec7f  jnz     short loc_18002ECD7
0x18002ec81  mov     eax, [rsp+88h+arg_18]
0x18002ec88  mov     [rbx+44h], eax
0x18002ec8b  mov     rcx, [rbx+48h]
0x18002ec8f  mov     rax, [rcx]
0x18002ec92  mov     rdx, r12
0x18002ec95  mov     rax, [rax+38h]
0x18002ec99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ec9e  mov     esi, eax
0x18002eca0  test    eax, eax
0x18002eca2  jz      short loc_18002ECFB
0x18002eca4  jmp     short loc_18002ECD7
0x18002eca6  lea     rdi, WPP_GLOBAL_Control
0x18002ecad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecb4  cmp     rcx, rdi
0x18002ecb7  jz      short loc_18002ECD7
0x18002ecb9  test    byte ptr [rcx+1Ch], 4
0x18002ecbd  jz      short loc_18002ECD7
0x18002ecbf  mov     edx, 2Dh ; '-'
0x18002ecc4  mov     r9d, eax
0x18002ecc7  lea     r8, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids
0x18002ecce  mov     rcx, [rcx+10h]
0x18002ecd2  call    WPP_SF_d
0x18002ecd7  mov     rax, [rbx]
0x18002ecda  mov     edx, 1
0x18002ecdf  mov     rcx, rbx
0x18002ece2  mov     rax, [rax+60h]
0x18002ece6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eceb  mov     qword ptr [r14], 0
0x18002ecf2  jmp     short loc_18002ECFB
0x18002ecf4  lea     rdi, WPP_GLOBAL_Control
0x18002ecfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed02  cmp     rcx, rdi
0x18002ed05  jz      short loc_18002ED25
0x18002ed07  test    byte ptr [rcx+1Ch], 10h
0x18002ed0b  jz      short loc_18002ED25
0x18002ed0d  mov     edx, 2Fh ; '/'
0x18002ed12  mov     r9d, esi
0x18002ed15  lea     r8, WPP_a74ea408886f3a261c4767565e0d96a3_Traceguids
0x18002ed1c  mov     rcx, [rcx+10h]
0x18002ed20  call    WPP_SF_d
0x18002ed25  mov     eax, esi
0x18002ed27  add     rsp, 50h
0x18002ed2b  pop     r15
0x18002ed2d  pop     r14
0x18002ed2f  pop     r13
0x18002ed31  pop     r12
0x18002ed33  pop     rdi
0x18002ed34  pop     rsi
0x18002ed35  pop     rbx
0x18002ed36  retn
```
