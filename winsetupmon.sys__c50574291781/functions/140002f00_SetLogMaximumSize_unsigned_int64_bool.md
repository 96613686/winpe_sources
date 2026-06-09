# SetLogMaximumSize(unsigned __int64,bool)

- ea: `0x140002f00`
- end: `0x140002ff3`
- name: `?SetLogMaximumSize@@YAJ_K_N@Z`
- size: `243`
- prototype: `__int64 __fastcall(unsigned __int64, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140001a94`
- `0x14001e5cc`

## callees

- `0x140001674`
- `0x140002f00`
- `0x14000f900`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140002fcc`
- `ntoskrnl!KeReleaseMutex` at `0x140002fcc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002f58`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002f58`
- `FLTMGR!FltQueryInformationFile` at `0x140002f93`
- `FLTMGR!FltQueryInformationFile` at `0x140002f93`

## pseudocode

```c
__int64 __fastcall SetLogMaximumSize(unsigned __int64 a1, char a2)
{
  int v2; // edi
  __int64 v4; // rbx
  __int128 FileInformation; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h]

  v2 = 0;
  v7 = 0;
  FileInformation = 0;
  if ( !a2 || (v2 = PersistLogMaximumSize(a1), v2 >= 0) )
  {
    KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
    if ( !FileObject
      || (v2 = FltQueryInformationFile(
                 (PFLT_INSTANCE)Instance,
                 (PFILE_OBJECT)FileObject,
                 &FileInformation,
                 0x18u,
                 FileStandardInformation,
                 0),
          v2 >= 0) )
    {
      qword_140019578 = a1;
      if ( *((_QWORD *)&FileInformation + 1) < a1 )
        v4 = a1 - *((_QWORD *)&FileInformation + 1);
      else
        v4 = 0;
      qword_140019580 = v4;
    }
    KeReleaseMutex(&Object, 0);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140002f00  mov     [rsp+arg_8], rbx
0x140002f05  push    rdi
0x140002f06  sub     rsp, 50h
0x140002f0a  mov     rax, cs:__security_cookie
0x140002f11  xor     rax, rsp
0x140002f14  mov     [rsp+58h+var_10], rax
0x140002f19  xor     eax, eax
0x140002f1b  xor     edi, edi
0x140002f1d  mov     [rsp+58h+var_18], rax
0x140002f22  xorps   xmm0, xmm0
0x140002f25  mov     rbx, rcx
0x140002f28  movups  [rsp+58h+FileInformation], xmm0
0x140002f2d  test    dl, dl
0x140002f2f  jz      short loc_140002F40
0x140002f31  call    ?PersistLogMaximumSize@@YAJ_K@Z; PersistLogMaximumSize(unsigned __int64)
0x140002f36  mov     edi, eax
0x140002f38  test    eax, eax
0x140002f3a  js      loc_140002FD8
0x140002f40  xor     r9d, r9d; Alertable
0x140002f43  mov     [rsp+58h+Timeout], 0; Timeout
0x140002f4c  xor     r8d, r8d; WaitMode
0x140002f4f  lea     rcx, Object; Object
0x140002f56  xor     edx, edx; WaitReason
0x140002f58  call    cs:__imp_KeWaitForSingleObject
0x140002f5f  nop     dword ptr [rax+rax+00h]
0x140002f64  mov     rdx, cs:FileObject; FileObject
0x140002f6b  test    rdx, rdx
0x140002f6e  jz      short loc_140002FA5
0x140002f70  mov     rcx, cs:Instance; Instance
0x140002f77  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x140002f7c  mov     [rsp+58h+LengthReturned], 0; LengthReturned
0x140002f85  mov     r9d, 18h; Length
0x140002f8b  mov     dword ptr [rsp+58h+Timeout], 5; FileInformationClass
0x140002f93  call    cs:__imp_FltQueryInformationFile
0x140002f9a  nop     dword ptr [rax+rax+00h]
0x140002f9f  mov     edi, eax
0x140002fa1  test    eax, eax
0x140002fa3  js      short loc_140002FC3
0x140002fa5  mov     cs:qword_140019578, rbx
0x140002fac  cmp     qword ptr [rsp+58h+FileInformation+8], rbx
0x140002fb1  jb      short loc_140002FB7
0x140002fb3  xor     ebx, ebx
0x140002fb5  jmp     short loc_140002FBC
0x140002fb7  sub     rbx, qword ptr [rsp+58h+FileInformation+8]
0x140002fbc  mov     cs:qword_140019580, rbx
0x140002fc3  xor     edx, edx; Wait
0x140002fc5  lea     rcx, Object; Mutex
0x140002fcc  call    cs:__imp_KeReleaseMutex
0x140002fd3  nop     dword ptr [rax+rax+00h]
0x140002fd8  mov     eax, edi
0x140002fda  mov     rcx, [rsp+58h+var_10]
0x140002fdf  xor     rcx, rsp; StackCookie
0x140002fe2  call    __security_check_cookie
0x140002fe7  mov     rbx, [rsp+58h+arg_8]
0x140002fec  add     rsp, 50h
0x140002ff0  pop     rdi
0x140002ff1  retn
```
