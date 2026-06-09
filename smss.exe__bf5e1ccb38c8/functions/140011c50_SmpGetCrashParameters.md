# SmpGetCrashParameters

- ea: `0x140011c50`
- end: `0x140011d1b`
- name: `SmpGetCrashParameters`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x140011438`

## callees

- `0x140004e30`
- `0x140011c50`
- `0x140011fe8`
- `0x140012204`
- `0x14001cc40`

## string_xrefs

- `0x140011c7d`: `Overwrite`

## pseudocode

```c
NTSTATUS __fastcall SmpGetCrashParameters(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v3; // rcx
  __int64 v4; // rcx
  struct _UNICODE_STRING v5; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v6; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF

  result = RtlStringCbPrintfW(
             pszDest,
             0x208u,
             L"%s\\MEMORY.DMP",
             SmpSystemRoot.Buffer,
             1179664,
             L"DumpFile",
             1310738,
             L"Overwrite");
  if ( result >= 0 )
  {
    result = SmpQueryPathFromRegistry(v3, &v5, pszDest, (struct _UNICODE_STRING *)a1);
    if ( result >= 0 )
    {
      result = SmpQueryDwordFromRegistry(v4, &v6, 1, a1 + 16);
      if ( result >= 0 )
      {
        *(_DWORD *)(a1 + 20) = 0;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011c50  mov     [rsp-8+arg_8], rbx
0x140011c55  push    rbp
0x140011c56  lea     rbp, [rsp-160h]
0x140011c5e  sub     rsp, 260h
0x140011c65  mov     rax, cs:__security_cookie
0x140011c6c  xor     rax, rsp
0x140011c6f  mov     [rbp+160h+var_10], rax
0x140011c76  mov     r9, cs:SmpSystemRoot.Buffer
0x140011c7d  lea     rax, aOverwrite; "Overwrite"
0x140011c84  mov     [rsp+260h+var_228], rax
0x140011c89  lea     r8, aSMemoryDmp; "%s\\MEMORY.DMP"
0x140011c90  lea     rax, aDumpfile; "DumpFile"
0x140011c97  mov     [rsp+260h+var_230], 140012h
0x140011ca0  mov     rbx, rcx
0x140011ca3  mov     [rsp+260h+var_238], rax
0x140011ca8  mov     edx, 208h; cbDest
0x140011cad  mov     [rsp+260h+var_240], 120010h
0x140011cb6  lea     rcx, [rsp+260h+pszDest]; pszDest
0x140011cbb  call    RtlStringCbPrintfW
0x140011cc0  test    eax, eax
0x140011cc2  js      short loc_140011CFB
0x140011cc4  mov     r9, rbx
0x140011cc7  lea     r8, [rsp+260h+pszDest]
0x140011ccc  lea     rdx, [rsp+260h+var_240]
0x140011cd1  call    SmpQueryPathFromRegistry
0x140011cd6  test    eax, eax
0x140011cd8  js      short loc_140011CFB
0x140011cda  lea     r9, [rbx+10h]
0x140011cde  mov     r8d, 1
0x140011ce4  lea     rdx, [rsp+260h+var_230]
0x140011ce9  call    SmpQueryDwordFromRegistry
0x140011cee  test    eax, eax
0x140011cf0  js      short loc_140011CFB
0x140011cf2  mov     dword ptr [rbx+14h], 0
0x140011cf9  xor     eax, eax
0x140011cfb  mov     rcx, [rbp+160h+var_10]
0x140011d02  xor     rcx, rsp; StackCookie
0x140011d05  call    __security_check_cookie
0x140011d0a  mov     rbx, [rsp+260h+arg_8]
0x140011d12  add     rsp, 260h
0x140011d19  pop     rbp
0x140011d1a  retn
```
