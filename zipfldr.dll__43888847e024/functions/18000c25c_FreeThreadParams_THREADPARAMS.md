# FreeThreadParams(THREADPARAMS *)

- ea: `0x18000c25c`
- end: `0x18000c2dc`
- name: `?FreeThreadParams@@YAXPEAUTHREADPARAMS@@@Z`
- size: `128`
- prototype: `void __fastcall(struct THREADPARAMS *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c380`
- `0x18000c93c`
- `0x18002bf78`

## callees

- `0x18000c25c`
- `0x180071010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18000c270`
- `SHELL32!__imp_ILFree` at `0x18000c270`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c294`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c294`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c2b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c2d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c2d4`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000c2bd`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x18000c2bd`

## pseudocode

```c
void __fastcall FreeThreadParams(struct THREADPARAMS *a1)
{
  IStream *v2; // rdi
  void *v3; // rcx

  ILFree(*((LPITEMIDLIST *)a1 + 134));
  v2 = (IStream *)*((_QWORD *)a1 + 135);
  *((_QWORD *)a1 + 135) = 0;
  if ( v2 )
  {
    CoReleaseMarshalData(v2);
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v2 + 16LL))(v2);
  }
  LocalFree(*((HLOCAL *)a1 + 132));
  v3 = (void *)*((_QWORD *)a1 + 131);
  if ( v3 )
    CoTaskMemFree(v3);
  LocalFree(a1);
}

```

## disassembly

```asm
0x18000c25c  mov     [rsp+arg_0], rbx
0x18000c261  push    rdi
0x18000c262  sub     rsp, 20h
0x18000c266  mov     rbx, rcx
0x18000c269  mov     rcx, [rcx+430h]; pidl
0x18000c270  call    cs:__imp_ILFree
0x18000c276  mov     rdi, [rbx+438h]
0x18000c27d  mov     qword ptr [rbx+438h], 0
0x18000c288  test    rdi, rdi
0x18000c28b  jnz     short loc_18000C2BA
0x18000c28d  mov     rcx, [rbx+420h]; hMem
0x18000c294  call    cs:__imp_LocalFree
0x18000c29a  mov     rcx, [rbx+418h]; pv
0x18000c2a1  test    rcx, rcx
0x18000c2a4  jnz     short loc_18000C2D4
0x18000c2a6  mov     rcx, rbx
0x18000c2a9  mov     rbx, [rsp+28h+arg_0]
0x18000c2ae  add     rsp, 20h
0x18000c2b2  pop     rdi
0x18000c2b3  jmp     cs:__imp_LocalFree
0x18000c2ba  mov     rcx, rdi; pStm
0x18000c2bd  call    cs:__imp_CoReleaseMarshalData
0x18000c2c3  mov     rax, [rdi]
0x18000c2c6  mov     rcx, rdi
0x18000c2c9  mov     rax, [rax+10h]
0x18000c2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2d2  jmp     short loc_18000C28D
0x18000c2d4  call    cs:__imp_CoTaskMemFree
0x18000c2da  jmp     short loc_18000C2A6
```
