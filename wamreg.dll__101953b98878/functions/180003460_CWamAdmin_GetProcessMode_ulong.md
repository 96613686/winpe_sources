# CWamAdmin::GetProcessMode(ulong *)

- ea: `0x180003460`
- end: `0x1800034a1`
- name: `?GetProcessMode@CWamAdmin@@UEAAJPEAK@Z`
- size: `65`
- prototype: `__int64 __fastcall(CWamAdmin *this, BOOL *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003460`
- `0x180004298`

## import_xrefs

- `iisutil!IsSSLReportingBackwardCompatibilityMode` at `0x18000348a`
- `iisutil!IsSSLReportingBackwardCompatibilityMode` at `0x18000348a`

## pseudocode

```c
__int64 __fastcall CWamAdmin::GetProcessMode(CWamAdmin *this, BOOL *a2)
{
  __int64 result; // rax
  BOOL v4; // ecx

  if ( !a2 )
    return 2147942487LL;
  result = ValidateAccessToMetabaseKey(L"\\LM\\W3SVC", 1u);
  if ( (int)result >= 0 )
  {
    v4 = IsSSLReportingBackwardCompatibilityMode() == 0;
    result = 0;
    *a2 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x180003460  push    rbx
0x180003462  sub     rsp, 20h
0x180003466  mov     rbx, rdx
0x180003469  test    rdx, rdx
0x18000346c  jnz     short loc_180003475
0x18000346e  mov     eax, 80070057h
0x180003473  jmp     short loc_18000349B
0x180003475  mov     edx, 1; unsigned int
0x18000347a  lea     rcx, aLmW3svc_1; "\\LM\\W3SVC"
0x180003481  call    ?ValidateAccessToMetabaseKey@@YAJPEBGK@Z; ValidateAccessToMetabaseKey(ushort const *,ulong)
0x180003486  test    eax, eax
0x180003488  js      short loc_18000349B
0x18000348a  call    cs:__imp_?IsSSLReportingBackwardCompatibilityMode@@YAHXZ; IsSSLReportingBackwardCompatibilityMode(void)
0x180003490  xor     ecx, ecx
0x180003492  test    eax, eax
0x180003494  setz    cl
0x180003497  xor     eax, eax
0x180003499  mov     [rbx], ecx
0x18000349b  add     rsp, 20h
0x18000349f  pop     rbx
0x1800034a0  retn
```
