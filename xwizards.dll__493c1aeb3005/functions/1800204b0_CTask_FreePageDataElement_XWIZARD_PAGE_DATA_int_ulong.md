# CTask::FreePageDataElement(_XWIZARD_PAGE_DATA * *,int,ulong)

- ea: `0x1800204b0`
- end: `0x1800207b9`
- name: `?FreePageDataElement@CTask@@AEAAXPEAPEAU_XWIZARD_PAGE_DATA@@HK@Z`
- size: `777`
- prototype: `void __fastcall(CTask *__hidden this, struct _XWIZARD_PAGE_DATA **, int, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180020188`
- `0x180021b1c`
- `0x180021d04`
- `0x180023d80`

## callees

- `0x18000ae04`
- `0x1800204b0`
- `0x180031b30`
- `0x180031d2c`
- `0x180032198`
- `0x1800329db`
- `0x180032a02`
- `0x180034010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180020665`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020665`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020683`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020683`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002050d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002050d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020700`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020792`

## pseudocode

```c
void __fastcall CTask::FreePageDataElement(CTask *this, struct _XWIZARD_PAGE_DATA **a2, int a3, unsigned int a4)
{
  BOOL v6; // ebp
  CTask *v8; // rbx
  void *v9; // rcx
  _DWORD *v10; // r10
  __int64 v11; // rdx
  int *v12; // rdx
  CPXWizardSemaphoreLock *v13; // rdi
  HMODULE v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int *v19; // rcx
  int v20; // ebx
  __int128 v21; // xmm6
  __int64 v22; // rdi
  unsigned int v23; // esi
  __int64 v24; // rbp
  __int64 v25; // r14
  __int64 v26; // r15
  unsigned int v27; // r12d

  v6 = *((_DWORD *)this + 1) == 0;
  v8 = this;
  if ( *a2 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 256);
    *((_DWORD *)*a2 + 25) = 1;
    v9 = (void *)*((_QWORD *)*a2 + 20);
    if ( v9 )
    {
      CoTaskMemFree(v9);
      *((_QWORD *)*a2 + 20) = 0;
    }
    v10 = *a2;
    if ( *((_DWORD *)*a2 + 16) )
    {
      v11 = *((_QWORD *)v10 + 19);
      if ( v11 )
      {
        if ( (*(int (__fastcall **)(_QWORD, __int64, unsigned __int64, _QWORD))(**((_QWORD **)v8 + 36) + 112LL))(
               *((_QWORD *)v8 + 36),
               v11,
               (unsigned __int64)(v10 + 40) & -(__int64)(a3 != 0),
               a4 & *((_DWORD *)v8 + 30)) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            2147500037LL);
        }
      }
    }
    v12 = (int *)*((_QWORD *)*a2 + 19);
    if ( v12
      && (*(int (__fastcall **)(_QWORD, int *, _QWORD))(**((_QWORD **)v8 + 36) + 96LL))(
           *((_QWORD *)v8 + 36),
           v12,
           *((unsigned int *)v8 + 30)) < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids, 2147500037LL);
    }
    *((_QWORD *)*a2 + 19) = 0;
    v13 = (CPXWizardSemaphoreLock *)*((_QWORD *)*a2 + 13);
    if ( v13 )
    {
      if ( a3 )
      {
        CPXWizardSemaphoreLock::GetRefCount(*((CPXWizardSemaphoreLock **)*a2 + 13), (int)v12);
      }
      else
      {
        if ( *((_DWORD *)*a2 + 28)
          && (int)CPXWizardSemaphoreLock::Release(*((CPXWizardSemaphoreLock **)*a2 + 13), v12, v6) < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            &WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids,
            2147500037LL);
        }
        CPXWizardSemaphoreLock::~CPXWizardSemaphoreLock(v13);
        operator delete(v13);
        *((_QWORD *)*a2 + 13) = 0;
      }
    }
    v14 = (HMODULE)*((_QWORD *)*a2 + 18);
    if ( v14 )
      FreeLibrary(v14);
    v15 = *((_QWORD *)*a2 + 3);
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( !a3 )
    {
      v16 = *((_QWORD *)*a2 + 4);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v17 = *((_QWORD *)*a2 + 5);
      if ( v17 )
      {
        v18 = _RTDynamicCast_0(
                v17,
                0,
                &IXWizardSource `RTTI Type Descriptor',
                &IPXWizardInternalSource `RTTI Type Descriptor',
                0);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 32LL))(v18);
      }
    }
    CoTaskMemFree(*((LPVOID *)*a2 + 7));
    v19 = (unsigned int *)*a2;
    if ( a3 )
    {
      v20 = *v19;
      v21 = *(_OWORD *)(v19 + 1);
      v22 = *((_QWORD *)v19 + 13);
      v23 = v19[28];
      v24 = *((_QWORD *)v19 + 5);
      v25 = *((_QWORD *)v19 + 4);
      v26 = *((_QWORD *)v19 + 20);
      v27 = v19[12];
      memset_0(v19, 0, *v19);
      *(_DWORD *)*a2 = v20;
      v8 = this;
      *(_OWORD *)((char *)*a2 + 4) = v21;
      *((_QWORD *)*a2 + 13) = v22;
      *((_DWORD *)*a2 + 28) = v23;
      *((_QWORD *)*a2 + 5) = v24;
      *((_QWORD *)*a2 + 4) = v25;
      *((_QWORD *)*a2 + 20) = v26;
      *((_DWORD *)*a2 + 12) = (v27 & 0x20) != 0 ? v27 : 0;
    }
    else
    {
      CoTaskMemFree(v19);
      *a2 = 0;
    }
    _InterlockedDecrement((volatile signed __int32 *)v8 + 256);
  }
}

