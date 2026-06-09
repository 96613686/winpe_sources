# Config_GetStringProperty(IAppHostElement *,ushort const *,STRU *)

- ea: `0x180007170`
- end: `0x18000728c`
- name: `?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAVSTRU@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct IAppHostElement *, const unsigned __int16 *, struct STRU *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800073e8`
- `0x180007744`
- `0x180007a44`

## callees

- `0x180007170`
- `0x180010010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180007197`
- `OLEAUT32!__imp_SysAllocString` at `0x180007197`
- `OLEAUT32!__imp_SysFreeString` at `0x180007246`
- `OLEAUT32!__imp_SysFreeString` at `0x180007259`
- `OLEAUT32!__imp_SysFreeString` at `0x180007246`
- `OLEAUT32!__imp_SysFreeString` at `0x180007259`
- `iisutil!PuDbgPrintError` at `0x180007238`
- `iisutil!PuDbgPrintError` at `0x180007238`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800071f3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800071f3`

## string_xrefs

- `0x180007227`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsite.cpp`
- `0x18000720f`: ` Failed to Config_GetStringProperty %S\n`
- `0x18000721b`: `Config_GetStringProperty`

## pseudocode

```c
__int64 __fastcall Config_GetStringProperty(struct IAppHostElement *a1, const unsigned __int16 *a2, struct STRU *a3)
{
  BSTR v6; // rax
  OLECHAR *v7; // rdi
  int v8; // ebx
  _QWORD v10[7]; // [rsp+40h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+20h] BYREF

  bstrString = 0;
  v10[0] = 0;
  v6 = SysAllocString(a2);
  v7 = v6;
  if ( v6 )
  {
    v8 = ((__int64 (__fastcall *)(struct IAppHostElement *, BSTR, _QWORD *))a1->lpVtbl->GetPropertyByName)(a1, v6, v10);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)v10[0] + 56LL))(v10[0], &bstrString);
      if ( v8 >= 0 )
      {
        v8 = STRU::Copy(a3, bstrString);
        if ( v8 >= 0 )
        {
LABEL_9:
          SysFreeString(v7);
          goto LABEL_10;
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
      201,
      "Config_GetStringProperty",
      v8,
      " Failed to Config_GetStringProperty %S\n",
      a2);
  if ( v7 )
    goto LABEL_9;
LABEL_10:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v10[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10[0] + 16LL))(v10[0]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007170  mov     rax, rsp
0x180007173  push    rbx
0x180007174  push    rbp
0x180007175  push    rsi
0x180007176  push    rdi
0x180007177  sub     rsp, 58h
0x18000717b  mov     rbx, rcx
0x18000717e  mov     qword ptr [rax+20h], 0
0x180007186  mov     rcx, rdx; psz
0x180007189  mov     qword ptr [rax-38h], 0
0x180007191  mov     rbp, r8
0x180007194  mov     rsi, rdx
0x180007197  call    cs:__imp_SysAllocString
0x18000719d  mov     rdi, rax
0x1800071a0  test    rax, rax
0x1800071a3  jnz     short loc_1800071AC
0x1800071a5  mov     ebx, 80070008h
0x1800071aa  jmp     short loc_1800071FF
0x1800071ac  mov     rax, [rbx]
0x1800071af  lea     r8, [rsp+78h+var_38]
0x1800071b4  mov     rdx, rdi
0x1800071b7  mov     rcx, rbx
0x1800071ba  mov     rax, [rax+58h]
0x1800071be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071c3  mov     ebx, eax
0x1800071c5  test    eax, eax
0x1800071c7  js      short loc_1800071FF
0x1800071c9  mov     rcx, [rsp+78h+var_38]
0x1800071ce  lea     rdx, [rsp+78h+bstrString]
0x1800071d6  mov     rax, [rcx]
0x1800071d9  mov     rax, [rax+38h]
0x1800071dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071e2  mov     ebx, eax
0x1800071e4  test    eax, eax
0x1800071e6  js      short loc_1800071FF
0x1800071e8  mov     rdx, [rsp+78h+bstrString]
0x1800071f0  mov     rcx, rbp
0x1800071f3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800071f9  mov     ebx, eax
0x1800071fb  test    eax, eax
0x1800071fd  jns     short loc_180007243
0x1800071ff  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180007206  jz      short loc_18000723E
0x180007208  mov     rcx, cs:g_pDebug
0x18000720f  lea     rax, aFailedToConfig_0; " Failed to Config_GetStringProperty %S"...
0x180007216  mov     [rsp+78h+var_48], rsi
0x18000721b  lea     r9, aConfigGetstrin; "Config_GetStringProperty"
0x180007222  mov     [rsp+78h+var_50], rax
0x180007227  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000722e  mov     r8d, 0C9h
0x180007234  mov     [rsp+78h+var_58], ebx
0x180007238  call    cs:__imp_PuDbgPrintError
0x18000723e  test    rdi, rdi
0x180007241  jz      short loc_18000724C
0x180007243  mov     rcx, rdi; bstrString
0x180007246  call    cs:__imp_SysFreeString
0x18000724c  mov     rcx, [rsp+78h+bstrString]; bstrString
0x180007254  test    rcx, rcx
0x180007257  jz      short loc_18000726B
0x180007259  call    cs:__imp_SysFreeString
0x18000725f  mov     [rsp+78h+bstrString], 0
0x18000726b  mov     rcx, [rsp+78h+var_38]
0x180007270  test    rcx, rcx
0x180007273  jz      short loc_180007281
0x180007275  mov     rax, [rcx]
0x180007278  mov     rax, [rax+10h]
0x18000727c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007281  mov     eax, ebx
0x180007283  add     rsp, 58h
0x180007287  pop     rdi
0x180007288  pop     rsi
0x180007289  pop     rbp
0x18000728a  pop     rbx
0x18000728b  retn
```
