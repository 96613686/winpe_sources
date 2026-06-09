# CCOMFactoryServer::Init(void)

- ea: `0x1800237d4`
- end: `0x18002389d`
- name: `?Init@CCOMFactoryServer@@QEAAJXZ`
- size: `201`
- prototype: `__int64 __fastcall(CCOMFactoryServer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001efc8`

## callees

- `0x180017ee8`
- `0x1800237d4`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002383a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002383a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002384b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002384b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023807`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023877`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023807`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023877`

## pseudocode

```c
__int64 __fastcall CCOMFactoryServer::Init(CCOMFactoryServer *this)
{
  HRESULT Instance; // ebx
  SIZE_T v3; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v5; // rax
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  Instance = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
    if ( Instance >= 0 )
    {
      v3 = 16LL * *((unsigned int *)this + 6);
      ProcessHeap = GetProcessHeap();
      v5 = HeapAlloc(ProcessHeap, 8u, v3);
      *((_QWORD *)this + 5) = v5;
      if ( v5 )
        Instance = CoCreateInstance(
                     &CLSID_ContextSwitcher,
                     0,
                     1u,
                     &GUID_000001da_0000_0000_c000_000000000046,
                     (LPVOID *)this + 4);
      else
        Instance = -2147024882;
    }
  }
  ATL::CComPtrBase<CDeviceQueryWrapper>::~CComPtrBase<CDeviceQueryWrapper>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800237d4  mov     r11, rsp
0x1800237d7  mov     [r11+8], rbx
0x1800237db  push    rdi
0x1800237dc  sub     rsp, 30h
0x1800237e0  xor     edx, edx; pUnkOuter
0x1800237e2  mov     qword ptr [r11+10h], 0
0x1800237ea  mov     rdi, rcx
0x1800237ed  lea     rax, [r11+10h]
0x1800237f1  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800237f8  mov     [r11-18h], rax
0x1800237fc  lea     rcx, CLSID_GlobalOptions; rclsid
0x180023803  lea     r8d, [rdx+1]; dwClsContext
0x180023807  call    cs:__imp_CoCreateInstance
0x18002380d  mov     ebx, eax
0x18002380f  test    eax, eax
0x180023811  js      short loc_180023886
0x180023813  mov     rcx, [rsp+38h+arg_8]
0x180023818  mov     edx, 5
0x18002381d  mov     rax, [rcx]
0x180023820  lea     r8d, [rdx-4]
0x180023824  mov     rax, [rax+18h]
0x180023828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002382d  mov     ebx, eax
0x18002382f  test    eax, eax
0x180023831  js      short loc_180023886
0x180023833  mov     ebx, [rdi+18h]
0x180023836  shl     rbx, 4
0x18002383a  call    cs:__imp_GetProcessHeap
0x180023840  mov     r8, rbx; dwBytes
0x180023843  mov     edx, 8; dwFlags
0x180023848  mov     rcx, rax; hHeap
0x18002384b  call    cs:__imp_HeapAlloc
0x180023851  mov     [rdi+28h], rax
0x180023855  test    rax, rax
0x180023858  jz      short loc_180023881
0x18002385a  xor     edx, edx; pUnkOuter
0x18002385c  lea     rax, [rdi+20h]
0x180023860  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180023867  mov     [rsp+38h+ppv], rax; ppv
0x18002386c  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180023873  lea     r8d, [rdx+1]; dwClsContext
0x180023877  call    cs:__imp_CoCreateInstance
0x18002387d  mov     ebx, eax
0x18002387f  jmp     short loc_180023886
0x180023881  mov     ebx, 8007000Eh
0x180023886  lea     rcx, [rsp+38h+arg_8]
0x18002388b  call    ??1?$CComPtrBase@VCDeviceQueryWrapper@@@ATL@@QEAA@XZ; ATL::CComPtrBase<CDeviceQueryWrapper>::~CComPtrBase<CDeviceQueryWrapper>(void)
0x180023890  mov     eax, ebx
0x180023892  mov     rbx, [rsp+38h+arg_0]
0x180023897  add     rsp, 30h
0x18002389b  pop     rdi
0x18002389c  retn
```
