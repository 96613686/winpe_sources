# NotificationServiceImpl::ConfigureNotificationPolicy(unsigned __int64,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,short,long)

- ea: `0x18006be50`
- end: `0x18006c273`
- name: `?ConfigureNotificationPolicy@NotificationServiceImpl@@UEAAJ_KW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@FJ@Z`
- size: `1059`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int16, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x1800133b0`
- `0x18001c06c`
- `0x180068d40`
- `0x18006b000`
- `0x18006be50`
- `0x180075f80`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c223`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006c223`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006c215`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006c215`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x18006becf`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x18006becf`

## string_xrefs

- `0x18006bf3c`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c03a`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c124`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006c1c2`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::ConfigureNotificationPolicy(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int16 a4,
        int a5)
{
  PVOID v9; // rcx
  int v10; // eax
  int v11; // edx
  int v12; // ecx
  void *v13; // r12
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  HANDLE ProcessHeap; // rax
  int v22; // [rsp+20h] [rbp-50h]
  int v23; // [rsp+20h] [rbp-50h]
  int v24; // [rsp+20h] [rbp-50h]
  __int64 RandomBuffer; // [rsp+60h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v28; // [rsp+C0h] [rbp+50h] BYREF

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, a2);
  }
  if ( a3 - 1 > 3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  lpMem = 0;
  v28 = 0;
  RandomBuffer = 0;
  SystemFunction036(&RandomBuffer, 8u);
  v10 = WNPMessageGenerator::GenerateConfigureNotificationPolicy(*(_QWORD *)(a1 + 128), a3, RandomBuffer, &lpMem);
  v13 = lpMem;
  v14 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        190,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v10);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7B6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v14,
      (int)&v28);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v16 = 191;
LABEL_44:
      WPP_SF_d(v15[2], v16, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  if ( a4 != -1 )
  {
    if ( (byte_1800AFD82 & 0x10) != 0 )
      McTemplateU0qtqbr2sxqbr6x_EventWriteTransfer(
        v12,
        v11,
        a3,
        0,
        (unsigned int)&v28,
        (__int64)&WNPMessageGenerator::s_PutCommand);
    v23 = v28;
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int8 near **, const char *))(**(_QWORD **)(a1 + 112)
                                                                                            + 48LL))(
            *(_QWORD *)(a1 + 112),
            a2,
            &WNPMessageGenerator::s_PutCommand,
            "FILTER");
    v14 = v18;
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          194,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v18);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7E3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v14,
        v23);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v16 = 195;
        goto LABEL_44;
      }
      goto LABEL_46;
    }
LABEL_36:
    v19 = NotificationServiceImpl::AddOutstandingRequest(a1, a1 + 160, a2, 0, a5, 5);
    v14 = v19;
    if ( v19 >= 0 )
    {
LABEL_45:
      v15 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_46;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        196,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v19);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7E8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v14,
      v24);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v16 = 197;
      goto LABEL_44;
    }
    goto LABEL_46;
  }
  if ( (byte_1800AFD82 & 0x10) != 0 )
    McTemplateU0qtqbr2sxqbr6x_EventWriteTransfer(
      v12,
      v11,
      a3,
      1,
      (unsigned int)&v28,
      (__int64)&WNPMessageGenerator::s_DelCommand);
  v22 = v28;
  v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int8 near **, const char *))(**(_QWORD **)(a1 + 112)
                                                                                          + 48LL))(
          *(_QWORD *)(a1 + 112),
          a2,
          &WNPMessageGenerator::s_DelCommand,
          "FILTER");
  v14 = v17;
  if ( v17 >= 0 )
    goto LABEL_36;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      192,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)v17);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x7CD,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
    (const char *)v14,
    v22);
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v16 = 193;
    goto LABEL_44;
  }
