# NotificationServiceImpl::RevokeChannel(unsigned __int64,ushort *,long)

- ea: `0x180073f20`
- end: `0x1800742ce`
- name: `?RevokeChannel@NotificationServiceImpl@@UEAAJ_KPEAGJ@Z`
- size: `942`
- prototype: `__int64 __fastcall(WNPMessageGenerator **this, __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x1800133b0`
- `0x18001c06c`
- `0x18001cc10`
- `0x1800685b8`
- `0x18006b000`
- `0x180073f20`
- `0x180076080`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007425d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007427d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007425d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007427d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007424e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007426f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007424e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007426f`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180074038`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x180074038`

## string_xrefs

- `0x180073fe0`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800740a7`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`
- `0x1800741a3`: `onecoreuap\base\diagnosis\platform\notifications\prov\wnp\notificationserviceimpl.cpp`

## pseudocode

```c
__int64 __fastcall NotificationServiceImpl::RevokeChannel(WNPMessageGenerator **this, __int64 a2, unsigned __int16 *a3)
{
  PVOID v6; // rcx
  unsigned __int8 *v7; // rdi
  int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // r9d
  int v16; // eax
  int v17; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  int v21; // [rsp+20h] [rbp-50h]
  int v22; // [rsp+20h] [rbp-50h]
  unsigned int v23; // [rsp+20h] [rbp-50h]
  LPVOID lpMem; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int8 *v25; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int64 RandomBuffer; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  unsigned int v28; // [rsp+B0h] [rbp+40h] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, a2);
  }
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  v7 = 0;
  lpMem = 0;
  v25 = 0;
  v28 = 0;
  v8 = WpnUtf16ToUtf8(a3, (char **)&lpMem);
  v9 = v8;
  if ( v8 >= 0 )
  {
    RandomBuffer = 0;
    SystemFunction036(&RandomBuffer, 8u);
    v12 = WNPMessageGenerator::GenerateChannelRevoke(this[16], (const char *)lpMem, RandomBuffer, &v25, &v28);
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          202,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v12);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x818,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v9,
        v22);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      {
        v7 = v25;
        goto LABEL_41;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
      v7 = v25;
      goto LABEL_40;
    }
    v7 = v25;
    if ( (byte_1800AFD82 & 0x10) != 0 )
      McTemplateU0sqbr1sxqbr5x_EventWriteTransfer(v14, v13, (_DWORD)lpMem, v15, v22);
    v23 = v28;
    v16 = (*(__int64 (__fastcall **)(WNPMessageGenerator *, __int64, unsigned __int8 near **, const char *))(*(_QWORD *)this[14] + 48LL))(
            this[14],
            a2,
            &WNPMessageGenerator::s_PutCommand,
            "CRL");
    v9 = v16;
    if ( v16 >= 0 )
    {
      v17 = NotificationServiceImpl::AddOutstandingRequest(this, this + 20, a2, 0);
      v9 = v17;
      if ( v17 >= 0 )
        goto LABEL_40;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          206,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v17);
        goto LABEL_40;
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
          204,
          &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
          (unsigned int)v16);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x82B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
        (const char *)v9,
        v23);
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v11 = 205;
        goto LABEL_15;
      }
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
        200,
        &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids,
        (unsigned int)v8);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x812,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\notificationserviceimpl.cpp",
      (const char *)v9,
      v21);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v11 = 201;
