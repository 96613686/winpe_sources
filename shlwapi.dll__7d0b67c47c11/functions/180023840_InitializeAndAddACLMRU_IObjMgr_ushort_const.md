# InitializeAndAddACLMRU(IObjMgr *,ushort const *)

- ea: `0x180023840`
- end: `0x180023939`
- name: `?InitializeAndAddACLMRU@@YAJPEAUIObjMgr@@PEBG@Z`
- size: `249`
- prototype: `__int64 __fastcall(struct IObjMgr *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180022f58`

## callees

- `0x180012550`
- `0x180023840`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023889`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023889`

## pseudocode

```c
__int64 __fastcall InitializeAndAddACLMRU(struct IObjMgr *a1, const unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  v4 = CoCreateInstance(&CLSID_ACLCustomMRU, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, &v6);
  if ( v4 >= 0 )
  {
    v7 = 0;
    v4 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v6)(
           v6,
           &GUID_f729fc5e_8769_4f3e_bdb2_d7b50fd2275b,
           &v7);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v7 + 24LL))(v7, a2, 26);
      if ( v4 >= 0 )
        ((void (__fastcall *)(struct IObjMgr *, LPVOID))a1->lpVtbl[1].Remove)(a1, v6);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180023840  mov     r11, rsp
0x180023843  mov     [r11+18h], rbx
0x180023847  mov     [r11+20h], rsi
0x18002384b  push    rdi
0x18002384c  sub     rsp, 50h
0x180023850  mov     rax, cs:__security_cookie
0x180023857  xor     rax, rsp
0x18002385a  mov     [rsp+58h+var_18], rax
0x18002385f  mov     rsi, rdx
0x180023862  mov     qword ptr [r11-28h], 0
0x18002386a  xor     edx, edx; pUnkOuter
0x18002386c  lea     rax, [r11-28h]
0x180023870  mov     rdi, rcx
0x180023873  mov     [r11-38h], rax
0x180023877  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002387e  lea     rcx, CLSID_ACLCustomMRU; rclsid
0x180023885  lea     r8d, [rdx+1]; dwClsContext
0x180023889  call    cs:__imp_CoCreateInstance
0x18002388f  mov     ebx, eax
0x180023891  test    eax, eax
0x180023893  js      loc_18002391A
0x180023899  mov     rcx, [rsp+58h+var_28]
0x18002389e  lea     r8, [rsp+58h+var_20]
0x1800238a3  mov     [rsp+58h+var_20], 0
0x1800238ac  lea     rdx, _GUID_f729fc5e_8769_4f3e_bdb2_d7b50fd2275b
0x1800238b3  mov     rax, [rcx]
0x1800238b6  mov     rax, [rax]
0x1800238b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238be  mov     ebx, eax
0x1800238c0  test    eax, eax
0x1800238c2  js      short loc_180023909
0x1800238c4  mov     rcx, [rsp+58h+var_20]
0x1800238c9  mov     r8d, 1Ah
0x1800238cf  mov     rdx, rsi
0x1800238d2  mov     rax, [rcx]
0x1800238d5  mov     rax, [rax+18h]
0x1800238d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238de  mov     ebx, eax
0x1800238e0  test    eax, eax
0x1800238e2  js      short loc_1800238F8
0x1800238e4  mov     rax, [rdi]
0x1800238e7  mov     rcx, rdi
0x1800238ea  mov     rdx, [rsp+58h+var_28]
0x1800238ef  mov     rax, [rax+18h]
0x1800238f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238f8  mov     rcx, [rsp+58h+var_20]
0x1800238fd  mov     rax, [rcx]
0x180023900  mov     rax, [rax+10h]
0x180023904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023909  mov     rcx, [rsp+58h+var_28]
0x18002390e  mov     rax, [rcx]
0x180023911  mov     rax, [rax+10h]
0x180023915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002391a  mov     eax, ebx
0x18002391c  mov     rcx, [rsp+58h+var_18]
0x180023921  xor     rcx, rsp; StackCookie
0x180023924  call    __security_check_cookie
0x180023929  mov     rbx, [rsp+58h+arg_10]
0x18002392e  mov     rsi, [rsp+58h+arg_18]
0x180023933  add     rsp, 50h
0x180023937  pop     rdi
0x180023938  retn
```
