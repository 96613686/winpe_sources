# DBTable::GetRowCount(ulong *)

- ea: `0x180059480`
- end: `0x1800596d8`
- name: `?GetRowCount@DBTable@@UEAAJPEAK@Z`
- size: `600`
- prototype: `__int64 __fastcall(DBTable *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x180050150`
- `0x180059480`
- `0x18006f180`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005949e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005949e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800595f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800595f3`

## string_xrefs

- `0x18005962d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180059645`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180059699`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18005961b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180059673`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`

## pseudocode

```c
__int64 __fastcall DBTable::GetRowCount(DBTable *this, unsigned int *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // r12d
  unsigned int v6; // r13d
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // r9
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int128 v23; // [rsp+30h] [rbp-28h] BYREF
  __int64 v24; // [rsp+40h] [rbp-18h] BYREF
  __int64 v25; // [rsp+48h] [rbp-10h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = *((_QWORD *)this + 16);
  v5 = *((_DWORD *)this + 31);
  v6 = *((_DWORD *)this + 30);
  v24 = 0;
  v25 = 0;
  v23 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 160LL))(v4, &v24);
  v8 = v7;
  if ( v7 < 0 )
  {
    v21 = 834;
    v22 = (unsigned int)v7;
    goto LABEL_29;
  }
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 32LL))(v24);
  if ( g_breakOnJetError == -1912 )
    Log_AssertionEvent(
      v9,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
      25);
  if ( v8 != -2134374536 )
  {
    if ( (v8 & 0x80000000) == 0 )
    {
      HIDWORD(v25) = 1;
      goto LABEL_7;
    }
    v21 = 838;
    v22 = v8;
LABEL_29:
    Log_UnistoreHREvent_0(
      v22,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v21);
    v18 = 412;
    goto LABEL_25;
  }
LABEL_7:
  v10 = v24;
  v11 = *((_QWORD *)&v23 + 1);
  LODWORD(v25) = 1;
  if ( *((_QWORD *)&v23 + 1) == v24 )
  {
    v10 = *((_QWORD *)&v23 + 1);
  }
  else
  {
    if ( v24 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      v11 = *((_QWORD *)&v23 + 1);
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = v10;
    *((_QWORD *)&v23 + 1) = v10;
  }
  if ( !v10 )
  {
    v8 = -2147418113;
    v15 = 764;
    v16 = 2147549183LL;
    v17 = 0;
LABEL_24:
    Log_UnistoreHREvent_0(
      v16,
      v17,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v15);
    v18 = 416;
LABEL_25:
    Log_UnistoreHREvent_0(
      v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v18);
    v19 = 6256;
    v20 = v8;
LABEL_26:
    Log_UnistoreHREvent_0(
      v20,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v19);
    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v23);
    goto LABEL_22;
  }
  if ( (_QWORD)v23 )
  {
    auto_TableHandle::Close((auto_TableHandle *)&v23);
    v11 = *((_QWORD *)&v23 + 1);
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v11 + 64LL))(v11, v6, v5, &v23);
  v8 = v12;
  if ( v12 < 0 )
  {
    v15 = 771;
    v17 = 1;
    v16 = (unsigned int)v12;
    goto LABEL_24;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 14) + 88LL))(
          *((_QWORD *)this + 14),
          v23,
          a2);
  v8 = v13;
  if ( v13 < 0 )
  {
    v19 = 6258;
    v20 = (unsigned int)v13;
    goto LABEL_26;
  }
  if ( *((_QWORD *)&v23 + 1) && (_QWORD)v23 )
  {
    (*(void (**)(void))(**((_QWORD **)&v23 + 1) + 80LL))();
    *(_QWORD *)&v23 = 0;
  }
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((char *)&v23 + 8);
  v8 = 0;
LABEL_22:
  auto_DBSession::~auto_DBSession((auto_DBSession *)&v24);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v8;
}

```

## disassembly

