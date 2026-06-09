# SetWin32kSilo(void * &)

- ea: `0x140018e90`
- end: `0x140018f25`
- name: `?SetWin32kSilo@@YAPEAU_EJOB@@AEAPEAX@Z`
- size: `149`
- prototype: `struct _EJOB *__fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b828`

## callees

- `0x140018e90`

## import_xrefs

- `ntoskrnl!ZwQueryInformationJobObject` at `0x140018ed6`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x140018ed6`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x140018e9f`
- `ntoskrnl!PsIsCurrentThreadInServerSilo` at `0x140018e9f`
- `ntoskrnl!PsGetHostSilo` at `0x140018ef0`
- `ntoskrnl!PsGetHostSilo` at `0x140018ef0`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140018eff`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140018eff`

## pseudocode

```c
struct _EJOB *__fastcall SetWin32kSilo(void **a1)
{
  __int64 v2; // rbx
  __int64 HostSilo; // rax
  __int128 JobInformation; // [rsp+30h] [rbp-38h] BYREF
  __int128 v6; // [rsp+40h] [rbp-28h]
  __int64 v7; // [rsp+50h] [rbp-18h]

  v2 = 0;
  if ( (unsigned __int8)PsIsCurrentThreadInServerSilo() )
  {
    v7 = 0;
    JobInformation = 0;
    v6 = 0;
    if ( ZwQueryInformationJobObject(0, JobObjectEndOfJobTimeInformation|0x20, &JobInformation, 0x28u, 0) >= 0
      && (unsigned int)v7 < HIDWORD(v7) )
    {
      HostSilo = PsGetHostSilo();
      v2 = PsAttachSiloToCurrentThread(HostSilo);
      *a1 = (void *)*((_QWORD *)&v6 + 1);
    }
  }
  return (struct _EJOB *)v2;
}

```

## disassembly

```asm
0x140018e90  mov     [rsp+arg_0], rbx
0x140018e95  push    rdi
0x140018e96  sub     rsp, 60h
0x140018e9a  mov     rdi, rcx
0x140018e9d  xor     ebx, ebx
0x140018e9f  call    cs:__imp_PsIsCurrentThreadInServerSilo
0x140018ea6  nop     dword ptr [rax+rax+00h]
0x140018eab  test    al, al
0x140018ead  jz      short loc_140018F16
0x140018eaf  xorps   xmm0, xmm0
0x140018eb2  lea     r9d, [rbx+28h]; JobInformationLength
0x140018eb6  xor     eax, eax
0x140018eb8  lea     r8, [rsp+68h+JobInformation]; JobInformation
0x140018ebd  lea     edx, [rbx+26h]; JobInformationClass
0x140018ec0  mov     [rsp+68h+var_18], rax
0x140018ec5  xor     ecx, ecx; JobHandle
0x140018ec7  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140018ecc  movups  [rsp+68h+JobInformation], xmm0
0x140018ed1  movups  [rsp+68h+var_28], xmm0
0x140018ed6  call    cs:__imp_ZwQueryInformationJobObject
0x140018edd  nop     dword ptr [rax+rax+00h]
0x140018ee2  test    eax, eax
0x140018ee4  js      short loc_140018F16
0x140018ee6  mov     eax, dword ptr [rsp+68h+var_18+4]
0x140018eea  cmp     dword ptr [rsp+68h+var_18], eax
0x140018eee  jnb     short loc_140018F16
0x140018ef0  call    cs:__imp_PsGetHostSilo
0x140018ef7  nop     dword ptr [rax+rax+00h]
0x140018efc  mov     rcx, rax
0x140018eff  call    cs:__imp_PsAttachSiloToCurrentThread
0x140018f06  nop     dword ptr [rax+rax+00h]
0x140018f0b  mov     rcx, qword ptr [rsp+68h+var_28+8]
0x140018f10  mov     rbx, rax
0x140018f13  mov     [rdi], rcx
0x140018f16  mov     rax, rbx
0x140018f19  mov     rbx, [rsp+68h+arg_0]
0x140018f1e  add     rsp, 60h
0x140018f22  pop     rdi
0x140018f23  retn
```
