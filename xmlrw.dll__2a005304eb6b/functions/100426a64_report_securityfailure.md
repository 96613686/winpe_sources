# __report_securityfailure

- ea: `0x100426a64`
- end: `0x100426b00`
- name: `__report_securityfailure`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100426a48`

## callees

- `0x10042692c`
- `0x100426a64`
- `0x100426b08`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x100426a71`
- `KERNEL32!IsProcessorFeaturePresent` at `0x100426a71`

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
  qword_100450C70 = retaddr;
  dword_100450C60 = -1073740791;
  dword_100450C64 = 1;
  dword_100450C78 = 1;
  qword_100450C80[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x100426a64  mov     [rsp+arg_0], ecx
0x100426a68  sub     rsp, 28h
0x100426a6c  mov     ecx, 17h; ProcessorFeature
0x100426a71  call    cs:__imp_IsProcessorFeaturePresent
0x100426a77  test    eax, eax
0x100426a79  jz      short loc_100426A83
0x100426a7b  mov     eax, [rsp+28h+arg_0]
0x100426a7f  mov     ecx, eax
0x100426a81  int     29h; Win8: RtlFailFast(ecx)
0x100426a83  lea     rcx, ContextRecord; ContextRecord
0x100426a8a  call    capture_current_context
0x100426a8f  mov     rax, [rsp+28h]
0x100426a94  mov     cs:ContextRecord.Rip, rax
0x100426a9b  lea     rax, [rsp+28h]
0x100426aa0  add     rax, 8
0x100426aa4  mov     cs:ContextRecord.Rsp, rax
0x100426aab  mov     rax, cs:ContextRecord.Rip
0x100426ab2  mov     cs:qword_100450C70, rax
0x100426ab9  mov     cs:dword_100450C60, 0C0000409h
0x100426ac3  mov     cs:dword_100450C64, 1
0x100426acd  mov     cs:dword_100450C78, 1
0x100426ad7  mov     eax, 8
0x100426adc  imul    rax, 0
0x100426ae0  lea     rcx, qword_100450C80
0x100426ae7  mov     edx, [rsp+28h+arg_0]
0x100426aeb  mov     [rcx+rax], rdx
0x100426aef  lea     rcx, ExceptionInfo; ExceptionInfo
0x100426af6  call    __raise_securityfailure
0x100426afb  add     rsp, 28h
0x100426aff  retn
```
