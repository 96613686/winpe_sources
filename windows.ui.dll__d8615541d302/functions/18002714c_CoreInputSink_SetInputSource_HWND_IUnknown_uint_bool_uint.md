# CoreInputSink::SetInputSource(HWND__ *,IUnknown *,uint,bool,uint)

- ea: `0x18002714c`
- end: `0x1800274d3`
- name: `?SetInputSource@CoreInputSink@@QEAAJPEAUHWND__@@PEAUIUnknown@@I_NI@Z`
- size: `903`
- prototype: `__int64 __fastcall(CoreInputSink *__hidden this, HWND, struct IUnknown *, unsigned int, bool, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180028ad0`
- `0x180070b00`
- `0x1800757c0`

## callees

- `0x1800038e0`
- `0x18002714c`
- `0x1800274f4`
- `0x1800275c0`
- `0x1800284e0`
- `0x180028614`
- `0x180056d3c`
- `0x180071d6c`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800272ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800272ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800271b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800271b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002733a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800273c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002747f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800274a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002733a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800273c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002747f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800274a0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002737b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002737b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CoreInputSink::SetInputSource(
        CoreInputSink *this,
        HWND a2,
        struct IUnknown *a3,
        int a4,
        char a5,
        unsigned int a6)
{
  PVOID *v10; // rax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v12; // eax
  struct Windows::UI::Composition::IVisual *v13; // r8
  int v14; // ebx
  struct _InputSinkEntry *v15; // r14
  struct Windows::UI::Composition::IVisual *v16; // rcx
  struct IDCompositionVisualPartner *v17; // rcx
  DWORD v19; // eax
  __int64 v20; // rdx
  HRESULT (__stdcall *v21)(IUnknown *, const IID *const, void **); // rbx
  DWORD CurrentThreadId; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  struct Windows::UI::Composition::IVisual *v25; // [rsp+40h] [rbp-30h] BYREF
  struct IDCompositionVisualPartner *v26; // [rsp+48h] [rbp-28h] BYREF
  struct _InputSinkEntry *v27[4]; // [rsp+50h] [rbp-20h] BYREF

  if ( (a4 & 0xFFFFFFF0) != 0 )
  {
    v14 = -2147024809;
LABEL_26:
    RoOriginateError((unsigned int)v14, 0);
    return (unsigned int)v14;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_qDqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
      this,
      CurrentThreadId,
      a2,
      a3);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    v14 = 0;
    CoreInputSink::Cleanup(this);
    return (unsigned int)v14;
  }
  if ( *(_QWORD *)this )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    {
      v24 = GetCurrentThreadId();
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids, this, v24);
    }
    v14 = -2147418113;
    goto LABEL_26;
  }
  AcquireSRWLockExclusive(&CoreInputSink::_srwLock);
  v27[1] = (struct _InputSinkEntry *)&CoreInputSink::_srwLock;
  v27[2] = (struct _InputSinkEntry *)a3;
  ((void (__fastcall *)(struct IUnknown *))a3->lpVtbl->AddRef)(a3);
  v26 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v26);
  v12 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IDCompositionVisualPartner **))QueryInterface)(
          a3,
          &GUID_2c4eef28_1bc0_4736_b7dd_b62692f9bd67,
          &v26);
  v13 = 0;
  v25 = 0;
  if ( v12 < 0 )
  {
    v21 = a3->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v25);
    v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct Windows::UI::Composition::IVisual **))v21)(
            a3,
            &GUID_117e202d_a859_4c89_873b_c2aa566788e3,
            &v25);
    if ( v14 < 0 )
      goto LABEL_13;
    v13 = v25;
  }
  v27[0] = 0;
  if ( CoreInputSink::FindInputSinkEntry(this, v26, v13, v27) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v23 = GetCurrentThreadId();
      v15 = v27[0];
      WPP_SF_qDqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
        this,
        v23,
        a2,
        v27[0]);
      goto LABEL_10;
    }
  }
  else
  {
    v14 = CoreInputSink::AddInputSinkEntry(this, v26, v25, v27);
    if ( v14 < 0 )
      goto LABEL_13;
  }
  v15 = v27[0];
