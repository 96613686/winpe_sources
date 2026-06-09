# CFilterRegistration::getClsidOfMimeType(TLMString<32,32,128> const &,_GUID &)

- ea: `0x180158858`
- end: `0x180158c74`
- name: `?getClsidOfMimeType@CFilterRegistration@@AEAAHAEBV?$TLMString@$0CA@$0CA@$0IA@@@AEAU_GUID@@@Z`
- size: `1052`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f035c`

## callees

- `0x18003b678`
- `0x18006242c`
- `0x180068af4`
- `0x180068b14`
- `0x1800699a0`
- `0x18008f4a4`
- `0x1800eb364`
- `0x1800f3e64`
- `0x1800f7a30`
- `0x18010fd00`
- `0x180158698`
- `0x180158858`
- `0x1801590bc`
- `0x1801590dc`
- `0x1801591a4`
- `0x1801591b8`
- `0x180188d90`
- `0x180188dc0`
- `0x1801f5388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801588b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015892a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158946`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158973`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015898b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801589c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801589de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158a40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158bd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158c0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801588b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015892a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158946`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158973`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015898b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801589c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801589de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158a40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158bd6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158c0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801588d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801589ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158c41`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801588d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801589ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158a01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158c41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801589cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801589cb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180158b3b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180158b3b`

## string_xrefs

