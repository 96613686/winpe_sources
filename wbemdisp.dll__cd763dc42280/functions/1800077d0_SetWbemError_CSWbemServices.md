# SetWbemError(CSWbemServices *)

- ea: `0x1800077d0`
- end: `0x1800079d5`
- name: `?SetWbemError@@YAXPEAVCSWbemServices@@@Z`
- size: `517`
- prototype: `void __fastcall(struct CSWbemServices *this)`
- caller_count: `37`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001e14`
- `0x180001f70`
- `0x180002610`
- `0x1800028b0`
- `0x1800031b0`
- `0x180006850`
- `0x180008230`
- `0x180008800`
- `0x18000bef0`
- `0x18001d250`
- `0x18001d490`
- `0x18001d630`
- `0x18001d830`
- `0x18001dc50`
- `0x18001e010`
- `0x18001e260`
- `0x18001f270`
- `0x1800296a0`
- `0x1800298b0`
- `0x180029a70`
- `0x180029c10`
- `0x180029d90`
- `0x180029f10`
- `0x18002a090`
- `0x18002a200`
- `0x18002a4e0`
- `0x18002a6d0`
- `0x18002abf0`
- `0x18002b880`
- `0x18002bd60`
- `0x18002cb20`
- `0x18002cc20`
- `0x18002cd80`
- `0x18002cdd0`
- `0x180031510`
- `0x1800322d0`
- `0x1800323e0`

## callees

- `0x18000311c`
- `0x180003170`
- `0x180006440`
- `0x180006550`
- `0x1800077d0`
- `0x18000b0ac`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000784a`
- `OLEAUT32!__imp_SysAllocString` at `0x180007868`
- `OLEAUT32!__imp_SysAllocString` at `0x1800078a2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000784a`
- `OLEAUT32!__imp_SysAllocString` at `0x180007868`
- `OLEAUT32!__imp_SysAllocString` at `0x1800078a2`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180007806`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180007806`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000782f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800077e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800077e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007919`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007919`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000792a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000792a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SetWbemError(const OLECHAR **this)
{
  CWbemErrorCache *v2; // rbx
  __int64 v3; // rax
  const OLECHAR *v4; // rcx
  __int64 v5; // rcx
  const OLECHAR *v6; // rcx
  CSWbemProxyCache *v7; // rcx
  struct _COAUTHIDENTITY *CoAuthIdentity; // rcx
  DWORD CurrentThreadId; // ebp
  __int64 v10; // rsi
  _QWORD *v11; // rax
  struct CSWbemSecurity *SecurityInfo; // rax
  struct CSWbemSecurity *v13; // rsi
  __int64 v14; // [rsp+58h] [rbp+10h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp+18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp+20h] BYREF

  EnterCriticalSection(&g_csErrorCache);
  v2 = g_pErrorCache;
  if ( g_pErrorCache )
  {
    pperrinfo = 0;
    if ( GetErrorInfo(0, &pperrinfo) >= 0 )
    {
      if ( pperrinfo )
      {
        v14 = 0;
        if ( ((__int64 (__fastcall *)(IErrorInfo *, GUID *, __int64 *))pperrinfo->lpVtbl->QueryInterface)(
               pperrinfo,
               &IID_IWbemClassObject,
               &v14) >= 0
          && v14 )
        {
          CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v2 + 8));
          CWbemErrorCache::ResetCurrentThreadError(v2);
          CurrentThreadId = GetCurrentThreadId();
          v10 = *((_QWORD *)v2 + 6);
          v11 = CWin32DefaultArena::WbemMemAlloc(0x48u);
          *((_QWORD *)v2 + 6) = v11;
          if ( v11 )
          {
            v11[1] = 0;
            **((_QWORD **)v2 + 6) = v10;
            if ( v10 )
              *(_QWORD *)(v10 + 8) = *((_QWORD *)v2 + 6);
            *(_DWORD *)(*((_QWORD *)v2 + 6) + 16LL) = CurrentThreadId;
            *(_QWORD *)(*((_QWORD *)v2 + 6) + 64LL) = v14;
            *(_QWORD *)(*((_QWORD *)v2 + 6) + 56LL) = 0;
            *(_QWORD *)(*((_QWORD *)v2 + 6) + 32LL) = 0;
            *(_QWORD *)(*((_QWORD *)v2 + 6) + 40LL) = 0;
            *(_QWORD *)(*((_QWORD *)v2 + 6) + 24LL) = 0;
            *(_QWORD *)(*((_QWORD *)v2 + 6) + 48LL) = 0;
            if ( this )
            {
              *(_QWORD *)(*((_QWORD *)v2 + 6) + 56LL) = CSWbemServices::GetIWbemServices((CSWbemServices *)this);
              SecurityInfo = CSWbemServices::GetSecurityInfo((CSWbemServices *)this);
              v13 = SecurityInfo;
              if ( SecurityInfo )
              {
                v3 = *((_QWORD *)SecurityInfo + 15);
                if ( v3 )
                  v4 = *(const OLECHAR **)(v3 + 296);
                else
                  v4 = 0;
                *(_QWORD *)(*((_QWORD *)v2 + 6) + 32LL) = SysAllocString(v4);
                v5 = *((_QWORD *)v13 + 15);
                if ( v5 )
                  v6 = *(const OLECHAR **)(v5 + 288);
                else
                  v6 = 0;
                *(_QWORD *)(*((_QWORD *)v2 + 6) + 40LL) = SysAllocString(v6);
                v7 = (CSWbemProxyCache *)*((_QWORD *)v13 + 15);
                if ( v7 )
                  CoAuthIdentity = CSWbemProxyCache::GetCoAuthIdentity(v7);
                else
                  CoAuthIdentity = 0;
                *(_QWORD *)(*((_QWORD *)v2 + 6) + 24LL) = CoAuthIdentity;
                (*(void (__fastcall **)(struct CSWbemSecurity *))(*(_QWORD *)v13 + 16LL))(v13);
              }
              *(_QWORD *)(*((_QWORD *)v2 + 6) + 48LL) = SysAllocString(this[5]);
            }
          }
          else
          {
            *((_QWORD *)v2 + 6) = v10;
          }
          LeaveCriticalSection(lpCriticalSection);
        }
        ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
      }
    }
  }
  LeaveCriticalSection(&g_csErrorCache);
}

