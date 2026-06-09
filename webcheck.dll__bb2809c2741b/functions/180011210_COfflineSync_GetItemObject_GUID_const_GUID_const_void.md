# COfflineSync::GetItemObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180011210`
- end: `0x18001134c`
- name: `?GetItemObject@COfflineSync@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `316`
- prototype: `int(COfflineSync *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180011210`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `USER32!LoadStringW` at `0x18001129e`
- `USER32!LoadStringW` at `0x18001129e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180011274`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180011274`

## pseudocode

```c
__int64 __fastcall COfflineSync::GetItemObject(
        COfflineSync *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT v5; // edx
  __int64 v6; // rax
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int128 v10; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+30h] [rbp-D0h]
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = -2147467262;
  if ( a4 )
  {
    *a4 = 0;
    v6 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IPropertyStore.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IPropertyStore.Data1 )
      v6 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IPropertyStore.Data4;
    if ( !v6 )
    {
      v5 = PSCreateMemoryPropertyStore(a3, a4);
      if ( v5 >= 0 )
      {
        v7 = (__int64 *)*a4;
        if ( !LoadStringW(g_hinstMUI, 0x203Du, Buffer, 260)
          || (v11 = 0,
              *(_QWORD *)&v10 = 31,
              *((_QWORD *)&v10 + 1) = Buffer,
              v5 = (*(__int64 (__fastcall **)(__int64 *, const PROPERTYKEY *, __int128 *))(*v7 + 48))(
                     v7,
                     &PKEY_Sync_HandlerTypeLabel,
                     &v10),
              v5 >= 0) )
        {
          v11 = 0;
          v10 = 0;
          LOWORD(v10) = 19;
          v8 = *v7;
          DWORD2(v10) = 1;
          return (unsigned int)(*(__int64 (__fastcall **)(__int64 *, const PROPERTYKEY *, __int128 *))(v8 + 48))(
                                 v7,
                                 &PKEY_Sync_HandlerType,
                                 &v10);
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011210  mov     [rsp-8+arg_0], rbx
0x180011215  push    rbp
0x180011216  lea     rbp, [rsp-160h]
0x18001121e  sub     rsp, 260h
0x180011225  mov     rax, cs:__security_cookie
0x18001122c  xor     rax, rsp
0x18001122f  mov     [rbp+160h+var_10], rax
0x180011236  mov     rbx, r9
0x180011239  mov     edx, 80004002h
0x18001123e  test    r9, r9
0x180011241  jz      loc_18001132A
0x180011247  mov     qword ptr [r9], 0
0x18001124e  mov     rax, [r8]
0x180011251  sub     rax, qword ptr cs:IID_IPropertyStore.Data1
0x180011258  jnz     short loc_180011265
0x18001125a  mov     rax, [r8+8]
0x18001125e  sub     rax, qword ptr cs:IID_IPropertyStore.Data4
0x180011265  test    rax, rax
0x180011268  jnz     loc_18001132A
0x18001126e  mov     rdx, rbx; ppv
0x180011271  mov     rcx, r8; riid
0x180011274  call    cs:__imp_PSCreateMemoryPropertyStore
0x18001127a  mov     edx, eax
0x18001127c  test    eax, eax
0x18001127e  js      loc_18001132A
0x180011284  mov     rcx, cs:g_hinstMUI; hInstance
0x18001128b  lea     r8, [rsp+260h+Buffer]; lpBuffer
0x180011290  mov     rbx, [rbx]
0x180011293  mov     r9d, 104h; cchBufferMax
0x180011299  mov     edx, 203Dh; uID
0x18001129e  call    cs:__imp_LoadStringW
0x1800112a4  test    eax, eax
0x1800112a6  jz      short loc_1800112EC
0x1800112a8  xor     eax, eax
0x1800112aa  lea     r8, [rsp+260h+var_240]
0x1800112af  mov     [rsp+260h+var_230], rax
0x1800112b4  lea     rdx, PKEY_Sync_HandlerTypeLabel
0x1800112bb  xorps   xmm0, xmm0
0x1800112be  mov     eax, 1Fh
0x1800112c3  movups  [rsp+260h+var_240], xmm0
0x1800112c8  mov     word ptr [rsp+260h+var_240], ax
0x1800112cd  mov     rcx, rbx
0x1800112d0  lea     rax, [rsp+260h+Buffer]
0x1800112d5  mov     qword ptr [rsp+260h+var_240+8], rax
0x1800112da  mov     rax, [rbx]
0x1800112dd  mov     rax, [rax+30h]
0x1800112e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112e6  mov     edx, eax
0x1800112e8  test    eax, eax
0x1800112ea  js      short loc_18001132A
0x1800112ec  xor     eax, eax
0x1800112ee  lea     r8, [rsp+260h+var_240]
0x1800112f3  mov     [rsp+260h+var_230], rax
0x1800112f8  lea     rdx, PKEY_Sync_HandlerType
0x1800112ff  xorps   xmm0, xmm0
0x180011302  mov     eax, 13h
0x180011307  movups  [rsp+260h+var_240], xmm0
0x18001130c  mov     word ptr [rsp+260h+var_240], ax
0x180011311  mov     rcx, rbx
0x180011314  mov     rax, [rbx]
0x180011317  mov     dword ptr [rsp+260h+var_240+8], 1
0x18001131f  mov     rax, [rax+30h]
0x180011323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011328  mov     edx, eax
0x18001132a  mov     eax, edx
0x18001132c  mov     rcx, [rbp+160h+var_10]
0x180011333  xor     rcx, rsp; StackCookie
0x180011336  call    __security_check_cookie
0x18001133b  mov     rbx, [rsp+260h+arg_0]
0x180011343  add     rsp, 260h
0x18001134a  pop     rbp
0x18001134b  retn
```
