# Config_GetBoolProperty(IAppHostElement *,ushort const *,int *)

- ea: `0x180006df8`
- end: `0x180006f43`
- name: `?Config_GetBoolProperty@@YAJPEAUIAppHostElement@@PEBGPEAH@Z`
- size: `331`
- prototype: `__int64 __fastcall(struct IAppHostElement *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007338`
- `0x180007744`

## callees

- `0x180006df8`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180006e38`
- `OLEAUT32!__imp_SysAllocString` at `0x180006e38`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ea0`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ea0`
- `OLEAUT32!__imp_VariantInit` at `0x180006e2f`
- `OLEAUT32!__imp_VariantInit` at `0x180006e2f`
- `OLEAUT32!__imp_VariantClear` at `0x180006e92`
- `OLEAUT32!__imp_VariantClear` at `0x180006e92`
- `OLEAUT32!__imp_VariantChangeType` at `0x180006f21`
- `OLEAUT32!__imp_VariantChangeType` at `0x180006f21`
- `iisutil!PuDbgPrintError` at `0x180006e88`
- `iisutil!PuDbgPrintError` at `0x180006e88`

## string_xrefs

- `0x180006e77`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsite.cpp`
- `0x180006e5f`: ` Failed to Config_GetBoolProperty %S\n`
- `0x180006e6b`: `Config_GetBoolProperty`

## pseudocode

```c
__int64 __fastcall Config_GetBoolProperty(struct IAppHostElement *a1, const unsigned __int16 *a2, int *a3)
{
  BSTR v6; // rax
  OLECHAR *v7; // rdi
  HRESULT v8; // ebx
  VARIANTARG pvarg; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+98h] [rbp+38h] BYREF

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
        {
          *a3 = pvarg.iVal == -1;
          goto LABEL_5;
        }
      }
    }
  }
  else
  {
    v8 = -2147024888;
  }
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsite.cpp",
      284,
      "Config_GetBoolProperty",
      v8,
      " Failed to Config_GetBoolProperty %S\n",
      a2);
LABEL_5:
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
0x180006df8  mov     [rsp-18h+arg_0], rbx
0x180006dfd  mov     [rsp-18h+arg_8], rsi
0x180006e02  push    rbp
0x180006e03  push    rdi
0x180006e04  push    r14
0x180006e06  mov     rbp, rsp
0x180006e09  sub     rsp, 60h
0x180006e0d  mov     rbx, rcx
0x180006e10  mov     [rbp+arg_18], 0
0x180006e18  xorps   xmm0, xmm0
0x180006e1b  lea     rcx, [rbp+pvarg]; pvarg
0x180006e1f  xor     eax, eax
0x180006e21  mov     r14, r8
0x180006e24  movups  xmmword ptr [rbp+pvarg], xmm0
0x180006e28  mov     qword ptr [rbp+pvarg+10h], rax
0x180006e2c  mov     rsi, rdx
0x180006e2f  call    cs:__imp_VariantInit
0x180006e35  mov     rcx, rsi; psz
0x180006e38  call    cs:__imp_SysAllocString
0x180006e3e  mov     rdi, rax
0x180006e41  test    rax, rax
0x180006e44  jnz     loc_180006ED2
0x180006e4a  mov     ebx, 80070008h
0x180006e4f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006e56  jz      short loc_180006E8E
0x180006e58  mov     rcx, cs:g_pDebug
0x180006e5f  lea     rax, aFailedToConfig_1; " Failed to Config_GetBoolProperty %S\n"
0x180006e66  mov     [rsp+60h+var_30], rsi
0x180006e6b  lea     r9, aConfigGetboolp; "Config_GetBoolProperty"
0x180006e72  mov     [rsp+60h+var_38], rax
0x180006e77  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006e7e  mov     r8d, 11Ch
0x180006e84  mov     [rsp+60h+var_40], ebx
0x180006e88  call    cs:__imp_PuDbgPrintError
0x180006e8e  lea     rcx, [rbp+pvarg]; pvarg
0x180006e92  call    cs:__imp_VariantClear
0x180006e98  test    rdi, rdi
0x180006e9b  jz      short loc_180006EA6
0x180006e9d  mov     rcx, rdi; bstrString
0x180006ea0  call    cs:__imp_SysFreeString
0x180006ea6  mov     rcx, [rbp+arg_18]
0x180006eaa  test    rcx, rcx
0x180006ead  jz      short loc_180006EBB
0x180006eaf  mov     rax, [rcx]
0x180006eb2  mov     rax, [rax+10h]
0x180006eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ebb  lea     r11, [rsp+60h+var_s0]
0x180006ec0  mov     eax, ebx
0x180006ec2  mov     rbx, [r11+20h]
0x180006ec6  mov     rsi, [r11+28h]
0x180006eca  mov     rsp, r11
0x180006ecd  pop     r14
0x180006ecf  pop     rdi
0x180006ed0  pop     rbp
0x180006ed1  retn
0x180006ed2  mov     rax, [rbx]
0x180006ed5  lea     r8, [rbp+arg_18]
0x180006ed9  mov     rdx, rdi
0x180006edc  mov     rcx, rbx
0x180006edf  mov     rax, [rax+58h]
0x180006ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ee8  mov     ebx, eax
0x180006eea  test    eax, eax
0x180006eec  js      loc_180006E4F
0x180006ef2  mov     rcx, [rbp+arg_18]
0x180006ef6  lea     rdx, [rbp+pvarg]
0x180006efa  mov     rax, [rcx]
0x180006efd  mov     rax, [rax+20h]
0x180006f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f06  mov     ebx, eax
0x180006f08  test    eax, eax
0x180006f0a  js      loc_180006E4F
0x180006f10  mov     r9d, 0Bh; vt
0x180006f16  lea     rdx, [rbp+pvarg]; pvarSrc
0x180006f1a  xor     r8d, r8d; wFlags
0x180006f1d  lea     rcx, [rbp+pvarg]; pvargDest
0x180006f21  call    cs:__imp_VariantChangeType
0x180006f27  mov     ebx, eax
0x180006f29  test    eax, eax
0x180006f2b  js      loc_180006E4F
0x180006f31  xor     eax, eax
0x180006f33  cmp     word ptr [rbp+pvarg+8], 0FFFFh
0x180006f38  setz    al
0x180006f3b  mov     [r14], eax
0x180006f3e  jmp     loc_180006E8E
```
