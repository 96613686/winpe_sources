# MpGetParentProcessByObject

- ea: `0x14008bee4`
- end: `0x14008bff6`
- name: `MpGetParentProcessByObject`
- size: `274`
- prototype: `__int64 __fastcall(PVOID Object, PEPROCESS *Process)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14006eba0`

## callees

- `0x1400118d0`
- `0x14008bee4`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14008bf5d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14008bf5d`
- `ntoskrnl!PsProcessType` at `0x14008bf43`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14008bfa4`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14008bfa4`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14008bf8a`
- `ntoskrnl!ZwQueryInformationProcess` at `0x14008bf8a`
- `ntoskrnl!ZwClose` at `0x14008bfc9`
- `ntoskrnl!ZwClose` at `0x14008bfc9`

## pseudocode

```c
__int64 __fastcall MpGetParentProcessByObject(PVOID Object, PEPROCESS *Process)
{
  HANDLE v3; // rcx
  NTSTATUS InformationProcess; // ebx
  HANDLE ProcessHandle; // [rsp+40h] [rbp-48h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+48h] [rbp-40h] BYREF
  HANDLE ProcessId[2]; // [rsp+68h] [rbp-20h]

  v3 = 0;
  ProcessHandle = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)ProcessId = 0;
  if ( Object && Process )
  {
    InformationProcess = ObOpenObjectByPointer(
                           Object,
                           0x200u,
                           0,
                           0x1000u,
                           (POBJECT_TYPE)PsProcessType,
                           0,
                           &ProcessHandle);
    if ( InformationProcess >= 0 )
    {
      InformationProcess = ZwQueryInformationProcess(
                             ProcessHandle,
                             ProcessBasicInformation,
                             ProcessInformation,
                             0x30u,
                             0);
      if ( InformationProcess >= 0 )
      {
        InformationProcess = PsLookupProcessByProcessId(ProcessId[1], Process);
        if ( InformationProcess >= 0 )
          InformationProcess = 0;
      }
    }
    v3 = ProcessHandle;
  }
  else
  {
    InformationProcess = -1073741811;
  }
  if ( v3 )
    ZwClose(v3);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x14008bee4  mov     r11, rsp
0x14008bee7  mov     [r11+18h], rbx
0x14008beeb  push    rdi
0x14008beec  sub     rsp, 80h
0x14008bef3  mov     rax, cs:__security_cookie
0x14008befa  xor     rax, rsp
0x14008befd  mov     [rsp+88h+var_10], rax
0x14008bf02  xorps   xmm0, xmm0
0x14008bf05  mov     r10, rcx
0x14008bf08  xor     ecx, ecx; Handle
0x14008bf0a  mov     rdi, rdx
0x14008bf0d  mov     [r11-48h], rcx
0x14008bf11  movups  [rsp+88h+ProcessInformation], xmm0
0x14008bf16  movups  [rsp+88h+var_30], xmm0
0x14008bf1b  movups  xmmword ptr [rsp+88h+ProcessId], xmm0
0x14008bf20  test    r10, r10
0x14008bf23  jz      loc_14008BFBF
0x14008bf29  test    rdx, rdx
0x14008bf2c  jz      loc_14008BFBF
0x14008bf32  lea     rax, [r11-48h]
0x14008bf36  mov     r9d, 1000h; DesiredAccess
0x14008bf3c  mov     [r11-58h], rax
0x14008bf40  xor     r8d, r8d; PassedAccessState
0x14008bf43  mov     rax, cs:__imp_PsProcessType
0x14008bf4a  mov     [rsp+88h+AccessMode], cl; AccessMode
0x14008bf4e  mov     rcx, r10; Object
0x14008bf51  mov     rdx, [rax]
0x14008bf54  mov     [r11-68h], rdx
0x14008bf58  mov     edx, 200h; HandleAttributes
0x14008bf5d  call    cs:__imp_ObOpenObjectByPointer
0x14008bf64  nop     dword ptr [rax+rax+00h]
0x14008bf69  mov     ebx, eax
0x14008bf6b  test    eax, eax
0x14008bf6d  js      short loc_14008BFB8
0x14008bf6f  mov     rcx, [rsp+88h+ProcessHandle]; ProcessHandle
0x14008bf74  lea     r8, [rsp+88h+ProcessInformation]; ProcessInformation
0x14008bf79  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14008bf7f  mov     [rsp+88h+ReturnLength], 0; ReturnLength
0x14008bf88  xor     edx, edx; ProcessInformationClass
0x14008bf8a  call    cs:__imp_ZwQueryInformationProcess
0x14008bf91  nop     dword ptr [rax+rax+00h]
0x14008bf96  mov     ebx, eax
0x14008bf98  test    eax, eax
0x14008bf9a  js      short loc_14008BFB8
0x14008bf9c  mov     rcx, [rsp+88h+ProcessId+8]; ProcessId
0x14008bfa1  mov     rdx, rdi; Process
0x14008bfa4  call    cs:__imp_PsLookupProcessByProcessId
0x14008bfab  nop     dword ptr [rax+rax+00h]
0x14008bfb0  mov     ebx, eax
0x14008bfb2  test    eax, eax
0x14008bfb4  js      short loc_14008BFB8
0x14008bfb6  xor     ebx, ebx
0x14008bfb8  mov     rcx, [rsp+88h+ProcessHandle]
0x14008bfbd  jmp     short loc_14008BFC4
0x14008bfbf  mov     ebx, 0C000000Dh
0x14008bfc4  test    rcx, rcx
0x14008bfc7  jz      short loc_14008BFD5
0x14008bfc9  call    cs:__imp_ZwClose
0x14008bfd0  nop     dword ptr [rax+rax+00h]
0x14008bfd5  mov     eax, ebx
0x14008bfd7  mov     rcx, [rsp+88h+var_10]
0x14008bfdc  xor     rcx, rsp; StackCookie
0x14008bfdf  call    __security_check_cookie
0x14008bfe4  mov     rbx, [rsp+88h+arg_10]
0x14008bfec  add     rsp, 80h
0x14008bff3  pop     rdi
0x14008bff4  retn
```
