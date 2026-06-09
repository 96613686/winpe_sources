# DllCanUnloadNow

- ea: `0x18001c230`
- end: `0x18001c2f3`
- name: `DllCanUnloadNow`
- size: `195`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001ec0`
- `0x18001b238`
- `0x18001b3a4`
- `0x18001c230`
- `0x180037010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18001c29c`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18001c29c`

## string_xrefs

- `0x18001c24b`: `DllCanUnloadNow`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT CanUnloadNow; // eax
  _BOOL8 v1; // rbx
  int v2; // eax
  BOOL v4; // [rsp+20h] [rbp-40h] BYREF
  int v5; // [rsp+24h] [rbp-3Ch] BYREF
  _QWORD *v6; // [rsp+28h] [rbp-38h] BYREF
  _QWORD v7[3]; // [rsp+30h] [rbp-30h] BYREF
  char v8[16]; // [rsp+48h] [rbp-18h] BYREF

  v4 = 0;
  v7[0] = v8;
  v5 = 0;
  v7[1] = &v5;
  v7[2] = &v4;
  strcpy(v8, "DllCanUnloadNow");
  lambda_8c4291b8468c6a263ea730b1ce0a4e3b_::operator()(v7);
  v5 = 1;
  v6 = v7;
  CanUnloadNow = NdrDllCanUnloadNow(&gPFactory);
  v4 = CanUnloadNow;
  LODWORD(v1) = CanUnloadNow;
  if ( CanUnloadNow >= 0 && CanUnloadNow != 1 )
  {
    v2 = (*(__int64 (__fastcall **)(void *))(g_module + 24LL))(&g_module);
    v1 = v2 != 0;
    v4 = v2 != 0;
  }
  WppTraceUnwinder__lambda_8c4291b8468c6a263ea730b1ce0a4e3b____::_WppTraceUnwinder__lambda_8c4291b8468c6a263ea730b1ce0a4e3b____(&v6);
  return v1;
}

```

## disassembly

```asm
0x18001c230  mov     [rsp-8+arg_0], rbx
0x18001c235  push    rbp
0x18001c236  mov     rbp, rsp
0x18001c239  sub     rsp, 60h
0x18001c23d  mov     rax, cs:__security_cookie
0x18001c244  xor     rax, rsp
0x18001c247  mov     [rbp+var_8], rax
0x18001c24b  movups  xmm0, xmmword ptr cs:aDllcanunloadno_0; "DllCanUnloadNow"
0x18001c252  lea     rax, [rbp+var_18]
0x18001c256  mov     [rbp+var_40], 0
0x18001c25d  mov     [rbp+var_30], rax
0x18001c261  lea     rcx, [rbp+var_30]
0x18001c265  lea     rax, [rbp+var_3C]
0x18001c269  mov     [rbp+var_3C], 0
0x18001c270  mov     [rbp+var_28], rax
0x18001c274  lea     rax, [rbp+var_40]
0x18001c278  mov     [rbp+var_20], rax
0x18001c27c  movdqu  [rbp+var_18], xmm0
0x18001c281  call    _lambda_8c4291b8468c6a263ea730b1ce0a4e3b___operator__
0x18001c286  lea     rax, [rbp+var_30]
0x18001c28a  mov     [rbp+var_3C], 1
0x18001c291  lea     rcx, gPFactory; pPSFactoryBuffer
0x18001c298  mov     [rbp+var_38], rax
0x18001c29c  call    cs:__imp_NdrDllCanUnloadNow
0x18001c2a2  mov     [rbp+var_40], eax
0x18001c2a5  mov     ebx, eax
0x18001c2a7  test    eax, eax
0x18001c2a9  js      short loc_18001C2D1
0x18001c2ab  cmp     eax, 1
0x18001c2ae  jz      short loc_18001C2D1
0x18001c2b0  mov     rax, cs:?g_module@@3VTpmVCardManagerModule@@A; TpmVCardManagerModule g_module
0x18001c2b7  lea     rcx, ?g_module@@3VTpmVCardManagerModule@@A; TpmVCardManagerModule g_module
0x18001c2be  mov     rax, [rax+18h]
0x18001c2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2c7  xor     ebx, ebx
0x18001c2c9  test    eax, eax
0x18001c2cb  setnz   bl
0x18001c2ce  mov     [rbp+var_40], ebx
0x18001c2d1  lea     rcx, [rbp+var_38]
0x18001c2d5  call    WppTraceUnwinder__lambda_8c4291b8468c6a263ea730b1ce0a4e3b_______WppTraceUnwinder__lambda_8c4291b8468c6a263ea730b1ce0a4e3b____
0x18001c2da  mov     eax, ebx
0x18001c2dc  mov     rcx, [rbp+var_8]
0x18001c2e0  xor     rcx, rsp; StackCookie
0x18001c2e3  call    __security_check_cookie
0x18001c2e8  mov     rbx, [rsp+60h+arg_0]
0x18001c2ed  add     rsp, 60h
0x18001c2f1  pop     rbp
0x18001c2f2  retn
```
