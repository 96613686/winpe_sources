# CServiceModule::CompleteInitialization(void)

- ea: `0x18001e478`
- end: `0x18001e5b7`
- name: `?CompleteInitialization@CServiceModule@@QEAAJXZ`
- size: `319`
- prototype: `__int64 __fastcall(struct IUnknown *this)`
- caller_count: `15`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001c1e0`
- `0x18001e070`
- `0x18001e130`
- `0x18001e1f0`
- `0x18001e300`
- `0x18002b790`
- `0x180033b14`
- `0x180035320`
- `0x180035770`
- `0x180035be0`
- `0x18004bec0`
- `0x18004c230`
- `0x18004c6b0`
- `0x18004cb90`
- `0x18004d640`

## callees

- `0x18001e478`
- `0x18001e5c0`
- `0x18001ef30`
- `0x180038ce4`
- `0x180039a84`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e489`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e489`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e5a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e5a9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e56b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e56b`

## pseudocode

```c
__int64 __fastcall CServiceModule::CompleteInitialization(struct IUnknown *this)
{
  HRESULT Instance; // ebx
  struct IUnknown *ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = this;
  EnterCriticalSection(&CriticalSection);
  if ( DWORD1(xmmword_180071C28) == 4 )
  {
    Instance = 0;
    if ( !dword_180071C14 )
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
        dword_180071C14 = 1;
    }
    if ( !dword_180071C10 )
    {
      if ( dword_180071C14 )
      {
        dword_180071C10 = 1;
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
          dword_180071C10 = 0;
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
0x18001e478  mov     [rsp+arg_0], rcx
0x18001e47d  push    rbx
0x18001e47e  sub     rsp, 30h
0x18001e482  lea     rcx, CriticalSection; lpCriticalSection
0x18001e489  call    cs:__imp_EnterCriticalSection
0x18001e48f  cmp     dword ptr cs:xmmword_180071C28+4, 4
0x18001e496  jz      short loc_18001E4D0
0x18001e498  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e49f  lea     rax, WPP_GLOBAL_Control
0x18001e4a6  cmp     rcx, rax
0x18001e4a9  jz      short loc_18001E4C6
0x18001e4ab  test    byte ptr [rcx+1Ch], 1
0x18001e4af  jz      short loc_18001E4C6
0x18001e4b1  mov     rcx, [rcx+10h]
0x18001e4b5  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18001e4bc  mov     edx, 20h ; ' '
0x18001e4c1  call    WPP_SF_
0x18001e4c6  mov     ebx, 80004005h
0x18001e4cb  jmp     loc_18001E5A2
0x18001e4d0  xor     ebx, ebx
0x18001e4d2  cmp     cs:dword_180071C14, ebx
0x18001e4d8  jnz     short loc_18001E524
0x18001e4da  call    ?HrHttpInitialize@@YAJXZ; HrHttpInitialize(void)
0x18001e4df  mov     ebx, eax
0x18001e4e1  test    eax, eax
0x18001e4e3  jz      short loc_18001E51A
0x18001e4e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4ec  lea     rax, WPP_GLOBAL_Control
0x18001e4f3  cmp     rcx, rax
0x18001e4f6  jz      short loc_18001E516
0x18001e4f8  test    byte ptr [rcx+1Ch], 1
0x18001e4fc  jz      short loc_18001E516
0x18001e4fe  mov     rcx, [rcx+10h]
0x18001e502  lea     r8, WPP_2670124a663039e2f0c82c5e619b77a4_Traceguids
0x18001e509  mov     edx, 21h ; '!'
0x18001e50e  mov     r9d, ebx
0x18001e511  call    WPP_SF_d
0x18001e516  test    ebx, ebx
0x18001e518  js      short loc_18001E524
0x18001e51a  mov     cs:dword_180071C14, 1
0x18001e524  mov     eax, cs:dword_180071C10
0x18001e52a  test    eax, eax
0x18001e52c  jnz     short loc_18001E5A2
0x18001e52e  cmp     cs:dword_180071C14, eax
0x18001e534  jz      short loc_18001E5A2
0x18001e536  mov     cs:dword_180071C10, 1
0x18001e540  test    ebx, ebx
0x18001e542  js      short loc_18001E598
0x18001e544  xor     edx, edx; pUnkOuter
0x18001e546  mov     [rsp+38h+arg_0], 0
0x18001e54f  lea     rax, [rsp+38h+arg_0]
0x18001e554  lea     r9, _GUID_6d8ff8db_730d_11d4_bf42_00b0d0118b56; riid
0x18001e55b  mov     [rsp+38h+ppv], rax; ppv
0x18001e560  lea     rcx, CLSID_UPnPRegistrar; rclsid
0x18001e567  lea     r8d, [rdx+1]; dwClsContext
0x18001e56b  call    cs:__imp_CoCreateInstance
0x18001e571  mov     ebx, eax
0x18001e573  test    eax, eax
0x18001e575  js      short loc_18001E598
0x18001e577  mov     rcx, [rsp+38h+arg_0]
0x18001e57c  mov     rax, [rcx]
0x18001e57f  mov     rax, [rax+18h]
0x18001e583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e588  mov     rcx, [rsp+38h+arg_0]; struct IUnknown *
0x18001e58d  mov     ebx, eax
0x18001e58f  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18001e594  test    ebx, ebx
0x18001e596  jns     short loc_18001E5A2
0x18001e598  mov     cs:dword_180071C10, 0
0x18001e5a2  lea     rcx, CriticalSection; lpCriticalSection
0x18001e5a9  call    cs:__imp_LeaveCriticalSection
0x18001e5af  mov     eax, ebx
0x18001e5b1  add     rsp, 30h
0x18001e5b5  pop     rbx
0x18001e5b6  retn
```
