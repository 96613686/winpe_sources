# ATL::CComCreator<ATL::CComObject<TaskServiceImpl>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004b50`
- end: `0x180004e1e`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VTaskServiceImpl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `718`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180004b20`

## callees

- `0x180004b50`
- `0x180004e30`
- `0x18003e88c`
- `0x180058010`

## import_xrefs

- `msvcrt!malloc` at `0x180004b8b`
- `msvcrt!malloc` at `0x180004b8b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004c72`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180004c72`
- `OLEAUT32!__imp_VariantInit` at `0x180004be9`
- `OLEAUT32!__imp_VariantInit` at `0x180004bf9`
- `OLEAUT32!__imp_VariantInit` at `0x180004c0c`
- `OLEAUT32!__imp_VariantInit` at `0x180004c1f`
- `OLEAUT32!__imp_VariantInit` at `0x180004c32`
- `OLEAUT32!__imp_VariantInit` at `0x180004c45`
- `OLEAUT32!__imp_VariantInit` at `0x180004be9`
- `OLEAUT32!__imp_VariantInit` at `0x180004bf9`
- `OLEAUT32!__imp_VariantInit` at `0x180004c0c`
- `OLEAUT32!__imp_VariantInit` at `0x180004c1f`
- `OLEAUT32!__imp_VariantInit` at `0x180004c32`
- `OLEAUT32!__imp_VariantInit` at `0x180004c45`

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
        v15 = &qword_18007B2F0;
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
0x180004b50  mov     [rsp+arg_10], r8
0x180004b55  mov     [rsp+arg_8], rdx
0x180004b5a  mov     [rsp+arg_0], rcx
0x180004b5f  push    rbx
0x180004b60  push    rsi
0x180004b61  push    rdi
0x180004b62  push    r14
0x180004b64  push    r15
0x180004b66  sub     rsp, 60h
0x180004b6a  mov     r14, r8
0x180004b6d  mov     r15, rdx
0x180004b70  test    r8, r8
0x180004b73  jz      loc_180004D96
0x180004b79  xor     esi, esi
0x180004b7b  mov     [r8], rsi
0x180004b7e  mov     [rsp+88h+arg_0], rsi
0x180004b86  mov     ecx, 148h; Size
0x180004b8b  call    cs:__imp_malloc
0x180004b92  nop     dword ptr [rax+rax+00h]
0x180004b97  mov     rdi, rax
0x180004b9a  test    rax, rax
0x180004b9d  jz      loc_180004D9D
0x180004ba3  mov     [rax+20h], esi
0x180004ba6  xorps   xmm0, xmm0
0x180004ba9  xor     eax, eax
0x180004bab  movups  xmmword ptr [rdi+28h], xmm0
0x180004baf  movups  xmmword ptr [rdi+38h], xmm0
0x180004bb3  mov     [rdi+48h], rax
0x180004bb7  mov     [rdi+50h], al
0x180004bba  lea     rax, ??_7TaskServiceImpl@@6B?$IDispatchImpl@UITaskService@@$1?_GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85@@3U__s_GUID@@B$1?LIBID_TaskScheduler@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const TaskServiceImpl::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'}
0x180004bc1  mov     [rdi], rax
0x180004bc4  lea     rax, ??_7TaskServiceImpl@@6BITaskSchedulerEx2@@@; const TaskServiceImpl::`vftable'{for `ITaskSchedulerEx2'}
0x180004bcb  mov     [rdi+8], rax
0x180004bcf  lea     rax, ??_7TaskServiceImpl@@6BIMaintenanceScheduler@@@; const TaskServiceImpl::`vftable'{for `IMaintenanceScheduler'}
0x180004bd6  mov     [rdi+10h], rax
0x180004bda  lea     rax, ??_7TaskServiceImpl@@6BISupportErrorInfo@@@; const TaskServiceImpl::`vftable'{for `ISupportErrorInfo'}
0x180004be1  mov     [rdi+18h], rax
0x180004be5  lea     rcx, [rdi+58h]; pvarg
0x180004be9  call    cs:__imp_VariantInit
0x180004bf0  nop     dword ptr [rax+rax+00h]
0x180004bf5  lea     rcx, [rdi+70h]; pvarg
0x180004bf9  call    cs:__imp_VariantInit
0x180004c00  nop     dword ptr [rax+rax+00h]
0x180004c05  lea     rcx, [rdi+88h]; pvarg
0x180004c0c  call    cs:__imp_VariantInit
0x180004c13  nop     dword ptr [rax+rax+00h]
0x180004c18  lea     rcx, [rdi+0A0h]; pvarg
0x180004c1f  call    cs:__imp_VariantInit
0x180004c26  nop     dword ptr [rax+rax+00h]
0x180004c2b  lea     rcx, [rdi+0B8h]; pvarg
0x180004c32  call    cs:__imp_VariantInit
0x180004c39  nop     dword ptr [rax+rax+00h]
0x180004c3e  lea     rcx, [rdi+0D0h]; pvarg
0x180004c45  call    cs:__imp_VariantInit
0x180004c4c  nop     dword ptr [rax+rax+00h]
0x180004c51  mov     [rdi+0F0h], rsi
0x180004c58  mov     [rdi+0F8h], rsi
0x180004c5f  mov     [rdi+100h], rsi
0x180004c66  lea     rcx, [rdi+108h]; lpCriticalSection
0x180004c6d  xor     r8d, r8d; Flags
0x180004c70  xor     edx, edx; dwSpinCount
0x180004c72  call    cs:__imp_InitializeCriticalSectionEx
0x180004c79  nop     dword ptr [rax+rax+00h]
0x180004c7e  mov     [rdi+130h], rsi
0x180004c85  mov     [rdi+138h], rsi
0x180004c8c  mov     [rdi+140h], rsi
0x180004c93  mov     dword ptr [rdi+0ECh], 434A5349h
0x180004c9d  mov     [rdi+0E8h], si
0x180004ca4  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6B?$IDispatchImpl@UITaskService@@$1?_GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85@@3U__s_GUID@@B$1?LIBID_TaskScheduler@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ATL::IDispatchImpl<ITaskService,&__s_GUID const _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,&_GUID const LIBID_TaskScheduler,1,0,ATL::CComTypeInfoHolder>'}
0x180004cab  mov     [rdi], rax
0x180004cae  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BITaskSchedulerEx2@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ITaskSchedulerEx2'}
0x180004cb5  mov     [rdi+8], rax
0x180004cb9  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BIMaintenanceScheduler@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `IMaintenanceScheduler'}
0x180004cc0  mov     [rdi+10h], rax
0x180004cc4  lea     rax, ??_7?$CComObject@VTaskServiceImpl@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<TaskServiceImpl>::`vftable'{for `ISupportErrorInfo'}
0x180004ccb  mov     [rdi+18h], rax
0x180004ccf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004cd6  mov     rax, [rcx]
0x180004cd9  mov     rax, [rax+8]
0x180004cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce2  mov     [rsp+88h+arg_0], rdi
0x180004cea  jmp     short loc_180004D6B
0x180004cec  lea     rcx, [rdi+28h]; this
0x180004cf0  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004cf5  test    eax, eax
0x180004cf7  js      short loc_180004D01
0x180004cf9  mov     byte ptr [rdi+50h], 1
0x180004cfd  mov     eax, esi
0x180004cff  test    eax, eax
0x180004d01  cmovs   esi, eax
0x180004d04  mov     eax, [rdi+20h]
0x180004d07  cmp     eax, 7FFFFFFFh
0x180004d0c  jz      short loc_180004D24
0x180004d0e  xchg    ax, ax
0x180004d10  lea     ecx, [rax-1]
0x180004d13  lock cmpxchg [rdi+20h], ecx
0x180004d18  jz      short loc_180004D24
0x180004d1a  mov     eax, [rdi+20h]
0x180004d1d  cmp     eax, 7FFFFFFFh
0x180004d22  jnz     short loc_180004D10
0x180004d24  test    esi, esi
0x180004d26  jnz     loc_180004E02
0x180004d2c  mov     rax, [rdi]
0x180004d2f  mov     r8, r14
0x180004d32  mov     rdx, r15
0x180004d35  mov     rcx, rdi
0x180004d38  mov     rax, [rax]
0x180004d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d40  mov     esi, eax
0x180004d42  test    eax, eax
0x180004d44  jnz     loc_180004E02
0x180004d4a  mov     eax, esi
0x180004d4c  add     rsp, 60h
0x180004d50  pop     r15
0x180004d52  pop     r14
0x180004d54  pop     rdi
0x180004d55  pop     rsi
0x180004d56  pop     rbx
0x180004d57  retn
0x180004d59  xor     esi, esi
0x180004d5b  mov     r14, [rsp+88h+arg_10]
0x180004d63  mov     r15, [rsp+88h+arg_8]
0x180004d6b  mov     eax, [rdi+20h]
0x180004d6e  cmp     eax, 7FFFFFFFh
0x180004d73  jz      loc_180004CEC
0x180004d79  lea     ecx, [rax+1]
0x180004d7c  lock cmpxchg [rdi+20h], ecx
0x180004d81  jz      loc_180004CEC
0x180004d87  mov     eax, [rdi+20h]
0x180004d8a  cmp     eax, 7FFFFFFFh
0x180004d8f  jnz     short loc_180004D79
0x180004d91  jmp     loc_180004CEC
0x180004d96  mov     eax, 80004003h
0x180004d9b  jmp     short loc_180004D4C
0x180004d9d  mov     [rsp+88h+var_60], 0
0x180004da2  lea     rax, qword_18007B2F0
0x180004da9  mov     [rsp+88h+var_58], rax
0x180004dae  mov     [rsp+88h+var_50], rsi
0x180004db3  mov     [rsp+88h+var_48], rsi
0x180004db8  mov     [rsp+88h+var_40], 0Eh
0x180004dc0  mov     [rsp+88h+var_3C], 0FFFFFFFFFFFFFFFFh
0x180004dc9  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180004dd0  mov     [rsp+88h+pExceptionObject], rax
0x180004dd5  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180004ddc  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180004de1  call    _CxxThrowException_0
0x180004de7  mov     esi, 8007000Eh
0x180004dec  mov     rdi, [rsp+88h+arg_0]
0x180004df4  test    rdi, rdi
0x180004df7  jnz     loc_180004D59
0x180004dfd  jmp     loc_180004D4A
0x180004e02  mov     rdx, [rdi]
0x180004e05  mov     rax, [rdx+80h]
0x180004e0c  mov     edx, 1
0x180004e11  mov     rcx, rdi
0x180004e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e19  jmp     loc_180004D4A
```
