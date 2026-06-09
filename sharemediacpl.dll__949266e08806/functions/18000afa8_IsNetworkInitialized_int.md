# IsNetworkInitialized(int *)

- ea: `0x18000afa8`
- end: `0x18000b134`
- name: `?IsNetworkInitialized@@YAJPEAH@Z`
- size: `396`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c3d0`
- `0x180012a10`

## callees

- `0x18000afa8`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000afea`
- `ole32!CoCreateInstance` at `0x18000afea`
- `OLEAUT32!__imp_VariantInit` at `0x18000b09b`
- `OLEAUT32!__imp_VariantInit` at `0x18000b09b`
- `OLEAUT32!__imp_VariantClear` at `0x18000b0d5`
- `OLEAUT32!__imp_VariantClear` at `0x18000b0d5`

## pseudocode

```c
__int64 __fastcall IsNetworkInitialized(int *a1)
{
  HRESULT v2; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-18h] BYREF
  int v6; // [rsp+70h] [rbp+20h] BYREF
  __int64 v7; // [rsp+78h] [rbp+28h] BYREF
  __int64 v8; // [rsp+80h] [rbp+30h] BYREF
  __int64 v9; // [rsp+88h] [rbp+38h] BYREF

  if ( a1 )
  {
    *a1 = 0;
    ppv = 0;
    v2 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv);
    if ( v2 >= 0 )
    {
      v9 = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, 1, &v9);
      if ( v2 >= 0 )
      {
        v8 = 0;
        v6 = 0;
        do
        {
          if ( *a1
            || (*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v9 + 64LL))(
                 v9,
                 1,
                 &v8,
                 &v6) )
          {
            break;
          }
          v7 = 0;
          v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v8)(
                 v8,
                 &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
                 &v7);
          if ( v2 >= 0 )
          {
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v7 + 24LL))(
                   v7,
                   L"NA_NetworkClass",
                   &pvarg,
                   0);
            if ( v2 >= 0 && pvarg.lVal != 1 )
              *a1 = 1;
            VariantClear(&pvarg);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
        while ( v2 >= 0 );
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000afa8  push    rbp
0x18000afaa  push    rbx
0x18000afab  push    rdi
0x18000afac  mov     rbp, rsp
0x18000afaf  sub     rsp, 50h
0x18000afb3  mov     rdi, rcx
0x18000afb6  test    rcx, rcx
0x18000afb9  jz      loc_18000B125
0x18000afbf  xor     edx, edx; pUnkOuter
0x18000afc1  mov     dword ptr [rcx], 0
0x18000afc7  lea     rax, [rbp+var_20]
0x18000afcb  mov     [rbp+var_20], 0
0x18000afd3  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18000afda  mov     [rsp+50h+ppv], rax; ppv
0x18000afdf  lea     rcx, CLSID_NetworkListManager; rclsid
0x18000afe6  lea     r8d, [rdx+1]; dwClsContext
0x18000afea  call    cs:__imp_CoCreateInstance
0x18000aff0  mov     ebx, eax
0x18000aff2  test    eax, eax
0x18000aff4  js      loc_18000B12A
0x18000affa  mov     rcx, [rbp+var_20]
0x18000affe  lea     r8, [rbp+arg_18]
0x18000b002  mov     [rbp+arg_18], 0
0x18000b00a  mov     edx, 1
0x18000b00f  mov     rax, [rcx]
0x18000b012  mov     rax, [rax+38h]
0x18000b016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b01b  mov     ebx, eax
0x18000b01d  test    eax, eax
0x18000b01f  js      loc_18000B113
0x18000b025  mov     [rbp+arg_10], 0
0x18000b02d  mov     [rbp+arg_0], 0
0x18000b034  cmp     dword ptr [rdi], 0
0x18000b037  jnz     loc_18000B103
0x18000b03d  mov     rcx, [rbp+arg_18]
0x18000b041  lea     r9, [rbp+arg_0]
0x18000b045  lea     r8, [rbp+arg_10]
0x18000b049  mov     edx, 1
0x18000b04e  mov     rax, [rcx]
0x18000b051  mov     rax, [rax+40h]
0x18000b055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b05a  test    eax, eax
0x18000b05c  jnz     loc_18000B103
0x18000b062  mov     rcx, [rbp+arg_10]
0x18000b066  lea     r8, [rbp+arg_8]
0x18000b06a  mov     [rbp+arg_8], 0
0x18000b072  lea     rdx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851
0x18000b079  mov     rax, [rcx]
0x18000b07c  mov     rax, [rax]
0x18000b07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b084  mov     ebx, eax
0x18000b086  test    eax, eax
0x18000b088  js      short loc_18000B0EB
0x18000b08a  xorps   xmm0, xmm0
0x18000b08d  lea     rcx, [rbp+pvarg]; pvarg
0x18000b091  xor     eax, eax
0x18000b093  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000b097  mov     qword ptr [rbp+pvarg+10h], rax
0x18000b09b  call    cs:__imp_VariantInit
0x18000b0a1  mov     rcx, [rbp+arg_8]
0x18000b0a5  lea     r8, [rbp+pvarg]
0x18000b0a9  xor     r9d, r9d
0x18000b0ac  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x18000b0b3  mov     rax, [rcx]
0x18000b0b6  mov     rax, [rax+18h]
0x18000b0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0bf  mov     ebx, eax
0x18000b0c1  test    eax, eax
0x18000b0c3  js      short loc_18000B0D1
0x18000b0c5  cmp     dword ptr [rbp+pvarg+8], 1
0x18000b0c9  jz      short loc_18000B0D1
0x18000b0cb  mov     dword ptr [rdi], 1
0x18000b0d1  lea     rcx, [rbp+pvarg]; pvarg
0x18000b0d5  call    cs:__imp_VariantClear
0x18000b0db  mov     rcx, [rbp+arg_8]
0x18000b0df  mov     rax, [rcx]
0x18000b0e2  mov     rax, [rax+10h]
0x18000b0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0eb  mov     rcx, [rbp+arg_10]
0x18000b0ef  mov     rax, [rcx]
0x18000b0f2  mov     rax, [rax+10h]
0x18000b0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0fb  test    ebx, ebx
0x18000b0fd  jns     loc_18000B034
0x18000b103  mov     rcx, [rbp+arg_18]
0x18000b107  mov     rax, [rcx]
0x18000b10a  mov     rax, [rax+10h]
0x18000b10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b113  mov     rcx, [rbp+var_20]
0x18000b117  mov     rax, [rcx]
0x18000b11a  mov     rax, [rax+10h]
0x18000b11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b123  jmp     short loc_18000B12A
0x18000b125  mov     ebx, 80004003h
0x18000b12a  mov     eax, ebx
0x18000b12c  add     rsp, 50h
0x18000b130  pop     rdi
0x18000b131  pop     rbx
0x18000b132  pop     rbp
0x18000b133  retn
```
