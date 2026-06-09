# CPXWizardTaskProxy::HrCreateInstance(HWND__ *,_GUID *,IMultiObjectElevationFactory * *,IPXWizardTypeEvent *,IXWizardTaskEvent * *)

- ea: `0x18002f9c8`
- end: `0x18002fc7e`
- name: `?HrCreateInstance@CPXWizardTaskProxy@@SAJPEAUHWND__@@PEAU_GUID@@PEAPEAUIMultiObjectElevationFactory@@PEAUIPXWizardTypeEvent@@PEAPEAUIXWizardTaskEvent@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(HWND, struct _GUID *, LPVOID *, struct IPXWizardTypeEvent *, struct IXWizardTaskEvent **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f6f8`
- `0x18002bae0`

## callees

- `0x180001200`
- `0x18000ae04`
- `0x18000f024`
- `0x18002f0d8`
- `0x18002f9c8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fbb9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fbb9`

## pseudocode

```c
__int64 __fastcall CPXWizardTaskProxy::HrCreateInstance(
        HWND a1,
        struct _GUID *a2,
        LPVOID *a3,
        struct IPXWizardTypeEvent *a4,
        struct IXWizardTaskEvent **a5)
{
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int v11; // esi
  struct IXWizardTaskEvent **v12; // r14
  CPXWizardTaskProxy *v13; // rax
  CPXWizardTaskProxy *v14; // rbx
  unsigned int v15; // eax
  unsigned int ElevatedInstance; // eax
  int v17; // [rsp+A8h] [rbp+20h] BYREF

  v17 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IPXWizardTypeEvent *, int *))(*(_QWORD *)a4 + 56LL))(a4, &v17);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids,
        (unsigned int)v8);
    return v9;
  }
  v11 = -2147024882;
  v12 = a5;
  *a5 = 0;
  v13 = (CPXWizardTaskProxy *)operator new(0x58u);
  v14 = v13;
  if ( v13 )
  {
    CPXWizardTaskProxy::CPXWizardTaskProxy(v13);
    *(_QWORD *)v14 = &ATL::CComObject<CPXWizardTaskProxy>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v14 )
  {
    v15 = (**(__int64 (__fastcall ***)(CPXWizardTaskProxy *, GUID *, struct IXWizardTaskEvent **))v14)(
            v14,
            &IID_IXWizardTaskEvent,
            v12);
    v11 = v15;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids, v15);
    }
    else
    {
      if ( a3 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids, a2->Data1);
        *((_DWORD *)v14 + 16) = 4096;
        ElevatedInstance = CoCreateElevatedInstance(
                             a1,
                             a3,
                             &CLSID_CPXWizardTaskStub,
                             &IID_IPXWizardTaskEventStub,
                             (void **)v14 + 9);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids, a2->Data1);
        *((_DWORD *)v14 + 16) = 256;
        ElevatedInstance = CoCreateInstance(
                             &CLSID_CPXWizardTaskStub,
                             0,
                             0x404u,
                             &IID_IPXWizardTaskEventStub,
                             (LPVOID *)v14 + 9);
      }
      v11 = ElevatedInstance;
      if ( !ElevatedInstance )
      {
        *((_DWORD *)v14 + 17) = v17;
        v11 = (*(__int64 (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)v14 + 9) + 48LL))(
                *((_QWORD *)v14 + 9),
                a2);
        if ( !v11 )
          goto LABEL_26;
      }
    }
    (*(void (__fastcall **)(CPXWizardTaskProxy *, __int64))(*(_QWORD *)v14 + 136LL))(v14, 1);
    *v12 = 0;
  }
LABEL_26:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18002f9c8  mov     r11, rsp
0x18002f9cb  mov     [r11+18h], r8
0x18002f9cf  mov     [r11+10h], rdx
0x18002f9d3  mov     [r11+8], rcx
0x18002f9d7  push    rbx
0x18002f9d8  push    rsi
0x18002f9d9  push    rdi
0x18002f9da  push    r12
0x18002f9dc  push    r13
0x18002f9de  push    r14
0x18002f9e0  push    r15
0x18002f9e2  sub     rsp, 50h
0x18002f9e6  mov     r15, r8
0x18002f9e9  mov     r12, rdx
0x18002f9ec  mov     r13, rcx
0x18002f9ef  mov     dword ptr [r11+20h], 0
0x18002f9f7  mov     rax, [r9]
0x18002f9fa  lea     rdx, [r11+20h]
0x18002f9fe  mov     rcx, r9
0x18002fa01  mov     rax, [rax+38h]
0x18002fa05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa0a  mov     ebx, eax
0x18002fa0c  test    eax, eax
0x18002fa0e  jns     short loc_18002FA48
0x18002fa10  lea     rdi, WPP_GLOBAL_Control
0x18002fa17  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa1e  cmp     rcx, rdi
0x18002fa21  jz      short loc_18002FA41
0x18002fa23  test    byte ptr [rcx+1Ch], 4
0x18002fa27  jz      short loc_18002FA41
0x18002fa29  mov     edx, 27h ; '''
0x18002fa2e  mov     r9d, eax
0x18002fa31  lea     r8, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids
0x18002fa38  mov     rcx, [rcx+10h]
0x18002fa3c  call    WPP_SF_d
0x18002fa41  mov     eax, ebx
0x18002fa43  jmp     loc_18002FC6E
0x18002fa48  mov     [rsp+88h+var_50], 0
0x18002fa51  mov     esi, 8007000Eh
0x18002fa56  mov     [rsp+88h+var_58], esi
0x18002fa5a  mov     r14, [rsp+88h+arg_20]
0x18002fa62  mov     qword ptr [r14], 0
0x18002fa69  mov     ecx, 58h ; 'X'; Size
0x18002fa6e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fa73  mov     rbx, rax
0x18002fa76  mov     [rsp+88h+var_48], rax
0x18002fa7b  test    rbx, rbx
0x18002fa7e  jz      short loc_18002FAA6
0x18002fa80  mov     rcx, rax; this
0x18002fa83  call    ??0CPXWizardTaskProxy@@QEAA@XZ; CPXWizardTaskProxy::CPXWizardTaskProxy(void)
0x18002fa88  lea     rax, ??_7?$CComObject@VCPXWizardTaskProxy@@@ATL@@6B@; const ATL::CComObject<CPXWizardTaskProxy>::`vftable'
0x18002fa8f  mov     [rbx], rax
0x18002fa92  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002fa99  mov     rax, [rcx]
0x18002fa9c  mov     rax, [rax+8]
0x18002faa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faa5  nop
0x18002faa6  mov     [rsp+88h+var_50], rbx
0x18002faab  jmp     short loc_18002FAD6
0x18002faad  mov     r14, [rsp+88h+arg_20]
0x18002fab5  mov     r15, [rsp+88h+arg_10]
0x18002fabd  mov     r12, [rsp+88h+arg_8]
0x18002fac5  mov     r13, [rsp+88h+arg_0]
0x18002facd  mov     rbx, [rsp+88h+var_50]
0x18002fad2  mov     esi, [rsp+88h+var_58]
0x18002fad6  test    rbx, rbx
0x18002fad9  jz      loc_18002FC3B
0x18002fadf  mov     rax, [rbx]
0x18002fae2  mov     r8, r14
0x18002fae5  lea     rdx, IID_IXWizardTaskEvent
0x18002faec  mov     rcx, rbx
0x18002faef  mov     rax, [rax]
0x18002faf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002faf7  mov     esi, eax
0x18002faf9  test    eax, eax
0x18002fafb  jnz     loc_18002FBEA
0x18002fb01  test    r15, r15
0x18002fb04  jz      short loc_18002FB61
0x18002fb06  lea     rdi, WPP_GLOBAL_Control
0x18002fb0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb14  cmp     rcx, rdi
0x18002fb17  jz      short loc_18002FB36
0x18002fb19  test    byte ptr [rcx+1Ch], 8
0x18002fb1d  jz      short loc_18002FB36
0x18002fb1f  lea     edx, [rax+28h]
0x18002fb22  mov     r9d, [r12]
0x18002fb26  lea     r8, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids
0x18002fb2d  mov     rcx, [rcx+10h]
0x18002fb31  call    WPP_SF_d
0x18002fb36  mov     dword ptr [rbx+40h], 1000h
0x18002fb3d  lea     rax, [rbx+48h]
0x18002fb41  mov     [rsp+88h+ppv], rax; void **
0x18002fb46  lea     r9, IID_IPXWizardTaskEventStub; struct _GUID *
0x18002fb4d  lea     r8, CLSID_CPXWizardTaskStub; struct _GUID *
0x18002fb54  mov     rdx, r15; struct IMultiObjectElevationFactory **
0x18002fb57  mov     rcx, r13; HWND
0x18002fb5a  call    ?CoCreateElevatedInstance@@YAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@AEBU_GUID@@2PEAPEAX@Z; CoCreateElevatedInstance(HWND__ *,IMultiObjectElevationFactory * *,_GUID const &,_GUID const &,void * *)
0x18002fb5f  jmp     short loc_18002FBBF
0x18002fb61  lea     rdi, WPP_GLOBAL_Control
0x18002fb68  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb6f  cmp     rcx, rdi
0x18002fb72  jz      short loc_18002FB93
0x18002fb74  test    byte ptr [rcx+1Ch], 8
0x18002fb78  jz      short loc_18002FB93
0x18002fb7a  mov     edx, 29h ; ')'
0x18002fb7f  mov     r9d, [r12]
0x18002fb83  lea     r8, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids
0x18002fb8a  mov     rcx, [rcx+10h]
0x18002fb8e  call    WPP_SF_d
0x18002fb93  mov     dword ptr [rbx+40h], 100h
0x18002fb9a  lea     rax, [rbx+48h]
0x18002fb9e  mov     [rsp+88h+ppv], rax; ppv
0x18002fba3  lea     r9, IID_IPXWizardTaskEventStub; riid
0x18002fbaa  xor     edx, edx; pUnkOuter
0x18002fbac  mov     r8d, 404h; dwClsContext
0x18002fbb2  lea     rcx, CLSID_CPXWizardTaskStub; rclsid
0x18002fbb9  call    cs:__imp_CoCreateInstance
0x18002fbbf  mov     esi, eax
0x18002fbc1  test    eax, eax
0x18002fbc3  jnz     short loc_18002FC1B
0x18002fbc5  mov     eax, [rsp+88h+arg_18]
0x18002fbcc  mov     [rbx+44h], eax
0x18002fbcf  mov     rcx, [rbx+48h]
0x18002fbd3  mov     rax, [rcx]
0x18002fbd6  mov     rdx, r12
0x18002fbd9  mov     rax, [rax+30h]
0x18002fbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbe2  mov     esi, eax
0x18002fbe4  test    eax, eax
0x18002fbe6  jz      short loc_18002FC42
0x18002fbe8  jmp     short loc_18002FC1B
0x18002fbea  lea     rdi, WPP_GLOBAL_Control
0x18002fbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbf8  cmp     rcx, rdi
0x18002fbfb  jz      short loc_18002FC1B
0x18002fbfd  test    byte ptr [rcx+1Ch], 4
0x18002fc01  jz      short loc_18002FC1B
0x18002fc03  mov     edx, 2Ah ; '*'
0x18002fc08  mov     r9d, eax
0x18002fc0b  lea     r8, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids
0x18002fc12  mov     rcx, [rcx+10h]
0x18002fc16  call    WPP_SF_d
0x18002fc1b  mov     rax, [rbx]
0x18002fc1e  mov     edx, 1
0x18002fc23  mov     rcx, rbx
0x18002fc26  mov     rax, [rax+88h]
0x18002fc2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc32  mov     qword ptr [r14], 0
0x18002fc39  jmp     short loc_18002FC42
0x18002fc3b  lea     rdi, WPP_GLOBAL_Control
0x18002fc42  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc49  cmp     rcx, rdi
0x18002fc4c  jz      short loc_18002FC6C
0x18002fc4e  test    byte ptr [rcx+1Ch], 10h
0x18002fc52  jz      short loc_18002FC6C
0x18002fc54  mov     edx, 2Ch ; ','
0x18002fc59  mov     r9d, esi
0x18002fc5c  lea     r8, WPP_7eca1bd1bc263f7bc55efbd7ed37d1b3_Traceguids
0x18002fc63  mov     rcx, [rcx+10h]
0x18002fc67  call    WPP_SF_d
0x18002fc6c  mov     eax, esi
0x18002fc6e  add     rsp, 50h
0x18002fc72  pop     r15
0x18002fc74  pop     r14
0x18002fc76  pop     r13
0x18002fc78  pop     r12
0x18002fc7a  pop     rdi
0x18002fc7b  pop     rsi
0x18002fc7c  pop     rbx
0x18002fc7d  retn
```
