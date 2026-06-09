# NotificationServiceImpl::ConfigureBatching(__MIDL___MIDL_itf_wpntypes_0000_0000_0008,long)

- ea: `0x18006b5c0`
- end: `0x18006b922`
- name: `?ConfigureBatching@NotificationServiceImpl@@UEAAJW4__MIDL___MIDL_itf_wpntypes_0000_0000_0008@@J@Z`
- size: `866`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x1800687d4`
- `0x18006b000`
- `0x18006b5c0`
- `0x180075d18`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b64c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b661`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b846`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b64c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b661`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006b846`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b635`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b831`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b635`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006b831`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b8d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006b8d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b8c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006b8c4`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x18006b6a6`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x18006b6a6`

## string_xrefs

- `0x18006b685`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006b718`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006b7f6`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::ConfigureBatching(__int64 a1, unsigned int a2, int a3)
{
  PVOID v6; // rcx
  int v8; // eax
  int ConfigureBatching; // eax
  int v10; // edx
  int v11; // ecx
  int v12; // r9d
  void *v13; // r15
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  HANDLE ProcessHeap; // rax
  int v20; // [rsp+20h] [rbp-40h]
  LPVOID lpMem[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v23; // [rsp+A8h] [rbp+48h] BYREF
  __int64 RandomBuffer; // [rsp+B8h] [rbp+58h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  if ( a2 > 4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  lpMem[0] = 0;
  v23 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 264));
  if ( *(_DWORD *)(a1 + 260) == a2 )
  {
    if ( a1 != -264 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 264));
    return 0;
  }
  if ( a1 != -264 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 264));
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 112) + 144LL))(*(_QWORD *)(a1 + 112), a2);
  if ( v8 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x582,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)(unsigned int)v8,
      v20);
  RandomBuffer = 0;
  SystemFunction036(&RandomBuffer, 8u);
  ConfigureBatching = WNPMessageGenerator::GenerateConfigureBatching(*(_QWORD *)(a1 + 128), a2, RandomBuffer, lpMem);
  v13 = lpMem[0];
  v14 = ConfigureBatching;
  if ( ConfigureBatching < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        140,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)ConfigureBatching);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x588,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v14,
      (int)&v23);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_42;
    v16 = 141;
    goto LABEL_23;
  }
  if ( (byte_1800AFD82 & 0x10) != 0 )
    McTemplateU0qqbr1sxqbr5_EventWriteTransfer(v11, v10, a2, v12, (unsigned int)&v23);
  v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 near **, const char *, _QWORD))(**(_QWORD **)(a1 + 112) + 40LL))(
          *(_QWORD *)(a1 + 112),
          &WNPMessageGenerator::s_PutCommand,
          "OPTIONS",
          (unsigned int)v23);
  v14 = v17;
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v17);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x598,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v14,
      (int)v13);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_42;
    v16 = 143;
LABEL_23:
    WPP_SF_d(v15[2], v16, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
    goto LABEL_41;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 264));
  *(_DWORD *)(a1 + 260) = a2;
  if ( a1 != -264 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 264));
  v18 = NotificationServiceImpl::AddOutstandingRequest(a1, a1 + 160, 1000, 0, a3, 6);
  v14 = v18;
  if ( v18 < 0 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      144,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)v18);
  }
