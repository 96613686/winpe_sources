# WcLocateSourceDirectory

- ea: `0x14002eec8`
- end: `0x14002ef89`
- name: `WcLocateSourceDirectory`
- size: `193`
- prototype: `__int64 __fastcall(PUNICODE_STRING FileName, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140030da4`

## callees

- `0x140007c60`
- `0x14002eec8`

## import_xrefs

- `FLTMGR!FltQueryDirectoryFile` at `0x14002ef65`
- `FLTMGR!FltQueryDirectoryFile` at `0x14002ef65`

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
0x14002eec8  push    rbx
0x14002eeca  push    rbp
0x14002eecb  push    rsi
0x14002eecc  push    rdi
0x14002eecd  push    r14
0x14002eecf  sub     rsp, 70h
0x14002eed3  mov     rax, cs:__security_cookie
0x14002eeda  xor     rax, rsp
0x14002eedd  mov     [rsp+98h+var_38], rax
0x14002eee2  mov     rbx, [rdx]
0x14002eee5  xorps   xmm0, xmm0
0x14002eee8  movups  [rsp+98h+FileInformation], xmm0
0x14002eeed  mov     rsi, r8
0x14002eef0  mov     rdi, rdx
0x14002eef3  mov     rbp, rcx
0x14002eef6  mov     r14d, 80000000h
0x14002eefc  cmp     rbx, rdi
0x14002eeff  jz      short loc_14002EF09
0x14002ef01  cmp     [rbx], rdi
0x14002ef04  jnz     short loc_14002EF2F
0x14002ef06  mov     [rsi], rbx
0x14002ef09  xor     ecx, ecx
0x14002ef0b  mov     eax, 0C0000034h
0x14002ef10  cmp     rbx, rdi
0x14002ef13  cmovnz  eax, ecx
0x14002ef16  mov     rcx, [rsp+98h+var_38]
0x14002ef1b  xor     rcx, rsp; StackCookie
0x14002ef1e  call    __security_check_cookie
0x14002ef23  add     rsp, 70h
0x14002ef27  pop     r14
0x14002ef29  pop     rdi
0x14002ef2a  pop     rsi
0x14002ef2b  pop     rbp
0x14002ef2c  pop     rbx
0x14002ef2d  retn
0x14002ef2f  mov     rcx, [rbx+18h]
0x14002ef33  lea     r8, [rsp+98h+FileInformation]; FileInformation
0x14002ef38  mov     [rsp+98h+LengthReturned], 0; LengthReturned
0x14002ef41  mov     r9d, 10h; Length
0x14002ef47  mov     [rsp+98h+RestartScan], 1; RestartScan
0x14002ef4c  mov     [rsp+98h+FileName], rbp; FileName
0x14002ef51  mov     rdx, [rcx+10h]; FileObject
0x14002ef55  mov     rcx, [rcx]; Instance
0x14002ef58  mov     [rsp+98h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14002ef5d  mov     [rsp+98h+FileInformationClass], 0Ch; FileInformationClass
0x14002ef65  call    cs:__imp_FltQueryDirectoryFile
0x14002ef6c  nop     dword ptr [rax+rax+00h]
0x14002ef71  lea     ecx, [rax+r14]
0x14002ef75  test    r14d, ecx
0x14002ef78  jnz     short loc_14002EF06
0x14002ef7a  cmp     eax, 80000005h
0x14002ef7f  jz      short loc_14002EF06
0x14002ef81  mov     rbx, [rbx]
0x14002ef84  jmp     loc_14002EEFC
```
