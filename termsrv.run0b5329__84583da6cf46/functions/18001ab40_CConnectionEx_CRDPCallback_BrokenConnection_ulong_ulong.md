# CConnectionEx::CRDPCallback::BrokenConnection(ulong,ulong)

- ea: `0x18001ab40`
- end: `0x18001b14a`
- name: `?BrokenConnection@CRDPCallback@CConnectionEx@@UEAAJKK@Z`
- size: `1546`
- prototype: `__int64 __fastcall(CConnectionEx::CRDPCallback *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001688`
- `0x180013d00`
- `0x1800148f0`
- `0x18001ab40`
- `0x1800321f0`
- `0x1800c8010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001ab98`
- `ntdll!EtwEventActivityIdControl` at `0x18001ad51`
- `ntdll!EtwEventActivityIdControl` at `0x18001af5e`
- `ntdll!EtwEventActivityIdControl` at `0x18001ab98`
- `ntdll!EtwEventActivityIdControl` at `0x18001ad51`
- `ntdll!EtwEventActivityIdControl` at `0x18001af5e`
- `ntdll!EtwEventWriteTransfer` at `0x18001ac6e`
- `ntdll!EtwEventWriteTransfer` at `0x18001ad38`
- `ntdll!EtwEventWriteTransfer` at `0x18001aeac`
- `ntdll!EtwEventWriteTransfer` at `0x18001ac6e`
- `ntdll!EtwEventWriteTransfer` at `0x18001ad38`
- `ntdll!EtwEventWriteTransfer` at `0x18001aeac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ada7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ada7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001afbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ad93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001af04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001afbf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001adbd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001adbd`

## string_xrefs

