# ATL::CComCreator<ATL::CComObject<TaskServiceImpl>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800048a0`
- end: `0x180004b3d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VTaskServiceImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180004870`

## callees

- `0x1800048a0`
- `0x180004b50`
- `0x18003b51c`
- `0x180054010`

## import_xrefs

- `msvcrt!malloc` at `0x1800048db`
- `msvcrt!malloc` at `0x1800048db`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004998`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004998`
- `OLEAUT32!__imp_VariantInit` at `0x180004933`
- `OLEAUT32!__imp_VariantInit` at `0x18000493d`
- `OLEAUT32!__imp_VariantInit` at `0x18000494a`
- `OLEAUT32!__imp_VariantInit` at `0x180004957`
- `OLEAUT32!__imp_VariantInit` at `0x180004964`
- `OLEAUT32!__imp_VariantInit` at `0x180004971`
- `OLEAUT32!__imp_VariantInit` at `0x180004933`
- `OLEAUT32!__imp_VariantInit` at `0x18000493d`
- `OLEAUT32!__imp_VariantInit` at `0x18000494a`
- `OLEAUT32!__imp_VariantInit` at `0x180004957`
- `OLEAUT32!__imp_VariantInit` at `0x180004964`
- `OLEAUT32!__imp_VariantInit` at `0x180004971`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<TaskServiceImpl>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  unsigned int v5; // esi
  char *v6; // rax
  char *v7; // rdi
  int v8; // eax
  bool v9; // sf
  signed __int32 j; // eax
  signed __int32 i; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-68h] BYREF
  char v14; // [rsp+28h] [rbp-60h]
  __int64 *v15; // [rsp+30h] [rbp-58h]
  __int64 v16; // [rsp+38h] [rbp-50h]
  __int64 v17; // [rsp+40h] [rbp-48h]
  int v18; // [rsp+48h] [rbp-40h]
  __int64 v19; // [rsp+4Ch] [rbp-3Ch]
  char *v20; // [rsp+90h] [rbp+8h]
  __int64 v21; // [rsp+98h] [rbp+10h]
  _QWORD *v22; // [rsp+A0h] [rbp+18h]

  v3 = a3;
  if ( a3 )
  {
    v5 = 0;
    *a3 = 0;
    v6 = (char *)malloc(0x148u);
    v7 = v6;
    if ( !v6 )
    {
      try
      {
        v14 = 0;
        v15 = &qword_180077320;
        v16 = 0;
        v17 = 0;
        v18 = 14;
        v19 = -1;
        pExceptionObject = &wmi::GenericException::`vftable';
        throw (wmi::OutOfMemoryException *)&pExceptionObject;
      }
      catch ( ... )
      {
        v5 = -2147024882;
        v7 = v20;
        if ( !v20 )
          return v5;
        v5 = 0;
        v3 = v22;
        a2 = v21;
LABEL_15:
        for ( i = *((_DWORD *)v7 + 8); i != 0x7FFFFFFF; i = *((_DWORD *)v7 + 8) )
        {
          if ( i == _InterlockedCompareExchange((volatile signed __int32 *)v7 + 8, i + 1, i) )
            break;
        }
        v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v7 + 1);
        v9 = v8 < 0;
        if ( v8 >= 0 )
        {
          v7[80] = 1;
          v8 = 0;
          v9 = 0;
        }
        if ( v9 )
          v5 = v8;
        for ( j = *((_DWORD *)v7 + 8); j != 0x7FFFFFFF; j = *((_DWORD *)v7 + 8) )
        {
          if ( j == _InterlockedCompareExchange((volatile signed __int32 *)v7 + 8, j - 1, j) )
            break;
        }
        if ( v5 || (v5 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v7)(v7, a2, v3)) != 0 )
          (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 128LL))(v7, 1);
        return v5;
      }
    }
    *((_DWORD *)v6 + 8) = 0;
    *(_OWORD *)(v6 + 40) = 0;
    *(_OWORD *)(v6 + 56) = 0;
    *((_QWORD *)v6 + 9) = 0;
    v6[80] = 0;
    *(_QWORD *)v6 = &TaskServiceImpl::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 1) = &TaskServiceImpl::`vftable'{for `ITaskSchedulerEx2'};
    *((_QWORD *)v6 + 2) = &TaskServiceImpl::`vftable'{for `IMaintenanceScheduler'};
    *((_QWORD *)v6 + 3) = &TaskServiceImpl::`vftable'{for `ISupportErrorInfo'};
    VariantInit((VARIANTARG *)(v6 + 88));
    VariantInit((VARIANTARG *)(v7 + 112));
    VariantInit((VARIANTARG *)(v7 + 136));
    VariantInit((VARIANTARG *)(v7 + 160));
    VariantInit((VARIANTARG *)(v7 + 184));
    VariantInit((VARIANTARG *)(v7 + 208));
    *((_QWORD *)v7 + 30) = 0;
    *((_QWORD *)v7 + 31) = 0;
    *((_QWORD *)v7 + 32) = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v7 + 264), 0, 0);
    *((_QWORD *)v7 + 38) = 0;
    *((_QWORD *)v7 + 39) = 0;
    *((_QWORD *)v7 + 40) = 0;
    *((_DWORD *)v7 + 59) = 1128944457;
    *((_WORD *)v7 + 116) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<TaskServiceImpl>::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 1) = &ATL::CComObject<TaskServiceImpl>::`vftable'{for `ITaskSchedulerEx2'};
    *((_QWORD *)v7 + 2) = &ATL::CComObject<TaskServiceImpl>::`vftable'{for `IMaintenanceScheduler'};
    *((_QWORD *)v7 + 3) = &ATL::CComObject<TaskServiceImpl>::`vftable'{for `ISupportErrorInfo'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    goto LABEL_15;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800048a0  mov     [rsp+arg_10], r8
