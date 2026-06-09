# DBTable::MoveToIndex(ulong)

- ea: `0x180019ea0`
- end: `0x18001a16b`
- name: `?MoveToIndex@DBTable@@UEAAJK@Z`
- size: `715`
- prototype: `__int64 __fastcall(DBTable *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x180019ea0`
- `0x18001a180`
- `0x180050150`
- `0x18006f180`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019ebe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019ebe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a036`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a036`

## string_xrefs

- `0x180019fee`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001a070`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001a088`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001a12c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18001a05e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18001a103`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`

## pseudocode

```c
__int64 __fastcall DBTable::MoveToIndex(DBTable *this, unsigned int a2)
{
  __int64 v4; // rcx
  unsigned int v5; // r14d
  unsigned int v6; // r15d
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  struct UnifiedStoreCursorLocation *v14; // rdx
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rcx
  __int128 v25; // [rsp+30h] [rbp-28h] BYREF
  __int64 v26; // [rsp+40h] [rbp-18h] BYREF
  __int64 v27; // [rsp+48h] [rbp-10h]

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = *((_QWORD *)this + 16);
  v5 = *((_DWORD *)this + 31);
  v6 = *((_DWORD *)this + 30);
  v26 = 0;
  v27 = 0;
  v25 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 160LL))(v4, &v26);
  v8 = v7;
  if ( v7 < 0 )
  {
    v23 = 834;
    v24 = (unsigned int)v7;
    goto LABEL_37;
  }
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 32LL))(v26);
  if ( g_breakOnJetError == -1912 )
    Log_AssertionEvent(
      v9,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
      25);
  if ( v8 != -2134374536 )
  {
    if ( (v8 & 0x80000000) == 0 )
    {
      HIDWORD(v27) = 1;
      goto LABEL_7;
    }
    v23 = 838;
    v24 = v8;
LABEL_37:
    Log_UnistoreHREvent_0(
      v24,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v23);
    v19 = 412;
    goto LABEL_28;
  }
LABEL_7:
  v10 = v26;
  v11 = *((_QWORD *)&v25 + 1);
  LODWORD(v27) = 1;
  if ( *((_QWORD *)&v25 + 1) == v26 )
  {
    v10 = *((_QWORD *)&v25 + 1);
  }
  else
  {
    if ( v26 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
      v11 = *((_QWORD *)&v25 + 1);
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = v10;
    *((_QWORD *)&v25 + 1) = v10;
  }
  if ( !v10 )
  {
    v8 = -2147418113;
    v16 = 764;
    v17 = 2147549183LL;
    v18 = 0;
LABEL_27:
    Log_UnistoreHREvent_0(
      v17,
      v18,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v16);
    v19 = 416;
LABEL_28:
    Log_UnistoreHREvent_0(
      v8,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v19);
    v20 = 6312;
    v21 = v8;
LABEL_29:
    Log_UnistoreHREvent_0(
      v21,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v20);
    auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v25);
    goto LABEL_25;
  }
  if ( (_QWORD)v25 )
  {
    auto_TableHandle::Close((auto_TableHandle *)&v25);
    v11 = *((_QWORD *)&v25 + 1);
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v11 + 64LL))(v11, v6, v5, &v25);
  v8 = v12;
  if ( v12 < 0 )
  {
    v16 = 771;
    v18 = 1;
    v17 = (unsigned int)v12;
    goto LABEL_27;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 14) + 96LL))(
          *((_QWORD *)this + 14),
          v25,
          a2);
  v14 = (DBTable *)((char *)this + 56);
  v8 = v13;
  if ( v13 == -2147024871 )
  {
    *(_DWORD *)v14 = 0;
LABEL_21:
    if ( *((_QWORD *)&v25 + 1) && (_QWORD)v25 )
    {
      (*(void (**)(void))(**((_QWORD **)&v25 + 1) + 80LL))();
      *(_QWORD *)&v25 = 0;
    }
    ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((char *)&v25 + 8);
    goto LABEL_25;
  }
  if ( v13 < 0 )
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v13,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      6319);
    goto LABEL_21;
  }
  v22 = UnifiedStoreCursorLocation::CopyTo((UnifiedStoreCursorLocation *)(v25 + 24), v14, 0);
  v8 = v22;
  if ( v22 < 0 )
  {
    v20 = 6322;
    v21 = (unsigned int)v22;
    goto LABEL_29;
  }
  if ( *((_QWORD *)&v25 + 1) && (_QWORD)v25 )
  {
    (*(void (**)(void))(**((_QWORD **)&v25 + 1) + 80LL))();
    *(_QWORD *)&v25 = 0;
  }
  ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>((char *)&v25 + 8);
  v8 = 0;
LABEL_25:
  auto_DBSession::~auto_DBSession((auto_DBSession *)&v26);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return v8;
}

```

## disassembly

