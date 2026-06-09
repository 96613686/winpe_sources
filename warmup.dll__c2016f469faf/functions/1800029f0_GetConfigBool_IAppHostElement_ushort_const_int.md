# GetConfigBool(IAppHostElement *,ushort const *,int *)

- ea: `0x1800029f0`
- end: `0x180002ae7`
- name: `?GetConfigBool@@YAJPEAUIAppHostElement@@PEBGPEAH@Z`
- size: `247`
- prototype: `int(struct IAppHostElement *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003818`
- `0x180003c74`

## callees

- `0x1800029f0`
- `0x180006010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180002a30`
- `OLEAUT32!__imp_SysAllocString` at `0x180002a30`
- `OLEAUT32!__imp_SysFreeString` at `0x180002ab7`
- `OLEAUT32!__imp_SysFreeString` at `0x180002ab7`
- `OLEAUT32!__imp_VariantInit` at `0x180002a27`
- `OLEAUT32!__imp_VariantInit` at `0x180002a27`
- `OLEAUT32!__imp_VariantClear` at `0x180002aa9`
- `OLEAUT32!__imp_VariantClear` at `0x180002aa9`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002a8c`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002a8c`

## pseudocode

```c
__int64 __fastcall GetConfigBool(struct IAppHostElement *a1, const unsigned __int16 *a2, int *a3)
{
  BSTR v6; // rax
  OLECHAR *v7; // rdi
  HRESULT v8; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+78h] [rbp+38h] BYREF

  v11 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = SysAllocString(a2);
  v7 = v6;
  if ( v6 )
  {
    v8 = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, __int64 *))a1->lpVtbl->GetPropertyByName)(
           a1,
           v6,
           &v11);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v11 + 32LL))(v11, &pvarg);
      if ( v8 >= 0 )
      {
        v8 = VariantChangeType(&pvarg, &pvarg, 0, 0xBu);
        if ( v8 >= 0 )
          *a3 = pvarg.iVal == -1;
      }
    }
  }
  else
  {
    v8 = -2147024882;
  }
  VariantClear(&pvarg);
  if ( v7 )
    SysFreeString(v7);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800029f0  mov     [rsp-18h+arg_0], rbx
0x1800029f5  mov     [rsp-18h+arg_8], rsi
0x1800029fa  push    rbp
0x1800029fb  push    rdi
0x1800029fc  push    r14
0x1800029fe  mov     rbp, rsp
0x180002a01  sub     rsp, 40h
0x180002a05  mov     rsi, rcx
0x180002a08  mov     [rbp+arg_18], 0
0x180002a10  xorps   xmm0, xmm0
0x180002a13  lea     rcx, [rbp+pvarg]; pvarg
0x180002a17  xor     eax, eax
0x180002a19  mov     r14, r8
0x180002a1c  movups  xmmword ptr [rbp+pvarg], xmm0
0x180002a20  mov     qword ptr [rbp+pvarg+10h], rax
0x180002a24  mov     rbx, rdx
0x180002a27  call    cs:__imp_VariantInit
0x180002a2d  mov     rcx, rbx; psz
0x180002a30  call    cs:__imp_SysAllocString
0x180002a36  mov     rdi, rax
0x180002a39  test    rax, rax
0x180002a3c  jnz     short loc_180002A45
0x180002a3e  mov     ebx, 8007000Eh
0x180002a43  jmp     short loc_180002AA5
0x180002a45  mov     rax, [rsi]
0x180002a48  lea     r8, [rbp+arg_18]
0x180002a4c  mov     rdx, rdi
0x180002a4f  mov     rcx, rsi
0x180002a52  mov     rax, [rax+58h]
0x180002a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a5b  mov     ebx, eax
0x180002a5d  test    eax, eax
0x180002a5f  js      short loc_180002AA5
0x180002a61  mov     rcx, [rbp+arg_18]
0x180002a65  lea     rdx, [rbp+pvarg]
0x180002a69  mov     rax, [rcx]
0x180002a6c  mov     rax, [rax+20h]
0x180002a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a75  mov     ebx, eax
0x180002a77  test    eax, eax
0x180002a79  js      short loc_180002AA5
0x180002a7b  mov     r9d, 0Bh; vt
0x180002a81  lea     rdx, [rbp+pvarg]; pvarSrc
0x180002a85  xor     r8d, r8d; wFlags
0x180002a88  lea     rcx, [rbp+pvarg]; pvargDest
0x180002a8c  call    cs:__imp_VariantChangeType
0x180002a92  mov     ebx, eax
0x180002a94  test    eax, eax
0x180002a96  js      short loc_180002AA5
0x180002a98  xor     eax, eax
0x180002a9a  cmp     word ptr [rbp+pvarg+8], 0FFFFh
0x180002a9f  setz    al
0x180002aa2  mov     [r14], eax
0x180002aa5  lea     rcx, [rbp+pvarg]; pvarg
0x180002aa9  call    cs:__imp_VariantClear
0x180002aaf  test    rdi, rdi
0x180002ab2  jz      short loc_180002ABD
0x180002ab4  mov     rcx, rdi; bstrString
0x180002ab7  call    cs:__imp_SysFreeString
0x180002abd  mov     rcx, [rbp+arg_18]
0x180002ac1  test    rcx, rcx
0x180002ac4  jz      short loc_180002AD2
0x180002ac6  mov     rax, [rcx]
0x180002ac9  mov     rax, [rax+10h]
0x180002acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad2  mov     rsi, [rsp+40h+arg_8]
0x180002ad7  mov     eax, ebx
0x180002ad9  mov     rbx, [rsp+40h+arg_0]
0x180002ade  add     rsp, 40h
0x180002ae2  pop     r14
0x180002ae4  pop     rdi
0x180002ae5  pop     rbp
0x180002ae6  retn
```
