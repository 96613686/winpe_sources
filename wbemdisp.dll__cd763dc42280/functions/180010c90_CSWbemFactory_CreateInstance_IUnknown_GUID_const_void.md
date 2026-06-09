# CSWbemFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180010c90`
- end: `0x180010ee2`
- name: `?CreateInstance@CSWbemFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `594`
- prototype: `__int64 __fastcall(CSWbemFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010590`
- `0x180010c90`
- `0x180010ee8`
- `0x1800112ac`
- `0x1800112fc`
- `0x180018574`
- `0x18001e408`
- `0x180022eb4`
- `0x180026e70`
- `0x180027224`
- `0x180030b44`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ecd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010ecd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010eaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010eaf`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010cfb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010d5e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010d80`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010da7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010dd4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010e0c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010e7d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010cfb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010d5e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010d80`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010da7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010dd4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010e0c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180010e7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSWbemFactory::CreateInstance(
        CSWbemFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  int v9; // eax
  CSWbemDateTime *v10; // rax
  CWbemParseDN *v11; // rdi
  unsigned int v12; // ebx
  CWbemParseDN *v13; // rax
  CSWbemLocator *v14; // rax
  struct IDispatch *v15; // rax
  CSWbemObjectPath *v16; // rax
  CSWbemSink *v17; // rax
  CSWbemSink *v18; // rbx
  unsigned int v19; // edx
  int v20; // edi
  struct IDispatch *v21; // rax
  struct _RTL_CRITICAL_SECTION *v22; // rcx

  *a4 = 0;
  result = EnsureGlobalsInitialized();
  if ( (int)result >= 0 )
  {
    if ( a2 )
      return 2147746064LL;
    v9 = *((_DWORD *)this + 3);
    if ( !v9 )
    {
      v14 = (CSWbemLocator *)CWin32DefaultArena::WbemMemAlloc(0xA0u);
      if ( v14 )
        v11 = CSWbemLocator::CSWbemLocator(v14, 0);
      else
        v11 = 0;
      goto LABEL_11;
    }
    if ( v9 != 5 )
    {
      switch ( v9 )
      {
        case 1:
          v15 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0x98u);
          if ( !v15 )
            goto LABEL_10;
          v11 = (CWbemParseDN *)CSWbemNamedValueSet::CSWbemNamedValueSet(v15);
          break;
        case 2:
          v16 = (CSWbemObjectPath *)CWin32DefaultArena::WbemMemAlloc(0x98u);
          if ( v16 )
            v11 = CSWbemObjectPath::CSWbemObjectPath(v16, 0, 0);
          else
            v11 = 0;
          break;
        case 3:
          v13 = (CWbemParseDN *)CWin32DefaultArena::WbemMemAlloc(0x10u);
          if ( !v13 )
            goto LABEL_10;
          v11 = CWbemParseDN::CWbemParseDN(v13);
          break;
        case 6:
          v10 = (CSWbemDateTime *)CWin32DefaultArena::WbemMemAlloc(0xB0u);
          if ( !v10 )
          {
LABEL_10:
            v11 = 0;
            break;
          }
          v11 = CSWbemDateTime::CSWbemDateTime(v10);
          break;
        case 7:
          v21 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0xA0u);
          if ( v21 )
            v11 = CSWbemRefresher::CSWbemRefresher(v21);
          else
            v11 = 0;
          break;
        case 4:
          v11 = 0;
          EnterCriticalSection(&g_csErrorCache);
          if ( g_pErrorCache )
            v11 = CWbemErrorCache::GetAndResetCurrentThreadError(v22);
          LeaveCriticalSection(&g_csErrorCache);
          break;
        default:
          return 2147500037LL;
      }
LABEL_11:
      if ( v11 )
      {
        (*(void (__fastcall **)(CWbemParseDN *))(*(_QWORD *)v11 + 8LL))(v11);
        v12 = (**(__int64 (__fastcall ***)(CWbemParseDN *, const struct _GUID *, void **))v11)(v11, a3, a4);
        (*(void (__fastcall **)(CWbemParseDN *))(*(_QWORD *)v11 + 16LL))(v11);
        return v12;
      }
      return 2147500037LL;
    }
    v17 = (CSWbemSink *)CWin32DefaultArena::WbemMemAlloc(0xA8u);
    if ( v17 )
      v18 = CSWbemSink::CSWbemSink(v17);
    else
      v18 = 0;
    if ( v18 )
    {
      v20 = (**(__int64 (__fastcall ***)(CSWbemSink *, const struct _GUID *, void **))v18)(v18, a3, a4);
      if ( v20 < 0 )
        CSWbemSink::`scalar deleting destructor'(v18, v19);
      return (unsigned int)v20;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010c90  push    rbx
0x180010c92  push    rbp
0x180010c93  push    rsi
0x180010c94  push    rdi
0x180010c95  sub     rsp, 28h
0x180010c99  mov     rsi, r9
0x180010c9c  mov     rbp, r8
0x180010c9f  mov     rbx, rdx
0x180010ca2  mov     rdi, rcx
0x180010ca5  mov     qword ptr [r9], 0
0x180010cac  call    ?EnsureGlobalsInitialized@@YAJXZ; EnsureGlobalsInitialized(void)
0x180010cb1  test    eax, eax
0x180010cb3  js      loc_180010D50
0x180010cb9  test    rbx, rbx
0x180010cbc  jnz     loc_180010DFD
0x180010cc2  mov     eax, [rdi+0Ch]
0x180010cc5  test    eax, eax
0x180010cc7  jz      loc_180010D7B
0x180010ccd  cmp     eax, 5
0x180010cd0  jz      loc_180010E07
0x180010cd6  cmp     eax, 1
0x180010cd9  jz      loc_180010DA2
0x180010cdf  cmp     eax, 2
0x180010ce2  jz      loc_180010DCF
0x180010ce8  cmp     eax, 3
0x180010ceb  jz      short loc_180010D59
0x180010ced  cmp     eax, 6
0x180010cf0  jnz     loc_180010E73
0x180010cf6  mov     ecx, 0B0h
0x180010cfb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010d01  mov     [rsp+48h+arg_18], rax
0x180010d06  test    rax, rax
0x180010d09  jnz     loc_180010E63
0x180010d0f  xor     edi, edi
0x180010d11  test    rdi, rdi
0x180010d14  jz      loc_180010ED8
0x180010d1a  mov     rcx, [rdi]
0x180010d1d  mov     rax, [rcx+8]
0x180010d21  mov     rcx, rdi
0x180010d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d29  mov     rax, [rdi]
0x180010d2c  mov     r8, rsi
0x180010d2f  mov     rdx, rbp
0x180010d32  mov     rcx, rdi
0x180010d35  mov     rax, [rax]
0x180010d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d3d  mov     ebx, eax
0x180010d3f  mov     rcx, [rdi]
0x180010d42  mov     rax, [rcx+10h]
0x180010d46  mov     rcx, rdi
0x180010d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d4e  mov     eax, ebx
0x180010d50  add     rsp, 28h
0x180010d54  pop     rdi
0x180010d55  pop     rsi
0x180010d56  pop     rbp
0x180010d57  pop     rbx
0x180010d58  retn
0x180010d59  mov     ecx, 10h
0x180010d5e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010d64  mov     [rsp+48h+arg_18], rax
0x180010d69  test    rax, rax
0x180010d6c  jz      short loc_180010D0F
0x180010d6e  mov     rcx, rax; this
0x180010d71  call    ??0CWbemParseDN@@QEAA@XZ; CWbemParseDN::CWbemParseDN(void)
0x180010d76  mov     rdi, rax
0x180010d79  jmp     short loc_180010D11
0x180010d7b  mov     ecx, 0A0h
0x180010d80  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010d86  mov     [rsp+48h+arg_18], rax
0x180010d8b  test    rax, rax
0x180010d8e  jz      short loc_180010DCB
0x180010d90  xor     edx, edx; struct CSWbemPrivilegeSet *
0x180010d92  mov     rcx, rax; this
0x180010d95  call    ??0CSWbemLocator@@QEAA@PEAVCSWbemPrivilegeSet@@@Z; CSWbemLocator::CSWbemLocator(CSWbemPrivilegeSet *)
0x180010d9a  mov     rdi, rax
0x180010d9d  jmp     loc_180010D11
0x180010da2  mov     ecx, 98h
0x180010da7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010dad  mov     [rsp+48h+arg_18], rax
0x180010db2  test    rax, rax
0x180010db5  jz      loc_180010D0F
0x180010dbb  mov     rcx, rax; this
0x180010dbe  call    ??0CSWbemNamedValueSet@@QEAA@XZ; CSWbemNamedValueSet::CSWbemNamedValueSet(void)
0x180010dc3  mov     rdi, rax
0x180010dc6  jmp     loc_180010D11
0x180010dcb  xor     edi, edi
0x180010dcd  jmp     short loc_180010D9D
0x180010dcf  mov     ecx, 98h
0x180010dd4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010dda  mov     [rsp+48h+arg_18], rax
0x180010ddf  test    rax, rax
0x180010de2  jz      short loc_180010DF9
0x180010de4  xor     r8d, r8d; unsigned __int16 *
0x180010de7  xor     edx, edx; struct CSWbemSecurity *
0x180010de9  mov     rcx, rax; this
0x180010dec  call    ??0CSWbemObjectPath@@QEAA@PEAVCSWbemSecurity@@PEAG@Z; CSWbemObjectPath::CSWbemObjectPath(CSWbemSecurity *,ushort *)
0x180010df1  mov     rdi, rax
0x180010df4  jmp     loc_180010D11
0x180010df9  xor     edi, edi
0x180010dfb  jmp     short loc_180010DF4
0x180010dfd  mov     eax, 80040110h
0x180010e02  jmp     loc_180010D50
0x180010e07  mov     ecx, 0A8h
0x180010e0c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010e12  mov     [rsp+48h+arg_18], rax
0x180010e17  test    rax, rax
0x180010e1a  jz      short loc_180010E29
0x180010e1c  mov     rcx, rax; this
0x180010e1f  call    ??0CSWbemSink@@QEAA@XZ; CSWbemSink::CSWbemSink(void)
0x180010e24  mov     rbx, rax
0x180010e27  jmp     short loc_180010E2B
0x180010e29  xor     ebx, ebx
0x180010e2b  test    rbx, rbx
0x180010e2e  jnz     short loc_180010E3A
0x180010e30  mov     eax, 8007000Eh
0x180010e35  jmp     loc_180010D50
0x180010e3a  mov     rax, [rbx]
0x180010e3d  mov     r8, rsi
0x180010e40  mov     rdx, rbp
0x180010e43  mov     rcx, rbx
0x180010e46  mov     rax, [rax]
0x180010e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e4e  mov     edi, eax
0x180010e50  test    eax, eax
0x180010e52  jns     short loc_180010E5C
0x180010e54  mov     rcx, rbx; this
0x180010e57  call    ??_GCSWbemSink@@QEAAPEAXI@Z; CSWbemSink::`scalar deleting destructor'(uint)
0x180010e5c  mov     eax, edi
0x180010e5e  jmp     loc_180010D50
0x180010e63  mov     rcx, rax; this
0x180010e66  call    ??0CSWbemDateTime@@QEAA@XZ; CSWbemDateTime::CSWbemDateTime(void)
0x180010e6b  mov     rdi, rax
0x180010e6e  jmp     loc_180010D11
0x180010e73  cmp     eax, 7
0x180010e76  jnz     short loc_180010EA1
0x180010e78  mov     ecx, 0A0h
0x180010e7d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180010e83  mov     [rsp+48h+arg_18], rax
0x180010e88  test    rax, rax
0x180010e8b  jz      short loc_180010E9A
0x180010e8d  mov     rcx, rax; this
0x180010e90  call    ??0CSWbemRefresher@@QEAA@XZ; CSWbemRefresher::CSWbemRefresher(void)
0x180010e95  mov     rdi, rax
0x180010e98  jmp     short loc_180010E9C
0x180010e9a  xor     edi, edi
0x180010e9c  jmp     loc_180010D11
0x180010ea1  cmp     eax, 4
0x180010ea4  jnz     short loc_180010ED8
0x180010ea6  xor     edi, edi
0x180010ea8  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010eaf  call    cs:__imp_EnterCriticalSection
0x180010eb5  cmp     cs:?g_pErrorCache@@3PEAVCWbemErrorCache@@EA, rdi; CWbemErrorCache * g_pErrorCache
0x180010ebc  jz      short loc_180010EC6
0x180010ebe  call    ?GetAndResetCurrentThreadError@CWbemErrorCache@@QEAAPEAVCSWbemObject@@XZ; CWbemErrorCache::GetAndResetCurrentThreadError(void)
0x180010ec3  mov     rdi, rax
0x180010ec6  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010ecd  call    cs:__imp_LeaveCriticalSection
0x180010ed3  jmp     loc_180010D11
0x180010ed8  mov     eax, 80004005h
0x180010edd  jmp     loc_180010D50
```