```

## disassembly

```asm
0x1800204b0  mov     [rsp+arg_0], rcx
0x1800204b5  push    rbx
0x1800204b6  push    rbp
0x1800204b7  push    rsi
0x1800204b8  push    rdi
0x1800204b9  push    r12
0x1800204bb  push    r13
0x1800204bd  push    r14
0x1800204bf  push    r15
0x1800204c1  sub     rsp, 48h
0x1800204c5  xor     r14d, r14d
0x1800204c8  movaps  [rsp+88h+var_58], xmm6
0x1800204cd  cmp     [rcx+4], r14d
0x1800204d1  mov     ebp, r14d
0x1800204d4  mov     edi, r9d
0x1800204d7  mov     esi, r8d
0x1800204da  setz    bpl
0x1800204de  mov     r13, rdx
0x1800204e1  mov     rbx, rcx
0x1800204e4  cmp     [rdx], r14
0x1800204e7  jz      loc_1800207A3
0x1800204ed  lock inc dword ptr [rcx+400h]
0x1800204f4  mov     rax, [rdx]
0x1800204f7  mov     dword ptr [rax+64h], 1
0x1800204fe  mov     rax, [rdx]
0x180020501  mov     rcx, [rax+0A0h]; pv
0x180020508  test    rcx, rcx
0x18002050b  jz      short loc_18002051E
0x18002050d  call    cs:__imp_CoTaskMemFree
0x180020513  mov     rax, [r13+0]
0x180020517  mov     [rax+0A0h], r14
0x18002051e  mov     r10, [r13+0]
0x180020522  lea     r15, WPP_GLOBAL_Control
0x180020529  mov     r12b, 4
0x18002052c  cmp     [r10+40h], r14d
0x180020530  jz      short loc_18002059A
0x180020532  mov     rdx, [r10+98h]
0x180020539  test    rdx, rdx
0x18002053c  jz      short loc_18002059A
0x18002053e  mov     rcx, [rbx+120h]
0x180020545  add     r10, 0A0h
0x18002054c  mov     r9d, [rbx+78h]
0x180020550  mov     eax, esi
0x180020552  and     r9d, edi
0x180020555  neg     eax
0x180020557  mov     r11, [rcx]
0x18002055a  sbb     r8, r8
0x18002055d  and     r8, r10
0x180020560  mov     rax, [r11+70h]
0x180020564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020569  test    eax, eax
0x18002056b  jns     short loc_18002059A
0x18002056d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020574  cmp     rcx, r15
0x180020577  jz      short loc_18002059A
0x180020579  test    [rcx+1Ch], r12b
0x18002057d  jz      short loc_18002059A
0x18002057f  mov     rcx, [rcx+10h]
0x180020583  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x18002058a  mov     edx, 22h ; '"'
0x18002058f  mov     r9d, 80004005h
0x180020595  call    WPP_SF_d
0x18002059a  mov     rax, [r13+0]
0x18002059e  mov     rdx, [rax+98h]
0x1800205a5  test    rdx, rdx
0x1800205a8  jz      short loc_1800205F2
0x1800205aa  mov     rcx, [rbx+120h]
0x1800205b1  mov     r8d, [rbx+78h]
0x1800205b5  mov     rax, [rcx]
0x1800205b8  mov     rax, [rax+60h]
0x1800205bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205c1  test    eax, eax
0x1800205c3  jns     short loc_1800205F2
0x1800205c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205cc  cmp     rcx, r15
0x1800205cf  jz      short loc_1800205F2
0x1800205d1  test    [rcx+1Ch], r12b
0x1800205d5  jz      short loc_1800205F2
0x1800205d7  mov     rcx, [rcx+10h]
0x1800205db  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x1800205e2  mov     edx, 23h ; '#'
0x1800205e7  mov     r9d, 80004005h
0x1800205ed  call    WPP_SF_d
0x1800205f2  mov     rax, [r13+0]
0x1800205f6  mov     [rax+98h], r14
0x1800205fd  mov     rax, [r13+0]
0x180020601  mov     rdi, [rax+68h]
0x180020605  test    rdi, rdi
0x180020608  jz      short loc_180020673
0x18002060a  test    esi, esi
0x18002060c  jz      short loc_180020618
0x18002060e  mov     rcx, rdi; this
0x180020611  call    ?GetRefCount@CPXWizardSemaphoreLock@@QEAAJH@Z; CPXWizardSemaphoreLock::GetRefCount(int)
0x180020616  jmp     short loc_180020673
0x180020618  cmp     [rax+70h], r14d
0x18002061c  jz      short loc_18002065A
0x18002061e  mov     r8d, ebp; int
0x180020621  mov     rcx, rdi; this
0x180020624  call    ?Release@CPXWizardSemaphoreLock@@QEAAJPEAJH@Z; CPXWizardSemaphoreLock::Release(long *,int)
0x180020629  test    eax, eax
0x18002062b  jns     short loc_18002065A
0x18002062d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020634  cmp     rcx, r15
0x180020637  jz      short loc_18002065A
0x180020639  test    [rcx+1Ch], r12b
0x18002063d  jz      short loc_18002065A
0x18002063f  mov     rcx, [rcx+10h]
0x180020643  lea     r8, WPP_1d0e0644b79332cca5d83374acd55a12_Traceguids
0x18002064a  mov     edx, 24h ; '$'
0x18002064f  mov     r9d, 80004005h
0x180020655  call    WPP_SF_d
0x18002065a  mov     rcx, rdi; this
0x18002065d  call    ??1CPXWizardSemaphoreLock@@QEAA@XZ; CPXWizardSemaphoreLock::~CPXWizardSemaphoreLock(void)
0x180020662  mov     rcx, rdi
0x180020665  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002066b  mov     rax, [r13+0]
0x18002066f  mov     [rax+68h], r14
0x180020673  mov     rax, [r13+0]
0x180020677  mov     rcx, [rax+90h]; hLibModule
0x18002067e  test    rcx, rcx
0x180020681  jz      short loc_180020689
0x180020683  call    cs:__imp_FreeLibrary
0x180020689  mov     rax, [r13+0]
0x18002068d  mov     rcx, [rax+18h]
0x180020691  test    rcx, rcx
0x180020694  jz      short loc_1800206A2
0x180020696  mov     rax, [rcx]
0x180020699  mov     rax, [rax+10h]
0x18002069d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206a2  test    esi, esi
0x1800206a4  jnz     short loc_1800206F8
0x1800206a6  mov     rax, [r13+0]
0x1800206aa  mov     rcx, [rax+20h]
0x1800206ae  test    rcx, rcx
0x1800206b1  jz      short loc_1800206BF
0x1800206b3  mov     rax, [rcx]
0x1800206b6  mov     rax, [rax+10h]
0x1800206ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206bf  mov     rax, [r13+0]
0x1800206c3  mov     rcx, [rax+28h]
0x1800206c7  test    rcx, rcx
0x1800206ca  jz      short loc_1800206F8
0x1800206cc  lea     r9, ??_R0?AUIPXWizardInternalSource@@@8; IPXWizardInternalSource `RTTI Type Descriptor'
0x1800206d3  mov     [rsp+88h+var_68], r14d
0x1800206d8  lea     r8, ??_R0?AUIXWizardSource@@@8; IXWizardSource `RTTI Type Descriptor'
0x1800206df  xor     edx, edx
0x1800206e1  call    __RTDynamicCast_0
0x1800206e6  mov     rdx, rax
0x1800206e9  mov     rcx, [rax]
0x1800206ec  mov     rax, [rcx+20h]
0x1800206f0  mov     rcx, rdx
0x1800206f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206f8  mov     rcx, [r13+0]
0x1800206fc  mov     rcx, [rcx+38h]; pv
0x180020700  call    cs:__imp_CoTaskMemFree
0x180020706  mov     rcx, [r13+0]; void *
0x18002070a  test    esi, esi
0x18002070c  jz      loc_180020792
0x180020712  mov     ebx, [rcx]
0x180020714  xor     edx, edx; Val
0x180020716  movups  xmm6, xmmword ptr [rcx+4]
0x18002071a  mov     rdi, [rcx+68h]
0x18002071e  mov     r8d, ebx; Size
0x180020721  mov     esi, [rcx+70h]
0x180020724  mov     rbp, [rcx+28h]
0x180020728  mov     r14, [rcx+20h]
0x18002072c  mov     r15, [rcx+0A0h]
0x180020733  mov     r12d, [rcx+30h]
0x180020737  call    memset_0
0x18002073c  mov     rax, [r13+0]
0x180020740  mov     [rax], ebx
0x180020742  mov     rax, [r13+0]
0x180020746  mov     rbx, [rsp+88h+arg_0]
0x18002074e  movdqu  xmmword ptr [rax+4], xmm6
0x180020753  mov     rax, [r13+0]
0x180020757  mov     [rax+68h], rdi
0x18002075b  mov     rax, [r13+0]
0x18002075f  mov     [rax+70h], esi
0x180020762  mov     rax, [r13+0]
0x180020766  mov     [rax+28h], rbp
0x18002076a  mov     rax, [r13+0]
0x18002076e  mov     [rax+20h], r14
0x180020772  mov     rax, [r13+0]
0x180020776  mov     [rax+0A0h], r15
0x18002077d  mov     eax, r12d
0x180020780  and     al, 20h
0x180020782  neg     al
0x180020784  mov     rax, [r13+0]
0x180020788  sbb     ecx, ecx
0x18002078a  and     ecx, r12d
0x18002078d  mov     [rax+30h], ecx
0x180020790  jmp     short loc_18002079C
0x180020792  call    cs:__imp_CoTaskMemFree
0x180020798  mov     [r13+0], r14
0x18002079c  lock dec dword ptr [rbx+400h]
0x1800207a3  movaps  xmm6, [rsp+88h+var_58]
0x1800207a8  add     rsp, 48h
0x1800207ac  pop     r15
0x1800207ae  pop     r14
0x1800207b0  pop     r13
0x1800207b2  pop     r12
0x1800207b4  pop     rdi
0x1800207b5  pop     rsi
0x1800207b6  pop     rbp
0x1800207b7  pop     rbx
0x1800207b8  retn
```
