# CShareMediaCore::Initialize(void)

- ea: `0x18000a85c`
- end: `0x18000a957`
- name: `?Initialize@CShareMediaCore@@QEAAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(CShareMediaCore *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013248`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000a85c`
- `0x18001e010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000a912`
- `KERNEL32!InitializeCriticalSection` at `0x18000a91c`
- `KERNEL32!InitializeCriticalSection` at `0x18000a912`
- `KERNEL32!InitializeCriticalSection` at `0x18000a91c`
- `ole32!CoCreateInstance` at `0x18000a8b3`
- `ole32!CoCreateInstance` at `0x18000a902`
- `ole32!CoCreateInstance` at `0x18000a8b3`
- `ole32!CoCreateInstance` at `0x18000a902`

## pseudocode

```c
__int64 __fastcall CShareMediaCore::Initialize(CShareMediaCore *this)
{
  HRESULT Instance; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  Instance = CoCreateInstance(
               &CLSID_StdGlobalInterfaceTable,
               0,
               1u,
               &GUID_00000146_0000_0000_c000_000000000046,
               (LPVOID *)this + 5);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(_QWORD, CShareMediaCore *, GUID *, char *))(**((_QWORD **)this + 5) + 24LL))(
                 *((_QWORD *)this + 5),
                 this,
                 &GUID_595d6e65_732c_4736_853f_db64f5aa1eec,
                 (char *)this + 48);
    if ( Instance >= 0 )
    {
      Instance = CoCreateInstance(
                   &GUID_ad581b00_7b64_4e59_a38d_d2c5bf51ddb3,
                   0,
                   1u,
                   &GUID_01f5f85e_0a81_40da_a7c8_21ef3af8440c,
                   (LPVOID *)this + 27);
      if ( Instance >= 0 )
      {
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000a85c  push    rbx
0x18000a85e  push    rbp
0x18000a85f  push    rsi
0x18000a860  push    rdi
0x18000a861  sub     rsp, 38h
0x18000a865  mov     rdi, rcx
0x18000a868  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a86f  lea     rbp, WPP_GLOBAL_Control
0x18000a876  cmp     rcx, rbp
0x18000a879  jz      short loc_18000A896
0x18000a87b  test    byte ptr [rcx+1Ch], 20h
0x18000a87f  jz      short loc_18000A896
0x18000a881  mov     rcx, [rcx+10h]
0x18000a885  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000a88c  mov     edx, 14h
0x18000a891  call    WPP_SF_
0x18000a896  xor     edx, edx; pUnkOuter
0x18000a898  lea     rsi, [rdi+28h]
0x18000a89c  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000a8a3  mov     [rsp+58h+ppv], rsi; ppv
0x18000a8a8  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000a8af  lea     r8d, [rdx+1]; dwClsContext
0x18000a8b3  call    cs:__imp_CoCreateInstance
0x18000a8b9  mov     ebx, eax
0x18000a8bb  test    eax, eax
0x18000a8bd  js      short loc_18000A922
0x18000a8bf  mov     rcx, [rsi]
0x18000a8c2  lea     r9, [rdi+30h]
0x18000a8c6  lea     r8, _GUID_595d6e65_732c_4736_853f_db64f5aa1eec
0x18000a8cd  mov     rdx, rdi
0x18000a8d0  mov     rax, [rcx]
0x18000a8d3  mov     rax, [rax+18h]
0x18000a8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8dc  mov     ebx, eax
0x18000a8de  test    eax, eax
0x18000a8e0  js      short loc_18000A922
0x18000a8e2  xor     edx, edx; pUnkOuter
0x18000a8e4  lea     rax, [rdi+0D8h]
0x18000a8eb  lea     r9, _GUID_01f5f85e_0a81_40da_a7c8_21ef3af8440c; riid
0x18000a8f2  mov     [rsp+58h+ppv], rax; ppv
0x18000a8f7  lea     rcx, _GUID_ad581b00_7b64_4e59_a38d_d2c5bf51ddb3; rclsid
0x18000a8fe  lea     r8d, [rdx+1]; dwClsContext
0x18000a902  call    cs:__imp_CoCreateInstance
0x18000a908  mov     ebx, eax
0x18000a90a  test    eax, eax
0x18000a90c  js      short loc_18000A922
0x18000a90e  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000a912  call    cs:__imp_InitializeCriticalSection
0x18000a918  lea     rcx, [rdi+70h]; lpCriticalSection
0x18000a91c  call    cs:__imp_InitializeCriticalSection
0x18000a922  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a929  cmp     rcx, rbp
0x18000a92c  jz      short loc_18000A94C
0x18000a92e  test    byte ptr [rcx+1Ch], 20h
0x18000a932  jz      short loc_18000A94C
0x18000a934  mov     rcx, [rcx+10h]
0x18000a938  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000a93f  mov     edx, 15h
0x18000a944  mov     r9d, ebx
0x18000a947  call    WPP_SF_d
0x18000a94c  mov     eax, ebx
0x18000a94e  add     rsp, 38h
0x18000a952  pop     rdi
0x18000a953  pop     rsi
0x18000a954  pop     rbp
0x18000a955  pop     rbx
0x18000a956  retn
```
