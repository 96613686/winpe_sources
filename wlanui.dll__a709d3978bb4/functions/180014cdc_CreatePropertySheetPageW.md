# CreatePropertySheetPageW

- ea: `0x180014cdc`
- end: `0x180014d71`
- name: `CreatePropertySheetPageW`
- size: `149`
- prototype: `HPROPSHEETPAGE __stdcall(LPCPROPSHEETPAGEW constPropSheetPagePointer)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800068e8`

## callees

- `0x180014b00`
- `0x180014cdc`
- `0x180014fd0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180014d5d`
- `KERNEL32!DeactivateActCtx` at `0x180014d5d`

## string_xrefs

- `0x180014d0b`: `CreatePropertySheetPageW`

## pseudocode

```c
HPROPSHEETPAGE __stdcall CreatePropertySheetPageW(LPCPROPSHEETPAGEW constPropSheetPagePointer)
{
  struct _PSP *v2; // rdi
  __int64 (__fastcall *v3)(LPCPROPSHEETPAGEW); // rax
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  SHActivateContext(&ulCookie);
  v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_18002E2E0;
  if ( qword_18002E2E0 == -1 )
  {
    GetProcFromComCtl32(&qword_18002E2E0, "CreatePropertySheetPageW");
    v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_18002E2E0;
  }
  if ( v3 )
  {
    if ( constPropSheetPagePointer->dwSize > 0x58 )
    {
      constPropSheetPagePointer->dwFlags |= 0x4000u;
      constPropSheetPagePointer->hActCtx = g_hActCtx;
      v3 = (__int64 (__fastcall *)(LPCPROPSHEETPAGEW))qword_18002E2E0;
    }
    v2 = (struct _PSP *)v3(constPropSheetPagePointer);
  }
  if ( ulCookie )
    DeactivateActCtx(0, ulCookie);
  return v2;
}

```

## disassembly

```asm
0x180014cdc  mov     [rsp+arg_0], rbx
0x180014ce1  push    rdi
0x180014ce2  sub     rsp, 20h
0x180014ce6  mov     rbx, rcx
0x180014ce9  mov     [rsp+28h+ulCookie], 0
0x180014cf2  lea     rcx, [rsp+28h+ulCookie]
0x180014cf7  xor     edi, edi
0x180014cf9  call    SHActivateContext
0x180014cfe  mov     rax, cs:qword_18002E2E0
0x180014d05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014d09  jnz     short loc_180014D25
0x180014d0b  lea     rdx, aCreateproperty; "CreatePropertySheetPageW"
0x180014d12  lea     rcx, qword_18002E2E0
0x180014d19  call    _GetProcFromComCtl32
0x180014d1e  mov     rax, cs:qword_18002E2E0
0x180014d25  test    rax, rax
0x180014d28  jz      short loc_180014D51
0x180014d2a  cmp     dword ptr [rbx], 58h ; 'X'
0x180014d2d  jbe     short loc_180014D46
0x180014d2f  bts     dword ptr [rbx+4], 0Eh
0x180014d34  mov     rax, cs:g_hActCtx
0x180014d3b  mov     [rbx+58h], rax
0x180014d3f  mov     rax, cs:qword_18002E2E0
0x180014d46  mov     rcx, rbx
0x180014d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d4e  mov     rdi, rax
0x180014d51  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180014d56  test    rdx, rdx
0x180014d59  jz      short loc_180014D63
0x180014d5b  xor     ecx, ecx; dwFlags
0x180014d5d  call    cs:__imp_DeactivateActCtx
0x180014d63  mov     rbx, [rsp+28h+arg_0]
0x180014d68  mov     rax, rdi
0x180014d6b  add     rsp, 20h
0x180014d6f  pop     rdi
0x180014d70  retn
```
