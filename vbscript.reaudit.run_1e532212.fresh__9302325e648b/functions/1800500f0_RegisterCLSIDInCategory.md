# RegisterCLSIDInCategory

- ea: `0x1800500f0`
- end: `0x1800501a4`
- name: `RegisterCLSIDInCategory`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004494c`

## callees

- `0x1800500f0`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x180050139`
- `OLE32!CoCreateInstance` at `0x180050139`

## pseudocode

```c
__int64 __fastcall RegisterCLSIDInCategory(__int64 a1, __int128 *a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // [rsp+30h] [rbp-28h] BYREF
  __int128 v7; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  v4 = CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &v6);
  if ( v4 >= 0 )
  {
    v7 = *a2;
    v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int128 *))(*(_QWORD *)v6 + 40LL))(v6, a1, 1, &v7);
  }
  if ( v6 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800500f0  mov     r11, rsp
0x1800500f3  mov     [r11+10h], rbx
0x1800500f7  mov     [r11+18h], rsi
0x1800500fb  push    rdi
0x1800500fc  sub     rsp, 50h
0x180050100  mov     rax, cs:__security_cookie
0x180050107  xor     rax, rsp
0x18005010a  mov     [rsp+58h+var_10], rax
0x18005010f  mov     rdi, rdx
0x180050112  mov     qword ptr [r11-28h], 0
0x18005011a  xor     edx, edx; pUnkOuter
0x18005011c  lea     rax, [r11-28h]
0x180050120  mov     rsi, rcx
0x180050123  mov     [r11-38h], rax
0x180050127  lea     r9, IID_ICatRegister; riid
0x18005012e  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180050135  lea     r8d, [rdx+1]; dwClsContext
0x180050139  call    cs:__imp_CoCreateInstance
0x18005013f  mov     ebx, eax
0x180050141  test    eax, eax
0x180050143  js      short loc_18005016F
0x180050145  mov     rcx, [rsp+58h+var_28]
0x18005014a  lea     r9, [rsp+58h+var_20]
0x18005014f  movaps  xmm0, xmmword ptr [rdi]
0x180050152  mov     r8d, 1
0x180050158  movdqu  [rsp+58h+var_20], xmm0
0x18005015e  mov     rdx, rsi
0x180050161  mov     rax, [rcx]
0x180050164  mov     rax, [rax+28h]
0x180050168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005016d  mov     ebx, eax
0x18005016f  mov     rcx, [rsp+58h+var_28]
0x180050174  test    rcx, rcx
0x180050177  jz      short loc_180050185
0x180050179  mov     rax, [rcx]
0x18005017c  mov     rax, [rax+10h]
0x180050180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050185  mov     eax, ebx
0x180050187  mov     rcx, [rsp+58h+var_10]
0x18005018c  xor     rcx, rsp; StackCookie
0x18005018f  call    __security_check_cookie
0x180050194  mov     rbx, [rsp+58h+arg_8]
0x180050199  mov     rsi, [rsp+58h+arg_10]
0x18005019e  add     rsp, 50h
0x1800501a2  pop     rdi
0x1800501a3  retn
```
