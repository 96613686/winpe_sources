# DllRegisterServer

- ea: `0x18006f330`
- end: `0x18006f406`
- name: `DllRegisterServer`
- size: `214`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001330`
- `0x18006f330`
- `0x180082894`

## import_xrefs

- `msdmo!DMORegister` at `0x18006f3d8`
- `msdmo!DMORegister` at `0x18006f3d8`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT result; // eax
  int v1; // eax
  HRESULT v2; // ecx
  DMO_PARTIAL_MEDIATYPE pOutTypes; // [rsp+40h] [rbp-78h] BYREF
  DMO_PARTIAL_MEDIATYPE pInTypes; // [rsp+60h] [rbp-58h] BYREF
  __int128 v5; // [rsp+80h] [rbp-38h]
  __int128 v6; // [rsp+90h] [rbp-28h]

  result = sub_180082894();
  if ( result >= 0 )
  {
    pInTypes.subtype = (GUID)xmmword_1800CB3D0;
    pInTypes.type = (GUID)xmmword_1800CB010;
    v6 = xmmword_1800CB3F8;
    v5 = xmmword_1800CB010;
    pOutTypes.subtype = (GUID)xmmword_1800CB070;
    pOutTypes.type = (GUID)xmmword_1800CB010;
    v1 = DMORegister(L"WMA Voice Decoder DMO", &clsidDMO, &guidCategory, 0, 2u, &pInTypes, 1u, &pOutTypes);
    v2 = 0;
    if ( v1 < 0 )
      return v1;
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18006f330  sub     rsp, 0B8h
0x18006f337  mov     rax, cs:__security_cookie
0x18006f33e  xor     rax, rsp
0x18006f341  mov     [rsp+0B8h+var_18], rax
0x18006f349  call    sub_180082894
0x18006f34e  test    eax, eax
0x18006f350  js      loc_18006F3ED
0x18006f356  movups  xmm1, cs:xmmword_1800CB010
0x18006f35d  lea     rax, [rsp+0B8h+var_78]
0x18006f362  xor     r9d, r9d; dwFlags
0x18006f365  movups  xmm0, cs:xmmword_1800CB3D0
0x18006f36c  mov     [rsp+0B8h+pOutTypes], rax; pOutTypes
0x18006f371  lea     r8, guidCategory; guidCategory
0x18006f378  lea     rax, [rsp+0B8h+var_58]
0x18006f37d  mov     [rsp+0B8h+cOutTypes], 1; cOutTypes
0x18006f385  movdqu  xmmword ptr [rsp+0B8h+var_58.subtype.Data1], xmm0
0x18006f38b  mov     [rsp+0B8h+pInTypes], rax; pInTypes
0x18006f390  lea     rdx, clsidDMO; clsidDMO
0x18006f397  movups  xmm0, cs:xmmword_1800CB3F8
0x18006f39e  lea     rcx, szName; "WMA Voice Decoder DMO"
0x18006f3a5  mov     [rsp+0B8h+cInTypes], 2; cInTypes
0x18006f3ad  movdqu  xmmword ptr [rsp+0B8h+var_58.type.Data1], xmm1
0x18006f3b3  movdqu  [rsp+0B8h+var_28], xmm0
0x18006f3bc  movups  xmm0, cs:xmmword_1800CB070
0x18006f3c3  movdqu  [rsp+0B8h+var_38], xmm1
0x18006f3cc  movdqu  xmmword ptr [rsp+0B8h+var_78.subtype.Data1], xmm0
0x18006f3d2  movdqu  xmmword ptr [rsp+0B8h+var_78.type.Data1], xmm1
0x18006f3d8  call    cs:DMORegister
0x18006f3df  nop     dword ptr [rax+rax+00h]
0x18006f3e4  xor     ecx, ecx
0x18006f3e6  test    eax, eax
0x18006f3e8  cmovs   ecx, eax
0x18006f3eb  mov     eax, ecx
0x18006f3ed  mov     rcx, [rsp+0B8h+var_18]
0x18006f3f5  xor     rcx, rsp; StackCookie
0x18006f3f8  call    __security_check_cookie
0x18006f3fd  add     rsp, 0B8h
0x18006f404  retn
```
