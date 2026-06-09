# CUserAccounts::FindByName(ushort const *,IPropertyStore * *)

- ea: `0x18000ddc0`
- end: `0x18000de3a`
- name: `?FindByName@CUserAccounts@@UEAAJPEBGPEAPEAUIPropertyStore@@@Z`
- size: `122`
- prototype: `int(CUserAccounts *__hidden this, const unsigned __int16 *, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180005980`
- `0x180008230`
- `0x18000ddc0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de22`

## pseudocode

```c
__int64 __fastcall CUserAccounts::FindByName(
        CUserAccounts *this,
        const unsigned __int16 *a2,
        struct IPropertyStore **a3)
{
  int v5; // ebx
  __int64 (__fastcall *v6)(CUserAccounts *, _QWORD, struct IPropertyStore **); // rbx
  unsigned int v7; // eax
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  pv = 0;
  v5 = LookupName(a2, &pv);
  if ( v5 >= 0 )
  {
    v6 = *(__int64 (__fastcall **)(CUserAccounts *, _QWORD, struct IPropertyStore **))(*(_QWORD *)this + 80LL);
    v7 = RIDFromSID(pv);
    v5 = v6(this, v7, a3);
    CoTaskMemFree(pv);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ddc0  mov     r11, rsp
0x18000ddc3  mov     [r11+8], rbx
0x18000ddc7  mov     [r11+10h], rsi
0x18000ddcb  push    rdi
0x18000ddcc  sub     rsp, 20h
0x18000ddd0  mov     rax, rdx
0x18000ddd3  mov     qword ptr [r8], 0
0x18000ddda  mov     rsi, rcx
0x18000dddd  mov     qword ptr [r11+18h], 0
0x18000dde5  mov     rcx, rax; unsigned __int16 *
0x18000dde8  lea     rdx, [r11+18h]; void **
0x18000ddec  mov     rdi, r8
0x18000ddef  call    ?LookupName@@YAJPEBGPEAPEAX@Z; LookupName(ushort const *,void * *)
0x18000ddf4  mov     ebx, eax
0x18000ddf6  test    eax, eax
0x18000ddf8  js      short loc_18000DE28
0x18000ddfa  mov     rax, [rsi]
0x18000ddfd  mov     rcx, [rsp+28h+pv]; pSid
0x18000de02  mov     rbx, [rax+50h]
0x18000de06  call    ?RIDFromSID@@YAKQEAX@Z; RIDFromSID(void * const)
0x18000de0b  mov     edx, eax
0x18000de0d  mov     r8, rdi
0x18000de10  mov     rax, rbx
0x18000de13  mov     rcx, rsi
0x18000de16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de1b  mov     rcx, [rsp+28h+pv]; pv
0x18000de20  mov     ebx, eax
0x18000de22  call    cs:__imp_CoTaskMemFree
0x18000de28  mov     rsi, [rsp+28h+arg_8]
0x18000de2d  mov     eax, ebx
0x18000de2f  mov     rbx, [rsp+28h+arg_0]
0x18000de34  add     rsp, 20h
0x18000de38  pop     rdi
0x18000de39  retn
```
