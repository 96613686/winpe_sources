# CFilterRegistration::getExtOfMimeType(TLMString<32,32,128> const &,TLMString<16,32,256> &)

- ea: `0x180158c7c`
- end: `0x1801590b3`
- name: `?getExtOfMimeType@CFilterRegistration@@AEAAHAEBV?$TLMString@$0CA@$0CA@$0IA@@@AEAV?$TLMString@$0BA@$0CA@$0BAA@@@@Z`
- size: `1079`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x1800f035c`

## callees

- `0x18003b678`
- `0x18006242c`
- `0x180068af4`
- `0x180068b14`
- `0x1800699a0`
- `0x18008f4a4`
- `0x18008facc`
- `0x18008fb4c`
- `0x1800eb364`
- `0x1800f3e64`
- `0x1800f7a30`
- `0x18010fd00`
- `0x180158698`
- `0x180158c7c`
- `0x1801590bc`
- `0x1801590dc`
- `0x180159120`
- `0x180159154`
- `0x1801591a4`
- `0x1801591b8`
- `0x180188d90`
- `0x180188dc0`
- `0x1801f5388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158ccd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158d48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158d64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158d91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158da9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158ddc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158df7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158e58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180159013`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015904f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158ccd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158d48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158d64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158d91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158da9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158ddc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158df7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180158e58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180159013`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18015904f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158cef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158e1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180159079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180159083`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158cef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180158e1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180159079`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180159083`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180158de6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180158de6`

## string_xrefs