- `0x18001af15`: `Task completed successfully`
- `0x18001ae1d`: `Protocol notified Broken Connection`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CConnectionEx::CRDPCallback::BrokenConnection(
        CConnectionEx::CRDPCallback *this,
        unsigned int a2,
        unsigned int a3)
{
  const char *v3; // r15
  __int64 v4; // r14
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  int v9; // r8d
  int v10; // r9d
  void *v11; // rcx
  int v12; // edi
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v16; // rax
  char *v17; // rdx
  __int64 v18; // rbx
  const char *v19; // rax
  char *v20; // rdx
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  const char *v22; // [rsp+48h] [rbp-B8h] BYREF
  const char *v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v28[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+88h] [rbp-78h] BYREF
  char *v31; // [rsp+A0h] [rbp-60h] BYREF
  int v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+ACh] [rbp-54h]
  __int16 *v34; // [rsp+B0h] [rbp-50h]
  int v35; // [rsp+B8h] [rbp-48h]
  int v36; // [rsp+BCh] [rbp-44h]
  const char *v37; // [rsp+C0h] [rbp-40h]
  __int64 v38; // [rsp+C8h] [rbp-38h]
  const char **v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  __int64 *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  const char **v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+F8h] [rbp-8h]

  v3 = (const char *)a3;
  v4 = a2;
  v27 = 0;
  v26 = 0;
  v30 = *(_OWORD *)(*((_QWORD *)this + 4) + 17920LL);
  EtwEventActivityIdControl(4, &v30);
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v41 = (__int64 *)"Got broken connection from client";
    v42 = 34;
    v39 = (const char **)"CConnectionEx::CRDPCallback::BrokenConnection";
    v40 = 46;
    v37 = "Broken Connection";
    v38 = 18;
    v24 = 0x40B000000LL;
    v25 = 0;
    v31 = (char *)off_180128178;
    v32 = *(unsigned __int16 *)off_180128178;
    v33 = 2;
    v34 = &word_18010DEAE;
    v35 = 50;
    v36 = 1;
    LODWORD(v22) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(RegHandle, &v24, 0, 0, 5, &v31);
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 4) + 1648LL);
  EnterCriticalSection(v6);
  if ( *(_DWORD *)(*((_QWORD *)this + 4) + 17868LL) == 1 )
  {
    if ( (unsigned int)dword_180128170 > 2 )
    {
      v37 = "CConnectionEx::CRDPCallback::BrokenConnection called after BrokenConnection was signaled. Returning ERROR_NOT_CONNECTED";
      v38 = 120;
      v24 = 0x20B000000LL;
      v25 = 0;
      v31 = (char *)off_180128178;
      v32 = *(unsigned __int16 *)off_180128178;
      v33 = 2;
      v34 = (__int16 *)&dword_18010DE84;
      v35 = 30;
      v36 = 1;
      LODWORD(v22) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(RegHandle, &v24, 0, 0, 3, &v31);
    }
    LeaveCriticalSection(v6);
    EtwEventActivityIdControl(2, &v30);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    return 2147944650LL;
  }
  LeaveCriticalSection(v6);
  v8 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 4) + 1648LL);
  EnterCriticalSection(v8);
  v11 = *(void **)(*((_QWORD *)this + 4) + 17872LL);
  if ( v11 )
    SetEvent(v11);
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v23 = v3;
    v24 = v4;
    LODWORD(v22) = *(_DWORD *)(*((_QWORD *)this + 4) + 17276LL);
    v43 = &v23;
    v44 = 8;
    v41 = &v24;
    v42 = 8;
    v39 = &v22;
    v40 = 4;
    v37 = "Protocol notified Broken Connection";
    v38 = 36;
    v28[0] = 184549376;
    v28[1] = 4;
    v29 = 0;
    v31 = (char *)off_180128178;
    v32 = *(unsigned __int16 *)off_180128178;
    v33 = 2;
    v34 = word_18010DE42;
    v35 = 54;
    v36 = 1;
    v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(RegHandle, v28, 0, 0, 6, &v31);
  }
  *(_DWORD *)(*((_QWORD *)this + 4) + 17868LL) = 1;
  if ( *(_DWORD *)(*((_QWORD *)this + 4) + 17276LL) != -1 )
  {
    LeaveCriticalSection(v8);
    v18 = 0;
    v24 = 0;
    if ( qword_180128DF0 )
    {
      v18 = qword_180128DF0;
      v24 = qword_180128DF0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180128DF0 + 8LL))(qword_180128DF0);
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 152LL))(v18, &v26);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 24LL))(
              v26,
              *(unsigned int *)(*((_QWORD *)this + 4) + 17276LL),
              &v27);
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v27 + 256LL))(
                v27,
                (unsigned int)v4,
                (unsigned int)v3);
        if ( v12 >= 0 )
          goto LABEL_19;
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v24 = (__int64)"BrokenConnection";
          v19 = "Session->OnBrokenConnection";
          v20 = byte_18010DD51;
          goto LABEL_38;
        }
      }
      else
      {
        v13 = dword_180128170;
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v24 = (__int64)"BrokenConnection";
          v19 = "List->FindSessionById";
          v20 = byte_18010DD91;
          goto LABEL_38;
        }
      }
    }
    else if ( (unsigned int)dword_180128170 > 3 )
    {
      v24 = (__int64)"BrokenConnection";
      v19 = "GetSessionList";
      v20 = byte_18010DDD1;
LABEL_38:
      v23 = v19;
      v22 = "Warning HResult failed";
      v21 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v13,
        (_DWORD)v20,
        v14,
        v15,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v24);
    }
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_22;
    v16 = "Broken Connection";
    v17 = (char *)&unk_18010DD10;
    goto LABEL_21;
  }
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v24 = (__int64)"Broken connection is likely client closing for the cert warning prompt";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v11,
      (unsigned int)byte_18010DE11,
      v9,
      v10,
      (__int64)&v24);
  }
  v12 = 0;
  LeaveCriticalSection(v8);
LABEL_19:
  if ( (unsigned int)dword_180128170 > 5 )
  {
    v16 = "Task completed successfully";
    v17 = &byte_18010DCD7;
LABEL_21:
    v23 = v16;
    v21 = v12;
    v24 = (__int64)"CConnectionEx::CRDPCallback::BrokenConnection";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v13,
      (_DWORD)v17,
      v14,
      v15,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v21);
  }
LABEL_22:
  EtwEventActivityIdControl(2, &v30);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001ab40  mov     [rsp-8+arg_18], rbx
