# CConnectionEx::CRDPCallback::BrokenConnection(ulong,ulong)

- ea: `0x18001b880`
- end: `0x18001bed9`
- name: `?BrokenConnection@CRDPCallback@CConnectionEx@@UEAAJKK@Z`
- size: `1625`
- prototype: `__int64 __fastcall(CConnectionEx::CRDPCallback *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016a8`
- `0x1800146c8`
- `0x180015310`
- `0x18001b880`
- `0x180033f60`
- `0x1800ce010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001b8d8`
- `ntdll!EtwEventActivityIdControl` at `0x18001baaf`
- `ntdll!EtwEventActivityIdControl` at `0x18001bce0`
- `ntdll!EtwEventActivityIdControl` at `0x18001b8d8`
- `ntdll!EtwEventActivityIdControl` at `0x18001baaf`
- `ntdll!EtwEventActivityIdControl` at `0x18001bce0`
- `ntdll!EtwEventWriteTransfer` at `0x18001b9b4`
- `ntdll!EtwEventWriteTransfer` at `0x18001ba8a`
- `ntdll!EtwEventWriteTransfer` at `0x18001bc22`
- `ntdll!EtwEventWriteTransfer` at `0x18001b9b4`
- `ntdll!EtwEventWriteTransfer` at `0x18001ba8a`
- `ntdll!EtwEventWriteTransfer` at `0x18001bc22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b9ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bb11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b9ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bb11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001baf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bd48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001baf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bd48`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bb2d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bb2d`

## string_xrefs

- `0x18001bc97`: `Task completed successfully`
- `0x18001bb93`: `Protocol notified Broken Connection`

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
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v41 = (__int64 *)"Got broken connection from client";
    v42 = 34;
    v39 = (const char **)"CConnectionEx::CRDPCallback::BrokenConnection";
    v40 = 46;
    v37 = "Broken Connection";
    v38 = 18;
    v24 = 0x40B000000LL;
    v25 = 0;
    v31 = (char *)off_18012E178;
    v32 = *(unsigned __int16 *)off_18012E178;
    v33 = 2;
    v34 = &word_180113F2E;
    v35 = 50;
    v36 = 1;
    LODWORD(v22) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(RegHandle, &v24, 0, 0, 5, &v31);
  }
  v6 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 4) + 1648LL);
  EnterCriticalSection(v6);
  if ( *(_DWORD *)(*((_QWORD *)this + 4) + 17868LL) == 1 )
  {
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      v37 = "CConnectionEx::CRDPCallback::BrokenConnection called after BrokenConnection was signaled. Returning ERROR_NOT_CONNECTED";
      v38 = 120;
      v24 = 0x20B000000LL;
      v25 = 0;
      v31 = (char *)off_18012E178;
      v32 = *(unsigned __int16 *)off_18012E178;
      v33 = 2;
      v34 = (__int16 *)&dword_180113F04;
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
  if ( (unsigned int)dword_18012E170 > 4 )
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
    v31 = (char *)off_18012E178;
    v32 = *(unsigned __int16 *)off_18012E178;
    v33 = 2;
    v34 = word_180113EC2;
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
    if ( qword_18012EDF8 )
    {
      v18 = qword_18012EDF8;
      v24 = qword_18012EDF8;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18012EDF8 + 8LL))(qword_18012EDF8);
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
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v24 = (__int64)"BrokenConnection";
          v19 = "Session->OnBrokenConnection";
          v20 = byte_180113DD1;
          goto LABEL_38;
        }
      }
      else
      {
        v13 = dword_18012E170;
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v24 = (__int64)"BrokenConnection";
          v19 = "List->FindSessionById";
          v20 = byte_180113E11;
          goto LABEL_38;
        }
      }
    }
    else if ( (unsigned int)dword_18012E170 > 3 )
    {
      v24 = (__int64)"BrokenConnection";
      v19 = "GetSessionList";
      v20 = byte_180113E51;
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
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_22;
    v16 = "Broken Connection";
    v17 = (char *)&unk_180113D90;
    goto LABEL_21;
  }
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v24 = (__int64)"Broken connection is likely client closing for the cert warning prompt";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v11,
      (unsigned int)byte_180113E91,
      v9,
      v10,
      (__int64)&v24);
  }
  v12 = 0;
  LeaveCriticalSection(v8);
LABEL_19:
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    v16 = "Task completed successfully";
    v17 = &byte_180113D57;
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
0x18001b880  mov     [rsp-8+arg_18], rbx
0x18001b885  push    rbp
0x18001b886  push    rsi
0x18001b887  push    rdi
0x18001b888  push    r12
0x18001b88a  push    r13
0x18001b88c  push    r14
0x18001b88e  push    r15
0x18001b890  lea     rbp, [rsp-10h]
0x18001b895  sub     rsp, 110h
0x18001b89c  mov     rax, cs:__security_cookie
0x18001b8a3  xor     rax, rsp
0x18001b8a6  mov     [rbp+40h+var_40], rax
0x18001b8aa  mov     r15d, r8d
0x18001b8ad  mov     r14d, edx
0x18001b8b0  mov     rsi, rcx
0x18001b8b3  xor     r12d, r12d
0x18001b8b6  mov     [rsp+140h+var_D0], r12
0x18001b8bb  mov     [rsp+140h+var_D8], r12
0x18001b8c0  mov     rax, [rcx+20h]
0x18001b8c4  movups  xmm0, xmmword ptr [rax+4600h]
0x18001b8cb  movups  [rbp+40h+var_B8], xmm0
0x18001b8cf  lea     rdx, [rbp+40h+var_B8]
0x18001b8d3  mov     ecx, 4
0x18001b8d8  call    cs:__imp_EtwEventActivityIdControl
0x18001b8df  nop     dword ptr [rax+rax+00h]
0x18001b8e4  nop
0x18001b8e5  mov     eax, cs:dword_18012E170
0x18001b8eb  lea     r13, aCconnectionexC_1; "CConnectionEx::CRDPCallback::BrokenConn"...
0x18001b8f2  lea     rdx, aBrokenConnecti_0; "Broken Connection"
0x18001b8f9  lea     rdi, _TraceLoggingMetadataEnd
0x18001b900  lea     rcx, _TraceLoggingMetadata
0x18001b907  cmp     eax, 4
0x18001b90a  jbe     loc_18001B9C0
0x18001b910  lea     rax, aGotBrokenConne; "Got broken connection from client"
0x18001b917  mov     [rbp+40h+var_60], rax
0x18001b91b  mov     [rbp+40h+var_58], 22h ; '"'
0x18001b923  mov     [rbp+40h+var_70], r13
0x18001b927  mov     [rbp+40h+var_68], 2Eh ; '.'
0x18001b92f  mov     [rbp+40h+var_80], rdx
0x18001b933  mov     [rbp+40h+var_78], 12h
0x18001b93b  mov     dword ptr [rsp+140h+var_E8], 0B000000h
0x18001b943  movzx   eax, cs:word_180113F24
0x18001b94a  mov     dword ptr [rsp+140h+var_E8+4], eax
0x18001b94e  mov     [rsp+140h+var_E0], r12
0x18001b953  mov     rax, cs:off_18012E178
0x18001b95a  mov     [rbp+40h+var_A0], rax
0x18001b95e  movzx   eax, word ptr [rax]
0x18001b961  mov     [rbp+40h+var_98], eax
0x18001b964  mov     [rbp+40h+var_94], 2
0x18001b96b  lea     rax, word_180113F2E
0x18001b972  mov     [rbp+40h+var_90], rax
0x18001b976  mov     [rbp+40h+var_88], 32h ; '2'
0x18001b97d  mov     [rbp+40h+var_84], 1
0x18001b984  mov     rax, rdi
0x18001b987  sub     eax, ecx
0x18001b989  mov     dword ptr [rsp+140h+var_F8], eax
0x18001b98d  mov     eax, dword ptr [rsp+140h+var_F8]
0x18001b991  lea     rax, [rbp+40h+var_A0]
0x18001b995  mov     [rsp+140h+var_118], rax
0x18001b99a  mov     dword ptr [rsp+140h+var_120], 5
0x18001b9a2  xor     r9d, r9d
0x18001b9a5  xor     r8d, r8d
0x18001b9a8  lea     rdx, [rsp+140h+var_E8]
0x18001b9ad  mov     rcx, cs:RegHandle
0x18001b9b4  call    cs:__imp_EtwEventWriteTransfer
0x18001b9bb  nop     dword ptr [rax+rax+00h]
0x18001b9c0  mov     rbx, [rsi+20h]
0x18001b9c4  add     rbx, 670h
0x18001b9cb  mov     rcx, rbx; lpCriticalSection
0x18001b9ce  call    cs:__imp_EnterCriticalSection
0x18001b9d5  nop     dword ptr [rax+rax+00h]
0x18001b9da  mov     rax, [rsi+20h]
0x18001b9de  cmp     dword ptr [rax+45CCh], 1
0x18001b9e5  jnz     loc_18001BAF4
0x18001b9eb  mov     eax, cs:dword_18012E170
0x18001b9f1  cmp     eax, 2
0x18001b9f4  jbe     loc_18001BA96
0x18001b9fa  lea     rax, aCconnectionexC_13; "CConnectionEx::CRDPCallback::BrokenConn"...
0x18001ba01  mov     [rbp+40h+var_80], rax
0x18001ba05  mov     [rbp+40h+var_78], 78h ; 'x'
0x18001ba0d  mov     dword ptr [rsp+140h+var_E8], 0B000000h
0x18001ba15  movzx   eax, cs:word_180113EFA
0x18001ba1c  mov     dword ptr [rsp+140h+var_E8+4], eax
0x18001ba20  mov     [rsp+140h+var_E0], r12
0x18001ba25  mov     rax, cs:off_18012E178
0x18001ba2c  mov     [rbp+40h+var_A0], rax
0x18001ba30  movzx   eax, word ptr [rax]
0x18001ba33  mov     [rbp+40h+var_98], eax
0x18001ba36  mov     [rbp+40h+var_94], 2
0x18001ba3d  lea     rax, dword_180113F04
0x18001ba44  mov     [rbp+40h+var_90], rax
0x18001ba48  mov     [rbp+40h+var_88], 1Eh
0x18001ba4f  mov     [rbp+40h+var_84], 1
0x18001ba56  lea     rax, _TraceLoggingMetadata
0x18001ba5d  sub     edi, eax
0x18001ba5f  mov     dword ptr [rsp+140h+var_F8], edi
0x18001ba63  mov     eax, dword ptr [rsp+140h+var_F8]
0x18001ba67  lea     rax, [rbp+40h+var_A0]
0x18001ba6b  mov     [rsp+140h+var_118], rax
0x18001ba70  mov     dword ptr [rsp+140h+var_120], 3
0x18001ba78  xor     r9d, r9d
0x18001ba7b  xor     r8d, r8d
0x18001ba7e  lea     rdx, [rsp+140h+var_E8]
0x18001ba83  mov     rcx, cs:RegHandle
0x18001ba8a  call    cs:__imp_EtwEventWriteTransfer
0x18001ba91  nop     dword ptr [rax+rax+00h]
0x18001ba96  mov     rcx, rbx; lpCriticalSection
0x18001ba99  call    cs:__imp_LeaveCriticalSection
0x18001baa0  nop     dword ptr [rax+rax+00h]
0x18001baa5  nop
0x18001baa6  lea     rdx, [rbp+40h+var_B8]
0x18001baaa  mov     ecx, 2
0x18001baaf  call    cs:__imp_EtwEventActivityIdControl
0x18001bab6  nop     dword ptr [rax+rax+00h]
0x18001babb  nop
0x18001babc  mov     rcx, [rsp+140h+var_D8]
0x18001bac1  test    rcx, rcx
0x18001bac4  jz      short loc_18001BAD3
0x18001bac6  mov     rax, [rcx]
0x18001bac9  mov     rax, [rax+10h]
0x18001bacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bad2  nop
0x18001bad3  mov     rcx, [rsp+140h+var_D0]
0x18001bad8  test    rcx, rcx
0x18001badb  jz      short loc_18001BAEA
0x18001badd  mov     rax, [rcx]
0x18001bae0  mov     rax, [rax+10h]
0x18001bae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bae9  nop
0x18001baea  mov     eax, 800708CAh
0x18001baef  jmp     loc_18001BD1D
0x18001baf4  mov     rcx, rbx; lpCriticalSection
0x18001baf7  call    cs:__imp_LeaveCriticalSection
0x18001bafe  nop     dword ptr [rax+rax+00h]
0x18001bb03  mov     rbx, [rsi+20h]
0x18001bb07  add     rbx, 670h
0x18001bb0e  mov     rcx, rbx; lpCriticalSection
0x18001bb11  call    cs:__imp_EnterCriticalSection
0x18001bb18  nop     dword ptr [rax+rax+00h]
0x18001bb1d  mov     rax, [rsi+20h]
0x18001bb21  mov     rcx, [rax+45D0h]; hEvent
0x18001bb28  test    rcx, rcx
0x18001bb2b  jz      short loc_18001BB39
0x18001bb2d  call    cs:__imp_SetEvent
0x18001bb34  nop     dword ptr [rax+rax+00h]
0x18001bb39  mov     eax, cs:dword_18012E170
0x18001bb3f  cmp     eax, 4
0x18001bb42  jbe     loc_18001BC2E
0x18001bb48  mov     [rsp+140h+var_F0], r15
0x18001bb4d  mov     [rsp+140h+var_E8], r14
0x18001bb52  mov     rax, [rsi+20h]
0x18001bb56  mov     ecx, [rax+437Ch]
0x18001bb5c  mov     dword ptr [rsp+140h+var_F8], ecx
0x18001bb60  lea     rax, [rsp+140h+var_F0]
0x18001bb65  mov     [rbp+40h+var_50], rax
0x18001bb69  mov     [rbp+40h+var_48], 8
0x18001bb71  lea     rax, [rsp+140h+var_E8]
0x18001bb76  mov     [rbp+40h+var_60], rax
0x18001bb7a  mov     [rbp+40h+var_58], 8
0x18001bb82  lea     rax, [rsp+140h+var_F8]
0x18001bb87  mov     [rbp+40h+var_70], rax
0x18001bb8b  mov     [rbp+40h+var_68], 4
0x18001bb93  lea     rax, aProtocolNotifi; "Protocol notified Broken Connection"
0x18001bb9a  mov     [rbp+40h+var_80], rax
0x18001bb9e  mov     [rbp+40h+var_78], 24h ; '$'
0x18001bba6  mov     [rsp+140h+var_C8], 0B000000h
0x18001bbae  movzx   eax, cs:word_180113EB8
0x18001bbb5  mov     [rsp+140h+var_C4], eax
0x18001bbb9  mov     [rbp+40h+var_C0], r12
0x18001bbbd  mov     rax, cs:off_18012E178
0x18001bbc4  mov     [rbp+40h+var_A0], rax
0x18001bbc8  movzx   eax, word ptr [rax]
0x18001bbcb  mov     [rbp+40h+var_98], eax
0x18001bbce  mov     [rbp+40h+var_94], 2
0x18001bbd5  lea     rax, word_180113EC2
0x18001bbdc  mov     [rbp+40h+var_90], rax
0x18001bbe0  mov     [rbp+40h+var_88], 36h ; '6'
0x18001bbe7  mov     [rbp+40h+var_84], 1
0x18001bbee  lea     rax, _TraceLoggingMetadata
0x18001bbf5  sub     edi, eax
0x18001bbf7  mov     [rsp+140h+var_100], edi
0x18001bbfb  mov     eax, [rsp+140h+var_100]
0x18001bbff  lea     rax, [rbp+40h+var_A0]
0x18001bc03  mov     [rsp+140h+var_118], rax
0x18001bc08  mov     dword ptr [rsp+140h+var_120], 6
0x18001bc10  xor     r9d, r9d
0x18001bc13  xor     r8d, r8d
0x18001bc16  lea     rdx, [rsp+140h+var_C8]
0x18001bc1b  mov     rcx, cs:RegHandle
0x18001bc22  call    cs:__imp_EtwEventWriteTransfer
0x18001bc29  nop     dword ptr [rax+rax+00h]
0x18001bc2e  mov     rax, [rsi+20h]
0x18001bc32  mov     dword ptr [rax+45CCh], 1
0x18001bc3c  mov     rax, [rsi+20h]
0x18001bc40  cmp     dword ptr [rax+437Ch], 0FFFFFFFFh
0x18001bc47  jnz     loc_18001BD45
0x18001bc4d  mov     eax, cs:dword_18012E170
0x18001bc53  cmp     eax, 4
0x18001bc56  jbe     short loc_18001BC7A
0x18001bc58  lea     rax, aBrokenConnecti; "Broken connection is likely client clos"...
0x18001bc5f  mov     [rsp+140h+var_E8], rax
0x18001bc64  lea     rax, [rsp+140h+var_E8]
0x18001bc69  mov     [rsp+140h+var_120], rax
0x18001bc6e  lea     rdx, byte_180113E91
0x18001bc75  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18001bc7a  mov     edi, r12d
0x18001bc7d  mov     rcx, rbx; lpCriticalSection
0x18001bc80  call    cs:__imp_LeaveCriticalSection
0x18001bc87  nop     dword ptr [rax+rax+00h]
0x18001bc8c  mov     eax, cs:dword_18012E170
0x18001bc92  cmp     eax, 5
0x18001bc95  jbe     short loc_18001BCD7
0x18001bc97  lea     rax, aTaskCompletedS; "Task completed successfully"
0x18001bc9e  lea     rdx, byte_180113D57
0x18001bca5  mov     [rsp+140h+var_F0], rax
0x18001bcaa  lea     rax, [rsp+140h+var_100]
0x18001bcaf  mov     [rsp+140h+var_110], rax
0x18001bcb4  lea     rax, [rsp+140h+var_E8]
0x18001bcb9  mov     [rsp+140h+var_118], rax
0x18001bcbe  lea     rax, [rsp+140h+var_F0]
0x18001bcc3  mov     [rsp+140h+var_120], rax
0x18001bcc8  mov     [rsp+140h+var_100], edi
0x18001bccc  mov     [rsp+140h+var_E8], r13
0x18001bcd1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001bcd6  nop
0x18001bcd7  lea     rdx, [rbp+40h+var_B8]
0x18001bcdb  mov     ecx, 2
0x18001bce0  call    cs:__imp_EtwEventActivityIdControl
0x18001bce7  nop     dword ptr [rax+rax+00h]
0x18001bcec  nop
0x18001bced  mov     rcx, [rsp+140h+var_D8]
0x18001bcf2  test    rcx, rcx
0x18001bcf5  jz      short loc_18001BD04
0x18001bcf7  mov     rax, [rcx]
0x18001bcfa  mov     rax, [rax+10h]
0x18001bcfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd03  nop
0x18001bd04  mov     rcx, [rsp+140h+var_D0]
0x18001bd09  test    rcx, rcx
0x18001bd0c  jz      short loc_18001BD1B
0x18001bd0e  mov     rax, [rcx]
0x18001bd11  mov     rax, [rax+10h]
0x18001bd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd1a  nop
0x18001bd1b  mov     eax, edi
0x18001bd1d  mov     rcx, [rbp+40h+var_40]
0x18001bd21  xor     rcx, rsp; StackCookie
0x18001bd24  call    __security_check_cookie
0x18001bd29  mov     rbx, [rsp+140h+arg_18]
0x18001bd31  add     rsp, 110h
0x18001bd38  pop     r15
0x18001bd3a  pop     r14
0x18001bd3c  pop     r13
0x18001bd3e  pop     r12
0x18001bd40  pop     rdi
0x18001bd41  pop     rsi
0x18001bd42  pop     rbp
0x18001bd43  retn
0x18001bd45  mov     rcx, rbx; lpCriticalSection
0x18001bd48  call    cs:__imp_LeaveCriticalSection
0x18001bd4f  nop     dword ptr [rax+rax+00h]
0x18001bd54  mov     rbx, r12
0x18001bd57  mov     [rsp+140h+var_E8], rbx
0x18001bd5c  mov     rax, cs:qword_18012EDF8
0x18001bd63  test    rax, rax
0x18001bd66  jz      short loc_18001BD7F
0x18001bd68  mov     rbx, rax
0x18001bd6b  mov     [rsp+140h+var_E8], rax
0x18001bd70  mov     rax, [rax]
0x18001bd73  mov     rcx, rbx
0x18001bd76  mov     rax, [rax+8]
0x18001bd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd7f  mov     rax, [rbx]
0x18001bd82  lea     rdx, [rsp+140h+var_D8]
0x18001bd87  mov     rcx, rbx
0x18001bd8a  mov     rax, [rax+98h]
0x18001bd91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd96  mov     edi, eax
0x18001bd98  mov     rax, [rbx]
0x18001bd9b  mov     rcx, rbx
0x18001bd9e  mov     rax, [rax+10h]
0x18001bda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bda7  nop
0x18001bda8  test    edi, edi
0x18001bdaa  jns     short loc_18001BDDA
0x18001bdac  mov     eax, cs:dword_18012E170
0x18001bdb2  cmp     eax, 3
0x18001bdb5  jbe     loc_18001BEB6
0x18001bdbb  lea     rax, aBrokenconnecti; "BrokenConnection"
0x18001bdc2  mov     [rsp+140h+var_E8], rax
0x18001bdc7  lea     rax, aGetsessionlist_1; "GetSessionList"
0x18001bdce  lea     rdx, byte_180113E51
0x18001bdd5  jmp     loc_18001BE74
0x18001bdda  mov     rcx, [rsp+140h+var_D8]
0x18001bddf  mov     rax, [rcx]
0x18001bde2  mov     rdx, [rsi+20h]
0x18001bde6  lea     r8, [rsp+140h+var_D0]
0x18001bdeb  mov     edx, [rdx+437Ch]
0x18001bdf1  mov     rax, [rax+18h]
  ... truncated ...
```
