# RemoveItemFromAllSchedules(_GUID *)

- ea: `0x18000d2ec`
- end: `0x18000d477`
- name: `?RemoveItemFromAllSchedules@@YAJPEAU_GUID@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000afb4`
- `0x180013490`

## callees

- `0x18000af60`
- `0x18000af94`
- `0x18000d2ec`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000d34f`
- `ole32!CoCreateInstance` at `0x18000d34f`
- `ole32!CoUninitialize` at `0x18000d451`
- `ole32!CoUninitialize` at `0x18000d451`
- `ole32!CoInitialize` at `0x18000d319`
- `ole32!CoInitialize` at `0x18000d319`

## pseudocode

```c
__int64 __fastcall RemoveItemFromAllSchedules(struct _GUID *a1)
{
  HRESULT v2; // ebx
  int v4; // [rsp+30h] [rbp-40h] BYREF
  __int64 v5; // [rsp+38h] [rbp-38h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-30h] BYREF
  __int64 v7; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v8[8]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v9; // [rsp+58h] [rbp-18h] BYREF

  ppv = 0;
  v2 = CoInitialize(0);
  if ( v2 >= 0 )
  {
    CWaitCursor::CWaitCursor((CWaitCursor *)v8);
    v2 = CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv);
    if ( v2 >= 0 )
    {
      v7 = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, &v7);
      if ( v2 >= 0 )
      {
        v4 = 0;
        v9 = 0;
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int128 *, int *))(*(_QWORD *)v7 + 24LL))(
                   v7,
                   1,
                   &v9,
                   &v4)
             && v4 )
        {
          v5 = 0;
          if ( (*(int (__fastcall **)(LPVOID, __int128 *, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, &v9, 0, &v5) >= 0 )
          {
            (*(void (__fastcall **)(__int64, GUID *, struct _GUID *, _QWORD))(*(_QWORD *)v5 + 136LL))(
              v5,
              &CLSID_WebCheckOfflineSync,
              a1,
              0);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 160LL))(v5);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CWaitCursor::~CWaitCursor((CWaitCursor *)v8);
    CoUninitialize();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000d2ec  mov     [rsp-8+arg_8], rbx
0x18000d2f1  mov     [rsp-8+arg_10], rdi
0x18000d2f6  push    rbp
0x18000d2f7  mov     rbp, rsp
0x18000d2fa  sub     rsp, 70h
0x18000d2fe  mov     rax, cs:__security_cookie
0x18000d305  xor     rax, rsp
0x18000d308  mov     [rbp+var_8], rax
0x18000d30c  mov     rdi, rcx
0x18000d30f  mov     [rbp+var_30], 0
0x18000d317  xor     ecx, ecx; pvReserved
0x18000d319  call    cs:__imp_CoInitialize
0x18000d31f  mov     ebx, eax
0x18000d321  test    eax, eax
0x18000d323  js      loc_18000D457
0x18000d329  lea     rcx, [rbp+var_20]; this
0x18000d32d  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18000d332  xor     edx, edx; pUnkOuter
0x18000d334  lea     rax, [rbp+var_30]
0x18000d338  lea     r9, IID_ISyncScheduleMgr; riid
0x18000d33f  mov     [rsp+70h+ppv], rax; ppv
0x18000d344  lea     rcx, CLSID_SyncMgr; rclsid
0x18000d34b  lea     r8d, [rdx+17h]; dwClsContext
0x18000d34f  call    cs:__imp_CoCreateInstance
0x18000d355  mov     ebx, eax
0x18000d357  test    eax, eax
0x18000d359  js      loc_18000D448
0x18000d35f  mov     rcx, [rbp+var_30]
0x18000d363  lea     rdx, [rbp+var_28]
0x18000d367  mov     [rbp+var_28], 0
0x18000d36f  mov     rax, [rcx]
0x18000d372  mov     rax, [rax+38h]
0x18000d376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d37b  mov     ebx, eax
0x18000d37d  test    eax, eax
0x18000d37f  js      loc_18000D438
0x18000d385  xorps   xmm0, xmm0
0x18000d388  mov     [rbp+var_40], 0
0x18000d38f  movups  [rbp+var_18], xmm0
0x18000d393  mov     rcx, [rbp+var_28]
0x18000d397  lea     r9, [rbp+var_40]
0x18000d39b  lea     r8, [rbp+var_18]
0x18000d39f  mov     edx, 1
0x18000d3a4  mov     rax, [rcx]
0x18000d3a7  mov     rax, [rax+18h]
0x18000d3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b0  test    eax, eax
0x18000d3b2  jnz     short loc_18000D428
0x18000d3b4  cmp     [rbp+var_40], eax
0x18000d3b7  jz      short loc_18000D428
0x18000d3b9  mov     rcx, [rbp+var_30]
0x18000d3bd  lea     r9, [rbp+var_38]
0x18000d3c1  mov     [rbp+var_38], 0
0x18000d3c9  lea     rdx, [rbp+var_18]
0x18000d3cd  xor     r8d, r8d
0x18000d3d0  mov     rax, [rcx]
0x18000d3d3  mov     rax, [rax+28h]
0x18000d3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3dc  test    eax, eax
0x18000d3de  js      short loc_18000D393
0x18000d3e0  mov     rcx, [rbp+var_38]
0x18000d3e4  lea     rdx, CLSID_WebCheckOfflineSync
0x18000d3eb  xor     r9d, r9d
0x18000d3ee  mov     r8, rdi
0x18000d3f1  mov     rax, [rcx]
0x18000d3f4  mov     rax, [rax+88h]
0x18000d3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d400  mov     rcx, [rbp+var_38]
0x18000d404  mov     rax, [rcx]
0x18000d407  mov     rax, [rax+0A0h]
0x18000d40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d413  mov     rcx, [rbp+var_38]
0x18000d417  mov     rax, [rcx]
0x18000d41a  mov     rax, [rax+10h]
0x18000d41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d423  jmp     loc_18000D393
0x18000d428  mov     rcx, [rbp+var_28]
0x18000d42c  mov     rax, [rcx]
0x18000d42f  mov     rax, [rax+10h]
0x18000d433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d438  mov     rcx, [rbp+var_30]
0x18000d43c  mov     rax, [rcx]
0x18000d43f  mov     rax, [rax+10h]
0x18000d443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d448  lea     rcx, [rbp+var_20]; this
0x18000d44c  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x18000d451  call    cs:__imp_CoUninitialize
0x18000d457  mov     eax, ebx
0x18000d459  mov     rcx, [rbp+var_8]
0x18000d45d  xor     rcx, rsp; StackCookie
0x18000d460  call    __security_check_cookie
0x18000d465  lea     r11, [rsp+70h+var_s0]
0x18000d46a  mov     rbx, [r11+18h]
0x18000d46e  mov     rdi, [r11+20h]
0x18000d472  mov     rsp, r11
0x18000d475  pop     rbp
0x18000d476  retn
```
