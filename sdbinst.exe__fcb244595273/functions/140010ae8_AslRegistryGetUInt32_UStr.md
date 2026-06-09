# AslRegistryGetUInt32_UStr

- ea: `0x140010ae8`
- end: `0x140010bcf`
- name: `AslRegistryGetUInt32_UStr`
- size: `231`
- prototype: `__int64 __fastcall(_DWORD *, void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140010a68`

## callees

- `0x14001008c`
- `0x140010ae8`
- `0x14002e420`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x140010b40`
- `ntdll!ZwQueryValueKey` at `0x140010b40`

## string_xrefs

- `0x140010b64`: `AslRegistryGetUInt32_UStr`
- `0x140010b9c`: `AslRegistryGetUInt32_UStr`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32_UStr(_DWORD *a1, void *a2, struct _UNICODE_STRING *a3)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  ULONG v7; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+38h] [rbp-30h] BYREF
  int v9; // [rsp+48h] [rbp-20h]

  v9 = 0;
  v7 = 0;
  *a1 = 0;
  v8 = 0;
  v4 = ZwQueryValueKey(a2, a3, KeyValuePartialInformation, &v8, 0x14u, &v7);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( *(_QWORD *)((char *)&v8 + 4) == 0x400000004LL )
    {
      v5 = 0;
      *a1 = HIDWORD(v8);
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1098, "Invalid value type");
      return (unsigned int)-1073741788;
    }
  }
  else if ( v4 != -1073741772 )
  {
    AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1091, "Failed to query key value [%x]", v4);
  }
  return v5;
}

```

## disassembly

```asm
0x140010ae8  mov     r11, rsp
0x140010aeb  mov     [r11+20h], rbx
0x140010aef  push    rdi
0x140010af0  sub     rsp, 60h
0x140010af4  mov     rax, cs:__security_cookie
0x140010afb  xor     rax, rsp
0x140010afe  mov     [rsp+68h+var_18], rax
0x140010b03  mov     rdi, rcx
0x140010b06  lea     r9, [r11-30h]; KeyValueInformation
0x140010b0a  xor     ecx, ecx
0x140010b0c  mov     r10, r8
0x140010b0f  mov     [rsp+68h+var_20], ecx
0x140010b13  mov     rax, rdx
0x140010b16  mov     [rsp+68h+var_38], ecx
0x140010b1a  xorps   xmm0, xmm0
0x140010b1d  mov     [rdi], ecx
0x140010b1f  mov     r8d, 2; KeyValueInformationClass
0x140010b25  lea     rcx, [r11-38h]
0x140010b29  mov     rdx, r10; ValueName
0x140010b2c  mov     [r11-40h], rcx
0x140010b30  mov     rcx, rax; KeyHandle
0x140010b33  movups  [rsp+68h+var_30], xmm0
0x140010b38  mov     [rsp+68h+Length], 14h; Length
0x140010b40  call    cs:__imp_ZwQueryValueKey
0x140010b46  mov     ebx, eax
0x140010b48  test    eax, eax
0x140010b4a  jns     short loc_140010B77
0x140010b4c  cmp     eax, 0C0000034h
0x140010b51  jz      short loc_140010BB2
0x140010b53  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x140010b5a  mov     [rsp+68h+Length], eax
0x140010b5e  mov     r8d, 443h
0x140010b64  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x140010b6b  mov     ecx, 1
0x140010b70  call    AslLogCallPrintf
0x140010b75  jmp     short loc_140010BB2
0x140010b77  cmp     dword ptr [rsp+68h+var_30+4], 4
0x140010b7c  jnz     short loc_140010B8F
0x140010b7e  cmp     dword ptr [rsp+68h+var_30+8], 4
0x140010b83  jnz     short loc_140010B8F
0x140010b85  mov     eax, dword ptr [rsp+68h+var_30+0Ch]
0x140010b89  xor     ebx, ebx
0x140010b8b  mov     [rdi], eax
0x140010b8d  jmp     short loc_140010BB2
0x140010b8f  lea     r9, aInvalidValueTy; "Invalid value type"
0x140010b96  mov     r8d, 44Ah
0x140010b9c  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x140010ba3  mov     ecx, 1
0x140010ba8  call    AslLogCallPrintf
0x140010bad  mov     ebx, 0C0000024h
0x140010bb2  mov     eax, ebx
0x140010bb4  mov     rcx, [rsp+68h+var_18]
0x140010bb9  xor     rcx, rsp; StackCookie
0x140010bbc  call    __security_check_cookie
0x140010bc1  mov     rbx, [rsp+68h+arg_18]
0x140010bc9  add     rsp, 60h
0x140010bcd  pop     rdi
0x140010bce  retn
```
