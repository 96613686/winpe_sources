# TransportRelay::HandleFailedIoContext(Transport const *,std::shared_ptr<TransportIoContext> const &)

- ea: `0x1400eed8c`
- end: `0x1400ef029`
- name: `?HandleFailedIoContext@TransportRelay@@AEAAXPEBVTransport@@AEBV?$shared_ptr@VTransportIoContext@@@std@@@Z`
- size: `669`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400ef564`

## callees

- `0x1400016ec`
- `0x140005360`
- `0x14000aeec`
- `0x14000ea44`
- `0x1400eed8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400eef32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400eef32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400eeef5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400eeef5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400eeec6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400eeec6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400eefe6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1400eefe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400eeefb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400eeefb`

## string_xrefs

- `0x1400ef017`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall TransportRelay::HandleFailedIoContext(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v6; // r14
  __int64 v7; // r10
  int v8; // r15d
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  __int64 v11; // rcx
  int v12; // ecx
  const char *v13; // r9
  int v14; // eax
  char v15; // si
  __int64 v16; // rcx
  const WCHAR *v17; // rax
  int v18; // [rsp+30h] [rbp-59h] BYREF
  int v19; // [rsp+34h] [rbp-55h] BYREF
  __int64 v20; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+40h] [rbp-49h] BYREF
  const WCHAR *v22; // [rsp+60h] [rbp-29h]
  int v23; // [rsp+68h] [rbp-21h]
  int v24; // [rsp+6Ch] [rbp-1Dh]
  int *v25; // [rsp+70h] [rbp-19h]
  __int64 v26; // [rsp+78h] [rbp-11h]
  int *v27; // [rsp+80h] [rbp-9h]
  __int64 v28; // [rsp+88h] [rbp-1h]
  __int64 *v29; // [rsp+90h] [rbp+7h]
  __int64 v30; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v6 = -1;
  v7 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
  v8 = 2;
  if ( *(_DWORD *)v7 > 4u
    && (*(_QWORD *)(v7 + 16) & 0x80u) != 0LL
    && (*(_QWORD *)(v7 + 24) & 0x80LL) == *(_QWORD *)(v7 + 24) )
  {
    v9 = *a3;
    v20 = a2;
    v18 = *(_DWORD *)(v9 + 16);
    v19 = *(_DWORD *)(v9 + 48);
    v10 = (const WCHAR *)(a1 + 200);
    if ( *(_QWORD *)(a1 + 224) > 7u )
      v10 = *(const WCHAR **)v10;
    v30 = 8;
    v29 = &v20;
    v27 = &v18;
    v25 = &v19;
    v28 = 4;
    v26 = 4;
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      v10 = &szPassword;
      v12 = 2;
    }
    v22 = v10;
    v23 = v12;
    v24 = 0;
    tlgWriteTransfer_EventWriteTransfer(v7, (int)&dword_14013BEAC, 0, 0, 6u, &v21);
  }
  if ( *(_DWORD *)(*a3 + 16) == 2 )
    *(_BYTE *)(*a3 + 73) = 1;
  *(_BYTE *)(*a3 + 72) = 0;
  if ( !SetEvent(*(HANDLE *)(*a3 + 56)) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v13);
  if ( !*(_BYTE *)(a1 + 232) && *(_DWORD *)(*a3 + 48) == 1236 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 120));
    *(_DWORD *)(a1 + 128) = GetCurrentThreadId();
    v14 = *(_DWORD *)(a1 + 136);
    if ( v14 == 5 || (v15 = 0, v14 == 6) )
    {
      v15 = 1;
      *(_DWORD *)(a1 + 136) = 4;
    }
    *(_DWORD *)(a1 + 128) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 120));
    if ( a2 == *(_QWORD *)(a1 + 8) )
    {
      *(_DWORD *)(a1 + 92) = 3;
    }
    else if ( a2 == *(_QWORD *)(a1 + 24) )
    {
      *(_DWORD *)(a1 + 96) = 3;
    }
    if ( v15 )
    {
      v16 = *((_QWORD *)ComputeService::Diagnostics::TraceProvider::Instance() + 1);
      if ( *(_DWORD *)v16 > 5u
        && (*(_QWORD *)(v16 + 16) & 0x80u) != 0LL
        && (*(_QWORD *)(v16 + 24) & 0x80LL) == *(_QWORD *)(v16 + 24) )
      {
        v17 = (const WCHAR *)(a1 + 200);
        if ( *(_QWORD *)(a1 + 224) > 7u )
          v17 = *(const WCHAR **)v17;
        if ( v17 )
        {
          do
            ++v6;
          while ( v17[v6] );
          v8 = 2 * v6 + 2;
        }
        else
        {
          v17 = &szPassword;
        }
        v22 = v17;
        v23 = v8;
        v24 = 0;
        tlgWriteTransfer_EventWriteTransfer(v16, (int)&byte_14013C21D, 0, 0, 3u, &v21);
      }
      SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 176));
    }
  }
}

```

