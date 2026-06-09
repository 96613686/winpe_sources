# __report_securityfailure

- ea: `0x180001718`
- end: `0x1800017b5`
- name: `__report_securityfailure`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800016fc`

## callees

- `0x1800015e0`
- `0x180001718`
- `0x1800017bc`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x180001725`
- `KERNEL32!IsProcessorFeaturePresent` at `0x180001725`

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
  qword_180012350 = retaddr;
  dword_180012340 = -1073740791;
  dword_180012344 = 1;
  dword_180012358 = 1;
  qword_180012360[0] = v2;
  _raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x180001718  mov     [rsp+arg_0], ecx
0x18000171c  sub     rsp, 28h
0x180001720  mov     ecx, 17h; ProcessorFeature
0x180001725  call    cs:__imp_IsProcessorFeaturePresent
0x18000172b  test    eax, eax
0x18000172d  jz      short loc_180001737
0x18000172f  mov     eax, [rsp+28h+arg_0]
0x180001733  mov     ecx, eax
0x180001735  int     29h; Win8: RtlFailFast(ecx)
0x180001737  lea     rcx, ContextRecord; ContextRecord
0x18000173e  call    capture_current_context
0x180001743  mov     rax, [rsp+28h]
0x180001748  mov     cs:ContextRecord.Rip, rax
0x18000174f  lea     rax, [rsp+28h]
0x180001754  add     rax, 8
0x180001758  mov     cs:ContextRecord.Rsp, rax
0x18000175f  mov     rax, cs:ContextRecord.Rip
0x180001766  mov     cs:qword_180012350, rax
0x18000176d  mov     cs:dword_180012340, 0C0000409h
0x180001777  mov     cs:dword_180012344, 1
0x180001781  mov     cs:dword_180012358, 1
0x18000178b  mov     eax, 8
0x180001790  imul    rax, 0
0x180001794  lea     rcx, qword_180012360
0x18000179b  mov     edx, [rsp+28h+arg_0]
0x18000179f  mov     [rcx+rax], rdx
0x1800017a3  lea     rcx, ExceptionInfo; ExceptionInfo
0x1800017aa  call    __raise_securityfailure
0x1800017af  nop
0x1800017b0  add     rsp, 28h
0x1800017b4  retn
```
