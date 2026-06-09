# InitWICFactory(void)

- ea: `0x18002f018`
- end: `0x18002f0c7`
- name: `?InitWICFactory@@YAJXZ`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002aec8`
- `0x18002eec0`

## callees

- `0x18002f018`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f0b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f0b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f038`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f038`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f066`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f066`

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
  if ( !qword_1800503B0 )
  {
    v0 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &IID_IWICImagingFactory, &ppv);
    if ( v0 >= 0 )
      v0 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &IID_IWICComponentFactory,
             &qword_1800503B0);
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
0x18002f018  mov     [rsp+arg_10], rbx
0x18002f01d  push    rsi
0x18002f01e  sub     rsp, 30h
0x18002f022  xor     ebx, ebx
0x18002f024  mov     [rsp+38h+arg_0], rbx
0x18002f029  lea     rsi, ?g_csWICFactoryLock@@3VCCriticalSection@@A; CCriticalSection g_csWICFactoryLock
0x18002f030  mov     [rsp+38h+arg_8], rsi
0x18002f035  mov     rcx, rsi; lpCriticalSection
0x18002f038  call    cs:__imp_EnterCriticalSection
0x18002f03e  nop
0x18002f03f  cmp     cs:qword_1800503B0, rbx
0x18002f046  jnz     short loc_18002F092
0x18002f048  lea     rax, [rsp+38h+arg_0]
0x18002f04d  mov     [rsp+38h+ppv], rax; ppv
0x18002f052  lea     r9, IID_IWICImagingFactory; riid
0x18002f059  xor     edx, edx; pUnkOuter
0x18002f05b  lea     r8d, [rbx+1]; dwClsContext
0x18002f05f  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18002f066  call    cs:__imp_CoCreateInstance
0x18002f06c  mov     ebx, eax
0x18002f06e  test    eax, eax
0x18002f070  js      short loc_18002F092
0x18002f072  mov     rcx, [rsp+38h+arg_0]
0x18002f077  mov     rax, [rcx]
0x18002f07a  lea     r8, qword_1800503B0
0x18002f081  lea     rdx, IID_IWICComponentFactory
0x18002f088  mov     rax, [rax]
0x18002f08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f090  mov     ebx, eax
0x18002f092  mov     rcx, [rsp+38h+arg_0]
0x18002f097  test    rcx, rcx
0x18002f09a  jz      short loc_18002F0B1
0x18002f09c  mov     rax, [rcx]
0x18002f09f  mov     rax, [rax+10h]
0x18002f0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0a8  mov     [rsp+38h+arg_0], 0
0x18002f0b1  mov     rcx, rsi; lpCriticalSection
0x18002f0b4  call    cs:__imp_LeaveCriticalSection
0x18002f0ba  mov     eax, ebx
0x18002f0bc  mov     rbx, [rsp+38h+arg_10]
0x18002f0c1  add     rsp, 30h
0x18002f0c5  pop     rsi
0x18002f0c6  retn
```
