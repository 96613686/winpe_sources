# EnumSchedules(int (*)(ISyncSchedule *,_GUID const *,__int64),__int64)

- ea: `0x18000b910`
- end: `0x18000ba8d`
- name: `?EnumSchedules@@YAJP6AHPEAUISyncSchedule@@PEBU_GUID@@_J@Z2@Z`
- size: `381`
- prototype: `__int64 __fastcall(int (*)(struct ISyncSchedule *, const struct _GUID *, __int64), __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bd20`
- `0x180013b38`
- `0x180023b54`

## callees

- `0x18000af60`
- `0x18000af94`
- `0x18000b910`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000b979`
- `ole32!CoCreateInstance` at `0x18000b979`
- `ole32!CoUninitialize` at `0x18000ba64`
- `ole32!CoUninitialize` at `0x18000ba64`
- `ole32!CoInitialize` at `0x18000b943`
- `ole32!CoInitialize` at `0x18000b943`

## pseudocode

```c
__int64 __fastcall EnumSchedules(__int64 (__fastcall *a1)(__int64, __int128 *, __int64), __int64 a2)
{
  HRESULT v4; // edi
  int v5; // ebx
  int v7; // [rsp+30h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-38h] BYREF
  __int64 v9; // [rsp+40h] [rbp-30h] BYREF
  __int64 v10; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v11[8]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v12; // [rsp+58h] [rbp-18h] BYREF

  ppv = 0;
  v4 = CoInitialize(0);
  if ( v4 >= 0 )
  {
    CWaitCursor::CWaitCursor((CWaitCursor *)v11);
    v4 = CoCreateInstance(&CLSID_SyncMgr, 0, 0x17u, &IID_ISyncScheduleMgr, &ppv);
    if ( v4 >= 0 )
    {
      v10 = 0;
      v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, &v10);
      if ( v4 >= 0 )
      {
        v7 = 0;
        v12 = 0;
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int128 *, int *))(*(_QWORD *)v10 + 24LL))(
                   v10,
                   1,
                   &v12,
                   &v7)
             && v7 )
        {
          v9 = 0;
          if ( (*(int (__fastcall **)(LPVOID, __int128 *, _QWORD, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, &v12, 0, &v9) >= 0 )
          {
            if ( v9 )
            {
              v5 = a1(v9, &v12, a2);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
              if ( !v5 )
              {
                v4 = 1;
                break;
              }
            }
          }
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CWaitCursor::~CWaitCursor((CWaitCursor *)v11);
    CoUninitialize();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b910  mov     [rsp-18h+arg_10], rbx
0x18000b915  mov     [rsp-18h+arg_18], rsi
0x18000b91a  push    rbp
0x18000b91b  push    rdi
0x18000b91c  push    r14
0x18000b91e  mov     rbp, rsp
0x18000b921  sub     rsp, 70h
0x18000b925  mov     rax, cs:__security_cookie
0x18000b92c  xor     rax, rsp
0x18000b92f  mov     [rbp+var_8], rax
0x18000b933  mov     rsi, rcx
0x18000b936  mov     [rbp+var_38], 0
0x18000b93e  xor     ecx, ecx; pvReserved
0x18000b940  mov     r14, rdx
0x18000b943  call    cs:__imp_CoInitialize
0x18000b949  mov     edi, eax
0x18000b94b  test    eax, eax
0x18000b94d  js      loc_18000BA6A
0x18000b953  lea     rcx, [rbp+var_20]; this
0x18000b957  call    ??0CWaitCursor@@QEAA@XZ; CWaitCursor::CWaitCursor(void)
0x18000b95c  xor     edx, edx; pUnkOuter
0x18000b95e  lea     rax, [rbp+var_38]
0x18000b962  lea     r9, IID_ISyncScheduleMgr; riid
0x18000b969  mov     [rsp+70h+ppv], rax; ppv
0x18000b96e  lea     rcx, CLSID_SyncMgr; rclsid
0x18000b975  lea     r8d, [rdx+17h]; dwClsContext
0x18000b979  call    cs:__imp_CoCreateInstance
0x18000b97f  mov     edi, eax
0x18000b981  test    eax, eax
0x18000b983  js      loc_18000BA5B
0x18000b989  mov     rcx, [rbp+var_38]
0x18000b98d  lea     rdx, [rbp+var_28]
0x18000b991  mov     [rbp+var_28], 0
0x18000b999  mov     rax, [rcx]
0x18000b99c  mov     rax, [rax+38h]
0x18000b9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9a5  mov     edi, eax
0x18000b9a7  test    eax, eax
0x18000b9a9  js      loc_18000BA4B
0x18000b9af  xorps   xmm0, xmm0
0x18000b9b2  mov     [rbp+var_40], 0
0x18000b9b9  movups  [rbp+var_18], xmm0
0x18000b9bd  mov     rcx, [rbp+var_28]
0x18000b9c1  lea     r9, [rbp+var_40]
0x18000b9c5  lea     r8, [rbp+var_18]
0x18000b9c9  mov     edx, 1
0x18000b9ce  mov     rax, [rcx]
0x18000b9d1  mov     rax, [rax+18h]
0x18000b9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9da  test    eax, eax
0x18000b9dc  jnz     short loc_18000BA3B
0x18000b9de  cmp     [rbp+var_40], eax
0x18000b9e1  jz      short loc_18000BA3B
0x18000b9e3  mov     rcx, [rbp+var_38]
0x18000b9e7  lea     r9, [rbp+var_30]
0x18000b9eb  mov     [rbp+var_30], 0
0x18000b9f3  lea     rdx, [rbp+var_18]
0x18000b9f7  xor     r8d, r8d
0x18000b9fa  mov     rax, [rcx]
0x18000b9fd  mov     rax, [rax+28h]
0x18000ba01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba06  test    eax, eax
0x18000ba08  js      short loc_18000B9BD
0x18000ba0a  mov     rcx, [rbp+var_30]
0x18000ba0e  test    rcx, rcx
0x18000ba11  jz      short loc_18000B9BD
0x18000ba13  mov     r8, r14
0x18000ba16  lea     rdx, [rbp+var_18]
0x18000ba1a  mov     rax, rsi
0x18000ba1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba22  mov     rcx, [rbp+var_30]
0x18000ba26  mov     ebx, eax
0x18000ba28  mov     rdx, [rcx]
0x18000ba2b  mov     rax, [rdx+10h]
0x18000ba2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba34  test    ebx, ebx
0x18000ba36  jnz     short loc_18000B9BD
0x18000ba38  lea     edi, [rbx+1]
0x18000ba3b  mov     rcx, [rbp+var_28]
0x18000ba3f  mov     rax, [rcx]
0x18000ba42  mov     rax, [rax+10h]
0x18000ba46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba4b  mov     rcx, [rbp+var_38]
0x18000ba4f  mov     rax, [rcx]
0x18000ba52  mov     rax, [rax+10h]
0x18000ba56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba5b  lea     rcx, [rbp+var_20]; this
0x18000ba5f  call    ??1CWaitCursor@@QEAA@XZ; CWaitCursor::~CWaitCursor(void)
0x18000ba64  call    cs:__imp_CoUninitialize
0x18000ba6a  mov     eax, edi
0x18000ba6c  mov     rcx, [rbp+var_8]
0x18000ba70  xor     rcx, rsp; StackCookie
0x18000ba73  call    __security_check_cookie
0x18000ba78  lea     r11, [rsp+70h+var_s0]
0x18000ba7d  mov     rbx, [r11+30h]
0x18000ba81  mov     rsi, [r11+38h]
0x18000ba85  mov     rsp, r11
0x18000ba88  pop     r14
0x18000ba8a  pop     rdi
0x18000ba8b  pop     rbp
0x18000ba8c  retn
```
