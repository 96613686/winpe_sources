# OpenStorageTypeSearch

- ea: `0x1800078b0`
- end: `0x180007ac4`
- name: `OpenStorageTypeSearch`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001b870`

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x1800078b0`
- `0x1800254c0`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180007942`
- `RPCRT4!RpcBindingFree` at `0x180007942`
- `RPCRT4!NdrClientCall3` at `0x180007916`
- `RPCRT4!NdrClientCall3` at `0x180007916`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800078df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000795e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800078df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000795e`

## pseudocode

```c
__int64 __fastcall OpenStorageTypeSearch(__int64 a1)
{
  signed int Pointer; // ebx
  ULONGLONG TickCount64; // rsi
  CLIENT_CALL_RETURN v4; // rax
  __int64 v5; // r8
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-F8h] BYREF
  int v8; // [rsp+38h] [rbp-F0h]
  ULONGLONG v9; // [rsp+40h] [rbp-E8h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+50h] [rbp-D8h] BYREF
  ULONGLONG v12; // [rsp+58h] [rbp-D0h] BYREF
  ULONGLONG v13; // [rsp+60h] [rbp-C8h] BYREF
  ULONGLONG v14; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+70h] [rbp-B8h] BYREF
  char v16[32]; // [rsp+80h] [rbp-A8h] BYREF
  __int64 *v17; // [rsp+A0h] [rbp-88h]
  __int64 v18; // [rsp+A8h] [rbp-80h]
  ULONGLONG *v19; // [rsp+B0h] [rbp-78h]
  __int64 v20; // [rsp+B8h] [rbp-70h]
  ULONGLONG *v21; // [rsp+C0h] [rbp-68h]
  __int64 v22; // [rsp+C8h] [rbp-60h]
  ULONGLONG *v23; // [rsp+D0h] [rbp-58h]
  __int64 v24; // [rsp+D8h] [rbp-50h]
  ULONGLONG *v25; // [rsp+E0h] [rbp-48h]
  __int64 v26; // [rsp+E8h] [rbp-40h]
  CLIENT_CALL_RETURN *v27; // [rsp+F0h] [rbp-38h]
  __int64 v28; // [rsp+F8h] [rbp-30h]
  __int64 *v29; // [rsp+100h] [rbp-28h]
  __int64 v30; // [rsp+108h] [rbp-20h]

  Pointer = 0;
  Binding = 0;
  TickCount64 = GetTickCount64();
  v9 = TickCount64;
  if ( (int)StorageSvcInit(&Binding) >= 0 )
  {
    v10.Simple = 0;
    v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, Binding, a1).Pointer;
    Pointer = (signed int)v4.Pointer;
    v10.Pointer = v4.Pointer;
    v8 = (int)v4.Pointer;
    if ( Binding )
    {
      RpcBindingFree(&Binding);
      Binding = 0;
    }
    if ( Pointer > 0 )
      Pointer = (unsigned __int16)Pointer | 0x80070000;
  }
  GetTickCount64();
  if ( (unsigned int)dword_180040048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040048, 0x400000000000LL) )
  {
    v11 = 1;
    v17 = &v11;
    v18 = 8;
    v12 = v5 - TickCount64;
    v19 = &v12;
    v20 = 8;
    v13 = v5 - TickCount64;
    v21 = &v13;
    v22 = 8;
    v14 = v5 - TickCount64;
    v23 = &v14;
    v24 = 8;
    LODWORD(v9) = 0;
    v25 = &v9;
    v26 = 4;
    LODWORD(v10.Pointer) = Pointer;
    v27 = &v10;
    v28 = 4;
    v15 = 0x1000000;
    v29 = &v15;
    v30 = 8;
    tlgWriteAgg((__int64)&dword_180040048, (unsigned __int8 *)byte_180035DA1, 0, 9u, (__int64)v16);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800078b0  mov     [rsp+arg_8], rbx
0x1800078b5  mov     [rsp+arg_10], rsi
0x1800078ba  push    r14
0x1800078bc  sub     rsp, 120h
0x1800078c3  mov     rax, cs:__security_cookie
0x1800078ca  xor     rax, rsp
0x1800078cd  mov     [rsp+128h+var_18], rax
0x1800078d5  mov     r14, rcx
0x1800078d8  xor     ebx, ebx
0x1800078da  mov     [rsp+128h+Binding], rbx
0x1800078df  call    cs:__imp_GetTickCount64
0x1800078e5  mov     rsi, rax
0x1800078e8  mov     [rsp+128h+var_E8], rax
0x1800078ed  lea     rcx, [rsp+128h+Binding]; Binding
0x1800078f2  call    StorageSvcInit
0x1800078f7  test    eax, eax
0x1800078f9  js      short loc_18000795E
0x1800078fb  mov     [rsp+128h+var_E0], rbx
0x180007900  mov     [rsp+128h+var_108], r14
0x180007905  mov     r9, [rsp+128h+Binding]
0x18000790a  xor     r8d, r8d; pReturnValue
0x18000790d  xor     edx, edx; nProcNum
0x18000790f  lea     rcx, pProxyInfo; pProxyInfo
0x180007916  call    cs:__imp_NdrClientCall3
0x18000791c  mov     rbx, rax
0x18000791f  mov     [rsp+128h+var_E0], rax
0x180007924  mov     [rsp+128h+var_F0], eax
0x180007928  jmp     short loc_180007935
0x18000792a  mov     ebx, eax
0x18000792c  mov     [rsp+128h+var_F0], eax
0x180007930  mov     rsi, [rsp+128h+var_E8]
0x180007935  cmp     [rsp+128h+Binding], 0
0x18000793b  jz      short loc_180007951
0x18000793d  lea     rcx, [rsp+128h+Binding]; Binding
0x180007942  call    cs:__imp_RpcBindingFree
0x180007948  mov     [rsp+128h+Binding], 0
0x180007951  test    ebx, ebx
0x180007953  jle     short loc_18000795E
0x180007955  movzx   ebx, bx
0x180007958  or      ebx, 80070000h
0x18000795e  call    cs:__imp_GetTickCount64
0x180007964  mov     r8, rax
0x180007967  mov     ecx, cs:dword_180040048
0x18000796d  cmp     ecx, 5
0x180007970  jbe     loc_180007A9C
0x180007976  mov     rdx, 400000000000h
0x180007980  lea     rcx, dword_180040048
0x180007987  call    _tlgKeywordOn
0x18000798c  test    al, al
0x18000798e  jz      loc_180007A9C
0x180007994  sub     r8, rsi
0x180007997  mov     [rsp+128h+var_D8], 1
0x1800079a0  lea     rax, [rsp+128h+var_D8]
0x1800079a5  mov     [rsp+128h+var_88], rax
0x1800079ad  mov     [rsp+128h+var_80], 8
0x1800079b9  mov     [rsp+128h+var_D0], r8
0x1800079be  lea     rax, [rsp+128h+var_D0]
0x1800079c3  mov     [rsp+128h+var_78], rax
0x1800079cb  mov     [rsp+128h+var_70], 8
0x1800079d7  mov     [rsp+128h+var_C8], r8
0x1800079dc  lea     rax, [rsp+128h+var_C8]
0x1800079e1  mov     [rsp+128h+var_68], rax
0x1800079e9  mov     [rsp+128h+var_60], 8
0x1800079f5  mov     [rsp+128h+var_C0], r8
0x1800079fa  lea     rax, [rsp+128h+var_C0]
0x1800079ff  mov     [rsp+128h+var_58], rax
0x180007a07  mov     [rsp+128h+var_50], 8
0x180007a13  mov     dword ptr [rsp+128h+var_E8], 0
0x180007a1b  lea     rax, [rsp+128h+var_E8]
0x180007a20  mov     [rsp+128h+var_48], rax
0x180007a28  mov     [rsp+128h+var_40], 4
0x180007a34  mov     dword ptr [rsp+128h+var_E0], ebx
0x180007a38  lea     rax, [rsp+128h+var_E0]
0x180007a3d  mov     [rsp+128h+var_38], rax
0x180007a45  mov     [rsp+128h+var_30], 4
0x180007a51  mov     [rsp+128h+var_B8], 1000000h
0x180007a5a  lea     rax, [rsp+128h+var_B8]
0x180007a5f  mov     [rsp+128h+var_28], rax
0x180007a67  mov     [rsp+128h+var_20], 8
0x180007a73  lea     rax, [rsp+128h+var_A8]
0x180007a7b  mov     [rsp+128h+var_108], rax
0x180007a80  mov     r9d, 9
0x180007a86  xor     r8d, r8d
0x180007a89  lea     rdx, byte_180035DA1
0x180007a90  lea     rcx, dword_180040048
0x180007a97  call    _tlgWriteAgg
0x180007a9c  mov     eax, ebx
0x180007a9e  mov     rcx, [rsp+128h+var_18]
0x180007aa6  xor     rcx, rsp; StackCookie
0x180007aa9  call    __security_check_cookie
0x180007aae  lea     r11, [rsp+128h+var_8]
0x180007ab6  mov     rbx, [r11+18h]
0x180007aba  mov     rsi, [r11+20h]
0x180007abe  mov     rsp, r11
0x180007ac1  pop     r14
0x180007ac3  retn
0x18002b17a  push    rbp
0x18002b17c  sub     rsp, 30h
0x18002b180  mov     rbp, rdx
0x18002b183  mov     rcx, [rcx]
0x18002b186  mov     ecx, [rcx]; ExceptionCode
0x18002b188  call    cs:__imp_I_RpcExceptionFilter
0x18002b18e  nop
0x18002b18f  add     rsp, 30h
0x18002b193  pop     rbp
0x18002b194  retn
```
