# W3WP_HOST::SetupConfigSystemMetadata(void)

- ea: `0x180006b70`
- end: `0x180006ccf`
- name: `?SetupConfigSystemMetadata@W3WP_HOST@@AEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800051dc`

## callees

- `0x180006b70`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180006cbc`
- `OLEAUT32!__imp_VariantClear` at `0x180006cbc`

## string_xrefs

- `0x180006c3f`: `disableExtensions`

## pseudocode

```c
__int64 __fastcall W3WP_HOST::SetupConfigSystemMetadata(W3WP_HOST *this)
{
  __int64 (__fastcall ***v1)(_QWORD, GUID *, __int64 **); // rcx
  int v2; // ebx
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 (__fastcall *v5)(__int64 *, const wchar_t *, VARIANTARG *); // rax
  __int64 v6; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG v9; // [rsp+40h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+70h] [rbp+10h] BYREF

  v1 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))*((_QWORD *)this + 24);
  v10 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 11;
  pvarg.iVal = 0;
  v2 = (**v1)(v1, &IID_IAppHostAdminManager, &v10);
  if ( v2 >= 0 )
  {
    v3 = *v10;
    v9 = pvarg;
    v2 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v3 + 40))(
           v10,
           L"ignoreInvalidRanges",
           &v9);
    if ( v2 >= 0 )
    {
      v4 = *v10;
      v9 = pvarg;
      v2 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v4 + 40))(
             v10,
             L"ignoreInvalidDecryption",
             &v9);
      if ( v2 >= 0 )
      {
        v9.pRecInfo = pvarg.pRecInfo;
        pvarg.iVal = -1;
        v5 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*v10 + 40);
        *(_OWORD *)&v9.vt = *(_OWORD *)&pvarg.vt;
        v2 = v5(v10, L"disableExtensions", &v9);
        if ( v2 >= 0 )
        {
          v6 = *v10;
          v9 = pvarg;
          v2 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v6 + 40))(
                 v10,
                 L"lockMetadata",
                 &v9);
        }
      }
    }
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
    v10 = 0;
  }
  VariantClear(&pvarg);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006b70  mov     [rsp-8+arg_8], rbx
0x180006b75  push    rbp
0x180006b76  mov     rbp, rsp
0x180006b79  sub     rsp, 60h
0x180006b7d  mov     rcx, [rcx+0C0h]
0x180006b84  lea     r8, [rbp+arg_0]
0x180006b88  xor     eax, eax
0x180006b8a  mov     [rbp+arg_0], 0
0x180006b92  mov     qword ptr [rbp+pvarg+10h], rax
0x180006b96  lea     rdx, IID_IAppHostAdminManager
0x180006b9d  mov     eax, 0Bh
0x180006ba2  xorps   xmm0, xmm0
0x180006ba5  movups  xmmword ptr [rbp+pvarg], xmm0
0x180006ba9  mov     word ptr [rbp+pvarg], ax
0x180006bad  xor     eax, eax
0x180006baf  mov     word ptr [rbp+pvarg+8], ax
0x180006bb3  mov     rax, [rcx]
0x180006bb6  mov     rax, [rax]
0x180006bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bbe  mov     ebx, eax
0x180006bc0  test    eax, eax
0x180006bc2  js      loc_180006C9B
0x180006bc8  mov     rcx, [rbp+arg_0]
0x180006bcc  lea     r8, [rbp+var_20]
0x180006bd0  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180006bd4  lea     rdx, aIgnoreinvalidr; "ignoreInvalidRanges"
0x180006bdb  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180006be0  mov     rax, [rcx]
0x180006be3  movaps  [rbp+var_20], xmm0
0x180006be7  movsd   [rbp+var_10], xmm1
0x180006bec  mov     rax, [rax+28h]
0x180006bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf5  mov     ebx, eax
0x180006bf7  test    eax, eax
0x180006bf9  js      loc_180006C9B
0x180006bff  mov     rcx, [rbp+arg_0]
0x180006c03  lea     r8, [rbp+var_20]
0x180006c07  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180006c0b  lea     rdx, aIgnoreinvalidd; "ignoreInvalidDecryption"
0x180006c12  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180006c17  mov     rax, [rcx]
0x180006c1a  movaps  [rbp+var_20], xmm0
0x180006c1e  movsd   [rbp+var_10], xmm1
0x180006c23  mov     rax, [rax+28h]
0x180006c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c2c  mov     ebx, eax
0x180006c2e  test    eax, eax
0x180006c30  js      short loc_180006C9B
0x180006c32  mov     rcx, [rbp+arg_0]
0x180006c36  lea     r8, [rbp+var_20]
0x180006c3a  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180006c3f  lea     rdx, aDisableextensi; "disableExtensions"
0x180006c46  or      eax, 0FFFFFFFFh
0x180006c49  movsd   [rbp+var_10], xmm1
0x180006c4e  mov     word ptr [rbp+pvarg+8], ax
0x180006c52  mov     rax, [rcx]
0x180006c55  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180006c59  mov     rax, [rax+28h]
0x180006c5d  movaps  [rbp+var_20], xmm0
0x180006c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c66  mov     ebx, eax
0x180006c68  test    eax, eax
0x180006c6a  js      short loc_180006C9B
0x180006c6c  mov     rcx, [rbp+arg_0]
0x180006c70  lea     r8, [rbp+var_20]
0x180006c74  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180006c78  lea     rdx, aLockmetadata; "lockMetadata"
0x180006c7f  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180006c84  mov     rax, [rcx]
0x180006c87  movaps  [rbp+var_20], xmm0
0x180006c8b  movsd   [rbp+var_10], xmm1
0x180006c90  mov     rax, [rax+28h]
0x180006c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c99  mov     ebx, eax
0x180006c9b  mov     rcx, [rbp+arg_0]
0x180006c9f  test    rcx, rcx
0x180006ca2  jz      short loc_180006CB8
0x180006ca4  mov     rax, [rcx]
0x180006ca7  mov     rax, [rax+10h]
0x180006cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb0  mov     [rbp+arg_0], 0
0x180006cb8  lea     rcx, [rbp+pvarg]; pvarg
0x180006cbc  call    cs:__imp_VariantClear
0x180006cc2  mov     eax, ebx
0x180006cc4  mov     rbx, [rsp+60h+arg_8]
0x180006cc9  add     rsp, 60h
0x180006ccd  pop     rbp
0x180006cce  retn
```
