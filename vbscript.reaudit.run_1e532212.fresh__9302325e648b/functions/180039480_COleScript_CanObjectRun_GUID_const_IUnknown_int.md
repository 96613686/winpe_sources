# COleScript::CanObjectRun(_GUID const &,IUnknown *,int)

- ea: `0x180039480`
- end: `0x1800395c8`
- name: `?CanObjectRun@COleScript@@QEAAHAEBU_GUID@@PEAUIUnknown@@H@Z`
- size: `328`
- prototype: `__int64 __fastcall(COleScript *__hidden this, const struct _GUID *, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003a30`

## callees

- `0x180039480`
- `0x180039668`
- `0x1800542c4`
- `0x18005454c`
- `0x1800562f0`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18003958c`
- `OLE32!CoTaskMemFree` at `0x18003958c`

## pseudocode

```c
__int64 __fastcall COleScript::CanObjectRun(COleScript *this, const struct _GUID *a2, struct IUnknown *a3, int a4)
{
  COleScript *v8; // rcx
  COleScript *v10; // rcx
  struct IInternetHostSecurityManager *v11; // rdi
  struct _GUID v12; // xmm0
  int v13; // ebx
  unsigned int v14; // [rsp+40h] [rbp-40h] BYREF
  struct IInternetHostSecurityManager *v15; // [rsp+48h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID v17; // [rsp+58h] [rbp-28h] BYREF
  struct IUnknown *v18; // [rsp+68h] [rbp-18h]
  BOOL v19; // [rsp+70h] [rbp-10h]
  int v20; // [rsp+74h] [rbp-Ch]

  if ( !(unsigned int)COleScript::InSafeMode(this, a2) )
    return 1;
  if ( (*((_BYTE *)this + 688) & 8) == 0 )
    return COleScript::IsObjectSafeForScripting(v8, a2, a3, a4);
  v15 = 0;
  if ( (int)COleScript::GetSiteHostSecurityManagerNoRef(this, &v15) < 0 )
    return 0;
  v11 = v15;
  if ( !(unsigned int)COleScript::VerifyHostSecurityManager(v10, v15, a2) )
    return 0;
  v12 = *a2;
  v20 = 0;
  pv = 0;
  v14 = 0;
  v17 = v12;
  v18 = a3;
  v19 = a4 != 0;
  if ( ((int (__fastcall *)(struct IInternetHostSecurityManager *, GUID *, LPVOID *, unsigned int *, struct _GUID *, int, _DWORD))v11->lpVtbl->QueryCustomPolicy)(
         v11,
         &GUID_CUSTOM_CONFIRMOBJECTSAFETY,
         &pv,
         &v14,
         &v17,
         32,
         0) < 0 )
    return 0;
  LOBYTE(v13) = 3;
  if ( pv )
  {
    if ( v14 >= 4 )
      v13 = *(_DWORD *)pv;
    CoTaskMemFree(pv);
  }
  return (v13 & 0xF) == 0;
}

