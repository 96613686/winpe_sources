# CStgCreationStream::_NotifyObjectCreated(void)

- ea: `0x1800644cc`
- end: `0x180064746`
- name: `?_NotifyObjectCreated@CStgCreationStream@@IEAAJXZ`
- size: `634`
- prototype: `__int64 __fastcall(CStgCreationStream *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063480`

## callees

- `0x18000ef50`
- `0x1800285c8`
- `0x1800287d0`
- `0x18002ff5c`
- `0x1800644cc`
- `0x180078010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180064700`
- `ole32!CoTaskMemFree` at `0x18006470b`
- `ole32!CoTaskMemFree` at `0x180064716`
- `ole32!CoTaskMemFree` at `0x180064700`
- `ole32!CoTaskMemFree` at `0x18006470b`
- `ole32!CoTaskMemFree` at `0x180064716`
- `SHELL32!SHChangeNotify` at `0x1800646ce`
- `SHELL32!SHChangeNotify` at `0x1800646df`
- `SHELL32!SHChangeNotify` at `0x1800646ce`
- `SHELL32!SHChangeNotify` at `0x1800646df`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CStgCreationStream::_NotifyObjectCreated(CStgCreationStream *this)
{
  void *v2; // rbx
  int v3; // eax
  unsigned int v4; // edi
  PVOID *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-18h] BYREF
  struct IPortableDevice *v10[2]; // [rsp+38h] [rbp-10h] BYREF
  int v11; // [rsp+80h] [rbp+38h] BYREF
  LPCVOID dwItem1; // [rsp+88h] [rbp+40h] BYREF
  unsigned __int16 *v13; // [rsp+90h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+50h] BYREF

  v10[0] = 0;
  v9 = 0;
  v13 = 0;
  pv = 0;
  v2 = 0;
  dwItem1 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IPortableDevice **))(**((_QWORD **)this + 5) + 136LL))(
         *((_QWORD *)this + 5),
         *(_QWORD *)(*((_QWORD *)this + 5) + 64LL),
         v10);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_26;
    v6 = 47;
LABEL_5:
    WPP_SF_d(v5[2], v6, WPP_e110864b817937850ad9b0b0d0efdde1_Traceguids, (unsigned int)v3);
LABEL_16:
    v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
      WPP_SF_d(v5[2], 52, WPP_e110864b817937850ad9b0b0d0efdde1_Traceguids, v4);
    goto LABEL_32;
  }
  v3 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 4))(
         *((_QWORD *)this + 4),
         &GUID_88e04db3_1012_4d64_9996_f703a950d3f4,
         &v9);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_26;
    v6 = 48;
    goto LABEL_5;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v9 + 112LL))(v9, &v13);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_26;
    v6 = 49;
    goto LABEL_5;
  }
  if ( !v13 )
  {
    v4 = -2147418113;
    goto LABEL_16;
  }
  v3 = CContentFolder::_CreateIDList(*((CContentFolder **)this + 5), v10[0], v13, 0, (struct _ITEMIDLIST **)&pv, &v11);
  v4 = v3;
  if ( v3 < 0 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_26;
    v6 = 50;
    goto LABEL_5;
  }
  v7 = SHILCombine(*(_QWORD *)(*((_QWORD *)this + 5) + 64LL), pv, &dwItem1);
  v4 = v7;
  if ( v7 < 0 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        WPP_e110864b817937850ad9b0b0d0efdde1_Traceguids,
        (unsigned int)v7);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    v2 = (void *)dwItem1;
    goto LABEL_26;
  }
  v2 = (void *)dwItem1;
  if ( *((_QWORD *)this + 72) )
    SHChangeNotify(0x2000, 0, dwItem1, 0);
  SHChangeNotify(2, 0, v2, 0);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 160LL))(
    *((_QWORD *)this + 5),
    *(_QWORD *)(*((_QWORD *)this + 5) + 64LL));
LABEL_32:
  CoTaskMemFree(v2);
  CoTaskMemFree(pv);
  CoTaskMemFree(v13);
  v13 = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v10);
  return v4;
}

