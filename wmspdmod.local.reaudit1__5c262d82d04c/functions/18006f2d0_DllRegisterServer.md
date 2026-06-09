# DllRegisterServer

- ea: `0x18006f2d0`
- end: `0x18006f3a6`
- name: `DllRegisterServer`
- size: `214`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001330`
- `0x18006f2d0`
- `0x180082834`

## import_xrefs

- `msdmo!DMORegister` at `0x18006f378`
- `msdmo!DMORegister` at `0x18006f378`

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

  result = sub_180082834();
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
0x18006f2d0  sub     rsp, 0B8h
0x18006f2d7  mov     rax, cs:__security_cookie
0x18006f2de  xor     rax, rsp
0x18006f2e1  mov     [rsp+0B8h+var_18], rax
0x18006f2e9  call    sub_180082834
0x18006f2ee  test    eax, eax
0x18006f2f0  js      loc_18006F38D
0x18006f2f6  movups  xmm1, cs:xmmword_1800CB010
0x18006f2fd  lea     rax, [rsp+0B8h+var_78]
0x18006f302  xor     r9d, r9d; dwFlags
0x18006f305  movups  xmm0, cs:xmmword_1800CB3D0
0x18006f30c  mov     [rsp+0B8h+pOutTypes], rax; pOutTypes
0x18006f311  lea     r8, guidCategory; guidCategory
0x18006f318  lea     rax, [rsp+0B8h+var_58]
0x18006f31d  mov     [rsp+0B8h+cOutTypes], 1; cOutTypes
0x18006f325  movdqu  xmmword ptr [rsp+0B8h+var_58.subtype.Data1], xmm0
0x18006f32b  mov     [rsp+0B8h+pInTypes], rax; pInTypes
0x18006f330  lea     rdx, clsidDMO; clsidDMO
0x18006f337  movups  xmm0, cs:xmmword_1800CB3F8
0x18006f33e  lea     rcx, szName; "WMA Voice Decoder DMO"
0x18006f345  mov     [rsp+0B8h+cInTypes], 2; cInTypes
0x18006f34d  movdqu  xmmword ptr [rsp+0B8h+var_58.type.Data1], xmm1
0x18006f353  movdqu  [rsp+0B8h+var_28], xmm0
0x18006f35c  movups  xmm0, cs:xmmword_1800CB070
0x18006f363  movdqu  [rsp+0B8h+var_38], xmm1
0x18006f36c  movdqu  xmmword ptr [rsp+0B8h+var_78.subtype.Data1], xmm0
0x18006f372  movdqu  xmmword ptr [rsp+0B8h+var_78.type.Data1], xmm1
0x18006f378  call    cs:DMORegister
0x18006f37f  nop     dword ptr [rax+rax+00h]
0x18006f384  xor     ecx, ecx
0x18006f386  test    eax, eax
0x18006f388  cmovs   ecx, eax
0x18006f38b  mov     eax, ecx
0x18006f38d  mov     rcx, [rsp+0B8h+var_18]
0x18006f395  xor     rcx, rsp; StackCookie
0x18006f398  call    __security_check_cookie
0x18006f39d  add     rsp, 0B8h
0x18006f3a4  retn
```
