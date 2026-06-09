# SrvLibCleanupSecurityDescriptors

- ea: `0x1400280ec`
- end: `0x14002819f`
- name: `SrvLibCleanupSecurityDescriptors`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002970c`

## callees

- `0x140007360`
- `0x1400280ec`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140028120`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140028120`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028155`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028181`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028155`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028181`

## pseudocode

```c
void SrvLibCleanupSecurityDescriptors()
{
  PACL v0; // rbx
  char *v1; // rbx
  unsigned __int8 v2; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int8 v3; // [rsp+38h] [rbp+10h] BYREF
  PACL v4; // [rsp+40h] [rbp+18h] BYREF

  if ( SrvLibCommonGroupSD )
  {
    v2 = 0;
    v3 = 0;
    v4 = 0;
    if ( RtlGetDaclSecurityDescriptor(SrvLibCommonGroupSD, &v2, &v4, &v3) >= 0 )
    {
      if ( v2 )
      {
        v0 = v4;
        if ( v4 )
        {
          SrvNetUpdateMemStatistics(*(unsigned int *)&v4[-2].AceCount, *(unsigned int *)&v4[-2].AclRevision, 0);
          ExFreePoolWithTag(&v0[-2], 0);
        }
      }
    }
    v1 = (char *)SrvLibCommonGroupSD;
    if ( SrvLibCommonGroupSD )
    {
      SrvNetUpdateMemStatistics(
        *((unsigned int *)SrvLibCommonGroupSD - 3),
        *((unsigned int *)SrvLibCommonGroupSD - 4),
        0);
      ExFreePoolWithTag(v1 - 16, 0);
    }
    SrvLibCommonGroupSD = 0;
  }
}

```

## disassembly

```asm
0x1400280ec  mov     rax, rsp
0x1400280ef  push    rbx
0x1400280f0  sub     rsp, 20h
0x1400280f4  mov     rcx, cs:SrvLibCommonGroupSD; SecurityDescriptor
0x1400280fb  test    rcx, rcx
0x1400280fe  jz      loc_140028198
0x140028104  lea     r9, [rax+10h]; DaclDefaulted
0x140028108  mov     byte ptr [rax+8], 0
0x14002810c  lea     r8, [rax+18h]; Dacl
0x140028110  mov     byte ptr [rax+10h], 0
0x140028114  lea     rdx, [rax+8]; DaclPresent
0x140028118  mov     qword ptr [rax+18h], 0
0x140028120  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140028127  nop     dword ptr [rax+rax+00h]
0x14002812c  test    eax, eax
0x14002812e  js      short loc_140028161
0x140028130  cmp     [rsp+28h+arg_0], 0
0x140028135  jz      short loc_140028161
0x140028137  mov     rbx, [rsp+28h+arg_10]
0x14002813c  test    rbx, rbx
0x14002813f  jz      short loc_140028161
0x140028141  mov     ecx, [rbx-0Ch]
0x140028144  xor     r8d, r8d
0x140028147  mov     edx, [rbx-10h]
0x14002814a  call    SrvNetUpdateMemStatistics
0x14002814f  xor     edx, edx; Tag
0x140028151  lea     rcx, [rbx-10h]; P
0x140028155  call    cs:__imp_ExFreePoolWithTag
0x14002815c  nop     dword ptr [rax+rax+00h]
0x140028161  mov     rbx, cs:SrvLibCommonGroupSD
0x140028168  test    rbx, rbx
0x14002816b  jz      short loc_14002818D
0x14002816d  mov     ecx, [rbx-0Ch]
0x140028170  xor     r8d, r8d
0x140028173  mov     edx, [rbx-10h]
0x140028176  call    SrvNetUpdateMemStatistics
0x14002817b  xor     edx, edx; Tag
0x14002817d  lea     rcx, [rbx-10h]; P
0x140028181  call    cs:__imp_ExFreePoolWithTag
0x140028188  nop     dword ptr [rax+rax+00h]
0x14002818d  mov     cs:SrvLibCommonGroupSD, 0
0x140028198  add     rsp, 20h
0x14002819c  pop     rbx
0x14002819d  retn
```
