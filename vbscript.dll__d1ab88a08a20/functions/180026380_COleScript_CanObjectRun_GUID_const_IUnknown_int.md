# COleScript::CanObjectRun(_GUID const &,IUnknown *,int)

- ea: `0x180026380`
- end: `0x1800264cf`
- name: `?CanObjectRun@COleScript@@QEAAHAEBU_GUID@@PEAUIUnknown@@H@Z`
- size: `335`
- prototype: `__int64 __fastcall(COleScript *__hidden this, const struct _GUID *, struct IUnknown *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002583c`

## callees

- `0x180026380`
- `0x180026570`
- `0x180055bbc`
- `0x180055e54`
- `0x180057c90`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLE32!CoTaskMemFree` at `0x18002648c`
- `OLE32!CoTaskMemFree` at `0x18002648c`

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
0x180026380  push    rbp
0x180026382  push    rbx
0x180026383  push    rsi
0x180026384  push    rdi
0x180026385  push    r14
0x180026387  mov     rbp, rsp
0x18002638a  sub     rsp, 80h
0x180026391  mov     rax, cs:__security_cookie
0x180026398  xor     rax, rsp
0x18002639b  mov     [rbp+var_8], rax
0x18002639f  mov     r14d, r9d
0x1800263a2  mov     rsi, r8
0x1800263a5  mov     rbx, rdx
0x1800263a8  mov     rdi, rcx
0x1800263ab  call    ?InSafeMode@COleScript@@QEAAHPEBU_GUID@@@Z; COleScript::InSafeMode(_GUID const *)
0x1800263b0  test    eax, eax
0x1800263b2  jnz     short loc_1800263BE
0x1800263b4  mov     eax, 1
0x1800263b9  jmp     loc_1800264B4
0x1800263be  test    byte ptr [rdi+2B0h], 8
0x1800263c5  jz      loc_1800264A6
0x1800263cb  lea     rdx, [rbp+var_38]; struct IInternetHostSecurityManager **
0x1800263cf  mov     [rbp+var_38], 0
0x1800263d7  mov     rcx, rdi; this
0x1800263da  call    ?GetSiteHostSecurityManagerNoRef@COleScript@@IEAAJPEAPEAUIInternetHostSecurityManager@@@Z; COleScript::GetSiteHostSecurityManagerNoRef(IInternetHostSecurityManager * *)
0x1800263df  test    eax, eax
0x1800263e1  js      loc_1800264A2
0x1800263e7  mov     rdi, [rbp+var_38]
0x1800263eb  mov     r8, rbx; struct _GUID *
0x1800263ee  mov     rdx, rdi; struct IInternetHostSecurityManager *
0x1800263f1  call    ?VerifyHostSecurityManager@COleScript@@IEAAHPEAUIInternetHostSecurityManager@@PEBU_GUID@@@Z; COleScript::VerifyHostSecurityManager(IInternetHostSecurityManager *,_GUID const *)
0x1800263f6  test    eax, eax
0x1800263f8  jz      loc_1800264A2
0x1800263fe  movups  xmm0, xmmword ptr [rbx]
0x180026401  xor     eax, eax
0x180026403  mov     qword ptr [rbp+var_28], 0
0x18002640b  mov     qword ptr [rbp+var_28+8], 0
0x180026413  lea     rcx, [rbp+var_28]
0x180026417  mov     [rbp+var_C], 0
0x18002641e  lea     r9, [rbp+var_40]
0x180026422  mov     [rbp+pv], 0
0x18002642a  lea     r8, [rbp+pv]
0x18002642e  mov     [rbp+var_40], 0
0x180026435  lea     rdx, GUID_CUSTOM_CONFIRMOBJECTSAFETY
0x18002643c  movdqu  [rbp+var_28], xmm0
0x180026441  mov     [rbp+var_18], rsi
0x180026445  test    r14d, r14d
0x180026448  mov     [rsp+80h+var_50], 0
0x180026450  setnz   al
0x180026453  mov     [rsp+80h+var_58], 20h ; ' '
0x18002645b  mov     [rbp+var_10], eax
0x18002645e  mov     rax, [rdi]
0x180026461  mov     [rsp+80h+var_60], rcx
0x180026466  mov     rcx, rdi
0x180026469  mov     rax, [rax+28h]
0x18002646d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026472  test    eax, eax
0x180026474  js      short loc_1800264A2
0x180026476  mov     rcx, [rbp+pv]; pv
0x18002647a  mov     ebx, 3
0x18002647f  test    rcx, rcx
0x180026482  jz      short loc_180026498
0x180026484  cmp     [rbp+var_40], 4
0x180026488  jb      short loc_18002648C
0x18002648a  mov     ebx, [rcx]
0x18002648c  call    cs:__imp_CoTaskMemFree
0x180026493  nop     dword ptr [rax+rax+00h]
0x180026498  xor     eax, eax
0x18002649a  test    bl, 0Fh
0x18002649d  setz    al
0x1800264a0  jmp     short loc_1800264B4
0x1800264a2  xor     eax, eax
0x1800264a4  jmp     short loc_1800264B4
0x1800264a6  mov     r9d, r14d; int
0x1800264a9  mov     r8, rsi; struct IUnknown *
0x1800264ac  mov     rdx, rbx; struct _GUID *
0x1800264af  call    ?IsObjectSafeForScripting@COleScript@@IEAAHAEBU_GUID@@PEAUIUnknown@@H@Z; COleScript::IsObjectSafeForScripting(_GUID const &,IUnknown *,int)
0x1800264b4  mov     rcx, [rbp+var_8]
0x1800264b8  xor     rcx, rsp; StackCookie
0x1800264bb  call    __security_check_cookie
0x1800264c0  add     rsp, 80h
0x1800264c7  pop     r14
0x1800264c9  pop     rdi
0x1800264ca  pop     rsi
0x1800264cb  pop     rbx
0x1800264cc  pop     rbp
0x1800264cd  retn
```
