# CFirewall::Initialize(void)

- ea: `0x180006d20`
- end: `0x180006e5b`
- name: `?Initialize@CFirewall@@QEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(CFirewall *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006d20`
- `0x180006f7c`
- `0x180031010`

## import_xrefs

- `OLE32!CoInitializeEx` at `0x180006d6e`
- `OLE32!CoInitializeEx` at `0x180006d6e`
- `OLE32!CoCreateInstance` at `0x180006d55`
- `OLE32!CoCreateInstance` at `0x180006daf`
- `OLE32!CoCreateInstance` at `0x180006d55`
- `OLE32!CoCreateInstance` at `0x180006daf`

## pseudocode

```c
__int64 __fastcall CFirewall::Initialize(CFirewall *this)
{
  __int64 v2; // rdx
  __int64 v3; // rbx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  ppv = 0;
  v12 = 0;
  LODWORD(v3) = CoCreateInstance(
                  &GUID_304ce942_6e39_40d8_943a_b913c40c9cd4,
                  0,
                  1u,
                  &GUID_f7898af5_cac4_4632_a2ec_da06e5111af2,
                  &ppv);
  if ( (_DWORD)v3 == -2147221008 )
  {
    v3 = (unsigned int)CoInitializeEx(0, 0);
    if ( (int)ElValidateHr(v3, v5, v6, 67) < 0 )
      goto LABEL_7;
    LODWORD(v3) = CoCreateInstance(
                    &GUID_304ce942_6e39_40d8_943a_b913c40c9cd4,
                    0,
                    1u,
                    &GUID_f7898af5_cac4_4632_a2ec_da06e5111af2,
                    &ppv);
  }
  if ( (int)ElValidateHr((unsigned int)v3, v2, v4, 78) >= 0 )
  {
    v3 = (*(unsigned int (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, &v12);
    if ( (int)ElValidateHr(v3, v7, v8, 83) >= 0 )
    {
      v3 = (*(unsigned int (__fastcall **)(__int64, char *))(*(_QWORD *)v12 + 56LL))(v12, (char *)this + 8);
      ElValidateHr(v3, v9, v10, 86);
    }
  }
LABEL_7:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006d20  mov     r11, rsp
0x180006d23  mov     [r11+8], rbx
0x180006d27  push    rdi
0x180006d28  sub     rsp, 30h
0x180006d2c  and     qword ptr [r11+18h], 0
0x180006d31  lea     rax, [r11+18h]
0x180006d35  and     qword ptr [r11+10h], 0
0x180006d3a  lea     r9, _GUID_f7898af5_cac4_4632_a2ec_da06e5111af2; riid
0x180006d41  xor     edx, edx; pUnkOuter
0x180006d43  mov     [r11-18h], rax
0x180006d47  mov     rdi, rcx
0x180006d4a  lea     rcx, _GUID_304ce942_6e39_40d8_943a_b913c40c9cd4; rclsid
0x180006d51  lea     r8d, [rdx+1]; dwClsContext
0x180006d55  call    cs:__imp_CoCreateInstance
0x180006d5c  nop     dword ptr [rax+rax+00h]
0x180006d61  mov     ebx, eax
0x180006d63  cmp     eax, 800401F0h
0x180006d68  jnz     short loc_180006DBD
0x180006d6a  xor     edx, edx; dwCoInit
0x180006d6c  xor     ecx, ecx; pvReserved
0x180006d6e  call    cs:__imp_CoInitializeEx
0x180006d75  nop     dword ptr [rax+rax+00h]
0x180006d7a  mov     ecx, eax
0x180006d7c  mov     r9d, 43h ; 'C'
0x180006d82  mov     ebx, eax
0x180006d84  call    ElValidateHr
0x180006d89  test    eax, eax
0x180006d8b  js      loc_180006E1B
0x180006d91  xor     edx, edx; pUnkOuter
0x180006d93  lea     rax, [rsp+38h+arg_10]
0x180006d98  lea     r9, _GUID_f7898af5_cac4_4632_a2ec_da06e5111af2; riid
0x180006d9f  mov     [rsp+38h+ppv], rax; ppv
0x180006da4  lea     rcx, _GUID_304ce942_6e39_40d8_943a_b913c40c9cd4; rclsid
0x180006dab  lea     r8d, [rdx+1]; dwClsContext
0x180006daf  call    cs:__imp_CoCreateInstance
0x180006db6  nop     dword ptr [rax+rax+00h]
0x180006dbb  mov     ebx, eax
0x180006dbd  mov     r9d, 4Eh ; 'N'
0x180006dc3  mov     ecx, ebx
0x180006dc5  call    ElValidateHr
0x180006dca  test    eax, eax
0x180006dcc  js      short loc_180006E1B
0x180006dce  mov     rcx, [rsp+38h+arg_10]
0x180006dd3  lea     rdx, [rsp+38h+arg_8]
0x180006dd8  mov     rax, [rcx]
0x180006ddb  mov     rax, [rax+38h]
0x180006ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006de4  mov     r9d, 53h ; 'S'
0x180006dea  mov     ecx, eax
0x180006dec  mov     ebx, eax
0x180006dee  call    ElValidateHr
0x180006df3  test    eax, eax
0x180006df5  js      short loc_180006E1B
0x180006df7  mov     rcx, [rsp+38h+arg_8]
0x180006dfc  lea     rdx, [rdi+8]
0x180006e00  mov     rax, [rcx]
0x180006e03  mov     rax, [rax+38h]
0x180006e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e0c  mov     r9d, 56h ; 'V'
0x180006e12  mov     ecx, eax
0x180006e14  mov     ebx, eax
0x180006e16  call    ElValidateHr
0x180006e1b  mov     rcx, [rsp+38h+arg_8]
0x180006e20  test    rcx, rcx
0x180006e23  jz      short loc_180006E37
0x180006e25  mov     rax, [rcx]
0x180006e28  mov     rax, [rax+10h]
0x180006e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e31  and     [rsp+38h+arg_8], 0
0x180006e37  mov     rcx, [rsp+38h+arg_10]
0x180006e3c  test    rcx, rcx
0x180006e3f  jz      short loc_180006E4D
0x180006e41  mov     rax, [rcx]
0x180006e44  mov     rax, [rax+10h]
0x180006e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e4d  mov     eax, ebx
0x180006e4f  mov     rbx, [rsp+38h+arg_0]
0x180006e54  add     rsp, 30h
0x180006e58  pop     rdi
0x180006e59  retn
```
