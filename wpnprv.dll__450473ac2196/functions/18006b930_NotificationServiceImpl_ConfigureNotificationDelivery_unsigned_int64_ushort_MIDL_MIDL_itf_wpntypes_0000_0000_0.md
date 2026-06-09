# NotificationServiceImpl::ConfigureNotificationDelivery(unsigned __int64,ushort *,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,short,long)

- ea: `0x18006b930`
- end: `0x18006be46`
- name: `?ConfigureNotificationDelivery@NotificationServiceImpl@@UEAAJ_KPEAGW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@FJ@Z`
- size: `1302`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, unsigned int, __int16, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x1800133b0`
- `0x18001c06c`
- `0x18001cc10`
- `0x180068aa8`
- `0x18006b000`
- `0x18006b930`
- `0x180076190`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bdd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bdf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bdd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006bdf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bdc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bde4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bdc3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006bde4`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x18006ba46`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x18006ba46`

## string_xrefs

- `0x18006ba01`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006babd`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006bbdd`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006bcd0`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x18006bd6e`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::ConfigureNotificationDelivery(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        unsigned int a4,
        __int16 a5,
        int a6)
{
  PVOID v10; // rcx
  void *v11; // rdi
  int v12; // eax
  unsigned int v13; // ebx
  PVOID *v14; // rcx
  __int64 v15; // rdx
  int ConfigureNotificationDelivery; // eax
  int v17; // edx
  int v18; // ecx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v23; // rax
  int v25; // [rsp+20h] [rbp-60h]
  int v26; // [rsp+20h] [rbp-60h]
  int v27; // [rsp+20h] [rbp-60h]
  int v28; // [rsp+20h] [rbp-60h]
  LPVOID lpMem; // [rsp+60h] [rbp-20h] BYREF
  int v30[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 RandomBuffer; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  int v33; // [rsp+C8h] [rbp+48h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, a2);
  }
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  if ( a4 - 1 > 4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v10);
  v11 = 0;
  lpMem = 0;
  *(_QWORD *)v30 = 0;
  v33 = 0;
  v12 = WpnUtf16ToUtf8(a3, (char **)&lpMem);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        178,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v12);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x74C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v13,
      v25);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 179;
LABEL_55:
      WPP_SF_d(v14[2], v15, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v13);
      goto LABEL_56;
    }
    goto LABEL_57;
  }
  RandomBuffer = 0;
  SystemFunction036(&RandomBuffer, 8u);
  ConfigureNotificationDelivery = WNPMessageGenerator::GenerateConfigureNotificationDelivery(
                                    *(_QWORD *)(a1 + 128),
                                    lpMem,
                                    a4,
                                    RandomBuffer);
  v13 = ConfigureNotificationDelivery;
  if ( ConfigureNotificationDelivery < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        180,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)ConfigureNotificationDelivery);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x752,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v13,
      (int)v30);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
    {
      v11 = *(void **)v30;
      goto LABEL_57;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v13);
    v11 = *(void **)v30;
    goto LABEL_56;
  }
  v11 = *(void **)v30;
  if ( a5 != -1 )
  {
    if ( (byte_1800AFD82 & 0x10) != 0 )
      McTemplateU0sqtqbr3sxqbr7x_EventWriteTransfer(
        v18,
        v17,
        (_DWORD)lpMem,
        a4,
        0,
        (unsigned int)&v33,
        (__int64)&WNPMessageGenerator::s_PutCommand);
    v27 = v33;
    v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int8 near **, const char *))(**(_QWORD **)(a1 + 112)
                                                                                            + 48LL))(
            *(_QWORD *)(a1 + 112),
            a2,
            &WNPMessageGenerator::s_PutCommand,
            "CBL");
    v13 = v20;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          184,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v20);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x782,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v13,
        v27);
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v15 = 185;
        goto LABEL_55;
      }
      goto LABEL_57;
    }
