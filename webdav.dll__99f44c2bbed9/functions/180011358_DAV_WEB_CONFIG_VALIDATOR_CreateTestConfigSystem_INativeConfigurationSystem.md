# DAV_WEB_CONFIG_VALIDATOR::CreateTestConfigSystem(INativeConfigurationSystem * *)

- ea: `0x180011358`
- end: `0x18001150c`
- name: `?CreateTestConfigSystem@DAV_WEB_CONFIG_VALIDATOR@@AEAAJPEAPEAVINativeConfigurationSystem@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(DAV_WEB_CONFIG_VALIDATOR *__hidden this, struct INativeConfigurationSystem **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011cf8`

## callees

- `0x180011358`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800113b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800113b6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011393`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011393`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011496`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800114e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011496`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800114e0`

## pseudocode

```c
__int64 __fastcall DAV_WEB_CONFIG_VALIDATOR::CreateTestConfigSystem(
        DAV_WEB_CONFIG_VALIDATOR *this,
        struct INativeConfigurationSystem **a2)
{
  HRESULT v4; // ebx
  LPVOID v5; // rcx
  _WORD *v6; // r8
  LPVOID ppv; // [rsp+30h] [rbp-50h] BYREF
  struct INativeConfigurationSystem *v9; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v10[56]; // [rsp+40h] [rbp-40h] BYREF

  ppv = 0;
  v9 = 0;
  STRU::STRU((STRU *)v10);
  v4 = CoCreateInstance(
         &GUID_2b72133b_3f5b_4602_8952_803546ce3344,
         0,
         1u,
         &GUID_fa7660f6_7b3f_4237_a8bf_ed0ad0dcbbd9,
         &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv + 72LL))(ppv, &Src);
    if ( v4 >= 0 )
      v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct INativeConfigurationSystem **))ppv)(
             ppv,
             &IID_INativeConfigurationSystem,
             &v9);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v5 = 0;
    ppv = 0;
    if ( v4 < 0 )
      goto LABEL_11;
    v6 = (_WORD *)(*((_QWORD *)DAV_STATIC_CONFIG::sm_StaticConfig + 11)
                 & -(__int64)(**((_WORD **)DAV_STATIC_CONFIG::sm_StaticConfig + 11) != 0));
    if ( !v6
      || !*v6
      || (v4 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, _WORD *, __int64))(*(_QWORD *)v9 + 64LL))(
                 v9,
                 L"MACHINE/WEBROOT/APPHOST",
                 v6,
                 3),
          v4 >= 0) )
    {
      v4 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 64LL))(
             v9,
             *((_QWORD *)this + 24),
             *((_QWORD *)this + 17),
             *((unsigned int *)this + 54));
      if ( v4 >= 0 )
      {
        *a2 = v9;
        STRU::~STRU((STRU *)v10);
        return 0;
      }
    }
  }
  v5 = ppv;