LABEL_41:
  v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_42:
  if ( v13 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 6u )
    WPP_SF_d(v15[2], 145, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18006b5c0  mov     [rsp-38h+arg_10], rbx
0x18006b5c5  push    rbp
0x18006b5c6  push    rsi
0x18006b5c7  push    rdi
0x18006b5c8  push    r12
0x18006b5ca  push    r13
0x18006b5cc  push    r14
0x18006b5ce  push    r15
0x18006b5d0  mov     rbp, rsp
0x18006b5d3  sub     rsp, 60h
0x18006b5d7  mov     r13d, r8d
0x18006b5da  mov     r14d, edx
0x18006b5dd  mov     rsi, rcx
0x18006b5e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b5e7  lea     rax, WPP_GLOBAL_Control
0x18006b5ee  cmp     rcx, rax
0x18006b5f1  jz      short loc_18006B614
0x18006b5f3  test    byte ptr [rcx+1Ch], 2
0x18006b5f7  jz      short loc_18006B614
0x18006b5f9  cmp     byte ptr [rcx+19h], 6
0x18006b5fd  jb      short loc_18006B614
0x18006b5ff  mov     rcx, [rcx+10h]
0x18006b603  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b60a  mov     edx, 8Bh
0x18006b60f  call    WPP_SF_
0x18006b614  cmp     r14d, 4
0x18006b618  jbe     short loc_18006B61F
0x18006b61a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006b61f  xor     ebx, ebx
0x18006b621  lea     rdi, [rsi+108h]
0x18006b628  mov     rcx, rdi; lpCriticalSection
0x18006b62b  mov     [rbp+lpMem], rbx
0x18006b62f  mov     [rbp+arg_8], ebx
0x18006b632  mov     [rbp+arg_0], ebx
0x18006b635  call    cs:__imp_EnterCriticalSection
0x18006b63b  cmp     [rsi+104h], r14d
0x18006b642  jnz     short loc_18006B659
0x18006b644  test    rdi, rdi
0x18006b647  jz      short loc_18006B652
0x18006b649  mov     rcx, rdi; lpCriticalSection
0x18006b64c  call    cs:__imp_LeaveCriticalSection
0x18006b652  xor     eax, eax
0x18006b654  jmp     loc_18006B90A
0x18006b659  test    rdi, rdi
0x18006b65c  jz      short loc_18006B667
0x18006b65e  mov     rcx, rdi; lpCriticalSection
0x18006b661  call    cs:__imp_LeaveCriticalSection
0x18006b667  mov     rcx, [rsi+70h]
0x18006b66b  mov     edx, r14d
0x18006b66e  mov     rax, [rcx]
0x18006b671  mov     rax, [rax+90h]
0x18006b678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b67d  test    eax, eax
0x18006b67f  jns     short loc_18006B699
0x18006b681  mov     rcx, [rbp+38h]; this
0x18006b685  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006b68c  mov     r9d, eax; char *
0x18006b68f  mov     edx, 582h; void *
0x18006b694  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006b699  mov     edx, 8; RandomBufferLength
0x18006b69e  mov     [rbp+RandomBuffer], rbx
0x18006b6a2  lea     rcx, [rbp+RandomBuffer]; RandomBuffer
0x18006b6a6  call    cs:__imp_SystemFunction036
0x18006b6ac  mov     r12, [rbp+RandomBuffer]
0x18006b6b0  lea     rax, [rbp+arg_8]
0x18006b6b4  mov     rcx, [rsi+80h]
0x18006b6bb  lea     r9, [rbp+lpMem]
0x18006b6bf  mov     r8, r12
0x18006b6c2  mov     qword ptr [rsp+60h+var_40], rax; int
0x18006b6c7  mov     edx, r14d
0x18006b6ca  call    ?GenerateConfigureBatching@WNPMessageGenerator@@QEAAJW4__MIDL___MIDL_itf_wpntypes_0000_0000_0008@@_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateConfigureBatching(__MIDL___MIDL_itf_wpntypes_0000_0000_0008,unsigned __int64,uchar * *,ulong *)
0x18006b6cf  mov     r15, [rbp+lpMem]
0x18006b6d3  mov     ebx, eax
0x18006b6d5  test    eax, eax
0x18006b6d7  jns     loc_18006B763
0x18006b6dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6e4  lea     rdi, WPP_GLOBAL_Control
0x18006b6eb  cmp     rcx, rdi
0x18006b6ee  jz      short loc_18006B714
0x18006b6f0  test    byte ptr [rcx+1Ch], 2
0x18006b6f4  jz      short loc_18006B714
0x18006b6f6  cmp     byte ptr [rcx+19h], 2
0x18006b6fa  jb      short loc_18006B714
0x18006b6fc  mov     rcx, [rcx+10h]
0x18006b700  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b707  mov     edx, 8Ch
0x18006b70c  mov     r9d, eax
0x18006b70f  call    WPP_SF_d
0x18006b714  mov     rcx, [rbp+38h]; this
0x18006b718  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006b71f  mov     r9d, ebx; char *
0x18006b722  mov     edx, 588h; void *
0x18006b727  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006b72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b733  cmp     rcx, rdi
0x18006b736  jz      loc_18006B8BF
0x18006b73c  test    byte ptr [rcx+1Ch], 80h
0x18006b740  jz      loc_18006B8BF
0x18006b746  mov     edx, 8Dh
0x18006b74b  mov     rcx, [rcx+10h]
0x18006b74f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b756  mov     r9d, ebx
0x18006b759  call    WPP_SF_d
0x18006b75e  jmp     loc_18006B8B8
0x18006b763  test    cs:byte_1800AFD82, 10h
0x18006b76a  jz      short loc_18006B785
0x18006b76c  mov     eax, [rbp+arg_8]
0x18006b76f  mov     r8d, r14d
0x18006b772  mov     [rsp+60h+var_20], r15
0x18006b777  mov     [rsp+60h+var_28], eax
0x18006b77b  mov     [rsp+60h+var_30], r12
0x18006b780  call    McTemplateU0qqbr1sxqbr5_EventWriteTransfer
0x18006b785  mov     rcx, [rsi+70h]
0x18006b789  lea     rdx, [rbp+arg_0]
0x18006b78d  mov     r9d, [rbp+arg_8]
0x18006b791  lea     r8, aOptions; "OPTIONS"
0x18006b798  mov     [rsp+60h+var_38], rdx
0x18006b79d  lea     rdx, ?s_PutCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_PutCommand
0x18006b7a4  mov     qword ptr [rsp+60h+var_40], r15; int
0x18006b7a9  mov     rax, [rcx]
0x18006b7ac  mov     rax, [rax+28h]
0x18006b7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b7b5  mov     ebx, eax
0x18006b7b7  test    eax, eax
0x18006b7b9  jns     short loc_18006B82E
0x18006b7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b7c2  lea     rdi, WPP_GLOBAL_Control
0x18006b7c9  cmp     rcx, rdi
0x18006b7cc  jz      short loc_18006B7F2
0x18006b7ce  test    byte ptr [rcx+1Ch], 2
0x18006b7d2  jz      short loc_18006B7F2
0x18006b7d4  cmp     byte ptr [rcx+19h], 2
0x18006b7d8  jb      short loc_18006B7F2
0x18006b7da  mov     rcx, [rcx+10h]
0x18006b7de  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b7e5  mov     edx, 8Eh
0x18006b7ea  mov     r9d, eax
0x18006b7ed  call    WPP_SF_d
0x18006b7f2  mov     rcx, [rbp+38h]; this
0x18006b7f6  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006b7fd  mov     r9d, ebx; char *
0x18006b800  mov     edx, 598h; void *
0x18006b805  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006b80a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b811  cmp     rcx, rdi
0x18006b814  jz      loc_18006B8BF
0x18006b81a  test    byte ptr [rcx+1Ch], 80h
0x18006b81e  jz      loc_18006B8BF
0x18006b824  mov     edx, 8Fh
0x18006b829  jmp     loc_18006B74B
0x18006b82e  mov     rcx, rdi; lpCriticalSection
0x18006b831  call    cs:__imp_EnterCriticalSection
0x18006b837  mov     [rsi+104h], r14d
0x18006b83e  test    rdi, rdi
0x18006b841  jz      short loc_18006B84C
0x18006b843  mov     rcx, rdi; lpCriticalSection
0x18006b846  call    cs:__imp_LeaveCriticalSection
0x18006b84c  mov     r9d, [rbp+arg_0]
0x18006b850  lea     rdx, [rsi+0A0h]
0x18006b857  mov     dword ptr [rsp+60h+var_38], 6
0x18006b85f  mov     r8d, 3E8h
0x18006b865  mov     rcx, rsi
0x18006b868  mov     [rsp+60h+var_40], r13d
0x18006b86d  call    ?AddOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@_KKJW4_RequestTypes@@@Z; NotificationServiceImpl::AddOutstandingRequest(_LIST_ENTRY *,unsigned __int64,ulong,long,_RequestTypes)
0x18006b872  mov     ebx, eax
0x18006b874  test    eax, eax
0x18006b876  jns     short loc_18006B8B1
0x18006b878  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b87f  lea     rdi, WPP_GLOBAL_Control
0x18006b886  cmp     rcx, rdi
0x18006b889  jz      short loc_18006B8BF
0x18006b88b  test    byte ptr [rcx+1Ch], 2
0x18006b88f  jz      short loc_18006B8BF
0x18006b891  cmp     byte ptr [rcx+19h], 2
0x18006b895  jb      short loc_18006B8BF
0x18006b897  mov     rcx, [rcx+10h]
0x18006b89b  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b8a2  mov     edx, 90h
0x18006b8a7  mov     r9d, eax
0x18006b8aa  call    WPP_SF_d
0x18006b8af  jmp     short loc_18006B8B8
0x18006b8b1  lea     rdi, WPP_GLOBAL_Control
0x18006b8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b8bf  test    r15, r15
0x18006b8c2  jz      short loc_18006B8DF
0x18006b8c4  call    cs:__imp_GetProcessHeap
0x18006b8ca  mov     r8, r15; lpMem
0x18006b8cd  xor     edx, edx; dwFlags
0x18006b8cf  mov     rcx, rax; hHeap
0x18006b8d2  call    cs:__imp_HeapFree
0x18006b8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b8df  cmp     rcx, rdi
0x18006b8e2  jz      short loc_18006B908
0x18006b8e4  test    byte ptr [rcx+1Ch], 2
0x18006b8e8  jz      short loc_18006B908
0x18006b8ea  cmp     byte ptr [rcx+19h], 6
0x18006b8ee  jb      short loc_18006B908
0x18006b8f0  mov     rcx, [rcx+10h]
0x18006b8f4  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b8fb  mov     edx, 91h
0x18006b900  mov     r9d, ebx
0x18006b903  call    WPP_SF_d
0x18006b908  mov     eax, ebx
0x18006b90a  mov     rbx, [rsp+60h+arg_10]
0x18006b912  add     rsp, 60h
0x18006b916  pop     r15
0x18006b918  pop     r14
0x18006b91a  pop     r13
0x18006b91c  pop     r12
0x18006b91e  pop     rdi
0x18006b91f  pop     rsi
0x18006b920  pop     rbp
0x18006b921  retn
```
