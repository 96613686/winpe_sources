# CServiceModule::CompleteInitialization(void)

- ea: `0x1800134e4`
- end: `0x180013636`
- name: `?CompleteInitialization@CServiceModule@@QEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(CServiceModule *__hidden this)`
- caller_count: `15`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180011070`
- `0x180013080`
- `0x180013160`
- `0x180013230`
- `0x180013350`
- `0x18002cf60`
- `0x180035a7c`
- `0x180037620`
- `0x180037aa0`
- `0x180037f40`
- `0x18004f1f0`
- `0x18004f5b0`
- `0x18004fa60`
- `0x18004ff50`
- `0x180050a80`

## callees

- `0x1800134e4`
- `0x18001363c`
- `0x180014038`
- `0x18003b1cc`
- `0x18003c018`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800134f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800134f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013621`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800135dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800135dd`

## pseudocode

```c
__int64 __fastcall CServiceModule::CompleteInitialization(struct IUnknown *this)
{
  HRESULT Instance; // ebx
  struct IUnknown *ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  EnterCriticalSection(&CriticalSection);
  if ( DWORD1(xmmword_180075D18) == 4 )
  {
    Instance = 0;
    if ( !dword_180075D04 )
    {
      Instance = HrHttpInitialize();
      if ( !Instance )
        goto LABEL_12;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids,
          (unsigned int)Instance);
      if ( Instance >= 0 )
LABEL_12:
        dword_180075D04 = 1;
    }
    if ( !dword_180075D00 )
    {
      if ( dword_180075D04 )
      {
        dword_180075D00 = 1;
        if ( Instance < 0
          || (ppv = 0,
              Instance = CoCreateInstance(
                           &CLSID_UPnPRegistrar,
                           0,
                           1u,
                           &GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56,
                           (LPVOID *)&ppv),
              Instance < 0)
          || (Instance = ((__int64 (__fastcall *)(struct IUnknown *))ppv->lpVtbl[1].QueryInterface)(ppv),
              ReleaseObj(ppv),
              Instance < 0) )
        {
          dword_180075D00 = 0;
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids);
    Instance = -2147467259;
  }
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800134e4  mov     [rsp+arg_0], rcx
0x1800134e9  push    rbx
0x1800134ea  sub     rsp, 30h
0x1800134ee  lea     rcx, CriticalSection; lpCriticalSection
0x1800134f5  call    cs:__imp_EnterCriticalSection
0x1800134fc  nop     dword ptr [rax+rax+00h]
0x180013501  cmp     dword ptr cs:xmmword_180075D18+4, 4
0x180013508  jz      short loc_180013542
0x18001350a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013511  lea     rax, WPP_GLOBAL_Control
0x180013518  cmp     rcx, rax
0x18001351b  jz      short loc_180013538
0x18001351d  test    byte ptr [rcx+1Ch], 1
0x180013521  jz      short loc_180013538
0x180013523  mov     rcx, [rcx+10h]
0x180013527  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18001352e  mov     edx, 20h ; ' '
0x180013533  call    WPP_SF_
0x180013538  mov     ebx, 80004005h
0x18001353d  jmp     loc_18001361A
0x180013542  xor     ebx, ebx
0x180013544  cmp     cs:dword_180075D04, ebx
0x18001354a  jnz     short loc_180013596
0x18001354c  call    ?HrHttpInitialize@@YAJXZ; HrHttpInitialize(void)
0x180013551  mov     ebx, eax
0x180013553  test    eax, eax
0x180013555  jz      short loc_18001358C
0x180013557  mov     rcx, cs:WPP_GLOBAL_Control
0x18001355e  lea     rax, WPP_GLOBAL_Control
0x180013565  cmp     rcx, rax
0x180013568  jz      short loc_180013588
0x18001356a  test    byte ptr [rcx+1Ch], 1
0x18001356e  jz      short loc_180013588
0x180013570  mov     rcx, [rcx+10h]
0x180013574  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18001357b  mov     edx, 21h ; '!'
0x180013580  mov     r9d, ebx
0x180013583  call    WPP_SF_d
0x180013588  test    ebx, ebx
0x18001358a  js      short loc_180013596
0x18001358c  mov     cs:dword_180075D04, 1
0x180013596  mov     eax, cs:dword_180075D00
0x18001359c  test    eax, eax
0x18001359e  jnz     short loc_18001361A
0x1800135a0  cmp     cs:dword_180075D04, eax
0x1800135a6  jz      short loc_18001361A
0x1800135a8  mov     cs:dword_180075D00, 1
0x1800135b2  test    ebx, ebx
0x1800135b4  js      short loc_180013610
0x1800135b6  xor     edx, edx; pUnkOuter
0x1800135b8  mov     [rsp+38h+arg_0], 0
0x1800135c1  lea     rax, [rsp+38h+arg_0]
0x1800135c6  lea     r9, _GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56; riid
0x1800135cd  mov     [rsp+38h+ppv], rax; ppv
0x1800135d2  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x1800135d9  lea     r8d, [rdx+1]; dwClsContext
0x1800135dd  call    cs:__imp_CoCreateInstance
0x1800135e4  nop     dword ptr [rax+rax+00h]
0x1800135e9  mov     ebx, eax
0x1800135eb  test    eax, eax
0x1800135ed  js      short loc_180013610
0x1800135ef  mov     rcx, [rsp+38h+arg_0]
0x1800135f4  mov     rax, [rcx]
0x1800135f7  mov     rax, [rax+18h]
0x1800135fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013600  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x180013605  mov     ebx, eax
0x180013607  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001360c  test    ebx, ebx
0x18001360e  jns     short loc_18001361A
0x180013610  mov     cs:dword_180075D00, 0
0x18001361a  lea     rcx, CriticalSection; lpCriticalSection
0x180013621  call    cs:__imp_LeaveCriticalSection
0x180013628  nop     dword ptr [rax+rax+00h]
0x18001362d  mov     eax, ebx
0x18001362f  add     rsp, 30h
0x180013633  pop     rbx
0x180013634  retn
```
