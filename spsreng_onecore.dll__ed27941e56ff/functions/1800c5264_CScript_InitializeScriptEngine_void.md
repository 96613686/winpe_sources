# CScript::InitializeScriptEngine(void)

- ea: `0x1800c5264`
- end: `0x1800c534d`
- name: `?InitializeScriptEngine@CScript@@QEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(CScript *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800c4d44`

## callees

- `0x180002db8`
- `0x1800c5264`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c5297`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c5297`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CScript::InitializeScriptEngine(LPVOID *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rdx
  HRESULT Instance; // ebx
  __int64 v6; // [rsp+60h] [rbp+8h] BYREF

  v6 = 0;
  v2 = this + 1;
  Instance = CoCreateInstance(&rclsid, 0, 0x17u, &GUID_bb1a2ae1_a4f9_11cf_8f20_00805f2cd064, this + 1);
  if ( Instance >= 0 )
  {
    Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v2)(
                 *v2,
                 &GUID_c7ef7658_e1ee_480e_97ea_d52cb4d76d17,
                 (char *)this + 16);
    if ( Instance >= 0 )
    {
      Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v2)(
                   *v2,
                   &GUID_cb5bdc81_93c1_11cf_8f20_00805f2cd064,
                   &v6);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int64))(*(_QWORD *)v6 + 32LL))(
                     v6,
                     &IID_IActiveScript,
                     2,
                     2);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)this[2] + 24LL))(this[2]);
          if ( Instance >= 0 )
            Instance = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*v2 + 24LL))(*v2, this);
        }
      }
    }
  }
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v6, v3);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800c5264  push    rbx
0x1800c5266  push    rsi
0x1800c5267  push    rdi
0x1800c5268  push    r14
0x1800c526a  sub     rsp, 38h
0x1800c526e  mov     rsi, rcx
0x1800c5271  mov     [rsp+58h+arg_0], 0
0x1800c527a  lea     rdi, [rcx+8]
0x1800c527e  mov     [rsp+58h+ppv], rdi; ppv
0x1800c5283  lea     r9, _GUID_bb1a2ae1_a4f9_11cf_8f20_00805f2cd064; riid
0x1800c528a  xor     edx, edx; pUnkOuter
0x1800c528c  lea     r8d, [rdx+17h]; dwClsContext
0x1800c5290  lea     rcx, rclsid; rclsid
0x1800c5297  call    cs:__imp_CoCreateInstance
0x1800c529d  mov     ebx, eax
0x1800c529f  test    eax, eax
0x1800c52a1  js      loc_1800C5337
0x1800c52a7  mov     rcx, [rdi]
0x1800c52aa  mov     rax, [rcx]
0x1800c52ad  lea     r8, [rsi+10h]
0x1800c52b1  lea     rdx, _GUID_c7ef7658_e1ee_480e_97ea_d52cb4d76d17
0x1800c52b8  mov     rax, [rax]
0x1800c52bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c52c0  mov     ebx, eax
0x1800c52c2  test    eax, eax
0x1800c52c4  js      short loc_1800C5337
0x1800c52c6  mov     rcx, [rdi]
0x1800c52c9  mov     rax, [rcx]
0x1800c52cc  lea     r8, [rsp+58h+arg_0]
0x1800c52d1  lea     rdx, _GUID_cb5bdc81_93c1_11cf_8f20_00805f2cd064
0x1800c52d8  mov     rax, [rax]
0x1800c52db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c52e0  mov     ebx, eax
0x1800c52e2  test    eax, eax
0x1800c52e4  js      short loc_1800C5337
0x1800c52e6  mov     rcx, [rsp+58h+arg_0]
0x1800c52eb  mov     rax, [rcx]
0x1800c52ee  mov     r8d, 2
0x1800c52f4  mov     r9d, r8d
0x1800c52f7  lea     rdx, IID_IActiveScript
0x1800c52fe  mov     rax, [rax+20h]
0x1800c5302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5307  mov     ebx, eax
0x1800c5309  test    eax, eax
0x1800c530b  js      short loc_1800C5337
0x1800c530d  mov     rcx, [rsi+10h]
0x1800c5311  mov     rax, [rcx]
0x1800c5314  mov     rax, [rax+18h]
0x1800c5318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c531d  mov     ebx, eax
0x1800c531f  test    eax, eax
0x1800c5321  js      short loc_1800C5337
0x1800c5323  mov     rcx, [rdi]
0x1800c5326  mov     rax, [rcx]
0x1800c5329  mov     rdx, rsi
0x1800c532c  mov     rax, [rax+18h]
0x1800c5330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5335  mov     ebx, eax
0x1800c5337  lea     rcx, [rsp+58h+arg_0]
0x1800c533c  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x1800c5341  mov     eax, ebx
0x1800c5343  add     rsp, 38h
0x1800c5347  pop     r14
0x1800c5349  pop     rdi
0x1800c534a  pop     rsi
0x1800c534b  pop     rbx
0x1800c534c  retn
```
