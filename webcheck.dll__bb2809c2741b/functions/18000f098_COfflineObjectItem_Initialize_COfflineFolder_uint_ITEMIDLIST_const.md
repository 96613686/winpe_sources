# COfflineObjectItem::Initialize(COfflineFolder *,uint,_ITEMIDLIST const * *)

- ea: `0x18000f098`
- end: `0x18000f2b2`
- name: `?Initialize@COfflineObjectItem@@QEAAJPEAVCOfflineFolder@@IPEAPEFBU_ITEMIDLIST@@@Z`
- size: `538`
- prototype: `__int64 __fastcall(COfflineObjectItem *__hidden this, struct COfflineFolder *, unsigned int, const struct _ITEMIDLIST **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e9c8`

## callees

- `0x180003950`
- `0x18000f098`
- `0x180029280`
- `0x180029310`
- `0x18002a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000f0e1`
- `KERNEL32!LocalAlloc` at `0x18000f0e1`
- `KERNEL32!LocalFree` at `0x18000f153`
- `KERNEL32!LocalFree` at `0x18000f153`
- `ole32!CoCreateInstance` at `0x18000f1b7`
- `ole32!CoCreateInstance` at `0x18000f1b7`
- `ole32!CoUninitialize` at `0x18000f289`
- `ole32!CoUninitialize` at `0x18000f289`
- `ole32!CoInitialize` at `0x18000f181`
- `ole32!CoInitialize` at `0x18000f181`
- `SHELL32!__imp_ILClone` at `0x18000f109`
- `SHELL32!__imp_ILClone` at `0x18000f109`
- `SHELL32!__imp_ILFree` at `0x18000f135`
- `SHELL32!__imp_ILFree` at `0x18000f135`

## pseudocode

