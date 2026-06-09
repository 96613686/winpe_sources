# WcLocateSourceDirectory

- ea: `0x14002ee78`
- end: `0x14002ef39`
- name: `WcLocateSourceDirectory`
- size: `193`
- prototype: `__int64 __fastcall(PUNICODE_STRING FileName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140030d54`

## callees

- `0x140007c60`
- `0x14002ee78`

## import_xrefs

- `FLTMGR!FltQueryDirectoryFile` at `0x14002ef15`
- `FLTMGR!FltQueryDirectoryFile` at `0x14002ef15`

## pseudocode

```c
__int64 __fastcall WcLocateSourceDirectory(PUNICODE_STRING FileName, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // rbx
  __int64 result; // rax
  NTSTATUS v8; // eax
  __int128 FileInformation; // [rsp+50h] [rbp-48h] BYREF

  v3 = (_QWORD *)*a2;
  FileInformation = 0;
  while ( v3 != a2 )
  {
    if ( (_QWORD *)*v3 == a2
      || (v8 = FltQueryDirectoryFile(
                 *(PFLT_INSTANCE *)v3[3],
                 *(PFILE_OBJECT *)(v3[3] + 16LL),
                 &FileInformation,
                 0x10u,
                 FileNamesInformation,
                 1u,
                 FileName,
                 1u,
                 0),
          ((v8 + 0x80000000) & 0x80000000) != 0)
      || v8 == -2147483643 )
    {
      *a3 = v3;
      break;
    }
    v3 = (_QWORD *)*v3;
  }
  result = 3221225524LL;
  if ( v3 != a2 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x14002ee78  push    rbx
0x14002ee7a  push    rbp
0x14002ee7b  push    rsi
0x14002ee7c  push    rdi
0x14002ee7d  push    r14
0x14002ee7f  sub     rsp, 70h
0x14002ee83  mov     rax, cs:__security_cookie
0x14002ee8a  xor     rax, rsp
0x14002ee8d  mov     [rsp+98h+var_38], rax
0x14002ee92  mov     rbx, [rdx]
0x14002ee95  xorps   xmm0, xmm0
0x14002ee98  movups  [rsp+98h+FileInformation], xmm0
0x14002ee9d  mov     rsi, r8
0x14002eea0  mov     rdi, rdx
0x14002eea3  mov     rbp, rcx
0x14002eea6  mov     r14d, 80000000h
0x14002eeac  cmp     rbx, rdi
0x14002eeaf  jz      short loc_14002EEB9
0x14002eeb1  cmp     [rbx], rdi
0x14002eeb4  jnz     short loc_14002EEDF
0x14002eeb6  mov     [rsi], rbx
0x14002eeb9  xor     ecx, ecx
0x14002eebb  mov     eax, 0C0000034h
0x14002eec0  cmp     rbx, rdi
0x14002eec3  cmovnz  eax, ecx
0x14002eec6  mov     rcx, [rsp+98h+var_38]
0x14002eecb  xor     rcx, rsp; StackCookie
0x14002eece  call    __security_check_cookie
0x14002eed3  add     rsp, 70h
0x14002eed7  pop     r14
0x14002eed9  pop     rdi
0x14002eeda  pop     rsi
0x14002eedb  pop     rbp
0x14002eedc  pop     rbx
0x14002eedd  retn
0x14002eedf  mov     rcx, [rbx+18h]
0x14002eee3  lea     r8, [rsp+98h+FileInformation]; FileInformation
0x14002eee8  mov     [rsp+98h+LengthReturned], 0; LengthReturned
0x14002eef1  mov     r9d, 10h; Length
0x14002eef7  mov     [rsp+98h+RestartScan], 1; RestartScan
0x14002eefc  mov     [rsp+98h+FileName], rbp; FileName
0x14002ef01  mov     rdx, [rcx+10h]; FileObject
0x14002ef05  mov     rcx, [rcx]; Instance
0x14002ef08  mov     [rsp+98h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14002ef0d  mov     [rsp+98h+FileInformationClass], 0Ch; FileInformationClass
0x14002ef15  call    cs:__imp_FltQueryDirectoryFile
0x14002ef1c  nop     dword ptr [rax+rax+00h]
0x14002ef21  lea     ecx, [rax+r14]
0x14002ef25  test    r14d, ecx
0x14002ef28  jnz     short loc_14002EEB6
0x14002ef2a  cmp     eax, 80000005h
0x14002ef2f  jz      short loc_14002EEB6
0x14002ef31  mov     rbx, [rbx]
0x14002ef34  jmp     loc_14002EEAC
```
