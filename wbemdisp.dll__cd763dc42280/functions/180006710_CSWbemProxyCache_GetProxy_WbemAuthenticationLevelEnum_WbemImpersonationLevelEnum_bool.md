# CSWbemProxyCache::GetProxy(WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum,bool)

- ea: `0x180006710`
- end: `0x18000683e`
- name: `?GetProxy@CSWbemProxyCache@@QEAAPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@_N@Z`
- size: `302`
- prototype: `struct IUnknown *__fastcall(CSWbemProxyCache *__hidden this, enum WbemAuthenticationLevelEnum, enum WbemImpersonationLevelEnum, bool)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800036e0`
- `0x180004e10`
- `0x180006850`
- `0x180008230`
- `0x180008800`
- `0x18000a270`
- `0x18001e5dc`
- `0x18001e8bc`
- `0x18001ef60`

## callees

- `0x180006550`
- `0x180006710`
- `0x180008de0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006771`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006771`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct IUnknown *__fastcall CSWbemProxyCache::GetProxy(
        CSWbemProxyCache *this,
        enum WbemAuthenticationLevelEnum a2,
        enum WbemImpersonationLevelEnum a3,
        char a4)
{
  __int64 v5; // rsi
  __int64 v6; // rbp
  char *v8; // r14
  struct IUnknown *v9; // rbx
  unsigned int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // r15
  struct IUnknown *v12; // rcx
  __int64 v13; // [rsp+20h] [rbp-48h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[8]; // [rsp+28h] [rbp-40h] BYREF
  struct IUnknown *v15; // [rsp+70h] [rbp+8h] BYREF

  v5 = a3;
  v6 = a2;
  CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 16));
  v8 = (char *)this + 32 * v6 + 8 * v5;
  v9 = (struct IUnknown *)*((_QWORD *)v8 + 6);
  v15 = v9;
  if ( v9 )
  {
    ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->AddRef)(v9);
    if ( a4 )
      CSWbemProxyCache::SecureProxy(this, v15, v6, v5);
  }
  else
  {
    v11 = (unsigned int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this
                                                                    + 4 * *((int *)this + 81)
                                                                    + *((int *)this + 82)
                                                                    + 6);
    if ( !v11 )
      goto LABEL_5;
    v13 = 0;
    if ( !(**v11)(v11, &IID_IClientSecurity, &v13) )
    {
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, struct IUnknown **))(*(_QWORD *)v13 + 40LL))(
              v13,
              v11,
              &v15) )
      {
        CSWbemProxyCache::SecureProxy(this, v15, v6, v5);
        v12 = v15;
        *((_QWORD *)v8 + 6) = v15;
        ((void (__fastcall *)(struct IUnknown *))v12->lpVtbl->AddRef)(v12);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  v9 = v15;
LABEL_5:
  LeaveCriticalSection(lpCriticalSection[0]);
  return v9;
}

```

## disassembly

```asm
0x180006710  push    rbx
0x180006712  push    rbp
0x180006713  push    rsi
0x180006714  push    rdi
0x180006715  push    r14
0x180006717  push    r15
0x180006719  sub     rsp, 38h
0x18000671d  movzx   r15d, r9b
0x180006721  movsxd  rsi, r8d
0x180006724  movsxd  rbp, edx
0x180006727  mov     rdi, rcx
0x18000672a  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x18000672e  lea     rcx, [rsp+68h+lpCriticalSection]; this
0x180006733  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180006738  nop
0x180006739  lea     r10, [rsi+rbp*4]
0x18000673d  lea     r14, [rdi+r10*8]
0x180006741  mov     rbx, [r14+30h]
0x180006745  mov     [rsp+68h+arg_0], rbx
0x18000674a  test    rbx, rbx
0x18000674d  jz      short loc_180006787
0x18000674f  mov     rax, [rbx]
0x180006752  mov     rcx, rbx
0x180006755  mov     rax, [rax+8]
0x180006759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000675e  test    r15b, r15b
0x180006761  jnz     loc_180006825
0x180006767  mov     rbx, [rsp+68h+arg_0]
0x18000676c  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x180006771  call    cs:__imp_LeaveCriticalSection
0x180006777  mov     rax, rbx
0x18000677a  add     rsp, 38h
0x18000677e  pop     r15
0x180006780  pop     r14
0x180006782  pop     rdi
0x180006783  pop     rsi
0x180006784  pop     rbp
0x180006785  pop     rbx
0x180006786  retn
0x180006787  movsxd  rcx, dword ptr [rdi+144h]
0x18000678e  movsxd  rax, dword ptr [rdi+148h]
0x180006795  lea     rcx, [rax+rcx*4]
0x180006799  mov     r15, [rdi+rcx*8+30h]
0x18000679e  test    r15, r15
0x1800067a1  jz      short loc_18000676C
0x1800067a3  mov     [rsp+68h+var_48], 0
0x1800067ac  mov     rax, [r15]
0x1800067af  lea     r8, [rsp+68h+var_48]
0x1800067b4  lea     rdx, IID_IClientSecurity
0x1800067bb  mov     rcx, r15
0x1800067be  mov     rax, [rax]
0x1800067c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067c6  test    eax, eax
0x1800067c8  jnz     short loc_180006767
0x1800067ca  mov     rcx, [rsp+68h+var_48]
0x1800067cf  mov     rax, [rcx]
0x1800067d2  lea     r8, [rsp+68h+arg_0]
0x1800067d7  mov     rdx, r15
0x1800067da  mov     rax, [rax+28h]
0x1800067de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067e3  test    eax, eax
0x1800067e5  jnz     short loc_18000680F
0x1800067e7  mov     r9d, esi; enum WbemImpersonationLevelEnum
0x1800067ea  mov     r8d, ebp; enum WbemAuthenticationLevelEnum
0x1800067ed  mov     rdx, [rsp+68h+arg_0]; struct IUnknown *
0x1800067f2  mov     rcx, rdi; this
0x1800067f5  call    ?SecureProxy@CSWbemProxyCache@@QEAAXPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@@Z; CSWbemProxyCache::SecureProxy(IUnknown *,WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum)
0x1800067fa  mov     rcx, [rsp+68h+arg_0]
0x1800067ff  mov     [r14+30h], rcx
0x180006803  mov     rax, [rcx]
0x180006806  mov     rax, [rax+8]
0x18000680a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000680f  mov     rcx, [rsp+68h+var_48]
0x180006814  mov     rax, [rcx]
0x180006817  mov     rax, [rax+10h]
0x18000681b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006820  jmp     loc_180006767
0x180006825  mov     r9d, esi; enum WbemImpersonationLevelEnum
0x180006828  mov     r8d, ebp; enum WbemAuthenticationLevelEnum
0x18000682b  mov     rdx, [rsp+68h+arg_0]; struct IUnknown *
0x180006830  mov     rcx, rdi; this
0x180006833  call    ?SecureProxy@CSWbemProxyCache@@QEAAXPEAUIUnknown@@W4WbemAuthenticationLevelEnum@@W4WbemImpersonationLevelEnum@@@Z; CSWbemProxyCache::SecureProxy(IUnknown *,WbemAuthenticationLevelEnum,WbemImpersonationLevelEnum)
0x180006838  jmp     loc_180006767
```
