# SrvLibFreeSrvServiceSD

- ea: `0x14004e530`
- end: `0x14004e595`
- name: `SrvLibFreeSrvServiceSD`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140007ec0`
- `0x14004e530`

## import_xrefs

- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14004e557`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14004e557`

## pseudocode

```c
__int64 __fastcall SrvLibFreeSrvServiceSD(void *a1)
{
  PACL v2; // rcx
  unsigned __int8 v4; // [rsp+38h] [rbp+10h] BYREF
  unsigned __int8 v5; // [rsp+40h] [rbp+18h] BYREF
  PACL v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v4 = 0;
  v5 = 0;
  if ( RtlGetDaclSecurityDescriptor(a1, &v4, &v6, &v5) >= 0 && v4 )
  {
    v2 = v6;
  }
  else
  {
    v2 = 0;
    v6 = 0;
  }
  if ( v2 )
    SrvNetWskNotifyCleanupProviderContext(v2);
  return SrvNetWskNotifyCleanupProviderContext(a1);
}

```

## disassembly

```asm
0x14004e530  mov     rax, rsp
0x14004e533  push    rbx
0x14004e534  sub     rsp, 20h
0x14004e538  lea     r9, [rax+18h]; DaclDefaulted
0x14004e53c  mov     qword ptr [rax+20h], 0
0x14004e544  lea     r8, [rax+20h]; Dacl
0x14004e548  mov     byte ptr [rax+10h], 0
0x14004e54c  lea     rdx, [rax+10h]; DaclPresent
0x14004e550  mov     byte ptr [rax+18h], 0
0x14004e554  mov     rbx, rcx
0x14004e557  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14004e55e  nop     dword ptr [rax+rax+00h]
0x14004e563  test    eax, eax
0x14004e565  js      short loc_14004E575
0x14004e567  cmp     [rsp+28h+arg_8], 0
0x14004e56c  jz      short loc_14004E575
0x14004e56e  mov     rcx, [rsp+28h+arg_18]
0x14004e573  jmp     short loc_14004E57C
0x14004e575  xor     ecx, ecx
0x14004e577  mov     [rsp+28h+arg_18], rcx
0x14004e57c  test    rcx, rcx
0x14004e57f  jz      short loc_14004E586
0x14004e581  call    SrvNetWskNotifyCleanupProviderContext
0x14004e586  mov     rcx, rbx
0x14004e589  call    SrvNetWskNotifyCleanupProviderContext
0x14004e58e  add     rsp, 20h
0x14004e592  pop     rbx
0x14004e593  retn
```