LABEL_47:
    v21 = NotificationServiceImpl::AddOutstandingRequest(a1, a1 + 160, a2, 0, a6, 4);
    v13 = v21;
    if ( v21 >= 0 )
    {
LABEL_56:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_57;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        186,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v21);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x787,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v13,
      v28);
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v15 = 187;
      goto LABEL_55;
    }
    goto LABEL_57;
  }
  if ( (byte_1800AFD82 & 0x10) != 0 )
    McTemplateU0sqtqbr3sxqbr7x_EventWriteTransfer(
      v18,
      v17,
      (_DWORD)lpMem,
      a4,
      1,
      (unsigned int)&v33,
      (__int64)&WNPMessageGenerator::s_DelCommand);
  v26 = v33;
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned __int8 near **, const char *))(**(_QWORD **)(a1 + 112)
                                                                                          + 48LL))(
          *(_QWORD *)(a1 + 112),
          a2,
          &WNPMessageGenerator::s_DelCommand,
          "CBL");
  v13 = v19;
  if ( v19 >= 0 )
    goto LABEL_47;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      182,
      &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
      (unsigned int)v19);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x76B,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
    (const char *)v13,
    v26);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v15 = 183;
    goto LABEL_55;
  }
LABEL_57:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v11);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    WPP_SF_d(v14[2], 188, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18006b930  mov     [rsp-28h+arg_0], rbx
0x18006b935  mov     [rsp-28h+arg_8], rsi
0x18006b93a  push    rbp
0x18006b93b  push    rdi
0x18006b93c  push    r13
0x18006b93e  push    r14
0x18006b940  push    r15
0x18006b942  mov     rbp, rsp
0x18006b945  sub     rsp, 80h
0x18006b94c  mov     r14d, r9d
0x18006b94f  mov     rbx, r8
0x18006b952  mov     rsi, rdx
0x18006b955  mov     r13, rcx
0x18006b958  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b95f  lea     r15, WPP_GLOBAL_Control
0x18006b966  cmp     rcx, r15
0x18006b969  jz      short loc_18006B98F
0x18006b96b  test    byte ptr [rcx+1Ch], 2
0x18006b96f  jz      short loc_18006B98F
0x18006b971  cmp     byte ptr [rcx+19h], 6
0x18006b975  jb      short loc_18006B98F
0x18006b977  mov     rcx, [rcx+10h]
0x18006b97b  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b982  mov     edx, 0B1h
0x18006b987  mov     r9, rsi
0x18006b98a  call    WPP_SF_I
0x18006b98f  test    rbx, rbx
0x18006b992  jnz     short loc_18006B999
0x18006b994  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006b999  lea     eax, [r14-1]
0x18006b99d  cmp     eax, 4
0x18006b9a0  jbe     short loc_18006B9A7
0x18006b9a2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18006b9a7  xor     edi, edi
0x18006b9a9  mov     [rbp+lpMem], 0
0x18006b9b1  lea     rdx, [rbp+lpMem]; char **
0x18006b9b5  mov     qword ptr [rbp+var_18], rdi
0x18006b9b9  mov     rcx, rbx; lpWideCharStr
0x18006b9bc  mov     [rbp+arg_18], edi
0x18006b9bf  mov     [rbp+arg_10], edi
0x18006b9c2  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x18006b9c7  mov     ebx, eax
0x18006b9c9  test    eax, eax
0x18006b9cb  jns     short loc_18006BA39
0x18006b9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b9d4  cmp     rcx, r15
0x18006b9d7  jz      short loc_18006B9FD
0x18006b9d9  test    byte ptr [rcx+1Ch], 2
0x18006b9dd  jz      short loc_18006B9FD
0x18006b9df  cmp     byte ptr [rcx+19h], 2
0x18006b9e3  jb      short loc_18006B9FD
0x18006b9e5  mov     rcx, [rcx+10h]
0x18006b9e9  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006b9f0  mov     edx, 0B2h
0x18006b9f5  mov     r9d, eax
0x18006b9f8  call    WPP_SF_d
0x18006b9fd  mov     rcx, [rbp+28h]; this
0x18006ba01  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006ba08  mov     r9d, ebx; char *
0x18006ba0b  mov     edx, 74Ch; void *
0x18006ba10  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006ba15  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ba1c  cmp     rcx, r15
0x18006ba1f  jz      loc_18006BDBC
0x18006ba25  test    byte ptr [rcx+1Ch], 80h
0x18006ba29  jz      loc_18006BDBC
0x18006ba2f  mov     edx, 0B3h
0x18006ba34  jmp     loc_18006BD99
0x18006ba39  mov     edx, 8; RandomBufferLength
0x18006ba3e  mov     [rbp+RandomBuffer], rdi
0x18006ba42  lea     rcx, [rbp+RandomBuffer]; RandomBuffer
0x18006ba46  call    cs:__imp_SystemFunction036
0x18006ba4c  mov     r15, [rbp+RandomBuffer]
0x18006ba50  lea     rax, [rbp+arg_18]
0x18006ba54  mov     rdx, [rbp+lpMem]
0x18006ba58  mov     r9, r15
0x18006ba5b  mov     rcx, [r13+80h]
0x18006ba62  mov     r8d, r14d
0x18006ba65  mov     [rsp+80h+var_58], rax
0x18006ba6a  lea     rax, [rbp+var_18]
0x18006ba6e  mov     qword ptr [rsp+80h+var_60], rax; int
0x18006ba73  call    ?GenerateConfigureNotificationDelivery@WNPMessageGenerator@@QEAAJPEBDW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateConfigureNotificationDelivery(char const *,__MIDL___MIDL_itf_wpntypes_0000_0000_0005,unsigned __int64,uchar * *,ulong *)
0x18006ba78  mov     ebx, eax
0x18006ba7a  test    eax, eax
0x18006ba7c  jns     loc_18006BB0D
0x18006ba82  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ba89  lea     r15, WPP_GLOBAL_Control
0x18006ba90  cmp     rcx, r15
0x18006ba93  jz      short loc_18006BAB9
0x18006ba95  test    byte ptr [rcx+1Ch], 2
0x18006ba99  jz      short loc_18006BAB9
0x18006ba9b  cmp     byte ptr [rcx+19h], 2
0x18006ba9f  jb      short loc_18006BAB9
0x18006baa1  mov     rcx, [rcx+10h]
0x18006baa5  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006baac  mov     edx, 0B4h
0x18006bab1  mov     r9d, eax
0x18006bab4  call    WPP_SF_d
0x18006bab9  mov     rcx, [rbp+28h]; this
0x18006babd  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006bac4  mov     r9d, ebx; char *
0x18006bac7  mov     edx, 752h; void *
0x18006bacc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006bad1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bad8  cmp     rcx, r15
0x18006badb  jz      short loc_18006BB04
0x18006badd  test    byte ptr [rcx+1Ch], 80h
0x18006bae1  jz      short loc_18006BB04
0x18006bae3  mov     rcx, [rcx+10h]
0x18006bae7  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006baee  mov     edx, 0B5h
0x18006baf3  mov     r9d, ebx
0x18006baf6  call    WPP_SF_d
0x18006bafb  mov     rdi, qword ptr [rbp+var_18]
0x18006baff  jmp     loc_18006BDB5
0x18006bb04  mov     rdi, qword ptr [rbp+var_18]
0x18006bb08  jmp     loc_18006BDBC
0x18006bb0d  mov     rdi, qword ptr [rbp+var_18]
0x18006bb11  or      eax, 0FFFFFFFFh
0x18006bb14  cmp     ax, [rbp+arg_20]
0x18006bb18  jnz     loc_18006BC15
0x18006bb1e  test    cs:byte_1800AFD82, 10h
0x18006bb25  lea     rbx, ?s_DelCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_DelCommand
0x18006bb2c  jz      short loc_18006BB5D
0x18006bb2e  mov     eax, [rbp+arg_18]
0x18006bb31  mov     r9d, r14d
0x18006bb34  mov     r8, [rbp+lpMem]
0x18006bb38  mov     [rsp+80h+var_28], rsi
0x18006bb3d  mov     [rsp+80h+var_30], rdi
0x18006bb42  mov     [rsp+80h+var_38], eax
0x18006bb46  mov     [rsp+80h+var_40], r15
0x18006bb4b  mov     [rsp+80h+var_50], rbx
0x18006bb50  mov     [rsp+80h+var_60], 1
0x18006bb58  call    McTemplateU0sqtqbr3sxqbr7x_EventWriteTransfer
0x18006bb5d  mov     edx, [rbp+arg_18]
0x18006bb60  lea     r9, [rbp+arg_10]
0x18006bb64  mov     rcx, [r13+70h]
0x18006bb68  mov     r8, rbx
0x18006bb6b  mov     [rsp+80h+var_48], r9
0x18006bb70  lea     r9, aCbl; "CBL"
0x18006bb77  mov     [rsp+80h+var_50], 0
0x18006bb80  mov     [rsp+80h+var_58], rdi
0x18006bb85  mov     rax, [rcx]
0x18006bb88  mov     [rsp+80h+var_60], edx; int
0x18006bb8c  mov     rdx, rsi
0x18006bb8f  mov     rax, [rax+30h]
0x18006bb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bb98  mov     ebx, eax
0x18006bb9a  test    eax, eax
0x18006bb9c  jns     loc_18006BD08
0x18006bba2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bba9  lea     r15, WPP_GLOBAL_Control
0x18006bbb0  cmp     rcx, r15
0x18006bbb3  jz      short loc_18006BBD9
0x18006bbb5  test    byte ptr [rcx+1Ch], 2
0x18006bbb9  jz      short loc_18006BBD9
0x18006bbbb  cmp     byte ptr [rcx+19h], 2
0x18006bbbf  jb      short loc_18006BBD9
0x18006bbc1  mov     rcx, [rcx+10h]
0x18006bbc5  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006bbcc  mov     edx, 0B6h
0x18006bbd1  mov     r9d, eax
0x18006bbd4  call    WPP_SF_d
0x18006bbd9  mov     rcx, [rbp+28h]; this
0x18006bbdd  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006bbe4  mov     r9d, ebx; char *
0x18006bbe7  mov     edx, 76Bh; void *
0x18006bbec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006bbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bbf8  cmp     rcx, r15
0x18006bbfb  jz      loc_18006BDBC
0x18006bc01  test    byte ptr [rcx+1Ch], 80h
0x18006bc05  jz      loc_18006BDBC
0x18006bc0b  mov     edx, 0B7h
0x18006bc10  jmp     loc_18006BD99
0x18006bc15  test    cs:byte_1800AFD82, 10h
0x18006bc1c  lea     rbx, ?s_PutCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_PutCommand
0x18006bc23  jz      short loc_18006BC54
0x18006bc25  mov     eax, [rbp+arg_18]
0x18006bc28  mov     r9d, r14d
0x18006bc2b  mov     r8, [rbp+lpMem]
0x18006bc2f  mov     [rsp+80h+var_28], rsi
0x18006bc34  mov     [rsp+80h+var_30], rdi
0x18006bc39  mov     [rsp+80h+var_38], eax
0x18006bc3d  mov     [rsp+80h+var_40], r15
0x18006bc42  mov     [rsp+80h+var_50], rbx
0x18006bc47  mov     [rsp+80h+var_60], 0
0x18006bc4f  call    McTemplateU0sqtqbr3sxqbr7x_EventWriteTransfer
0x18006bc54  mov     edx, [rbp+arg_18]
0x18006bc57  lea     r9, [rbp+arg_10]
0x18006bc5b  mov     rcx, [r13+70h]
0x18006bc5f  mov     r8, rbx
0x18006bc62  mov     [rsp+80h+var_48], r9
0x18006bc67  lea     r9, aCbl; "CBL"
0x18006bc6e  mov     [rsp+80h+var_50], 0
0x18006bc77  mov     [rsp+80h+var_58], rdi
0x18006bc7c  mov     rax, [rcx]
0x18006bc7f  mov     [rsp+80h+var_60], edx; int
0x18006bc83  mov     rdx, rsi
0x18006bc86  mov     rax, [rax+30h]
0x18006bc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bc8f  mov     ebx, eax
0x18006bc91  test    eax, eax
0x18006bc93  jns     short loc_18006BD08
0x18006bc95  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bc9c  lea     r15, WPP_GLOBAL_Control
0x18006bca3  cmp     rcx, r15
0x18006bca6  jz      short loc_18006BCCC
0x18006bca8  test    byte ptr [rcx+1Ch], 2
0x18006bcac  jz      short loc_18006BCCC
0x18006bcae  cmp     byte ptr [rcx+19h], 2
0x18006bcb2  jb      short loc_18006BCCC
0x18006bcb4  mov     rcx, [rcx+10h]
0x18006bcb8  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006bcbf  mov     edx, 0B8h
0x18006bcc4  mov     r9d, eax
0x18006bcc7  call    WPP_SF_d
0x18006bccc  mov     rcx, [rbp+28h]; this
0x18006bcd0  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006bcd7  mov     r9d, ebx; char *
0x18006bcda  mov     edx, 782h; void *
0x18006bcdf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006bce4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bceb  cmp     rcx, r15
0x18006bcee  jz      loc_18006BDBC
0x18006bcf4  test    byte ptr [rcx+1Ch], 80h
0x18006bcf8  jz      loc_18006BDBC
0x18006bcfe  mov     edx, 0B9h
0x18006bd03  jmp     loc_18006BD99
0x18006bd08  mov     eax, [rbp+arg_28]
0x18006bd0b  lea     rdx, [r13+0A0h]
0x18006bd12  mov     r9d, [rbp+arg_10]
0x18006bd16  mov     r8, rsi
0x18006bd19  mov     dword ptr [rsp+80h+var_58], 4
0x18006bd21  mov     rcx, r13
0x18006bd24  mov     [rsp+80h+var_60], eax; int
0x18006bd28  call    ?AddOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@_KKJW4_RequestTypes@@@Z; NotificationServiceImpl::AddOutstandingRequest(_LIST_ENTRY *,unsigned __int64,ulong,long,_RequestTypes)
0x18006bd2d  mov     ebx, eax
0x18006bd2f  test    eax, eax
0x18006bd31  jns     short loc_18006BDAE
0x18006bd33  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bd3a  lea     r15, WPP_GLOBAL_Control
0x18006bd41  cmp     rcx, r15
0x18006bd44  jz      short loc_18006BD6A
0x18006bd46  test    byte ptr [rcx+1Ch], 2
0x18006bd4a  jz      short loc_18006BD6A
0x18006bd4c  cmp     byte ptr [rcx+19h], 2
0x18006bd50  jb      short loc_18006BD6A
0x18006bd52  mov     rcx, [rcx+10h]
0x18006bd56  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006bd5d  mov     edx, 0BAh
0x18006bd62  mov     r9d, eax
0x18006bd65  call    WPP_SF_d
0x18006bd6a  mov     rcx, [rbp+28h]; this
0x18006bd6e  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006bd75  mov     r9d, ebx; char *
0x18006bd78  mov     edx, 787h; void *
0x18006bd7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006bd82  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bd89  cmp     rcx, r15
0x18006bd8c  jz      short loc_18006BDBC
0x18006bd8e  test    byte ptr [rcx+1Ch], 80h
0x18006bd92  jz      short loc_18006BDBC
0x18006bd94  mov     edx, 0BBh
0x18006bd99  mov     rcx, [rcx+10h]
0x18006bd9d  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006bda4  mov     r9d, ebx
0x18006bda7  call    WPP_SF_d
0x18006bdac  jmp     short loc_18006BDB5
0x18006bdae  lea     r15, WPP_GLOBAL_Control
0x18006bdb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bdbc  cmp     [rbp+lpMem], 0
0x18006bdc1  jz      short loc_18006BDDF
0x18006bdc3  call    cs:__imp_GetProcessHeap
0x18006bdc9  mov     r8, [rbp+lpMem]; lpMem
0x18006bdcd  xor     edx, edx; dwFlags
0x18006bdcf  mov     rcx, rax; hHeap
0x18006bdd2  call    cs:__imp_HeapFree
0x18006bdd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bddf  test    rdi, rdi
0x18006bde2  jz      short loc_18006BDFF
0x18006bde4  call    cs:__imp_GetProcessHeap
0x18006bdea  mov     r8, rdi; lpMem
0x18006bded  xor     edx, edx; dwFlags
0x18006bdef  mov     rcx, rax; hHeap
0x18006bdf2  call    cs:__imp_HeapFree
0x18006bdf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bdff  cmp     rcx, r15
0x18006be02  jz      short loc_18006BE28
0x18006be04  test    byte ptr [rcx+1Ch], 2
0x18006be08  jz      short loc_18006BE28
0x18006be0a  cmp     byte ptr [rcx+19h], 6
0x18006be0e  jb      short loc_18006BE28
0x18006be10  mov     rcx, [rcx+10h]
0x18006be14  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18006be1b  mov     edx, 0BCh
0x18006be20  mov     r9d, ebx
0x18006be23  call    WPP_SF_d
0x18006be28  lea     r11, [rsp+80h+var_s0]
0x18006be30  mov     eax, ebx
  ... truncated ...
```