LABEL_10:
  v14 = CoreInputSink::UpdateAndRegisterInputSink(this, a4, a2, a5, a6, v15);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_13;
    }
    v19 = GetCurrentThreadId();
    v20 = 15;
  }
  else
  {
    *(_QWORD *)this = v15;
    *((_DWORD *)this + 2) = a4;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_13;
    }
    v19 = GetCurrentThreadId();
    v20 = 14;
  }
  WPP_SF_qDqq(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v20,
    &WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
    this,
    v19,
    a2,
    v15);
LABEL_13:
  v16 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(struct Windows::UI::Composition::IVisual *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(struct IDCompositionVisualPartner *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  ((void (__fastcall *)(struct IUnknown *))a3->lpVtbl->Release)(a3);
  ReleaseSRWLockExclusive(&CoreInputSink::_srwLock);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002714c  push    rbp
0x18002714e  push    rbx
0x18002714f  push    rsi
0x180027150  push    rdi
0x180027151  push    r12
0x180027153  push    r14
0x180027155  push    r15
0x180027157  mov     rbp, rsp
0x18002715a  sub     rsp, 70h
0x18002715e  mov     r12d, r9d
0x180027161  mov     rsi, r8
0x180027164  mov     r15, rdx
0x180027167  mov     rdi, rcx
0x18002716a  test    r9d, 0FFFFFFF0h
0x180027171  jnz     loc_180027372
0x180027177  lea     rcx, WPP_GLOBAL_Control
0x18002717e  mov     r14b, 40h ; '@'
0x180027181  mov     rax, cs:WPP_GLOBAL_Control
0x180027188  cmp     rax, rcx
0x18002718b  jz      short loc_180027197
0x18002718d  test    [rax+1Ch], r14b
0x180027191  jnz     loc_1800273BE
0x180027197  test    rsi, rsi
0x18002719a  jz      loc_180027303
0x1800271a0  cmp     qword ptr [rdi], 0
0x1800271a4  jnz     loc_18002748F
0x1800271aa  lea     rbx, ?_srwLock@CoreInputSink@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CoreInputSink::_srwLock
0x1800271b1  mov     rcx, rbx; SRWLock
0x1800271b4  call    cs:__imp_AcquireSRWLockExclusive
0x1800271ba  mov     [rbp+var_18], rbx
0x1800271be  mov     [rbp+var_10], rsi
0x1800271c2  mov     rax, [rsi]
0x1800271c5  mov     rcx, rsi
0x1800271c8  mov     rax, [rax+8]
0x1800271cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271d1  nop
0x1800271d2  mov     [rbp+var_28], 0
0x1800271da  mov     rax, [rsi]
0x1800271dd  mov     rbx, [rax]
0x1800271e0  lea     rcx, [rbp+var_28]
0x1800271e4  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800271e9  lea     r8, [rbp+var_28]
0x1800271ed  lea     rdx, _GUID_2c4eef28_1bc0_4736_b7dd_b62692f9bd67
0x1800271f4  mov     rcx, rsi
0x1800271f7  mov     rax, rbx
0x1800271fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271ff  nop
0x180027200  xor     r8d, r8d; struct Windows::UI::Composition::IVisual *
0x180027203  mov     [rbp+var_30], r8
0x180027207  test    eax, eax
0x180027209  js      loc_180027386
0x18002720f  mov     [rbp+var_20], 0
0x180027217  lea     r9, [rbp+var_20]; struct _InputSinkEntry **
0x18002721b  mov     rdx, [rbp+var_28]; struct IDCompositionVisualPartner *
0x18002721f  mov     rcx, rdi; this
0x180027222  call    ?FindInputSinkEntry@CoreInputSink@@AEAA_NPEAUIDCompositionVisualPartner@@PEAUIVisual@Composition@UI@Windows@@PEAPEAU_InputSinkEntry@@@Z; CoreInputSink::FindInputSinkEntry(IDCompositionVisualPartner *,Windows::UI::Composition::IVisual *,_InputSinkEntry * *)
0x180027227  test    al, al
0x180027229  jnz     loc_18002740E
0x18002722f  lea     r9, [rbp+var_20]; struct _InputSinkEntry **
0x180027233  mov     r8, [rbp+var_30]; struct Windows::UI::Composition::IVisual *
0x180027237  mov     rdx, [rbp+var_28]; struct IDCompositionVisualPartner *
0x18002723b  mov     rcx, rdi; this
0x18002723e  call    ?AddInputSinkEntry@CoreInputSink@@AEAAJPEAUIDCompositionVisualPartner@@PEAUIVisual@Composition@UI@Windows@@PEAPEAU_InputSinkEntry@@@Z; CoreInputSink::AddInputSinkEntry(IDCompositionVisualPartner *,Windows::UI::Composition::IVisual *,_InputSinkEntry * *)
0x180027243  mov     ebx, eax
0x180027245  test    eax, eax
0x180027247  js      short loc_180027299
0x180027249  mov     r14, [rbp+var_20]
0x18002724d  mov     [rsp+70h+var_48], r14; struct _InputSinkEntry *
0x180027252  mov     eax, [rbp+arg_28]
0x180027255  mov     [rsp+70h+var_50], eax; unsigned int
0x180027259  mov     r9b, [rbp+arg_20]; bool
0x18002725d  mov     r8, r15; HWND
0x180027260  mov     edx, r12d; unsigned int
0x180027263  mov     rcx, rdi; this
0x180027266  call    ?UpdateAndRegisterInputSink@CoreInputSink@@AEAAJIPEAUHWND__@@_NIPEAU_InputSinkEntry@@@Z; CoreInputSink::UpdateAndRegisterInputSink(uint,HWND__ *,bool,uint,_InputSinkEntry *)
0x18002726b  mov     ebx, eax
0x18002726d  test    eax, eax
0x18002726f  js      loc_18002730F
0x180027275  mov     [rdi], r14
0x180027278  mov     [rdi+8], r12d
0x18002727c  mov     rax, cs:WPP_GLOBAL_Control
0x180027283  lea     rcx, WPP_GLOBAL_Control
0x18002728a  cmp     rax, rcx
0x18002728d  jz      short loc_180027299
0x18002728f  test    byte ptr [rax+1Ch], 40h
0x180027293  jnz     loc_180027475
0x180027299  mov     rcx, [rbp+var_30]
0x18002729d  test    rcx, rcx
0x1800272a0  jz      short loc_1800272B7
0x1800272a2  mov     [rbp+var_30], 0
0x1800272aa  mov     rax, [rcx]
0x1800272ad  mov     rax, [rax+10h]
0x1800272b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272b6  nop
0x1800272b7  mov     rcx, [rbp+var_28]
0x1800272bb  test    rcx, rcx
0x1800272be  jz      short loc_1800272D5
0x1800272c0  mov     [rbp+var_28], 0
0x1800272c8  mov     rax, [rcx]
0x1800272cb  mov     rax, [rax+10h]
0x1800272cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272d4  nop
0x1800272d5  mov     rax, [rsi]
0x1800272d8  mov     rcx, rsi
0x1800272db  mov     rax, [rax+10h]
0x1800272df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272e4  nop
0x1800272e5  lea     rcx, ?_srwLock@CoreInputSink@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x1800272ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800272f2  mov     eax, ebx
0x1800272f4  add     rsp, 70h
0x1800272f8  pop     r15
0x1800272fa  pop     r14
0x1800272fc  pop     r12
0x1800272fe  pop     rdi
0x1800272ff  pop     rsi
0x180027300  pop     rbx
0x180027301  pop     rbp
0x180027302  retn
0x180027303  xor     ebx, ebx
0x180027305  mov     rcx, rdi; this
0x180027308  call    ?Cleanup@CoreInputSink@@QEAAXXZ; CoreInputSink::Cleanup(void)
0x18002730d  jmp     short loc_1800272F2
0x18002730f  mov     rax, cs:WPP_GLOBAL_Control
0x180027316  lea     rcx, WPP_GLOBAL_Control
0x18002731d  cmp     rax, rcx
0x180027320  jz      loc_180027299
0x180027326  test    byte ptr [rax+1Ch], 40h
0x18002732a  jz      loc_180027299
0x180027330  cmp     byte ptr [rax+19h], 4
0x180027334  jb      loc_180027299
0x18002733a  call    cs:__imp_GetCurrentThreadId
0x180027340  mov     edx, 0Fh
0x180027345  mov     [rsp+70h+var_40], r14
0x18002734a  mov     [rsp+70h+var_48], r15
0x18002734f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027356  mov     [rsp+70h+var_50], eax
0x18002735a  mov     r9, rdi
0x18002735d  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x180027364  mov     rcx, [rcx+10h]
0x180027368  call    WPP_SF_qDqq
0x18002736d  jmp     loc_180027299
0x180027372  mov     ebx, 80070057h
0x180027377  xor     edx, edx
0x180027379  mov     ecx, ebx
0x18002737b  call    cs:__imp_RoOriginateError
0x180027381  jmp     loc_1800272F2
0x180027386  mov     rax, [rsi]
0x180027389  mov     rbx, [rax]
0x18002738c  lea     rcx, [rbp+var_30]
0x180027390  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180027395  lea     r8, [rbp+var_30]
0x180027399  lea     rdx, _GUID_117e202d_a859_4c89_873b_c2aa566788e3
0x1800273a0  mov     rcx, rsi
0x1800273a3  mov     rax, rbx
0x1800273a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273ab  mov     ebx, eax
0x1800273ad  test    eax, eax
0x1800273af  js      loc_180027299
0x1800273b5  mov     r8, [rbp+var_30]
0x1800273b9  jmp     loc_18002720F
0x1800273be  cmp     byte ptr [rax+19h], 4
0x1800273c2  jb      loc_180027197
0x1800273c8  call    cs:__imp_GetCurrentThreadId
0x1800273ce  mov     edx, 0Ch
0x1800273d3  mov     [rsp+70h+var_40], rsi
0x1800273d8  mov     [rsp+70h+var_48], r15
0x1800273dd  mov     [rsp+70h+var_50], eax
0x1800273e1  mov     r9, rdi
0x1800273e4  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x1800273eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273f2  mov     rcx, [rcx+10h]
0x1800273f6  call    WPP_SF_qDqq
0x1800273fb  mov     rax, cs:WPP_GLOBAL_Control
0x180027402  lea     rcx, WPP_GLOBAL_Control
0x180027409  jmp     loc_180027197
0x18002740e  mov     rax, cs:WPP_GLOBAL_Control
0x180027415  lea     rcx, WPP_GLOBAL_Control
0x18002741c  cmp     rax, rcx
0x18002741f  jz      loc_180027249
0x180027425  test    [rax+1Ch], r14b
0x180027429  jz      loc_180027249
0x18002742f  cmp     byte ptr [rax+19h], 4
0x180027433  jb      loc_180027249
0x180027439  call    cs:__imp_GetCurrentThreadId
0x18002743f  mov     edx, 0Dh
0x180027444  mov     r14, [rbp+var_20]
0x180027448  mov     [rsp+70h+var_40], r14
0x18002744d  mov     [rsp+70h+var_48], r15
0x180027452  mov     [rsp+70h+var_50], eax
0x180027456  mov     r9, rdi
0x180027459  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x180027460  mov     rcx, cs:WPP_GLOBAL_Control
0x180027467  mov     rcx, [rcx+10h]
0x18002746b  call    WPP_SF_qDqq
0x180027470  jmp     loc_18002724D
0x180027475  cmp     byte ptr [rax+19h], 4
0x180027479  jb      loc_180027299
0x18002747f  call    cs:__imp_GetCurrentThreadId
0x180027485  mov     edx, 0Eh
0x18002748a  jmp     loc_180027345
0x18002748f  cmp     rax, rcx
0x180027492  jz      short loc_1800274C9
0x180027494  test    [rax+1Ch], r14b
0x180027498  jz      short loc_1800274C9
0x18002749a  cmp     byte ptr [rax+19h], 2
0x18002749e  jb      short loc_1800274C9
0x1800274a0  call    cs:__imp_GetCurrentThreadId
0x1800274a6  mov     edx, 10h
0x1800274ab  mov     [rsp+70h+var_50], eax
0x1800274af  mov     r9, rdi
0x1800274b2  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x1800274b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274c0  mov     rcx, [rcx+10h]
0x1800274c4  call    WPP_SF_qD
0x1800274c9  mov     ebx, 8000FFFFh
0x1800274ce  jmp     loc_180027377
```
