# CFirewall::Initialize(void)

- ea: `0x180006240`
- end: `0x18000637b`
- name: `?Initialize@CFirewall@@QEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(CFirewall *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006240`
- `0x18000649c`
- `0x180030010`

## import_xrefs

- `OLE32!CoCreateInstance` at `0x180006275`
- `OLE32!CoCreateInstance` at `0x1800062cf`
- `OLE32!CoCreateInstance` at `0x180006275`
- `OLE32!CoCreateInstance` at `0x1800062cf`
- `OLE32!CoInitializeEx` at `0x18000628e`
- `OLE32!CoInitializeEx` at `0x18000628e`

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
0x180006240  mov     r11, rsp
0x180006243  mov     [r11+8], rbx
0x180006247  push    rdi
0x180006248  sub     rsp, 30h
0x18000624c  and     qword ptr [r11+18h], 0
0x180006251  lea     rax, [r11+18h]
0x180006255  and     qword ptr [r11+10h], 0
0x18000625a  lea     r9, _GUID_f7898af5_cac4_4632_a2ec_da06e5111af2; riid
0x180006261  xor     edx, edx; pUnkOuter
0x180006263  mov     [r11-18h], rax
0x180006267  mov     rdi, rcx
0x18000626a  lea     rcx, _GUID_304ce942_6e39_40d8_943a_b913c40c9cd4; rclsid
0x180006271  lea     r8d, [rdx+1]; dwClsContext
0x180006275  call    cs:__imp_CoCreateInstance
0x18000627c  nop     dword ptr [rax+rax+00h]
0x180006281  mov     ebx, eax
0x180006283  cmp     eax, 800401F0h
0x180006288  jnz     short loc_1800062DD
0x18000628a  xor     edx, edx; dwCoInit
0x18000628c  xor     ecx, ecx; pvReserved
0x18000628e  call    cs:__imp_CoInitializeEx
0x180006295  nop     dword ptr [rax+rax+00h]
0x18000629a  mov     ecx, eax
0x18000629c  mov     r9d, 43h ; 'C'
0x1800062a2  mov     ebx, eax
0x1800062a4  call    ElValidateHr
0x1800062a9  test    eax, eax
0x1800062ab  js      loc_18000633B
0x1800062b1  xor     edx, edx; pUnkOuter
0x1800062b3  lea     rax, [rsp+38h+arg_10]
0x1800062b8  lea     r9, _GUID_f7898af5_cac4_4632_a2ec_da06e5111af2; riid
0x1800062bf  mov     [rsp+38h+ppv], rax; ppv
0x1800062c4  lea     rcx, _GUID_304ce942_6e39_40d8_943a_b913c40c9cd4; rclsid
0x1800062cb  lea     r8d, [rdx+1]; dwClsContext
0x1800062cf  call    cs:__imp_CoCreateInstance
0x1800062d6  nop     dword ptr [rax+rax+00h]
0x1800062db  mov     ebx, eax
0x1800062dd  mov     r9d, 4Eh ; 'N'
0x1800062e3  mov     ecx, ebx
0x1800062e5  call    ElValidateHr
0x1800062ea  test    eax, eax
0x1800062ec  js      short loc_18000633B
0x1800062ee  mov     rcx, [rsp+38h+arg_10]
0x1800062f3  lea     rdx, [rsp+38h+arg_8]
0x1800062f8  mov     rax, [rcx]
0x1800062fb  mov     rax, [rax+38h]
0x1800062ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006304  mov     r9d, 53h ; 'S'
0x18000630a  mov     ecx, eax
0x18000630c  mov     ebx, eax
0x18000630e  call    ElValidateHr
0x180006313  test    eax, eax
0x180006315  js      short loc_18000633B
0x180006317  mov     rcx, [rsp+38h+arg_8]
0x18000631c  lea     rdx, [rdi+8]
0x180006320  mov     rax, [rcx]
0x180006323  mov     rax, [rax+38h]
0x180006327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000632c  mov     r9d, 56h ; 'V'
0x180006332  mov     ecx, eax
0x180006334  mov     ebx, eax
0x180006336  call    ElValidateHr
0x18000633b  mov     rcx, [rsp+38h+arg_8]
0x180006340  test    rcx, rcx
0x180006343  jz      short loc_180006357
0x180006345  mov     rax, [rcx]
0x180006348  mov     rax, [rax+10h]
0x18000634c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006351  and     [rsp+38h+arg_8], 0
0x180006357  mov     rcx, [rsp+38h+arg_10]
0x18000635c  test    rcx, rcx
0x18000635f  jz      short loc_18000636D
0x180006361  mov     rax, [rcx]
0x180006364  mov     rax, [rax+10h]
0x180006368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636d  mov     eax, ebx
0x18000636f  mov     rbx, [rsp+38h+arg_0]
0x180006374  add     rsp, 30h
0x180006378  pop     rdi
0x180006379  retn
```
