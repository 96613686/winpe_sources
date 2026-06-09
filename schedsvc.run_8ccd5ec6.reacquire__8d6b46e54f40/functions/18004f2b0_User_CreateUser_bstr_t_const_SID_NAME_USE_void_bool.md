# User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x18004f2b0`
- end: `0x18004f891`
- name: `?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z`
- size: `1505`
- prototype: `static struct User __high(const struct _bstr_t *, enum _SID_NAME_USE, void *, bool)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800044fc`
- `0x18001d1e0`

## callees

- `0x180001534`
- `0x180001544`
- `0x180001d10`
- `0x180002790`
- `0x18000fe50`
- `0x180017820`
- `0x18001d130`
- `0x180027910`
- `0x180030620`
- `0x180034c40`
- `0x18003bb74`
- `0x18003dfb0`
- `0x1800460dc`
- `0x18004658c`
- `0x18004d0cc`
- `0x18004f2b0`
- `0x180050660`
- `0x1800507b4`
- `0x1800529a0`
- `0x180054bd8`
- `0x18005a2bc`

## import_xrefs

- `msvcrt!wcschr` at `0x18004f3f3`
- `msvcrt!wcschr` at `0x18004f3f3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004f4b7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004f4b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f51f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f573`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f6f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f76a`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f51f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f573`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f6f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18004f76a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f6a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f6c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f603`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f677`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f6a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f6c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f590`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f5f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f665`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f590`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f5f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f665`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f690`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f544`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f564`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f71b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f73b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f78f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f7af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f544`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f564`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f71b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f73b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f78f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f7af`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004f2f7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004f338`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004f379`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004f2f7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004f338`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004f379`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
const wchar_t **__fastcall User::CreateUser(
        const wchar_t **a1,
        const wchar_t ***a2,
        enum _SID_NAME_USE a3,
        void *a4,
        bool a5)
{
  enum _SID_NAME_USE v6; // ebx
  __int64 v9; // rdi
  __int64 LocalSystem; // rax
  __int64 LocalService; // rax
  __int64 NetworkService; // rax
  const unsigned __int16 *v13; // rsi
  wchar_t *v14; // rax
  int v15; // r8d
  int v16; // r9d
  wchar_t *v17; // rbx
  __int64 v18; // rcx
  const wchar_t *v19; // rcx
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rbx
  bool v22; // r8
  _bstr_t *v23; // rax
  BSTR *v24; // rbx
  BSTR v25; // r8
  struct _RTL_CRITICAL_SECTION *v26; // rsi
  const wchar_t *v27; // rdi
  struct _RTL_CRITICAL_SECTION *v28; // rbx
  User::UserEntry *v29; // rax
  __int64 v30; // rcx
  _DWORD *v31; // rdi
  struct _RTL_CRITICAL_SECTION *v32; // rbx
  struct _RTL_CRITICAL_SECTION *v33; // rbx
  BSTR *v34; // rbx
  BSTR v35; // r8
  BSTR *v36; // rbx
  BSTR v37; // r8
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // r10
  const wchar_t *v46; // [rsp+50h] [rbp-81h] BYREF
  enum _SID_NAME_USE v47; // [rsp+58h] [rbp-79h] BYREF
  LPVOID v48; // [rsp+60h] [rbp-71h] BYREF
  LPVOID v49; // [rsp+68h] [rbp-69h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-61h] BYREF
  void *v51; // [rsp+78h] [rbp-59h] BYREF
  _QWORD v52[2]; // [rsp+80h] [rbp-51h] BYREF
  char v53[8]; // [rsp+90h] [rbp-41h] BYREF
  char v54[8]; // [rsp+98h] [rbp-39h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+A0h] [rbp-31h] BYREF

  v6 = a3;
  LODWORD(v9) = 0;
  v49 = 0;
  v48 = 0;
  LocalSystem = User::GetLocalSystem(&v46);
  if ( EqualSid(*(PSID *)(*(_QWORD *)LocalSystem + 32LL), a4) )
  {
    wmi::AutoRef<User::UserEntry>::Release(&v46);
    User::GetLocalSystem(a1);
  }
  else
  {
    wmi::AutoRef<User::UserEntry>::Release(&v46);
    LocalService = User::GetLocalService(&v46);
    if ( EqualSid(*(PSID *)(*(_QWORD *)LocalService + 32LL), a4) )
    {
      wmi::AutoRef<User::UserEntry>::Release(&v46);
      User::GetLocalService(a1);
    }
    else
    {
      wmi::AutoRef<User::UserEntry>::Release(&v46);
      NetworkService = User::GetNetworkService(&v46);
      if ( EqualSid(*(PSID *)(*(_QWORD *)NetworkService + 32LL), a4) )
      {
        wmi::AutoRef<User::UserEntry>::Release(&v46);
        User::GetNetworkService(a1);
      }
      else
      {
        wmi::AutoRef<User::UserEntry>::Release(&v46);
        v46 = 0;
        _bstr_t::operator=(&v49, &v46);
        v46 = 0;
        _bstr_t::operator=(&v48, &v46);
        if ( *a2 )
        {
          v13 = **a2;
          if ( v13 )
          {
            v14 = wcschr(**a2, 0x5Cu);
            v17 = v14;
            v18 = (unsigned int)dword_1800C0358;
            if ( (unsigned int)dword_1800C0358 > 4 )
            {
              v47 = a3;
              if ( *a2 )
                v19 = **a2;
              else
                v19 = 0;
              v46 = v19;
              v52[0] = v14;
              v51 = (void *)v13;
              lpMem = a4;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (_DWORD)v19,
                (unsigned int)&byte_1800B160F,
                v15,
                v16,
                (__int64)&lpMem,
                (__int64)&v51,
                (__int64)v52,
                (__int64)&v46,
                (__int64)&v47);
            }
            if ( !v17 || (v9 = v17 - v13, ++v17 == 0) || !*v17 )
            {
              if ( (unsigned int)dword_1800C0358 > 4 )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  v18,
                  &word_1800B15DE);
            }
            _bstr_t::operator=(&v49, v17);
            if ( (_DWORD)v9 )
            {
              v20 = SysAllocStringLen(0, v9);
              v21 = v20;
              v51 = v20;
              if ( !v20 )
                ATL::PrivateAtlThrow(0x8007000E);
              StringCchCopyNW(v20, (unsigned int)(v9 + 1), v13, (unsigned int)v9);
              v23 = _bstr_t::_bstr_t((_bstr_t *)&lpMem, v21, v22);
              _bstr_t::operator=(&v48, v23);
              v24 = (BSTR *)lpMem;
              if ( lpMem && _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 4, 0xFFFFFFFF) == 1 && v24 )
              {
                if ( *v24 )
                {
                  SysFreeString(*v24);
                  *v24 = 0;
                }
                v25 = v24[1];
                if ( v25 )
                {
                  HeapFree(g_PrivateHeap, 0, v25);
                  v24[1] = 0;
                }
                HeapFree(g_PrivateHeap, 0, v24);
              }
              SysFreeString(0);
            }
            v6 = a3;
          }
        }
        v26 = User::s_cs;
        lpMem = User::s_cs;
        EnterCriticalSection(User::s_cs);
        User::LookupUser(&v46, a4);
        v27 = v46;
        if ( v46 )
        {
          User::UpdateEntry(
            (User *)&v46,
            (const struct _bstr_t *)&v49,
            (const struct _bstr_t *)&v48,
            (const struct _bstr_t *)a2,
            v6,
            a4,
            a5);
          *a1 = v27;
          v28 = User::s_cs;
          EnterCriticalSection(User::s_cs);
          ++*((_DWORD *)v27 + 11);
          LeaveCriticalSection(v28);
        }
        else
        {
          v29 = (User::UserEntry *)operator new(0x30u);
          v51 = v29;
          if ( v29 )
            v31 = (_DWORD *)User::UserEntry::UserEntry(
                              v29,
                              0,
                              (const struct _bstr_t *)&v49,
                              (const struct _bstr_t *)&v48,
                              (const struct _bstr_t *)a2,
                              v6,
                              a4);
          else
            v31 = 0;
          if ( !v31 )
          {
            if ( (unsigned int)dword_1800C0358 > 2 && (unsigned __int8)tlgKeywordOn(v30, 0) )
            {
              v47 = v6;
              v39 = _bstr_t::operator unsigned short const *(a2);
              wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v51, v39);
              v40 = _bstr_t::operator unsigned short const *(&v48);
              wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v52, v40);
              v41 = _bstr_t::operator unsigned short const *(&v49);
              wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v53, v41);
              v42 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                      v54,
                      a4);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (unsigned int)&v47,
                (unsigned int)&dword_1800B1574,
                v43,
                v44,
                v42,
                v43,
                v44,
                v45,
                (__int64)&v47);
            }
            wmi::OutOfMemoryException::OutOfMemoryException((wmi::OutOfMemoryException *)pExceptionObject);
            throw (wmi::OutOfMemoryException *)pExceptionObject;
          }
          lpMem = v31;
          v32 = User::s_cs;
          EnterCriticalSection(User::s_cs);
          ++v31[11];
          LeaveCriticalSection(v32);
          *a1 = (const wchar_t *)v31;
          v33 = User::s_cs;
          EnterCriticalSection(User::s_cs);
          ++v31[11];
          LeaveCriticalSection(v33);
          wmi::AutoRef<User::UserEntry>::Release(&lpMem);
        }
        wmi::AutoRef<User::UserEntry>::Release(&v46);
        LeaveCriticalSection(v26);
        v34 = (BSTR *)v48;
        if ( v48 && _InterlockedExchangeAdd((volatile signed __int32 *)v48 + 4, 0xFFFFFFFF) == 1 && v34 )
        {
          if ( *v34 )
          {
            SysFreeString(*v34);
            *v34 = 0;
          }
          v35 = v34[1];
          if ( v35 )
          {
            HeapFree(g_PrivateHeap, 0, v35);
            v34[1] = 0;
          }
          HeapFree(g_PrivateHeap, 0, v34);
        }
        v36 = (BSTR *)v49;
        if ( v49 && _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 4, 0xFFFFFFFF) == 1 && v36 )
        {
          if ( *v36 )
          {
            SysFreeString(*v36);
            *v36 = 0;
          }
          v37 = v36[1];
          if ( v37 )
          {
            HeapFree(g_PrivateHeap, 0, v37);
            v36[1] = 0;
          }
          HeapFree(g_PrivateHeap, 0, v36);
        }
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18004f2b0  mov     [rsp-8+arg_10], r8d
0x18004f2b5  push    rbp
0x18004f2b6  push    rbx
0x18004f2b7  push    rsi
0x18004f2b8  push    rdi
0x18004f2b9  push    r12
0x18004f2bb  push    r13
0x18004f2bd  push    r14
0x18004f2bf  push    r15
0x18004f2c1  lea     rbp, [rsp-17h]
0x18004f2c6  sub     rsp, 0E8h
0x18004f2cd  mov     r12, r9
0x18004f2d0  mov     ebx, r8d
0x18004f2d3  mov     r13, rdx
0x18004f2d6  mov     r15, rcx
0x18004f2d9  xor     edi, edi
0x18004f2db  mov     [rbp+4Fh+var_B8], rdi
0x18004f2df  mov     [rbp+4Fh+var_C0], rdi
0x18004f2e3  lea     rcx, [rsp+120h+var_D0]
0x18004f2e8  call    ?GetLocalSystem@User@@SA?AV1@XZ; User::GetLocalSystem(void)
0x18004f2ed  mov     rcx, [rax]
0x18004f2f0  mov     rdx, r12; pSid2
0x18004f2f3  mov     rcx, [rcx+20h]; pSid1
0x18004f2f7  call    cs:__imp_EqualSid
0x18004f2fe  nop     dword ptr [rax+rax+00h]
0x18004f303  lea     rcx, [rsp+120h+var_D0]
0x18004f308  test    eax, eax
0x18004f30a  jz      short loc_18004F31F
0x18004f30c  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004f311  mov     rcx, r15
0x18004f314  call    ?GetLocalSystem@User@@SA?AV1@XZ; User::GetLocalSystem(void)
0x18004f319  nop
0x18004f31a  jmp     loc_18004F7BB
0x18004f31f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004f324  lea     rcx, [rsp+120h+var_D0]
0x18004f329  call    ?GetLocalService@User@@SA?AV1@XZ; User::GetLocalService(void)
0x18004f32e  mov     rcx, [rax]
0x18004f331  mov     rdx, r12; pSid2
0x18004f334  mov     rcx, [rcx+20h]; pSid1
0x18004f338  call    cs:__imp_EqualSid
0x18004f33f  nop     dword ptr [rax+rax+00h]
0x18004f344  lea     rcx, [rsp+120h+var_D0]
0x18004f349  test    eax, eax
0x18004f34b  jz      short loc_18004F360
0x18004f34d  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004f352  mov     rcx, r15
0x18004f355  call    ?GetLocalService@User@@SA?AV1@XZ; User::GetLocalService(void)
0x18004f35a  nop
0x18004f35b  jmp     loc_18004F7BB
0x18004f360  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004f365  lea     rcx, [rsp+120h+var_D0]
0x18004f36a  call    ?GetNetworkService@User@@SA?AV1@XZ; User::GetNetworkService(void)
0x18004f36f  mov     rcx, [rax]
0x18004f372  mov     rdx, r12; pSid2
0x18004f375  mov     rcx, [rcx+20h]; pSid1
0x18004f379  call    cs:__imp_EqualSid
0x18004f380  nop     dword ptr [rax+rax+00h]
0x18004f385  lea     rcx, [rsp+120h+var_D0]
0x18004f38a  test    eax, eax
0x18004f38c  jz      short loc_18004F3A1
0x18004f38e  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004f393  mov     rcx, r15
0x18004f396  call    ?GetNetworkService@User@@SA?AV1@XZ; User::GetNetworkService(void)
0x18004f39b  nop
0x18004f39c  jmp     loc_18004F7BB
0x18004f3a1  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004f3a6  mov     [rsp+120h+var_D0], rdi
0x18004f3ab  lea     rdx, [rsp+120h+var_D0]
0x18004f3b0  lea     rcx, [rbp+4Fh+var_B8]
0x18004f3b4  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004f3b9  mov     [rsp+120h+var_D0], rdi
0x18004f3be  lea     rdx, [rsp+120h+var_D0]
0x18004f3c3  lea     rcx, [rbp+4Fh+var_C0]
0x18004f3c7  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004f3cc  mov     rsi, [r13+0]
0x18004f3d0  mov     r14d, 0FFFFFFFFh
0x18004f3d6  test    rsi, rsi
0x18004f3d9  jz      loc_18004F582
0x18004f3df  mov     rsi, [rsi]
0x18004f3e2  test    rsi, rsi
0x18004f3e5  jz      loc_18004F582
0x18004f3eb  mov     edx, 5Ch ; '\'; Ch
0x18004f3f0  mov     rcx, rsi; Str
0x18004f3f3  call    cs:__imp_wcschr
0x18004f3fa  nop     dword ptr [rax+rax+00h]
0x18004f3ff  mov     rbx, rax
0x18004f402  mov     ecx, cs:dword_1800C0358
0x18004f408  cmp     ecx, 4
0x18004f40b  jbe     short loc_18004F46E
0x18004f40d  mov     eax, [rbp+4Fh+arg_10]
0x18004f410  mov     [rbp+4Fh+var_C8], eax
0x18004f413  mov     rax, [r13+0]
0x18004f417  test    rax, rax
0x18004f41a  jz      short loc_18004F421
0x18004f41c  mov     rcx, [rax]
0x18004f41f  jmp     short loc_18004F423
0x18004f421  xor     ecx, ecx
0x18004f423  mov     [rsp+120h+var_D0], rcx
0x18004f428  mov     [rbp+4Fh+var_A0], rbx
0x18004f42c  mov     [rbp+4Fh+var_A8], rsi
0x18004f430  mov     [rbp+4Fh+lpMem], r12
0x18004f434  lea     rax, [rbp+4Fh+var_C8]
0x18004f438  mov     [rsp+120h+var_E0], rax
0x18004f43d  lea     rax, [rsp+120h+var_D0]
0x18004f442  mov     [rsp+120h+var_E8], rax
0x18004f447  lea     rax, [rbp+4Fh+var_A0]
0x18004f44b  mov     [rsp+120h+var_F0], rax
0x18004f450  lea     rax, [rbp+4Fh+var_A8]
0x18004f454  mov     qword ptr [rsp+120h+var_F8], rax
0x18004f459  lea     rax, [rbp+4Fh+lpMem]
0x18004f45d  mov     qword ptr [rsp+120h+var_100], rax
0x18004f462  lea     rdx, byte_1800B160F
0x18004f469  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18004f46e  test    rbx, rbx
0x18004f471  jz      short loc_18004F488
0x18004f473  mov     rdi, rbx
0x18004f476  sub     rdi, rsi
0x18004f479  sar     rdi, 1
0x18004f47c  add     rbx, 2
0x18004f480  jz      short loc_18004F488
0x18004f482  cmp     word ptr [rbx], 0
0x18004f486  jnz     short loc_18004F49F
0x18004f488  mov     eax, cs:dword_1800C0358
0x18004f48e  cmp     eax, 4
0x18004f491  jbe     short loc_18004F49F
0x18004f493  lea     rdx, word_1800B15DE
0x18004f49a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18004f49f  mov     rdx, rbx
0x18004f4a2  lea     rcx, [rbp+4Fh+var_B8]
0x18004f4a6  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18004f4ab  test    edi, edi
0x18004f4ad  jz      loc_18004F57F
0x18004f4b3  mov     edx, edi; ui
0x18004f4b5  xor     ecx, ecx; strIn
0x18004f4b7  call    cs:__imp_SysAllocStringLen
0x18004f4be  nop     dword ptr [rax+rax+00h]
0x18004f4c3  mov     rbx, rax
0x18004f4c6  mov     [rbp+4Fh+var_A8], rax
0x18004f4ca  test    rax, rax
0x18004f4cd  jz      loc_18004F886
0x18004f4d3  mov     r9d, edi; unsigned __int64
0x18004f4d6  lea     edx, [rdi+1]; unsigned __int64
0x18004f4d9  mov     r8, rsi; unsigned __int16 *
0x18004f4dc  mov     rcx, rax; unsigned __int16 *
0x18004f4df  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004f4e4  mov     rdx, rbx; unsigned __int16 *
0x18004f4e7  lea     rcx, [rbp+4Fh+lpMem]; this
0x18004f4eb  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18004f4f0  mov     rdx, rax
0x18004f4f3  lea     rcx, [rbp+4Fh+var_C0]
0x18004f4f7  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004f4fc  mov     rbx, [rbp+4Fh+lpMem]
0x18004f500  test    rbx, rbx
0x18004f503  jz      short loc_18004F571
0x18004f505  mov     eax, r14d
0x18004f508  lock xadd [rbx+10h], eax
0x18004f50d  cmp     eax, 1
0x18004f510  jnz     short loc_18004F571
0x18004f512  test    rbx, rbx
0x18004f515  jz      short loc_18004F571
0x18004f517  mov     rcx, [rbx]; bstrString
0x18004f51a  test    rcx, rcx
0x18004f51d  jz      short loc_18004F532
0x18004f51f  call    cs:__imp_SysFreeString
0x18004f526  nop     dword ptr [rax+rax+00h]
0x18004f52b  mov     qword ptr [rbx], 0
0x18004f532  mov     r8, [rbx+8]; lpMem
0x18004f536  test    r8, r8
0x18004f539  jz      short loc_18004F558
0x18004f53b  xor     edx, edx; dwFlags
0x18004f53d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004f544  call    cs:__imp_HeapFree
0x18004f54b  nop     dword ptr [rax+rax+00h]
0x18004f550  mov     qword ptr [rbx+8], 0
0x18004f558  mov     r8, rbx; lpMem
0x18004f55b  xor     edx, edx; dwFlags
0x18004f55d  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004f564  call    cs:__imp_HeapFree
0x18004f56b  nop     dword ptr [rax+rax+00h]
0x18004f570  nop
0x18004f571  xor     ecx, ecx; bstrString
0x18004f573  call    cs:__imp_SysFreeString
0x18004f57a  nop     dword ptr [rax+rax+00h]
0x18004f57f  mov     ebx, [rbp+4Fh+arg_10]
0x18004f582  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18004f589  mov     [rbp+4Fh+lpMem], rsi
0x18004f58d  mov     rcx, rsi; lpCriticalSection
0x18004f590  call    cs:__imp_EnterCriticalSection
0x18004f597  nop     dword ptr [rax+rax+00h]
0x18004f59c  nop
0x18004f59d  mov     rdx, r12
0x18004f5a0  lea     rcx, [rsp+120h+var_D0]
0x18004f5a5  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x18004f5aa  nop
0x18004f5ab  mov     rdi, [rsp+120h+var_D0]
0x18004f5b0  test    rdi, rdi
0x18004f5b3  jz      short loc_18004F614
0x18004f5b5  movzx   eax, [rbp+4Fh+arg_20]
0x18004f5b9  mov     byte ptr [rsp+120h+var_F0], al; bool
0x18004f5bd  mov     qword ptr [rsp+120h+var_F8], r12; void *
0x18004f5c2  mov     [rsp+120h+var_100], ebx; enum _SID_NAME_USE
0x18004f5c6  mov     r9, r13; struct _bstr_t *
0x18004f5c9  lea     r8, [rbp+4Fh+var_C0]; struct _bstr_t *
0x18004f5cd  lea     rdx, [rbp+4Fh+var_B8]; struct _bstr_t *
0x18004f5d1  lea     rcx, [rsp+120h+var_D0]; this
0x18004f5d6  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18004f5db  mov     [r15], rdi
0x18004f5de  test    rdi, rdi
0x18004f5e1  jz      loc_18004F6B8
0x18004f5e7  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18004f5ee  mov     rcx, rbx; lpCriticalSection
0x18004f5f1  call    cs:__imp_EnterCriticalSection
0x18004f5f8  nop     dword ptr [rax+rax+00h]
0x18004f5fd  inc     dword ptr [rdi+2Ch]
0x18004f600  mov     rcx, rbx; lpCriticalSection
0x18004f603  call    cs:__imp_LeaveCriticalSection
0x18004f60a  nop     dword ptr [rax+rax+00h]
0x18004f60f  jmp     loc_18004F6B8
0x18004f614  mov     ecx, 30h ; '0'; dwBytes
0x18004f619  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f61e  mov     [rbp+4Fh+var_A8], rax
0x18004f622  test    rax, rax
0x18004f625  jz      short loc_18004F64C
0x18004f627  mov     [rsp+120h+var_F0], r12; void *
0x18004f62c  mov     [rsp+120h+var_F8], ebx; enum _SID_NAME_USE
0x18004f630  mov     qword ptr [rsp+120h+var_100], r13; struct _bstr_t *
0x18004f635  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x18004f639  lea     r8, [rbp+4Fh+var_B8]; struct _bstr_t *
0x18004f63d  xor     edx, edx; bool
0x18004f63f  mov     rcx, rax; this
0x18004f642  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18004f647  mov     rdi, rax
0x18004f64a  jmp     short loc_18004F64E
0x18004f64c  xor     edi, edi
0x18004f64e  test    rdi, rdi
0x18004f651  jz      loc_18004F7D3
0x18004f657  mov     [rbp+4Fh+lpMem], rdi
0x18004f65b  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18004f662  mov     rcx, rbx; lpCriticalSection
0x18004f665  call    cs:__imp_EnterCriticalSection
0x18004f66c  nop     dword ptr [rax+rax+00h]
0x18004f671  inc     dword ptr [rdi+2Ch]
0x18004f674  mov     rcx, rbx; lpCriticalSection
0x18004f677  call    cs:__imp_LeaveCriticalSection
0x18004f67e  nop     dword ptr [rax+rax+00h]
0x18004f683  mov     [r15], rdi
0x18004f686  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18004f68d  mov     rcx, rbx; lpCriticalSection
0x18004f690  call    cs:__imp_EnterCriticalSection
0x18004f697  nop     dword ptr [rax+rax+00h]
0x18004f69c  inc     dword ptr [rdi+2Ch]
0x18004f69f  mov     rcx, rbx; lpCriticalSection
0x18004f6a2  call    cs:__imp_LeaveCriticalSection
0x18004f6a9  nop     dword ptr [rax+rax+00h]
0x18004f6ae  lea     rcx, [rbp+4Fh+lpMem]
0x18004f6b2  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004f6b7  nop
0x18004f6b8  lea     rcx, [rsp+120h+var_D0]
0x18004f6bd  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004f6c2  nop
0x18004f6c3  mov     rcx, rsi; lpCriticalSection
0x18004f6c6  call    cs:__imp_LeaveCriticalSection
0x18004f6cd  nop     dword ptr [rax+rax+00h]
0x18004f6d2  nop
0x18004f6d3  mov     rbx, [rbp+4Fh+var_C0]
0x18004f6d7  test    rbx, rbx
0x18004f6da  jz      short loc_18004F748
0x18004f6dc  mov     eax, r14d
0x18004f6df  lock xadd [rbx+10h], eax
0x18004f6e4  cmp     eax, 1
0x18004f6e7  jnz     short loc_18004F748
0x18004f6e9  test    rbx, rbx
0x18004f6ec  jz      short loc_18004F748
0x18004f6ee  mov     rcx, [rbx]; bstrString
0x18004f6f1  test    rcx, rcx
0x18004f6f4  jz      short loc_18004F709
0x18004f6f6  call    cs:__imp_SysFreeString
0x18004f6fd  nop     dword ptr [rax+rax+00h]
0x18004f702  mov     qword ptr [rbx], 0
0x18004f709  mov     r8, [rbx+8]; lpMem
0x18004f70d  test    r8, r8
0x18004f710  jz      short loc_18004F72F
0x18004f712  xor     edx, edx; dwFlags
0x18004f714  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004f71b  call    cs:__imp_HeapFree
0x18004f722  nop     dword ptr [rax+rax+00h]
0x18004f727  mov     qword ptr [rbx+8], 0
0x18004f72f  mov     r8, rbx; lpMem
0x18004f732  xor     edx, edx; dwFlags
0x18004f734  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004f73b  call    cs:__imp_HeapFree
0x18004f742  nop     dword ptr [rax+rax+00h]
0x18004f747  nop
0x18004f748  mov     rbx, [rbp+4Fh+var_B8]
0x18004f74c  test    rbx, rbx
0x18004f74f  jz      short loc_18004F7BB
0x18004f751  lock xadd [rbx+10h], r14d
0x18004f757  cmp     r14d, 1
0x18004f75b  jnz     short loc_18004F7BB
0x18004f75d  test    rbx, rbx
  ... truncated ...
```
