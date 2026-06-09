# DoAbortItems(ulong,_GUID const *)

- ea: `0x180018d04`
- end: `0x180018d90`
- name: `?DoAbortItems@@YAJKPEBU_GUID@@@Z`
- size: `140`
- prototype: `__int64 __fastcall(unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018a30`

## callees

- `0x180018d04`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180018d42`
- `ole32!CoCreateInstance` at `0x180018d42`

## pseudocode

```c
__int64 __fastcall DoAbortItems(unsigned int a1, const struct _GUID *a2)
{
  unsigned int v4; // ebx
  LPVOID v6; // [rsp+50h] [rbp+18h] BYREF

  if ( !a1 || !a2 )
    return 2147942487LL;
  v6 = 0;
  if ( CoCreateInstance(&CLSID_SubscriptionThrottler, 0, 5u, &IID_ISubscriptionThrottler, &v6) < 0 )
  {
    return 1;
  }
  else
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const struct _GUID *))(*(_QWORD *)v6 + 32LL))(v6, a1, a2);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180018d04  mov     r11, rsp
0x180018d07  mov     [r11+8], rbx
0x180018d0b  push    rdi
0x180018d0c  sub     rsp, 30h
0x180018d10  mov     rbx, rdx
0x180018d13  mov     edi, ecx
0x180018d15  test    ecx, ecx
0x180018d17  jz      short loc_180018D80
0x180018d19  test    rdx, rdx
0x180018d1c  jz      short loc_180018D80
0x180018d1e  xor     edx, edx; pUnkOuter
0x180018d20  mov     qword ptr [r11+18h], 0
0x180018d28  lea     rax, [r11+18h]
0x180018d2c  lea     r9, IID_ISubscriptionThrottler; riid
0x180018d33  mov     [r11-18h], rax
0x180018d37  lea     rcx, CLSID_SubscriptionThrottler; rclsid
0x180018d3e  lea     r8d, [rdx+5]; dwClsContext
0x180018d42  call    cs:__imp_CoCreateInstance
0x180018d48  test    eax, eax
0x180018d4a  js      short loc_180018D77
0x180018d4c  mov     rcx, [rsp+38h+arg_10]
0x180018d51  mov     r8, rbx
0x180018d54  mov     edx, edi
0x180018d56  mov     rax, [rcx]
0x180018d59  mov     rax, [rax+20h]
0x180018d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d62  mov     rcx, [rsp+38h+arg_10]
0x180018d67  mov     ebx, eax
0x180018d69  mov     rdx, [rcx]
0x180018d6c  mov     rax, [rdx+10h]
0x180018d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018d75  jmp     short loc_180018D7C
0x180018d77  mov     ebx, 1
0x180018d7c  mov     eax, ebx
0x180018d7e  jmp     short loc_180018D85
0x180018d80  mov     eax, 80070057h
0x180018d85  mov     rbx, [rsp+38h+arg_0]
0x180018d8a  add     rsp, 30h
0x180018d8e  pop     rdi
0x180018d8f  retn
```
