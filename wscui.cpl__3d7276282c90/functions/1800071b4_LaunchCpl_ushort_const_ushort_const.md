# LaunchCpl(ushort const *,ushort const *)

- ea: `0x1800071b4`
- end: `0x18000723f`
- name: `?LaunchCpl@@YA_NPEBG0@Z`
- size: `139`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006520`
- `0x180007248`

## callees

- `0x1800071b4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800071f0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800071f0`

## pseudocode

```c
char __fastcall LaunchCpl(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char v4; // bl
  int v5; // ebx
  LPVOID v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v4 = 0;
  if ( CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &v7) >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, const unsigned __int16 *, _QWORD))(*(_QWORD *)v7 + 24LL))(
           v7,
           a1,
           a2,
           0);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    return v5 >= 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800071b4  mov     r11, rsp
0x1800071b7  mov     [r11+8], rbx
0x1800071bb  mov     [r11+10h], rsi
0x1800071bf  push    rdi
0x1800071c0  sub     rsp, 30h
0x1800071c4  mov     rdi, rdx
0x1800071c7  mov     qword ptr [r11+18h], 0
0x1800071cf  xor     edx, edx; pUnkOuter
0x1800071d1  lea     rax, [r11+18h]
0x1800071d5  mov     rsi, rcx
0x1800071d8  mov     [r11-18h], rax
0x1800071dc  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x1800071e3  xor     bl, bl
0x1800071e5  lea     rcx, CLSID_OpenControlPanel; rclsid
0x1800071ec  lea     r8d, [rdx+1]; dwClsContext
0x1800071f0  call    cs:__imp_CoCreateInstance
0x1800071f6  test    eax, eax
0x1800071f8  js      short loc_18000722D
0x1800071fa  mov     rcx, [rsp+38h+arg_10]
0x1800071ff  xor     r9d, r9d
0x180007202  mov     r8, rdi
0x180007205  mov     rdx, rsi
0x180007208  mov     rax, [rcx]
0x18000720b  mov     rax, [rax+18h]
0x18000720f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007214  mov     rcx, [rsp+38h+arg_10]
0x180007219  mov     ebx, eax
0x18000721b  mov     rdx, [rcx]
0x18000721e  mov     rax, [rdx+10h]
0x180007222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007227  shr     ebx, 1Fh
0x18000722a  xor     bl, 1
0x18000722d  mov     rsi, [rsp+38h+arg_8]
0x180007232  mov     al, bl
0x180007234  mov     rbx, [rsp+38h+arg_0]
0x180007239  add     rsp, 30h
0x18000723d  pop     rdi
0x18000723e  retn
```
