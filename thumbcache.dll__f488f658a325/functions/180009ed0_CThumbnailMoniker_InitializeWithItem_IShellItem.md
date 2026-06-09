# CThumbnailMoniker::InitializeWithItem(IShellItem *)

- ea: `0x180009ed0`
- end: `0x18000a215`
- name: `?InitializeWithItem@CThumbnailMoniker@@QEAAJPEAUIShellItem@@@Z`
- size: `837`
- prototype: `__int64 __fastcall(CThumbnailMoniker *__hidden this, struct IShellItem *)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014ae0`
- `0x18002e470`
- `0x180041040`

## callees

- `0x180003624`
- `0x1800085c0`
- `0x1800089e8`
- `0x180009ed0`
- `0x180035830`
- `0x1800364ac`
- `0x180049010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000a0d8`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x18000a0d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a110`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a14c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a110`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a14c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a04c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a04c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a021`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000a021`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CThumbnailMoniker::InitializeWithItem(CThumbnailMoniker *this, struct IShellItem *a2)
{
  unsigned __int64 v4; // r12
  unsigned __int16 *v5; // r14
  HRESULT (__stdcall *QueryInterface)(IShellItem *, const IID *const, void **); // rbx
  int v7; // esi
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, PROPERTYKEY *, __int64, __int64, GUID *, struct IPropertyStore **); // rbx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rax
  int v12; // edi
  unsigned __int16 *v13; // rbx
  void *v14; // rcx
  void *v15; // rcx
  struct IPropertyStore *v16; // rcx
  unsigned __int16 *v18; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int64 v19; // [rsp+48h] [rbp-61h] BYREF
  PROPERTYKEY v20; // [rsp+50h] [rbp-59h] BYREF
  struct IPropertyStore *v21; // [rsp+70h] [rbp-39h] BYREF
  __int64 v22; // [rsp+78h] [rbp-31h] BYREF
  PROPVARIANT pvar; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v24; // [rsp+88h] [rbp-21h]
  PROPERTYKEY v25[2]; // [rsp+98h] [rbp-11h] BYREF

  v4 = 0;
  v19 = 0;
  v5 = 0;
  v18 = 0;
  v25[0] = PKEY_DateModified;
  v25[1] = PKEY_ThumbnailCacheId;
  v21 = 0;
  v22 = 0;
  QueryInterface = a2->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  v7 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 *))QueryInterface)(
         a2,
         &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
         &v22);
  if ( v7 >= 0 )
  {
    v8 = v22;
    v9 = *(__int64 (__fastcall **)(__int64, PROPERTYKEY *, __int64, __int64, GUID *, struct IPropertyStore **))(*(_QWORD *)v22 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v7 = v9(v8, v25, 2, 8, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &v21);
  }
  v10 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( v7 < 0 )
    goto LABEL_21;
  LOWORD(pvar) = 0;
  v20 = PKEY_ThumbnailCacheId;
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, PROPERTYKEY *, PROPVARIANT *))v21->lpVtbl->GetValue)(
         v21,
         &v20,
         &pvar);
  if ( v7 >= 0 )
  {
    if ( (_WORD)pvar )
    {
      if ( (_WORD)pvar == 21 )
      {
        v4 = v24;
        v19 = v24;
      }
      else
      {
        v7 = -2147352571;
      }
    }
    else
    {
      v7 = -2147023728;
    }
  }
  PropVariantClear(&pvar);
  if ( v7 < 0 )
    goto LABEL_21;
  v18 = 0;
  if ( is_mul_ok(0x11u, 2u) )
  {
    v11 = (unsigned __int16 *)CoTaskMemAlloc(0x22u);
    v5 = v11;
    v18 = v11;
    v7 = -2147024882;
    if ( v11 )
      v7 = 0;
    if ( v7 >= 0 )
    {
      if ( v11 )
      {
        *v11 = 0;
        memset_0(v11 + 1, 0, 0x20u);
      }
      else
      {
        MEMORY[0] = 0;
      }
      _o__ui64tow_s(v4, v5, 17, 16);
      goto LABEL_17;
    }
LABEL_21:
    if ( v7 == -2147024882 )
      goto LABEL_18;
  }
  v7 = CThumbnailMoniker::_NonLocalFSInitFallback(this, a2, v21, &v19, &v18);
  v5 = v18;
  if ( v7 >= 0 )
  {
    v4 = v19;
LABEL_17:
    v12 = 2 - ((unsigned int)IsShellItemEncrypted(a2) != 0);
    v13 = v5;
    v5 = 0;
    v18 = 0;
    v14 = (void *)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    CoTaskMemFree(v14);
    v15 = (void *)*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    CoTaskMemFree(v15);
    *((_QWORD *)this + 2) = v13;
    *((_DWORD *)this + 7) = v12;
    *(_QWORD *)this = v4;
    *((_DWORD *)this + 2) = 0;
    *((_DWORD *)this + 3) = 19;
  }