LABEL_15:
      WPP_SF_d(v10[2], v11, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
LABEL_40:
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_41:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v7);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 207, &WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180073f20  mov     [rsp-28h+arg_0], rbx
0x180073f25  mov     [rsp-28h+arg_8], rsi
0x180073f2a  push    rbp
0x180073f2b  push    rdi
0x180073f2c  push    r13
0x180073f2e  push    r14
0x180073f30  push    r15
0x180073f32  mov     rbp, rsp
0x180073f35  sub     rsp, 70h
0x180073f39  mov     r13d, r9d
0x180073f3c  mov     rbx, r8
0x180073f3f  mov     rsi, rdx
0x180073f42  mov     r14, rcx
0x180073f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180073f4c  lea     r15, WPP_GLOBAL_Control
0x180073f53  cmp     rcx, r15
0x180073f56  jz      short loc_180073F7C
0x180073f58  test    byte ptr [rcx+1Ch], 2
0x180073f5c  jz      short loc_180073F7C
0x180073f5e  cmp     byte ptr [rcx+19h], 6
0x180073f62  jb      short loc_180073F7C
0x180073f64  mov     rcx, [rcx+10h]
0x180073f68  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073f6f  mov     edx, 0C7h
0x180073f74  mov     r9, rsi
0x180073f77  call    WPP_SF_I
0x180073f7c  test    rbx, rbx
0x180073f7f  jnz     short loc_180073F86
0x180073f81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180073f86  xor     edi, edi
0x180073f88  mov     [rbp+lpMem], 0
0x180073f90  lea     rdx, [rbp+lpMem]; char **
0x180073f94  mov     [rbp+var_10], rdi
0x180073f98  mov     rcx, rbx; lpWideCharStr
0x180073f9b  mov     [rbp+arg_10], edi
0x180073f9e  mov     [rbp+var_20], edi
0x180073fa1  call    ?WpnUtf16ToUtf8@@YAJPEBGPEAPEAD@Z; WpnUtf16ToUtf8(ushort const *,char * *)
0x180073fa6  mov     ebx, eax
0x180073fa8  test    eax, eax
0x180073faa  jns     short loc_18007402B
0x180073fac  mov     rcx, cs:WPP_GLOBAL_Control
0x180073fb3  cmp     rcx, r15
0x180073fb6  jz      short loc_180073FDC
0x180073fb8  test    byte ptr [rcx+1Ch], 2
0x180073fbc  jz      short loc_180073FDC
0x180073fbe  cmp     byte ptr [rcx+19h], 2
0x180073fc2  jb      short loc_180073FDC
0x180073fc4  mov     rcx, [rcx+10h]
0x180073fc8  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180073fcf  mov     edx, 0C8h
0x180073fd4  mov     r9d, eax
0x180073fd7  call    WPP_SF_d
0x180073fdc  mov     rcx, [rbp+28h]; this
0x180073fe0  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180073fe7  mov     r9d, ebx; char *
0x180073fea  mov     edx, 812h; void *
0x180073fef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180073ffb  cmp     rcx, r15
0x180073ffe  jz      loc_180074247
0x180074004  test    byte ptr [rcx+1Ch], 80h
0x180074008  jz      loc_180074247
0x18007400e  mov     edx, 0C9h
0x180074013  mov     rcx, [rcx+10h]
0x180074017  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18007401e  mov     r9d, ebx
0x180074021  call    WPP_SF_d
0x180074026  jmp     loc_180074240
0x18007402b  mov     edx, 8; RandomBufferLength
0x180074030  mov     [rbp+RandomBuffer], rdi
0x180074034  lea     rcx, [rbp+RandomBuffer]; RandomBuffer
0x180074038  call    cs:__imp_SystemFunction036
0x18007403e  mov     r15, [rbp+RandomBuffer]
0x180074042  lea     rax, [rbp+arg_10]
0x180074046  mov     rdx, [rbp+lpMem]; char *
0x18007404a  lea     r9, [rbp+var_10]; unsigned __int8 **
0x18007404e  mov     rcx, [r14+80h]; this
0x180074055  mov     r8, r15; unsigned __int64
0x180074058  mov     [rsp+70h+var_50], rax; int
0x18007405d  call    ?GenerateChannelRevoke@WNPMessageGenerator@@QEAAJPEBD_KPEAPEAEPEAK@Z; WNPMessageGenerator::GenerateChannelRevoke(char const *,unsigned __int64,uchar * *,ulong *)
0x180074062  mov     ebx, eax
0x180074064  test    eax, eax
0x180074066  jns     loc_1800740F7
0x18007406c  mov     rcx, cs:WPP_GLOBAL_Control
0x180074073  lea     r15, WPP_GLOBAL_Control
0x18007407a  cmp     rcx, r15
0x18007407d  jz      short loc_1800740A3
0x18007407f  test    byte ptr [rcx+1Ch], 2
0x180074083  jz      short loc_1800740A3
0x180074085  cmp     byte ptr [rcx+19h], 2
0x180074089  jb      short loc_1800740A3
0x18007408b  mov     rcx, [rcx+10h]
0x18007408f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180074096  mov     edx, 0CAh
0x18007409b  mov     r9d, eax
0x18007409e  call    WPP_SF_d
0x1800740a3  mov     rcx, [rbp+28h]; this
0x1800740a7  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800740ae  mov     r9d, ebx; char *
0x1800740b1  mov     edx, 818h; void *
0x1800740b6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800740bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800740c2  cmp     rcx, r15
0x1800740c5  jz      short loc_1800740EE
0x1800740c7  test    byte ptr [rcx+1Ch], 80h
0x1800740cb  jz      short loc_1800740EE
0x1800740cd  mov     rcx, [rcx+10h]
0x1800740d1  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800740d8  mov     edx, 0CBh
0x1800740dd  mov     r9d, ebx
0x1800740e0  call    WPP_SF_d
0x1800740e5  mov     rdi, [rbp+var_10]
0x1800740e9  jmp     loc_180074240
0x1800740ee  mov     rdi, [rbp+var_10]
0x1800740f2  jmp     loc_180074247
0x1800740f7  test    cs:byte_1800AFD82, 10h
0x1800740fe  mov     rdi, [rbp+var_10]
0x180074102  jz      short loc_180074123
0x180074104  mov     eax, [rbp+arg_10]
0x180074107  mov     r8, [rbp+lpMem]
0x18007410b  mov     [rsp+70h+var_28], rsi
0x180074110  mov     [rsp+70h+var_30], rdi
0x180074115  mov     dword ptr [rsp+70h+var_38], eax
0x180074119  mov     [rsp+70h+var_40], r15
0x18007411e  call    McTemplateU0sqbr1sxqbr5x_EventWriteTransfer
0x180074123  mov     edx, [rbp+arg_10]
0x180074126  lea     r8, [rbp+var_20]
0x18007412a  mov     rcx, [r14+70h]
0x18007412e  lea     r9, aCrl; "CRL"
0x180074135  mov     [rsp+70h+var_38], r8
0x18007413a  lea     r8, ?s_PutCommand@WNPMessageGenerator@@2PAEA; uchar near * WNPMessageGenerator::s_PutCommand
0x180074141  mov     [rsp+70h+var_40], 0
0x18007414a  mov     [rsp+70h+var_48], rdi
0x18007414f  mov     rax, [rcx]
0x180074152  mov     dword ptr [rsp+70h+var_50], edx; int
0x180074156  mov     rdx, rsi
0x180074159  mov     rax, [rax+30h]
0x18007415d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074162  mov     ebx, eax
0x180074164  test    eax, eax
0x180074166  jns     short loc_1800741D7
0x180074168  mov     rcx, cs:WPP_GLOBAL_Control
0x18007416f  lea     r15, WPP_GLOBAL_Control
0x180074176  cmp     rcx, r15
0x180074179  jz      short loc_18007419F
0x18007417b  test    byte ptr [rcx+1Ch], 2
0x18007417f  jz      short loc_18007419F
0x180074181  cmp     byte ptr [rcx+19h], 2
0x180074185  jb      short loc_18007419F
0x180074187  mov     rcx, [rcx+10h]
0x18007418b  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x180074192  mov     edx, 0CCh
0x180074197  mov     r9d, eax
0x18007419a  call    WPP_SF_d
0x18007419f  mov     rcx, [rbp+28h]; this
0x1800741a3  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800741aa  mov     r9d, ebx; char *
0x1800741ad  mov     edx, 82Bh; void *
0x1800741b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800741b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800741be  cmp     rcx, r15
0x1800741c1  jz      loc_180074247
0x1800741c7  test    byte ptr [rcx+1Ch], 80h
0x1800741cb  jz      short loc_180074247
0x1800741cd  mov     edx, 0CDh
0x1800741d2  jmp     loc_180074013
0x1800741d7  mov     r9d, [rbp+var_20]
0x1800741db  lea     rdx, [r14+0A0h]
0x1800741e2  mov     dword ptr [rsp+70h+var_48], 3
0x1800741ea  mov     r8, rsi
0x1800741ed  mov     rcx, r14
0x1800741f0  mov     dword ptr [rsp+70h+var_50], r13d
0x1800741f5  call    ?AddOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@_KKJW4_RequestTypes@@@Z; NotificationServiceImpl::AddOutstandingRequest(_LIST_ENTRY *,unsigned __int64,ulong,long,_RequestTypes)
0x1800741fa  mov     ebx, eax
0x1800741fc  test    eax, eax
0x1800741fe  jns     short loc_180074239
0x180074200  mov     rcx, cs:WPP_GLOBAL_Control
0x180074207  lea     r15, WPP_GLOBAL_Control
0x18007420e  cmp     rcx, r15
0x180074211  jz      short loc_180074247
0x180074213  test    byte ptr [rcx+1Ch], 2
0x180074217  jz      short loc_180074247
0x180074219  cmp     byte ptr [rcx+19h], 2
0x18007421d  jb      short loc_180074247
0x18007421f  mov     rcx, [rcx+10h]
0x180074223  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x18007422a  mov     edx, 0CEh
0x18007422f  mov     r9d, eax
0x180074232  call    WPP_SF_d
0x180074237  jmp     short loc_180074240
0x180074239  lea     r15, WPP_GLOBAL_Control
0x180074240  mov     rcx, cs:WPP_GLOBAL_Control
0x180074247  cmp     [rbp+lpMem], 0
0x18007424c  jz      short loc_18007426A
0x18007424e  call    cs:__imp_GetProcessHeap
0x180074254  mov     r8, [rbp+lpMem]; lpMem
0x180074258  xor     edx, edx; dwFlags
0x18007425a  mov     rcx, rax; hHeap
0x18007425d  call    cs:__imp_HeapFree
0x180074263  mov     rcx, cs:WPP_GLOBAL_Control
0x18007426a  test    rdi, rdi
0x18007426d  jz      short loc_18007428A
0x18007426f  call    cs:__imp_GetProcessHeap
0x180074275  mov     r8, rdi; lpMem
0x180074278  xor     edx, edx; dwFlags
0x18007427a  mov     rcx, rax; hHeap
0x18007427d  call    cs:__imp_HeapFree
0x180074283  mov     rcx, cs:WPP_GLOBAL_Control
0x18007428a  cmp     rcx, r15
0x18007428d  jz      short loc_1800742B3
0x18007428f  test    byte ptr [rcx+1Ch], 2
0x180074293  jz      short loc_1800742B3
0x180074295  cmp     byte ptr [rcx+19h], 6
0x180074299  jb      short loc_1800742B3
0x18007429b  mov     rcx, [rcx+10h]
0x18007429f  lea     r8, WPP_faf6a26f18eb388e2a2d7bab3d04a983_Traceguids
0x1800742a6  mov     edx, 0CFh
0x1800742ab  mov     r9d, ebx
0x1800742ae  call    WPP_SF_d
0x1800742b3  lea     r11, [rsp+70h+var_s0]
0x1800742b8  mov     eax, ebx
0x1800742ba  mov     rbx, [r11+30h]
0x1800742be  mov     rsi, [r11+38h]
0x1800742c2  mov     rsp, r11
0x1800742c5  pop     r15
0x1800742c7  pop     r14
0x1800742c9  pop     r13
0x1800742cb  pop     rdi
0x1800742cc  pop     rbp
0x1800742cd  retn
```