```

## disassembly

```asm
0x1800644cc  push    rbp
0x1800644ce  push    rbx
0x1800644cf  push    rsi
0x1800644d0  push    rdi
0x1800644d1  push    r12
0x1800644d3  push    r13
0x1800644d5  mov     rbp, rsp
0x1800644d8  sub     rsp, 48h
0x1800644dc  mov     rsi, rcx
0x1800644df  mov     [rbp+var_10], 0
0x1800644e7  mov     [rbp+var_18], 0
0x1800644ef  mov     [rbp+arg_10], 0
0x1800644f7  mov     [rbp+pv], 0
0x1800644ff  xor     ebx, ebx
0x180064501  mov     [rbp+dwItem1], rbx
0x180064505  mov     rcx, [rcx+28h]
0x180064509  mov     rax, [rcx]
0x18006450c  lea     r8, [rbp+var_10]
0x180064510  mov     rdx, [rcx+40h]
0x180064514  mov     rax, [rax+88h]
0x18006451b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064520  mov     edi, eax
0x180064522  lea     r12, WPP_GLOBAL_Control
0x180064529  lea     r13, WPP_e110864b817937850ad9b0b0d0efdde1_Traceguids
0x180064530  test    eax, eax
0x180064532  jns     short loc_180064565
0x180064534  mov     rcx, cs:WPP_GLOBAL_Control
0x18006453b  cmp     rcx, r12
0x18006453e  jz      loc_1800646FD
0x180064544  test    byte ptr [rcx+1Ch], 2
0x180064548  jz      loc_180064692
0x18006454e  lea     edx, [rbx+2Fh]
0x180064551  mov     r9d, eax
0x180064554  mov     r8, r13
0x180064557  mov     rcx, [rcx+10h]
0x18006455b  call    WPP_SF_d
0x180064560  jmp     loc_1800645F2
0x180064565  mov     rcx, [rsi+20h]
0x180064569  mov     rax, [rcx]
0x18006456c  lea     r8, [rbp+var_18]
0x180064570  lea     rdx, _GUID_88e04db3_1012_4d64_9996_f703a950d3f4
0x180064577  mov     rax, [rax]
0x18006457a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006457f  mov     edi, eax
0x180064581  test    eax, eax
0x180064583  jns     short loc_1800645A6
0x180064585  mov     rcx, cs:WPP_GLOBAL_Control
0x18006458c  cmp     rcx, r12
0x18006458f  jz      loc_1800646FD
0x180064595  test    byte ptr [rcx+1Ch], 2
0x180064599  jz      loc_180064692
0x18006459f  mov     edx, 30h ; '0'
0x1800645a4  jmp     short loc_180064551
0x1800645a6  mov     rcx, [rbp+var_18]
0x1800645aa  mov     rax, [rcx]
0x1800645ad  lea     rdx, [rbp+arg_10]
0x1800645b1  mov     rax, [rax+70h]
0x1800645b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800645ba  mov     edi, eax
0x1800645bc  test    eax, eax
0x1800645be  jns     short loc_1800645E4
0x1800645c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800645c7  cmp     rcx, r12
0x1800645ca  jz      loc_1800646FD
0x1800645d0  test    byte ptr [rcx+1Ch], 2
0x1800645d4  jz      loc_180064692
0x1800645da  mov     edx, 31h ; '1'
0x1800645df  jmp     loc_180064551
0x1800645e4  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x1800645e8  test    r8, r8
0x1800645eb  jnz     short loc_1800645FE
0x1800645ed  mov     edi, 8000FFFFh
0x1800645f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800645f9  jmp     loc_180064692
0x1800645fe  lea     rax, [rbp+arg_0]
0x180064602  mov     [rsp+48h+var_20], rax; int *
0x180064607  lea     rax, [rbp+pv]
0x18006460b  mov     [rsp+48h+var_28], rax; struct _ITEMIDLIST **
0x180064610  xor     r9d, r9d; int
0x180064613  mov     rdx, [rbp+var_10]; struct IPortableDevice *
0x180064617  mov     rcx, [rsi+28h]; this
0x18006461b  call    ?_CreateIDList@CContentFolder@@QEAAJPEAUIPortableDevice@@PEBGHPEAPEFAU_ITEMIDLIST@@PEAH@Z; CContentFolder::_CreateIDList(IPortableDevice *,ushort const *,int,_ITEMIDLIST * *,int *)
0x180064620  mov     edi, eax
0x180064622  test    eax, eax
0x180064624  jns     short loc_180064646
0x180064626  mov     rcx, cs:WPP_GLOBAL_Control
0x18006462d  cmp     rcx, r12
0x180064630  jz      loc_1800646FD
0x180064636  test    byte ptr [rcx+1Ch], 2
0x18006463a  jz      short loc_180064692
0x18006463c  mov     edx, 32h ; '2'
0x180064641  jmp     loc_180064551
0x180064646  mov     rcx, [rsi+28h]
0x18006464a  lea     r8, [rbp+dwItem1]
0x18006464e  mov     rdx, [rbp+pv]
0x180064652  mov     rcx, [rcx+40h]
0x180064656  call    SHILCombine
0x18006465b  mov     edi, eax
0x18006465d  test    eax, eax
0x18006465f  jns     short loc_1800646B3
0x180064661  mov     rcx, cs:WPP_GLOBAL_Control
0x180064668  cmp     rcx, r12
0x18006466b  jz      short loc_18006468E
0x18006466d  test    byte ptr [rcx+1Ch], 2
0x180064671  jz      short loc_18006468E
0x180064673  mov     edx, 33h ; '3'
0x180064678  mov     r9d, eax
0x18006467b  mov     r8, r13
0x18006467e  mov     rcx, [rcx+10h]
0x180064682  call    WPP_SF_d
0x180064687  mov     rcx, cs:WPP_GLOBAL_Control
0x18006468e  mov     rbx, [rbp+dwItem1]
0x180064692  cmp     rcx, r12
0x180064695  jz      short loc_1800646FD
0x180064697  test    byte ptr [rcx+1Ch], 2
0x18006469b  jz      short loc_1800646FD
0x18006469d  mov     edx, 34h ; '4'
0x1800646a2  mov     r9d, edi
0x1800646a5  mov     r8, r13
0x1800646a8  mov     rcx, [rcx+10h]
0x1800646ac  call    WPP_SF_d
0x1800646b1  jmp     short loc_1800646FD
0x1800646b3  mov     rbx, [rbp+dwItem1]
0x1800646b7  cmp     qword ptr [rsi+240h], 0
0x1800646bf  jz      short loc_1800646D4
0x1800646c1  xor     r9d, r9d; dwItem2
0x1800646c4  mov     r8, rbx; dwItem1
0x1800646c7  xor     edx, edx; uFlags
0x1800646c9  mov     ecx, 2000h; wEventId
0x1800646ce  call    cs:__imp_SHChangeNotify
0x1800646d4  xor     r9d, r9d; dwItem2
0x1800646d7  mov     r8, rbx; dwItem1
0x1800646da  xor     edx, edx; uFlags
0x1800646dc  lea     ecx, [rdx+2]; wEventId
0x1800646df  call    cs:__imp_SHChangeNotify
0x1800646e5  mov     rcx, [rsi+28h]
0x1800646e9  mov     rax, [rcx]
0x1800646ec  mov     rdx, [rcx+40h]
0x1800646f0  mov     rax, [rax+0A0h]
0x1800646f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800646fc  nop
0x1800646fd  mov     rcx, rbx; pv
0x180064700  call    cs:__imp_CoTaskMemFree
0x180064706  nop
0x180064707  mov     rcx, [rbp+pv]; pv
0x18006470b  call    cs:__imp_CoTaskMemFree
0x180064711  nop
0x180064712  mov     rcx, [rbp+arg_10]; pv
0x180064716  call    cs:__imp_CoTaskMemFree
0x18006471c  mov     [rbp+arg_10], 0
0x180064724  lea     rcx, [rbp+var_18]
0x180064728  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006472d  nop
0x18006472e  lea     rcx, [rbp+var_10]
0x180064732  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180064737  mov     eax, edi
0x180064739  add     rsp, 48h
0x18006473d  pop     r13
0x18006473f  pop     r12
0x180064741  pop     rdi
0x180064742  pop     rsi
0x180064743  pop     rbx
0x180064744  pop     rbp
0x180064745  retn
```
