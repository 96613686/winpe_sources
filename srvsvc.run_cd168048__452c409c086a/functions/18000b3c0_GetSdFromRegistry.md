# GetSdFromRegistry

- ea: `0x18000b3c0`
- end: `0x18000b4b3`
- name: `GetSdFromRegistry`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002038`
- `0x18000b3c0`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b3f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b3f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b498`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b498`
- `ntdll!RtlValidSecurityDescriptor` at `0x18000b415`
- `ntdll!RtlValidSecurityDescriptor` at `0x18000b415`
- `ntdll!RtlNtStatusToDosError` at `0x18000b478`
- `ntdll!RtlNtStatusToDosError` at `0x18000b478`

## pseudocode

```c
__int64 __fastcall GetSdFromRegistry(const WCHAR *a1, __int64 a2, const void *a3, unsigned int a4, __int64 a5)
{
  HLOCAL v8; // rax
  void *v9; // rdi
  __int64 result; // rax
  LPCWSTR Strings; // [rsp+20h] [rbp-18h] BYREF

  Strings = 0;
  if ( a4 )
  {
    v8 = LocalAlloc(0x40u, a4);
    v9 = v8;
    if ( v8 )
    {
      memcpy_0(v8, a3, a4);
      if ( RtlValidSecurityDescriptor(v9) )
      {
        result = 0;
        *(_QWORD *)(a5 + 72) = v9;
      }
      else
      {
        Strings = a1;
        RtlNtStatusToDosError(0);
        SsLogEvent(0x800009CB, 1u, &Strings);
        LocalFree(v9);
        *(_QWORD *)(a5 + 72) = 0;
        return 3221225593LL;
      }
    }
    else
    {
      *(_QWORD *)(a5 + 72) = 0;
      return 3221225626LL;
    }
  }
  else
  {
    *(_QWORD *)(a5 + 72) = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b3c0  mov     [rsp+arg_10], rbx
0x18000b3c5  mov     [rsp+arg_18], rbp
0x18000b3ca  push    rsi
0x18000b3cb  sub     rsp, 30h
0x18000b3cf  xor     ebx, ebx
0x18000b3d1  mov     rsi, r8
0x18000b3d4  mov     [rsp+38h+Strings], rbx
0x18000b3d9  mov     rbp, rcx
0x18000b3dc  test    r9d, r9d
0x18000b3df  jz      short loc_18000B444
0x18000b3e1  mov     [rsp+38h+arg_0], rdi
0x18000b3e6  mov     ecx, 40h ; '@'; uFlags
0x18000b3eb  mov     [rsp+38h+arg_8], r14
0x18000b3f0  mov     edx, r9d; uBytes
0x18000b3f3  mov     r14d, r9d
0x18000b3f6  call    cs:__imp_LocalAlloc
0x18000b3fc  mov     rdi, rax
0x18000b3ff  test    rax, rax
0x18000b402  jz      short loc_18000B461
0x18000b404  mov     r8d, r14d; Size
0x18000b407  mov     rdx, rsi; Src
0x18000b40a  mov     rcx, rax; void *
0x18000b40d  call    memcpy_0
0x18000b412  mov     rcx, rdi; SecurityDescriptor
0x18000b415  call    cs:__imp_RtlValidSecurityDescriptor
0x18000b41b  test    al, al
0x18000b41d  jz      short loc_18000B471
0x18000b41f  mov     rcx, [rsp+38h+arg_20]
0x18000b424  mov     eax, ebx
0x18000b426  mov     [rcx+48h], rdi
0x18000b42a  mov     rdi, [rsp+38h+arg_0]
0x18000b42f  mov     r14, [rsp+38h+arg_8]
0x18000b434  mov     rbx, [rsp+38h+arg_10]
0x18000b439  mov     rbp, [rsp+38h+arg_18]
0x18000b43e  add     rsp, 30h
0x18000b442  pop     rsi
0x18000b443  retn
0x18000b444  mov     rax, [rsp+38h+arg_20]
0x18000b449  xor     ecx, ecx
0x18000b44b  mov     rbp, [rsp+38h+arg_18]
0x18000b450  mov     [rax+48h], rcx
0x18000b454  mov     eax, ebx
0x18000b456  mov     rbx, [rsp+38h+arg_10]
0x18000b45b  add     rsp, 30h
0x18000b45f  pop     rsi
0x18000b460  retn
0x18000b461  mov     rax, [rsp+38h+arg_20]
0x18000b466  mov     [rax+48h], rdi
0x18000b46a  mov     eax, 0C000009Ah
0x18000b46f  jmp     short loc_18000B42A
0x18000b471  xor     ecx, ecx; Status
0x18000b473  mov     [rsp+38h+Strings], rbp
0x18000b478  call    cs:__imp_RtlNtStatusToDosError
0x18000b47e  lea     r8, [rsp+38h+Strings]; lpStrings
0x18000b483  mov     edx, 1; wNumStrings
0x18000b488  mov     r9d, eax
0x18000b48b  mov     ecx, 800009CBh; dwEventID
0x18000b490  call    SsLogEvent
0x18000b495  mov     rcx, rdi; hMem
0x18000b498  call    cs:__imp_LocalFree
0x18000b49e  mov     rax, [rsp+38h+arg_20]
0x18000b4a3  xor     ecx, ecx
0x18000b4a5  mov     [rax+48h], rcx
0x18000b4a9  mov     eax, 0C0000079h
0x18000b4ae  jmp     loc_18000B42A
```
