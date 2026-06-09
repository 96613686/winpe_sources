# Config_GetSubElement(IAppHostElement *,ushort const *,IAppHostElement * *)

- ea: `0x180007294`
- end: `0x180007331`
- name: `?Config_GetSubElement@@YAJPEAUIAppHostElement@@PEBGPEAPEAU1@@Z`
- size: `157`
- prototype: `__int64 __fastcall(struct IAppHostElement *, const unsigned __int16 *, struct IAppHostElement **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800073e8`
- `0x180007744`

## callees

- `0x180007294`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800072a9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800072a9`
- `OLEAUT32!__imp_SysFreeString` at `0x180007320`
- `OLEAUT32!__imp_SysFreeString` at `0x180007320`
- `iisutil!PuDbgPrintError` at `0x180007312`
- `iisutil!PuDbgPrintError` at `0x180007312`

## string_xrefs

- `0x180007301`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsite.cpp`
- `0x1800072e9`: ` Failed to Config_GetSubElement %S\n`
- `0x1800072f5`: `Config_GetSubElement`

## pseudocode

```c
__int64 __fastcall Config_GetSubElement(
        struct IAppHostElement *a1,
        const unsigned __int16 *a2,
        struct IAppHostElement **a3)
{
  BSTR v6; // rax
  OLECHAR *v7; // rbx
  int v8; // edi

  v6 = SysAllocString(a2);
  v7 = v6;
  if ( v6 )
  {
    v8 = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, struct IAppHostElement **))a1->lpVtbl->GetElementByName)(
           a1,
           v6,
           a3);
    if ( v8 >= 0 )
    {
LABEL_7:
      SysFreeString(v7);
      return (unsigned int)v8;
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
      137,
      "Config_GetSubElement",
      v8,
      " Failed to Config_GetSubElement %S\n",
      a2);
  if ( v7 )
    goto LABEL_7;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007294  push    rbx
0x180007296  push    rbp
0x180007297  push    rsi
0x180007298  push    rdi
0x180007299  sub     rsp, 48h
0x18000729d  mov     rdi, rcx
0x1800072a0  mov     rbp, r8
0x1800072a3  mov     rcx, rdx; psz
0x1800072a6  mov     rsi, rdx
0x1800072a9  call    cs:__imp_SysAllocString
0x1800072af  mov     rbx, rax
0x1800072b2  test    rax, rax
0x1800072b5  jnz     short loc_1800072BE
0x1800072b7  mov     edi, 80070008h
0x1800072bc  jmp     short loc_1800072D9
0x1800072be  mov     rax, [rdi]
0x1800072c1  mov     r8, rbp
0x1800072c4  mov     rdx, rbx
0x1800072c7  mov     rcx, rdi
0x1800072ca  mov     rax, [rax+50h]
0x1800072ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d3  mov     edi, eax
0x1800072d5  test    eax, eax
0x1800072d7  jns     short loc_18000731D
0x1800072d9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800072e0  jz      short loc_180007318
0x1800072e2  mov     rcx, cs:g_pDebug
0x1800072e9  lea     rax, aFailedToConfig_3; " Failed to Config_GetSubElement %S\n"
0x1800072f0  mov     [rsp+68h+var_38], rsi
0x1800072f5  lea     r9, aConfigGetsubel; "Config_GetSubElement"
0x1800072fc  mov     [rsp+68h+var_40], rax
0x180007301  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007308  mov     r8d, 89h
0x18000730e  mov     [rsp+68h+var_48], edi
0x180007312  call    cs:__imp_PuDbgPrintError
0x180007318  test    rbx, rbx
0x18000731b  jz      short loc_180007326
0x18000731d  mov     rcx, rbx; bstrString
0x180007320  call    cs:__imp_SysFreeString
0x180007326  mov     eax, edi
0x180007328  add     rsp, 48h
0x18000732c  pop     rdi
0x18000732d  pop     rsi
0x18000732e  pop     rbp
0x18000732f  pop     rbx
0x180007330  retn
```