- `0x180158f29`: `Extension`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CFilterRegistration::getExtOfMimeType(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  int v7; // esi
  unsigned int v8; // r15d
  int v9; // edi
  __int64 v10; // rax
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  volatile signed __int32 *v12; // r14
  __int64 v13; // rax
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  const wchar_t *v15; // r9
  bool v16; // sf
  wchar_t *Buffer; // rax
  int v18; // edx
  _QWORD *v19; // rsi
  wchar_t *v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  struct _RTL_CRITICAL_SECTION *v23; // rbx
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  void **v29; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v30; // [rsp+68h] [rbp-98h]
  __int64 v31; // [rsp+70h] [rbp-90h]
  __int16 v32; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v33[8]; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpSubKey; // [rsp+A8h] [rbp-58h]

  v27 = a3;
  v6 = a1 + 88;
  v7 = 0;
  v8 = 1;
  while ( 1 )
  {
    if ( *(_DWORD *)v6 )
    {
      do
      {
        v9 = 0;
        EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
        if ( *(_DWORD *)v6 )
        {
          CSyncReadWrite::LokInitReadEvent((CSyncReadWrite *)v6);
          CEventSem::Reset((CEventSem *)(v6 + 112));
          v9 = 1;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
        if ( v9 )
          CEventSem::Wait((CEventSem *)(v6 + 112), 0xFFFFFFFF, 0);
      }
      while ( *(_DWORD *)v6 );
      v7 = 0;
    }
    _InterlockedAdd((volatile signed __int32 *)(v6 + 8), 1u);
    if ( !*(_DWORD *)v6 )
      break;
    CSyncReadWrite::SyncReadDecrement((CSyncReadWrite *)v6);
  }
  v10 = CTKPLiteHashMap<TLMString<32,32,128>,CMimeToDataTableEntry<_GUID>>::Lookup(a1 + 40, a2);
  if ( !v10 )
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
        goto LABEL_26;
      EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
    }
    if ( !*(_DWORD *)(v6 + 8) )
    {
      CSyncReadWrite::LokInitWriteEvent((CSyncReadWrite *)v6);
      CEventSem::Set((CEventSem *)(v6 + 120));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
LABEL_26:
    v12 = (volatile signed __int32 *)(a1 + 88);
    v28 = a1 + 88;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
    _InterlockedAdd((volatile signed __int32 *)(a1 + 88), 1u);
    *(_DWORD *)(a1 + 92) = GetCurrentThreadId();
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
    if ( *(_DWORD *)(a1 + 96) )
    {
      CSyncReadWrite::LokInitWriteEvent((CSyncReadWrite *)(a1 + 88));
      CEventSem::Reset((CEventSem *)(a1 + 208));
      v7 = 1;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
    if ( v7 )
      CEventSem::Wait((CEventSem *)(a1 + 208), 0xFFFFFFFF, 0);
    v13 = CTKPLiteHashMap<TLMString<32,32,128>,CMimeToDataTableEntry<_GUID>>::Lookup(a1 + 40, a2);
    if ( v13 )
    {
      CLMString::operator=(v27, *(_QWORD *)(v13 + 120));
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
      if ( *v12 == 1 )
        *(_DWORD *)(a1 + 92) = 0;
      _InterlockedDecrement(v12);
      CSyncReadWrite::LokInitReadEvent((CSyncReadWrite *)(a1 + 88));
      CEventSem::Set((CEventSem *)(a1 + 200));
      v14 = (struct _RTL_CRITICAL_SECTION *)(a1 + 152);
      goto LABEL_45;
    }
    TLMString<64,64,32767>::TLMString<64,64,32767>(v33, L"Software\\Classes\\MIME\\Database\\Content Type\\");
    CLMString::Append((CLMString *)v33, *(const wchar_t **)(a2 + 8), *(_DWORD *)(a2 + 20));
    phkResult = 0;
    v26 = 0;
    CWin32RegAccess::OpenKey((wchar_t *)&phkResult, HKEY_LOCAL_MACHINE, (wchar_t *)lpSubKey, v15, 0x20019u);
    v16 = (int)v26 < 0;
    if ( (int)v26 > 0 )
      v16 = 1;
    if ( !v16 )
    {
      v30 = (wchar_t *)&v32;
      v31 = 17;
      v32 = 0;
      v29 = &TLMString<16,32,256>::`vftable';
      Buffer = CLMString::GetBuffer((CLMString *)&v29, 260);
      if ( CWin32RegAccess::Get((CWin32RegAccess *)&phkResult, L"Extension", Buffer, 0x104u) )
      {
        CLMString::ReleaseBuffer((CLMString *)&v29, v18);
        v19 = operator new(0xB0u);
        *v19 = 0;
        v19[1] = 0;
        TLMString<32,32,128>::TLMString<32,32,128>(v19 + 2, a2);
        v20 = v30;
        v19[14] = &CLMString::`vftable';
        v19[15] = v19 + 17;
        *((_DWORD *)v19 + 32) = 17;
        CLMString::AssignInConstructor((CLMString *)(v19 + 14), v20, 0xFFFFFFFF);
        v19[14] = &TLMString<16,32,256>::`vftable';
        v21 = (unsigned int)PSmallStringHash(v19 + 2) % *(_DWORD *)(a1 + 40);
        v22 = *(_QWORD *)(a1 + 48);
        *v19 = *(_QWORD *)(v22 + 8 * v21);
        v19[1] = v19;
        *(_QWORD *)(v22 + 8LL * (unsigned int)v21) = v19;
        ++*(_DWORD *)(a1 + 44);
        CLMString::operator=(v27, v30);
        TLMString<16,32,256>::~TLMString<16,32,256>(&v29);
        CWin32RegAccess::~CWin32RegAccess((CWin32RegAccess *)&phkResult);
        TLMString<64,64,32767>::~TLMString<64,64,32767>(v33);
        v23 = (struct _RTL_CRITICAL_SECTION *)(a1 + 152);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
        if ( *v12 == 1 )
          *(_DWORD *)(a1 + 92) = 0;
LABEL_44:
        _InterlockedDecrement(v12);
        CSyncReadWrite::LokInitReadEvent((CSyncReadWrite *)(a1 + 88));
        CEventSem::Set((CEventSem *)(a1 + 200));
        v14 = v23;
LABEL_45:
        LeaveCriticalSection(v14);
        v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 104);
LABEL_46:
        LeaveCriticalSection(v11);
        return v8;
      }
      TLMString<16,32,256>::~TLMString<16,32,256>(&v29);
    }
    CWin32RegAccess::~CWin32RegAccess((CWin32RegAccess *)&phkResult);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v33);
    v23 = (struct _RTL_CRITICAL_SECTION *)(a1 + 152);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
    if ( *v12 == 1 )
      *(_DWORD *)(a1 + 92) = 0;
    v8 = 0;
    goto LABEL_44;
  }
  CLMString::operator=(a3, *(_QWORD *)(v10 + 120));
  if ( *(_DWORD *)v6 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
    _InterlockedDecrement((volatile signed __int32 *)(v6 + 8));
LABEL_16:
    if ( !*(_DWORD *)(v6 + 8) )
    {
      CSyncReadWrite::LokInitWriteEvent((CSyncReadWrite *)v6);
      CEventSem::Set((CEventSem *)(v6 + 120));
    }
    v11 = (struct _RTL_CRITICAL_SECTION *)(v6 + 64);
    goto LABEL_46;
  }
  _InterlockedDecrement((volatile signed __int32 *)(v6 + 8));
  if ( *(_DWORD *)v6 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
    goto LABEL_16;
  }
  return v8;
}

```

## disassembly

```asm
0x180158c7c  mov     [rsp-8+arg_18], rbx
0x180158c81  push    rbp
0x180158c82  push    rsi
0x180158c83  push    rdi
0x180158c84  push    r12
0x180158c86  push    r13
0x180158c88  push    r14
0x180158c8a  push    r15
0x180158c8c  lea     rbp, [rsp-50h]
0x180158c91  sub     rsp, 150h
0x180158c98  mov     rax, cs:__security_cookie
0x180158c9f  xor     rax, rsp
0x180158ca2  mov     [rbp+80h+var_40], rax
0x180158ca6  mov     r14, r8
0x180158ca9  mov     [rsp+180h+var_138], r8
0x180158cae  mov     r12, rdx
0x180158cb1  mov     r13, rcx
0x180158cb4  lea     rbx, [rcx+58h]
0x180158cb8  mov     [rsp+180h+var_150], rbx
0x180158cbd  xor     esi, esi
0x180158cbf  lea     r15d, [rsi+1]
0x180158cc3  cmp     [rbx], esi
0x180158cc5  jz      short loc_180158D0F
0x180158cc7  xor     edi, edi
0x180158cc9  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158ccd  call    cs:__imp_EnterCriticalSection
0x180158cd3  cmp     [rbx], edi
0x180158cd5  jz      short loc_180158CEB
0x180158cd7  mov     rcx, rbx; this
0x180158cda  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x180158cdf  lea     rcx, [rbx+70h]; this
0x180158ce3  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x180158ce8  mov     edi, r15d
0x180158ceb  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158cef  call    cs:__imp_LeaveCriticalSection
0x180158cf5  test    edi, edi
0x180158cf7  jz      short loc_180158D08
0x180158cf9  lea     rcx, [rbx+70h]; this
0x180158cfd  xor     r8d, r8d; int
0x180158d00  or      edx, 0FFFFFFFFh; unsigned int
0x180158d03  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x180158d08  cmp     dword ptr [rbx], 0
0x180158d0b  jnz     short loc_180158CC7
0x180158d0d  xor     esi, esi
0x180158d0f  lock add [rbx+8], r15d
0x180158d14  cmp     [rbx], esi
0x180158d16  jz      short loc_180158D22
0x180158d18  mov     rcx, rbx; this
0x180158d1b  call    ?SyncReadDecrement@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::SyncReadDecrement(void)
0x180158d20  jmp     short loc_180158CC3
0x180158d22  lea     rcx, [r13+28h]
0x180158d26  mov     rdx, r12
0x180158d29  call    ?Lookup@?$CTKPLiteHashMap@V?$TLMString@$0CA@$0CA@$0IA@@@V?$CMimeToDataTableEntry@U_GUID@@@@@@QEBAPEAV?$CMimeToDataTableEntry@U_GUID@@@@PEBV?$TLMString@$0CA@$0CA@$0IA@@@@Z; CTKPLiteHashMap<TLMString<32,32,128>,CMimeToDataTableEntry<_GUID>>::Lookup(TLMString<32,32,128> const *)
0x180158d2e  test    rax, rax
0x180158d31  jz      short loc_180158D89
0x180158d33  mov     rdx, [rax+78h]
0x180158d37  mov     rcx, r14
0x180158d3a  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180158d3f  nop
0x180158d40  cmp     [rbx], esi
0x180158d42  jz      short loc_180158D54
0x180158d44  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158d48  call    cs:__imp_EnterCriticalSection
0x180158d4e  lock dec dword ptr [rbx+8]
0x180158d52  jmp     short loc_180158D6A
0x180158d54  lock dec dword ptr [rbx+8]
0x180158d58  cmp     [rbx], esi
0x180158d5a  jz      loc_180159089
0x180158d60  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158d64  call    cs:__imp_EnterCriticalSection
0x180158d6a  cmp     [rbx+8], esi
0x180158d6d  jnz     short loc_180158D80
0x180158d6f  mov     rcx, rbx; this
0x180158d72  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x180158d77  lea     rcx, [rbx+78h]; this
0x180158d7b  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180158d80  lea     rcx, [rbx+40h]
0x180158d84  jmp     loc_180159083
0x180158d89  cmp     [rbx], esi
0x180158d8b  jz      short loc_180158D9D
0x180158d8d  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158d91  call    cs:__imp_EnterCriticalSection
0x180158d97  lock dec dword ptr [rbx+8]
0x180158d9b  jmp     short loc_180158DAF
0x180158d9d  lock dec dword ptr [rbx+8]
0x180158da1  cmp     [rbx], esi
0x180158da3  jz      short loc_180158DCF
0x180158da5  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158da9  call    cs:__imp_EnterCriticalSection
0x180158daf  cmp     [rbx+8], esi
0x180158db2  jnz     short loc_180158DC5
0x180158db4  mov     rcx, rbx; this
0x180158db7  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x180158dbc  lea     rcx, [rbx+78h]; this
0x180158dc0  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180158dc5  lea     rcx, [rbx+40h]; lpCriticalSection
0x180158dc9  call    cs:__imp_LeaveCriticalSection
0x180158dcf  lea     r14, [r13+58h]
0x180158dd3  mov     [rsp+180h+var_130], r14
0x180158dd8  lea     rcx, [r14+10h]; lpCriticalSection
0x180158ddc  call    cs:__imp_EnterCriticalSection
0x180158de2  lock add [r14], r15d
0x180158de6  call    cs:__imp_GetCurrentThreadId
0x180158dec  mov     [r14+4], eax
0x180158df0  lea     rdi, [r14+40h]
0x180158df4  mov     rcx, rdi; lpCriticalSection
0x180158df7  call    cs:__imp_EnterCriticalSection
0x180158dfd  cmp     dword ptr [r14+8], 0
0x180158e02  jz      short loc_180158E18
0x180158e04  mov     rcx, r14; this
0x180158e07  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x180158e0c  lea     rcx, [r14+78h]; this
0x180158e10  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x180158e15  mov     esi, r15d
0x180158e18  mov     rcx, rdi; lpCriticalSection
0x180158e1b  call    cs:__imp_LeaveCriticalSection
0x180158e21  test    esi, esi
0x180158e23  jz      short loc_180158E35
0x180158e25  xor     r8d, r8d; int
0x180158e28  or      edx, 0FFFFFFFFh; unsigned int
0x180158e2b  lea     rcx, [r14+78h]; this
0x180158e2f  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x180158e34  nop
0x180158e35  lea     rcx, [r13+28h]
0x180158e39  mov     rdx, r12
0x180158e3c  call    ?Lookup@?$CTKPLiteHashMap@V?$TLMString@$0CA@$0CA@$0IA@@@V?$CMimeToDataTableEntry@U_GUID@@@@@@QEBAPEAV?$CMimeToDataTableEntry@U_GUID@@@@PEBV?$TLMString@$0CA@$0CA@$0IA@@@@Z; CTKPLiteHashMap<TLMString<32,32,128>,CMimeToDataTableEntry<_GUID>>::Lookup(TLMString<32,32,128> const *)
0x180158e41  test    rax, rax
0x180158e44  jz      short loc_180158E88
0x180158e46  mov     rdx, [rax+78h]
0x180158e4a  mov     rcx, [rsp+180h+var_138]
0x180158e4f  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180158e54  nop
0x180158e55  mov     rcx, rdi; lpCriticalSection
0x180158e58  call    cs:__imp_EnterCriticalSection
0x180158e5e  cmp     [r14], r15d
0x180158e61  jnz     short loc_180158E6B
0x180158e63  mov     dword ptr [r14+4], 0
0x180158e6b  lock dec dword ptr [r14]
0x180158e6f  mov     rcx, r14; this
0x180158e72  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x180158e77  lea     rcx, [r14+70h]; this
0x180158e7b  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180158e80  mov     rcx, rdi
0x180158e83  jmp     loc_180159079
0x180158e88  lea     rdx, aSoftwareClasse; "Software\\Classes\\MIME\\Database\\Cont"...
0x180158e8f  lea     rcx, [rbp+80h+var_E0]
0x180158e93  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x180158e98  nop
0x180158e99  mov     r8d, [r12+14h]; unsigned int
0x180158e9e  mov     rdx, [r12+8]; wchar_t *
0x180158ea3  lea     rcx, [rbp+80h+var_E0]; this
0x180158ea7  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180158eac  xor     edi, edi
0x180158eae  mov     [rsp+180h+phkResult], rdi
0x180158eb3  mov     [rsp+180h+var_140], rdi
0x180158eb8  mov     [rsp+180h+var_160], 20019h; unsigned int
0x180158ec0  mov     r8, [rbp+80h+lpSubKey]; lpSubKey
0x180158ec4  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180158ecb  lea     rcx, [rsp+180h+phkResult]; phkResult
0x180158ed0  call    ?OpenKey@CWin32RegAccess@@IEAAXPEAUHKEY__@@PEB_W1K@Z; CWin32RegAccess::OpenKey(HKEY__ *,wchar_t const *,wchar_t const *,ulong)
0x180158ed5  nop
0x180158ed6  mov     eax, dword ptr [rsp+180h+var_140]
0x180158eda  test    eax, eax
0x180158edc  jle     short loc_180158EE8
0x180158ede  movzx   eax, ax
0x180158ee1  or      eax, 80070000h
0x180158ee6  test    eax, eax
0x180158ee8  js      loc_180159033
0x180158eee  lea     rax, [rsp+180h+var_108]
0x180158ef3  mov     [rsp+180h+var_118], rax
0x180158ef8  mov     [rsp+180h+var_110], 11h
0x180158f01  mov     [rsp+180h+var_108], di
0x180158f06  lea     rax, ??_7?$TLMString@$0BA@$0CA@$0BAA@@@6B@; const TLMString<16,32,256>::`vftable'
0x180158f0d  mov     [rsp+180h+var_120], rax
0x180158f12  mov     ebx, 104h
0x180158f17  mov     edx, ebx; int
0x180158f19  lea     rcx, [rsp+180h+var_120]; this
0x180158f1e  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180158f23  mov     r8, rax; wchar_t *
0x180158f26  mov     r9d, ebx; unsigned int
0x180158f29  lea     rdx, aExtension; "Extension"
0x180158f30  lea     rcx, [rsp+180h+phkResult]; this
0x180158f35  call    ?Get@CWin32RegAccess@@QEAAHPEB_WPEA_WI@Z; CWin32RegAccess::Get(wchar_t const *,wchar_t *,uint)
0x180158f3a  test    eax, eax
0x180158f3c  jz      loc_180159028
0x180158f42  lea     rcx, [rsp+180h+var_120]; this
0x180158f47  call    ?ReleaseBuffer@CLMString@@QEAAXH@Z; CLMString::ReleaseBuffer(int)
0x180158f4c  lea     ecx, [rbx-54h]; Size
0x180158f4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180158f54  mov     rsi, rax
0x180158f57  mov     [rsp+180h+var_150], rax
0x180158f5c  mov     [rax], rdi
0x180158f5f  mov     [rax+8], rdi
0x180158f63  mov     rdx, r12
0x180158f66  lea     rcx, [rax+10h]
0x180158f6a  call    ??0?$TLMString@$0CA@$0CA@$0IA@@@QEAA@AEBV0@@Z; TLMString<32,32,128>::TLMString<32,32,128>(TLMString<32,32,128> const &)
0x180158f6f  nop
0x180158f70  lea     rbx, [rsi+70h]
0x180158f74  mov     rdx, [rsp+180h+var_118]; wchar_t *
0x180158f79  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180158f80  mov     [rbx], rax
0x180158f83  lea     rax, [rbx+18h]
0x180158f87  mov     [rbx+8], rax
0x180158f8b  mov     dword ptr [rbx+10h], 11h
0x180158f92  or      r8d, 0FFFFFFFFh; unsigned int
0x180158f96  mov     rcx, rbx; this
0x180158f99  call    ?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z; CLMString::AssignInConstructor(wchar_t const *,uint)
0x180158f9e  lea     rax, ??_7?$TLMString@$0BA@$0CA@$0BAA@@@6B@; const TLMString<16,32,256>::`vftable'
0x180158fa5  mov     [rbx], rax
0x180158fa8  mov     [rsp+180h+var_150], rsi
0x180158fad  lea     rcx, [rsi+10h]
0x180158fb1  call    ?PSmallStringHash@@YAKPEBV?$TLMString@$0CA@$0CA@$0EAA@@@@Z; PSmallStringHash(TLMString<32,32,1024> const *)
0x180158fb6  xor     edx, edx
0x180158fb8  div     dword ptr [r13+28h]
0x180158fbc  mov     rcx, [r13+30h]
0x180158fc0  mov     rax, [rcx+rdx*8]
0x180158fc4  mov     [rsi], rax
0x180158fc7  mov     [rsi+8], rsi
0x180158fcb  mov     [rcx+rdx*8], rsi
0x180158fcf  add     [r13+2Ch], r15d
0x180158fd3  mov     [rsp+180h+var_150], 0
0x180158fdc  mov     rdx, [rsp+180h+var_118]
0x180158fe1  mov     rcx, [rsp+180h+var_138]
0x180158fe6  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180158feb  nop
0x180158fec  lea     rcx, [rsp+180h+var_120]
0x180158ff1  call    ??1?$TLMString@$0BA@$0CA@$0BAA@@@UEAA@XZ; TLMString<16,32,256>::~TLMString<16,32,256>(void)
0x180158ff6  nop
0x180158ff7  lea     rcx, [rsp+180h+phkResult]; this
0x180158ffc  call    ??1CWin32RegAccess@@QEAA@XZ; CWin32RegAccess::~CWin32RegAccess(void)
0x180159001  nop
0x180159002  lea     rcx, [rbp+80h+var_E0]
0x180159006  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x18015900b  nop
0x18015900c  lea     rbx, [r14+40h]
0x180159010  mov     rcx, rbx; lpCriticalSection
0x180159013  call    cs:__imp_EnterCriticalSection
0x180159019  cmp     [r14], r15d
0x18015901c  jnz     short loc_180159061
0x18015901e  mov     dword ptr [r14+4], 0
0x180159026  jmp     short loc_180159061
0x180159028  lea     rcx, [rsp+180h+var_120]
0x18015902d  call    ??1?$TLMString@$0BA@$0CA@$0BAA@@@UEAA@XZ; TLMString<16,32,256>::~TLMString<16,32,256>(void)
0x180159032  nop
0x180159033  lea     rcx, [rsp+180h+phkResult]; this
0x180159038  call    ??1CWin32RegAccess@@QEAA@XZ; CWin32RegAccess::~CWin32RegAccess(void)
0x18015903d  nop
0x18015903e  lea     rcx, [rbp+80h+var_E0]
0x180159042  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180159047  nop
0x180159048  lea     rbx, [r14+40h]
0x18015904c  mov     rcx, rbx; lpCriticalSection
0x18015904f  call    cs:__imp_EnterCriticalSection
0x180159055  cmp     [r14], r15d
0x180159058  jnz     short loc_18015905E
0x18015905a  mov     [r14+4], edi
0x18015905e  mov     r15d, edi
0x180159061  lock dec dword ptr [r14]
0x180159065  mov     rcx, r14; this
0x180159068  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x18015906d  lea     rcx, [r14+70h]; this
0x180159071  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x180159076  mov     rcx, rbx; lpCriticalSection
0x180159079  call    cs:__imp_LeaveCriticalSection
0x18015907f  lea     rcx, [r14+10h]; lpCriticalSection
0x180159083  call    cs:__imp_LeaveCriticalSection
0x180159089  mov     eax, r15d
0x18015908c  mov     rcx, [rbp+80h+var_40]
0x180159090  xor     rcx, rsp; StackCookie
0x180159093  call    __security_check_cookie
0x180159098  mov     rbx, [rsp+180h+arg_18]
0x1801590a0  add     rsp, 150h
0x1801590a7  pop     r15
0x1801590a9  pop     r14
0x1801590ab  pop     r13
0x1801590ad  pop     r12
0x1801590af  pop     rdi
0x1801590b0  pop     rsi
0x1801590b1  pop     rbp
0x1801590b2  retn
```
