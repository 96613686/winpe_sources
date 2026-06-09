# SecDeleteUserModeContext(_SecHandle *)

- ea: `0x18001c7b0`
- end: `0x18001c81d`
- name: `?SecDeleteUserModeContext@@YAJPEAU_SecHandle@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct _SecHandle *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003ee0`
- `0x18001c7b0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c7d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c7d0`

## pseudocode

```c
__int64 __fastcall SecDeleteUserModeContext(struct _SecHandle *a1)
{
  int v2; // ecx
  _QWORD *v3; // rdx
  unsigned int (__fastcall *v4)(ULONG_PTR); // rax
  HLOCAL *v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  if ( LsaPackageShutdown )
  {
    SetLastError(0x45Bu);
    return (unsigned int)-2146893051;
  }
  else
  {
    v2 = SecLocatePackageById((HLOCAL)a1->dwLower, &v6);
    if ( v2 >= 0 )
    {
      v3 = v6[23];
      if ( v3 )
      {
        v4 = (unsigned int (__fastcall *)(ULONG_PTR))v3[9];
        if ( v4 )
          return v4(a1->dwUpper);
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001c7b0  push    rbx
0x18001c7b2  sub     rsp, 20h
0x18001c7b6  cmp     cs:?LsaPackageShutdown@@3HA, 0; int LsaPackageShutdown
0x18001c7bd  mov     rbx, rcx
0x18001c7c0  mov     [rsp+28h+arg_8], 0
0x18001c7c9  jz      short loc_18001C7DD
0x18001c7cb  mov     ecx, 45Bh; dwErrCode
0x18001c7d0  call    cs:__imp_SetLastError
0x18001c7d6  mov     ecx, 80090305h
0x18001c7db  jmp     short loc_18001C815
0x18001c7dd  mov     rcx, [rcx]
0x18001c7e0  lea     rdx, [rsp+28h+arg_8]
0x18001c7e5  call    SecLocatePackageById
0x18001c7ea  mov     ecx, eax
0x18001c7ec  test    eax, eax
0x18001c7ee  js      short loc_18001C815
0x18001c7f0  mov     rax, [rsp+28h+arg_8]
0x18001c7f5  mov     rdx, [rax+0B8h]
0x18001c7fc  test    rdx, rdx
0x18001c7ff  jz      short loc_18001C815
0x18001c801  mov     rax, [rdx+48h]
0x18001c805  test    rax, rax
0x18001c808  jz      short loc_18001C815
0x18001c80a  mov     rcx, [rbx+8]
0x18001c80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c813  mov     ecx, eax
0x18001c815  mov     eax, ecx
0x18001c817  add     rsp, 20h
0x18001c81b  pop     rbx
0x18001c81c  retn
```