```

## disassembly

```asm
0x1800077d0  push    rbx
0x1800077d2  push    rbp
0x1800077d3  push    rsi
0x1800077d4  push    rdi
0x1800077d5  push    r14
0x1800077d7  sub     rsp, 20h
0x1800077db  mov     rdi, rcx
0x1800077de  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800077e5  call    cs:__imp_EnterCriticalSection
0x1800077eb  mov     rbx, cs:?g_pErrorCache@@3PEAVCWbemErrorCache@@EA; CWbemErrorCache * g_pErrorCache
0x1800077f2  test    rbx, rbx
0x1800077f5  jz      short loc_18000781E
0x1800077f7  xor     r14d, r14d
0x1800077fa  mov     [rsp+48h+pperrinfo], r14
0x1800077ff  lea     rdx, [rsp+48h+pperrinfo]; pperrinfo
0x180007804  xor     ecx, ecx; dwReserved
0x180007806  call    cs:__imp_GetErrorInfo
0x18000780c  test    eax, eax
0x18000780e  js      short loc_18000781E
0x180007810  mov     rcx, [rsp+48h+pperrinfo]
0x180007815  test    rcx, rcx
0x180007818  jnz     loc_1800078DB
0x18000781e  lea     rcx, ?g_csErrorCache@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csErrorCache
0x180007825  add     rsp, 20h
0x180007829  pop     r14
0x18000782b  pop     rdi
0x18000782c  pop     rsi
0x18000782d  pop     rbp
0x18000782e  pop     rbx
0x18000782f  jmp     cs:__imp_LeaveCriticalSection
0x180007836  mov     rax, [rax+78h]
0x18000783a  test    rax, rax
0x18000783d  jz      loc_1800079C3
0x180007843  mov     rcx, [rax+128h]; psz
0x18000784a  call    cs:__imp_SysAllocString
0x180007850  mov     rcx, [rbx+30h]
0x180007854  mov     [rcx+20h], rax
0x180007858  mov     rcx, [rsi+78h]
0x18000785c  test    rcx, rcx
0x18000785f  jz      short loc_1800078D1
0x180007861  mov     rcx, [rcx+120h]; psz
0x180007868  call    cs:__imp_SysAllocString
0x18000786e  mov     rcx, [rbx+30h]
0x180007872  mov     [rcx+28h], rax
0x180007876  mov     rcx, [rsi+78h]; this
0x18000787a  test    rcx, rcx
0x18000787d  jz      short loc_1800078D6
0x18000787f  call    ?GetCoAuthIdentity@CSWbemProxyCache@@QEAAPEAU_COAUTHIDENTITY@@XZ; CSWbemProxyCache::GetCoAuthIdentity(void)
0x180007884  mov     rcx, rax
0x180007887  mov     rax, [rbx+30h]
0x18000788b  mov     [rax+18h], rcx
0x18000788f  mov     rax, [rsi]
0x180007892  mov     rcx, rsi
0x180007895  mov     rax, [rax+10h]
0x180007899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000789e  mov     rcx, [rdi+28h]; psz
0x1800078a2  call    cs:__imp_SysAllocString
0x1800078a8  mov     rcx, [rbx+30h]
0x1800078ac  mov     [rcx+30h], rax
0x1800078b0  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x1800078b5  call    cs:__imp_LeaveCriticalSection
0x1800078bb  mov     rcx, [rsp+48h+pperrinfo]
0x1800078c0  mov     rax, [rcx]
0x1800078c3  mov     rax, [rax+10h]
0x1800078c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078cc  jmp     loc_18000781E
0x1800078d1  mov     rcx, r14
0x1800078d4  jmp     short loc_180007868
0x1800078d6  mov     rcx, r14
0x1800078d9  jmp     short loc_180007887
0x1800078db  mov     [rsp+48h+arg_8], r14
0x1800078e0  mov     rax, [rcx]
0x1800078e3  lea     r8, [rsp+48h+arg_8]
0x1800078e8  lea     rdx, IID_IWbemClassObject
0x1800078ef  mov     rax, [rax]
0x1800078f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078f7  test    eax, eax
0x1800078f9  js      short loc_1800078BB
0x1800078fb  cmp     [rsp+48h+arg_8], r14
0x180007900  jz      short loc_1800078BB
0x180007902  lea     rdx, [rbx+8]; struct _RTL_CRITICAL_SECTION *
0x180007906  lea     rcx, [rsp+48h+lpCriticalSection]; this
0x18000790b  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180007910  nop
0x180007911  mov     rcx, rbx; this
0x180007914  call    ?ResetCurrentThreadError@CWbemErrorCache@@QEAAXXZ; CWbemErrorCache::ResetCurrentThreadError(void)
0x180007919  call    cs:__imp_GetCurrentThreadId
0x18000791f  mov     ebp, eax
0x180007921  mov     rsi, [rbx+30h]
0x180007925  mov     ecx, 48h ; 'H'
0x18000792a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180007930  mov     [rbx+30h], rax
0x180007934  test    rax, rax
0x180007937  jz      loc_1800079CB
0x18000793d  mov     [rax+8], r14
0x180007941  mov     rcx, [rbx+30h]
0x180007945  mov     [rcx], rsi
0x180007948  test    rsi, rsi
0x18000794b  jz      short loc_180007955
0x18000794d  mov     rax, [rbx+30h]
0x180007951  mov     [rsi+8], rax
0x180007955  mov     rax, [rbx+30h]
0x180007959  mov     [rax+10h], ebp
0x18000795c  mov     rcx, [rbx+30h]
0x180007960  mov     rax, [rsp+48h+arg_8]
0x180007965  mov     [rcx+40h], rax
0x180007969  mov     rax, [rbx+30h]
0x18000796d  mov     [rax+38h], r14
0x180007971  mov     rax, [rbx+30h]
0x180007975  mov     [rax+20h], r14
0x180007979  mov     rax, [rbx+30h]
0x18000797d  mov     [rax+28h], r14
0x180007981  mov     rax, [rbx+30h]
0x180007985  mov     [rax+18h], r14
0x180007989  mov     rax, [rbx+30h]
0x18000798d  mov     [rax+30h], r14
0x180007991  test    rdi, rdi
0x180007994  jz      loc_1800078B0
0x18000799a  mov     rcx, rdi; this
0x18000799d  call    ?GetIWbemServices@CSWbemServices@@QEAAPEAUIWbemServices@@XZ; CSWbemServices::GetIWbemServices(void)
0x1800079a2  mov     rcx, [rbx+30h]
0x1800079a6  mov     [rcx+38h], rax
0x1800079aa  mov     rcx, rdi; this
0x1800079ad  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x1800079b2  mov     rsi, rax
0x1800079b5  test    rax, rax
0x1800079b8  jz      loc_18000789E
0x1800079be  jmp     loc_180007836
0x1800079c3  mov     rcx, r14
0x1800079c6  jmp     loc_18000784A
0x1800079cb  mov     [rbx+30h], rsi
0x1800079cf  jmp     loc_1800078B0
```
