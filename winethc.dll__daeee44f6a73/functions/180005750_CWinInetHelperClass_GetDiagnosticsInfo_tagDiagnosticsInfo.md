# CWinInetHelperClass::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x180005750`
- end: `0x18000578f`
- name: `?GetDiagnosticsInfo@CWinInetHelperClass@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `63`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000575e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000575e`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::GetDiagnosticsInfo(CWinInetHelperClass *this, struct tagDiagnosticsInfo **a2)
{
  struct tagDiagnosticsInfo *v3; // rax

  v3 = (struct tagDiagnosticsInfo *)CoTaskMemAlloc(8u);
  if ( !v3 )
    return 2147942414LL;
  v3->cost = 0;
  v3->flags = -1073741824;
  *a2 = v3;
  return 0;
}

```

## disassembly

```asm
0x180005750  push    rbx
0x180005752  sub     rsp, 20h
0x180005756  mov     ecx, 8; cb
0x18000575b  mov     rbx, rdx
0x18000575e  call    cs:__imp_CoTaskMemAlloc
0x180005765  nop     dword ptr [rax+rax+00h]
0x18000576a  test    rax, rax
0x18000576d  jnz     short loc_180005776
0x18000576f  mov     eax, 8007000Eh
0x180005774  jmp     short loc_180005788
0x180005776  mov     dword ptr [rax], 0
0x18000577c  mov     dword ptr [rax+4], 0C0000000h
0x180005783  mov     [rbx], rax
0x180005786  xor     eax, eax
0x180005788  add     rsp, 20h
0x18000578c  pop     rbx
0x18000578d  retn
```
