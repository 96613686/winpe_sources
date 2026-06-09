# DBTable::SeekToBeginning(void)

- ea: `0x180050190`
- end: `0x1800506ef`
- name: `?SeekToBeginning@DBTable@@UEAAJXZ`
- size: `1375`
- prototype: `__int64 __fastcall(DBTable *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x1800068f0`
- `0x18000866c`
- `0x1800086bc`
- `0x18004bd20`
- `0x180050150`
- `0x180050190`
- `0x18006f180`
- `0x1800c5092`
- `0x1800c50aa`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800501b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800501b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180050479`

## string_xrefs

- `0x18005033e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x180050354`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800503af`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800506cd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800505c1`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18005032c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180050408`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x1800504ba`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18005052c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x18005057e`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x180050599`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBSession.h`
- `0x1800506b9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\EseHelper.h`

## pseudocode

```c
__int64 __fastcall DBTable::SeekToBeginning(DBTable *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // r12
  __int64 v3; // rcx
  unsigned int v4; // r14d
  unsigned int v5; // r15d
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rbx
  void **v14; // r15
  void **v15; // r12
  __int64 v16; // rax
  unsigned __int64 v17; // r14
  unsigned __int64 v18; // r13
  char *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v28; // r9
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  int v32; // eax
  void **v33; // r14
  __int64 v34; // rax
  unsigned __int64 v35; // r15
  unsigned __int64 v36; // r12
  char *v37; // rax
  __int64 v38; // r9
  __int64 v39; // [rsp+30h] [rbp-28h] BYREF
  __int64 v40; // [rsp+38h] [rbp-20h]
  __int128 v41; // [rsp+40h] [rbp-18h] BYREF
  struct _RTL_CRITICAL_SECTION *v42; // [rsp+A0h] [rbp+48h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v42 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v3 = *((_QWORD *)this + 16);
  v4 = *((_DWORD *)this + 31);
  v5 = *((_DWORD *)this + 30);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 160LL))(v3, &v39);
  v7 = v6;
  if ( v6 < 0 )
  {
    v28 = 834;
    v29 = (unsigned int)v6;
    goto LABEL_55;
  }
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 32LL))(v39);
  if ( g_breakOnJetError == -1912 )
    Log_AssertionEvent(
      v8,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
      25);
  if ( v7 != -2134374536 )
  {
    if ( (v7 & 0x80000000) == 0 )
    {
      HIDWORD(v40) = 1;
      goto LABEL_7;
    }
    v28 = 838;
    v29 = v7;
LABEL_55:
    Log_UnistoreHREvent_0(
      v29,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v28);
    v23 = 412;
LABEL_25:
    Log_UnistoreHREvent_0(
      v7,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      v23);
    Log_UnistoreHREvent_0(
      v7,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      6080);
    v24 = *((_QWORD *)&v41 + 1);
    if ( *((_QWORD *)&v41 + 1) )
    {
      if ( (_QWORD)v41 )
      {
        (*(void (**)(void))(**((_QWORD **)&v41 + 1) + 80LL))();
        v24 = *((_QWORD *)&v41 + 1);
        *(_QWORD *)&v41 = 0;
      }
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    goto LABEL_30;
  }
LABEL_7:
  v9 = v39;
  v10 = *((_QWORD *)&v41 + 1);
  LODWORD(v40) = 1;
  if ( *((_QWORD *)&v41 + 1) == v39 )
  {
    v9 = *((_QWORD *)&v41 + 1);
  }
  else
  {
    if ( v39 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
      v10 = *((_QWORD *)&v41 + 1);
    }
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = v9;
    *((_QWORD *)&v41 + 1) = v9;
  }
  if ( !v9 )
  {
    v7 = -2147418113;
    v20 = 764;
    v21 = 2147549183LL;
    v22 = 0;
LABEL_24:
    Log_UnistoreHREvent_0(
      v21,
      v22,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      v20);
    v23 = 416;
    goto LABEL_25;
  }
  if ( (_QWORD)v41 )
  {
    auto_TableHandle::Close((auto_TableHandle *)&v41);
    v10 = *((_QWORD *)&v41 + 1);
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v10 + 64LL))(v10, v5, v4, &v41);
  v7 = v11;
  if ( v11 < 0 )
  {
    v20 = 771;
    v22 = 1;
    v21 = (unsigned int)v11;
    goto LABEL_24;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 14) + 56LL))(*((_QWORD *)this + 14), v41);
  v7 = v12;
  if ( v12 == -2147024871 )
  {
    *((_DWORD *)this + 14) = 0;
  }
  else
  {
    if ( v12 >= 0 )
    {
      v13 = v41;
      if ( !*(_DWORD *)(v41 + 24) )
      {
        *((_DWORD *)this + 15) = -1;
        v30 = 0;
        goto LABEL_57;
      }
      *((_DWORD *)this + 14) = 0;
      v14 = (void **)((char *)this + 64);
      v15 = (void **)((char *)this + 72);
      *((_DWORD *)this + 15) = *(_DWORD *)(v13 + 28);
      v16 = *((_QWORD *)this + 8);
      v17 = *(_QWORD *)(v13 + 40) - *(_QWORD *)(v13 + 32);
      v18 = *((_QWORD *)this + 9) - v16;
      if ( v17 > v18 )
      {
        if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                                 (char *)this + 64,
                                 *(_QWORD *)(v13 + 40) - *(_QWORD *)(v13 + 32)) )
        {
          v38 = 399;
LABEL_83:
          v7 = -2147024882;
          Log_UnistoreHREvent_0(
            2147942414LL,
            0,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\EseHelper.h",
            v38);
          Log_UnistoreHREvent_0(
            2147942414LL,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
            6090);
          auto_TableHandle::~auto_TableHandle((auto_TableHandle *)&v41);
          v1 = v42;
LABEL_30:
          auto_DBSession::~auto_DBSession((auto_DBSession *)&v39);
          goto LABEL_52;
        }
        memset_0(*v15, 0, v17 - v18);
        v19 = (char *)*v14 + v17;
      }
      else
      {
        v19 = (char *)(v17 + v16);
      }
      *v15 = v19;
      memcpy_0(*v14, *(const void **)(v13 + 32), *(_QWORD *)(v13 + 40) - *(_QWORD *)(v13 + 32));
      v33 = (void **)((char *)this + 88);
      v34 = *((_QWORD *)this + 11);
      v35 = *(_QWORD *)(v13 + 64) - *(_QWORD *)(v13 + 56);
      v36 = *((_QWORD *)this + 12) - v34;
      if ( v35 <= v36 )
      {
        v37 = (char *)(v35 + v34);
LABEL_80:
        *((_QWORD *)this + 12) = v37;
        memcpy_0(*v33, *(const void **)(v13 + 56), *(_QWORD *)(v13 + 64) - *(_QWORD *)(v13 + 56));
        v13 = v41;
        v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
        v30 = 1;
LABEL_57:
        *((_DWORD *)this + 14) = v30;
        v31 = *((_QWORD *)&v41 + 1);
        if ( *((_QWORD *)&v41 + 1) )
        {
          if ( v13 )
          {
            (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)&v41 + 1) + 80LL))(*((_QWORD *)&v41 + 1), v13);
            v31 = *((_QWORD *)&v41 + 1);
            *(_QWORD *)&v41 = 0;
          }
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        if ( !(_DWORD)v40 )
          goto LABEL_49;
        if ( !v39 )
          Log_AssertionEvent(
            v31,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
            850);
        if ( HIDWORD(v40) )
        {
          v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 40LL))(v39);
          if ( v32 < 0 )
          {
            Log_UnistoreHREvent_0(
              (unsigned int)v32,
              1,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
              853);
LABEL_49:
            if ( v39 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
            v7 = 0;
            goto LABEL_52;
          }
          HIDWORD(v40) = 0;
        }
        if ( v39 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
          v39 = 0;
        }
        LODWORD(v40) = 0;
        goto LABEL_49;
      }
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              (char *)this + 88,
                              *(_QWORD *)(v13 + 64) - *(_QWORD *)(v13 + 56)) )
      {
        memset_0(*((void **)this + 12), 0, v35 - v36);
        v37 = (char *)*v33 + v35;
        goto LABEL_80;
      }
      v38 = 404;
      goto LABEL_83;
    }
    Log_UnistoreHREvent_0(
      (unsigned int)v12,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      6087);
  }
  v25 = *((_QWORD *)&v41 + 1);
  if ( *((_QWORD *)&v41 + 1) )
  {
    if ( (_QWORD)v41 )
    {
      (*(void (**)(void))(**((_QWORD **)&v41 + 1) + 80LL))();
      v25 = *((_QWORD *)&v41 + 1);
      *(_QWORD *)&v41 = 0;
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( (_DWORD)v40 )
  {
    if ( !v39 )
      Log_AssertionEvent(
        v25,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
        850);
    if ( !HIDWORD(v40) )
      goto LABEL_43;
    v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 40LL))(v39);
    if ( v26 >= 0 )
    {
      HIDWORD(v40) = 0;
LABEL_43:
      if ( v39 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        v39 = 0;
      }
      LODWORD(v40) = 0;
      goto LABEL_46;
    }
    Log_UnistoreHREvent_0(
      (unsigned int)v26,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\DBSession.h",
      853);
  }
LABEL_46:
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
LABEL_52:
  LeaveCriticalSection(v1);
  return v7;
}

```

