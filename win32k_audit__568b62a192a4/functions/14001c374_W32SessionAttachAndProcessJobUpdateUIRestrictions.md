# W32SessionAttachAndProcessJobUpdateUIRestrictions

- ea: `0x14001c374`
- end: `0x14001c4e7`
- name: `W32SessionAttachAndProcessJobUpdateUIRestrictions`
- size: `371`
- prototype: `void __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14001b080`

## callees

- `0x14001c164`
- `0x14001c374`
- `0x14006d6b0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001c478`
- `ntoskrnl!ZwClose` at `0x14001c478`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x14001c402`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x14001c462`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x14001c402`
- `ntoskrnl!ZwQueryInformationJobObject` at `0x14001c462`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001c3d6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14001c3d6`
- `ntoskrnl!PsJobType` at `0x14001c3b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c4b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c4b9`
- `ntoskrnl!ExAllocatePool2` at `0x14001c43a`
- `ntoskrnl!ExAllocatePool2` at `0x14001c43a`
- `ntoskrnl!PsGetJobSessionId` at `0x14001c48f`
- `ntoskrnl!PsGetJobSessionId` at `0x14001c48f`

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
0x14001c374  mov     r11, rsp
0x14001c377  mov     [r11+10h], rbx
0x14001c37b  mov     [r11+18h], rsi
0x14001c37f  push    rbp
0x14001c380  push    rdi
0x14001c381  push    r14
0x14001c383  mov     rbp, rsp
0x14001c386  sub     rsp, 70h
0x14001c38a  mov     rax, cs:__security_cookie
0x14001c391  xor     rax, rsp
0x14001c394  mov     [rbp+var_10], rax
0x14001c398  mov     r14, rcx
0x14001c39b  mov     [rbp+JobHandle], 0
0x14001c3a3  lea     rax, [rbp+JobHandle]
0x14001c3a7  xorps   xmm0, xmm0
0x14001c3aa  mov     [r11-58h], rax
0x14001c3ae  mov     r9d, 4; DesiredAccess
0x14001c3b4  mov     rax, cs:PsJobType
0x14001c3bb  xor     r8d, r8d; PassedAccessState
0x14001c3be  mov     [rsp+70h+AccessMode], 0; AccessMode
0x14001c3c3  mov     edx, 200h; HandleAttributes
0x14001c3c8  movups  [rbp+JobInformation], xmm0
0x14001c3cc  mov     rcx, [rax]
0x14001c3cf  mov     [r11-68h], rcx
0x14001c3d3  mov     rcx, r14; Object
0x14001c3d6  call    cs:__imp_ObOpenObjectByPointer
0x14001c3dd  nop     dword ptr [rax+rax+00h]
0x14001c3e2  test    eax, eax
0x14001c3e4  js      loc_14001C4C5
0x14001c3ea  mov     rcx, [rbp+JobHandle]; JobHandle
0x14001c3ee  lea     r8, [rbp+JobInformation]; JobInformation
0x14001c3f2  xor     ebx, ebx
0x14001c3f4  xor     edi, edi
0x14001c3f6  mov     [rsp+70h+ReturnLength], rbx; ReturnLength
0x14001c3fb  lea     r9d, [rbx+10h]; JobInformationLength
0x14001c3ff  lea     edx, [rbx+3]; JobInformationClass
0x14001c402  call    cs:__imp_ZwQueryInformationJobObject
0x14001c409  nop     dword ptr [rax+rax+00h]
0x14001c40e  test    eax, eax
0x14001c410  js      short loc_14001C474
0x14001c412  mov     eax, dword ptr [rbp+JobInformation]
0x14001c415  test    eax, eax
0x14001c417  jz      short loc_14001C474
0x14001c419  cmp     eax, 1
0x14001c41c  jnz     short loc_14001C426
0x14001c41e  lea     rbx, [rbp+JobInformation]
0x14001c422  mov     edi, eax
0x14001c424  jmp     short loc_14001C474
0x14001c426  lea     esi, ds:8[rax*8]
0x14001c42d  mov     ecx, 100h
0x14001c432  mov     edx, esi
0x14001c434  mov     r8d, 626A7355h
0x14001c43a  call    cs:__imp_ExAllocatePool2
0x14001c441  nop     dword ptr [rax+rax+00h]
0x14001c446  mov     rbx, rax
0x14001c449  test    rax, rax
0x14001c44c  jz      short loc_14001C474
0x14001c44e  mov     rcx, [rbp+JobHandle]; JobHandle
0x14001c452  mov     r9d, esi; JobInformationLength
0x14001c455  mov     r8, rax; JobInformation
0x14001c458  mov     [rsp+70h+ReturnLength], rdi; ReturnLength
0x14001c45d  mov     edx, 3; JobInformationClass
0x14001c462  call    cs:__imp_ZwQueryInformationJobObject
0x14001c469  nop     dword ptr [rax+rax+00h]
0x14001c46e  test    eax, eax
0x14001c470  setns   dil
0x14001c474  mov     rcx, [rbp+JobHandle]; Handle
0x14001c478  call    cs:__imp_ZwClose
0x14001c47f  nop     dword ptr [rax+rax+00h]
0x14001c484  test    edi, edi
0x14001c486  jz      short loc_14001C4A6
0x14001c488  mov     rcx, r14
0x14001c48b  mov     [rbp+var_28], rbx
0x14001c48f  call    cs:__imp_PsGetJobSessionId
0x14001c496  nop     dword ptr [rax+rax+00h]
0x14001c49b  mov     ecx, eax
0x14001c49d  lea     rdx, [rbp+var_28]
0x14001c4a1  call    W32AttachToSessionAndExecute__lambda_a68a4ae4ab423316b921358be06460a3___; W32AttachToSessionAndExecute__lambda_a68a4ae4ab423316b921358be06460a3_
0x14001c4a6  test    rbx, rbx
0x14001c4a9  jz      short loc_14001C4C5
0x14001c4ab  lea     rax, [rbp+JobInformation]
0x14001c4af  cmp     rbx, rax
0x14001c4b2  jz      short loc_14001C4C5
0x14001c4b4  xor     edx, edx; Tag
0x14001c4b6  mov     rcx, rbx; P
0x14001c4b9  call    cs:__imp_ExFreePoolWithTag
0x14001c4c0  nop     dword ptr [rax+rax+00h]
0x14001c4c5  mov     rcx, [rbp+var_10]
0x14001c4c9  xor     rcx, rsp; StackCookie
0x14001c4cc  call    __security_check_cookie
0x14001c4d1  lea     r11, [rsp+70h+var_s0]
0x14001c4d6  mov     rbx, [r11+28h]
0x14001c4da  mov     rsi, [r11+30h]
0x14001c4de  mov     rsp, r11
0x14001c4e1  pop     r14
0x14001c4e3  pop     rdi
0x14001c4e4  pop     rbp
0x14001c4e5  retn
```
