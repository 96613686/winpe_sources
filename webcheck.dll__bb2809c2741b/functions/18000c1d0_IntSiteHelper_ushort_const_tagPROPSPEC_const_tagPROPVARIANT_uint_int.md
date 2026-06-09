# IntSiteHelper(ushort const *,tagPROPSPEC const *,tagPROPVARIANT *,uint,int)

- ea: `0x18000c1d0`
- end: `0x18000c322`
- name: `?IntSiteHelper@@YAJPEBGPEBUtagPROPSPEC@@PEAUtagPROPVARIANT@@IH@Z`
- size: `338`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct tagPROPSPEC *, struct tagPROPVARIANT *, unsigned int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000501c`
- `0x180007370`
- `0x18000cc84`
- `0x18000dd40`

## callees

- `0x18000c1d0`
- `0x18002a010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x18000c21b`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18000c21b`

## pseudocode

```c
__int64 __fastcall IntSiteHelper(
        const unsigned __int16 *a1,
        const struct tagPROPSPEC *a2,
        struct tagPROPVARIANT *a3,
        __int64 a4,
        int a5)
{
  HRESULT v8; // ebx
  __int64 v9; // rax
  __int64 *v11; // [rsp+30h] [rbp-20h] BYREF
  void *ppv; // [rsp+38h] [rbp-18h] BYREF
  __int64 v13; // [rsp+40h] [rbp-10h] BYREF

  ppv = 0;
  v13 = 0;
  v11 = 0;
  v8 = SHCoCreateInstance(0, &CLSID_InternetShortcut, 0, &IID_IUniformResourceLocatorW, &ppv);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(void *, const unsigned __int16 *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, a1, 0);
    if ( v8 >= 0 )
    {
      v8 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(ppv, &IID_IPropertySetStorage, &v13);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64, __int64 **))(*(_QWORD *)v13 + 32LL))(
               v13,
               &FMTID_InternetSite,
               2,
               &v11);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        if ( v8 >= 0 )
        {
          v9 = *v11;
          if ( a5 )
          {
            v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, const struct tagPROPSPEC *, struct tagPROPVARIANT *, _DWORD))(v9 + 32))(
                   v11,
                   1,
                   a2,
                   a3,
                   0);
            (*(void (__fastcall **)(__int64 *, _QWORD))(*v11 + 72))(v11, 0);
          }
          else
          {
            v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, const struct tagPROPSPEC *, struct tagPROPVARIANT *))(v9 + 24))(
                   v11,
                   1,
                   a2,
                   a3);
          }
          (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
        }
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000c1d0  push    rbp
0x18000c1d2  push    rbx
0x18000c1d3  push    rsi
0x18000c1d4  push    rdi
0x18000c1d5  push    r14
0x18000c1d7  mov     rbp, rsp
0x18000c1da  sub     rsp, 50h
0x18000c1de  mov     rsi, r8
0x18000c1e1  mov     [rbp+var_18], 0
0x18000c1e9  mov     r14, rdx
0x18000c1ec  mov     [rbp+var_10], 0
0x18000c1f4  mov     rdi, rcx
0x18000c1f7  mov     [rbp+var_20], 0
0x18000c1ff  lea     rax, [rbp+var_18]
0x18000c203  xor     r8d, r8d; pUnkOuter
0x18000c206  lea     rdx, CLSID_InternetShortcut; pclsid
0x18000c20d  mov     [rsp+50h+ppv], rax; ppv
0x18000c212  xor     ecx, ecx; pszCLSID
0x18000c214  lea     r9, IID_IUniformResourceLocatorW; riid
0x18000c21b  call    cs:__imp_SHCoCreateInstance
0x18000c221  mov     ebx, eax
0x18000c223  test    eax, eax
0x18000c225  js      loc_18000C300
0x18000c22b  mov     rcx, [rbp+var_18]
0x18000c22f  xor     r8d, r8d
0x18000c232  mov     rdx, rdi
0x18000c235  mov     rax, [rcx]
0x18000c238  mov     rax, [rax+18h]
0x18000c23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c241  mov     ebx, eax
0x18000c243  test    eax, eax
0x18000c245  js      loc_18000C300
0x18000c24b  mov     rcx, [rbp+var_18]
0x18000c24f  lea     r8, [rbp+var_10]
0x18000c253  lea     rdx, IID_IPropertySetStorage
0x18000c25a  mov     rax, [rcx]
0x18000c25d  mov     rax, [rax]
0x18000c260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c265  mov     ebx, eax
0x18000c267  test    eax, eax
0x18000c269  js      loc_18000C300
0x18000c26f  mov     rcx, [rbp+var_10]
0x18000c273  lea     r9, [rbp+var_20]
0x18000c277  mov     r8d, 2
0x18000c27d  lea     rdx, FMTID_InternetSite
0x18000c284  mov     rax, [rcx]
0x18000c287  mov     rax, [rax+20h]
0x18000c28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c290  mov     rcx, [rbp+var_10]
0x18000c294  mov     ebx, eax
0x18000c296  mov     rax, [rcx]
0x18000c299  mov     rax, [rax+10h]
0x18000c29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a2  test    ebx, ebx
0x18000c2a4  js      short loc_18000C300
0x18000c2a6  cmp     [rbp+arg_20], 0
0x18000c2aa  mov     r9, rsi
0x18000c2ad  mov     rcx, [rbp+var_20]
0x18000c2b1  mov     r8, r14
0x18000c2b4  mov     edx, 1
0x18000c2b9  mov     rax, [rcx]
0x18000c2bc  jz      short loc_18000C2E5
0x18000c2be  mov     rax, [rax+20h]
0x18000c2c2  mov     dword ptr [rsp+50h+ppv], 0
0x18000c2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2cf  mov     rcx, [rbp+var_20]
0x18000c2d3  mov     ebx, eax
0x18000c2d5  xor     edx, edx
0x18000c2d7  mov     rax, [rcx]
0x18000c2da  mov     rax, [rax+48h]
0x18000c2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2e3  jmp     short loc_18000C2F0
0x18000c2e5  mov     rax, [rax+18h]
0x18000c2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ee  mov     ebx, eax
0x18000c2f0  mov     rcx, [rbp+var_20]
0x18000c2f4  mov     rax, [rcx]
0x18000c2f7  mov     rax, [rax+10h]
0x18000c2fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c300  mov     rcx, [rbp+var_18]
0x18000c304  test    rcx, rcx
0x18000c307  jz      short loc_18000C315
0x18000c309  mov     rax, [rcx]
0x18000c30c  mov     rax, [rax+10h]
0x18000c310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c315  mov     eax, ebx
0x18000c317  add     rsp, 50h
0x18000c31b  pop     r14
0x18000c31d  pop     rdi
0x18000c31e  pop     rsi
0x18000c31f  pop     rbx
0x18000c320  pop     rbp
0x18000c321  retn
```
