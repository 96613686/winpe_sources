# CNetDiagHelperImpl::GetDiagnosticsInfo(tagDiagnosticsInfo * *)

- ea: `0x1800122f0`
- end: `0x18001233c`
- name: `?GetDiagnosticsInfo@CNetDiagHelperImpl@@UEAAJPEAPEAUtagDiagnosticsInfo@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, struct tagDiagnosticsInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800122f0`
- `0x180012ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012308`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012308`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetDiagnosticsInfo(CNetDiagHelperImpl *this, struct tagDiagnosticsInfo **a2)
{
  struct tagDiagnosticsInfo *v3; // rax

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  v3 = (struct tagDiagnosticsInfo *)CoTaskMemAlloc(8u);
  *a2 = v3;
  if ( !v3 )
    return 2147942414LL;
  v3->cost = 0;
  (*a2)->flags = 0x40000000;
  return 0;
}

```

## disassembly

```asm
0x1800122f0  push    rbx
0x1800122f2  sub     rsp, 20h
0x1800122f6  mov     rbx, rdx
0x1800122f9  test    rdx, rdx
0x1800122fc  jnz     short loc_180012303
0x1800122fe  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180012303  mov     ecx, 8; cb
0x180012308  call    cs:__imp_CoTaskMemAlloc
0x18001230f  nop     dword ptr [rax+rax+00h]
0x180012314  mov     [rbx], rax
0x180012317  test    rax, rax
0x18001231a  jnz     short loc_180012323
0x18001231c  mov     eax, 8007000Eh
0x180012321  jmp     short loc_180012335
0x180012323  mov     dword ptr [rax], 0
0x180012329  mov     rax, [rbx]
0x18001232c  mov     dword ptr [rax+4], 40000000h
0x180012333  xor     eax, eax
0x180012335  add     rsp, 20h
0x180012339  pop     rbx
0x18001233a  retn
```
