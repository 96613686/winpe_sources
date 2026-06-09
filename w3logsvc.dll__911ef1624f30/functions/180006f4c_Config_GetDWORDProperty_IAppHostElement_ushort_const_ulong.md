# Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)

- ea: `0x180006f4c`
- end: `0x180007097`
- name: `?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z`
- size: `331`
- prototype: `__int64 __fastcall(struct IAppHostElement *, const unsigned __int16 *, unsigned int *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800073e8`
- `0x180007744`
- `0x180007a44`
- `0x180008230`
- `0x180008858`

## callees

- `0x180006f4c`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180006f8c`
- `OLEAUT32!__imp_SysAllocString` at `0x180006f8c`
- `OLEAUT32!__imp_SysFreeString` at `0x180007011`
- `OLEAUT32!__imp_SysFreeString` at `0x180007011`
- `OLEAUT32!__imp_VariantInit` at `0x180006f83`
- `OLEAUT32!__imp_VariantInit` at `0x180006f83`
- `OLEAUT32!__imp_VariantClear` at `0x180006fe6`
- `OLEAUT32!__imp_VariantClear` at `0x180006fe6`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000707d`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000707d`
- `iisutil!PuDbgPrintError` at `0x180006fdc`
- `iisutil!PuDbgPrintError` at `0x180006fdc`

## string_xrefs

- `0x180006fb3`: ` Failed to Config_GetDWORDProperty %S\n`
- `0x180006fbf`: `Config_GetDWORDProperty`
- `0x180006fcb`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsite.cpp`

## pseudocode

```c
__int64 __fastcall Config_GetDWORDProperty(struct IAppHostElement *a1, const unsigned __int16 *a2, unsigned int *a3)
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
        v8 = VariantChangeType(&pvarg, &pvarg, 0, 0x13u);
        if ( v8 >= 0 )
        {
          *a3 = pvarg.cyVal.Lo;
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
      79,
      "Config_GetDWORDProperty",
      v8,
      " Failed to Config_GetDWORDProperty %S\n",
      a2);
LABEL_5:
  VariantClear(&pvarg);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006f4c  mov     [rsp-18h+arg_0], rbx
0x180006f51  mov     [rsp-18h+arg_8], rsi
0x180006f56  push    rbp
0x180006f57  push    rdi
0x180006f58  push    r14
0x180006f5a  mov     rbp, rsp
0x180006f5d  sub     rsp, 60h
0x180006f61  mov     rbx, rcx
0x180006f64  mov     [rbp+arg_18], 0
0x180006f6c  xorps   xmm0, xmm0
0x180006f6f  lea     rcx, [rbp+pvarg]; pvarg
0x180006f73  xor     eax, eax
0x180006f75  mov     rsi, r8
0x180006f78  movups  xmmword ptr [rbp+pvarg], xmm0
0x180006f7c  mov     qword ptr [rbp+pvarg+10h], rax
0x180006f80  mov     r14, rdx
0x180006f83  call    cs:__imp_VariantInit
0x180006f89  mov     rcx, r14; psz
0x180006f8c  call    cs:__imp_SysAllocString
0x180006f92  mov     rdi, rax
0x180006f95  test    rax, rax
0x180006f98  jnz     loc_18000702E
0x180006f9e  mov     ebx, 80070008h
0x180006fa3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180006faa  jz      short loc_180006FE2
0x180006fac  mov     rcx, cs:g_pDebug
0x180006fb3  lea     rax, aFailedToConfig; " Failed to Config_GetDWORDProperty %S\n"
0x180006fba  mov     [rsp+60h+var_30], r14
0x180006fbf  lea     r9, aConfigGetdword; "Config_GetDWORDProperty"
0x180006fc6  mov     [rsp+60h+var_38], rax
0x180006fcb  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006fd2  mov     r8d, 4Fh ; 'O'
0x180006fd8  mov     [rsp+60h+var_40], ebx
0x180006fdc  call    cs:__imp_PuDbgPrintError
0x180006fe2  lea     rcx, [rbp+pvarg]; pvarg
0x180006fe6  call    cs:__imp_VariantClear
0x180006fec  mov     rcx, [rbp+arg_18]
0x180006ff0  test    rcx, rcx
0x180006ff3  jz      short loc_180007009
0x180006ff5  mov     rax, [rcx]
0x180006ff8  mov     rax, [rax+10h]
0x180006ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007001  mov     [rbp+arg_18], 0
0x180007009  test    rdi, rdi
0x18000700c  jz      short loc_180007017
0x18000700e  mov     rcx, rdi; bstrString
0x180007011  call    cs:__imp_SysFreeString
0x180007017  lea     r11, [rsp+60h+var_s0]
0x18000701c  mov     eax, ebx
0x18000701e  mov     rbx, [r11+20h]
0x180007022  mov     rsi, [r11+28h]
0x180007026  mov     rsp, r11
0x180007029  pop     r14
0x18000702b  pop     rdi
0x18000702c  pop     rbp
0x18000702d  retn
0x18000702e  mov     rax, [rbx]
0x180007031  lea     r8, [rbp+arg_18]
0x180007035  mov     rdx, rdi
0x180007038  mov     rcx, rbx
0x18000703b  mov     rax, [rax+58h]
0x18000703f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007044  mov     ebx, eax
0x180007046  test    eax, eax
0x180007048  js      loc_180006FA3
0x18000704e  mov     rcx, [rbp+arg_18]
0x180007052  lea     rdx, [rbp+pvarg]
0x180007056  mov     rax, [rcx]
0x180007059  mov     rax, [rax+20h]
0x18000705d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007062  mov     ebx, eax
0x180007064  test    eax, eax
0x180007066  js      loc_180006FA3
0x18000706c  mov     r9d, 13h; vt
0x180007072  lea     rdx, [rbp+pvarg]; pvarSrc
0x180007076  xor     r8d, r8d; wFlags
0x180007079  lea     rcx, [rbp+pvarg]; pvargDest
0x18000707d  call    cs:__imp_VariantChangeType
0x180007083  mov     ebx, eax
0x180007085  test    eax, eax
0x180007087  js      loc_180006FA3
0x18000708d  mov     eax, dword ptr [rbp+pvarg+8]
0x180007090  mov     [rsi], eax
0x180007092  jmp     loc_180006FE2
```
