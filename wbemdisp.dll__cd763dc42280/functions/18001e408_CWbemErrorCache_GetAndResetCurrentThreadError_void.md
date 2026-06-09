# CWbemErrorCache::GetAndResetCurrentThreadError(void)

- ea: `0x18001e408`
- end: `0x18001e5d3`
- name: `?GetAndResetCurrentThreadError@CWbemErrorCache@@QEAAPEAVCSWbemObject@@XZ`
- size: `459`
- prototype: `struct CSWbemObject *__fastcall(CWbemErrorCache *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010c90`

## callees

- `0x180006550`
- `0x180009320`
- `0x18001d064`
- `0x18001e408`
- `0x180033d68`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001e506`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e518`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e52a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e506`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e518`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e52a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e5bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e5bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e422`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e422`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e494`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e553`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e494`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001e553`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e5b1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001e5b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct CSWbemObject *__fastcall CWbemErrorCache::GetAndResetCurrentThreadError(struct _RTL_CRITICAL_SECTION *this)
{
  CWbemErrorCache *v1; // rdi
  CSWbemObject *v2; // rsi
  DWORD CurrentThreadId; // ebp
  __int64 *i; // rbx
  __int64 *v5; // rcx
  struct CSWbemServices *v6; // rdi
  struct IDispatch *v7; // rcx
  __int64 v8; // rcx
  struct _COAUTHIDENTITY *v9; // rcx
  CSWbemObject *v10; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp+8h] BYREF
  void *v13; // [rsp+58h] [rbp+10h]

  lpCriticalSection = this;
  v1 = g_pErrorCache;
  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v1 + 8));
  for ( i = (__int64 *)*((_QWORD *)v1 + 6); i; i = (__int64 *)*i )
  {
    if ( CurrentThreadId == *((_DWORD *)i + 4) )
    {
      if ( i[8] )
      {
        if ( i == *((__int64 **)v1 + 6) )
          *((_QWORD *)v1 + 6) = *i;
        if ( *i )
          *(_QWORD *)(*i + 8) = i[1];
        v5 = (__int64 *)i[1];
        if ( v5 )
          *v5 = *i;
        v6 = 0;
        if ( i[7] )
        {
          v7 = (struct IDispatch *)CWin32DefaultArena::WbemMemAlloc(0xA8u);
          v13 = v7;
          v6 = v7
             ? CSWbemServices::CSWbemServices(
                 v7,
                 (struct IWbemServices *)i[7],
                 (unsigned __int16 *)i[6],
                 (struct _COAUTHIDENTITY *)i[3],
                 (unsigned __int16 *)i[5],
                 (unsigned __int16 *)i[4])
             : 0LL;
          if ( v6 )
            (*(void (__fastcall **)(struct CSWbemServices *))(*(_QWORD *)v6 + 8LL))(v6);
        }
        v8 = i[7];
        if ( v8 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          i[7] = 0;
        }
        SysFreeString((BSTR)i[6]);
        i[6] = 0;
        SysFreeString((BSTR)i[4]);
        i[4] = 0;
        SysFreeString((BSTR)i[5]);
        i[5] = 0;
        v9 = (struct _COAUTHIDENTITY *)i[3];
        if ( v9 )
        {
          WbemFreeAuthIdentity(v9);
          i[3] = 0;
        }
        v10 = (CSWbemObject *)CWin32DefaultArena::WbemMemAlloc(0x78u);
        v13 = v10;
        if ( v10 )
          v2 = CSWbemObject::CSWbemObject(v10, v6, (struct IWbemClassObject *)i[8], 0, 1);
        else
          v2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)i[8] + 16LL))(i[8]);
        i[8] = 0;
        if ( v6 )
          (*(void (__fastcall **)(struct CSWbemServices *))(*(_QWORD *)v6 + 16LL))(v6);
        CWin32DefaultArena::WbemMemFree(i);
      }
      break;
    }
  }
  LeaveCriticalSection(lpCriticalSection);
  return v2;
}

