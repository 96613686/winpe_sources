# ScCreateServiceSidFromString

- ea: `0x180018dd8`
- end: `0x180018e7d`
- name: `ScCreateServiceSidFromString`
- size: `165`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180012840`
- `0x180017584`

## callees

- `0x180018dd8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018e00`
- `ntdll!RtlInitUnicodeString` at `0x180018e00`
- `ntdll!RtlCreateServiceSid` at `0x180018e12`
- `ntdll!RtlCreateServiceSid` at `0x180018e51`
- `ntdll!RtlCreateServiceSid` at `0x180018e12`
- `ntdll!RtlCreateServiceSid` at `0x180018e51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018e2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018e2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018e60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018e60`

## pseudocode

```c
__int64 __fastcall ScCreateServiceSidFromString(PCWSTR SourceString, _QWORD *a2)
{
  NTSTATUS v3; // ebx
  HLOCAL v4; // rax
  void *v5; // rdi
  struct _UNICODE_STRING ServiceName; // [rsp+20h] [rbp-18h] BYREF
  ULONG ServiceSidLength; // [rsp+50h] [rbp+18h] BYREF

  ServiceSidLength = 0;
  ServiceName = 0;
  RtlInitUnicodeString(&ServiceName, SourceString);
  if ( RtlCreateServiceSid(&ServiceName, 0, &ServiceSidLength) == -1073741789 )
  {
    v4 = LocalAlloc(0x40u, ServiceSidLength);
    v5 = v4;
    if ( v4 )
    {
      v3 = RtlCreateServiceSid(&ServiceName, v4, &ServiceSidLength);
      if ( v3 >= 0 )
        *a2 = v5;
      else
        LocalFree(v5);
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else
  {
    return (unsigned int)-1073283059;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180018dd8  mov     rax, rsp
0x180018ddb  mov     [rax+8], rbx
0x180018ddf  mov     [rax+10h], rsi
0x180018de3  push    rdi
0x180018de4  sub     rsp, 30h
0x180018de8  mov     rsi, rdx
0x180018deb  mov     dword ptr [rax+18h], 0
0x180018df2  mov     rdx, rcx; SourceString
0x180018df5  xorps   xmm0, xmm0
0x180018df8  lea     rcx, [rax-18h]; DestinationString
0x180018dfc  movups  xmmword ptr [rax-18h], xmm0
0x180018e00  call    cs:__imp_RtlInitUnicodeString
0x180018e06  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x180018e0b  xor     edx, edx; ServiceSid
0x180018e0d  lea     rcx, [rsp+38h+ServiceName]; ServiceName
0x180018e12  call    cs:__imp_RtlCreateServiceSid
0x180018e18  cmp     eax, 0C0000023h
0x180018e1d  jz      short loc_180018E26
0x180018e1f  mov     ebx, 0C007000Dh
0x180018e24  jmp     short loc_180018E6B
0x180018e26  mov     edx, [rsp+38h+ServiceSidLength]; uBytes
0x180018e2a  mov     ecx, 40h ; '@'; uFlags
0x180018e2f  call    cs:__imp_LocalAlloc
0x180018e35  mov     rdi, rax
0x180018e38  test    rax, rax
0x180018e3b  jnz     short loc_180018E44
0x180018e3d  mov     ebx, 0C0000017h
0x180018e42  jmp     short loc_180018E6B
0x180018e44  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x180018e49  mov     rdx, rdi; ServiceSid
0x180018e4c  lea     rcx, [rsp+38h+ServiceName]; ServiceName
0x180018e51  call    cs:__imp_RtlCreateServiceSid
0x180018e57  mov     ebx, eax
0x180018e59  test    eax, eax
0x180018e5b  jns     short loc_180018E68
0x180018e5d  mov     rcx, rdi; hMem
0x180018e60  call    cs:__imp_LocalFree
0x180018e66  jmp     short loc_180018E6B
0x180018e68  mov     [rsi], rdi
0x180018e6b  mov     rsi, [rsp+38h+arg_8]
0x180018e70  mov     eax, ebx
0x180018e72  mov     rbx, [rsp+38h+arg_0]
0x180018e77  add     rsp, 30h
0x180018e7b  pop     rdi
0x180018e7c  retn
```
