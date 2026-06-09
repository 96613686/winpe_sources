# NotificationServiceImpl::SendChallengeResponse(char const *)

- ea: `0x180074654`
- end: `0x180074990`
- name: `?SendChallengeResponse@NotificationServiceImpl@@AEAAJPEBD@Z`
- size: `828`
- prototype: `__int64 __fastcall(WNPMessageGenerator **this, const char *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180070300`

## callees

- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001c06c`
- `0x180067fe8`
- `0x180074654`
- `0x1800762c8`
- `0x18007c7d8`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007491c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074944`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007491c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007490e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074936`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007490e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074936`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180074758`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180074758`

## string_xrefs

- `0x180074713`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800747cc`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800748b7`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::SendChallengeResponse(WNPMessageGenerator **this, const char *a2)
{
  PVOID v4; // rcx
  unsigned __int8 *v5; // rdi
  int ChallengeResponse; // eax
  unsigned int v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  const char *v10; // rdx
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // eax
  void *v15; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  int v19; // [rsp+20h] [rbp-40h]
  int v20; // [rsp+20h] [rbp-40h]
  int v21; // [rsp+28h] [rbp-38h]
  unsigned __int8 *v22; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 RandomBuffer; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  unsigned int v25; // [rsp+98h] [rbp+38h] BYREF
  int v26; // [rsp+A0h] [rbp+40h]
  LPVOID lpMem; // [rsp+A8h] [rbp+48h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids);
  }
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  v5 = 0;
  lpMem = 0;
  v22 = 0;
  v25 = 0;
  v26 = 0;
  ChallengeResponse = Utils::GenerateChallengeResponse(a2, "PROD0120PW!CCV9@", "C1BX{V4W}Q3*10SM", (char **)&lpMem);
  v7 = ChallengeResponse;
  if ( ChallengeResponse >= 0 )
  {
    RandomBuffer = 0;
    SystemFunction036(&RandomBuffer, 8u);
    v11 = WNPMessageGenerator::GenerateChallenge(this[16], v10, (const char *)lpMem, RandomBuffer, &v22, &v25);
    v7 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          230,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v11);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x956,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v7,
        v20);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      {
        v5 = v22;
        goto LABEL_36;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v7);
      v5 = v22;
      goto LABEL_35;
    }
    v5 = v22;
    if ( (byte_1800AFD82 & 0x10) != 0 )
      McTemplateU0ssqbr2sxqbr6_EventWriteTransfer(v13, v12, (_DWORD)a2, (_DWORD)lpMem, v20, v21);
    v14 = (*(__int64 (__fastcall **)(WNPMessageGenerator *, unsigned __int8 near **, const char *, _QWORD))(*(_QWORD *)this[14] + 40LL))(
            this[14],
            &WNPMessageGenerator::s_PutCommand,
            "CHALLENGE",
            v25);
    v7 = v14;
    if ( v14 >= 0 )
    {
LABEL_35:
      v8 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_36;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        232,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v14);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x967,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v7,
      (int)v5);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v9 = 233;
      goto LABEL_34;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        228,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)ChallengeResponse);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x950,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v7,
      v19);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v9 = 229;
LABEL_34:
      WPP_SF_d(v8[2], v9, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v7);
      goto LABEL_35;
    }
  }
LABEL_36:
  v15 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    lpMem = 0;
  }
  if ( v5 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v5);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 234, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180074654  mov     [rsp-28h+arg_0], rbx
