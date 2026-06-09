# _BioCredMgrGetLogonUserIdentity(void *,ulong,_WINBIO_IDENTITY *,unsigned __int64 *)

- ea: `0x180025bc0`
- end: `0x180025d8d`
- name: `?_BioCredMgrGetLogonUserIdentity@@YAJPEAXKPEAU_WINBIO_IDENTITY@@PEA_K@Z`
- size: `461`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _WINBIO_IDENTITY *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023b80`

## callees

- `0x180011d24`
- `0x180025bc0`
- `0x180025d94`
- `0x180025e7c`
- `0x180026040`
- `0x1800275b4`
- `0x180040600`
- `0x180060dc8`
- `0x180068f60`
- `0x180069cc8`
- `0x1800bbb84`
- `0x1800bc048`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025c8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180025cec`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180025cec`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180025cb4`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180025cb4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025cfa`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180025cfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _BioCredMgrGetLogonUserIdentity(
        void *a1,
        unsigned int a2,
        struct _WINBIO_IDENTITY *a3,
        unsigned __int64 *a4)
{
  enum WELL_KNOWN_SID_TYPE v8; // edx
  __int64 v9; // rcx
  CFUSManager *v10; // rcx
  CUserContext *v12; // rcx
  unsigned int v13; // ebx
  HANDLE hObject[2]; // [rsp+20h] [rbp-59h] BYREF
  int v15; // [rsp+30h] [rbp-49h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-41h] BYREF
  _OWORD pSid[3]; // [rsp+40h] [rbp-39h] BYREF
  _OWORD v18[2]; // [rsp+70h] [rbp-9h]
  unsigned __int64 v19; // [rsp+90h] [rbp+17h]
  FILETIME FileTime1; // [rsp+98h] [rbp+1Fh] BYREF

  if ( !a3 || !a4 )
    return 2147942487LL;
  CActivityMonitor::NotifyClientArrival(0xC0FFFFFF);
  *(_OWORD *)hObject = 0;
  v15 = 0;
  if ( CUserContext::OpenContext((CUserContext *)hObject, a1) < 0 )
    goto LABEL_21;
  if ( !CUserContext::IsWellKnown(hObject, v8) )
    goto LABEL_20;
  if ( !g_FUS_Manager )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
  memset_0(pSid, 0, 0x60u);
  if ( CFUSManager::RetrieveFUSTarget(v10, a2, (struct _WINBIO_FUS_EVENT *)pSid) >= 0 )
  {
    if ( LODWORD(pSid[0]) == 3 && IsValidSid((char *)pSid + 8) && LODWORD(pSid[0]) == 3 )
    {
      if ( !CUserContext::IsCredProvEnabled(v12, (char *)pSid + 8) )
      {
        v13 = -2146861008;
LABEL_22:
        CUserContext::~CUserContext((CUserContext *)hObject);
        CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
        return v13;
      }
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime(&FileTime1, &SystemTimeAsFileTime) >= 0 )
      {
        *(_OWORD *)&a3->Type = pSid[0];
        *(_OWORD *)&a3->Value.AccountSid.Data[8] = pSid[1];
        *(_OWORD *)&a3->Value.AccountSid.Data[24] = pSid[2];
        *(_OWORD *)&a3->Value.AccountSid.Data[40] = v18[0];
        *(_OWORD *)&a3->Value.AccountSid.Data[52] = *(_OWORD *)((char *)v18 + 12);
        *a4 = v19;
        CUserContext::~CUserContext((CUserContext *)hObject);
        CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
        return 0;
      }
LABEL_20:
      v13 = -2147024891;
      goto LABEL_22;
    }
LABEL_21:
    v13 = -2146861053;
    goto LABEL_22;
  }
  if ( v15 )
    CUserContext::RevertToSelf((CUserContext *)hObject);
  v15 = 0;
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
  return 2148106243LL;
}

```

## disassembly

