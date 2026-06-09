# LOG_SVC_CONFIG_CHANGE_HANDLER::OnSectionChanges(ushort *,ushort *)

- ea: `0x18000c860`
- end: `0x18000c8e3`
- name: `?OnSectionChanges@LOG_SVC_CONFIG_CHANGE_HANDLER@@UEAAJPEAG0@Z`
- size: `131`
- prototype: `__int64 __fastcall(LOG_SVC_CONFIG_CHANGE_HANDLER *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c860`
- `0x18000e4c4`

## import_xrefs

- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18000c870`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x18000c870`
- `iisutil!PuDbgPrintError` at `0x18000c8d5`
- `iisutil!PuDbgPrintError` at `0x18000c8d5`

## string_xrefs

- `0x18000c8b1`: `Couldn't queue HttpLogSiteTableConfigChangeWorkItem\n`
- `0x18000c8bd`: `LOG_SVC_CONFIG_CHANGE_HANDLER::OnSectionChanges`
- `0x18000c8ce`: `servercommon\inetsrv\iis\iisrearc\core\ap\logsvc\dll\logsvcadmin.cpp`

## pseudocode

```c
__int64 __fastcall LOG_SVC_CONFIG_CHANGE_HANDLER::OnSectionChanges(
        LOG_SVC_CONFIG_CHANGE_HANDLER *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  int v4; // ebx

  if ( !IsStringEqualOrdinalIgnoreCase(a3, L"MACHINE/WEBROOT/APPHOST") )
    return 0;
  v4 = MULTI_WORK_QUEUE::GetAndQueueWorkItem(
         (MULTI_WORK_QUEUE *)((char *)g_pLogSvcAdmin + 1584),
         (struct MULTI_WORK_DISPATCH *)((char *)g_pLogSvcAdmin + 40),
         1);
  if ( v4 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\logsvc\\dll\\logsvcadmin.cpp",
      100,
      "LOG_SVC_CONFIG_CHANGE_HANDLER::OnSectionChanges",
      v4,
      "Couldn't queue HttpLogSiteTableConfigChangeWorkItem\n");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c860  push    rbx
0x18000c862  sub     rsp, 30h
0x18000c866  lea     rdx, psz; "MACHINE/WEBROOT/APPHOST"
0x18000c86d  mov     rcx, r8
0x18000c870  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x18000c876  test    al, al
0x18000c878  jnz     short loc_18000C87E
0x18000c87a  xor     eax, eax
0x18000c87c  jmp     short loc_18000C8DD
0x18000c87e  mov     rcx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x18000c885  mov     r8d, 1; unsigned __int64
0x18000c88b  lea     rdx, [rcx+28h]; struct MULTI_WORK_DISPATCH *
0x18000c88f  add     rcx, 630h; this
0x18000c896  call    ?GetAndQueueWorkItem@MULTI_WORK_QUEUE@@QEAAJPEAVMULTI_WORK_DISPATCH@@_K@Z; MULTI_WORK_QUEUE::GetAndQueueWorkItem(MULTI_WORK_DISPATCH *,unsigned __int64)
0x18000c89b  mov     ebx, eax
0x18000c89d  test    eax, eax
0x18000c89f  jns     short loc_18000C8DB
0x18000c8a1  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000c8a8  jz      short loc_18000C8DB
0x18000c8aa  mov     rcx, cs:g_pDebug
0x18000c8b1  lea     rax, aCouldnTQueueHt_2; "Couldn't queue HttpLogSiteTableConfigCh"...
0x18000c8b8  mov     [rsp+38h+var_10], rax
0x18000c8bd  lea     r9, aLogSvcConfigCh; "LOG_SVC_CONFIG_CHANGE_HANDLER::OnSectio"...
0x18000c8c4  mov     r8d, 64h ; 'd'
0x18000c8ca  mov     [rsp+38h+var_18], ebx
0x18000c8ce  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000c8d5  call    cs:__imp_PuDbgPrintError
0x18000c8db  mov     eax, ebx
0x18000c8dd  add     rsp, 30h
0x18000c8e1  pop     rbx
0x18000c8e2  retn
```