```

## disassembly

```asm
0x180039480  push    rbp
0x180039482  push    rbx
0x180039483  push    rsi
0x180039484  push    rdi
0x180039485  push    r14
0x180039487  mov     rbp, rsp
0x18003948a  sub     rsp, 80h
0x180039491  mov     rax, cs:__security_cookie
0x180039498  xor     rax, rsp
0x18003949b  mov     [rbp+var_8], rax
0x18003949f  mov     r14d, r9d
0x1800394a2  mov     rsi, r8
0x1800394a5  mov     rbx, rdx
0x1800394a8  mov     rdi, rcx
0x1800394ab  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x1800394b0  test    eax, eax
0x1800394b2  jnz     short loc_1800394BE
0x1800394b4  mov     eax, 1
0x1800394b9  jmp     loc_1800395AE
0x1800394be  test    byte ptr [rdi+2B0h], 8
0x1800394c5  jz      loc_1800395A0
0x1800394cb  lea     rdx, [rbp+var_38]; struct IInternetHostSecurityManager **
0x1800394cf  mov     [rbp+var_38], 0
0x1800394d7  mov     rcx, rdi; this
0x1800394da  call    ?GetSiteHostSecurityManagerNoRef@COleScript@@IEAAJPEAPEAUIInternetHostSecurityManager@@@Z; COleScript::GetSiteHostSecurityManagerNoRef(IInternetHostSecurityManager * *)
0x1800394df  test    eax, eax
0x1800394e1  js      loc_18003959C
0x1800394e7  mov     rdi, [rbp+var_38]
0x1800394eb  mov     r8, rbx; struct _GUID *
0x1800394ee  mov     rdx, rdi; struct IInternetHostSecurityManager *
0x1800394f1  call    ?VerifyHostSecurityManager@COleScript@@IEAAHPEAUIInternetHostSecurityManager@@PEBU_GUID@@@Z; COleScript::VerifyHostSecurityManager(IInternetHostSecurityManager *,_GUID const *)
0x1800394f6  test    eax, eax
0x1800394f8  jz      loc_18003959C
0x1800394fe  movups  xmm0, xmmword ptr [rbx]
0x180039501  xor     eax, eax
0x180039503  mov     qword ptr [rbp+var_28], 0
0x18003950b  mov     qword ptr [rbp+var_28+8], 0
0x180039513  lea     rcx, [rbp+var_28]
0x180039517  mov     [rbp+var_C], 0
0x18003951e  lea     r9, [rbp+var_40]
0x180039522  mov     [rbp+pv], 0
0x18003952a  lea     r8, [rbp+pv]
0x18003952e  mov     [rbp+var_40], 0
0x180039535  lea     rdx, GUID_CUSTOM_CONFIRMOBJECTSAFETY
0x18003953c  movdqu  [rbp+var_28], xmm0
0x180039541  mov     [rbp+var_18], rsi
0x180039545  test    r14d, r14d
0x180039548  mov     [rsp+80h+var_50], 0
0x180039550  setnz   al
0x180039553  mov     [rsp+80h+var_58], 20h ; ' '
0x18003955b  mov     [rbp+var_10], eax
0x18003955e  mov     rax, [rdi]
0x180039561  mov     [rsp+80h+var_60], rcx
0x180039566  mov     rcx, rdi
0x180039569  mov     rax, [rax+28h]
0x18003956d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039572  test    eax, eax
0x180039574  js      short loc_18003959C
0x180039576  mov     rcx, [rbp+pv]; pv
0x18003957a  mov     ebx, 3
0x18003957f  test    rcx, rcx
0x180039582  jz      short loc_180039592
0x180039584  cmp     [rbp+var_40], 4
0x180039588  jb      short loc_18003958C
0x18003958a  mov     ebx, [rcx]
0x18003958c  call    cs:__imp_CoTaskMemFree
0x180039592  xor     eax, eax
0x180039594  test    bl, 0Fh
0x180039597  setz    al
0x18003959a  jmp     short loc_1800395AE
0x18003959c  xor     eax, eax
0x18003959e  jmp     short loc_1800395AE
0x1800395a0  mov     r9d, r14d; int
0x1800395a3  mov     r8, rsi; struct IUnknown *
0x1800395a6  mov     rdx, rbx; struct _GUID *
0x1800395a9  call    ?IsObjectSafeForScripting@COleScript@@IEAAHAEBU_GUID@@PEAUIUnknown@@H@Z; COleScript::IsObjectSafeForScripting(_GUID const &,IUnknown *,int)
0x1800395ae  mov     rcx, [rbp+var_8]
0x1800395b2  xor     rcx, rsp; StackCookie
0x1800395b5  call    __security_check_cookie
0x1800395ba  add     rsp, 80h
0x1800395c1  pop     r14
0x1800395c3  pop     rdi
0x1800395c4  pop     rsi
0x1800395c5  pop     rbx
0x1800395c6  pop     rbp
0x1800395c7  retn
```
