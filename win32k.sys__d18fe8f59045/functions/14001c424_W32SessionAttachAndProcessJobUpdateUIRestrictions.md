# W32SessionAttachAndProcessJobUpdateUIRestrictions

- ea: `0x14001c424`
- end: `0x14001c597`
- name: `W32SessionAttachAndProcessJobUpdateUIRestrictions`
- size: `371`
- prototype: `void __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14001b0d0`

## callees

- `0x14001c214`
- `0x14001c424`
- `0x14006da90`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001c528`
- `ntoskrnl!ZwClose` at `0x14001c528`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x14001c4b2`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x14001c512`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x14001c4b2`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x14001c512`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001c486`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001c486`
- `ntoskrnl!PsJobType` at `0x14001c464`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c569`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c569`
- `ntoskrnl!ExAllocatePool2` at `0x14001c4ea`
- `ntoskrnl!ExAllocatePool2` at `0x14001c4ea`
- `ntoskrnl!PsGetJobSessionId` at `0x14001c53f`
- `ntoskrnl!PsGetJobSessionId` at `0x14001c53f`

## pseudocode

```c
void __fastcall W32SessionAttachAndProcessJobUpdateUIRestrictions(PVOID Object)
{
  __int128 *p_JobInformation; // rbx
  int v3; // edi
  ULONG v4; // esi
  __int128 *Pool2; // rax
  unsigned int JobSessionId; // eax
  HANDLE JobHandle; // [rsp+40h] [rbp-30h] BYREF
  __int128 *v8; // [rsp+48h] [rbp-28h] BYREF
  __int128 JobInformation; // [rsp+50h] [rbp-20h] BYREF

  JobHandle = 0;
  JobInformation = 0;
  if ( ObOpenObjectByPointer(Object, 0x200u, 0, 4u, (POBJECT_TYPE)PsJobType, 0, &JobHandle) >= 0 )
  {
    p_JobInformation = 0;
    v3 = 0;
    if ( ZwQueryInformationJobObject(JobHandle, JobObjectBasicProcessIdList, &JobInformation, 0x10u, 0) >= 0
      && (_DWORD)JobInformation )
    {
      if ( (_DWORD)JobInformation == 1 )
      {
        p_JobInformation = &JobInformation;
        v3 = 1;
      }
      else
      {
        v4 = 8 * JobInformation + 8;
        Pool2 = (__int128 *)ExAllocatePool2(256, v4, 1651143509);
        p_JobInformation = Pool2;
        if ( Pool2 )
          LOBYTE(v3) = ZwQueryInformationJobObject(JobHandle, JobObjectBasicProcessIdList, Pool2, v4, 0) >= 0;
      }
    }
    ZwClose(JobHandle);
    if ( v3 )
    {
      v8 = p_JobInformation;
      JobSessionId = PsGetJobSessionId(Object);
      W32AttachToSessionAndExecute__lambda_a68a4ae4ab423316b921358be06460a3_(JobSessionId, &v8);
    }
    if ( p_JobInformation )
    {
      if ( p_JobInformation != &JobInformation )
        ExFreePoolWithTag(p_JobInformation, 0);
    }
  }
}