```asm
0x180059480  push    rbp
0x180059482  push    rbx
0x180059483  push    rsi
0x180059484  push    rdi
0x180059485  push    r12
0x180059487  push    r13
0x180059489  push    r14
0x18005948b  push    r15
0x18005948d  mov     rbp, rsp
0x180059490  sub     rsp, 58h
0x180059494  mov     rsi, rcx
0x180059497  mov     r15, rdx
0x18005949a  add     rcx, 10h; lpCriticalSection
0x18005949e  call    cs:__imp_EnterCriticalSection
0x1800594a4  mov     rcx, [rsi+80h]
0x1800594ab  lea     rdx, [rbp+var_18]
0x1800594af  mov     r12d, [rsi+7Ch]
0x1800594b3  xor     edi, edi
0x1800594b5  mov     r13d, [rsi+78h]
0x1800594b9  xorps   xmm0, xmm0
0x1800594bc  mov     [rbp+var_18], rdi
0x1800594c0  mov     [rbp+var_10], rdi
0x1800594c4  movdqu  [rbp+var_28], xmm0
0x1800594c9  mov     rax, [rcx]
0x1800594cc  mov     rax, [rax+0A0h]
0x1800594d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594d8  mov     ebx, eax
0x1800594da  test    eax, eax
0x1800594dc  js      loc_180059666
0x1800594e2  mov     rcx, [rbp+var_18]
0x1800594e6  mov     rax, [rcx]
0x1800594e9  mov     rax, [rax+20h]
0x1800594ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800594f2  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFF888h; long g_breakOnJetError
0x1800594fc  mov     ebx, eax
0x1800594fe  jz      loc_180059693
0x180059504  mov     edi, 1
0x180059509  cmp     ebx, 80C80778h
0x18005950f  jz      short loc_18005951C
0x180059511  test    ebx, ebx
0x180059513  js      loc_180059689
0x180059519  mov     dword ptr [rbp+var_10+4], edi
0x18005951c  mov     rbx, [rbp+var_18]
0x180059520  mov     rcx, qword ptr [rbp+var_28+8]
0x180059524  mov     dword ptr [rbp+var_10], edi
0x180059527  cmp     rcx, rbx
0x18005952a  jz      loc_18005965E
0x180059530  test    rbx, rbx
0x180059533  jz      short loc_180059548
0x180059535  mov     rax, [rbx]
0x180059538  mov     rcx, rbx
0x18005953b  mov     rax, [rax+8]
0x18005953f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059544  mov     rcx, qword ptr [rbp+var_28+8]
0x180059548  test    rcx, rcx
0x18005954b  jz      short loc_180059559
0x18005954d  mov     rax, [rcx]
0x180059550  mov     rax, [rax+10h]
0x180059554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059559  mov     rcx, rbx
0x18005955c  mov     qword ptr [rbp+var_28+8], rbx
0x180059560  test    rbx, rbx
0x180059563  jz      loc_18005960C
0x180059569  cmp     qword ptr [rbp+var_28], 0
0x18005956e  jnz     loc_1800596AA
0x180059574  mov     rax, [rcx]
0x180059577  lea     r9, [rbp+var_28]
0x18005957b  mov     r8d, r12d
0x18005957e  mov     edx, r13d
0x180059581  mov     rax, [rax+40h]
0x180059585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005958a  mov     ebx, eax
0x18005958c  test    eax, eax
0x18005958e  js      loc_1800596BC
0x180059594  mov     rcx, [rsi+70h]
0x180059598  mov     r8, r15
0x18005959b  mov     rdx, qword ptr [rbp+var_28]
0x18005959f  mov     rax, [rcx]
0x1800595a2  mov     rax, [rax+58h]
0x1800595a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595ab  mov     ebx, eax
0x1800595ad  test    eax, eax
0x1800595af  js      loc_1800596CB
0x1800595b5  mov     rcx, qword ptr [rbp+var_28+8]
0x1800595b9  test    rcx, rcx
0x1800595bc  jz      short loc_1800595DB
0x1800595be  mov     rdx, qword ptr [rbp+var_28]
0x1800595c2  test    rdx, rdx
0x1800595c5  jz      short loc_1800595DB
0x1800595c7  mov     rax, [rcx]
0x1800595ca  mov     rax, [rax+50h]
0x1800595ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595d3  mov     qword ptr [rbp+var_28], 0
0x1800595db  lea     rcx, [rbp+var_28+8]; void *
0x1800595df  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x1800595e4  xor     ebx, ebx
0x1800595e6  lea     rcx, [rbp+var_18]; this
0x1800595ea  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800595ef  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800595f3  call    cs:__imp_LeaveCriticalSection
0x1800595f9  mov     eax, ebx
0x1800595fb  add     rsp, 58h
0x1800595ff  pop     r15
0x180059601  pop     r14
0x180059603  pop     r13
0x180059605  pop     r12
0x180059607  pop     rdi
0x180059608  pop     rsi
0x180059609  pop     rbx
0x18005960a  pop     rbp
0x18005960b  retn
0x18005960c  mov     ebx, 8000FFFFh
0x180059611  mov     r9d, 2FCh
0x180059617  mov     ecx, ebx
0x180059619  xor     edx, edx
0x18005961b  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180059622  call    Log_UnistoreHREvent_0
0x180059627  mov     r9d, 1A0h
0x18005962d  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180059634  mov     edx, edi
0x180059636  mov     ecx, ebx
0x180059638  call    Log_UnistoreHREvent_0
0x18005963d  mov     r9d, 1870h
0x180059643  mov     ecx, ebx
0x180059645  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18005964c  mov     edx, edi
0x18005964e  call    Log_UnistoreHREvent_0
0x180059653  lea     rcx, [rbp+var_28]; this
0x180059657  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x18005965c  jmp     short loc_1800595E6
0x18005965e  mov     rbx, rcx
0x180059661  jmp     loc_180059560
0x180059666  mov     r9d, 342h
0x18005966c  mov     edi, 1
0x180059671  mov     ecx, eax
0x180059673  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18005967a  mov     edx, edi
0x18005967c  call    Log_UnistoreHREvent_0
0x180059681  mov     r9d, 19Ch
0x180059687  jmp     short loc_18005962D
0x180059689  mov     r9d, 346h
0x18005968f  mov     ecx, ebx
0x180059691  jmp     short loc_180059673
0x180059693  mov     r8d, 19h
0x180059699  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800596a0  call    Log_AssertionEvent
0x1800596a5  jmp     loc_180059504
0x1800596aa  lea     rcx, [rbp+var_28]; this
0x1800596ae  call    ?Close@auto_TableHandle@@QEAAXXZ; auto_TableHandle::Close(void)
0x1800596b3  mov     rcx, qword ptr [rbp+var_28+8]
0x1800596b7  jmp     loc_180059574
0x1800596bc  mov     r9d, 303h
0x1800596c2  mov     edx, edi
0x1800596c4  mov     ecx, eax
0x1800596c6  jmp     loc_18005961B
0x1800596cb  mov     r9d, 1872h
0x1800596d1  mov     ecx, eax
0x1800596d3  jmp     loc_180059645
```
