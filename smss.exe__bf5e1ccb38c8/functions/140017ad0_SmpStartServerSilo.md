# SmpStartServerSilo

- ea: `0x140017ad0`
- end: `0x140017c5c`
- name: `SmpStartServerSilo`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1400010ec`
- `0x1400053e0`
- `0x14000d4c0`
- `0x140017ad0`
- `0x14001cc29`

## import_xrefs

- `ntdll!NtClose` at `0x140017b8a`
- `ntdll!NtClose` at `0x140017bcc`
- `ntdll!NtClose` at `0x140017c2b`
- `ntdll!NtClose` at `0x140017c35`
- `ntdll!NtClose` at `0x140017c3f`
- `ntdll!NtClose` at `0x140017b8a`
- `ntdll!NtClose` at `0x140017bcc`
- `ntdll!NtClose` at `0x140017c2b`
- `ntdll!NtClose` at `0x140017c35`
- `ntdll!NtClose` at `0x140017c3f`
- `ntdll!NtResumeThread` at `0x140017bfb`
- `ntdll!NtResumeThread` at `0x140017bfb`
- `ntdll!NtTerminateProcess` at `0x140017c21`
- `ntdll!NtTerminateProcess` at `0x140017c21`
- `ntdll!NtDuplicateObject` at `0x140017b3a`
- `ntdll!NtDuplicateObject` at `0x140017b3a`
- `ntdll!NtQueryInformationJobObject` at `0x140017b7a`
- `ntdll!NtQueryInformationJobObject` at `0x140017b7a`

## pseudocode

```c
__int64 __fastcall SmpStartServerSilo(__int64 a1, __int64 a2)
{
  void *v4; // rdx
  void *v5; // rcx
  int InformationJobObject; // ebx
  __int64 v7; // rdx
  __int64 v8; // r9
  NTSTATUS v9; // eax
  _OWORD JobInformation[2]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v12; // [rsp+60h] [rbp-29h]
  __int128 v13; // [rsp+70h] [rbp-19h] BYREF
  HANDLE ThreadHandle; // [rsp+80h] [rbp-9h]
  void *TargetHandle; // [rsp+F0h] [rbp+67h] BYREF

  TargetHandle = 0;
  DWORD1(v13) = 0;
  memset_0(&v13, 0, 0x64u);
  v4 = *(void **)(a1 + 48);
  v5 = *(void **)(a2 + 32);
  memset(JobInformation, 0, sizeof(JobInformation));
  v12 = 0;
  InformationJobObject = NtDuplicateObject(v5, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &TargetHandle, 0x1F003Fu, 0, 0);
  if ( InformationJobObject < 0 )
  {
    v7 = 440;
LABEL_3:
    SmpLogFailure("SmpStartServerSilo", v7, (unsigned int)InformationJobObject);
    return (unsigned int)InformationJobObject;
  }
  InformationJobObject = NtQueryInformationJobObject(
                           TargetHandle,
                           JobObjectEndOfJobTimeInformation|0x20,
                           JobInformation,
                           0x28u,
                           0);
  if ( InformationJobObject < 0 )
  {
    NtClose(TargetHandle);
    v7 = 458;
    goto LABEL_3;
  }
  InformationJobObject = SmpExecuteImage((__int64)&SmpHelperCmd, 0, 0, v8, (__int64)TargetHandle, 20512, &v13);
  if ( InformationJobObject >= 0 )
  {
    if ( !*(_BYTE *)(a1 + 56) )
    {
      v9 = NtResumeThread(ThreadHandle, 0);
      InformationJobObject = v9;
      if ( v9 < 0 )
      {
        SmpLogFailure("SmpStartServerSilo", 489, (unsigned int)v9);
        NtTerminateProcess(*((HANDLE *)&v13 + 1), 0);
      }
    }
    NtClose(TargetHandle);
    NtClose(*((HANDLE *)&v13 + 1));
    NtClose(ThreadHandle);
  }
  else
  {
    NtClose(TargetHandle);
    SmpLogFailureString("SmpStartServerSilo", 476, SmpHelperCmd.Buffer, (unsigned int)InformationJobObject);
  }
  return (unsigned int)InformationJobObject;
}

