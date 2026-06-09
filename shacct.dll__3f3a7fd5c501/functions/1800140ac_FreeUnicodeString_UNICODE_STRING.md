# _FreeUnicodeString(_UNICODE_STRING *)

- ea: `0x1800140ac`
- end: `0x1800140e6`
- name: `?_FreeUnicodeString@@YAXPEAU_UNICODE_STRING@@@Z`
- size: `58`
- prototype: `void __fastcall(struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800075b0`
- `0x18000bdac`

## callees

- `0x1800140ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800140cf`

## pseudocode

```c
void __fastcall _FreeUnicodeString(struct _UNICODE_STRING *a1)
{
  PWSTR Buffer; // rcx

  if ( a1 )
  {
    if ( a1->MaximumLength )
    {
      Buffer = a1->Buffer;
      if ( Buffer )
        CoTaskMemFree(Buffer);
    }
    *(_DWORD *)&a1->Length = 0;
    a1->Buffer = 0;
  }
}

```

## disassembly

```asm
0x1800140ac  test    rcx, rcx
0x1800140af  jz      short locret_1800140E5
0x1800140b1  mov     [rsp+arg_0], rbx
0x1800140b6  push    rdi
0x1800140b7  sub     rsp, 20h
0x1800140bb  xor     edi, edi
0x1800140bd  mov     rbx, rcx
0x1800140c0  cmp     [rcx+2], di
0x1800140c4  jbe     short loc_1800140D5
0x1800140c6  mov     rcx, [rcx+8]; pv
0x1800140ca  test    rcx, rcx
0x1800140cd  jz      short loc_1800140D5
0x1800140cf  call    cs:__imp_CoTaskMemFree
0x1800140d5  mov     [rbx], edi
0x1800140d7  mov     [rbx+8], rdi
0x1800140db  mov     rbx, [rsp+28h+arg_0]
0x1800140e0  add     rsp, 20h
0x1800140e4  pop     rdi
0x1800140e5  retn
```
