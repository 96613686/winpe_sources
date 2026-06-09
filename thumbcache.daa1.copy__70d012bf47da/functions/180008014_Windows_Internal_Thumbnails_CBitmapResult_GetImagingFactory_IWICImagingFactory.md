# Windows::Internal::Thumbnails::CBitmapResult::_GetImagingFactory(IWICImagingFactory * *)

- ea: `0x180008014`
- end: `0x180008130`
- name: `?_GetImagingFactory@CBitmapResult@Thumbnails@Internal@Windows@@AEAAJPEAPEAUIWICImagingFactory@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(Windows::Internal::Thumbnails::CBitmapResult *__hidden this, struct IWICImagingFactory **)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800078c4`
- `0x180007cb0`
- `0x180022bbc`

## callees

- `0x180003624`
- `0x180008014`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000808d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000808d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Thumbnails::CBitmapResult::_GetImagingFactory(
        Windows::Internal::Thumbnails::CBitmapResult *this,
        struct IWICImagingFactory **a2)
{
  struct IWICImagingFactory *v4; // rcx
  HRESULT v5; // esi
  LPVOID v6; // rbx
  __int64 v7; // rdx
  LPVOID v8; // rdx
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF

  *a2 = 0;
  v4 = (struct IWICImagingFactory *)*((_QWORD *)this + 12);
  ppv = v4;
  if ( v4 )
  {
    ((void (__fastcall *)(struct IWICImagingFactory *))v4->lpVtbl->AddRef)(v4);
    v4 = (struct IWICImagingFactory *)ppv;
  }
  if ( v4 )
  {
    v5 = 0;
LABEL_10:
    v8 = 0;
    *a2 = v4;
    goto LABEL_11;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v5 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  if ( v5 >= 0 )
  {
    v4 = (struct IWICImagingFactory *)ppv;
    if ( *((LPVOID *)this + 12) != ppv )
    {
      v6 = ppv;
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
        v4 = (struct IWICImagingFactory *)ppv;
      }
      v7 = *((_QWORD *)this + 12);
      *((_QWORD *)this + 12) = v6;
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        v4 = (struct IWICImagingFactory *)ppv;
      }
    }
    goto LABEL_10;
  }
  v8 = ppv;
LABEL_11:
  if ( v8 )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008014  mov     [rsp+arg_10], rbx
0x180008019  push    rsi
0x18000801a  push    rdi
0x18000801b  push    r14
0x18000801d  sub     rsp, 40h
0x180008021  mov     rax, cs:__security_cookie
0x180008028  xor     rax, rsp
0x18000802b  mov     [rsp+58h+var_20], rax
0x180008030  mov     r14, rdx
0x180008033  mov     rdi, rcx
0x180008036  mov     qword ptr [rdx], 0
0x18000803d  mov     rcx, [rcx+60h]
0x180008041  mov     [rsp+58h+var_28], rcx
0x180008046  test    rcx, rcx
0x180008049  jz      short loc_18000805C
0x18000804b  mov     rax, [rcx]
0x18000804e  mov     rax, [rax+8]
0x180008052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008057  mov     rcx, [rsp+58h+var_28]
0x18000805c  test    rcx, rcx
0x18000805f  jnz     loc_18000812C
0x180008065  lea     rcx, [rsp+58h+var_28]
0x18000806a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000806f  lea     rax, [rsp+58h+var_28]
0x180008074  mov     [rsp+58h+ppv], rax; ppv
0x180008079  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180008080  xor     edx, edx; pUnkOuter
0x180008082  lea     r8d, [rdx+1]; dwClsContext
0x180008086  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18000808d  call    cs:__imp_CoCreateInstance
0x180008093  mov     esi, eax
0x180008095  test    eax, eax
0x180008097  js      loc_180008125
0x18000809d  mov     rcx, [rsp+58h+var_28]
0x1800080a2  cmp     [rdi+60h], rcx
0x1800080a6  jz      short loc_1800080E5
0x1800080a8  mov     rbx, rcx
0x1800080ab  test    rcx, rcx
0x1800080ae  jz      short loc_1800080C4
0x1800080b0  mov     rcx, [rcx]
0x1800080b3  mov     rax, [rcx+8]
0x1800080b7  mov     rcx, rbx
0x1800080ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080bf  mov     rcx, [rsp+58h+var_28]
0x1800080c4  mov     rdx, [rdi+60h]
0x1800080c8  mov     [rdi+60h], rbx
0x1800080cc  test    rdx, rdx
0x1800080cf  jz      short loc_1800080E5
0x1800080d1  mov     rax, [rdx]
0x1800080d4  mov     rcx, rdx
0x1800080d7  mov     rax, [rax+10h]
0x1800080db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080e0  mov     rcx, [rsp+58h+var_28]
0x1800080e5  xor     edx, edx
0x1800080e7  mov     [r14], rcx
0x1800080ea  test    rdx, rdx
0x1800080ed  jz      short loc_180008108
0x1800080ef  mov     [rsp+58h+var_28], 0
0x1800080f8  mov     rax, [rdx]
0x1800080fb  mov     rcx, rdx
0x1800080fe  mov     rax, [rax+10h]
0x180008102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008107  nop
0x180008108  mov     eax, esi
0x18000810a  mov     rcx, [rsp+58h+var_20]
0x18000810f  xor     rcx, rsp; StackCookie
0x180008112  call    __security_check_cookie
0x180008117  mov     rbx, [rsp+58h+arg_10]
0x18000811c  add     rsp, 40h
0x180008120  pop     r14
0x180008122  pop     rdi
0x180008123  pop     rsi
0x180008124  retn
0x180008125  mov     rdx, [rsp+58h+var_28]
0x18000812a  jmp     short loc_1800080EA
0x18000812c  xor     esi, esi
0x18000812e  jmp     short loc_1800080E5
```
