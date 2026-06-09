# _CreateInstanceInProcess

- ea: `0x180016fac`
- end: `0x1800170a8`
- name: `_CreateInstanceInProcess`
- size: `252`
- prototype: `__int64 __usercall@<rax>(HANDLE ProcessHandle@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ad34`

## callees

- `0x1800043a4`
- `0x180016d0c`
- `0x180016f7c`
- `0x180016fac`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180016fef`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180016fef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017052`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017052`

## pseudocode

```c
__int64 CreateInstanceInProcess(HANDLE ProcessHandle, void *a2, ...)
{
  _QWORD *v2; // rdi
  HRESULT Instance; // ebx
  HANDLE v6[3]; // [rsp+30h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp+18h] BYREF
  va_list hObjecta; // [rsp+60h] [rbp+18h]
  LPVOID ppv; // [rsp+68h] [rbp+20h] BYREF
  va_list va1; // [rsp+68h] [rbp+20h]
  _QWORD *v11; // [rsp+70h] [rbp+28h]
  va_list va2; // [rsp+78h] [rbp+30h] BYREF

  va_start(va2, a2);
  va_start(va1, a2);
  va_start(hObjecta, a2);
  hObject = va_arg(va1, HANDLE);
  va_copy(va2, va1);
  ppv = va_arg(va2, LPVOID);
  v11 = va_arg(va2, _QWORD *);
  v2 = v11;
  v6[0] = a2;
  v6[1] = ProcessHandle;
  *v11 = 0;
  if ( WaitForMultipleObjectsEx(2u, v6, 0, 0x7530u, 0) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    hObject = 0;
    Instance = _ImpersonateProcessToken(ProcessHandle, (void **)hObjecta);
    if ( Instance >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)va1);
      Instance = CoCreateInstance(
                   &CLSID_CreateObjectLocalServer,
                   0,
                   0x100004u,
                   &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                   (LPVOID *)va1);
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(LPVOID, GUID *, _QWORD, GUID *, _QWORD *))(*(_QWORD *)ppv + 24LL))(
                     ppv,
                     &CLSID_ImageSanitizationValidator,
                     0,
                     &GUID_3a05b5ea_527e_4c9b_ba53_58aca78d0b56,
                     v2);
      _RevertImpersonationToken(hObject);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)va1);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180016fac  mov     rax, rsp
0x180016faf  mov     [rax+8], rbx
0x180016fb3  mov     [rax+20h], r9
0x180016fb7  mov     [rax+18h], r8
0x180016fbb  push    rdi
0x180016fbc  sub     rsp, 40h
0x180016fc0  mov     rdi, [rsp+48h+arg_20]
0x180016fc5  xor     r8d, r8d; bWaitAll
0x180016fc8  mov     rbx, rcx
0x180016fcb  mov     [rax-18h], rdx
0x180016fcf  mov     [rax-10h], rcx
0x180016fd3  lea     rdx, [rax-18h]; lpHandles
0x180016fd7  mov     r9d, 7530h; dwMilliseconds
0x180016fdd  mov     dword ptr [rax-28h], 0
0x180016fe4  lea     ecx, [r8+2]; nCount
0x180016fe8  mov     qword ptr [rdi], 0
0x180016fef  call    cs:__imp_WaitForMultipleObjectsEx
0x180016ff5  test    eax, eax
0x180016ff7  jz      short loc_180017003
0x180016ff9  mov     ebx, 80004005h
0x180016ffe  jmp     loc_18001709B
0x180017003  lea     rdx, [rsp+48h+hObject]; void **
0x180017008  mov     [rsp+48h+hObject], 0
0x180017011  mov     rcx, rbx; ProcessHandle
0x180017014  call    ?_ImpersonateProcessToken@@YAJPEAXPEAPEAX@Z; _ImpersonateProcessToken(void *,void * *)
0x180017019  mov     ebx, eax
0x18001701b  test    eax, eax
0x18001701d  js      short loc_18001709B
0x18001701f  lea     rcx, [rsp+48h+arg_18]
0x180017024  mov     [rsp+48h+arg_18], 0
0x18001702d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180017032  lea     rax, [rsp+48h+arg_18]
0x180017037  xor     edx, edx; pUnkOuter
0x180017039  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180017040  mov     [rsp+48h+ppv], rax; ppv
0x180017045  mov     r8d, 100004h; dwClsContext
0x18001704b  lea     rcx, CLSID_CreateObjectLocalServer; rclsid
0x180017052  call    cs:__imp_CoCreateInstance
0x180017058  mov     ebx, eax
0x18001705a  test    eax, eax
0x18001705c  js      short loc_180017087
0x18001705e  mov     rcx, [rsp+48h+arg_18]
0x180017063  lea     r9, _GUID_3a05b5ea_527e_4c9b_ba53_58aca78d0b56
0x18001706a  xor     r8d, r8d
0x18001706d  mov     [rsp+48h+ppv], rdi
0x180017072  lea     rdx, CLSID_ImageSanitizationValidator
0x180017079  mov     rax, [rcx]
0x18001707c  mov     rax, [rax+18h]
0x180017080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017085  mov     ebx, eax
0x180017087  mov     rcx, [rsp+48h+hObject]; hObject
0x18001708c  call    ?_RevertImpersonationToken@@YAXPEAX@Z; _RevertImpersonationToken(void *)
0x180017091  lea     rcx, [rsp+48h+arg_18]
0x180017096  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001709b  mov     eax, ebx
0x18001709d  mov     rbx, [rsp+48h+arg_0]
0x1800170a2  add     rsp, 40h
0x1800170a6  pop     rdi
0x1800170a7  retn
```
