# CWbemErrorCache::SetCurrentThreadError(CSWbemServices *)

- ea: `0x1800079e0`
- end: `0x180007bca`
- name: `?SetCurrentThreadError@CWbemErrorCache@@QEAAXPEAVCSWbemServices@@@Z`
- size: `490`
- prototype: `void(CWbemErrorCache *__hidden this, struct CSWbemServices *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006850`

## callees

- `0x18000311c`
- `0x180003170`
- `0x180006440`
- `0x180006550`
- `0x1800079e0`
- `0x18000b0ac`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007a3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180007a5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180007a97`
- `OLEAUT32!__imp_SysAllocString` at `0x180007a3f`
- `OLEAUT32!__imp_SysAllocString` at `0x180007a5d`
- `OLEAUT32!__imp_SysAllocString` at `0x180007a97`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180007a08`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180007a08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007aaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007aaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007b0e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180007b1f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180007b1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWbemErrorCache::SetCurrentThreadError(CWbemErrorCache *this, const OLECHAR **a2)
{
  CWbemErrorCache *v3; // rbx
  __int64 v4; // rax
  const OLECHAR *v5; // rcx
  __int64 v6; // rcx
  const OLECHAR *v7; // rcx
  CSWbemProxyCache *v8; // rcx
  struct _COAUTHIDENTITY *CoAuthIdentity; // rcx
  DWORD CurrentThreadId; // ebp
  __int64 v11; // rsi
  _QWORD *v12; // rax
  struct CSWbemSecurity *SecurityInfo; // rax
  struct CSWbemSecurity *v14; // rsi
  CWbemErrorCache *v15; // [rsp+50h] [rbp+8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp+18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+68h] [rbp+20h] BYREF

  v15 = this;
  v3 = g_pErrorCache;
  pperrinfo = 0;
  if ( GetErrorInfo(0, &pperrinfo) >= 0 && pperrinfo )
  {
    v15 = 0;
    if ( ((__int64 (__fastcall *)(IErrorInfo *, GUID *, CWbemErrorCache **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &IID_IWbemClassObject,
           &v15) >= 0
      && v15 )
    {
      CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v3 + 8));
      CWbemErrorCache::ResetCurrentThreadError(v3);
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)v3 + 6);
      v12 = CWin32DefaultArena::WbemMemAlloc(0x48u);
      *((_QWORD *)v3 + 6) = v12;
      if ( v12 )
      {
        v12[1] = 0;
        **((_QWORD **)v3 + 6) = v11;
        if ( v11 )
          *(_QWORD *)(v11 + 8) = *((_QWORD *)v3 + 6);
        *(_DWORD *)(*((_QWORD *)v3 + 6) + 16LL) = CurrentThreadId;
        *(_QWORD *)(*((_QWORD *)v3 + 6) + 64LL) = v15;
        *(_QWORD *)(*((_QWORD *)v3 + 6) + 56LL) = 0;
        *(_QWORD *)(*((_QWORD *)v3 + 6) + 32LL) = 0;
        *(_QWORD *)(*((_QWORD *)v3 + 6) + 40LL) = 0;
        *(_QWORD *)(*((_QWORD *)v3 + 6) + 24LL) = 0;
        *(_QWORD *)(*((_QWORD *)v3 + 6) + 48LL) = 0;
        if ( a2 )
        {
          *(_QWORD *)(*((_QWORD *)v3 + 6) + 56LL) = CSWbemServices::GetIWbemServices((CSWbemServices *)a2);
          SecurityInfo = CSWbemServices::GetSecurityInfo((CSWbemServices *)a2);
          v14 = SecurityInfo;
          if ( SecurityInfo )
          {
            v4 = *((_QWORD *)SecurityInfo + 15);
            if ( v4 )
              v5 = *(const OLECHAR **)(v4 + 296);
            else
              v5 = 0;
            *(_QWORD *)(*((_QWORD *)v3 + 6) + 32LL) = SysAllocString(v5);
            v6 = *((_QWORD *)v14 + 15);
            if ( v6 )
              v7 = *(const OLECHAR **)(v6 + 288);
            else
              v7 = 0;
            *(_QWORD *)(*((_QWORD *)v3 + 6) + 40LL) = SysAllocString(v7);
            v8 = (CSWbemProxyCache *)*((_QWORD *)v14 + 15);
            if ( v8 )
              CoAuthIdentity = CSWbemProxyCache::GetCoAuthIdentity(v8);
            else
              CoAuthIdentity = 0;
            *(_QWORD *)(*((_QWORD *)v3 + 6) + 24LL) = CoAuthIdentity;
            (*(void (__fastcall **)(struct CSWbemSecurity *))(*(_QWORD *)v14 + 16LL))(v14);
          }
          *(_QWORD *)(*((_QWORD *)v3 + 6) + 48LL) = SysAllocString(a2[5]);
        }
      }
      else
      {
        *((_QWORD *)v3 + 6) = v11;
      }
      LeaveCriticalSection(lpCriticalSection);
    }
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x1800079e0  mov     [rsp+arg_0], rcx
0x1800079e5  push    rbx
0x1800079e6  push    rbp
0x1800079e7  push    rsi
0x1800079e8  push    rdi
0x1800079e9  push    r14
0x1800079eb  sub     rsp, 20h
0x1800079ef  mov     rdi, rdx
0x1800079f2  mov     rbx, cs:?g_pErrorCache@@3PEAVCWbemErrorCache@@EA; CWbemErrorCache * g_pErrorCache
0x1800079f9  xor     r14d, r14d
0x1800079fc  mov     [rsp+48h+pperrinfo], r14
0x180007a01  lea     rdx, [rsp+48h+pperrinfo]; pperrinfo
0x180007a06  xor     ecx, ecx; dwReserved
0x180007a08  call    cs:__imp_GetErrorInfo
0x180007a0e  test    eax, eax
0x180007a10  js      short loc_180007A20
0x180007a12  mov     rcx, [rsp+48h+pperrinfo]
0x180007a17  test    rcx, rcx
0x180007a1a  jnz     loc_180007AD0
0x180007a20  add     rsp, 20h
0x180007a24  pop     r14
0x180007a26  pop     rdi
0x180007a27  pop     rsi
0x180007a28  pop     rbp
0x180007a29  pop     rbx
0x180007a2a  retn
0x180007a2b  mov     rax, [rax+78h]
0x180007a2f  test    rax, rax
0x180007a32  jz      loc_180007BB8
0x180007a38  mov     rcx, [rax+128h]; psz
0x180007a3f  call    cs:__imp_SysAllocString
0x180007a45  mov     rcx, [rbx+30h]
0x180007a49  mov     [rcx+20h], rax
0x180007a4d  mov     rcx, [rsi+78h]
0x180007a51  test    rcx, rcx
0x180007a54  jz      short loc_180007AC6
0x180007a56  mov     rcx, [rcx+120h]; psz
0x180007a5d  call    cs:__imp_SysAllocString
0x180007a63  mov     rcx, [rbx+30h]
0x180007a67  mov     [rcx+28h], rax
0x180007a6b  mov     rcx, [rsi+78h]; this
0x180007a6f  test    rcx, rcx
0x180007a72  jz      short loc_180007ACB
0x180007a74  call    ?GetCoAuthIdentity@CSWbemProxyCache@@QEAAPEAU_COAUTHIDENTITY@@XZ; CSWbemProxyCache::GetCoAuthIdentity(void)
0x180007a79  mov     rcx, rax
0x180007a7c  mov     rax, [rbx+30h]
0x180007a80  mov     [rax+18h], rcx
0x180007a84  mov     rax, [rsi]
0x180007a87  mov     rcx, rsi
0x180007a8a  mov     rax, [rax+10h]
0x180007a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a93  mov     rcx, [rdi+28h]; psz
0x180007a97  call    cs:__imp_SysAllocString
0x180007a9d  mov     rcx, [rbx+30h]
0x180007aa1  mov     [rcx+30h], rax
0x180007aa5  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x180007aaa  call    cs:__imp_LeaveCriticalSection
0x180007ab0  mov     rcx, [rsp+48h+pperrinfo]
0x180007ab5  mov     rax, [rcx]
0x180007ab8  mov     rax, [rax+10h]
0x180007abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac1  jmp     loc_180007A20
0x180007ac6  mov     rcx, r14
0x180007ac9  jmp     short loc_180007A5D
0x180007acb  mov     rcx, r14
0x180007ace  jmp     short loc_180007A7C
0x180007ad0  mov     [rsp+48h+arg_0], r14
0x180007ad5  mov     rax, [rcx]
0x180007ad8  lea     r8, [rsp+48h+arg_0]
0x180007add  lea     rdx, IID_IWbemClassObject
0x180007ae4  mov     rax, [rax]
0x180007ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aec  test    eax, eax
0x180007aee  js      short loc_180007AB0
0x180007af0  cmp     [rsp+48h+arg_0], r14
0x180007af5  jz      short loc_180007AB0
0x180007af7  lea     rdx, [rbx+8]; struct _RTL_CRITICAL_SECTION *
0x180007afb  lea     rcx, [rsp+48h+lpCriticalSection]; this
0x180007b00  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180007b05  nop
0x180007b06  mov     rcx, rbx; this
0x180007b09  call    ?ResetCurrentThreadError@CWbemErrorCache@@QEAAXXZ; CWbemErrorCache::ResetCurrentThreadError(void)
0x180007b0e  call    cs:__imp_GetCurrentThreadId
0x180007b14  mov     ebp, eax
0x180007b16  mov     rsi, [rbx+30h]
0x180007b1a  mov     ecx, 48h ; 'H'
0x180007b1f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180007b25  mov     [rbx+30h], rax
0x180007b29  test    rax, rax
0x180007b2c  jz      loc_180007BC0
0x180007b32  mov     [rax+8], r14
0x180007b36  mov     rcx, [rbx+30h]
0x180007b3a  mov     [rcx], rsi
0x180007b3d  test    rsi, rsi
0x180007b40  jz      short loc_180007B4A
0x180007b42  mov     rax, [rbx+30h]
0x180007b46  mov     [rsi+8], rax
0x180007b4a  mov     rax, [rbx+30h]
0x180007b4e  mov     [rax+10h], ebp
0x180007b51  mov     rcx, [rbx+30h]
0x180007b55  mov     rax, [rsp+48h+arg_0]
0x180007b5a  mov     [rcx+40h], rax
0x180007b5e  mov     rax, [rbx+30h]
0x180007b62  mov     [rax+38h], r14
0x180007b66  mov     rax, [rbx+30h]
0x180007b6a  mov     [rax+20h], r14
0x180007b6e  mov     rax, [rbx+30h]
0x180007b72  mov     [rax+28h], r14
0x180007b76  mov     rax, [rbx+30h]
0x180007b7a  mov     [rax+18h], r14
0x180007b7e  mov     rax, [rbx+30h]
0x180007b82  mov     [rax+30h], r14
0x180007b86  test    rdi, rdi
0x180007b89  jz      loc_180007AA5
0x180007b8f  mov     rcx, rdi; this
0x180007b92  call    ?GetIWbemServices@CSWbemServices@@QEAAPEAUIWbemServices@@XZ; CSWbemServices::GetIWbemServices(void)
0x180007b97  mov     rcx, [rbx+30h]
0x180007b9b  mov     [rcx+38h], rax
0x180007b9f  mov     rcx, rdi; this
0x180007ba2  call    ?GetSecurityInfo@CSWbemServices@@QEAAPEAVCSWbemSecurity@@XZ; CSWbemServices::GetSecurityInfo(void)
0x180007ba7  mov     rsi, rax
0x180007baa  test    rax, rax
0x180007bad  jz      loc_180007A93
0x180007bb3  jmp     loc_180007A2B
0x180007bb8  mov     rcx, r14
0x180007bbb  jmp     loc_180007A3F
0x180007bc0  mov     [rbx+30h], rsi
0x180007bc4  jmp     loc_180007AA5
```
