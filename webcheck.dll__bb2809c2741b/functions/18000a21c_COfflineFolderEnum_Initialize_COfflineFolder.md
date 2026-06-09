# COfflineFolderEnum::Initialize(COfflineFolder *)

- ea: `0x18000a21c`
- end: `0x18000a363`
- name: `?Initialize@COfflineFolderEnum@@QEAAJPEAVCOfflineFolder@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(COfflineFolderEnum *__hidden this, struct COfflineFolder *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ba0`

## callees

- `0x18000a21c`
- `0x18001ba08`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000a283`
- `ole32!CoCreateInstance` at `0x18000a283`
- `ole32!CoUninitialize` at `0x18000a344`
- `ole32!CoUninitialize` at `0x18000a344`
- `ole32!CoInitialize` at `0x18000a24c`
- `ole32!CoInitialize` at `0x18000a24c`

## pseudocode

```c
__int64 __fastcall COfflineFolderEnum::Initialize(COfflineFolderEnum *this, struct COfflineFolder *a2)
{
  HRESULT v3; // ebx
  unsigned int *v4; // rsi
  void *v5; // rax
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 )
  {
    *((_QWORD *)this + 4) = a2;
    (*(void (__fastcall **)(struct COfflineFolder *))(*(_QWORD *)a2 + 8LL))(a2);
    v3 = CoInitialize(0);
    if ( v3 >= 0 )
    {
      ppv = 0;
      v3 = CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr2, &ppv);
      if ( v3 >= 0 )
      {
        v7 = 0;
        v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 112LL))(ppv, 0, &v7);
        if ( v3 >= 0 )
        {
          v4 = (unsigned int *)((char *)this + 16);
          (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v7 + 56LL))(v7, (char *)this + 16);
          if ( *((_DWORD *)this + 4) )
          {
            v5 = operator new(saturated_mul(*v4, 0x10u));
            *((_QWORD *)this + 3) = v5;
            if ( v5 )
              v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *, char *))(*(_QWORD *)v7 + 24LL))(
                     v7,
                     *v4,
                     v5,
                     (char *)this + 16);
            else
              v3 = -2147024882;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      CoUninitialize();
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a21c  mov     [rsp+arg_0], rbx
0x18000a221  mov     [rsp+arg_18], rsi
0x18000a226  push    rdi
0x18000a227  sub     rsp, 30h
0x18000a22b  mov     rdi, rcx
0x18000a22e  test    rdx, rdx
0x18000a231  jz      loc_18000A34C
0x18000a237  mov     [rcx+20h], rdx
0x18000a23b  mov     rcx, rdx
0x18000a23e  mov     rax, [rdx]
0x18000a241  mov     rax, [rax+8]
0x18000a245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24a  xor     ecx, ecx; pvReserved
0x18000a24c  call    cs:__imp_CoInitialize
0x18000a252  mov     ebx, eax
0x18000a254  test    eax, eax
0x18000a256  js      loc_18000A351
0x18000a25c  xor     edx, edx; pUnkOuter
0x18000a25e  mov     [rsp+38h+arg_10], 0
0x18000a267  lea     rax, [rsp+38h+arg_10]
0x18000a26c  lea     r9, IID_ISubscriptionMgr2; riid
0x18000a273  mov     [rsp+38h+ppv], rax; ppv
0x18000a278  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x18000a27f  lea     r8d, [rdx+1]; dwClsContext
0x18000a283  call    cs:__imp_CoCreateInstance
0x18000a289  mov     ebx, eax
0x18000a28b  test    eax, eax
0x18000a28d  js      loc_18000A344
0x18000a293  mov     rcx, [rsp+38h+arg_10]
0x18000a298  lea     r8, [rsp+38h+arg_8]
0x18000a29d  mov     [rsp+38h+arg_8], 0
0x18000a2a6  xor     edx, edx
0x18000a2a8  mov     rax, [rcx]
0x18000a2ab  mov     rax, [rax+70h]
0x18000a2af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2b4  mov     ebx, eax
0x18000a2b6  test    eax, eax
0x18000a2b8  js      short loc_18000A333
0x18000a2ba  mov     rcx, [rsp+38h+arg_8]
0x18000a2bf  lea     rsi, [rdi+10h]
0x18000a2c3  mov     rdx, rsi
0x18000a2c6  mov     rax, [rcx]
0x18000a2c9  mov     rax, [rax+38h]
0x18000a2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2d2  cmp     dword ptr [rsi], 0
0x18000a2d5  jbe     short loc_18000A322
0x18000a2d7  mov     ecx, [rsi]
0x18000a2d9  mov     eax, 10h
0x18000a2de  mul     rcx
0x18000a2e1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a2e8  cmovb   rax, rcx
0x18000a2ec  mov     rcx, rax; dwBytes
0x18000a2ef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a2f4  mov     [rdi+18h], rax
0x18000a2f8  mov     rdx, rax
0x18000a2fb  test    rax, rax
0x18000a2fe  jz      short loc_18000A31D
0x18000a300  mov     rcx, [rsp+38h+arg_8]
0x18000a305  mov     r9, rsi
0x18000a308  mov     r8, [rcx]
0x18000a30b  mov     rax, [r8+18h]
0x18000a30f  mov     r8, rdx
0x18000a312  mov     edx, [rsi]
0x18000a314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a319  mov     ebx, eax
0x18000a31b  jmp     short loc_18000A322
0x18000a31d  mov     ebx, 8007000Eh
0x18000a322  mov     rcx, [rsp+38h+arg_8]
0x18000a327  mov     rax, [rcx]
0x18000a32a  mov     rax, [rax+10h]
0x18000a32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a333  mov     rcx, [rsp+38h+arg_10]
0x18000a338  mov     rax, [rcx]
0x18000a33b  mov     rax, [rax+10h]
0x18000a33f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a344  call    cs:__imp_CoUninitialize
0x18000a34a  jmp     short loc_18000A351
0x18000a34c  mov     ebx, 80070057h
0x18000a351  mov     rsi, [rsp+38h+arg_18]
0x18000a356  mov     eax, ebx
0x18000a358  mov     rbx, [rsp+38h+arg_0]
0x18000a35d  add     rsp, 30h
0x18000a361  pop     rdi
0x18000a362  retn
```