0x1800048a5  mov     [rsp+arg_8], rdx
0x1800048aa  mov     [rsp+arg_0], rcx
0x1800048af  push    rbx
0x1800048b0  push    rsi
0x1800048b1  push    rdi
0x1800048b2  push    r14
0x1800048b4  push    r15
0x1800048b6  sub     rsp, 60h
0x1800048ba  mov     r14, r8
0x1800048bd  mov     r15, rdx
0x1800048c0  test    r8, r8
0x1800048c3  jz      loc_180004AB5
0x1800048c9  xor     esi, esi
0x1800048cb  mov     [r8], rsi
0x1800048ce  mov     [rsp+88h+arg_0], rsi
0x1800048d6  mov     ecx, 148h; Size
0x1800048db  call    cs:__imp_malloc
0x1800048e1  mov     rdi, rax
0x1800048e4  test    rax, rax
0x1800048e7  jz      loc_180004ABC
0x1800048ed  mov     [rax+20h], esi
0x1800048f0  xorps   xmm0, xmm0
0x1800048f3  xor     eax, eax
0x1800048f5  movups  xmmword ptr [rdi+28h], xmm0
0x1800048f9  movups  xmmword ptr [rdi+38h], xmm0
0x1800048fd  mov     [rdi+48h], rax
0x180004901  mov     [rdi+50h], al
0x180004904  lea     rax, ??_7TaskServiceImpl@@6B?$IDispatchImpl@UITaskService@@$1?_GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85@@3U__s_GUID@@B$1?LIBID_TaskScheduler@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const TaskServiceImpl::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'}
0x18000490b  mov     [rdi], rax
0x18000490e  lea     rax, ??_7TaskServiceImpl@@6BITaskSchedulerEx2@@@; const TaskServiceImpl::`vftable'{for `ITaskSchedulerEx2'}
0x180004915  mov     [rdi+8], rax
0x180004919  lea     rax, ??_7TaskServiceImpl@@6BIMaintenanceScheduler@@@; const TaskServiceImpl::`vftable'{for `IMaintenanceScheduler'}
0x180004920  mov     [rdi+10h], rax
0x180004924  lea     rax, ??_7TaskServiceImpl@@6BISupportErrorInfo@@@; const TaskServiceImpl::`vftable'{for `ISupportErrorInfo'}
0x18000492b  mov     [rdi+18h], rax
0x18000492f  lea     rcx, [rdi+58h]; pvarg
0x180004933  call    cs:__imp_VariantInit
0x180004939  lea     rcx, [rdi+70h]; pvarg
0x18000493d  call    cs:__imp_VariantInit
0x180004943  lea     rcx, [rdi+88h]; pvarg
0x18000494a  call    cs:__imp_VariantInit
0x180004950  lea     rcx, [rdi+0A0h]; pvarg
0x180004957  call    cs:__imp_VariantInit
0x18000495d  lea     rcx, [rdi+0B8h]; pvarg
0x180004964  call    cs:__imp_VariantInit
0x18000496a  lea     rcx, [rdi+0D0h]; pvarg
0x180004971  call    cs:__imp_VariantInit
0x180004977  mov     [rdi+0F0h], rsi
0x18000497e  mov     [rdi+0F8h], rsi
0x180004985  mov     [rdi+100h], rsi
0x18000498c  lea     rcx, [rdi+108h]; lpCriticalSection
0x180004993  xor     r8d, r8d; Flags
0x180004996  xor     edx, edx; dwSpinCount
0x180004998  call    cs:__imp_InitializeCriticalSectionEx
0x18000499e  mov     [rdi+130h], rsi
0x1800049a5  mov     [rdi+138h], rsi
0x1800049ac  mov     [rdi+140h], rsi
0x1800049b3  mov     dword ptr [rdi+0ECh], 434A5349h
0x1800049bd  mov     [rdi+0E8h], si
0x1800049c4  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6B?$IDispatchImpl@UITaskService@@$1?_GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85@@3U__s_GUID@@B$1?LIBID_TaskScheduler@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'}
0x1800049cb  mov     [rdi], rax
0x1800049ce  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BITaskSchedulerEx2@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ITaskSchedulerEx2'}
0x1800049d5  mov     [rdi+8], rax
0x1800049d9  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BIMaintenanceScheduler@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `IMaintenanceScheduler'}
0x1800049e0  mov     [rdi+10h], rax
0x1800049e4  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ISupportErrorInfo'}
0x1800049eb  mov     [rdi+18h], rax
0x1800049ef  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800049f6  mov     rax, [rcx]
0x1800049f9  mov     rax, [rax+8]
0x1800049fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a02  mov     [rsp+88h+arg_0], rdi
0x180004a0a  jmp     short loc_180004A8A
0x180004a0c  lea     rcx, [rdi+28h]; this
0x180004a10  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004a15  test    eax, eax
0x180004a17  js      short loc_180004A21
0x180004a19  mov     byte ptr [rdi+50h], 1
0x180004a1d  mov     eax, esi
0x180004a1f  test    eax, eax
0x180004a21  cmovs   esi, eax
0x180004a24  mov     eax, [rdi+20h]
0x180004a27  cmp     eax, 7FFFFFFFh
0x180004a2c  jz      short loc_180004A44
0x180004a2e  xchg    ax, ax
0x180004a30  lea     ecx, [rax-1]
0x180004a33  lock cmpxchg [rdi+20h], ecx
0x180004a38  jz      short loc_180004A44
0x180004a3a  mov     eax, [rdi+20h]
0x180004a3d  cmp     eax, 7FFFFFFFh
0x180004a42  jnz     short loc_180004A30
0x180004a44  test    esi, esi
0x180004a46  jnz     loc_180004B21
0x180004a4c  mov     rax, [rdi]
0x180004a4f  mov     r8, r14
0x180004a52  mov     rdx, r15
0x180004a55  mov     rcx, rdi
0x180004a58  mov     rax, [rax]
0x180004a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a60  mov     esi, eax
0x180004a62  test    eax, eax
0x180004a64  jnz     loc_180004B21
0x180004a6a  mov     eax, esi
0x180004a6c  add     rsp, 60h
0x180004a70  pop     r15
0x180004a72  pop     r14
0x180004a74  pop     rdi
0x180004a75  pop     rsi
0x180004a76  pop     rbx
0x180004a77  retn
0x180004a78  xor     esi, esi
0x180004a7a  mov     r14, [rsp+88h+arg_10]
0x180004a82  mov     r15, [rsp+88h+arg_8]
0x180004a8a  mov     eax, [rdi+20h]
0x180004a8d  cmp     eax, 7FFFFFFFh
0x180004a92  jz      loc_180004A0C
0x180004a98  lea     ecx, [rax+1]
0x180004a9b  lock cmpxchg [rdi+20h], ecx
0x180004aa0  jz      loc_180004A0C
0x180004aa6  mov     eax, [rdi+20h]
0x180004aa9  cmp     eax, 7FFFFFFFh
0x180004aae  jnz     short loc_180004A98
0x180004ab0  jmp     loc_180004A0C
0x180004ab5  mov     eax, 80004003h
0x180004aba  jmp     short loc_180004A6C
0x180004abc  mov     [rsp+88h+var_60], 0
0x180004ac1  lea     rax, qword_180077320
0x180004ac8  mov     [rsp+88h+var_58], rax
0x180004acd  mov     [rsp+88h+var_50], rsi
0x180004ad2  mov     [rsp+88h+var_48], rsi
0x180004ad7  mov     [rsp+88h+var_40], 0Eh
0x180004adf  mov     [rsp+88h+var_3C], 0FFFFFFFFFFFFFFFFh
0x180004ae8  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004aef  mov     [rsp+88h+pExceptionObject], rax
0x180004af4  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180004afb  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180004b00  call    _CxxThrowException_0
0x180004b06  mov     esi, 8007000Eh
0x180004b0b  mov     rdi, [rsp+88h+arg_0]
0x180004b13  test    rdi, rdi
0x180004b16  jnz     loc_180004A78
0x180004b1c  jmp     loc_180004A6A
0x180004b21  mov     rdx, [rdi]
0x180004b24  mov     rax, [rdx+80h]
0x180004b2b  mov     edx, 1
0x180004b30  mov     rcx, rdi
0x180004b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b38  jmp     loc_180004A6A
```
