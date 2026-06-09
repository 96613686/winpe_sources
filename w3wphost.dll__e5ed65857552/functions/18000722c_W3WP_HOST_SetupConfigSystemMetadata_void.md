# W3WP_HOST::SetupConfigSystemMetadata(void)

- ea: `0x18000722c`
- end: `0x180007392`
- name: `?SetupConfigSystemMetadata@W3WP_HOST@@AEAAJXZ`
- size: `358`
- prototype: `__int64 __fastcall(W3WP_HOST *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000561c`

## callees

- `0x18000722c`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180007378`
- `OLEAUT32!__imp_VariantClear` at `0x180007378`

## string_xrefs

- `0x1800072fb`: `disableExtensions`

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
0x18000722c  mov     [rsp-8+arg_8], rbx
0x180007231  push    rbp
0x180007232  mov     rbp, rsp
0x180007235  sub     rsp, 60h
0x180007239  mov     rcx, [rcx+0C0h]
0x180007240  lea     r8, [rbp+arg_0]
0x180007244  xor     eax, eax
0x180007246  mov     [rbp+arg_0], 0
0x18000724e  mov     qword ptr [rbp+pvarg+10h], rax
0x180007252  lea     rdx, IID_IAppHostAdminManager
0x180007259  mov     eax, 0Bh
0x18000725e  xorps   xmm0, xmm0
0x180007261  movups  xmmword ptr [rbp+pvarg], xmm0
0x180007265  mov     word ptr [rbp+pvarg], ax
0x180007269  xor     eax, eax
0x18000726b  mov     word ptr [rbp+pvarg+8], ax
0x18000726f  mov     rax, [rcx]
0x180007272  mov     rax, [rax]
0x180007275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000727a  mov     ebx, eax
0x18000727c  test    eax, eax
0x18000727e  js      loc_180007357
0x180007284  mov     rcx, [rbp+arg_0]
0x180007288  lea     r8, [rbp+var_20]
0x18000728c  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180007290  lea     rdx, aIgnoreinvalidr; "ignoreInvalidRanges"
0x180007297  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000729c  mov     rax, [rcx]
0x18000729f  movaps  [rbp+var_20], xmm0
0x1800072a3  movsd   [rbp+var_10], xmm1
0x1800072a8  mov     rax, [rax+28h]
0x1800072ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b1  mov     ebx, eax
0x1800072b3  test    eax, eax
0x1800072b5  js      loc_180007357
0x1800072bb  mov     rcx, [rbp+arg_0]
0x1800072bf  lea     r8, [rbp+var_20]
0x1800072c3  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1800072c7  lea     rdx, aIgnoreinvalidd; "ignoreInvalidDecryption"
0x1800072ce  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800072d3  mov     rax, [rcx]
0x1800072d6  movaps  [rbp+var_20], xmm0
0x1800072da  movsd   [rbp+var_10], xmm1
0x1800072df  mov     rax, [rax+28h]
0x1800072e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e8  mov     ebx, eax
0x1800072ea  test    eax, eax
0x1800072ec  js      short loc_180007357
0x1800072ee  mov     rcx, [rbp+arg_0]
0x1800072f2  lea     r8, [rbp+var_20]
0x1800072f6  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1800072fb  lea     rdx, aDisableextensi; "disableExtensions"
0x180007302  or      eax, 0FFFFFFFFh
0x180007305  movsd   [rbp+var_10], xmm1
0x18000730a  mov     word ptr [rbp+pvarg+8], ax
0x18000730e  mov     rax, [rcx]
0x180007311  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180007315  mov     rax, [rax+28h]
0x180007319  movaps  [rbp+var_20], xmm0
0x18000731d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007322  mov     ebx, eax
0x180007324  test    eax, eax
0x180007326  js      short loc_180007357
0x180007328  mov     rcx, [rbp+arg_0]
0x18000732c  lea     r8, [rbp+var_20]
0x180007330  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180007334  lea     rdx, aLockmetadata; "lockMetadata"
0x18000733b  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180007340  mov     rax, [rcx]
0x180007343  movaps  [rbp+var_20], xmm0
0x180007347  movsd   [rbp+var_10], xmm1
0x18000734c  mov     rax, [rax+28h]
0x180007350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007355  mov     ebx, eax
0x180007357  mov     rcx, [rbp+arg_0]
0x18000735b  test    rcx, rcx
0x18000735e  jz      short loc_180007374
0x180007360  mov     rax, [rcx]
0x180007363  mov     rax, [rax+10h]
0x180007367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000736c  mov     [rbp+arg_0], 0
0x180007374  lea     rcx, [rbp+pvarg]; pvarg
0x180007378  call    cs:__imp_VariantClear
0x18000737f  nop     dword ptr [rax+rax+00h]
0x180007384  mov     eax, ebx
0x180007386  mov     rbx, [rsp+60h+arg_8]
0x18000738b  add     rsp, 60h
0x18000738f  pop     rbp
0x180007390  retn
```
