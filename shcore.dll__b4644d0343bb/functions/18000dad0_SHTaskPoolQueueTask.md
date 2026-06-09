# SHTaskPoolQueueTask

- ea: `0x18000dad0`
- end: `0x18000ddce`
- name: `SHTaskPoolQueueTask`
- size: `766`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, APTTYPE pAptType)`
- caller_count: `8`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d9b0`
- `0x18000da84`
- `0x180026154`
- `0x1800282f4`
- `0x18003d264`
- `0x18006507c`
- `0x1800712f4`
- `0x180091e38`

## callees

- `0x180008760`
- `0x18000dad0`
- `0x18000ddd4`
- `0x18000de00`
- `0x18000debc`
- `0x18000e2bc`
- `0x18000e308`
- `0x180053bd8`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000dbf9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000dcfa`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000dbf9`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000dcfa`

## string_xrefs

- `0x18000db72`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000db85`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000dcc5`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000dd25`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000dd7c`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000dda7`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SHTaskPoolQueueTask(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        _QWORD *pAptType)
{
  unsigned int v9; // ebx
  __int64 v10; // rdi
  unsigned int v11; // esi
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v15; // rcx
  HRESULT ApartmentType; // eax
  unsigned int v17; // ebx
  int v18; // eax
  unsigned int v19; // edi
  _DWORD *TaskPoolThreadData; // rax
  int v21; // ecx
  __int64 v22; // rcx
  int v23; // [rsp+20h] [rbp-28h]
  int v24; // [rsp+20h] [rbp-28h]
  APTTYPEQUALIFIER pAptQualifier; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v26[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]

  v9 = a1;
  if ( pAptType )
    *pAptType = 0;
  v10 = a5;
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x677,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)0x8007000ELL,
      v23);
    return 2147942414LL;
  }
  v26[0] = 0;
  switch ( a1 )
  {
    case 5u:
      v9 = 1;
      break;
    case 6u:
      LODWORD(pAptType) = 0;
      pAptQualifier = APTTYPEQUALIFIER_NONE;
      if ( CoGetApartmentType((APTTYPE *)&pAptType, &pAptQualifier) >= 0 && (_DWORD)pAptType && (_DWORD)pAptType != 3 )
        goto LABEL_14;
      v9 = 0;
      break;
    case 4u:
LABEL_14:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
LABEL_15:
      v15 = v26[0];
      if ( v26[0] )
      {
        v26[0] = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return 0;
    default:
      break;
  }
  if ( (a2 & 0x80u) != 0 )
  {
    TaskPoolThreadData = (_DWORD *)GetTaskPoolThreadData();
    if ( TaskPoolThreadData )
    {
      if ( *TaskPoolThreadData != 0x7FFFFFFF )
      {
        v21 = *TaskPoolThreadData - 1;
        if ( (v21 & 0x800000) != 0
          && (v9 == 3 || v9 == v21 >> 24)
          && (((unsigned __int8)a2 ^ (unsigned __int8)v21) & 0xB) == 0 )
        {
          goto LABEL_14;
        }
      }
    }
  }
  v11 = AdjustTaskPriorityOptions(a2);
  if ( v9 == 3 )
  {
    v9 = 0;
    goto LABEL_10;
  }
  if ( v9 != 2 )
  {
LABEL_10:
    if ( a4 )
    {
      v23 = v10;
      v12 = WorkThreadManager::s_QueueDelayedTask(v9, v11, a3, a4);
      if ( v12 >= 0 )
        goto LABEL_15;
      v13 = 234;
    }
    else
    {
      v12 = WorkThreadManager::s_QueuePoolTask(v9, v11, a3, v10);
      if ( v12 >= 0 )
        goto LABEL_15;
      v13 = 238;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)v12,
      v23);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A1,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)(unsigned int)v12,
      v24);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v26);
    return (unsigned int)v12;
  }
  LODWORD(pAptType) = 0;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType((APTTYPE *)&pAptType, &pAptQualifier);
  v17 = ApartmentType;
  if ( ApartmentType >= 0 )
  {
    v9 = 0;
    if ( (_DWORD)pAptType == 3 || !(_DWORD)pAptType )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v26);
      v18 = Microsoft::WRL::Details::MakeAndInitialize<CRemoteTask,Windows::Internal::IComPoolTask,Windows::Internal::IComPoolTask * &>(
              v26,
              &a5);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x695,
          (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
          (const char *)(unsigned int)v18,
          v23);
        Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v26);
        return v19;
      }
      LODWORD(v10) = v26[0];
    }
    else if ( (unsigned int)((_DWORD)pAptType - 1) >= 2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69C,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)0x8000FFFFLL,
        v23);
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(v26);
      return 2147549183LL;
    }
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x68E,
    (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
    (const char *)(unsigned int)ApartmentType,
    v23);
  v22 = v26[0];
  if ( v26[0] )
  {
    v26[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return v17;
}

```

## disassembly

```asm
0x18000dad0  push    rbp
0x18000dad2  push    rbx
0x18000dad3  push    rsi
0x18000dad4  push    rdi
0x18000dad5  push    r12
0x18000dad7  push    r13
0x18000dad9  push    r14
0x18000dadb  push    r15
0x18000dadd  mov     rbp, rsp
0x18000dae0  sub     rsp, 48h
0x18000dae4  mov     r14d, r9d
0x18000dae7  mov     r12d, r8d
0x18000daea  mov     esi, edx
0x18000daec  mov     ebx, ecx
0x18000daee  xor     r13d, r13d
0x18000daf1  mov     r15, [rbp+pAptType]
0x18000daf5  test    r15, r15
0x18000daf8  jnz     loc_18000DC83
0x18000dafe  mov     rdi, [rbp+arg_20]
0x18000db02  test    rdi, rdi
0x18000db05  jz      loc_18000DCBB
0x18000db0b  mov     [rbp+var_10], r13
0x18000db0f  cmp     ecx, 5
0x18000db12  jz      loc_18000DC8B
0x18000db18  cmp     ecx, 6
0x18000db1b  jz      loc_18000DCEA
0x18000db21  cmp     ecx, 4
0x18000db24  jz      short loc_18000DBA3
0x18000db26  test    sil, sil
0x18000db29  js      loc_18000DC41
0x18000db2f  mov     ecx, esi
0x18000db31  call    AdjustTaskPriorityOptions
0x18000db36  mov     esi, eax
0x18000db38  cmp     ebx, 3
0x18000db3b  jnz     loc_18000DBE0
0x18000db41  mov     ebx, r13d
0x18000db44  mov     r8d, r12d
0x18000db47  mov     edx, esi
0x18000db49  mov     ecx, ebx
0x18000db4b  test    r14d, r14d
0x18000db4e  jnz     loc_18000DC95
0x18000db54  mov     r9, rdi
0x18000db57  call    ?s_QueuePoolTask@WorkThreadManager@@CAJW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAUIComPoolTask@34@@Z; WorkThreadManager::s_QueuePoolTask(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,Windows::Internal::IComPoolTask *)
0x18000db5c  mov     ebx, eax
0x18000db5e  test    eax, eax
0x18000db60  jns     loc_18000DDC8
0x18000db66  mov     edx, 0EEh; void *
0x18000db6b  mov     r9d, ebx; char *
0x18000db6e  mov     rcx, [rbp+40h]; this
0x18000db72  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000db79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db7e  mov     rcx, [rbp+40h]; this
0x18000db82  mov     r9d, ebx; char *
0x18000db85  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000db8c  mov     edx, 6A1h; void *
0x18000db91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db96  lea     rcx, [rbp+var_10]
0x18000db9a  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18000db9f  mov     eax, ebx
0x18000dba1  jmp     short loc_18000DBCF
0x18000dba3  mov     rax, [rdi]
0x18000dba6  mov     rcx, rdi
0x18000dba9  mov     rax, [rax+18h]
0x18000dbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbb2  nop
0x18000dbb3  mov     rcx, [rbp+var_10]
0x18000dbb7  test    rcx, rcx
0x18000dbba  jz      short loc_18000DBCD
0x18000dbbc  mov     [rbp+var_10], r13
0x18000dbc0  mov     rax, [rcx]
0x18000dbc3  mov     rax, [rax+10h]
0x18000dbc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbcc  nop
0x18000dbcd  xor     eax, eax
0x18000dbcf  add     rsp, 48h
0x18000dbd3  pop     r15
0x18000dbd5  pop     r14
0x18000dbd7  pop     r13
0x18000dbd9  pop     r12
0x18000dbdb  pop     rdi
0x18000dbdc  pop     rsi
0x18000dbdd  pop     rbx
0x18000dbde  pop     rbp
0x18000dbdf  retn
0x18000dbe0  cmp     ebx, 2
0x18000dbe3  jnz     loc_18000DB44
0x18000dbe9  mov     dword ptr [rbp+pAptType], r13d
0x18000dbed  mov     [rbp+pAptQualifier], r13d
0x18000dbf1  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x18000dbf5  lea     rcx, [rbp+pAptType]; pAptType
0x18000dbf9  call    cs:__imp_CoGetApartmentType
0x18000dbff  mov     ebx, eax
0x18000dc01  test    eax, eax
0x18000dc03  js      loc_18000DD1E
0x18000dc09  mov     ebx, r13d
0x18000dc0c  mov     ecx, dword ptr [rbp+pAptType]
0x18000dc0f  cmp     ecx, 3
0x18000dc12  jnz     loc_18000DD58
0x18000dc18  lea     rcx, [rbp+var_10]
0x18000dc1c  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18000dc21  lea     rdx, [rbp+arg_20]
0x18000dc25  lea     rcx, [rbp+var_10]
0x18000dc29  call    ??$MakeAndInitialize@VCRemoteTask@@UIComPoolTask@Internal@Windows@@AEAPEAU234@@Details@WRL@Microsoft@@YAJPEAPEAUIComPoolTask@Internal@Windows@@AEAPEAU345@@Z; Microsoft::WRL::Details::MakeAndInitialize<CRemoteTask,Windows::Internal::IComPoolTask,Windows::Internal::IComPoolTask * &>(Windows::Internal::IComPoolTask * *,Windows::Internal::IComPoolTask * &)
0x18000dc2e  mov     edi, eax
0x18000dc30  test    eax, eax
0x18000dc32  js      loc_18000DDA0
0x18000dc38  mov     rdi, [rbp+var_10]
0x18000dc3c  jmp     loc_18000DB44
0x18000dc41  call    GetTaskPoolThreadData
0x18000dc46  test    rax, rax
0x18000dc49  jz      loc_18000DB2F
0x18000dc4f  mov     ecx, [rax]
0x18000dc51  cmp     ecx, 7FFFFFFFh
0x18000dc57  jz      loc_18000DB2F
0x18000dc5d  dec     ecx
0x18000dc5f  bt      ecx, 17h
0x18000dc63  jnb     loc_18000DB2F
0x18000dc69  mov     eax, ecx
0x18000dc6b  sar     eax, 18h
0x18000dc6e  cmp     ebx, 3
0x18000dc71  jnz     short loc_18000DCE0
0x18000dc73  xor     ecx, esi
0x18000dc75  test    cl, 0Bh
0x18000dc78  jnz     loc_18000DB2F
0x18000dc7e  jmp     loc_18000DBA3
0x18000dc83  mov     [r15], r13
0x18000dc86  jmp     loc_18000DAFE
0x18000dc8b  mov     ebx, 1
0x18000dc90  jmp     loc_18000DB26
0x18000dc95  mov     [rsp+48h+var_20], r15
0x18000dc9a  mov     [rsp+48h+var_28], rdi
0x18000dc9f  mov     r9d, r14d
0x18000dca2  call    ?s_QueueDelayedTask@WorkThreadManager@@CAJW4TaskApartment@Internal@Windows@@W4TaskOptions@34@KKPEAUIComPoolTask@34@PEAPEAUIUnknown@@@Z; WorkThreadManager::s_QueueDelayedTask(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,ulong,Windows::Internal::IComPoolTask *,IUnknown * *)
0x18000dca7  mov     ebx, eax
0x18000dca9  test    eax, eax
0x18000dcab  jns     loc_18000DDC8
0x18000dcb1  mov     edx, 0EAh
0x18000dcb6  jmp     loc_18000DB6B
0x18000dcbb  mov     rcx, [rbp+40h]; this
0x18000dcbf  mov     r9d, 8007000Eh; char *
0x18000dcc5  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000dccc  mov     edx, 677h; void *
0x18000dcd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcd6  mov     eax, 8007000Eh
0x18000dcdb  jmp     loc_18000DBCF
0x18000dce0  cmp     ebx, eax
0x18000dce2  jnz     loc_18000DB2F
0x18000dce8  jmp     short loc_18000DC73
0x18000dcea  mov     dword ptr [rbp+pAptType], r13d
0x18000dcee  mov     [rbp+pAptQualifier], r13d
0x18000dcf2  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x18000dcf6  lea     rcx, [rbp+pAptType]; pAptType
0x18000dcfa  call    cs:__imp_CoGetApartmentType
0x18000dd00  test    eax, eax
0x18000dd02  jns     short loc_18000DD0C
0x18000dd04  mov     ebx, r13d
0x18000dd07  jmp     loc_18000DB26
0x18000dd0c  mov     eax, dword ptr [rbp+pAptType]
0x18000dd0f  test    eax, eax
0x18000dd11  jz      short loc_18000DD04
0x18000dd13  cmp     eax, 3
0x18000dd16  jnz     loc_18000DBA3
0x18000dd1c  jmp     short loc_18000DD04
0x18000dd1e  mov     rcx, [rbp+40h]; this
0x18000dd22  mov     r9d, ebx; char *
0x18000dd25  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000dd2c  mov     edx, 68Eh; void *
0x18000dd31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd36  nop
0x18000dd37  mov     rcx, [rbp+var_10]
0x18000dd3b  test    rcx, rcx
0x18000dd3e  jz      short loc_18000DD51
0x18000dd40  mov     [rbp+var_10], r13
0x18000dd44  mov     rax, [rcx]
0x18000dd47  mov     rax, [rax+10h]
0x18000dd4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd50  nop
0x18000dd51  mov     eax, ebx
0x18000dd53  jmp     loc_18000DBCF
0x18000dd58  test    ecx, ecx
0x18000dd5a  jz      loc_18000DC18
0x18000dd60  sub     ecx, 1
0x18000dd63  jz      loc_18000DB44
0x18000dd69  cmp     ecx, 1
0x18000dd6c  jz      loc_18000DB44
0x18000dd72  mov     rcx, [rbp+40h]; this
0x18000dd76  mov     r9d, 8000FFFFh; char *
0x18000dd7c  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000dd83  mov     edx, 69Ch; void *
0x18000dd88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd8d  lea     rcx, [rbp+var_10]
0x18000dd91  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18000dd96  mov     eax, 8000FFFFh
0x18000dd9b  jmp     loc_18000DBCF
0x18000dda0  mov     rcx, [rbp+40h]; this
0x18000dda4  mov     r9d, edi; char *
0x18000dda7  lea     r8, aOnecoreShellSh_7; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000ddae  mov     edx, 695h; void *
0x18000ddb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddb8  lea     rcx, [rbp+var_10]
0x18000ddbc  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::InternalRelease(void)
0x18000ddc1  mov     eax, edi
0x18000ddc3  jmp     loc_18000DBCF
0x18000ddc8  jmp     loc_18000DBB3
```