LABEL_46:
  if ( v13 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 2) != 0 && *((_BYTE *)v15 + 25) >= 6u )
    WPP_SF_d(v15[2], 198, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x18006be50  mov     [rsp-38h+arg_8], rbx
0x18006be55  push    rbp
0x18006be56  push    rsi
0x18006be57  push    rdi
0x18006be58  push    r12
0x18006be5a  push    r13
0x18006be5c  push    r14
0x18006be5e  push    r15
0x18006be60  mov     rbp, rsp
0x18006be63  sub     rsp, 70h
0x18006be67  movzx   r13d, r9w
0x18006be6b  mov     esi, r8d
0x18006be6e  mov     rdi, rdx
0x18006be71  mov     r14, rcx
0x18006be74  mov     rcx, cs:WPP_GLOBAL_Control
0x18006be7b  lea     rax, WPP_GLOBAL_Control
0x18006be82  cmp     rcx, rax
0x18006be85  jz      short loc_18006BEAB
0x18006be87  test    byte ptr [rcx+1Ch], 2
0x18006be8b  jz      short loc_18006BEAB
0x18006be8d  cmp     byte ptr [rcx+19h], 6
0x18006be91  jb      short loc_18006BEAB
0x18006be93  mov     rcx, [rcx+10h]
0x18006be97  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006be9e  mov     edx, 0BDh
0x18006bea3  mov     r9, rdi
0x18006bea6  call    WPP_SF_I
0x18006beab  lea     eax, [rsi-1]
0x18006beae  cmp     eax, 3
0x18006beb1  jbe     short loc_18006BEB8
0x18006beb3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006beb8  xor     eax, eax
0x18006beba  lea     rcx, [rbp+RandomBuffer]; RandomBuffer
0x18006bebe  mov     [rbp+lpMem], rax
0x18006bec2  mov     [rbp+arg_10], eax
0x18006bec5  mov     [rbp+arg_0], eax
0x18006bec8  lea     edx, [rax+8]; RandomBufferLength
0x18006becb  mov     [rbp+RandomBuffer], rax
0x18006becf  call    cs:__imp_SystemFunction036
0x18006bed5  mov     r15, [rbp+RandomBuffer]
0x18006bed9  lea     rax, [rbp+arg_10]
0x18006bedd  mov     rcx, [r14+80h]
0x18006bee4  lea     r9, [rbp+lpMem]
0x18006bee8  mov     r8, r15
0x18006beeb  mov     qword ptr [rsp+70h+var_50], rax; int
0x18006bef0  mov     edx, esi
0x18006bef2  call    ?GenerateConfigureNotificationPolicy@WNPMessageGenerator@@QEAAJW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateConfigureNotificationPolicy(__MIDL___MIDL_itf_wpntypes_0000_0000_0005,unsigned __int64,uchar * *,ulong *)
0x18006bef7  mov     r12, [rbp+lpMem]
0x18006befb  mov     ebx, eax
0x18006befd  test    eax, eax
0x18006beff  jns     short loc_18006BF74
0x18006bf01  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bf08  lea     rdi, WPP_GLOBAL_Control
0x18006bf0f  cmp     rcx, rdi
0x18006bf12  jz      short loc_18006BF38
0x18006bf14  test    byte ptr [rcx+1Ch], 2
0x18006bf18  jz      short loc_18006BF38
0x18006bf1a  cmp     byte ptr [rcx+19h], 2
0x18006bf1e  jb      short loc_18006BF38
0x18006bf20  mov     rcx, [rcx+10h]
0x18006bf24  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006bf2b  mov     edx, 0BEh
0x18006bf30  mov     r9d, eax
0x18006bf33  call    WPP_SF_d
0x18006bf38  mov     rcx, [rbp+38h]; this
0x18006bf3c  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006bf43  mov     r9d, ebx; char *
0x18006bf46  mov     edx, 7B6h; void *
0x18006bf4b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006bf50  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bf57  cmp     rcx, rdi
0x18006bf5a  jz      loc_18006C210
0x18006bf60  test    byte ptr [rcx+1Ch], 80h
0x18006bf64  jz      loc_18006C210
0x18006bf6a  mov     edx, 0BFh
0x18006bf6f  jmp     loc_18006C1ED
0x18006bf74  or      eax, 0FFFFFFFFh
0x18006bf77  cmp     ax, r13w
0x18006bf7b  jnz     loc_18006C072
0x18006bf81  test    cs:byte_1800AFD82, 10h
0x18006bf88  lea     rbx, ?s_DelCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_DelCommand
0x18006bf8f  jz      short loc_18006BFBA
0x18006bf91  mov     eax, [rbp+arg_10]
0x18006bf94  mov     r9d, 1
0x18006bf9a  mov     [rsp+70h+var_20], rdi
0x18006bf9f  mov     r8d, esi
0x18006bfa2  mov     [rsp+70h+var_28], r12
0x18006bfa7  mov     [rsp+70h+var_30], eax
0x18006bfab  mov     [rsp+70h+var_38], r15
0x18006bfb0  mov     [rsp+70h+var_48], rbx
0x18006bfb5  call    McTemplateU0qtqbr2sxqbr6x_EventWriteTransfer
0x18006bfba  mov     edx, [rbp+arg_10]
0x18006bfbd  lea     r9, [rbp+arg_0]
0x18006bfc1  mov     rcx, [r14+70h]
0x18006bfc5  mov     r8, rbx
0x18006bfc8  mov     [rsp+70h+var_38], r9
0x18006bfcd  lea     r9, aFilter; "FILTER"
0x18006bfd4  mov     [rsp+70h+var_40], 0
0x18006bfdd  mov     [rsp+70h+var_48], r12
0x18006bfe2  mov     rax, [rcx]
0x18006bfe5  mov     [rsp+70h+var_50], edx; int
0x18006bfe9  mov     rdx, rdi
0x18006bfec  mov     rax, [rax+30h]
0x18006bff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bff5  mov     ebx, eax
0x18006bff7  test    eax, eax
0x18006bff9  jns     loc_18006C15C
0x18006bfff  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c006  lea     rdi, WPP_GLOBAL_Control
0x18006c00d  cmp     rcx, rdi
0x18006c010  jz      short loc_18006C036
0x18006c012  test    byte ptr [rcx+1Ch], 2
0x18006c016  jz      short loc_18006C036
0x18006c018  cmp     byte ptr [rcx+19h], 2
0x18006c01c  jb      short loc_18006C036
0x18006c01e  mov     rcx, [rcx+10h]
0x18006c022  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006c029  mov     edx, 0C0h
0x18006c02e  mov     r9d, eax
0x18006c031  call    WPP_SF_d
0x18006c036  mov     rcx, [rbp+38h]; this
0x18006c03a  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c041  mov     r9d, ebx; char *
0x18006c044  mov     edx, 7CDh; void *
0x18006c049  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c04e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c055  cmp     rcx, rdi
0x18006c058  jz      loc_18006C210
0x18006c05e  test    byte ptr [rcx+1Ch], 80h
0x18006c062  jz      loc_18006C210
0x18006c068  mov     edx, 0C1h
0x18006c06d  jmp     loc_18006C1ED
0x18006c072  test    cs:byte_1800AFD82, 10h
0x18006c079  lea     rbx, ?s_PutCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_PutCommand
0x18006c080  jz      short loc_18006C0A8
0x18006c082  mov     eax, [rbp+arg_10]
0x18006c085  xor     r9d, r9d
0x18006c088  mov     [rsp+70h+var_20], rdi
0x18006c08d  mov     r8d, esi
0x18006c090  mov     [rsp+70h+var_28], r12
0x18006c095  mov     [rsp+70h+var_30], eax
0x18006c099  mov     [rsp+70h+var_38], r15
0x18006c09e  mov     [rsp+70h+var_48], rbx
0x18006c0a3  call    McTemplateU0qtqbr2sxqbr6x_EventWriteTransfer
0x18006c0a8  mov     edx, [rbp+arg_10]
0x18006c0ab  lea     r9, [rbp+arg_0]
0x18006c0af  mov     rcx, [r14+70h]
0x18006c0b3  mov     r8, rbx
0x18006c0b6  mov     [rsp+70h+var_38], r9
0x18006c0bb  lea     r9, aFilter; "FILTER"
0x18006c0c2  mov     [rsp+70h+var_40], 0
0x18006c0cb  mov     [rsp+70h+var_48], r12
0x18006c0d0  mov     rax, [rcx]
0x18006c0d3  mov     [rsp+70h+var_50], edx; int
0x18006c0d7  mov     rdx, rdi
0x18006c0da  mov     rax, [rax+30h]
0x18006c0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0e3  mov     ebx, eax
0x18006c0e5  test    eax, eax
0x18006c0e7  jns     short loc_18006C15C
0x18006c0e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c0f0  lea     rdi, WPP_GLOBAL_Control
0x18006c0f7  cmp     rcx, rdi
0x18006c0fa  jz      short loc_18006C120
0x18006c0fc  test    byte ptr [rcx+1Ch], 2
0x18006c100  jz      short loc_18006C120
0x18006c102  cmp     byte ptr [rcx+19h], 2
0x18006c106  jb      short loc_18006C120
0x18006c108  mov     rcx, [rcx+10h]
0x18006c10c  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006c113  mov     edx, 0C2h
0x18006c118  mov     r9d, eax
0x18006c11b  call    WPP_SF_d
0x18006c120  mov     rcx, [rbp+38h]; this
0x18006c124  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c12b  mov     r9d, ebx; char *
0x18006c12e  mov     edx, 7E3h; void *
0x18006c133  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c138  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c13f  cmp     rcx, rdi
0x18006c142  jz      loc_18006C210
0x18006c148  test    byte ptr [rcx+1Ch], 80h
0x18006c14c  jz      loc_18006C210
0x18006c152  mov     edx, 0C3h
0x18006c157  jmp     loc_18006C1ED
0x18006c15c  mov     eax, [rbp+arg_20]
0x18006c15f  lea     rdx, [r14+0A0h]
0x18006c166  mov     r9d, [rbp+arg_0]
0x18006c16a  mov     r8, rdi
0x18006c16d  mov     dword ptr [rsp+70h+var_48], 5
0x18006c175  mov     rcx, r14
0x18006c178  mov     [rsp+70h+var_50], eax; int
0x18006c17c  call    ?AddOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@_KKJW4_RequestTypes@@@Z; NotificationServiceImpl::AddOutstandingRequest(_LIST_ENTRY *,unsigned __int64,ulong,long,_RequestTypes)
0x18006c181  mov     ebx, eax
0x18006c183  test    eax, eax
0x18006c185  jns     short loc_18006C202
0x18006c187  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c18e  lea     rdi, WPP_GLOBAL_Control
0x18006c195  cmp     rcx, rdi
0x18006c198  jz      short loc_18006C1BE
0x18006c19a  test    byte ptr [rcx+1Ch], 2
0x18006c19e  jz      short loc_18006C1BE
0x18006c1a0  cmp     byte ptr [rcx+19h], 2
0x18006c1a4  jb      short loc_18006C1BE
0x18006c1a6  mov     rcx, [rcx+10h]
0x18006c1aa  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006c1b1  mov     edx, 0C4h
0x18006c1b6  mov     r9d, eax
0x18006c1b9  call    WPP_SF_d
0x18006c1be  mov     rcx, [rbp+38h]; this
0x18006c1c2  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006c1c9  mov     r9d, ebx; char *
0x18006c1cc  mov     edx, 7E8h; void *
0x18006c1d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c1dd  cmp     rcx, rdi
0x18006c1e0  jz      short loc_18006C210
0x18006c1e2  test    byte ptr [rcx+1Ch], 80h
0x18006c1e6  jz      short loc_18006C210
0x18006c1e8  mov     edx, 0C5h
0x18006c1ed  mov     rcx, [rcx+10h]
0x18006c1f1  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006c1f8  mov     r9d, ebx
0x18006c1fb  call    WPP_SF_d
0x18006c200  jmp     short loc_18006C209
0x18006c202  lea     rdi, WPP_GLOBAL_Control
0x18006c209  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c210  test    r12, r12
0x18006c213  jz      short loc_18006C230
0x18006c215  call    cs:__imp_GetProcessHeap
0x18006c21b  mov     r8, r12; lpMem
0x18006c21e  xor     edx, edx; dwFlags
0x18006c220  mov     rcx, rax; hHeap
0x18006c223  call    cs:__imp_HeapFree
0x18006c229  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c230  cmp     rcx, rdi
0x18006c233  jz      short loc_18006C259
0x18006c235  test    byte ptr [rcx+1Ch], 2
0x18006c239  jz      short loc_18006C259
0x18006c23b  cmp     byte ptr [rcx+19h], 6
0x18006c23f  jb      short loc_18006C259
0x18006c241  mov     rcx, [rcx+10h]
0x18006c245  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006c24c  mov     edx, 0C6h
0x18006c251  mov     r9d, ebx
0x18006c254  call    WPP_SF_d
0x18006c259  mov     eax, ebx
0x18006c25b  mov     rbx, [rsp+70h+arg_8]
0x18006c263  add     rsp, 70h
0x18006c267  pop     r15
0x18006c269  pop     r14
0x18006c26b  pop     r13
0x18006c26d  pop     r12
0x18006c26f  pop     rdi
0x18006c270  pop     rsi
0x18006c271  pop     rbp
0x18006c272  retn
```
