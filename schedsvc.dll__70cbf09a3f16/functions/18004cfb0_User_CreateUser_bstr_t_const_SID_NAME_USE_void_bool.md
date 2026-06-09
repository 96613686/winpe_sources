# User::CreateUser(_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x18004cfb0`
- end: `0x18004d506`
- name: `?CreateUser@User@@SA?AV1@AEBV_bstr_t@@W4_SID_NAME_USE@@PEAX_N@Z`
- size: `1366`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002d3d0`
- `0x180031ef0`

## callees

- `0x180001510`
- `0x180001520`
- `0x18000b4e0`
- `0x180028efc`
- `0x18002a320`
- `0x18002ac60`
- `0x18002b690`
- `0x180030f80`
- `0x1800322a0`
- `0x1800339c0`
- `0x180033b40`
- `0x18003d3f0`
- `0x180043fcc`
- `0x1800444bc`
- `0x18004ac58`
- `0x18004cfb0`
- `0x18004e274`
- `0x18004e3b8`
- `0x1800504b4`
- `0x18005250c`
- `0x18005790c`

## import_xrefs

- `msvcrt!wcschr` at `0x18004d0e1`
- `msvcrt!wcschr` at `0x18004d0e1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004d19f`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18004d19f`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d201`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d243`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d390`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d3f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d201`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d243`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d390`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d3f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d2c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d348`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d2c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d329`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d348`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004d366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d25a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d2b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d31d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d33c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d25a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d2b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d31d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004d33c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d23a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d3af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d3c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d411`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d42b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d23a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d3af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d3c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d411`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d42b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004cff7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004d032`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004d06d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004cff7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004d032`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004d06d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
User::UserEntry **__fastcall User::CreateUser(
        User::UserEntry **a1,
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
  const OLECHAR *v13; // rsi
  wchar_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  const OLECHAR *v17; // rbx
  __int64 v18; // rcx
  User::UserEntry *v19; // rcx
  OLECHAR *v20; // rax
  unsigned __int16 *v21; // rbx
  bool v22; // r8
  __int64 *v23; // rax
  BSTR *v24; // rbx
  BSTR v25; // r8
  struct _RTL_CRITICAL_SECTION *v26; // rsi
  User::UserEntry *v27; // rdi
  struct _RTL_CRITICAL_SECTION *v28; // rbx
  OLECHAR *v29; // rax
  __int64 v30; // rcx
  User::UserEntry *v31; // rdi
  struct _RTL_CRITICAL_SECTION *v32; // rbx
  struct _RTL_CRITICAL_SECTION *v33; // rbx
  BSTR *v34; // rbx
  BSTR v35; // r8
  BSTR *v36; // rbx
  BSTR v37; // r8
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 *v42; // rax
  const OLECHAR **v43; // r8
  const OLECHAR **v44; // r9
  const OLECHAR **v45; // r10
  User::UserEntry *v46; // [rsp+50h] [rbp-81h] BYREF
  enum _SID_NAME_USE v47; // [rsp+58h] [rbp-79h] BYREF
  LPVOID v48; // [rsp+60h] [rbp-71h] BYREF
  LPVOID v49; // [rsp+68h] [rbp-69h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-61h] BYREF
  const OLECHAR *v51; // [rsp+78h] [rbp-59h] BYREF
  const OLECHAR *v52[2]; // [rsp+80h] [rbp-51h] BYREF
  __int64 v53; // [rsp+90h] [rbp-41h] BYREF
  __int64 v54; // [rsp+98h] [rbp-39h] BYREF
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
        _bstr_t::operator=((__int64 *)&v49, (__int64 *)&v46);
        v46 = 0;
        _bstr_t::operator=((__int64 *)&v48, (__int64 *)&v46);
        if ( *a2 )
        {
          v13 = **a2;
          if ( v13 )
          {
            v14 = wcschr(**a2, 0x5Cu);
            v17 = v14;
            v18 = (unsigned int)dword_1800BC358;
            if ( (unsigned int)dword_1800BC358 > 4 )
            {
              v47 = a3;
              if ( *a2 )
                v19 = (User::UserEntry *)**a2;
              else
                v19 = 0;
              v46 = v19;
              v52[0] = v14;
              v51 = v13;
              lpMem = a4;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (__int64)v19,
                (unsigned __int8 *)byte_1800AD5C7,
                v15,
                v16,
                (__int64 *)&lpMem,
                &v51,
                v52,
                (const OLECHAR **)&v46,
                (__int64)&v47);
            }
            if ( !v17 || (v9 = v17 - v13, ++v17 == 0) || !*v17 )
            {
              if ( (unsigned int)dword_1800BC358 > 4 )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  v18,
                  (unsigned __int8 *)&word_1800AD596);
            }
            _bstr_t::operator=((BSTR **)&v49, v17);
            if ( (_DWORD)v9 )
            {
              v20 = SysAllocStringLen(0, v9);
              v21 = v20;
              v51 = v20;
              if ( !v20 )
                ATL::PrivateAtlThrow(0x8007000E);
              StringCchCopyNW(v20, (unsigned int)(v9 + 1), v13, (unsigned int)v9);
              v23 = (__int64 *)_bstr_t::_bstr_t((_bstr_t *)&lpMem, v21, v22);
              _bstr_t::operator=((__int64 *)&v48, v23);
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
            &v46,
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
          v29 = (OLECHAR *)operator new(0x30u);
          v51 = v29;
          if ( v29 )
            v31 = User::UserEntry::UserEntry(
                    (User::UserEntry *)v29,
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
            if ( (unsigned int)dword_1800BC358 > 2 && (unsigned __int8)tlgKeywordOn(v30, 0) )
            {
              v47 = v6;
              v39 = _bstr_t::operator unsigned short const *(a2);
              wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v51, v39);
              v40 = _bstr_t::operator unsigned short const *(&v48);
              wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v52, v40);
              v41 = _bstr_t::operator unsigned short const *(&v49);
              wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v53, v41);
              v42 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                      &v54,
                      (__int64)a4);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (__int64)&v47,
                (unsigned __int8 *)&dword_1800AD52C,
                (__int64)v43,
                (__int64)v44,
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
          ++*((_DWORD *)v31 + 11);
          LeaveCriticalSection(v32);
          *a1 = v31;
          v33 = User::s_cs;
          EnterCriticalSection(User::s_cs);
          ++*((_DWORD *)v31 + 11);
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
0x18004cfb0  mov     [rsp-8+arg_10], r8d
0x18004cfb5  push    rbp
0x18004cfb6  push    rbx
0x18004cfb7  push    rsi
0x18004cfb8  push    rdi
0x18004cfb9  push    r12
0x18004cfbb  push    r13
0x18004cfbd  push    r14
0x18004cfbf  push    r15
0x18004cfc1  lea     rbp, [rsp-17h]
0x18004cfc6  sub     rsp, 0E8h
0x18004cfcd  mov     r12, r9
0x18004cfd0  mov     ebx, r8d
0x18004cfd3  mov     r13, rdx
0x18004cfd6  mov     r15, rcx
0x18004cfd9  xor     edi, edi
0x18004cfdb  mov     [rbp+4Fh+var_B8], rdi
0x18004cfdf  mov     [rbp+4Fh+var_C0], rdi
0x18004cfe3  lea     rcx, [rsp+120h+var_D0]
0x18004cfe8  call    ?GetLocalSystem@User@@SA?AV1@XZ; User::GetLocalSystem(void)
0x18004cfed  mov     rcx, [rax]
0x18004cff0  mov     rdx, r12; pSid2
0x18004cff3  mov     rcx, [rcx+20h]; pSid1
0x18004cff7  call    cs:__imp_EqualSid
0x18004cffd  lea     rcx, [rsp+120h+var_D0]
0x18004d002  test    eax, eax
0x18004d004  jz      short loc_18004D019
0x18004d006  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004d00b  mov     rcx, r15
0x18004d00e  call    ?GetLocalSystem@User@@SA?AV1@XZ; User::GetLocalSystem(void)
0x18004d013  nop
0x18004d014  jmp     loc_18004D431
0x18004d019  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004d01e  lea     rcx, [rsp+120h+var_D0]
0x18004d023  call    ?GetLocalService@User@@SA?AV1@XZ; User::GetLocalService(void)
0x18004d028  mov     rcx, [rax]
0x18004d02b  mov     rdx, r12; pSid2
0x18004d02e  mov     rcx, [rcx+20h]; pSid1
0x18004d032  call    cs:__imp_EqualSid
0x18004d038  lea     rcx, [rsp+120h+var_D0]
0x18004d03d  test    eax, eax
0x18004d03f  jz      short loc_18004D054
0x18004d041  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004d046  mov     rcx, r15
0x18004d049  call    ?GetLocalService@User@@SA?AV1@XZ; User::GetLocalService(void)
0x18004d04e  nop
0x18004d04f  jmp     loc_18004D431
0x18004d054  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004d059  lea     rcx, [rsp+120h+var_D0]
0x18004d05e  call    ?GetNetworkService@User@@SA?AV1@XZ; User::GetNetworkService(void)
0x18004d063  mov     rcx, [rax]
0x18004d066  mov     rdx, r12; pSid2
0x18004d069  mov     rcx, [rcx+20h]; pSid1
0x18004d06d  call    cs:__imp_EqualSid
0x18004d073  lea     rcx, [rsp+120h+var_D0]
0x18004d078  test    eax, eax
0x18004d07a  jz      short loc_18004D08F
0x18004d07c  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004d081  mov     rcx, r15
0x18004d084  call    ?GetNetworkService@User@@SA?AV1@XZ; User::GetNetworkService(void)
0x18004d089  nop
0x18004d08a  jmp     loc_18004D431
0x18004d08f  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004d094  mov     [rsp+120h+var_D0], rdi
0x18004d099  lea     rdx, [rsp+120h+var_D0]
0x18004d09e  lea     rcx, [rbp+4Fh+var_B8]
0x18004d0a2  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004d0a7  mov     [rsp+120h+var_D0], rdi
0x18004d0ac  lea     rdx, [rsp+120h+var_D0]
0x18004d0b1  lea     rcx, [rbp+4Fh+var_C0]
0x18004d0b5  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004d0ba  mov     rsi, [r13+0]
0x18004d0be  mov     r14d, 0FFFFFFFFh
0x18004d0c4  test    rsi, rsi
0x18004d0c7  jz      loc_18004D24C
0x18004d0cd  mov     rsi, [rsi]
0x18004d0d0  test    rsi, rsi
0x18004d0d3  jz      loc_18004D24C
0x18004d0d9  mov     edx, 5Ch ; '\'; Ch
0x18004d0de  mov     rcx, rsi; Str
0x18004d0e1  call    cs:__imp_wcschr
0x18004d0e7  mov     rbx, rax
0x18004d0ea  mov     ecx, cs:dword_1800BC358
0x18004d0f0  cmp     ecx, 4
0x18004d0f3  jbe     short loc_18004D156
0x18004d0f5  mov     eax, [rbp+4Fh+arg_10]
0x18004d0f8  mov     [rbp+4Fh+var_C8], eax
0x18004d0fb  mov     rax, [r13+0]
0x18004d0ff  test    rax, rax
0x18004d102  jz      short loc_18004D109
0x18004d104  mov     rcx, [rax]
0x18004d107  jmp     short loc_18004D10B
0x18004d109  xor     ecx, ecx
0x18004d10b  mov     [rsp+120h+var_D0], rcx
0x18004d110  mov     [rbp+4Fh+var_A0], rbx
0x18004d114  mov     [rbp+4Fh+var_A8], rsi
0x18004d118  mov     [rbp+4Fh+lpMem], r12
0x18004d11c  lea     rax, [rbp+4Fh+var_C8]
0x18004d120  mov     [rsp+120h+var_E0], rax
0x18004d125  lea     rax, [rsp+120h+var_D0]
0x18004d12a  mov     [rsp+120h+var_E8], rax
0x18004d12f  lea     rax, [rbp+4Fh+var_A0]
0x18004d133  mov     [rsp+120h+var_F0], rax
0x18004d138  lea     rax, [rbp+4Fh+var_A8]
0x18004d13c  mov     qword ptr [rsp+120h+var_F8], rax
0x18004d141  lea     rax, [rbp+4Fh+lpMem]
0x18004d145  mov     qword ptr [rsp+120h+var_100], rax
0x18004d14a  lea     rdx, byte_1800AD5C7
0x18004d151  call    ??$Write@U?$_tlgWrapSid@U_SID@@@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSid@U_SID@@@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSid<_SID>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSid<_SID> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18004d156  test    rbx, rbx
0x18004d159  jz      short loc_18004D170
0x18004d15b  mov     rdi, rbx
0x18004d15e  sub     rdi, rsi
0x18004d161  sar     rdi, 1
0x18004d164  add     rbx, 2
0x18004d168  jz      short loc_18004D170
0x18004d16a  cmp     word ptr [rbx], 0
0x18004d16e  jnz     short loc_18004D187
0x18004d170  mov     eax, cs:dword_1800BC358
0x18004d176  cmp     eax, 4
0x18004d179  jbe     short loc_18004D187
0x18004d17b  lea     rdx, word_1800AD596
0x18004d182  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18004d187  mov     rdx, rbx
0x18004d18a  lea     rcx, [rbp+4Fh+var_B8]
0x18004d18e  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18004d193  test    edi, edi
0x18004d195  jz      loc_18004D249
0x18004d19b  mov     edx, edi; ui
0x18004d19d  xor     ecx, ecx; strIn
0x18004d19f  call    cs:__imp_SysAllocStringLen
0x18004d1a5  mov     rbx, rax
0x18004d1a8  mov     [rbp+4Fh+var_A8], rax
0x18004d1ac  test    rax, rax
0x18004d1af  jz      loc_18004D4FB
0x18004d1b5  mov     r9d, edi; unsigned __int64
0x18004d1b8  lea     edx, [rdi+1]; unsigned __int64
0x18004d1bb  mov     r8, rsi; unsigned __int16 *
0x18004d1be  mov     rcx, rax; unsigned __int16 *
0x18004d1c1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18004d1c6  mov     rdx, rbx; unsigned __int16 *
0x18004d1c9  lea     rcx, [rbp+4Fh+lpMem]; this
0x18004d1cd  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18004d1d2  mov     rdx, rax
0x18004d1d5  lea     rcx, [rbp+4Fh+var_C0]
0x18004d1d9  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18004d1de  mov     rbx, [rbp+4Fh+lpMem]
0x18004d1e2  test    rbx, rbx
0x18004d1e5  jz      short loc_18004D241
0x18004d1e7  mov     eax, r14d
0x18004d1ea  lock xadd [rbx+10h], eax
0x18004d1ef  cmp     eax, 1
0x18004d1f2  jnz     short loc_18004D241
0x18004d1f4  test    rbx, rbx
0x18004d1f7  jz      short loc_18004D241
0x18004d1f9  mov     rcx, [rbx]; bstrString
0x18004d1fc  test    rcx, rcx
0x18004d1ff  jz      short loc_18004D20E
0x18004d201  call    cs:__imp_SysFreeString
0x18004d207  mov     qword ptr [rbx], 0
0x18004d20e  mov     r8, [rbx+8]; lpMem
0x18004d212  test    r8, r8
0x18004d215  jz      short loc_18004D22E
0x18004d217  xor     edx, edx; dwFlags
0x18004d219  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004d220  call    cs:__imp_HeapFree
0x18004d226  mov     qword ptr [rbx+8], 0
0x18004d22e  mov     r8, rbx; lpMem
0x18004d231  xor     edx, edx; dwFlags
0x18004d233  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004d23a  call    cs:__imp_HeapFree
0x18004d240  nop
0x18004d241  xor     ecx, ecx; bstrString
0x18004d243  call    cs:__imp_SysFreeString
0x18004d249  mov     ebx, [rbp+4Fh+arg_10]
0x18004d24c  mov     rsi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18004d253  mov     [rbp+4Fh+lpMem], rsi
0x18004d257  mov     rcx, rsi; lpCriticalSection
0x18004d25a  call    cs:__imp_EnterCriticalSection
0x18004d260  nop
0x18004d261  mov     rdx, r12
0x18004d264  lea     rcx, [rsp+120h+var_D0]
0x18004d269  call    ?LookupUser@User@@CA?AV1@PEAX@Z; User::LookupUser(void *)
0x18004d26e  nop
0x18004d26f  mov     rdi, [rsp+120h+var_D0]
0x18004d274  test    rdi, rdi
0x18004d277  jz      short loc_18004D2CC
0x18004d279  movzx   eax, [rbp+4Fh+arg_20]
0x18004d27d  mov     byte ptr [rsp+120h+var_F0], al; bool
0x18004d281  mov     qword ptr [rsp+120h+var_F8], r12; void *
0x18004d286  mov     [rsp+120h+var_100], ebx; enum _SID_NAME_USE
0x18004d28a  mov     r9, r13; struct _bstr_t *
0x18004d28d  lea     r8, [rbp+4Fh+var_C0]; struct _bstr_t *
0x18004d291  lea     rdx, [rbp+4Fh+var_B8]; struct _bstr_t *
0x18004d295  lea     rcx, [rsp+120h+var_D0]; this
0x18004d29a  call    ?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z; User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)
0x18004d29f  mov     [r15], rdi
0x18004d2a2  test    rdi, rdi
0x18004d2a5  jz      loc_18004D358
0x18004d2ab  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18004d2b2  mov     rcx, rbx; lpCriticalSection
0x18004d2b5  call    cs:__imp_EnterCriticalSection
0x18004d2bb  inc     dword ptr [rdi+2Ch]
0x18004d2be  mov     rcx, rbx; lpCriticalSection
0x18004d2c1  call    cs:__imp_LeaveCriticalSection
0x18004d2c7  jmp     loc_18004D358
0x18004d2cc  mov     ecx, 30h ; '0'; dwBytes
0x18004d2d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d2d6  mov     [rbp+4Fh+var_A8], rax
0x18004d2da  test    rax, rax
0x18004d2dd  jz      short loc_18004D304
0x18004d2df  mov     [rsp+120h+var_F0], r12; void *
0x18004d2e4  mov     [rsp+120h+var_F8], ebx; enum _SID_NAME_USE
0x18004d2e8  mov     qword ptr [rsp+120h+var_100], r13; struct _bstr_t *
0x18004d2ed  lea     r9, [rbp+4Fh+var_C0]; struct _bstr_t *
0x18004d2f1  lea     r8, [rbp+4Fh+var_B8]; struct _bstr_t *
0x18004d2f5  xor     edx, edx; bool
0x18004d2f7  mov     rcx, rax; this
0x18004d2fa  call    ??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z; User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)
0x18004d2ff  mov     rdi, rax
0x18004d302  jmp     short loc_18004D306
0x18004d304  xor     edi, edi
0x18004d306  test    rdi, rdi
0x18004d309  jz      loc_18004D448
0x18004d30f  mov     [rbp+4Fh+lpMem], rdi
0x18004d313  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18004d31a  mov     rcx, rbx; lpCriticalSection
0x18004d31d  call    cs:__imp_EnterCriticalSection
0x18004d323  inc     dword ptr [rdi+2Ch]
0x18004d326  mov     rcx, rbx; lpCriticalSection
0x18004d329  call    cs:__imp_LeaveCriticalSection
0x18004d32f  mov     [r15], rdi
0x18004d332  mov     rbx, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18004d339  mov     rcx, rbx; lpCriticalSection
0x18004d33c  call    cs:__imp_EnterCriticalSection
0x18004d342  inc     dword ptr [rdi+2Ch]
0x18004d345  mov     rcx, rbx; lpCriticalSection
0x18004d348  call    cs:__imp_LeaveCriticalSection
0x18004d34e  lea     rcx, [rbp+4Fh+lpMem]
0x18004d352  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004d357  nop
0x18004d358  lea     rcx, [rsp+120h+var_D0]
0x18004d35d  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x18004d362  nop
0x18004d363  mov     rcx, rsi; lpCriticalSection
0x18004d366  call    cs:__imp_LeaveCriticalSection
0x18004d36c  nop
0x18004d36d  mov     rbx, [rbp+4Fh+var_C0]
0x18004d371  test    rbx, rbx
0x18004d374  jz      short loc_18004D3D0
0x18004d376  mov     eax, r14d
0x18004d379  lock xadd [rbx+10h], eax
0x18004d37e  cmp     eax, 1
0x18004d381  jnz     short loc_18004D3D0
0x18004d383  test    rbx, rbx
0x18004d386  jz      short loc_18004D3D0
0x18004d388  mov     rcx, [rbx]; bstrString
0x18004d38b  test    rcx, rcx
0x18004d38e  jz      short loc_18004D39D
0x18004d390  call    cs:__imp_SysFreeString
0x18004d396  mov     qword ptr [rbx], 0
0x18004d39d  mov     r8, [rbx+8]; lpMem
0x18004d3a1  test    r8, r8
0x18004d3a4  jz      short loc_18004D3BD
0x18004d3a6  xor     edx, edx; dwFlags
0x18004d3a8  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004d3af  call    cs:__imp_HeapFree
0x18004d3b5  mov     qword ptr [rbx+8], 0
0x18004d3bd  mov     r8, rbx; lpMem
0x18004d3c0  xor     edx, edx; dwFlags
0x18004d3c2  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004d3c9  call    cs:__imp_HeapFree
0x18004d3cf  nop
0x18004d3d0  mov     rbx, [rbp+4Fh+var_B8]
0x18004d3d4  test    rbx, rbx
0x18004d3d7  jz      short loc_18004D431
0x18004d3d9  lock xadd [rbx+10h], r14d
0x18004d3df  cmp     r14d, 1
0x18004d3e3  jnz     short loc_18004D431
0x18004d3e5  test    rbx, rbx
0x18004d3e8  jz      short loc_18004D431
0x18004d3ea  mov     rcx, [rbx]; bstrString
0x18004d3ed  test    rcx, rcx
0x18004d3f0  jz      short loc_18004D3FF
0x18004d3f2  call    cs:__imp_SysFreeString
0x18004d3f8  mov     qword ptr [rbx], 0
0x18004d3ff  mov     r8, [rbx+8]; lpMem
0x18004d403  test    r8, r8
0x18004d406  jz      short loc_18004D41F
0x18004d408  xor     edx, edx; dwFlags
0x18004d40a  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004d411  call    cs:__imp_HeapFree
0x18004d417  mov     qword ptr [rbx+8], 0
0x18004d41f  mov     r8, rbx; lpMem
0x18004d422  xor     edx, edx; dwFlags
0x18004d424  mov     rcx, cs:?g_PrivateHeap@@3VPrivateHeap@@A; hHeap
0x18004d42b  call    cs:__imp_HeapFree
0x18004d431  mov     rax, r15
0x18004d434  add     rsp, 0E8h
0x18004d43b  pop     r15
  ... truncated ...
```
