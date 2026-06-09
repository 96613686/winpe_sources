# MultiWorkQueueWorkCallback(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x18000e660`
- end: `0x18000e6cf`
- name: `?MultiWorkQueueWorkCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `111`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD **Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e660`
- `0x180010010`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x18000e6b1`
- `iisutil!PuDbgPrintError` at `0x18000e6b1`

## string_xrefs

- `0x18000e6a6`: `servercommon\inetsrv\iis\iisrearc\core\ap\common\multiworkqueue\multi_work_item.cxx`

## pseudocode

```c
void __fastcall MultiWorkQueueWorkCallback(PTP_CALLBACK_INSTANCE Instance, _QWORD **Context)
{
  int v3; // eax

  v3 = (*(__int64 (__fastcall **)(_QWORD *))(*Context[3] + 16LL))(Context[3]);
  if ( v3 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\common\\multiworkqueue\\multi_work_item.cxx",
      150,
      "MULTI_WORK_ITEM::Execute",
      v3,
      "Work item execution returned an error\n");
  ((void (__fastcall *)(_QWORD **, __int64))**Context)(Context, 1);
}

```

## disassembly

```asm
0x18000e660  push    rbx
0x18000e662  sub     rsp, 30h
0x18000e666  mov     rcx, [rdx+18h]
0x18000e66a  mov     rbx, rdx
0x18000e66d  mov     rax, [rcx]
0x18000e670  mov     rax, [rax+10h]
0x18000e674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e679  test    eax, eax
0x18000e67b  jns     short loc_18000E6B7
0x18000e67d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000e684  jz      short loc_18000E6B7
0x18000e686  lea     rcx, aWorkItemExecut; "Work item execution returned an error\n"
0x18000e68d  mov     r8d, 96h
0x18000e693  mov     [rsp+38h+var_10], rcx
0x18000e698  lea     r9, aMultiWorkItemE; "MULTI_WORK_ITEM::Execute"
0x18000e69f  mov     rcx, cs:g_pDebug
0x18000e6a6  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000e6ad  mov     [rsp+38h+var_18], eax
0x18000e6b1  call    cs:__imp_PuDbgPrintError
0x18000e6b7  mov     rax, [rbx]
0x18000e6ba  mov     edx, 1
0x18000e6bf  mov     rcx, rbx
0x18000e6c2  mov     rax, [rax]
0x18000e6c5  add     rsp, 30h
0x18000e6c9  pop     rbx
0x18000e6ca  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
