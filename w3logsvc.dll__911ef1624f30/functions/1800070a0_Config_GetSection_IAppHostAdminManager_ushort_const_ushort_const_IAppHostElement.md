# Config_GetSection(IAppHostAdminManager *,ushort const *,ushort const *,IAppHostElement * *)

- ea: `0x1800070a0`
- end: `0x180007169`
- name: `?Config_GetSection@@YAJPEAUIAppHostAdminManager@@PEBG1PEAPEAUIAppHostElement@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(struct IAppHostAdminManager *, const unsigned __int16 *, const unsigned __int16 *, struct IAppHostElement **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008230`
- `0x180008858`

## callees

- `0x1800070a0`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800070b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800070d5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800070b7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800070d5`
- `OLEAUT32!__imp_SysFreeString` at `0x180007148`
- `OLEAUT32!__imp_SysFreeString` at `0x180007156`
- `OLEAUT32!__imp_SysFreeString` at `0x180007148`
- `OLEAUT32!__imp_SysFreeString` at `0x180007156`
- `iisutil!PuDbgPrintError` at `0x18000713a`
- `iisutil!PuDbgPrintError` at `0x18000713a`

## string_xrefs

- `0x180007129`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsite.cpp`
- `0x180007111`: ` Failed to Config_GetSection %S\n`
- `0x18000711d`: `Config_GetSection`

## pseudocode

```c
__int64 __fastcall Config_GetSection(
        struct IAppHostAdminManager *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IAppHostElement **a4)
{
  OLECHAR *v7; // rsi
  OLECHAR *v8; // rdi
  int v9; // ebx
  BSTR v10; // rax

  v7 = SysAllocString(a2);
  if ( !v7 )
  {
    v8 = 0;
LABEL_3:
    v9 = -2147024888;
    goto LABEL_6;
  }
  v10 = SysAllocString(L"MACHINE/WEBROOT/APPHOST");
  v8 = v10;
  if ( !v10 )
    goto LABEL_3;
  v9 = ((__int64 (__fastcall *)(struct IAppHostAdminManager *, OLECHAR *, BSTR, struct IAppHostElement **))a1->lpVtbl->GetAdminSection)(
         a1,
         v7,
         v10,
         a4);
  if ( v9 >= 0 )
  {
LABEL_9:
    SysFreeString(v7);
    goto LABEL_10;
  }
LABEL_6:
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsite.cpp",
      348,
      "Config_GetSection",
      v9,
      " Failed to Config_GetSection %S\n",
      a2);
  if ( v7 )
    goto LABEL_9;
LABEL_10:
  if ( v8 )
    SysFreeString(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800070a0  push    rbx
0x1800070a2  push    rbp
0x1800070a3  push    rsi
0x1800070a4  push    rdi
0x1800070a5  push    r14
0x1800070a7  sub     rsp, 40h
0x1800070ab  mov     rbx, rcx
0x1800070ae  mov     r14, r9
0x1800070b1  mov     rcx, rdx; psz
0x1800070b4  mov     rbp, rdx
0x1800070b7  call    cs:__imp_SysAllocString
0x1800070bd  mov     rsi, rax
0x1800070c0  test    rax, rax
0x1800070c3  jnz     short loc_1800070CE
0x1800070c5  xor     edi, edi
0x1800070c7  mov     ebx, 80070008h
0x1800070cc  jmp     short loc_180007101
0x1800070ce  lea     rcx, psz; "MACHINE/WEBROOT/APPHOST"
0x1800070d5  call    cs:__imp_SysAllocString
0x1800070db  mov     rdi, rax
0x1800070de  test    rax, rax
0x1800070e1  jz      short loc_1800070C7
0x1800070e3  mov     rax, [rbx]
0x1800070e6  mov     r9, r14
0x1800070e9  mov     r8, rdi
0x1800070ec  mov     rdx, rsi
0x1800070ef  mov     rcx, rbx
0x1800070f2  mov     rax, [rax+18h]
0x1800070f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070fb  mov     ebx, eax
0x1800070fd  test    eax, eax
0x1800070ff  jns     short loc_180007145
0x180007101  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007108  jz      short loc_180007140
0x18000710a  mov     rcx, cs:g_pDebug
0x180007111  lea     rax, aFailedToConfig_2; " Failed to Config_GetSection %S\n"
0x180007118  mov     [rsp+68h+var_38], rbp
0x18000711d  lea     r9, aConfigGetsecti; "Config_GetSection"
0x180007124  mov     [rsp+68h+var_40], rax
0x180007129  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007130  mov     r8d, 15Ch
0x180007136  mov     [rsp+68h+var_48], ebx
0x18000713a  call    cs:__imp_PuDbgPrintError
0x180007140  test    rsi, rsi
0x180007143  jz      short loc_18000714E
0x180007145  mov     rcx, rsi; bstrString
0x180007148  call    cs:__imp_SysFreeString
0x18000714e  test    rdi, rdi
0x180007151  jz      short loc_18000715C
0x180007153  mov     rcx, rdi; bstrString
0x180007156  call    cs:__imp_SysFreeString
0x18000715c  mov     eax, ebx
0x18000715e  add     rsp, 40h
0x180007162  pop     r14
0x180007164  pop     rdi
0x180007165  pop     rsi
0x180007166  pop     rbp
0x180007167  pop     rbx
0x180007168  retn
```