```

## disassembly

```asm
0x18001e408  mov     [rsp+arg_10], rbx
0x18001e40d  mov     [rsp+lpCriticalSection], rcx
0x18001e412  push    rbp
0x18001e413  push    rsi
0x18001e414  push    rdi
0x18001e415  sub     rsp, 30h
0x18001e419  mov     rdi, cs:?g_pErrorCache@@3PEAVCWbemErrorCache@@EA; CWbemErrorCache * g_pErrorCache
0x18001e420  xor     esi, esi
0x18001e422  call    cs:__imp_GetCurrentThreadId
0x18001e428  mov     ebp, eax
0x18001e42a  lea     rdx, [rdi+8]; struct _RTL_CRITICAL_SECTION *
0x18001e42e  lea     rcx, [rsp+48h+lpCriticalSection]; this
0x18001e433  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001e438  nop
0x18001e439  mov     rbx, [rdi+30h]
0x18001e43d  test    rbx, rbx
0x18001e440  jz      loc_18001E5B8
0x18001e446  cmp     ebp, [rbx+10h]
0x18001e449  jz      short loc_18001E450
0x18001e44b  mov     rbx, [rbx]
0x18001e44e  jmp     short loc_18001E43D
0x18001e450  cmp     qword ptr [rbx+40h], 0
0x18001e455  jz      loc_18001E5B8
0x18001e45b  cmp     rbx, [rdi+30h]
0x18001e45f  jnz     short loc_18001E468
0x18001e461  mov     rax, [rbx]
0x18001e464  mov     [rdi+30h], rax
0x18001e468  mov     rcx, [rbx]
0x18001e46b  test    rcx, rcx
0x18001e46e  jz      short loc_18001E478
0x18001e470  mov     rax, [rbx+8]
0x18001e474  mov     [rcx+8], rax
0x18001e478  mov     rcx, [rbx+8]
0x18001e47c  test    rcx, rcx
0x18001e47f  jz      short loc_18001E487
0x18001e481  mov     rax, [rbx]
0x18001e484  mov     [rcx], rax
0x18001e487  xor     edi, edi
0x18001e489  cmp     [rbx+38h], rdi
0x18001e48d  jz      short loc_18001E4E5
0x18001e48f  mov     ecx, 0A8h
0x18001e494  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e49a  mov     rcx, rax; this
0x18001e49d  mov     [rsp+48h+arg_8], rax
0x18001e4a2  test    rax, rax
0x18001e4a5  jz      short loc_18001E4CF
0x18001e4a7  mov     rax, [rbx+20h]
0x18001e4ab  mov     [rsp+48h+var_20], rax; unsigned __int16 *
0x18001e4b0  mov     rax, [rbx+28h]
0x18001e4b4  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x18001e4b9  mov     r9, [rbx+18h]; struct _COAUTHIDENTITY *
0x18001e4bd  mov     r8, [rbx+30h]; unsigned __int16 *
0x18001e4c1  mov     rdx, [rbx+38h]; struct IWbemServices *
0x18001e4c5  call    ??0CSWbemServices@@QEAA@PEAUIWbemServices@@PEAGPEAU_COAUTHIDENTITY@@11@Z; CSWbemServices::CSWbemServices(IWbemServices *,ushort *,_COAUTHIDENTITY *,ushort *,ushort *)
0x18001e4ca  mov     rdi, rax
0x18001e4cd  jmp     short loc_18001E4D1
0x18001e4cf  xor     edi, edi
0x18001e4d1  test    rdi, rdi
0x18001e4d4  jz      short loc_18001E4E5
0x18001e4d6  mov     rax, [rdi]
0x18001e4d9  mov     rcx, rdi
0x18001e4dc  mov     rax, [rax+8]
0x18001e4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4e5  mov     rcx, [rbx+38h]
0x18001e4e9  test    rcx, rcx
0x18001e4ec  jz      short loc_18001E502
0x18001e4ee  mov     rax, [rcx]
0x18001e4f1  mov     rax, [rax+10h]
0x18001e4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4fa  mov     qword ptr [rbx+38h], 0
0x18001e502  mov     rcx, [rbx+30h]; bstrString
0x18001e506  call    cs:__imp_SysFreeString
0x18001e50c  mov     qword ptr [rbx+30h], 0
0x18001e514  mov     rcx, [rbx+20h]; bstrString
0x18001e518  call    cs:__imp_SysFreeString
0x18001e51e  mov     qword ptr [rbx+20h], 0
0x18001e526  mov     rcx, [rbx+28h]; bstrString
0x18001e52a  call    cs:__imp_SysFreeString
0x18001e530  mov     qword ptr [rbx+28h], 0
0x18001e538  mov     rcx, [rbx+18h]; pv
0x18001e53c  test    rcx, rcx
0x18001e53f  jz      short loc_18001E54E
0x18001e541  call    ?WbemFreeAuthIdentity@@YAJPEAU_COAUTHIDENTITY@@@Z; WbemFreeAuthIdentity(_COAUTHIDENTITY *)
0x18001e546  mov     qword ptr [rbx+18h], 0
0x18001e54e  mov     ecx, 78h ; 'x'
0x18001e553  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001e559  mov     [rsp+48h+arg_8], rax
0x18001e55e  test    rax, rax
0x18001e561  jz      short loc_18001E57F
0x18001e563  mov     byte ptr [rsp+48h+var_28], 1; bool
0x18001e568  xor     r9d, r9d; struct CSWbemSecurity *
0x18001e56b  mov     r8, [rbx+40h]; struct IWbemClassObject *
0x18001e56f  mov     rdx, rdi; struct CSWbemServices *
0x18001e572  mov     rcx, rax; this
0x18001e575  call    ??0CSWbemObject@@QEAA@PEAVCSWbemServices@@PEAUIWbemClassObject@@PEAVCSWbemSecurity@@_N@Z; CSWbemObject::CSWbemObject(CSWbemServices *,IWbemClassObject *,CSWbemSecurity *,bool)
0x18001e57a  mov     rsi, rax
0x18001e57d  jmp     short loc_18001E581
0x18001e57f  xor     esi, esi
0x18001e581  mov     rcx, [rbx+40h]
0x18001e585  mov     rax, [rcx]
0x18001e588  mov     rax, [rax+10h]
0x18001e58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e591  mov     qword ptr [rbx+40h], 0
0x18001e599  test    rdi, rdi
0x18001e59c  jz      short loc_18001E5AE
0x18001e59e  mov     rax, [rdi]
0x18001e5a1  mov     rcx, rdi
0x18001e5a4  mov     rax, [rax+10h]
0x18001e5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ad  nop
0x18001e5ae  mov     rcx, rbx
0x18001e5b1  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001e5b7  nop
0x18001e5b8  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x18001e5bd  call    cs:__imp_LeaveCriticalSection
0x18001e5c3  mov     rax, rsi
0x18001e5c6  mov     rbx, [rsp+48h+arg_10]
0x18001e5cb  add     rsp, 30h
0x18001e5cf  pop     rdi
0x18001e5d0  pop     rsi
0x18001e5d1  pop     rbp
0x18001e5d2  retn
```
