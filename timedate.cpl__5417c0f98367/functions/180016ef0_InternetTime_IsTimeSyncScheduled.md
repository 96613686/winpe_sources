# InternetTime_IsTimeSyncScheduled

- ea: `0x180016ef0`
- end: `0x180017044`
- name: `InternetTime_IsTimeSyncScheduled`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001b618`

## callees

- `0x1800130b4`
- `0x180016ef0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016f32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016f32`

## pseudocode

```c
_BOOL8 InternetTime_IsTimeSyncScheduled()
{
  BOOL v0; // esi
  __int64 v1; // rax
  int (__fastcall *v2)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rax
  LPVOID v3; // rdi
  int (__fastcall *v4)(LPVOID, const wchar_t *, __int64 *); // rbx
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, const wchar_t *, __int64 *); // rbx
  __int128 v8; // [rsp+30h] [rbp-49h] BYREF
  __int64 v9; // [rsp+40h] [rbp-39h]
  __int128 v10; // [rsp+50h] [rbp-29h] BYREF
  __int64 v11; // [rsp+60h] [rbp-19h]
  __int128 v12; // [rsp+70h] [rbp-9h] BYREF
  __int64 v13; // [rsp+80h] [rbp+7h]
  __int128 v14; // [rsp+90h] [rbp+17h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+27h]
  int v16; // [rsp+E0h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v18; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v19; // [rsp+F8h] [rbp+7Fh] BYREF

  v0 = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  if ( CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv) >= 0 )
  {
    v9 = 0;
    v11 = 0;
    v13 = 0;
    v15 = 0;
    v1 = *(_QWORD *)ppv;
    v8 = 0;
    v10 = 0;
    v12 = 0;
    v2 = *(int (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(v1 + 80);
    v14 = 0;
    if ( v2(ppv, &v14, &v12, &v10, &v8) >= 0 )
    {
      v3 = ppv;
      v19 = 0;
      v4 = *(int (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 56LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      if ( v4(v3, L"\\Microsoft\\Windows\\Time Synchronization", &v19) >= 0 )
      {
        v5 = v19;
        v18 = 0;
        v6 = *(int (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v19 + 104LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
        if ( v6(v5, L"SynchronizeTime", &v18) >= 0 )
        {
          v16 = 0;
          if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 72LL))(v18, &v16) >= 0 )
            v0 = v16 != 1;
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return v0;
}

```

## disassembly

```asm
0x180016ef0  push    rbp
0x180016ef2  push    rbx
0x180016ef3  push    rsi
0x180016ef4  push    rdi
0x180016ef5  push    r15
0x180016ef7  lea     rbp, [rsp-37h]
0x180016efc  sub     rsp, 0B0h
0x180016f03  xor     esi, esi
0x180016f05  lea     rcx, [rbp+57h+arg_8]
0x180016f09  mov     [rbp+57h+arg_8], rsi
0x180016f0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016f12  lea     rax, [rbp+57h+arg_8]
0x180016f16  xor     edx, edx; pUnkOuter
0x180016f18  lea     r15d, [rsi+1]
0x180016f1c  mov     [rsp+0D0h+ppv], rax; ppv
0x180016f21  mov     r8d, r15d; dwClsContext
0x180016f24  lea     r9, IID_ITaskService; riid
0x180016f2b  lea     rcx, CLSID_TaskScheduler; rclsid
0x180016f32  call    cs:__imp_CoCreateInstance
0x180016f38  test    eax, eax
0x180016f3a  js      loc_18001702B
0x180016f40  mov     rcx, [rbp+57h+arg_8]
0x180016f44  lea     rdx, [rbp+57h+var_A0]
0x180016f48  xor     eax, eax
0x180016f4a  mov     [rsp+0D0h+ppv], rdx
0x180016f4f  xorps   xmm1, xmm1
0x180016f52  mov     [rbp+57h+var_90], rax
0x180016f56  mov     [rbp+57h+var_70], rax
0x180016f5a  lea     r9, [rbp+57h+var_80]
0x180016f5e  mov     [rbp+57h+var_50], rax
0x180016f62  lea     r8, [rbp+57h+var_60]
0x180016f66  mov     [rbp+57h+var_30], rax
0x180016f6a  lea     rdx, [rbp+57h+var_40]
0x180016f6e  mov     rax, [rcx]
0x180016f71  movaps  [rbp+57h+var_A0], xmm1
0x180016f75  movaps  [rbp+57h+var_80], xmm1
0x180016f79  movaps  [rbp+57h+var_60], xmm1
0x180016f7d  mov     rax, [rax+50h]
0x180016f81  movaps  [rbp+57h+var_40], xmm1
0x180016f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f8a  test    eax, eax
0x180016f8c  js      loc_18001702B
0x180016f92  mov     rdi, [rbp+57h+arg_8]
0x180016f96  lea     rcx, [rbp+57h+arg_18]
0x180016f9a  mov     [rbp+57h+arg_18], rsi
0x180016f9e  mov     rax, [rdi]
0x180016fa1  mov     rbx, [rax+38h]
0x180016fa5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016faa  lea     r8, [rbp+57h+arg_18]
0x180016fae  mov     rcx, rdi
0x180016fb1  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Time Synchronizat"...
0x180016fb8  mov     rax, rbx
0x180016fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fc0  test    eax, eax
0x180016fc2  js      short loc_180017022
0x180016fc4  mov     rdi, [rbp+57h+arg_18]
0x180016fc8  lea     rcx, [rbp+57h+arg_10]
0x180016fcc  mov     [rbp+57h+arg_10], rsi
0x180016fd0  mov     rax, [rdi]
0x180016fd3  mov     rbx, [rax+68h]
0x180016fd7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180016fdc  lea     r8, [rbp+57h+arg_10]
0x180016fe0  mov     rcx, rdi
0x180016fe3  lea     rdx, aSynchronizetim; "SynchronizeTime"
0x180016fea  mov     rax, rbx
0x180016fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ff2  test    eax, eax
0x180016ff4  js      short loc_180017019
0x180016ff6  mov     rcx, [rbp+57h+arg_10]
0x180016ffa  lea     rdx, [rbp+57h+arg_0]
0x180016ffe  mov     [rbp+57h+arg_0], esi
0x180017001  mov     rax, [rcx]
0x180017004  mov     rax, [rax+48h]
0x180017008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001700d  test    eax, eax
0x18001700f  js      short loc_180017019
0x180017011  cmp     [rbp+57h+arg_0], r15d
0x180017015  cmovnz  esi, r15d
0x180017019  lea     rcx, [rbp+57h+arg_10]
0x18001701d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017022  lea     rcx, [rbp+57h+arg_18]
0x180017026  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001702b  lea     rcx, [rbp+57h+arg_8]
0x18001702f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017034  mov     eax, esi
0x180017036  add     rsp, 0B0h
0x18001703d  pop     r15
0x18001703f  pop     rdi
0x180017040  pop     rsi
0x180017041  pop     rbx
0x180017042  pop     rbp
0x180017043  retn
```