0x18001ab45  push    rbp
0x18001ab46  push    rsi
0x18001ab47  push    rdi
0x18001ab48  push    r12
0x18001ab4a  push    r13
0x18001ab4c  push    r14
0x18001ab4e  push    r15
0x18001ab50  lea     rbp, [rsp-10h]
0x18001ab55  sub     rsp, 110h
0x18001ab5c  mov     rax, cs:__security_cookie
0x18001ab63  xor     rax, rsp
0x18001ab66  mov     [rbp+40h+var_40], rax
0x18001ab6a  mov     r15d, r8d
0x18001ab6d  mov     r14d, edx
0x18001ab70  mov     rsi, rcx
0x18001ab73  xor     r12d, r12d
0x18001ab76  mov     [rsp+140h+var_D0], r12
0x18001ab7b  mov     [rsp+140h+var_D8], r12
0x18001ab80  mov     rax, [rcx+20h]
0x18001ab84  movups  xmm0, xmmword ptr [rax+4600h]
0x18001ab8b  movups  [rbp+40h+var_B8], xmm0
0x18001ab8f  lea     rdx, [rbp+40h+var_B8]
0x18001ab93  mov     ecx, 4
0x18001ab98  call    cs:__imp_EtwEventActivityIdControl
0x18001ab9e  nop
0x18001ab9f  mov     eax, cs:dword_180128170
0x18001aba5  lea     r13, aCconnectionexC_1; "CConnectionEx::CRDPCallback::BrokenConn"...
0x18001abac  lea     rdx, aBrokenConnecti_0; "Broken Connection"
0x18001abb3  lea     rdi, _TraceLoggingMetadataEnd
0x18001abba  lea     rcx, _TraceLoggingMetadata
0x18001abc1  cmp     eax, 4
0x18001abc4  jbe     loc_18001AC74
0x18001abca  lea     rax, aGotBrokenConne; "Got broken connection from client"
0x18001abd1  mov     [rbp+40h+var_60], rax
0x18001abd5  mov     [rbp+40h+var_58], 22h ; '"'
0x18001abdd  mov     [rbp+40h+var_70], r13
0x18001abe1  mov     [rbp+40h+var_68], 2Eh ; '.'
0x18001abe9  mov     [rbp+40h+var_80], rdx
0x18001abed  mov     [rbp+40h+var_78], 12h
0x18001abf5  mov     dword ptr [rsp+140h+var_E8], 0B000000h
0x18001abfd  movzx   eax, cs:word_18010DEA4
0x18001ac04  mov     dword ptr [rsp+140h+var_E8+4], eax
0x18001ac08  mov     [rsp+140h+var_E0], r12
0x18001ac0d  mov     rax, cs:off_180128178
0x18001ac14  mov     [rbp+40h+var_A0], rax
0x18001ac18  movzx   eax, word ptr [rax]
0x18001ac1b  mov     [rbp+40h+var_98], eax
0x18001ac1e  mov     [rbp+40h+var_94], 2
0x18001ac25  lea     rax, word_18010DEAE
0x18001ac2c  mov     [rbp+40h+var_90], rax
0x18001ac30  mov     [rbp+40h+var_88], 32h ; '2'
0x18001ac37  mov     [rbp+40h+var_84], 1
0x18001ac3e  mov     rax, rdi
0x18001ac41  sub     eax, ecx
0x18001ac43  mov     dword ptr [rsp+140h+var_F8], eax
0x18001ac47  mov     eax, dword ptr [rsp+140h+var_F8]
0x18001ac4b  lea     rax, [rbp+40h+var_A0]
0x18001ac4f  mov     [rsp+140h+var_118], rax
0x18001ac54  mov     dword ptr [rsp+140h+var_120], 5
0x18001ac5c  xor     r9d, r9d
0x18001ac5f  xor     r8d, r8d
0x18001ac62  lea     rdx, [rsp+140h+var_E8]
0x18001ac67  mov     rcx, cs:RegHandle
0x18001ac6e  call    cs:__imp_EtwEventWriteTransfer
0x18001ac74  mov     rbx, [rsi+20h]
0x18001ac78  add     rbx, 670h
0x18001ac7f  mov     rcx, rbx; lpCriticalSection
0x18001ac82  call    cs:__imp_EnterCriticalSection
0x18001ac88  mov     rax, [rsi+20h]
0x18001ac8c  cmp     dword ptr [rax+45CCh], 1
0x18001ac93  jnz     loc_18001AD90
0x18001ac99  mov     eax, cs:dword_180128170
0x18001ac9f  cmp     eax, 2
0x18001aca2  jbe     loc_18001AD3E
0x18001aca8  lea     rax, aCconnectionexC_13; "CConnectionEx::CRDPCallback::BrokenConn"...
0x18001acaf  mov     [rbp+40h+var_80], rax
0x18001acb3  mov     [rbp+40h+var_78], 78h ; 'x'
0x18001acbb  mov     dword ptr [rsp+140h+var_E8], 0B000000h
0x18001acc3  movzx   eax, cs:word_18010DE7A
0x18001acca  mov     dword ptr [rsp+140h+var_E8+4], eax
0x18001acce  mov     [rsp+140h+var_E0], r12
0x18001acd3  mov     rax, cs:off_180128178
0x18001acda  mov     [rbp+40h+var_A0], rax
0x18001acde  movzx   eax, word ptr [rax]
0x18001ace1  mov     [rbp+40h+var_98], eax
0x18001ace4  mov     [rbp+40h+var_94], 2
0x18001aceb  lea     rax, dword_18010DE84
0x18001acf2  mov     [rbp+40h+var_90], rax
0x18001acf6  mov     [rbp+40h+var_88], 1Eh
0x18001acfd  mov     [rbp+40h+var_84], 1
0x18001ad04  lea     rax, _TraceLoggingMetadata
0x18001ad0b  sub     edi, eax
0x18001ad0d  mov     dword ptr [rsp+140h+var_F8], edi
0x18001ad11  mov     eax, dword ptr [rsp+140h+var_F8]
0x18001ad15  lea     rax, [rbp+40h+var_A0]
0x18001ad19  mov     [rsp+140h+var_118], rax
0x18001ad1e  mov     dword ptr [rsp+140h+var_120], 3
0x18001ad26  xor     r9d, r9d
0x18001ad29  xor     r8d, r8d
0x18001ad2c  lea     rdx, [rsp+140h+var_E8]
0x18001ad31  mov     rcx, cs:RegHandle
0x18001ad38  call    cs:__imp_EtwEventWriteTransfer
0x18001ad3e  mov     rcx, rbx; lpCriticalSection
0x18001ad41  call    cs:__imp_LeaveCriticalSection
0x18001ad47  nop
0x18001ad48  lea     rdx, [rbp+40h+var_B8]
0x18001ad4c  mov     ecx, 2
0x18001ad51  call    cs:__imp_EtwEventActivityIdControl
0x18001ad57  nop
0x18001ad58  mov     rcx, [rsp+140h+var_D8]
0x18001ad5d  test    rcx, rcx
0x18001ad60  jz      short loc_18001AD6F
0x18001ad62  mov     rax, [rcx]
0x18001ad65  mov     rax, [rax+10h]
0x18001ad69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad6e  nop
0x18001ad6f  mov     rcx, [rsp+140h+var_D0]
0x18001ad74  test    rcx, rcx
0x18001ad77  jz      short loc_18001AD86
0x18001ad79  mov     rax, [rcx]
0x18001ad7c  mov     rax, [rax+10h]
0x18001ad80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad85  nop
0x18001ad86  mov     eax, 800708CAh
0x18001ad8b  jmp     loc_18001AF95
0x18001ad90  mov     rcx, rbx; lpCriticalSection
0x18001ad93  call    cs:__imp_LeaveCriticalSection
0x18001ad99  mov     rbx, [rsi+20h]
0x18001ad9d  add     rbx, 670h
0x18001ada4  mov     rcx, rbx; lpCriticalSection
0x18001ada7  call    cs:__imp_EnterCriticalSection
0x18001adad  mov     rax, [rsi+20h]
0x18001adb1  mov     rcx, [rax+45D0h]; hEvent
0x18001adb8  test    rcx, rcx
0x18001adbb  jz      short loc_18001ADC3
0x18001adbd  call    cs:__imp_SetEvent
0x18001adc3  mov     eax, cs:dword_180128170
0x18001adc9  cmp     eax, 4
0x18001adcc  jbe     loc_18001AEB2
0x18001add2  mov     [rsp+140h+var_F0], r15
0x18001add7  mov     [rsp+140h+var_E8], r14
0x18001addc  mov     rax, [rsi+20h]
0x18001ade0  mov     ecx, [rax+437Ch]
0x18001ade6  mov     dword ptr [rsp+140h+var_F8], ecx
0x18001adea  lea     rax, [rsp+140h+var_F0]
0x18001adef  mov     [rbp+40h+var_50], rax
0x18001adf3  mov     [rbp+40h+var_48], 8
0x18001adfb  lea     rax, [rsp+140h+var_E8]
0x18001ae00  mov     [rbp+40h+var_60], rax
0x18001ae04  mov     [rbp+40h+var_58], 8
0x18001ae0c  lea     rax, [rsp+140h+var_F8]
0x18001ae11  mov     [rbp+40h+var_70], rax
0x18001ae15  mov     [rbp+40h+var_68], 4
0x18001ae1d  lea     rax, aProtocolNotifi; "Protocol notified Broken Connection"
0x18001ae24  mov     [rbp+40h+var_80], rax
0x18001ae28  mov     [rbp+40h+var_78], 24h ; '$'
0x18001ae30  mov     [rsp+140h+var_C8], 0B000000h
0x18001ae38  movzx   eax, cs:word_18010DE38
0x18001ae3f  mov     [rsp+140h+var_C4], eax
0x18001ae43  mov     [rbp+40h+var_C0], r12
0x18001ae47  mov     rax, cs:off_180128178
0x18001ae4e  mov     [rbp+40h+var_A0], rax
0x18001ae52  movzx   eax, word ptr [rax]
0x18001ae55  mov     [rbp+40h+var_98], eax
0x18001ae58  mov     [rbp+40h+var_94], 2
0x18001ae5f  lea     rax, word_18010DE42
0x18001ae66  mov     [rbp+40h+var_90], rax
0x18001ae6a  mov     [rbp+40h+var_88], 36h ; '6'
0x18001ae71  mov     [rbp+40h+var_84], 1
0x18001ae78  lea     rax, _TraceLoggingMetadata
0x18001ae7f  sub     edi, eax
0x18001ae81  mov     [rsp+140h+var_100], edi
0x18001ae85  mov     eax, [rsp+140h+var_100]
0x18001ae89  lea     rax, [rbp+40h+var_A0]
0x18001ae8d  mov     [rsp+140h+var_118], rax
0x18001ae92  mov     dword ptr [rsp+140h+var_120], 6
0x18001ae9a  xor     r9d, r9d
0x18001ae9d  xor     r8d, r8d
0x18001aea0  lea     rdx, [rsp+140h+var_C8]
0x18001aea5  mov     rcx, cs:RegHandle
0x18001aeac  call    cs:__imp_EtwEventWriteTransfer
0x18001aeb2  mov     rax, [rsi+20h]
0x18001aeb6  mov     dword ptr [rax+45CCh], 1
0x18001aec0  mov     rax, [rsi+20h]
0x18001aec4  cmp     dword ptr [rax+437Ch], 0FFFFFFFFh
0x18001aecb  jnz     loc_18001AFBC
0x18001aed1  mov     eax, cs:dword_180128170
0x18001aed7  cmp     eax, 4
0x18001aeda  jbe     short loc_18001AEFE
0x18001aedc  lea     rax, aBrokenConnecti; "Broken connection is likely client clos"...
0x18001aee3  mov     [rsp+140h+var_E8], rax
0x18001aee8  lea     rax, [rsp+140h+var_E8]
0x18001aeed  mov     [rsp+140h+var_120], rax
0x18001aef2  lea     rdx, byte_18010DE11
0x18001aef9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001aefe  mov     edi, r12d
0x18001af01  mov     rcx, rbx; lpCriticalSection
0x18001af04  call    cs:__imp_LeaveCriticalSection
0x18001af0a  mov     eax, cs:dword_180128170
0x18001af10  cmp     eax, 5
0x18001af13  jbe     short loc_18001AF55
0x18001af15  lea     rax, aTaskCompletedS; "Task completed successfully"
0x18001af1c  lea     rdx, byte_18010DCD7
0x18001af23  mov     [rsp+140h+var_F0], rax
0x18001af28  lea     rax, [rsp+140h+var_100]
0x18001af2d  mov     [rsp+140h+var_110], rax
0x18001af32  lea     rax, [rsp+140h+var_E8]
0x18001af37  mov     [rsp+140h+var_118], rax
0x18001af3c  lea     rax, [rsp+140h+var_F0]
0x18001af41  mov     [rsp+140h+var_120], rax
0x18001af46  mov     [rsp+140h+var_100], edi
0x18001af4a  mov     [rsp+140h+var_E8], r13
0x18001af4f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001af54  nop
0x18001af55  lea     rdx, [rbp+40h+var_B8]
0x18001af59  mov     ecx, 2
0x18001af5e  call    cs:__imp_EtwEventActivityIdControl
0x18001af64  nop
0x18001af65  mov     rcx, [rsp+140h+var_D8]
0x18001af6a  test    rcx, rcx
0x18001af6d  jz      short loc_18001AF7C
0x18001af6f  mov     rax, [rcx]
0x18001af72  mov     rax, [rax+10h]
0x18001af76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af7b  nop
0x18001af7c  mov     rcx, [rsp+140h+var_D0]
0x18001af81  test    rcx, rcx
0x18001af84  jz      short loc_18001AF93
0x18001af86  mov     rax, [rcx]
0x18001af89  mov     rax, [rax+10h]
0x18001af8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af92  nop
0x18001af93  mov     eax, edi
0x18001af95  mov     rcx, [rbp+40h+var_40]
0x18001af99  xor     rcx, rsp; StackCookie
0x18001af9c  call    __security_check_cookie
0x18001afa1  mov     rbx, [rsp+140h+arg_18]
0x18001afa9  add     rsp, 110h
0x18001afb0  pop     r15
0x18001afb2  pop     r14
0x18001afb4  pop     r13
0x18001afb6  pop     r12
0x18001afb8  pop     rdi
0x18001afb9  pop     rsi
0x18001afba  pop     rbp
0x18001afbb  retn
0x18001afbc  mov     rcx, rbx; lpCriticalSection
0x18001afbf  call    cs:__imp_LeaveCriticalSection
0x18001afc5  mov     rbx, r12
0x18001afc8  mov     [rsp+140h+var_E8], rbx
0x18001afcd  mov     rax, cs:qword_180128DF0
0x18001afd4  test    rax, rax
0x18001afd7  jz      short loc_18001AFF0
0x18001afd9  mov     rbx, rax
0x18001afdc  mov     [rsp+140h+var_E8], rax
0x18001afe1  mov     rax, [rax]
0x18001afe4  mov     rcx, rbx
0x18001afe7  mov     rax, [rax+8]
0x18001afeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aff0  mov     rax, [rbx]
0x18001aff3  lea     rdx, [rsp+140h+var_D8]
0x18001aff8  mov     rcx, rbx
0x18001affb  mov     rax, [rax+98h]
0x18001b002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b007  mov     edi, eax
0x18001b009  mov     rax, [rbx]
0x18001b00c  mov     rcx, rbx
0x18001b00f  mov     rax, [rax+10h]
0x18001b013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b018  nop
0x18001b019  test    edi, edi
0x18001b01b  jns     short loc_18001B04B
0x18001b01d  mov     eax, cs:dword_180128170
0x18001b023  cmp     eax, 3
0x18001b026  jbe     loc_18001B127
0x18001b02c  lea     rax, aBrokenconnecti; "BrokenConnection"
0x18001b033  mov     [rsp+140h+var_E8], rax
0x18001b038  lea     rax, aGetsessionlist_1; "GetSessionList"
0x18001b03f  lea     rdx, byte_18010DDD1
0x18001b046  jmp     loc_18001B0E5
0x18001b04b  mov     rcx, [rsp+140h+var_D8]
0x18001b050  mov     rax, [rcx]
0x18001b053  mov     rdx, [rsi+20h]
0x18001b057  lea     r8, [rsp+140h+var_D0]
0x18001b05c  mov     edx, [rdx+437Ch]
0x18001b062  mov     rax, [rax+18h]
0x18001b066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b06b  mov     edi, eax
0x18001b06d  test    eax, eax
0x18001b06f  jns     short loc_18001B09C
0x18001b071  mov     ecx, cs:dword_180128170
0x18001b077  cmp     ecx, 3
0x18001b07a  jbe     loc_18001B127
0x18001b080  lea     rax, aBrokenconnecti; "BrokenConnection"
0x18001b087  mov     [rsp+140h+var_E8], rax
0x18001b08c  lea     rax, aListFindsessio; "List->FindSessionById"
0x18001b093  lea     rdx, byte_18010DD91
0x18001b09a  jmp     short loc_18001B0E5
0x18001b09c  mov     rcx, [rsp+140h+var_D0]
  ... truncated ...
```