## disassembly

```asm
0x180050190  push    rbp
0x180050192  push    rbx
0x180050193  push    rsi
0x180050194  push    rdi
0x180050195  push    r12
0x180050197  push    r13
0x180050199  push    r14
0x18005019b  push    r15
0x18005019d  mov     rbp, rsp
0x1800501a0  sub     rsp, 58h
0x1800501a4  lea     r12, [rcx+10h]
0x1800501a8  mov     rsi, rcx
0x1800501ab  mov     rcx, r12; lpCriticalSection
0x1800501ae  mov     [rbp+arg_0], r12
0x1800501b2  call    cs:__imp_EnterCriticalSection
0x1800501b8  mov     rcx, [rsi+80h]
0x1800501bf  lea     rdx, [rbp+var_28]
0x1800501c3  mov     r14d, [rsi+7Ch]
0x1800501c7  xor     r13d, r13d
0x1800501ca  mov     r15d, [rsi+78h]
0x1800501ce  xorps   xmm0, xmm0
0x1800501d1  mov     [rbp+var_28], r13
0x1800501d5  mov     [rbp+var_20], r13
0x1800501d9  movdqu  [rbp+var_18], xmm0
0x1800501de  mov     rax, [rcx]
0x1800501e1  mov     rax, [rax+0A0h]
0x1800501e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501ed  mov     ebx, eax
0x1800501ef  test    eax, eax
0x1800501f1  js      loc_1800504AD
0x1800501f7  mov     rcx, [rbp+var_28]
0x1800501fb  mov     rax, [rcx]
0x1800501fe  mov     rax, [rax+20h]
0x180050202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050207  cmp     cs:?g_breakOnJetError@@3JA, 0FFFFF888h; long g_breakOnJetError
0x180050211  mov     ebx, eax
0x180050213  jz      loc_1800505BB
0x180050219  mov     edi, 1
0x18005021e  cmp     ebx, 80C80778h
0x180050224  jz      short loc_180050231
0x180050226  test    ebx, ebx
0x180050228  js      loc_1800505AE
0x18005022e  mov     dword ptr [rbp+var_20+4], edi
0x180050231  mov     rbx, [rbp+var_28]
0x180050235  mov     rcx, qword ptr [rbp+var_18+8]
0x180050239  mov     dword ptr [rbp+var_20], edi
0x18005023c  cmp     rcx, rbx
0x18005023f  jz      loc_180050315
0x180050245  test    rbx, rbx
0x180050248  jz      short loc_18005025D
0x18005024a  mov     rax, [rbx]
0x18005024d  mov     rcx, rbx
0x180050250  mov     rax, [rax+8]
0x180050254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050259  mov     rcx, qword ptr [rbp+var_18+8]
0x18005025d  test    rcx, rcx
0x180050260  jz      short loc_18005026E
0x180050262  mov     rax, [rcx]
0x180050265  mov     rax, [rax+10h]
0x180050269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005026e  mov     rcx, rbx
0x180050271  mov     qword ptr [rbp+var_18+8], rbx
0x180050275  test    rbx, rbx
0x180050278  jz      loc_18005031D
0x18005027e  cmp     qword ptr [rbp+var_18], r13
0x180050282  jnz     loc_1800505D2
0x180050288  mov     rax, [rcx]
0x18005028b  lea     r9, [rbp+var_18]
0x18005028f  mov     r8d, r14d
0x180050292  mov     edx, r15d
0x180050295  mov     rax, [rax+40h]
0x180050299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005029e  mov     ebx, eax
0x1800502a0  test    eax, eax
0x1800502a2  js      loc_1800505E4
0x1800502a8  mov     rcx, [rsi+70h]
0x1800502ac  mov     rdx, qword ptr [rbp+var_18]
0x1800502b0  mov     rax, [rcx]
0x1800502b3  mov     rax, [rax+38h]
0x1800502b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502bc  mov     ebx, eax
0x1800502be  cmp     eax, 80070019h
0x1800502c3  jz      loc_180050492
0x1800502c9  test    eax, eax
0x1800502cb  js      loc_1800503A9
0x1800502d1  mov     rbx, qword ptr [rbp+var_18]
0x1800502d5  cmp     [rbx+18h], r13d
0x1800502d9  jz      loc_1800504D3
0x1800502df  mov     [rsi+38h], r13d
0x1800502e3  lea     r15, [rsi+40h]
0x1800502e7  mov     eax, [rbx+1Ch]
0x1800502ea  lea     r12, [r15+8]
0x1800502ee  mov     [rsi+3Ch], eax
0x1800502f1  mov     r13, [r12]
0x1800502f5  mov     r14, [rbx+28h]
0x1800502f9  mov     rax, [r15]
0x1800502fc  sub     r14, [rbx+20h]
0x180050300  sub     r13, rax
0x180050303  cmp     r14, r13
0x180050306  ja      loc_1800505F3
0x18005030c  lea     rcx, [r14+rax]
0x180050310  jmp     loc_18005061D
0x180050315  mov     rbx, rcx
0x180050318  jmp     loc_180050275
0x18005031d  mov     ebx, 8000FFFFh
0x180050322  mov     r9d, 2FCh
0x180050328  mov     ecx, ebx
0x18005032a  xor     edx, edx
0x18005032c  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180050333  call    Log_UnistoreHREvent_0
0x180050338  mov     r9d, 1A0h
0x18005033e  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180050345  mov     edx, edi
0x180050347  mov     ecx, ebx
0x180050349  call    Log_UnistoreHREvent_0
0x18005034e  mov     r9d, 17C0h
0x180050354  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18005035b  mov     edx, edi
0x18005035d  mov     ecx, ebx
0x18005035f  call    Log_UnistoreHREvent_0
0x180050364  mov     rcx, qword ptr [rbp+var_18+8]
0x180050368  test    rcx, rcx
0x18005036b  jz      short loc_18005039B
0x18005036d  mov     rdx, qword ptr [rbp+var_18]
0x180050371  test    rdx, rdx
0x180050374  jz      short loc_18005038A
0x180050376  mov     rax, [rcx]
0x180050379  mov     rax, [rax+50h]
0x18005037d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050382  mov     rcx, qword ptr [rbp+var_18+8]
0x180050386  mov     qword ptr [rbp+var_18], r13
0x18005038a  test    rcx, rcx
0x18005038d  jz      short loc_18005039B
0x18005038f  mov     rax, [rcx]
0x180050392  mov     rax, [rax+10h]
0x180050396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005039b  lea     rcx, [rbp+var_28]; this
0x18005039f  call    ??1auto_DBSession@@QEAA@XZ; auto_DBSession::~auto_DBSession(void)
0x1800503a4  jmp     loc_180050476
0x1800503a9  mov     r9d, 17C7h
0x1800503af  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800503b6  mov     edx, edi
0x1800503b8  mov     ecx, eax
0x1800503ba  call    Log_UnistoreHREvent_0
0x1800503bf  mov     rcx, qword ptr [rbp+var_18+8]
0x1800503c3  test    rcx, rcx
0x1800503c6  jz      short loc_1800503F6
0x1800503c8  mov     rdx, qword ptr [rbp+var_18]
0x1800503cc  test    rdx, rdx
0x1800503cf  jz      short loc_1800503E5
0x1800503d1  mov     rax, [rcx]
0x1800503d4  mov     rax, [rax+50h]
0x1800503d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503dd  mov     rcx, qword ptr [rbp+var_18+8]
0x1800503e1  mov     qword ptr [rbp+var_18], r13
0x1800503e5  test    rcx, rcx
0x1800503e8  jz      short loc_1800503F6
0x1800503ea  mov     rax, [rcx]
0x1800503ed  mov     rax, [rax+10h]
0x1800503f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503f6  cmp     dword ptr [rbp+var_20], r13d
0x1800503fa  jz      short loc_180050443
0x1800503fc  cmp     [rbp+var_28], r13
0x180050400  jnz     short loc_180050414
0x180050402  mov     r8d, 352h
0x180050408  lea     rdx, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18005040f  call    Log_AssertionEvent
0x180050414  cmp     dword ptr [rbp+var_20+4], r13d
0x180050418  jz      short loc_180050436
0x18005041a  mov     rcx, [rbp+var_28]
0x18005041e  mov     rax, [rcx]
0x180050421  mov     rax, [rax+28h]
0x180050425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005042a  test    eax, eax
0x18005042c  js      loc_180050593
0x180050432  mov     dword ptr [rbp+var_20+4], r13d
0x180050436  mov     rcx, [rbp+var_28]
0x18005043a  test    rcx, rcx
0x18005043d  jnz     short loc_18005049B
0x18005043f  mov     dword ptr [rbp+var_20], r13d
0x180050443  mov     rcx, [rbp+var_28]
0x180050447  test    rcx, rcx
0x18005044a  jz      short loc_180050476
0x18005044c  mov     rax, [rcx]
0x18005044f  mov     rax, [rax+10h]
0x180050453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050458  jmp     short loc_180050476
0x18005045a  mov     dword ptr [rbp+var_20], r13d
0x18005045e  mov     rcx, [rbp+var_28]
0x180050462  test    rcx, rcx
0x180050465  jz      short loc_180050473
0x180050467  mov     rax, [rcx]
0x18005046a  mov     rax, [rax+10h]
0x18005046e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050473  mov     ebx, r13d
0x180050476  mov     rcx, r12; lpCriticalSection
0x180050479  call    cs:__imp_LeaveCriticalSection
0x18005047f  mov     eax, ebx
0x180050481  add     rsp, 58h
0x180050485  pop     r15
0x180050487  pop     r14
0x180050489  pop     r13
0x18005048b  pop     r12
0x18005048d  pop     rdi
0x18005048e  pop     rsi
0x18005048f  pop     rbx
0x180050490  pop     rbp
0x180050491  retn
0x180050492  mov     [rsi+38h], r13d
0x180050496  jmp     loc_1800503BF
0x18005049b  mov     rax, [rcx]
0x18005049e  mov     rax, [rax+10h]
0x1800504a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504a7  mov     [rbp+var_28], r13
0x1800504ab  jmp     short loc_18005043F
0x1800504ad  mov     r9d, 342h
0x1800504b3  mov     edi, 1
0x1800504b8  mov     ecx, eax
0x1800504ba  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800504c1  mov     edx, edi
0x1800504c3  call    Log_UnistoreHREvent_0
0x1800504c8  mov     r9d, 19Ch
0x1800504ce  jmp     loc_18005033E
0x1800504d3  mov     dword ptr [rsi+3Ch], 0FFFFFFFFh
0x1800504da  mov     eax, r13d
0x1800504dd  mov     [rsi+38h], eax
0x1800504e0  mov     rcx, qword ptr [rbp+var_18+8]
0x1800504e4  test    rcx, rcx
0x1800504e7  jz      short loc_180050516
0x1800504e9  test    rbx, rbx
0x1800504ec  jz      short loc_180050505
0x1800504ee  mov     rax, [rcx]
0x1800504f1  mov     rdx, rbx
0x1800504f4  mov     rax, [rax+50h]
0x1800504f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504fd  mov     rcx, qword ptr [rbp+var_18+8]
0x180050501  mov     qword ptr [rbp+var_18], r13
0x180050505  test    rcx, rcx
0x180050508  jz      short loc_180050516
0x18005050a  mov     rax, [rcx]
0x18005050d  mov     rax, [rax+10h]
0x180050511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050516  cmp     dword ptr [rbp+var_20], r13d
0x18005051a  jz      loc_18005045E
0x180050520  cmp     [rbp+var_28], r13
0x180050524  jnz     short loc_180050538
0x180050526  mov     r8d, 352h
0x18005052c  lea     rdx, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180050533  call    Log_AssertionEvent
0x180050538  cmp     dword ptr [rbp+var_20+4], r13d
0x18005053c  jz      short loc_180050556
0x18005053e  mov     rcx, [rbp+var_28]
0x180050542  mov     rax, [rcx]
0x180050545  mov     rax, [rax+28h]
0x180050549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005054e  test    eax, eax
0x180050550  js      short loc_180050578
0x180050552  mov     dword ptr [rbp+var_20+4], r13d
0x180050556  mov     rcx, [rbp+var_28]
0x18005055a  test    rcx, rcx
0x18005055d  jz      loc_18005045A
0x180050563  mov     rax, [rcx]
0x180050566  mov     rax, [rax+10h]
0x18005056a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005056f  mov     [rbp+var_28], r13
0x180050573  jmp     loc_18005045A
0x180050578  mov     r9d, 355h
0x18005057e  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180050585  mov     edx, edi
0x180050587  mov     ecx, eax
0x180050589  call    Log_UnistoreHREvent_0
0x18005058e  jmp     loc_18005045E
0x180050593  mov     r9d, 355h
0x180050599  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800505a0  mov     edx, edi
0x1800505a2  mov     ecx, eax
0x1800505a4  call    Log_UnistoreHREvent_0
0x1800505a9  jmp     loc_180050443
0x1800505ae  mov     r9d, 346h
0x1800505b4  mov     ecx, ebx
0x1800505b6  jmp     loc_1800504BA
0x1800505bb  mov     r8d, 19h
0x1800505c1  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800505c8  call    Log_AssertionEvent
0x1800505cd  jmp     loc_180050219
0x1800505d2  lea     rcx, [rbp+var_18]; this
0x1800505d6  call    ?Close@auto_TableHandle@@QEAAXXZ; auto_TableHandle::Close(void)
0x1800505db  mov     rcx, qword ptr [rbp+var_18+8]
0x1800505df  jmp     loc_180050288
0x1800505e4  mov     r9d, 303h
0x1800505ea  mov     edx, edi
0x1800505ec  mov     ecx, eax
0x1800505ee  jmp     loc_18005032C
0x1800505f3  mov     rdx, r14
0x1800505f6  mov     rcx, r15
0x1800505f9  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x1800505fe  xor     edx, edx; Val
0x180050600  test    al, al
0x180050602  jz      loc_1800506AE
0x180050608  mov     rcx, [r12]; void *
  ... truncated ...
```