LABEL_18:
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    ((void (__fastcall *)(struct IPropertyStore *))v16->lpVtbl->Release)(v16);
  }
  CoTaskMemFree(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009ed0  mov     [rsp-8+arg_10], rbx
0x180009ed5  push    rbp
0x180009ed6  push    rsi
0x180009ed7  push    rdi
0x180009ed8  push    r12
0x180009eda  push    r13
0x180009edc  push    r14
0x180009ede  push    r15
0x180009ee0  lea     rbp, [rsp-27h]
0x180009ee5  sub     rsp, 0D0h
0x180009eec  mov     rax, cs:__security_cookie
0x180009ef3  xor     rax, rsp
0x180009ef6  mov     [rbp+57h+var_40], rax
0x180009efa  mov     r13, rdx
0x180009efd  mov     r15, rcx
0x180009f00  xor     edi, edi
0x180009f02  mov     r12d, edi
0x180009f05  mov     [rbp+57h+var_B8], rdi
0x180009f09  mov     r14d, edi
0x180009f0c  mov     [rbp+57h+var_C0], rdi
0x180009f10  movups  xmm0, xmmword ptr cs:PKEY_DateModified.fmtid.Data1
0x180009f17  movups  [rbp+57h+var_68], xmm0
0x180009f1b  mov     eax, cs:PKEY_DateModified.pid
0x180009f21  mov     [rbp+57h+var_58], eax
0x180009f24  movups  xmm0, xmmword ptr cs:PKEY_ThumbnailCacheId.fmtid.Data1
0x180009f2b  movups  [rbp+57h+var_54], xmm0
0x180009f2f  mov     eax, cs:PKEY_ThumbnailCacheId.pid
0x180009f35  mov     [rbp+57h+var_44], eax
0x180009f38  mov     [rbp+57h+var_90], rdi
0x180009f3c  mov     [rbp+57h+var_88], rdi
0x180009f40  mov     rax, [rdx]
0x180009f43  mov     rbx, [rax]
0x180009f46  lea     rcx, [rbp+57h+var_88]
0x180009f4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009f4f  lea     r8, [rbp+57h+var_88]
0x180009f53  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180009f5a  mov     rcx, r13
0x180009f5d  mov     rax, rbx
0x180009f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f65  mov     esi, eax
0x180009f67  test    eax, eax
0x180009f69  js      short loc_180009FB3
0x180009f6b  mov     rdi, [rbp+57h+var_88]
0x180009f6f  mov     rax, [rdi]
0x180009f72  mov     rbx, [rax+50h]
0x180009f76  lea     rcx, [rbp+57h+var_90]
0x180009f7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009f7f  lea     rax, [rbp+57h+var_90]
0x180009f83  mov     [rsp+100h+var_D8], rax
0x180009f88  lea     rax, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180009f8f  mov     [rsp+100h+var_E0], rax
0x180009f94  mov     r9d, 8
0x180009f9a  mov     r8d, 2
0x180009fa0  lea     rdx, [rbp+57h+var_68]
0x180009fa4  mov     rcx, rdi
0x180009fa7  mov     rax, rbx
0x180009faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009faf  mov     esi, eax
0x180009fb1  xor     edi, edi
0x180009fb3  mov     rcx, [rbp+57h+var_88]
0x180009fb7  test    rcx, rcx
0x180009fba  jz      short loc_180009FCD
0x180009fbc  mov     [rbp+57h+var_88], rdi
0x180009fc0  mov     rax, [rcx]
0x180009fc3  mov     rax, [rax+10h]
0x180009fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fcc  nop
0x180009fcd  test    esi, esi
0x180009fcf  js      loc_18000A17B
0x180009fd5  movups  xmm0, xmmword ptr cs:PKEY_ThumbnailCacheId.fmtid.Data1
0x180009fdc  mov     ecx, cs:PKEY_ThumbnailCacheId.pid
0x180009fe2  mov     word ptr [rbp+57h+pvar], di
0x180009fe6  movaps  [rbp+57h+var_B0], xmm0
0x180009fea  mov     [rbp+57h+var_A0], ecx
0x180009fed  mov     rcx, [rbp+57h+var_90]
0x180009ff1  mov     rax, [rcx]
0x180009ff4  lea     r8, [rbp+57h+pvar]
0x180009ff8  lea     rdx, [rbp+57h+var_B0]
0x180009ffc  mov     rax, [rax+28h]
0x18000a000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a005  mov     esi, eax
0x18000a007  movzx   eax, word ptr [rbp+57h+pvar]
0x18000a00b  test    esi, esi
0x18000a00d  js      short loc_18000A01D
0x18000a00f  test    ax, ax
0x18000a012  jnz     loc_18000A1E7
0x18000a018  mov     esi, 80070490h
0x18000a01d  lea     rcx, [rbp+57h+pvar]; pvar
0x18000a021  call    cs:__imp_PropVariantClear
0x18000a027  test    esi, esi
0x18000a029  js      loc_18000A17B
0x18000a02f  mov     [rbp+57h+var_C0], rdi
0x18000a033  mov     ebx, 11h
0x18000a038  mov     eax, 2
0x18000a03d  mul     rbx
0x18000a040  test    rdx, rdx
0x18000a043  jnz     loc_18000A183
0x18000a049  mov     rcx, rax; cb
0x18000a04c  call    cs:__imp_CoTaskMemAlloc
0x18000a052  mov     r14, rax
0x18000a055  mov     [rbp+57h+var_C0], rax
0x18000a059  mov     esi, 8007000Eh
0x18000a05e  test    rax, rax
0x18000a061  cmovnz  esi, edi
0x18000a064  test    esi, esi
0x18000a066  js      loc_18000A17B
0x18000a06c  test    rax, rax
0x18000a06f  jz      loc_18000A20C
0x18000a075  mov     rax, rdi
0x18000a078  lea     r8, unk_1800509F8
0x18000a07f  mov     edx, ebx
0x18000a081  mov     r9, r14
0x18000a084  mov     r10, rdi
0x18000a087  test    rax, rax
0x18000a08a  jz      short loc_18000A0AD
0x18000a08c  movzx   ecx, word ptr [r8]
0x18000a090  test    cx, cx
0x18000a093  jz      short loc_18000A0AD
0x18000a095  add     r8, 2
0x18000a099  mov     [r9], cx
0x18000a09d  add     r9, 2
0x18000a0a1  dec     rax
0x18000a0a4  inc     r10
0x18000a0a7  sub     rdx, 1
0x18000a0ab  jnz     short loc_18000A087
0x18000a0ad  lea     r11, [r10-1]
0x18000a0b1  test    rdx, rdx
0x18000a0b4  cmovnz  r11, r10
0x18000a0b8  lea     rcx, [r9-2]
0x18000a0bc  cmovnz  rcx, r9
0x18000a0c0  mov     [rcx], di
0x18000a0c3  jnz     loc_18000A1B2
0x18000a0c9  mov     r9d, 10h
0x18000a0cf  mov     r8, rbx
0x18000a0d2  mov     rdx, r14
0x18000a0d5  mov     rcx, r12
0x18000a0d8  call    cs:__imp__o__ui64tow_s
0x18000a0de  mov     rcx, r13; struct IShellItem *
0x18000a0e1  call    ?IsShellItemEncrypted@@YAHPEAUIShellItem@@@Z; IsShellItemEncrypted(IShellItem *)
0x18000a0e6  neg     eax
0x18000a0e8  sbb     edi, edi
0x18000a0ea  add     edi, 2
0x18000a0ed  mov     rbx, r14
0x18000a0f0  xor     r13d, r13d
0x18000a0f3  mov     r14d, r13d
0x18000a0f6  mov     [rbp+57h+var_C0], r13
0x18000a0fa  mov     rcx, [r15+10h]; pv
0x18000a0fe  mov     [r15+10h], r13
0x18000a102  call    cs:__imp_CoTaskMemFree
0x18000a108  mov     rcx, [r15+10h]; pv
0x18000a10c  mov     [r15+10h], r13
0x18000a110  call    cs:__imp_CoTaskMemFree
0x18000a116  mov     [r15+10h], rbx
0x18000a11a  mov     [r15+1Ch], edi
0x18000a11e  mov     [r15], r12
0x18000a121  xor     edi, edi
0x18000a123  mov     [r15+8], edi
0x18000a127  mov     dword ptr [r15+0Ch], 13h
0x18000a12f  mov     rcx, [rbp+57h+var_90]
0x18000a133  test    rcx, rcx
0x18000a136  jz      short loc_18000A149
0x18000a138  mov     [rbp+57h+var_90], rdi
0x18000a13c  mov     rdx, [rcx]
0x18000a13f  mov     rax, [rdx+10h]
0x18000a143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a148  nop
0x18000a149  mov     rcx, r14; pv
0x18000a14c  call    cs:__imp_CoTaskMemFree
0x18000a152  mov     eax, esi
0x18000a154  mov     rcx, [rbp+57h+var_40]
0x18000a158  xor     rcx, rsp; StackCookie
0x18000a15b  call    __security_check_cookie
0x18000a160  mov     rbx, [rsp+100h+arg_10]
0x18000a168  add     rsp, 0D0h
0x18000a16f  pop     r15
0x18000a171  pop     r14
0x18000a173  pop     r13
0x18000a175  pop     r12
0x18000a177  pop     rdi
0x18000a178  pop     rsi
0x18000a179  pop     rbp
0x18000a17a  retn
0x18000a17b  cmp     esi, 8007000Eh
0x18000a181  jz      short loc_18000A12F
0x18000a183  lea     rax, [rbp+57h+var_C0]
0x18000a187  mov     [rsp+100h+var_E0], rax; unsigned __int16 **
0x18000a18c  lea     r9, [rbp+57h+var_B8]; unsigned __int64 *
0x18000a190  mov     r8, [rbp+57h+var_90]; struct IPropertyStore *
0x18000a194  mov     rdx, r13; struct IShellItem *
0x18000a197  mov     rcx, r15; this
0x18000a19a  call    ?_NonLocalFSInitFallback@CThumbnailMoniker@@AEBAJPEAUIShellItem@@PEAUIPropertyStore@@PEA_KPEAPEAG@Z; CThumbnailMoniker::_NonLocalFSInitFallback(IShellItem *,IPropertyStore *,unsigned __int64 *,ushort * *)
0x18000a19f  mov     esi, eax
0x18000a1a1  mov     r14, [rbp+57h+var_C0]
0x18000a1a5  test    eax, eax
0x18000a1a7  js      short loc_18000A12F
0x18000a1a9  mov     r12, [rbp+57h+var_B8]
0x18000a1ad  jmp     loc_18000A0DE
0x18000a1b2  mov     rax, rbx
0x18000a1b5  sub     rax, r11
0x18000a1b8  cmp     rax, 1
0x18000a1bc  jbe     loc_18000A0C9
0x18000a1c2  lea     r8, [rax+rax]
0x18000a1c6  cmp     r8, 2
0x18000a1ca  jbe     loc_18000A0C9
0x18000a1d0  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000a1d4  inc     r11
0x18000a1d7  lea     rcx, [r14+r11*2]; void *
0x18000a1db  xor     edx, edx; Val
0x18000a1dd  call    memset_0
0x18000a1e2  jmp     loc_18000A0C9
0x18000a1e7  test    esi, esi
0x18000a1e9  js      loc_18000A01D
0x18000a1ef  cmp     ax, 15h
0x18000a1f3  jnz     short loc_18000A202
0x18000a1f5  mov     r12, [rbp+57h+var_78]
0x18000a1f9  mov     [rbp+57h+var_B8], r12
0x18000a1fd  jmp     loc_18000A01D
0x18000a202  mov     esi, 80020005h
0x18000a207  jmp     loc_18000A01D
0x18000a20c  mov     [rax], di
0x18000a20f  jmp     loc_18000A0C9
```