0x180074659  push    rbp
0x18007465a  push    rsi
0x18007465b  push    rdi
0x18007465c  push    r14
0x18007465e  push    r15
0x180074660  mov     rbp, rsp
0x180074663  sub     rsp, 60h
0x180074667  mov     rsi, rdx
0x18007466a  mov     r15, rcx
0x18007466d  mov     rcx, cs:WPP_GLOBAL_Control
0x180074674  lea     r14, WPP_GLOBAL_Control
0x18007467b  cmp     rcx, r14
0x18007467e  jz      short loc_1800746A1
0x180074680  test    byte ptr [rcx+1Ch], 2
0x180074684  jz      short loc_1800746A1
0x180074686  cmp     byte ptr [rcx+19h], 6
0x18007468a  jb      short loc_1800746A1
0x18007468c  mov     rcx, [rcx+10h]
0x180074690  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180074697  mov     edx, 0E3h
0x18007469c  call    WPP_SF_
0x1800746a1  test    rsi, rsi
0x1800746a4  jnz     short loc_1800746AB
0x1800746a6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800746ab  xor     edi, edi
0x1800746ad  mov     [rbp+lpMem], 0
0x1800746b5  lea     r9, [rbp+lpMem]; char **
0x1800746b9  mov     [rbp+var_10], rdi
0x1800746bd  lea     r8, aC1bxV4wQ310sm; "C1BX{V4W}Q3*10SM"
0x1800746c4  mov     [rbp+arg_8], edi
0x1800746c7  lea     rdx, aProd0120pwCcv9; "PROD0120PW!CCV9@"
0x1800746ce  mov     [rbp+arg_10], edi
0x1800746d1  mov     rcx, rsi; char *
0x1800746d4  call    ?GenerateChallengeResponse@Utils@@SAJPEBD00PEAPEAD@Z; Utils::GenerateChallengeResponse(char const *,char const *,char const *,char * *)
0x1800746d9  mov     ebx, eax
0x1800746db  test    eax, eax
0x1800746dd  jns     short loc_18007474B
0x1800746df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800746e6  cmp     rcx, r14
0x1800746e9  jz      short loc_18007470F
0x1800746eb  test    byte ptr [rcx+1Ch], 2
0x1800746ef  jz      short loc_18007470F
0x1800746f1  cmp     byte ptr [rcx+19h], 2
0x1800746f5  jb      short loc_18007470F
0x1800746f7  mov     rcx, [rcx+10h]
0x1800746fb  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180074702  mov     edx, 0E4h
0x180074707  mov     r9d, eax
0x18007470a  call    WPP_SF_d
0x18007470f  mov     rcx, [rbp+28h]; this
0x180074713  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007471a  mov     r9d, ebx; char *
0x18007471d  mov     edx, 950h; void *
0x180074722  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180074727  mov     rcx, cs:WPP_GLOBAL_Control
0x18007472e  cmp     rcx, r14
0x180074731  jz      loc_180074905
0x180074737  test    byte ptr [rcx+1Ch], 80h
0x18007473b  jz      loc_180074905
0x180074741  mov     edx, 0E5h
0x180074746  jmp     loc_1800748E2
0x18007474b  mov     edx, 8; RandomBufferLength
0x180074750  mov     [rbp+RandomBuffer], rdi
0x180074754  lea     rcx, [rbp+RandomBuffer]; RandomBuffer
0x180074758  call    cs:__imp_SystemFunction036
0x18007475e  mov     r14, [rbp+RandomBuffer]
0x180074762  lea     rax, [rbp+arg_8]
0x180074766  mov     r8, [rbp+lpMem]; char *
0x18007476a  mov     r9, r14; unsigned __int64
0x18007476d  mov     rcx, [r15+80h]; this
0x180074774  mov     qword ptr [rsp+60h+var_38], rax; unsigned int *
0x180074779  lea     rax, [rbp+var_10]
0x18007477d  mov     [rsp+60h+var_40], rax; int
0x180074782  call    ?GenerateChallenge@WNPMessageGenerator@@QEAAJPEBD0_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateChallenge(char const *,char const *,unsigned __int64,uchar * *,ulong *)
0x180074787  mov     ebx, eax
0x180074789  test    eax, eax
0x18007478b  jns     loc_18007481C
0x180074791  mov     rcx, cs:WPP_GLOBAL_Control
0x180074798  lea     r14, WPP_GLOBAL_Control
0x18007479f  cmp     rcx, r14
0x1800747a2  jz      short loc_1800747C8
0x1800747a4  test    byte ptr [rcx+1Ch], 2
0x1800747a8  jz      short loc_1800747C8
0x1800747aa  cmp     byte ptr [rcx+19h], 2
0x1800747ae  jb      short loc_1800747C8
0x1800747b0  mov     rcx, [rcx+10h]
0x1800747b4  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800747bb  mov     edx, 0E6h
0x1800747c0  mov     r9d, eax
0x1800747c3  call    WPP_SF_d
0x1800747c8  mov     rcx, [rbp+28h]; this
0x1800747cc  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800747d3  mov     r9d, ebx; char *
0x1800747d6  mov     edx, 956h; void *
0x1800747db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800747e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800747e7  cmp     rcx, r14
0x1800747ea  jz      short loc_180074813
0x1800747ec  test    byte ptr [rcx+1Ch], 80h
0x1800747f0  jz      short loc_180074813
0x1800747f2  mov     rcx, [rcx+10h]
0x1800747f6  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800747fd  mov     edx, 0E7h
0x180074802  mov     r9d, ebx
0x180074805  call    WPP_SF_d
0x18007480a  mov     rdi, [rbp+var_10]
0x18007480e  jmp     loc_1800748FE
0x180074813  mov     rdi, [rbp+var_10]
0x180074817  jmp     loc_180074905
0x18007481c  test    cs:byte_1800AFD82, 10h
0x180074823  mov     rdi, [rbp+var_10]
0x180074827  jz      short loc_180074846
0x180074829  mov     eax, [rbp+arg_8]
0x18007482c  mov     r8, rsi
0x18007482f  mov     r9, [rbp+lpMem]
0x180074833  mov     [rsp+60h+var_18], rdi
0x180074838  mov     [rsp+60h+var_20], eax
0x18007483c  mov     [rsp+60h+var_28], r14
0x180074841  call    McTemplateU0ssqbr2sxqbr6_EventWriteTransfer
0x180074846  mov     rcx, [r15+70h]
0x18007484a  lea     rdx, [rbp+arg_10]
0x18007484e  mov     r9d, [rbp+arg_8]
0x180074852  lea     r8, aChallenge; "CHALLENGE"
0x180074859  mov     qword ptr [rsp+60h+var_38], rdx
0x18007485e  lea     rdx, ?s_PutCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_PutCommand
0x180074865  mov     [rsp+60h+var_40], rdi; int
0x18007486a  mov     rax, [rcx]
0x18007486d  mov     rax, [rax+28h]
0x180074871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074876  mov     ebx, eax
0x180074878  test    eax, eax
0x18007487a  jns     short loc_1800748F7
0x18007487c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074883  lea     r14, WPP_GLOBAL_Control
0x18007488a  cmp     rcx, r14
0x18007488d  jz      short loc_1800748B3
0x18007488f  test    byte ptr [rcx+1Ch], 2
0x180074893  jz      short loc_1800748B3
0x180074895  cmp     byte ptr [rcx+19h], 2
0x180074899  jb      short loc_1800748B3
0x18007489b  mov     rcx, [rcx+10h]
0x18007489f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800748a6  mov     edx, 0E8h
0x1800748ab  mov     r9d, eax
0x1800748ae  call    WPP_SF_d
0x1800748b3  mov     rcx, [rbp+28h]; this
0x1800748b7  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800748be  mov     r9d, ebx; char *
0x1800748c1  mov     edx, 967h; void *
0x1800748c6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800748cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800748d2  cmp     rcx, r14
0x1800748d5  jz      short loc_180074905
0x1800748d7  test    byte ptr [rcx+1Ch], 80h
0x1800748db  jz      short loc_180074905
0x1800748dd  mov     edx, 0E9h
0x1800748e2  mov     rcx, [rcx+10h]
0x1800748e6  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800748ed  mov     r9d, ebx
0x1800748f0  call    WPP_SF_d
0x1800748f5  jmp     short loc_1800748FE
0x1800748f7  lea     r14, WPP_GLOBAL_Control
0x1800748fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180074905  mov     rsi, [rbp+lpMem]
0x180074909  test    rsi, rsi
0x18007490c  jz      short loc_180074931
0x18007490e  call    cs:__imp_GetProcessHeap
0x180074914  mov     r8, rsi; lpMem
0x180074917  xor     edx, edx; dwFlags
0x180074919  mov     rcx, rax; hHeap
0x18007491c  call    cs:__imp_HeapFree
0x180074922  mov     rcx, cs:WPP_GLOBAL_Control
0x180074929  mov     [rbp+lpMem], 0
0x180074931  test    rdi, rdi
0x180074934  jz      short loc_180074951
0x180074936  call    cs:__imp_GetProcessHeap
0x18007493c  mov     r8, rdi; lpMem
0x18007493f  xor     edx, edx; dwFlags
0x180074941  mov     rcx, rax; hHeap
0x180074944  call    cs:__imp_HeapFree
0x18007494a  mov     rcx, cs:WPP_GLOBAL_Control
0x180074951  cmp     rcx, r14
0x180074954  jz      short loc_18007497A
0x180074956  test    byte ptr [rcx+1Ch], 2
0x18007495a  jz      short loc_18007497A
0x18007495c  cmp     byte ptr [rcx+19h], 6
0x180074960  jb      short loc_18007497A
0x180074962  mov     rcx, [rcx+10h]
0x180074966  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18007496d  mov     edx, 0EAh
0x180074972  mov     r9d, ebx
0x180074975  call    WPP_SF_d
0x18007497a  mov     eax, ebx
0x18007497c  mov     rbx, [rsp+60h+arg_0]
0x180074984  add     rsp, 60h
0x180074988  pop     r15
0x18007498a  pop     r14
0x18007498c  pop     rdi
0x18007498d  pop     rsi
0x18007498e  pop     rbp
0x18007498f  retn
```