## disassembly

```asm
0x1400eed8c  mov     [rsp-8+arg_8], rbx
0x1400eed91  push    rbp
0x1400eed92  push    rsi
0x1400eed93  push    rdi
0x1400eed94  push    r12
0x1400eed96  push    r13
0x1400eed98  push    r14
0x1400eed9a  push    r15
0x1400eed9c  lea     rbp, [rsp-27h]
0x1400eeda1  sub     rsp, 0B0h
0x1400eeda8  mov     rax, cs:__security_cookie
0x1400eedaf  xor     rax, rsp
0x1400eedb2  mov     [rbp+57h+var_40], rax
0x1400eedb6  mov     rdi, r8
0x1400eedb9  mov     r12, rdx
0x1400eedbc  mov     rbx, rcx
0x1400eedbf  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400eedc4  xor     r13d, r13d
0x1400eedc7  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400eedcb  mov     r10, [rax+8]
0x1400eedcf  lea     edx, [r13+4]
0x1400eedd3  lea     r15d, [r13+2]
0x1400eedd7  mov     eax, [r10]
0x1400eedda  cmp     eax, edx
0x1400eeddc  jbe     loc_1400EEEA5
0x1400eede2  mov     rcx, [r10+18h]
0x1400eede6  mov     rax, [r10+10h]
0x1400eedea  test    al, al
0x1400eedec  jns     loc_1400EEEA5
0x1400eedf2  mov     rax, rcx
0x1400eedf5  and     eax, 80h
0x1400eedfa  cmp     rax, rcx
0x1400eedfd  jnz     loc_1400EEEA5
0x1400eee03  mov     rcx, [rdi]
0x1400eee06  mov     [rbp+57h+var_A8], r12
0x1400eee0a  mov     eax, [rcx+10h]
0x1400eee0d  mov     [rbp+57h+var_B0], eax
0x1400eee10  mov     eax, [rcx+30h]
0x1400eee13  mov     [rbp+57h+var_AC], eax
0x1400eee16  lea     rax, [rbx+0C8h]
0x1400eee1d  cmp     qword ptr [rax+18h], 7
0x1400eee22  jbe     short loc_1400EEE27
0x1400eee24  mov     rax, [rax]
0x1400eee27  mov     [rbp+57h+var_48], 8
0x1400eee2f  lea     rcx, [rbp+57h+var_A8]
0x1400eee33  mov     [rbp+57h+var_50], rcx
0x1400eee37  lea     rcx, [rbp+57h+var_B0]
0x1400eee3b  mov     [rbp+57h+var_60], rcx
0x1400eee3f  lea     rcx, [rbp+57h+var_AC]
0x1400eee43  mov     [rbp+57h+var_70], rcx
0x1400eee47  mov     [rbp+57h+var_58], rdx
0x1400eee4b  mov     [rbp+57h+var_68], rdx
0x1400eee4f  test    rax, rax
0x1400eee52  jz      short loc_1400EEE6A
0x1400eee54  mov     rcx, r14
0x1400eee57  inc     rcx
0x1400eee5a  cmp     [rax+rcx*2], r13w
0x1400eee5f  jnz     short loc_1400EEE57
0x1400eee61  lea     ecx, ds:2[rcx*2]
0x1400eee68  jmp     short loc_1400EEE74
0x1400eee6a  lea     rax, szPassword
0x1400eee71  mov     ecx, r15d
0x1400eee74  mov     [rbp+57h+var_80], rax
0x1400eee78  lea     rdx, dword_14013BEAC; int
0x1400eee7f  lea     rax, [rbp+57h+var_A0]
0x1400eee83  mov     [rbp+57h+var_78], ecx
0x1400eee86  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1400eee8b  xor     r9d, r9d; int
0x1400eee8e  xor     r8d, r8d; int
0x1400eee91  mov     [rsp+0E0h+var_C0], 6; ULONG
0x1400eee99  mov     rcx, r10; int
0x1400eee9c  mov     [rbp+57h+var_74], r13d
0x1400eeea0  call    _tlgWriteTransfer_EventWriteTransfer
0x1400eeea5  mov     rcx, [rdi]
0x1400eeea8  cmp     [rcx+10h], r15d
0x1400eeeac  jnz     short loc_1400EEEB6
0x1400eeeae  mov     eax, 1
0x1400eeeb3  xchg    al, [rcx+49h]
0x1400eeeb6  mov     rcx, [rdi]
0x1400eeeb9  mov     eax, r13d
0x1400eeebc  xchg    al, [rcx+48h]
0x1400eeebf  mov     rcx, [rdi]
0x1400eeec2  mov     rcx, [rcx+38h]; hEvent
0x1400eeec6  call    cs:__imp_SetEvent
0x1400eeecc  test    eax, eax
0x1400eeece  jz      loc_1400EF013
0x1400eeed4  cmp     [rbx+0E8h], r13b
0x1400eeedb  jnz     loc_1400EEFEC
0x1400eeee1  mov     rax, [rdi]
0x1400eeee4  cmp     dword ptr [rax+30h], 4D4h
0x1400eeeeb  jnz     loc_1400EEFEC
0x1400eeef1  lea     rcx, [rbx+78h]; SRWLock
0x1400eeef5  call    cs:__imp_AcquireSRWLockExclusive
0x1400eeefb  call    cs:__imp_GetCurrentThreadId
0x1400eef01  mov     [rbx+80h], eax
0x1400eef07  mov     eax, [rbx+88h]
0x1400eef0d  cmp     eax, 5
0x1400eef10  jz      short loc_1400EEF1A
0x1400eef12  mov     sil, r13b
0x1400eef15  cmp     eax, 6
0x1400eef18  jnz     short loc_1400EEF27
0x1400eef1a  mov     sil, 1
0x1400eef1d  mov     dword ptr [rbx+88h], 4
0x1400eef27  lea     rcx, [rbx+78h]; SRWLock
0x1400eef2b  mov     [rbx+80h], r13d
0x1400eef32  call    cs:__imp_ReleaseSRWLockExclusive
0x1400eef38  mov     edi, 3
0x1400eef3d  cmp     r12, [rbx+8]
0x1400eef41  jnz     short loc_1400EEF48
0x1400eef43  mov     [rbx+5Ch], edi
0x1400eef46  jmp     short loc_1400EEF51
0x1400eef48  cmp     r12, [rbx+18h]
0x1400eef4c  jnz     short loc_1400EEF51
0x1400eef4e  mov     [rbx+60h], edi
0x1400eef51  test    sil, sil
0x1400eef54  jz      loc_1400EEFEC
0x1400eef5a  call    ?Instance@TraceProvider@Diagnostics@ComputeService@@KAPEAV123@XZ; ComputeService::Diagnostics::TraceProvider::Instance(void)
0x1400eef5f  mov     rcx, [rax+8]; int
0x1400eef63  mov     eax, [rcx]
0x1400eef65  cmp     eax, 5
0x1400eef68  jbe     short loc_1400EEFDF
0x1400eef6a  mov     rdx, [rcx+18h]
0x1400eef6e  mov     rax, [rcx+10h]
0x1400eef72  test    al, al
0x1400eef74  jns     short loc_1400EEFDF
0x1400eef76  mov     rax, rdx
0x1400eef79  and     eax, 80h
0x1400eef7e  cmp     rax, rdx
0x1400eef81  jnz     short loc_1400EEFDF
0x1400eef83  lea     rax, [rbx+0C8h]
0x1400eef8a  cmp     qword ptr [rax+18h], 7
0x1400eef8f  jbe     short loc_1400EEF94
0x1400eef91  mov     rax, [rax]
0x1400eef94  test    rax, rax
0x1400eef97  jz      short loc_1400EEFAD
0x1400eef99  inc     r14
0x1400eef9c  cmp     [rax+r14*2], r13w
0x1400eefa1  jnz     short loc_1400EEF99
0x1400eefa3  lea     r15d, ds:2[r14*2]
0x1400eefab  jmp     short loc_1400EEFB4
0x1400eefad  lea     rax, szPassword
0x1400eefb4  mov     [rbp+57h+var_80], rax
0x1400eefb8  lea     rdx, byte_14013C21D; int
0x1400eefbf  lea     rax, [rbp+57h+var_A0]
0x1400eefc3  mov     [rbp+57h+var_78], r15d
0x1400eefc7  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x1400eefcc  xor     r9d, r9d; int
0x1400eefcf  xor     r8d, r8d; int
0x1400eefd2  mov     [rsp+0E0h+var_C0], edi; ULONG
0x1400eefd6  mov     [rbp+57h+var_74], r13d
0x1400eefda  call    _tlgWriteTransfer_EventWriteTransfer
0x1400eefdf  mov     rcx, [rbx+0B0h]; pwk
0x1400eefe6  call    cs:__imp_SubmitThreadpoolWork
0x1400eefec  mov     rcx, [rbp+57h+var_40]
0x1400eeff0  xor     rcx, rsp; StackCookie
0x1400eeff3  call    __security_check_cookie
0x1400eeff8  mov     rbx, [rsp+0E0h+arg_8]
0x1400ef000  add     rsp, 0B0h
0x1400ef007  pop     r15
0x1400ef009  pop     r14
0x1400ef00b  pop     r13
0x1400ef00d  pop     r12
0x1400ef00f  pop     rdi
0x1400ef010  pop     rsi
0x1400ef011  pop     rbp
0x1400ef012  retn
0x1400ef013  mov     rcx, [rbp+5Fh]; this
0x1400ef017  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400ef01e  mov     edx, 0A01h; void *
0x1400ef023  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
