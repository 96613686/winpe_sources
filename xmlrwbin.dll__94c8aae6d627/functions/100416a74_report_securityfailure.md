# __report_securityfailure

- ea: `0x100416a74`
- end: `0x100416b10`
- name: `__report_securityfailure`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100416a58`

## callees

- `0x10041693c`
- `0x100416a74`
- `0x100416b18`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x100416a81`
- `KERNEL32!IsProcessorFeaturePresent` at `0x100416a81`

## pseudocode

```c
void __fastcall __noreturn _report_securityfailure(unsigned int a1)
{
  DWORD64 retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = a1;
  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(v2);
  capture_current_context(&ContextRecord);
  ContextRecord.Rip = retaddr;
  ContextRecord.Rsp = (DWORD64)&v2;
  qword_100434CF0 = retaddr;
  dword_100434CE0 = -1073740791;
  dword_100434CE4 = 1;
  dword_100434CF8 = 1;
  qword_100434D00[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x100416a74  mov     [rsp+arg_0], ecx
0x100416a78  sub     rsp, 28h
0x100416a7c  mov     ecx, 17h; ProcessorFeature
0x100416a81  call    cs:__imp_IsProcessorFeaturePresent
0x100416a87  test    eax, eax
0x100416a89  jz      short loc_100416A93
0x100416a8b  mov     eax, [rsp+28h+arg_0]
0x100416a8f  mov     ecx, eax
0x100416a91  int     29h; Win8: RtlFailFast(ecx)
0x100416a93  lea     rcx, ContextRecord; ContextRecord
0x100416a9a  call    capture_current_context
0x100416a9f  mov     rax, [rsp+28h]
0x100416aa4  mov     cs:ContextRecord.Rip, rax
0x100416aab  lea     rax, [rsp+28h]
0x100416ab0  add     rax, 8
0x100416ab4  mov     cs:ContextRecord.Rsp, rax
0x100416abb  mov     rax, cs:ContextRecord.Rip
0x100416ac2  mov     cs:qword_100434CF0, rax
0x100416ac9  mov     cs:dword_100434CE0, 0C0000409h
0x100416ad3  mov     cs:dword_100434CE4, 1
0x100416add  mov     cs:dword_100434CF8, 1
0x100416ae7  mov     eax, 8
0x100416aec  imul    rax, 0
0x100416af0  lea     rcx, qword_100434D00
0x100416af7  mov     edx, [rsp+28h+arg_0]
0x100416afb  mov     [rcx+rax], rdx
0x100416aff  lea     rcx, ExceptionInfo; ExceptionInfo
0x100416b06  call    __raise_securityfailure
0x100416b0b  add     rsp, 28h
0x100416b0f  retn
```