```asm
0x180025bc0  push    rbp
0x180025bc2  push    rbx
0x180025bc3  push    rsi
0x180025bc4  push    rdi
0x180025bc5  push    r14
0x180025bc7  lea     rbp, [rsp-37h]
0x180025bcc  sub     rsp, 0B0h
0x180025bd3  mov     rax, cs:__security_cookie
0x180025bda  xor     rax, rsp
0x180025bdd  mov     [rbp+57h+var_28], rax
0x180025be1  mov     rdi, r9
0x180025be4  mov     rbx, r8
0x180025be7  mov     r14d, edx
0x180025bea  mov     rsi, rcx
0x180025bed  test    r8, r8
0x180025bf0  jz      loc_180025D6E
0x180025bf6  test    r9, r9
0x180025bf9  jz      loc_180025D6E
0x180025bff  mov     ecx, 0C0FFFFFFh; unsigned int
0x180025c04  call    ?NotifyClientArrival@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientArrival(uint)
0x180025c09  nop
0x180025c0a  xorps   xmm0, xmm0
0x180025c0d  movdqu  xmmword ptr [rbp+57h+hObject], xmm0
0x180025c12  mov     [rbp+57h+var_A0], 0
0x180025c19  mov     rdx, rsi; void *
0x180025c1c  lea     rcx, [rbp+57h+hObject]; this
0x180025c20  call    ?OpenContext@CUserContext@@QEAAJPEAX@Z; CUserContext::OpenContext(void *)
0x180025c25  test    eax, eax
0x180025c27  js      loc_180025D51
0x180025c2d  lea     rcx, [rbp+57h+hObject]; this
0x180025c31  call    ?IsWellKnown@CUserContext@@QEAA_NW4WELL_KNOWN_SID_TYPE@@@Z; CUserContext::IsWellKnown(WELL_KNOWN_SID_TYPE)
0x180025c36  test    al, al
0x180025c38  jz      loc_180025D4A
0x180025c3e  cmp     cs:?g_FUS_Manager@@3PEAVCFUSManager@@EA, 0; CFUSManager * g_FUS_Manager
0x180025c46  jnz     short loc_180025C4D
0x180025c48  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025c4d  xor     edx, edx; Val
0x180025c4f  lea     r8d, [rdx+60h]; Size
0x180025c53  lea     rcx, [rbp+57h+pSid]; void *
0x180025c57  call    memset_0
0x180025c5c  lea     r8, [rbp+57h+pSid]; struct _WINBIO_FUS_EVENT *
0x180025c60  mov     edx, r14d; unsigned int
0x180025c63  call    ?RetrieveFUSTarget@CFUSManager@@QEAAJKPEAU_WINBIO_FUS_EVENT@@@Z; CFUSManager::RetrieveFUSTarget(ulong,_WINBIO_FUS_EVENT *)
0x180025c68  test    eax, eax
0x180025c6a  jns     short loc_180025CA6
0x180025c6c  cmp     [rbp+57h+var_A0], 0
0x180025c70  jz      short loc_180025C7B
0x180025c72  lea     rcx, [rbp+57h+hObject]; this
0x180025c76  call    ?RevertToSelf@CUserContext@@QEAAJXZ; CUserContext::RevertToSelf(void)
0x180025c7b  mov     [rbp+57h+var_A0], 0
0x180025c82  mov     rcx, [rbp+57h+hObject]; hObject
0x180025c86  test    rcx, rcx
0x180025c89  jz      short loc_180025C92
0x180025c8b  call    cs:__imp_CloseHandle
0x180025c91  nop
0x180025c92  mov     ecx, 0C0FFFFFFh; unsigned int
0x180025c97  call    ?NotifyClientDeparture@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientDeparture(uint)
0x180025c9c  mov     eax, 80098003h
0x180025ca1  jmp     loc_180025D73
0x180025ca6  cmp     dword ptr [rbp+57h+pSid], 3
0x180025caa  jnz     loc_180025D51
0x180025cb0  lea     rcx, [rbp+57h+pSid+8]; pSid
0x180025cb4  call    cs:__imp_IsValidSid
0x180025cba  test    eax, eax
0x180025cbc  jz      loc_180025D51
0x180025cc2  cmp     dword ptr [rbp+57h+pSid], 3
0x180025cc6  jnz     loc_180025D51
0x180025ccc  lea     rdx, [rbp+57h+pSid+8]; void *
0x180025cd0  call    ?IsCredProvEnabled@CUserContext@@QEBAHPEAX@Z; CUserContext::IsCredProvEnabled(void *)
0x180025cd5  test    eax, eax
0x180025cd7  jnz     short loc_180025CE0
0x180025cd9  mov     ebx, 80098030h
0x180025cde  jmp     short loc_180025D56
0x180025ce0  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180025ce8  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180025cec  call    cs:__imp_GetSystemTimeAsFileTime
0x180025cf2  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; lpFileTime2
0x180025cf6  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180025cfa  call    cs:__imp_CompareFileTime
0x180025d00  test    eax, eax
0x180025d02  js      short loc_180025D4A
0x180025d04  movaps  xmm0, [rbp+57h+pSid]
0x180025d08  movups  xmmword ptr [rbx], xmm0
0x180025d0b  movaps  xmm1, [rbp+57h+var_80]
0x180025d0f  movups  xmmword ptr [rbx+10h], xmm1
0x180025d13  movaps  xmm0, [rbp+57h+var_70]
0x180025d17  movups  xmmword ptr [rbx+20h], xmm0
0x180025d1b  movaps  xmm1, xmmword ptr [rbp+57h+var_60]
0x180025d1f  movups  xmmword ptr [rbx+30h], xmm1
0x180025d23  movups  xmm0, xmmword ptr [rbp+57h+var_60+0Ch]
0x180025d27  movups  xmmword ptr [rbx+3Ch], xmm0
0x180025d2b  mov     rax, [rbp+57h+var_40]
0x180025d2f  mov     [rdi], rax
0x180025d32  lea     rcx, [rbp+57h+hObject]; this
0x180025d36  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x180025d3b  nop
0x180025d3c  mov     ecx, 0C0FFFFFFh; unsigned int
0x180025d41  call    ?NotifyClientDeparture@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientDeparture(uint)
0x180025d46  xor     eax, eax
0x180025d48  jmp     short loc_180025D73
0x180025d4a  mov     ebx, 80070005h
0x180025d4f  jmp     short loc_180025D56
0x180025d51  mov     ebx, 80098003h
0x180025d56  lea     rcx, [rbp+57h+hObject]; this
0x180025d5a  call    ??1CUserContext@@QEAA@XZ; CUserContext::~CUserContext(void)
0x180025d5f  nop
0x180025d60  mov     ecx, 0C0FFFFFFh; unsigned int
0x180025d65  call    ?NotifyClientDeparture@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientDeparture(uint)
0x180025d6a  mov     eax, ebx
0x180025d6c  jmp     short loc_180025D73
0x180025d6e  mov     eax, 80070057h
0x180025d73  mov     rcx, [rbp+57h+var_28]
0x180025d77  xor     rcx, rsp; StackCookie
0x180025d7a  call    __security_check_cookie
0x180025d7f  add     rsp, 0B0h
0x180025d86  pop     r14
0x180025d88  pop     rdi
0x180025d89  pop     rsi
0x180025d8a  pop     rbx
0x180025d8b  pop     rbp
0x180025d8c  retn
```
