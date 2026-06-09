# GetConfigDWORD(IAppHostElement *,ushort const *,ulong *)

- ea: `0x180002af0`
- end: `0x180002bd1`
- name: `?GetConfigDWORD@@YAJPEAUIAppHostElement@@PEBGPEAK@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct IAppHostElement *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003c74`

## callees

- `0x180002af0`
- `0x180006010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002b2c`
- `OLEAUT32!__imp_SysAllocString` at `0x180002b2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002bab`
- `OLEAUT32!__imp_SysFreeString` at `0x180002bab`
- `OLEAUT32!__imp_VariantInit` at `0x180002b1f`
- `OLEAUT32!__imp_VariantInit` at `0x180002b1f`
- `OLEAUT32!__imp_VariantClear` at `0x180002b9d`
- `OLEAUT32!__imp_VariantClear` at `0x180002b9d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002b88`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002b88`

## pseudocode

```c
__int64 __fastcall GetConfigDWORD(struct IAppHostElement *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  BSTR v5; // rax
  OLECHAR *v6; // rdi
  HRESULT v7; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+78h] [rbp+30h] BYREF

  v10 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = SysAllocString(L"id");
  v6 = v5;
  if ( v5 )
  {
    v7 = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, __int64 *))a1->lpVtbl->GetPropertyByName)(
           a1,
           v5,
           &v10);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v10 + 32LL))(v10, &pvarg);
      if ( v7 >= 0 )
      {
        v7 = VariantChangeType(&pvarg, &pvarg, 0, 0x13u);
        if ( v7 >= 0 )
          *a3 = pvarg.cyVal.Lo;
      }
    }
  }
  else
  {
    v7 = -2147024882;
  }
  VariantClear(&pvarg);
  if ( v6 )
    SysFreeString(v6);
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002af0  mov     [rsp-20h+arg_8], rdx
0x180002af5  push    rbp
0x180002af6  push    rbx
0x180002af7  push    rsi
0x180002af8  push    rdi
0x180002af9  mov     rbp, rsp
0x180002afc  sub     rsp, 48h
0x180002b00  mov     rbx, rcx
0x180002b03  mov     [rbp+arg_8], 0
0x180002b0b  xorps   xmm0, xmm0
0x180002b0e  lea     rcx, [rbp+pvarg]; pvarg
0x180002b12  xor     eax, eax
0x180002b14  mov     rsi, r8
0x180002b17  movups  xmmword ptr [rbp+pvarg], xmm0
0x180002b1b  mov     qword ptr [rbp+pvarg+10h], rax
0x180002b1f  call    cs:__imp_VariantInit
0x180002b25  lea     rcx, psz; "id"
0x180002b2c  call    cs:__imp_SysAllocString
0x180002b32  mov     rdi, rax
0x180002b35  test    rax, rax
0x180002b38  jnz     short loc_180002B41
0x180002b3a  mov     ebx, 8007000Eh
0x180002b3f  jmp     short loc_180002B99
0x180002b41  mov     rax, [rbx]
0x180002b44  lea     r8, [rbp+arg_8]
0x180002b48  mov     rdx, rdi
0x180002b4b  mov     rcx, rbx
0x180002b4e  mov     rax, [rax+58h]
0x180002b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b57  mov     ebx, eax
0x180002b59  test    eax, eax
0x180002b5b  js      short loc_180002B99
0x180002b5d  mov     rcx, [rbp+arg_8]
0x180002b61  lea     rdx, [rbp+pvarg]
0x180002b65  mov     rax, [rcx]
0x180002b68  mov     rax, [rax+20h]
0x180002b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b71  mov     ebx, eax
0x180002b73  test    eax, eax
0x180002b75  js      short loc_180002B99
0x180002b77  mov     r9d, 13h; vt
0x180002b7d  lea     rdx, [rbp+pvarg]; pvarSrc
0x180002b81  xor     r8d, r8d; wFlags
0x180002b84  lea     rcx, [rbp+pvarg]; pvargDest
0x180002b88  call    cs:__imp_VariantChangeType
0x180002b8e  mov     ebx, eax
0x180002b90  test    eax, eax
0x180002b92  js      short loc_180002B99
0x180002b94  mov     eax, dword ptr [rbp+pvarg+8]
0x180002b97  mov     [rsi], eax
0x180002b99  lea     rcx, [rbp+pvarg]; pvarg
0x180002b9d  call    cs:__imp_VariantClear
0x180002ba3  test    rdi, rdi
0x180002ba6  jz      short loc_180002BB1
0x180002ba8  mov     rcx, rdi; bstrString
0x180002bab  call    cs:__imp_SysFreeString
0x180002bb1  mov     rcx, [rbp+arg_8]
0x180002bb5  test    rcx, rcx
0x180002bb8  jz      short loc_180002BC6
0x180002bba  mov     rax, [rcx]
0x180002bbd  mov     rax, [rax+10h]
0x180002bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc6  mov     eax, ebx
0x180002bc8  add     rsp, 48h
0x180002bcc  pop     rdi
0x180002bcd  pop     rsi
0x180002bce  pop     rbx
0x180002bcf  pop     rbp
0x180002bd0  retn
```