- `0x180158b06`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CFilterRegistration::getClsidOfMimeType(__int64 a1, __int64 a2, GUID *a3)
{
  __int64 v6; // rbx
  unsigned int v7; // r14d
  int v8; // edi
  __int64 v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  volatile signed __int32 *v11; // rsi
  int v12; // r12d
  __int64 v13; // rax
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  const wchar_t *v15; // r9
  bool v16; // sf
  wchar_t *Buffer; // rax
  const OLECHAR *v18; // rax
  _QWORD *v19; // rdi
  __int64 v20; // rdx
  __int64 v21; // rcx
  struct _RTL_CRITICAL_SECTION *v22; // rbx
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h]
  GUID *v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  _QWORD *v28; // [rsp+50h] [rbp-B0h]
  GUID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v30[3]; // [rsp+70h] [rbp-90h] BYREF
  __int16 v31; // [rsp+88h] [rbp-78h] BYREF
  char v32[8]; // [rsp+110h] [rbp+10h] BYREF
  LPCWSTR lpSubKey; // [rsp+118h] [rbp+18h]

  v26 = a3;
  v6 = a1 + 216;
  v27 = a1 + 216;
  v7 = 1;
  while ( 1 )
  {
    while ( *(_DWORD *)v6 )
    {
      v8 = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
      if ( *(_DWORD *)v6 )
      {
        CSyncReadWrite::LokInitReadEvent((CSyncReadWrite *)v6);
        CEventSem::Reset((CEventSem *)(v6 + 112));
        v8 = 1;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
      if ( v8 )
        CEventSem::Wait((CEventSem *)(v6 + 112), 0xFFFFFFFF, 0);
    }
    _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
    if ( !*(_DWORD *)v6 )
      break;
    CSyncReadWrite::SyncReadDecrement((CSyncReadWrite *)v6);
  }
  v9 = CTKPLiteHashMap<TLMString<32,32,128>,CMimeToDataTableEntry<_GUID>>::Lookup(a1 + 64, a2);
  if ( !v9 )
  {
    if ( *(_DWORD *)v6 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
      _InterlockedDecrement((volatile signed __int32 *)(v6 + 8));
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)(v6 + 8));
      if ( !*(_DWORD *)v6 )
        goto LABEL_25;
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
    }
    if ( !*(_DWORD *)(v6 + 8) )
    {
      CSyncReadWrite::LokInitWriteEvent((CSyncReadWrite *)v6);
      CEventSem::Set((CEventSem *)(v6 + 120));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
LABEL_25:
    v11 = (volatile signed __int32 *)(a1 + 216);
    v27 = a1 + 216;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 232));
    _InterlockedAdd((volatile signed __int32 *)(a1 + 216), 1u);
    *(_DWORD *)(a1 + 220) = GetCurrentThreadId();
    v12 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
    if ( *(_DWORD *)(a1 + 224) )
    {
      CSyncReadWrite::LokInitWriteEvent((CSyncReadWrite *)(a1 + 216));
      CEventSem::Reset((CEventSem *)(a1 + 336));
      v12 = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
    if ( v12 )
      CEventSem::Wait((CEventSem *)(a1 + 336), 0xFFFFFFFF, 0);
    v13 = CTKPLiteHashMap<TLMString<32,32,128>,CMimeToDataTableEntry<_GUID>>::Lookup(a1 + 64, a2);
    if ( v13 )
    {
      *v26 = *(GUID *)(v13 + 112);
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
      if ( *v11 == 1 )
        *(_DWORD *)(a1 + 220) = 0;
      _InterlockedDecrement(v11);
      CSyncReadWrite::LokInitReadEvent((CSyncReadWrite *)(a1 + 216));
      CEventSem::Set((CEventSem *)(a1 + 328));
      v14 = (struct _RTL_CRITICAL_SECTION *)(a1 + 280);
      goto LABEL_45;
    }
    TLMString<64,64,32767>::TLMString<64,64,32767>(v32, L"Software\\Classes\\MIME\\Database\\Content Type\\");
    CLMString::Append((CLMString *)v32, *(const wchar_t **)(a2 + 8), *(_DWORD *)(a2 + 20));
    phkResult = 0;
    v25 = 0;
    CWin32RegAccess::OpenKey((wchar_t *)&phkResult, HKEY_LOCAL_MACHINE, (wchar_t *)lpSubKey, v15, 0x20019u);
    v16 = (int)v25 < 0;
    if ( (int)v25 > 0 )
      v16 = 1;
    if ( !v16 )
    {
      v30[1] = &v31;
      v30[2] = 65;
      v31 = 0;
      v30[0] = &CCICommonPathString::`vftable';
      Buffer = CLMString::GetBuffer((CLMString *)v30, 41);
      if ( CWin32RegAccess::Get((CWin32RegAccess *)&phkResult, L"CLSID", Buffer, 0x29u) )
      {
        pclsid = 0;
        v18 = CLMString::GetBuffer((CLMString *)v30, 0);
        if ( CLSIDFromString(v18, &pclsid) >= 0 )
        {
          v19 = operator new(0x80u);
          v28 = v19;
          *v19 = 0;
          v19[1] = 0;
          TLMString<32,32,128>::TLMString<32,32,128>(v19 + 2, a2);
          *((GUID *)v19 + 7) = pclsid;
          v28 = v19;
          v20 = (unsigned int)PSmallStringHash(v19 + 2) % *(_DWORD *)(a1 + 64);
          v21 = *(_QWORD *)(a1 + 72);
          *v19 = *(_QWORD *)(v21 + 8 * v20);
          v19[1] = v19;
          *(_QWORD *)(v21 + 8LL * (unsigned int)v20) = v19;
          ++*(_DWORD *)(a1 + 68);
          *v26 = pclsid;
          TLMString<64,64,32767>::~TLMString<64,64,32767>(v30);
          CWin32RegAccess::~CWin32RegAccess((CWin32RegAccess *)&phkResult);
          TLMString<64,64,32767>::~TLMString<64,64,32767>(v32);
          v22 = (struct _RTL_CRITICAL_SECTION *)(a1 + 280);
          EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
          if ( *v11 == 1 )
            *(_DWORD *)(a1 + 220) = 0;
LABEL_44:
          _InterlockedDecrement(v11);
          CSyncReadWrite::LokInitReadEvent((CSyncReadWrite *)(a1 + 216));
          CEventSem::Set((CEventSem *)(a1 + 328));
          v14 = v22;
LABEL_45:
          LeaveCriticalSection(v14);
          v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 232);
LABEL_46:
          LeaveCriticalSection(v10);
          return v7;
        }
      }
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v30);
    }
    CWin32RegAccess::~CWin32RegAccess((CWin32RegAccess *)&phkResult);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v32);
    v22 = (struct _RTL_CRITICAL_SECTION *)(a1 + 280);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
    if ( *v11 == 1 )
      *(_DWORD *)(a1 + 220) = 0;
    v7 = 0;
    goto LABEL_44;
  }
  *a3 = *(GUID *)(v9 + 112);
  if ( *(_DWORD *)v6 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
    _InterlockedDecrement((volatile signed __int32 *)(v6 + 8));
LABEL_15:
    if ( !*(_DWORD *)(v6 + 8) )
    {
      CSyncReadWrite::LokInitWriteEvent((CSyncReadWrite *)v6);
      CEventSem::Set((CEventSem *)(v6 + 120));
    }
    v10 = (struct _RTL_CRITICAL_SECTION *)(v6 + 64);
    goto LABEL_46;
  }
  _InterlockedDecrement((volatile signed __int32 *)(v6 + 8));
  if ( *(_DWORD *)v6 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
    goto LABEL_15;
  }
  return v7;
}

```

## disassembly

```asm
0x180158858  mov     [rsp-8+arg_18], rbx
0x18015885d  push    rbp
0x18015885e  push    rsi
0x18015885f  push    rdi
0x180158860  push    r12
0x180158862  push    r13
0x180158864  push    r14
0x180158866  push    r15
0x180158868  lea     rbp, [rsp-0C0h]
0x180158870  sub     rsp, 1C0h
0x180158877  mov     rax, cs:__security_cookie
0x18015887e  xor     rax, rsp
0x180158881  mov     [rbp+0F0h+var_40], rax
0x180158888  mov     r12, r8
0x18015888b  mov     [rsp+1F0h+var_1B0], r8
0x180158890  mov     r13, rdx
0x180158893  mov     r15, rcx
0x180158896  lea     rbx, [rcx+0D8h]
0x18015889d  mov     [rsp+1F0h+var_1A8], rbx
0x1801588a2  xor     esi, esi
0x1801588a4  lea     r14d, [rsi+1]
0x1801588a8  cmp     [rbx], esi
0x1801588aa  jz      short loc_1801588F4
0x1801588ac  xor     edi, edi
0x1801588ae  lea     rcx, [rbx+40h]; lpCriticalSection
0x1801588b2  call    cs:__imp_EnterCriticalSection
0x1801588b8  cmp     [rbx], edi
0x1801588ba  jz      short loc_1801588D0
0x1801588bc  mov     rcx, rbx; this
0x1801588bf  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x1801588c4  lea     rcx, [rbx+70h]; this
0x1801588c8  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x1801588cd  mov     edi, r14d
0x1801588d0  lea     rcx, [rbx+40h]; lpCriticalSection
0x1801588d4  call    cs:__imp_LeaveCriticalSection
0x1801588da  test    edi, edi
0x1801588dc  jz      short loc_1801588ED
0x1801588de  lea     rcx, [rbx+70h]; this
0x1801588e2  xor     r8d, r8d; int
0x1801588e5  or      edx, 0FFFFFFFFh; unsigned int
0x1801588e8  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x1801588ed  cmp     dword ptr [rbx], 0
0x1801588f0  jnz     short loc_1801588AC
0x1801588f2  xor     esi, esi
0x1801588f4  lock add [rbx+8], r14d
0x1801588f9  cmp     [rbx], esi
0x1801588fb  jz      short loc_180158907
0x1801588fd  mov     rcx, rbx; this
0x180158900  call    ?SyncReadDecrement@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::SyncReadDecrement(void)
0x180158905  jmp     short loc_1801588A8
0x180158907  lea     rcx, [r15+40h]
0x18015890b  mov     rdx, r13
0x18015890e  call    ?Lookup@?$CTKPLiteHashMap@V?$TLMString@$0CA@$0CA@$0IA@@@V?$CMimeToDataTableEntry@U_GUID@@@@@@QEBAPEAV?$CMimeToDataTableEntry@U_GUID@@@@PEBV?$TLMString@$0CA@$0CA@$0IA@@@@Z; CTKPLiteHashMap<TLMString<32,32,128>,CMimeToDataTableEntry<_GUID>>::Lookup(TLMString<32,32,128> const *)
0x180158913  test    rax, rax
0x180158916  jz      short loc_18015896B
0x180158918  movups  xmm0, xmmword ptr [rax+70h]
0x18015891c  movdqu  xmmword ptr [r12], xmm0
0x180158922  cmp     [rbx], esi
0x180158924  jz      short loc_180158936
0x180158926  lea     rcx, [rbx+40h]; lpCriticalSection
0x18015892a  call    cs:__imp_EnterCriticalSection
0x180158930  lock dec dword ptr [rbx+8]
0x180158934  jmp     short loc_18015894C
0x180158936  lock dec dword ptr [rbx+8]
0x18015893a  cmp     [rbx], esi
0x18015893c  jz      loc_180158C47
0x180158942  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158946  call    cs:__imp_EnterCriticalSection
0x18015894c  cmp     [rbx+8], esi
0x18015894f  jnz     short loc_180158962
0x180158951  mov     rcx, rbx; this
0x180158954  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x180158959  lea     rcx, [rbx+78h]; this
0x18015895d  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180158962  lea     rcx, [rbx+40h]
0x180158966  jmp     loc_180158C41
0x18015896b  cmp     [rbx], esi
0x18015896d  jz      short loc_18015897F
0x18015896f  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158973  call    cs:__imp_EnterCriticalSection
0x180158979  lock dec dword ptr [rbx+8]
0x18015897d  jmp     short loc_180158991
0x18015897f  lock dec dword ptr [rbx+8]
0x180158983  cmp     [rbx], esi
0x180158985  jz      short loc_1801589B1
0x180158987  lea     rcx, [rbx+40h]; lpCriticalSection
0x18015898b  call    cs:__imp_EnterCriticalSection
0x180158991  cmp     [rbx+8], esi
0x180158994  jnz     short loc_1801589A7
0x180158996  mov     rcx, rbx; this
0x180158999  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x18015899e  lea     rcx, [rbx+78h]; this
0x1801589a2  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x1801589a7  lea     rcx, [rbx+40h]; lpCriticalSection
0x1801589ab  call    cs:__imp_LeaveCriticalSection
0x1801589b1  lea     rsi, [r15+0D8h]
0x1801589b8  mov     [rsp+1F0h+var_1A8], rsi
0x1801589bd  lea     rcx, [rsi+10h]; lpCriticalSection
0x1801589c1  call    cs:__imp_EnterCriticalSection
0x1801589c7  lock add [rsi], r14d
0x1801589cb  call    cs:__imp_GetCurrentThreadId
0x1801589d1  mov     [rsi+4], eax
0x1801589d4  xor     r12d, r12d
0x1801589d7  lea     rdi, [rsi+40h]
0x1801589db  mov     rcx, rdi; lpCriticalSection
0x1801589de  call    cs:__imp_EnterCriticalSection
0x1801589e4  cmp     [rsi+8], r12d
0x1801589e8  jz      short loc_1801589FE
0x1801589ea  mov     rcx, rsi; this
0x1801589ed  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x1801589f2  lea     rcx, [rsi+78h]; this
0x1801589f6  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x1801589fb  mov     r12d, r14d
0x1801589fe  mov     rcx, rdi; lpCriticalSection
0x180158a01  call    cs:__imp_LeaveCriticalSection
0x180158a07  test    r12d, r12d
0x180158a0a  jz      short loc_180158A1C
0x180158a0c  xor     r8d, r8d; int
0x180158a0f  or      edx, 0FFFFFFFFh; unsigned int
0x180158a12  lea     rcx, [rsi+78h]; this
0x180158a16  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x180158a1b  nop
0x180158a1c  lea     rcx, [r15+40h]
0x180158a20  mov     rdx, r13
0x180158a23  call    ?Lookup@?$CTKPLiteHashMap@V?$TLMString@$0CA@$0CA@$0IA@@@V?$CMimeToDataTableEntry@U_GUID@@@@@@QEBAPEAV?$CMimeToDataTableEntry@U_GUID@@@@PEBV?$TLMString@$0CA@$0CA@$0IA@@@@Z; CTKPLiteHashMap<TLMString<32,32,128>,CMimeToDataTableEntry<_GUID>>::Lookup(TLMString<32,32,128> const *)
0x180158a28  xor     r12d, r12d
0x180158a2b  test    rax, rax
0x180158a2e  jz      short loc_180158A6B
0x180158a30  movups  xmm0, xmmword ptr [rax+70h]
0x180158a34  mov     rax, [rsp+1F0h+var_1B0]
0x180158a39  movdqu  xmmword ptr [rax], xmm0
0x180158a3d  mov     rcx, rdi; lpCriticalSection
0x180158a40  call    cs:__imp_EnterCriticalSection
0x180158a46  cmp     [rsi], r14d
0x180158a49  jnz     short loc_180158A4F
0x180158a4b  mov     [rsi+4], r12d
0x180158a4f  lock dec dword ptr [rsi]
0x180158a52  mov     rcx, rsi; this
0x180158a55  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x180158a5a  lea     rcx, [rsi+70h]; this
0x180158a5e  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180158a63  mov     rcx, rdi
0x180158a66  jmp     loc_180158C37
0x180158a6b  lea     rdx, aSoftwareClasse; "Software\\Classes\\MIME\\Database\\Cont"...
0x180158a72  lea     rcx, [rbp+0F0h+var_E0]
0x180158a76  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x180158a7b  nop
0x180158a7c  mov     r8d, [r13+14h]; unsigned int
0x180158a80  mov     rdx, [r13+8]; wchar_t *
0x180158a84  lea     rcx, [rbp+0F0h+var_E0]; this
0x180158a88  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180158a8d  mov     [rsp+1F0h+phkResult], r12
0x180158a92  mov     [rsp+1F0h+var_1B8], r12
0x180158a97  mov     [rsp+1F0h+var_1D0], 20019h; unsigned int
0x180158a9f  mov     r8, [rbp+0F0h+lpSubKey]; lpSubKey
0x180158aa3  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180158aaa  lea     rcx, [rsp+1F0h+phkResult]; phkResult
0x180158aaf  call    ?OpenKey@CWin32RegAccess@@IEAAXPEAUHKEY__@@PEB_W1K@Z; CWin32RegAccess::OpenKey(HKEY__ *,wchar_t const *,wchar_t const *,ulong)
0x180158ab4  nop
0x180158ab5  mov     eax, dword ptr [rsp+1F0h+var_1B8]
0x180158ab9  test    eax, eax
0x180158abb  jle     short loc_180158AC7
0x180158abd  movzx   eax, ax
0x180158ac0  or      eax, 80070000h
0x180158ac5  test    eax, eax
0x180158ac7  js      loc_180158BF2
0x180158acd  lea     rax, [rbp+0F0h+var_168]
0x180158ad1  mov     [rsp+1F0h+var_178], rax
0x180158ad6  mov     [rbp+0F0h+var_170], 41h ; 'A'
0x180158ade  mov     [rbp+0F0h+var_168], r12w
0x180158ae3  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x180158aea  mov     [rsp+1F0h+var_180], rax
0x180158aef  mov     ebx, 29h ; ')'
0x180158af4  mov     edx, ebx; int
0x180158af6  lea     rcx, [rsp+1F0h+var_180]; this
0x180158afb  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180158b00  mov     r8, rax; wchar_t *
0x180158b03  mov     r9d, ebx; unsigned int
0x180158b06  lea     rdx, aClsid_1; "CLSID"
0x180158b0d  lea     rcx, [rsp+1F0h+phkResult]; this
0x180158b12  call    ?Get@CWin32RegAccess@@QEAAHPEB_WPEA_WI@Z; CWin32RegAccess::Get(wchar_t const *,wchar_t *,uint)
0x180158b17  test    eax, eax
0x180158b19  jz      loc_180158BE7
0x180158b1f  xorps   xmm0, xmm0
0x180158b22  movups  xmmword ptr [rsp+1F0h+pclsid.Data1], xmm0
0x180158b27  xor     edx, edx; int
0x180158b29  lea     rcx, [rsp+1F0h+var_180]; this
0x180158b2e  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180158b33  mov     rcx, rax; lpsz
0x180158b36  lea     rdx, [rsp+1F0h+pclsid]; pclsid
0x180158b3b  call    cs:__imp_CLSIDFromString
0x180158b41  test    eax, eax
0x180158b43  js      loc_180158BE7
0x180158b49  lea     ecx, [rbx+57h]; Size
0x180158b4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180158b51  mov     rdi, rax
0x180158b54  mov     [rsp+1F0h+var_1A0], rax
0x180158b59  mov     [rax], r12
0x180158b5c  mov     [rax+8], r12
0x180158b60  mov     rdx, r13
0x180158b63  lea     rcx, [rax+10h]
0x180158b67  call    ??0?$TLMString@$0CA@$0CA@$0IA@@@QEAA@AEBV0@@Z; TLMString<32,32,128>::TLMString<32,32,128>(TLMString<32,32,128> const &)
0x180158b6c  movups  xmm0, xmmword ptr [rsp+1F0h+pclsid.Data1]
0x180158b71  movdqu  xmmword ptr [rdi+70h], xmm0
0x180158b76  mov     [rsp+1F0h+var_1A0], rdi
0x180158b7b  lea     rcx, [rdi+10h]
0x180158b7f  call    ?PSmallStringHash@@YAKPEBV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; PSmallStringHash(TLMString<32,32,1024> const *)
0x180158b84  xor     edx, edx
0x180158b86  div     dword ptr [r15+40h]
0x180158b8a  mov     rcx, [r15+48h]
0x180158b8e  mov     rax, [rcx+rdx*8]
0x180158b92  mov     [rdi], rax
0x180158b95  mov     [rdi+8], rdi
0x180158b99  mov     [rcx+rdx*8], rdi
0x180158b9d  add     [r15+44h], r14d
0x180158ba1  movups  xmm0, xmmword ptr [rsp+1F0h+pclsid.Data1]
0x180158ba6  mov     rax, [rsp+1F0h+var_1B0]
0x180158bab  movdqu  xmmword ptr [rax], xmm0
0x180158baf  lea     rcx, [rsp+1F0h+var_180]
0x180158bb4  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180158bb9  nop
0x180158bba  lea     rcx, [rsp+1F0h+phkResult]; this
0x180158bbf  call    ??1CWin32RegAccess@@QEAA@XZ; CWin32RegAccess::~CWin32RegAccess(void)
0x180158bc4  nop
0x180158bc5  lea     rcx, [rbp+0F0h+var_E0]
0x180158bc9  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180158bce  nop
0x180158bcf  lea     rbx, [rsi+40h]
0x180158bd3  mov     rcx, rbx; lpCriticalSection
0x180158bd6  call    cs:__imp_EnterCriticalSection
0x180158bdc  cmp     [rsi], r14d
0x180158bdf  jnz     short loc_180158C20
0x180158be1  mov     [rsi+4], r12d
0x180158be5  jmp     short loc_180158C20
0x180158be7  lea     rcx, [rsp+1F0h+var_180]
0x180158bec  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180158bf1  nop
0x180158bf2  lea     rcx, [rsp+1F0h+phkResult]; this
0x180158bf7  call    ??1CWin32RegAccess@@QEAA@XZ; CWin32RegAccess::~CWin32RegAccess(void)
0x180158bfc  nop
0x180158bfd  lea     rcx, [rbp+0F0h+var_E0]
0x180158c01  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180158c06  nop
0x180158c07  lea     rbx, [rsi+40h]
0x180158c0b  mov     rcx, rbx; lpCriticalSection
0x180158c0e  call    cs:__imp_EnterCriticalSection
0x180158c14  cmp     [rsi], r14d
0x180158c17  jnz     short loc_180158C1D
0x180158c19  mov     [rsi+4], r12d
0x180158c1d  mov     r14d, r12d
0x180158c20  lock dec dword ptr [rsi]
0x180158c23  mov     rcx, rsi; this
0x180158c26  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x180158c2b  lea     rcx, [rsi+70h]; this
0x180158c2f  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180158c34  mov     rcx, rbx; lpCriticalSection
0x180158c37  call    cs:__imp_LeaveCriticalSection
0x180158c3d  lea     rcx, [rsi+10h]; lpCriticalSection
0x180158c41  call    cs:__imp_LeaveCriticalSection
0x180158c47  mov     eax, r14d
0x180158c4a  mov     rcx, [rbp+0F0h+var_40]
0x180158c51  xor     rcx, rsp; StackCookie
0x180158c54  call    __security_check_cookie
0x180158c59  mov     rbx, [rsp+1F0h+arg_18]
0x180158c61  add     rsp, 1C0h
0x180158c68  pop     r15
0x180158c6a  pop     r14
0x180158c6c  pop     r13
0x180158c6e  pop     r12
0x180158c70  pop     rdi
0x180158c71  pop     rsi
0x180158c72  pop     rbp
0x180158c73  retn
```