```

## disassembly

```asm
0x140017ad0  mov     [rsp-8+arg_8], rbx
0x140017ad5  mov     [rsp-8+arg_10], rdi
0x140017ada  push    rbp
0x140017adb  lea     rbp, [rsp-57h]
0x140017ae0  sub     rsp, 0E0h
0x140017ae7  xor     eax, eax
0x140017ae9  mov     [rbp+57h+TargetHandle], 0
0x140017af1  mov     rbx, rdx
0x140017af4  mov     [rbp+57h+var_6C], eax
0x140017af7  mov     rdi, rcx
0x140017afa  xor     edx, edx; Val
0x140017afc  lea     rcx, [rbp+57h+var_70]; void *
0x140017b00  lea     r8d, [rax+64h]; Size
0x140017b04  call    memset_0
0x140017b09  mov     rdx, [rdi+30h]; SourceHandle
0x140017b0d  lea     r9, [rbp+57h+TargetHandle]; TargetHandle
0x140017b11  mov     rcx, [rbx+20h]; SourceProcessHandle
0x140017b15  xor     eax, eax
0x140017b17  mov     [rsp+0E0h+Options], eax; Options
0x140017b1b  xorps   xmm0, xmm0
0x140017b1e  mov     [rsp+0E0h+HandleAttributes], eax; HandleAttributes
0x140017b22  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x140017b26  mov     [rsp+0E0h+DesiredAccess], 1F003Fh; DesiredAccess
0x140017b2e  movups  [rbp+57h+JobInformation], xmm0
0x140017b32  mov     [rbp+57h+var_80], rax
0x140017b36  movups  [rbp+57h+var_90], xmm0
0x140017b3a  call    cs:__imp_NtDuplicateObject
0x140017b40  mov     ebx, eax
0x140017b42  test    eax, eax
0x140017b44  jns     short loc_140017B5F
0x140017b46  mov     edx, 1B8h
0x140017b4b  mov     r8d, ebx
0x140017b4e  lea     rcx, aSmpstartserver; "SmpStartServerSilo"
0x140017b55  call    SmpLogFailure
0x140017b5a  jmp     loc_140017C45
0x140017b5f  mov     rcx, [rbp+57h+TargetHandle]; JobHandle
0x140017b63  lea     r8, [rbp+57h+JobInformation]; JobInformation
0x140017b67  mov     r9d, 28h ; '('; JobInformationLength
0x140017b6d  mov     qword ptr [rsp+0E0h+DesiredAccess], 0; ReturnLength
0x140017b76  lea     edx, [r9-2]; JobInformationClass
0x140017b7a  call    cs:__imp_NtQueryInformationJobObject
0x140017b80  mov     ebx, eax
0x140017b82  test    eax, eax
0x140017b84  jns     short loc_140017B97
0x140017b86  mov     rcx, [rbp+57h+TargetHandle]; Handle
0x140017b8a  call    cs:__imp_NtClose
0x140017b90  mov     edx, 1CAh
0x140017b95  jmp     short loc_140017B4B
0x140017b97  lea     rax, [rbp+57h+var_70]
0x140017b9b  xor     r8d, r8d
0x140017b9e  mov     qword ptr [rsp+0E0h+Options], rax
0x140017ba3  lea     rcx, SmpHelperCmd
0x140017baa  mov     rax, [rbp+57h+TargetHandle]
0x140017bae  xor     edx, edx
0x140017bb0  mov     [rsp+0E0h+HandleAttributes], 5020h
0x140017bb8  mov     qword ptr [rsp+0E0h+DesiredAccess], rax
0x140017bbd  call    SmpExecuteImage
0x140017bc2  mov     ebx, eax
0x140017bc4  test    eax, eax
0x140017bc6  jns     short loc_140017BEF
0x140017bc8  mov     rcx, [rbp+57h+TargetHandle]; Handle
0x140017bcc  call    cs:__imp_NtClose
0x140017bd2  mov     r8, cs:SmpHelperCmd.Buffer
0x140017bd9  lea     rcx, aSmpstartserver; "SmpStartServerSilo"
0x140017be0  mov     r9d, ebx
0x140017be3  mov     edx, 1DCh
0x140017be8  call    SmpLogFailureString
0x140017bed  jmp     short loc_140017C45
0x140017bef  cmp     byte ptr [rdi+38h], 0
0x140017bf3  jnz     short loc_140017C27
0x140017bf5  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x140017bf9  xor     edx, edx; SuspendCount
0x140017bfb  call    cs:__imp_NtResumeThread
0x140017c01  mov     ebx, eax
0x140017c03  test    eax, eax
0x140017c05  jns     short loc_140017C27
0x140017c07  mov     r8d, eax
0x140017c0a  lea     rcx, aSmpstartserver; "SmpStartServerSilo"
0x140017c11  mov     edx, 1E9h
0x140017c16  call    SmpLogFailure
0x140017c1b  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140017c1f  xor     edx, edx; ExitStatus
0x140017c21  call    cs:__imp_NtTerminateProcess
0x140017c27  mov     rcx, [rbp+57h+TargetHandle]; Handle
0x140017c2b  call    cs:__imp_NtClose
0x140017c31  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x140017c35  call    cs:__imp_NtClose
0x140017c3b  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x140017c3f  call    cs:__imp_NtClose
0x140017c45  lea     r11, [rsp+0E0h+var_s0]
0x140017c4d  mov     eax, ebx
0x140017c4f  mov     rbx, [r11+18h]
0x140017c53  mov     rdi, [r11+20h]
0x140017c57  mov     rsp, r11
0x140017c5a  pop     rbp
0x140017c5b  retn
```