```

## disassembly

```asm
0x14001c424  mov     r11, rsp
0x14001c427  mov     [r11+10h], rbx
0x14001c42b  mov     [r11+18h], rsi
0x14001c42f  push    rbp
0x14001c430  push    rdi
0x14001c431  push    r14
0x14001c433  mov     rbp, rsp
0x14001c436  sub     rsp, 70h
0x14001c43a  mov     rax, cs:__security_cookie
0x14001c441  xor     rax, rsp
0x14001c444  mov     [rbp+var_10], rax
0x14001c448  mov     r14, rcx
0x14001c44b  mov     [rbp+JobHandle], 0
0x14001c453  lea     rax, [rbp+JobHandle]
0x14001c457  xorps   xmm0, xmm0
0x14001c45a  mov     [r11-58h], rax
0x14001c45e  mov     r9d, 4; DesiredAccess
0x14001c464  mov     rax, cs:PsJobType
0x14001c46b  xor     r8d, r8d; PassedAccessState
0x14001c46e  mov     [rsp+70h+AccessMode], 0; AccessMode
0x14001c473  mov     edx, 200h; HandleAttributes
0x14001c478  movups  [rbp+JobInformation], xmm0
0x14001c47c  mov     rcx, [rax]
0x14001c47f  mov     [r11-68h], rcx
0x14001c483  mov     rcx, r14; Object
0x14001c486  call    cs:__imp_ObOpenObjectByPointer
0x14001c48d  nop     dword ptr [rax+rax+00h]
0x14001c492  test    eax, eax
0x14001c494  js      loc_14001C575
0x14001c49a  mov     rcx, [rbp+JobHandle]; JobHandle
0x14001c49e  lea     r8, [rbp+JobInformation]; JobInformation
0x14001c4a2  xor     ebx, ebx
0x14001c4a4  xor     edi, edi
0x14001c4a6  mov     [rsp+70h+ReturnLength], rbx; ReturnLength
0x14001c4ab  lea     r9d, [rbx+10h]; JobInformationLength
0x14001c4af  lea     edx, [rbx+3]; JobInformationClass
0x14001c4b2  call    cs:__imp_ZwQueryInformationJobObject
0x14001c4b9  nop     dword ptr [rax+rax+00h]
0x14001c4be  test    eax, eax
0x14001c4c0  js      short loc_14001C524
0x14001c4c2  mov     eax, dword ptr [rbp+JobInformation]
0x14001c4c5  test    eax, eax
0x14001c4c7  jz      short loc_14001C524
0x14001c4c9  cmp     eax, 1
0x14001c4cc  jnz     short loc_14001C4D6
0x14001c4ce  lea     rbx, [rbp+JobInformation]
0x14001c4d2  mov     edi, eax
0x14001c4d4  jmp     short loc_14001C524
0x14001c4d6  lea     esi, ds:8[rax*8]
0x14001c4dd  mov     ecx, 100h
0x14001c4e2  mov     edx, esi
0x14001c4e4  mov     r8d, 626A7355h
0x14001c4ea  call    cs:__imp_ExAllocatePool2
0x14001c4f1  nop     dword ptr [rax+rax+00h]
0x14001c4f6  mov     rbx, rax
0x14001c4f9  test    rax, rax
0x14001c4fc  jz      short loc_14001C524
0x14001c4fe  mov     rcx, [rbp+JobHandle]; JobHandle
0x14001c502  mov     r9d, esi; JobInformationLength
0x14001c505  mov     r8, rax; JobInformation
0x14001c508  mov     [rsp+70h+ReturnLength], rdi; ReturnLength
0x14001c50d  mov     edx, 3; JobInformationClass
0x14001c512  call    cs:__imp_ZwQueryInformationJobObject
0x14001c519  nop     dword ptr [rax+rax+00h]
0x14001c51e  test    eax, eax
0x14001c520  setns   dil
0x14001c524  mov     rcx, [rbp+JobHandle]; Handle
0x14001c528  call    cs:__imp_ZwClose
0x14001c52f  nop     dword ptr [rax+rax+00h]
0x14001c534  test    edi, edi
0x14001c536  jz      short loc_14001C556
0x14001c538  mov     rcx, r14
0x14001c53b  mov     [rbp+var_28], rbx
0x14001c53f  call    cs:__imp_PsGetJobSessionId
0x14001c546  nop     dword ptr [rax+rax+00h]
0x14001c54b  mov     ecx, eax
0x14001c54d  lea     rdx, [rbp+var_28]
0x14001c551  call    W32AttachToSessionAndExecute__lambda_a68a4ae4ab423316b921358be06460a3___; W32AttachToSessionAndExecute__lambda_a68a4ae4ab423316b921358be06460a3_
0x14001c556  test    rbx, rbx
0x14001c559  jz      short loc_14001C575
0x14001c55b  lea     rax, [rbp+JobInformation]
0x14001c55f  cmp     rbx, rax
0x14001c562  jz      short loc_14001C575
0x14001c564  xor     edx, edx; Tag
0x14001c566  mov     rcx, rbx; P
0x14001c569  call    cs:__imp_ExFreePoolWithTag
0x14001c570  nop     dword ptr [rax+rax+00h]
0x14001c575  mov     rcx, [rbp+var_10]
0x14001c579  xor     rcx, rsp; StackCookie
0x14001c57c  call    __security_check_cookie
0x14001c581  lea     r11, [rsp+70h+var_s0]
0x14001c586  mov     rbx, [r11+28h]
0x14001c58a  mov     rsi, [r11+30h]
0x14001c58e  mov     rsp, r11
0x14001c591  pop     r14
0x14001c593  pop     rdi
0x14001c594  pop     rbp
0x14001c595  retn
```