```asm
0x180019ea0  push    rbp
0x180019ea2  push    rbx
0x180019ea3  push    rsi
0x180019ea4  push    rdi
0x180019ea5  push    r12
0x180019ea7  push    r13
0x180019ea9  push    r14
0x180019eab  push    r15
0x180019ead  mov     rbp, rsp
0x180019eb0  sub     rsp, 58h
0x180019eb4  mov     rsi, rcx
0x180019eb7  mov     r12d, edx
0x180019eba  add     rcx, 10h; lpCriticalSection
0x180019ebe  call    cs:__imp_EnterCriticalSection
0x180019ec4  mov     rcx, [rsi+80h]
0x180019ecb  lea     rdx, [rbp+var_18]
0x180019ecf  mov     r14d, [rsi+7Ch]
0x180019ed3  xor     edi, edi
0x180019ed5  mov     r15d, [rsi+78h]
0x180019ed9  xorps   xmm0, xmm0
0x180019edc  mov     [rbp+var_18], rdi
0x180019ee0  mov     [rbp+var_10], rdi
0x180019ee4  movdqu  [rbp+var_28], xmm0
0x180019ee9  mov     rax, [rcx]
0x180019eec  mov     rax, [rax+0A0h]
0x180019ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ef8  mov     ebx, eax
0x180019efa  test    eax, eax
0x180019efc  js      loc_18001A0F6
0x180019f02  mov     rcx, [rbp+var_18]
0x180019f06  mov     rax, [rcx]
0x180019f09  mov     rax, [rax+20h]
0x180019f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f12  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFF888h; long g_breakOnJetError
0x180019f1c  mov     ebx, eax
0x180019f1e  jz      loc_18001A126
0x180019f24  mov     edi, 1
0x180019f29  cmp     ebx, 80C80778h
0x180019f2f  jz      short loc_180019F3C
0x180019f31  test    ebx, ebx
0x180019f33  js      loc_18001A11C
0x180019f39  mov     dword ptr [rbp+var_10+4], edi
0x180019f3c  mov     rbx, [rbp+var_18]
0x180019f40  mov     rcx, qword ptr [rbp+var_28+8]
0x180019f44  mov     dword ptr [rbp+var_10], edi
0x180019f47  cmp     rcx, rbx
0x180019f4a  jz      short loc_180019F7E
0x180019f4c  test    rbx, rbx
0x180019f4f  jz      short loc_180019F64
0x180019f51  mov     rax, [rbx]
0x180019f54  mov     rcx, rbx
0x180019f57  mov     rax, [rax+8]
0x180019f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f60  mov     rcx, qword ptr [rbp+var_28+8]
0x180019f64  test    rcx, rcx
0x180019f67  jz      short loc_180019F75
0x180019f69  mov     rax, [rcx]
0x180019f6c  mov     rax, [rax+10h]
0x180019f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f75  mov     rcx, rbx
0x180019f78  mov     qword ptr [rbp+var_28+8], rbx
0x180019f7c  jmp     short loc_180019F81
0x180019f7e  mov     rbx, rcx
0x180019f81  test    rbx, rbx
0x180019f84  jz      loc_18001A04F
0x180019f8a  cmp     qword ptr [rbp+var_28], 0
0x180019f8f  jnz     loc_18001A13D
0x180019f95  mov     rax, [rcx]
0x180019f98  lea     r9, [rbp+var_28]
0x180019f9c  mov     r8d, r14d
0x180019f9f  mov     edx, r15d
0x180019fa2  mov     rax, [rax+40h]
0x180019fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fab  xor     r14d, r14d
0x180019fae  mov     ebx, eax
0x180019fb0  test    eax, eax
0x180019fb2  js      loc_18001A14F
0x180019fb8  mov     rcx, [rsi+70h]
0x180019fbc  mov     r8d, r12d
0x180019fbf  mov     rdx, qword ptr [rbp+var_28]
0x180019fc3  mov     rax, [rcx]
0x180019fc6  mov     rax, [rax+60h]
0x180019fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fcf  lea     rdx, [rsi+38h]; struct UnifiedStoreCursorLocation *
0x180019fd3  mov     ebx, eax
0x180019fd5  cmp     eax, 80070019h
0x180019fda  jz      loc_18001A0EE
0x180019fe0  test    eax, eax
0x180019fe2  jns     loc_18001A0A1
0x180019fe8  mov     r9d, 18AFh
0x180019fee  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180019ff5  mov     edx, edi
0x180019ff7  mov     ecx, eax
0x180019ff9  call    Log_UnistoreHREvent_0
0x180019ffe  mov     rcx, qword ptr [rbp+var_28+8]
0x18001a002  test    rcx, rcx
0x18001a005  jz      short loc_18001A020
0x18001a007  mov     rdx, qword ptr [rbp+var_28]
0x18001a00b  test    rdx, rdx
0x18001a00e  jz      short loc_18001A020
0x18001a010  mov     rax, [rcx]
0x18001a013  mov     rax, [rax+50h]
0x18001a017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a01c  mov     qword ptr [rbp+var_28], r14
0x18001a020  lea     rcx, [rbp+var_28+8]; void *
0x18001a024  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18001a029  lea     rcx, [rbp+var_18]; this
0x18001a02d  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x18001a032  lea     rcx, [rsi+10h]; lpCriticalSection
0x18001a036  call    cs:__imp_LeaveCriticalSection
0x18001a03c  mov     eax, ebx
0x18001a03e  add     rsp, 58h
0x18001a042  pop     r15
0x18001a044  pop     r14
0x18001a046  pop     r13
0x18001a048  pop     r12
0x18001a04a  pop     rdi
0x18001a04b  pop     rsi
0x18001a04c  pop     rbx
0x18001a04d  pop     rbp
0x18001a04e  retn
0x18001a04f  mov     ebx, 8000FFFFh
0x18001a054  mov     r9d, 2FCh
0x18001a05a  mov     ecx, ebx
0x18001a05c  xor     edx, edx
0x18001a05e  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001a065  call    Log_UnistoreHREvent_0
0x18001a06a  mov     r9d, 1A0h
0x18001a070  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001a077  mov     edx, edi
0x18001a079  mov     ecx, ebx
0x18001a07b  call    Log_UnistoreHREvent_0
0x18001a080  mov     r9d, 18A8h
0x18001a086  mov     ecx, ebx
0x18001a088  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001a08f  mov     edx, edi
0x18001a091  call    Log_UnistoreHREvent_0
0x18001a096  lea     rcx, [rbp+var_28]; this
0x18001a09a  call    ??1auto_TableHandle@@QEAA@XZ; auto_TableHandle::~auto_TableHandle(void)
0x18001a09f  jmp     short loc_18001A029
0x18001a0a1  mov     rcx, qword ptr [rbp+var_28]
0x18001a0a5  xor     r8d, r8d; int
0x18001a0a8  add     rcx, 18h; this
0x18001a0ac  call    ?CopyTo@UnifiedStoreCursorLocation@@QEBAJAEAV1@H@Z; UnifiedStoreCursorLocation::CopyTo(UnifiedStoreCursorLocation &,int)
0x18001a0b1  mov     ebx, eax
0x18001a0b3  test    eax, eax
0x18001a0b5  js      loc_18001A15E
0x18001a0bb  mov     rcx, qword ptr [rbp+var_28+8]
0x18001a0bf  test    rcx, rcx
0x18001a0c2  jz      short loc_18001A0DD
0x18001a0c4  mov     rdx, qword ptr [rbp+var_28]
0x18001a0c8  test    rdx, rdx
0x18001a0cb  jz      short loc_18001A0DD
0x18001a0cd  mov     rax, [rcx]
0x18001a0d0  mov     rax, [rax+50h]
0x18001a0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0d9  mov     qword ptr [rbp+var_28], r14
0x18001a0dd  lea     rcx, [rbp+var_28+8]; void *
0x18001a0e1  call    ??1?$CComPtrBase@UIClockVectorElement@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClockVectorElement>::~CComPtrBase<IClockVectorElement>(void)
0x18001a0e6  mov     ebx, r14d
0x18001a0e9  jmp     loc_18001A029
0x18001a0ee  mov     [rdx], r14d
0x18001a0f1  jmp     loc_180019FFE
0x18001a0f6  mov     r9d, 342h
0x18001a0fc  mov     edi, 1
0x18001a101  mov     ecx, eax
0x18001a103  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001a10a  mov     edx, edi
0x18001a10c  call    Log_UnistoreHREvent_0
0x18001a111  mov     r9d, 19Ch
0x18001a117  jmp     loc_18001A070
0x18001a11c  mov     r9d, 346h
0x18001a122  mov     ecx, ebx
0x18001a124  jmp     short loc_18001A103
0x18001a126  mov     r8d, 19h
0x18001a12c  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001a133  call    Log_AssertionEvent
0x18001a138  jmp     loc_180019F24
0x18001a13d  lea     rcx, [rbp+var_28]; this
0x18001a141  call    ?Close@auto_TableHandle@@QEAAXXZ; auto_TableHandle::Close(void)
0x18001a146  mov     rcx, qword ptr [rbp+var_28+8]
0x18001a14a  jmp     loc_180019F95
0x18001a14f  mov     r9d, 303h
0x18001a155  mov     edx, edi
0x18001a157  mov     ecx, eax
0x18001a159  jmp     loc_18001A05E
0x18001a15e  mov     r9d, 18B2h
0x18001a164  mov     ecx, eax
0x18001a166  jmp     loc_18001A088
```