LABEL_11:
  if ( v9 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v9 + 16LL))(v9);
    v5 = ppv;
    v9 = 0;
  }
  if ( v5 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    ppv = 0;
  }
  *a2 = 0;
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180011358  mov     [rsp-18h+arg_10], rbx
0x18001135d  mov     [rsp-18h+arg_18], rsi
0x180011362  push    rbp
0x180011363  push    rdi
0x180011364  push    r14
0x180011366  mov     rbp, rsp
0x180011369  sub     rsp, 80h
0x180011370  mov     rax, cs:__security_cookie
0x180011377  xor     rax, rsp
0x18001137a  mov     [rbp+var_8], rax
0x18001137e  mov     rsi, rcx
0x180011381  xor     r14d, r14d
0x180011384  lea     rcx, [rbp+var_40]
0x180011388  mov     [rbp+var_50], r14
0x18001138c  mov     [rbp+var_48], r14
0x180011390  mov     rdi, rdx
0x180011393  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011399  lea     rax, [rbp+var_50]
0x18001139d  xor     edx, edx; pUnkOuter
0x18001139f  lea     r9, _GUID_fa7660f6_7b3f_4237_a8bf_ed0ad0dcbbd9; riid
0x1800113a6  mov     [rsp+80h+ppv], rax; ppv
0x1800113ab  lea     r8d, [r14+1]; dwClsContext
0x1800113af  lea     rcx, _GUID_2b72133b_3f5b_4602_8952_803546ce3344; rclsid
0x1800113b6  call    cs:__imp_CoCreateInstance
0x1800113bc  mov     ebx, eax
0x1800113be  test    eax, eax
0x1800113c0  js      loc_1800114A0
0x1800113c6  mov     rcx, [rbp+var_50]
0x1800113ca  lea     rdx, Src
0x1800113d1  mov     rax, [rcx]
0x1800113d4  mov     rax, [rax+48h]
0x1800113d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113dd  mov     ebx, eax
0x1800113df  test    eax, eax
0x1800113e1  js      short loc_1800113FF
0x1800113e3  mov     rcx, [rbp+var_50]
0x1800113e7  lea     r8, [rbp+var_48]
0x1800113eb  lea     rdx, IID_INativeConfigurationSystem
0x1800113f2  mov     rax, [rcx]
0x1800113f5  mov     rax, [rax]
0x1800113f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113fd  mov     ebx, eax
0x1800113ff  mov     rcx, [rbp+var_50]
0x180011403  mov     rax, [rcx]
0x180011406  mov     rax, [rax+10h]
0x18001140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001140f  mov     rcx, r14
0x180011412  mov     [rbp+var_50], rcx
0x180011416  test    ebx, ebx
0x180011418  js      loc_1800114A4
0x18001141e  mov     rax, cs:?sm_StaticConfig@DAV_STATIC_CONFIG@@0PEAV1@EA; DAV_STATIC_CONFIG * DAV_STATIC_CONFIG::sm_StaticConfig
0x180011425  mov     rcx, [rax+58h]
0x180011429  movzx   eax, word ptr [rcx]
0x18001142c  neg     ax
0x18001142f  sbb     r8, r8
0x180011432  and     r8, rcx
0x180011435  jz      short loc_180011460
0x180011437  cmp     [r8], r14w
0x18001143b  jz      short loc_180011460
0x18001143d  mov     rcx, [rbp+var_48]
0x180011441  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180011448  mov     r9d, 3
0x18001144e  mov     rax, [rcx]
0x180011451  mov     rax, [rax+40h]
0x180011455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001145a  mov     ebx, eax
0x18001145c  test    eax, eax
0x18001145e  js      short loc_1800114A0
0x180011460  mov     rcx, [rbp+var_48]
0x180011464  mov     r9d, [rsi+0D8h]
0x18001146b  mov     r8, [rsi+88h]
0x180011472  mov     rdx, [rsi+0C0h]
0x180011479  mov     rax, [rcx]
0x18001147c  mov     rax, [rax+40h]
0x180011480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011485  mov     ebx, eax
0x180011487  test    eax, eax
0x180011489  js      short loc_1800114A0
0x18001148b  mov     rax, [rbp+var_48]
0x18001148f  lea     rcx, [rbp+var_40]
0x180011493  mov     [rdi], rax
0x180011496  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001149c  xor     eax, eax
0x18001149e  jmp     short loc_1800114E8
0x1800114a0  mov     rcx, [rbp+var_50]
0x1800114a4  mov     rdx, [rbp+var_48]
0x1800114a8  test    rdx, rdx
0x1800114ab  jz      short loc_1800114C4
0x1800114ad  mov     rax, [rdx]
0x1800114b0  mov     rcx, rdx
0x1800114b3  mov     rax, [rax+10h]
0x1800114b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114bc  mov     rcx, [rbp+var_50]
0x1800114c0  mov     [rbp+var_48], r14
0x1800114c4  test    rcx, rcx
0x1800114c7  jz      short loc_1800114D9
0x1800114c9  mov     rax, [rcx]
0x1800114cc  mov     rax, [rax+10h]
0x1800114d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114d5  mov     [rbp+var_50], r14
0x1800114d9  lea     rcx, [rbp+var_40]
0x1800114dd  mov     [rdi], r14
0x1800114e0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800114e6  mov     eax, ebx
0x1800114e8  mov     rcx, [rbp+var_8]
0x1800114ec  xor     rcx, rsp; StackCookie
0x1800114ef  call    __security_check_cookie
0x1800114f4  lea     r11, [rsp+80h+var_s0]
0x1800114fc  mov     rbx, [r11+30h]
0x180011500  mov     rsi, [r11+38h]
0x180011504  mov     rsp, r11
0x180011507  pop     r14
0x180011509  pop     rdi
0x18001150a  pop     rbp
0x18001150b  retn
```
