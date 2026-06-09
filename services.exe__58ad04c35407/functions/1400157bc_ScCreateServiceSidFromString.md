# ScCreateServiceSidFromString

- ea: `0x1400157bc`
- end: `0x140015861`
- name: `ScCreateServiceSidFromString`
- size: `165`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x14001562c`
- `0x14002c220`
- `0x140078fb4`
- `0x14007bffc`
- `0x140083168`

## callees

- `0x1400157bc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140015813`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140015813`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015844`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015844`
- `ntdll!RtlInitUnicodeString` at `0x1400157e4`
- `ntdll!RtlInitUnicodeString` at `0x1400157e4`
- `ntdll!RtlCreateServiceSid` at `0x1400157f6`
- `ntdll!RtlCreateServiceSid` at `0x140015835`
- `ntdll!RtlCreateServiceSid` at `0x1400157f6`
- `ntdll!RtlCreateServiceSid` at `0x140015835`

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
0x1400157bc  mov     rax, rsp
0x1400157bf  mov     [rax+8], rbx
0x1400157c3  mov     [rax+10h], rsi
0x1400157c7  push    rdi
0x1400157c8  sub     rsp, 30h
0x1400157cc  mov     rsi, rdx
0x1400157cf  mov     dword ptr [rax+18h], 0
0x1400157d6  mov     rdx, rcx; SourceString
0x1400157d9  xorps   xmm0, xmm0
0x1400157dc  lea     rcx, [rax-18h]; DestinationString
0x1400157e0  movups  xmmword ptr [rax-18h], xmm0
0x1400157e4  call    cs:__imp_RtlInitUnicodeString
0x1400157ea  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x1400157ef  xor     edx, edx; ServiceSid
0x1400157f1  lea     rcx, [rsp+38h+ServiceName]; ServiceName
0x1400157f6  call    cs:__imp_RtlCreateServiceSid
0x1400157fc  cmp     eax, 0C0000023h
0x140015801  jz      short loc_14001580A
0x140015803  mov     ebx, 0C007000Dh
0x140015808  jmp     short loc_14001584F
0x14001580a  mov     edx, [rsp+38h+ServiceSidLength]; uBytes
0x14001580e  mov     ecx, 40h ; '@'; uFlags
0x140015813  call    cs:__imp_LocalAlloc
0x140015819  mov     rdi, rax
0x14001581c  test    rax, rax
0x14001581f  jnz     short loc_140015828
0x140015821  mov     ebx, 0C0000017h
0x140015826  jmp     short loc_14001584F
0x140015828  lea     r8, [rsp+38h+ServiceSidLength]; ServiceSidLength
0x14001582d  mov     rdx, rdi; ServiceSid
0x140015830  lea     rcx, [rsp+38h+ServiceName]; ServiceName
0x140015835  call    cs:__imp_RtlCreateServiceSid
0x14001583b  mov     ebx, eax
0x14001583d  test    eax, eax
0x14001583f  jns     short loc_14001584C
0x140015841  mov     rcx, rdi; hMem
0x140015844  call    cs:__imp_LocalFree
0x14001584a  jmp     short loc_14001584F
0x14001584c  mov     [rsi], rdi
0x14001584f  mov     rsi, [rsp+38h+arg_8]
0x140015854  mov     eax, ebx
0x140015856  mov     rbx, [rsp+38h+arg_0]
0x14001585b  add     rsp, 30h
0x14001585f  pop     rdi
0x140015860  retn
```
