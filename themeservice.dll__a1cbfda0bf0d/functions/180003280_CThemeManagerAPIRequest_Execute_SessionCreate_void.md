# CThemeManagerAPIRequest::Execute_SessionCreate(void)

- ea: `0x180003280`
- end: `0x18000342c`
- name: `?Execute_SessionCreate@CThemeManagerAPIRequest@@AEAAJXZ`
- size: `428`
- prototype: `__int64 __fastcall(CThemeManagerAPIRequest *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180002270`

## callees

- `0x180003280`
- `0x180003434`
- `0x180003f90`
- `0x180003fd0`
- `0x1800040e0`
- `0x180004178`
- `0x1800042c0`
- `0x180004a1c`
- `0x18000674c`
- `0x18000697c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800033e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003384`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032ed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800032a5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800032a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800032d7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800032d7`

## pseudocode

```c
__int64 __fastcall CThemeManagerAPIRequest::Execute_SessionCreate(CThemeManagerAPIRequest *this)
{
  int HasTcbPrivilege; // edi
  HANDLE v3; // rsi
  unsigned int ClientSessionID; // r15d
  volatile signed __int32 *v5; // rax
  unsigned int v6; // r8d
  volatile signed __int32 *v7; // r14
  CCriticalSection *v9; // rbp
  int IndexSessionData; // eax
  unsigned int v11; // r15d
  __int64 v12; // r8
  CThemeManagerSessionData *v13; // rcx
  __int64 v14; // rdx
  volatile signed __int32 *v15; // [rsp+60h] [rbp+8h] BYREF

  HasTcbPrivilege = CThemeManagerAPIRequest::ClientHasTcbPrivilege(this);
  if ( HasTcbPrivilege >= 0 )
  {
    v3 = OpenProcess(0x147Au, 0, *((_DWORD *)this + 22));
    if ( v3 )
    {
      ClientSessionID = CAPIDispatcher::GetClientSessionID(*((CAPIDispatcher **)this + 17));
      v5 = (volatile signed __int32 *)LocalAlloc(0, 0x40u);
      v7 = v5;
      if ( v5 )
      {
        *((_DWORD *)v5 + 2) = 1;
        *((_BYTE *)v5 + 12) = 0;
        *((_DWORD *)v5 + 4) = ClientSessionID;
        *(_QWORD *)v5 = &CThemeManagerSessionData::`vftable';
        *((_QWORD *)v5 + 3) = 0;
        *((_QWORD *)v5 + 4) = 0;
        *((_QWORD *)v5 + 5) = 0;
        *((_QWORD *)v5 + 6) = 0;
        *((_QWORD *)v5 + 7) = 0;
        HasTcbPrivilege = CThemeManagerSessionData::Allocate(
                            (CThemeManagerSessionData *)v5,
                            v3,
                            v6,
                            *((void **)this + 9),
                            *((_DWORD *)this + 20),
                            *((_DWORD *)this + 21));
        if ( HasTcbPrivilege >= 0 )
        {
          v9 = CThemeManagerAPIRequest::s_pLock;
          if ( *(int *)CThemeManagerAPIRequest::s_pLock >= 0 )
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)CThemeManagerAPIRequest::s_pLock + 8));
          IndexSessionData = CThemeManagerAPIRequest::FindIndexSessionData(ClientSessionID);
          v11 = IndexSessionData;
          if ( IndexSessionData < 0 )
            goto LABEL_24;
          v13 = 0;
          v14 = *((_QWORD *)CThemeManagerAPIRequest::s_pSessionData + 1);
          if ( v14 && (unsigned int)IndexSessionData < *(_DWORD *)CThemeManagerAPIRequest::s_pSessionData )
            v13 = *(CThemeManagerSessionData **)(v14 + 8LL * (unsigned int)IndexSessionData);
          CThemeManagerSessionData::Cleanup(v13);
          HasTcbPrivilege = CDynamicPointerArrayBase<CCountedObject,CTOwnershipPolicy_CountedObject<CCountedObject>>::Remove(
                              CThemeManagerAPIRequest::s_pSessionData,
                              v11,
                              v12);
          if ( HasTcbPrivilege >= 0 )
          {
LABEL_24:
            if ( CThemeManagerAPIRequest::s_pSessionData )
            {
              v15 = v7;
              HasTcbPrivilege = CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add(
                                  (unsigned int *)CThemeManagerAPIRequest::s_pSessionData,
                                  &v15);
              if ( HasTcbPrivilege >= 0 )
                _InterlockedIncrement(v7 + 2);
            }
          }
          if ( *(int *)v9 >= 0 )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 8));
        }
        CCountedObject::Release((CCountedObject *)v7);
      }
      else
      {
        HasTcbPrivilege = -1073741801;
      }
      CloseHandle(v3);
    }
    else
    {
      HasTcbPrivilege = CStatusCode::StatusCodeOfLastError();
    }
  }
  *((_DWORD *)this + 6) = 7340104;
  return (unsigned int)HasTcbPrivilege;
}

```

## disassembly

```asm
0x180003280  push    rbx
0x180003282  push    rdi
0x180003283  sub     rsp, 48h
0x180003287  mov     rbx, rcx
0x18000328a  call    ?ClientHasTcbPrivilege@CThemeManagerAPIRequest@@AEAAJXZ; CThemeManagerAPIRequest::ClientHasTcbPrivilege(void)
0x18000328f  mov     edi, eax
0x180003291  test    eax, eax
0x180003293  js      short loc_180003302
0x180003295  mov     r8d, [rbx+58h]; dwProcessId
0x180003299  xor     edx, edx; bInheritHandle
0x18000329b  mov     ecx, 147Ah; dwDesiredAccess
0x1800032a0  mov     [rsp+58h+arg_10], rsi
0x1800032a5  call    cs:__imp_OpenProcess
0x1800032ab  mov     rsi, rax
0x1800032ae  test    rax, rax
0x1800032b1  jz      loc_180003420
0x1800032b7  mov     rcx, [rbx+88h]; this
0x1800032be  mov     [rsp+58h+var_20], r14
0x1800032c3  mov     [rsp+58h+var_28], r15
0x1800032c8  call    ?GetClientSessionID@CAPIDispatcher@@QEBAKXZ; CAPIDispatcher::GetClientSessionID(void)
0x1800032cd  mov     edx, 40h ; '@'; uBytes
0x1800032d2  xor     ecx, ecx; uFlags
0x1800032d4  mov     r15d, eax
0x1800032d7  call    cs:__imp_LocalAlloc
0x1800032dd  mov     r14, rax
0x1800032e0  test    rax, rax
0x1800032e3  jnz     short loc_180003312
0x1800032e5  mov     edi, 0C0000017h
0x1800032ea  mov     rcx, rsi; hObject
0x1800032ed  call    cs:__imp_CloseHandle
0x1800032f3  mov     r15, [rsp+58h+var_28]
0x1800032f8  mov     r14, [rsp+58h+var_20]
0x1800032fd  mov     rsi, [rsp+58h+arg_10]
0x180003302  mov     dword ptr [rbx+18h], 700048h
0x180003309  mov     eax, edi
0x18000330b  add     rsp, 48h
0x18000330f  pop     rdi
0x180003310  pop     rbx
0x180003311  retn
0x180003312  mov     dword ptr [rax+8], 1
0x180003319  mov     rdx, rsi; ProcessHandle
0x18000331c  mov     byte ptr [rax+0Ch], 0
0x180003320  mov     rcx, r14; this
0x180003323  mov     [r14+10h], r15d
0x180003327  lea     rax, ??_7CThemeManagerSessionData@@6B@; const CThemeManagerSessionData::`vftable'
0x18000332e  mov     [r14], rax
0x180003331  mov     [rsp+58h+var_18], r12
0x180003336  xor     r12d, r12d
0x180003339  mov     [r14+18h], r12
0x18000333d  mov     [r14+20h], r12
0x180003341  mov     [r14+28h], r12
0x180003345  mov     [r14+30h], r12
0x180003349  mov     [r14+38h], r12
0x18000334d  mov     eax, [rbx+54h]
0x180003350  mov     r9, [rbx+48h]; void *
0x180003354  mov     [rsp+58h+var_30], eax; unsigned int
0x180003358  mov     eax, [rbx+50h]
0x18000335b  mov     [rsp+58h+var_38], eax; unsigned int
0x18000335f  call    ?Allocate@CThemeManagerSessionData@@QEAAJPEAXK0KK@Z; CThemeManagerSessionData::Allocate(void *,ulong,void *,ulong,ulong)
0x180003364  mov     edi, eax
0x180003366  test    eax, eax
0x180003368  js      loc_1800033F0
0x18000336e  mov     [rsp+58h+arg_8], rbp
0x180003373  mov     rbp, cs:?s_pLock@CThemeManagerAPIRequest@@0PEAVCCriticalSection@@EA; CCriticalSection * CThemeManagerAPIRequest::s_pLock
0x18000337a  cmp     [rbp+0], r12d
0x18000337e  jl      short loc_18000338A
0x180003380  lea     rcx, [rbp+8]; lpCriticalSection
0x180003384  call    cs:__imp_EnterCriticalSection
0x18000338a  mov     ecx, r15d; unsigned int
0x18000338d  call    ?FindIndexSessionData@CThemeManagerAPIRequest@@CAHK@Z; CThemeManagerAPIRequest::FindIndexSessionData(ulong)
0x180003392  mov     r15d, eax
0x180003395  test    eax, eax
0x180003397  jns     short loc_180003402
0x180003399  mov     rcx, cs:?s_pSessionData@CThemeManagerAPIRequest@@0PEAVCDynamicCountedObjectArray@@EA; CDynamicCountedObjectArray * CThemeManagerAPIRequest::s_pSessionData
0x1800033a0  test    rcx, rcx
0x1800033a3  jz      short loc_1800033DB
0x1800033a5  lea     rdx, [rsp+58h+arg_0]
0x1800033aa  mov     [rsp+58h+arg_0], r14
0x1800033af  call    ?Add@?$CDynamicArray@PEAU_ACCESS_ALLOWED_ACE@@@@QEAAJAEBQEAU_ACCESS_ALLOWED_ACE@@@Z; CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add(_ACCESS_ALLOWED_ACE * const &)
0x1800033b4  mov     edi, eax
0x1800033b6  test    eax, eax
0x1800033b8  js      short loc_1800033DB
0x1800033ba  lock inc dword ptr [r14+8]
0x1800033bf  jmp     short loc_1800033DB
0x1800033c1  call    ?Cleanup@CThemeManagerSessionData@@QEAAJXZ; CThemeManagerSessionData::Cleanup(void)
0x1800033c6  mov     rcx, cs:?s_pSessionData@CThemeManagerAPIRequest@@0PEAVCDynamicCountedObjectArray@@EA; CDynamicCountedObjectArray * CThemeManagerAPIRequest::s_pSessionData
0x1800033cd  mov     edx, r15d
0x1800033d0  call    ?Remove@?$CDynamicPointerArrayBase@VCCountedObject@@V?$CTOwnershipPolicy_CountedObject@VCCountedObject@@@@@@QEAAJI@Z; CDynamicPointerArrayBase<CCountedObject,CTOwnershipPolicy_CountedObject<CCountedObject>>::Remove(uint)
0x1800033d5  mov     edi, eax
0x1800033d7  test    eax, eax
0x1800033d9  jns     short loc_180003399
0x1800033db  cmp     [rbp+0], r12d
0x1800033df  jl      short loc_1800033EB
0x1800033e1  lea     rcx, [rbp+8]; lpCriticalSection
0x1800033e5  call    cs:__imp_LeaveCriticalSection
0x1800033eb  mov     rbp, [rsp+58h+arg_8]
0x1800033f0  mov     rcx, r14; this
0x1800033f3  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x1800033f8  mov     r12, [rsp+58h+var_18]
0x1800033fd  jmp     loc_1800032EA
0x180003402  mov     rax, cs:?s_pSessionData@CThemeManagerAPIRequest@@0PEAVCDynamicCountedObjectArray@@EA; CDynamicCountedObjectArray * CThemeManagerAPIRequest::s_pSessionData
0x180003409  mov     rcx, r12; this
0x18000340c  mov     rdx, [rax+8]
0x180003410  test    rdx, rdx
0x180003413  jz      short loc_1800033C1
0x180003415  cmp     r15d, [rax]
0x180003418  jnb     short loc_1800033C1
0x18000341a  mov     rcx, [rdx+r15*8]
0x18000341e  jmp     short loc_1800033C1
0x180003420  call    ?StatusCodeOfLastError@CStatusCode@@SAJXZ; CStatusCode::StatusCodeOfLastError(void)
0x180003425  mov     edi, eax
0x180003427  jmp     loc_1800032FD
```