```c
__int64 __fastcall COfflineObjectItem::Initialize(
        COfflineObjectItem *this,
        struct COfflineFolder *a2,
        unsigned int a3,
        const struct _ITEMIDLIST **a4)
{
  HLOCAL v8; // rax
  __int64 i; // rsi
  __int64 j; // r14
  __int64 v12; // rbx
  LPVOID *ppv; // rdi
  int (__fastcall ***v14)(LPVOID, GUID *, __int64 *); // rcx
  const unsigned __int16 *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+38h] [rbp-C8h] BYREF
  IID rclsid; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v20[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v21[2088]; // [rsp+270h] [rbp+170h] BYREF

  v8 = LocalAlloc(0x40u, 8LL * a3);
  *((_QWORD *)this + 8) = v8;
  if ( !v8 )
    return 2147942414LL;
  *((_DWORD *)this + 14) = a3;
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
  {
    *(_QWORD *)(*((_QWORD *)this + 8) + 8 * i) = ILClone(a4[i]);
    if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 8 * i) )
    {
      for ( j = 0; (unsigned int)j < (unsigned int)i; j = (unsigned int)(j + 1) )
      {
        ILFree(*(LPITEMIDLIST *)(*((_QWORD *)this + 8) + 8 * j));
        *(_QWORD *)(*((_QWORD *)this + 8) + 8 * j) = 0;
      }
      LocalFree(*((HLOCAL *)this + 8));
      return 2147942414LL;
    }
  }
  *((_QWORD *)this + 6) = a2;
  (*(void (__fastcall **)(struct COfflineFolder *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( *((_DWORD *)this + 14) == 1 )
  {
    v12 = **((_QWORD **)this + 8);
    if ( CoInitialize(0) >= 0 )
    {
      ppv = (LPVOID *)((char *)this + 72);
      rclsid = *(IID *)(v12 + 164);
      if ( CoCreateInstance(&rclsid, 0, 1u, &IID_IUnknown, ppv) >= 0 )
      {
        v14 = (int (__fastcall ***)(LPVOID, GUID *, __int64 *))*ppv;
        v17 = 0;
        if ( (**v14)(v14, &IID_ISubscriptionAgentShellExt, &v17) >= 0 )
        {
          v15 = (const unsigned __int16 *)(v12 + *(_QWORD *)(v12 + 200) + 8LL);
          v18 = 0;
          StringCchCopyW(v21, 0x825u, v15);
          StringCchCopyW(v20, 0x105u, (const unsigned __int16 *)(v12 + *(_QWORD *)(v12 + 208) + 8LL));
          v18 = *(_OWORD *)(v12 + 128);
          (*(void (__fastcall **)(__int64, __int128 *, unsigned __int16 *, unsigned __int16 *, int))(*(_QWORD *)v17 + 24LL))(
            v17,
            &v18,
            v21,
            v20,
            -1);
          v16 = v17;
          *(_OWORD *)(v12 + 128) = v18;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      CoUninitialize();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f098  push    rbp
0x18000f09a  push    rbx
0x18000f09b  push    rsi
0x18000f09c  push    rdi
0x18000f09d  push    r12
0x18000f09f  push    r14
0x18000f0a1  push    r15
0x18000f0a3  lea     rbp, [rsp-11D0h]
0x18000f0ab  mov     eax, 12D0h
0x18000f0b0  call    _alloca_probe
0x18000f0b5  sub     rsp, rax
0x18000f0b8  mov     rax, cs:__security_cookie
0x18000f0bf  xor     rax, rsp
0x18000f0c2  mov     [rbp+1200h+var_40], rax
0x18000f0c9  mov     r14, rdx
0x18000f0cc  mov     r15d, r8d
0x18000f0cf  mov     edx, r8d
0x18000f0d2  mov     rdi, rcx
0x18000f0d5  shl     rdx, 3; uBytes
0x18000f0d9  mov     ecx, 40h ; '@'; uFlags
0x18000f0de  mov     r12, r9
0x18000f0e1  call    cs:__imp_LocalAlloc
0x18000f0e7  mov     [rdi+40h], rax
0x18000f0eb  test    rax, rax
0x18000f0ee  jnz     short loc_18000F0FA
0x18000f0f0  mov     eax, 8007000Eh
0x18000f0f5  jmp     loc_18000F291
0x18000f0fa  mov     [rdi+38h], r15d
0x18000f0fe  xor     esi, esi
0x18000f100  cmp     esi, r15d
0x18000f103  jnb     short loc_18000F15B
0x18000f105  mov     rcx, [r12+rsi*8]; pidl
0x18000f109  call    cs:__imp_ILClone
0x18000f10f  mov     rcx, [rdi+40h]
0x18000f113  mov     [rcx+rsi*8], rax
0x18000f117  mov     rax, [rdi+40h]
0x18000f11b  cmp     qword ptr [rax+rsi*8], 0
0x18000f120  jz      short loc_18000F126
0x18000f122  inc     esi
0x18000f124  jmp     short loc_18000F100
0x18000f126  xor     r14d, r14d
0x18000f129  test    esi, esi
0x18000f12b  jz      short loc_18000F14F
0x18000f12d  mov     rcx, [rdi+40h]
0x18000f131  mov     rcx, [rcx+r14*8]; pidl
0x18000f135  call    cs:__imp_ILFree
0x18000f13b  mov     rax, [rdi+40h]
0x18000f13f  mov     qword ptr [rax+r14*8], 0
0x18000f147  inc     r14d
0x18000f14a  cmp     r14d, esi
0x18000f14d  jb      short loc_18000F12D
0x18000f14f  mov     rcx, [rdi+40h]; hMem
0x18000f153  call    cs:__imp_LocalFree
0x18000f159  jmp     short loc_18000F0F0
0x18000f15b  mov     [rdi+30h], r14
0x18000f15f  mov     rcx, r14
0x18000f162  mov     rax, [r14]
0x18000f165  mov     rax, [rax+8]
0x18000f169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f16e  cmp     dword ptr [rdi+38h], 1
0x18000f172  jnz     loc_18000F28F
0x18000f178  mov     rax, [rdi+40h]
0x18000f17c  xor     ecx, ecx; pvReserved
0x18000f17e  mov     rbx, [rax]
0x18000f181  call    cs:__imp_CoInitialize
0x18000f187  test    eax, eax
0x18000f189  js      loc_18000F28F
0x18000f18f  movups  xmm0, xmmword ptr [rbx+0A4h]
0x18000f196  xor     edx, edx; pUnkOuter
0x18000f198  lea     r9, IID_IUnknown; riid
0x18000f19f  add     rdi, 48h ; 'H'
0x18000f1a3  lea     rcx, [rsp+1300h+rclsid]; rclsid
0x18000f1a8  movdqu  xmmword ptr [rsp+1300h+rclsid.Data1], xmm0
0x18000f1ae  mov     [rsp+1300h+ppv], rdi; ppv
0x18000f1b3  lea     r8d, [rdx+1]; dwClsContext
0x18000f1b7  call    cs:__imp_CoCreateInstance
0x18000f1bd  test    eax, eax
0x18000f1bf  js      loc_18000F289
0x18000f1c5  mov     rcx, [rdi]
0x18000f1c8  lea     r8, [rsp+1300h+var_12D0]
0x18000f1cd  mov     [rsp+1300h+var_12D0], 0
0x18000f1d6  lea     rdx, IID_ISubscriptionAgentShellExt
0x18000f1dd  mov     rax, [rcx]
0x18000f1e0  mov     rax, [rax]
0x18000f1e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1e8  test    eax, eax
0x18000f1ea  js      loc_18000F289
0x18000f1f0  mov     r8, [rbx+0C8h]
0x18000f1f7  lea     rcx, [rbp+1200h+var_1090]; unsigned __int16 *
0x18000f1fe  add     r8, 8
0x18000f202  xorps   xmm0, xmm0
0x18000f205  add     r8, rbx; unsigned __int16 *
0x18000f208  mov     edx, 825h; unsigned __int64
0x18000f20d  movups  [rsp+1300h+var_12C8], xmm0
0x18000f212  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f217  mov     r8, [rbx+0D0h]
0x18000f21e  lea     rcx, [rsp+1300h+var_12A0]; unsigned __int16 *
0x18000f223  add     r8, 8
0x18000f227  mov     edx, 105h; unsigned __int64
0x18000f22c  add     r8, rbx; unsigned __int16 *
0x18000f22f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f234  mov     rcx, [rsp+1300h+var_12D0]
0x18000f239  lea     r9, [rsp+1300h+var_12A0]
0x18000f23e  movups  xmm0, xmmword ptr [rbx+80h]
0x18000f245  lea     r8, [rbp+1200h+var_1090]
0x18000f24c  mov     dword ptr [rsp+1300h+ppv], 0FFFFFFFFh
0x18000f254  lea     rdx, [rsp+1300h+var_12C8]
0x18000f259  movdqu  [rsp+1300h+var_12C8], xmm0
0x18000f25f  mov     rax, [rcx]
0x18000f262  mov     rax, [rax+18h]
0x18000f266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f26b  movups  xmm0, [rsp+1300h+var_12C8]
0x18000f270  mov     rcx, [rsp+1300h+var_12D0]
0x18000f275  movdqu  xmmword ptr [rbx+80h], xmm0
0x18000f27d  mov     rax, [rcx]
0x18000f280  mov     rax, [rax+10h]
0x18000f284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f289  call    cs:__imp_CoUninitialize
0x18000f28f  xor     eax, eax
0x18000f291  mov     rcx, [rbp+1200h+var_40]
0x18000f298  xor     rcx, rsp; StackCookie
0x18000f29b  call    __security_check_cookie
0x18000f2a0  add     rsp, 12D0h
0x18000f2a7  pop     r15
0x18000f2a9  pop     r14
0x18000f2ab  pop     r12
0x18000f2ad  pop     rdi
0x18000f2ae  pop     rsi
0x18000f2af  pop     rbx
0x18000f2b0  pop     rbp
0x18000f2b1  retn
```
