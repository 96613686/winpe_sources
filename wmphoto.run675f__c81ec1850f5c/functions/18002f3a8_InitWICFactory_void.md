# InitWICFactory(void)

- ea: `0x18002f3a8`
- end: `0x18002f46a`
- name: `?InitWICFactory@@YAJXZ`
- size: `194`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b078`
- `0x18002f250`

## callees

- `0x18002f3a8`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f450`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f3c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f3c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f3fc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f3fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 InitWICFactory(void)
{
  HRESULT v0; // ebx
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF
  _RTL_CRITICAL_SECTION *v3; // [rsp+48h] [rbp+10h]

  v0 = 0;
  ppv = 0;
  v3 = &g_csWICFactoryLock;
  EnterCriticalSection(&g_csWICFactoryLock);
  if ( !qword_1800513B0 )
  {
    v0 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &IID_IWICImagingFactory, &ppv);
    if ( v0 >= 0 )
      v0 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &IID_IWICComponentFactory,
             &qword_1800513B0);
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  LeaveCriticalSection(&g_csWICFactoryLock);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18002f3a8  mov     [rsp+arg_10], rbx
0x18002f3ad  push    rsi
0x18002f3ae  sub     rsp, 30h
0x18002f3b2  xor     ebx, ebx
0x18002f3b4  mov     [rsp+38h+arg_0], rbx
0x18002f3b9  lea     rsi, ?g_csWICFactoryLock@@3VCCriticalSection@@A; CCriticalSection g_csWICFactoryLock
0x18002f3c0  mov     [rsp+38h+arg_8], rsi
0x18002f3c5  mov     rcx, rsi; lpCriticalSection
0x18002f3c8  call    cs:__imp_EnterCriticalSection
0x18002f3cf  nop     dword ptr [rax+rax+00h]
0x18002f3d4  nop
0x18002f3d5  cmp     cs:qword_1800513B0, rbx
0x18002f3dc  jnz     short loc_18002F42E
0x18002f3de  lea     rax, [rsp+38h+arg_0]
0x18002f3e3  mov     [rsp+38h+ppv], rax; ppv
0x18002f3e8  lea     r9, IID_IWICImagingFactory; riid
0x18002f3ef  xor     edx, edx; pUnkOuter
0x18002f3f1  lea     r8d, [rbx+1]; dwClsContext
0x18002f3f5  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18002f3fc  call    cs:__imp_CoCreateInstance
0x18002f403  nop     dword ptr [rax+rax+00h]
0x18002f408  mov     ebx, eax
0x18002f40a  test    eax, eax
0x18002f40c  js      short loc_18002F42E
0x18002f40e  mov     rcx, [rsp+38h+arg_0]
0x18002f413  mov     rax, [rcx]
0x18002f416  lea     r8, qword_1800513B0
0x18002f41d  lea     rdx, IID_IWICComponentFactory
0x18002f424  mov     rax, [rax]
0x18002f427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f42c  mov     ebx, eax
0x18002f42e  mov     rcx, [rsp+38h+arg_0]
0x18002f433  test    rcx, rcx
0x18002f436  jz      short loc_18002F44D
0x18002f438  mov     rax, [rcx]
0x18002f43b  mov     rax, [rax+10h]
0x18002f43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f444  mov     [rsp+38h+arg_0], 0
0x18002f44d  mov     rcx, rsi; lpCriticalSection
0x18002f450  call    cs:__imp_LeaveCriticalSection
0x18002f457  nop     dword ptr [rax+rax+00h]
0x18002f45c  mov     eax, ebx
0x18002f45e  mov     rbx, [rsp+38h+arg_10]
0x18002f463  add     rsp, 30h
0x18002f467  pop     rsi
0x18002f468  retn
```
