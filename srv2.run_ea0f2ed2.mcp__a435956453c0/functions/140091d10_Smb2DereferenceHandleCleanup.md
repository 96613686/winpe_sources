# Smb2DereferenceHandleCleanup

- ea: `0x140091d10`
- end: `0x140091e0f`
- name: `Smb2DereferenceHandleCleanup`
- size: `255`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ca00`
- `0x14000cdf0`
- `0x14000e5f0`
- `0x14000f060`
- `0x1400136b0`
- `0x140013810`
- `0x14001b3fc`
- `0x1400286f0`

## callees

- `0x140005070`
- `0x140015960`
- `0x140077390`
- `0x140077650`
- `0x140091d10`
- `0x140091e18`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140091d8a`
- `ntoskrnl!ZwClose` at `0x140091d8a`
- `ntoskrnl!ObfDereferenceObject` at `0x140091dd0`
- `ntoskrnl!ObfDereferenceObject` at `0x140091dd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091df2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091df2`
- `ntoskrnl!PsIsThreadImpersonating` at `0x140091d4a`
- `ntoskrnl!PsIsThreadImpersonating` at `0x140091d4a`

## pseudocode

```c
void __fastcall Smb2DereferenceHandleCleanup(PVOID P, __int64 a2)
{
  SECURITY_STATUS v4; // esi
  __int64 v5; // rdx
  void *v6; // rcx
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-18h]
  char v9; // [rsp+20h] [rbp-18h]

  if ( *((_QWORD *)P + 11) )
  {
    v4 = -1073741823;
    Smb2RundownAndReleaseRdmaMappingsForRefHandle();
    if ( *((_QWORD *)P + 10) && !(unsigned __int8)PsIsThreadImpersonating(KeGetCurrentThread()) )
      v4 = Smb2ImpersonateSecurityContext(*((_QWORD *)P + 10));
    if ( a2 )
    {
      v9 = 1;
      LOBYTE(v5) = 3;
      SRV2_PERF_ENTER_EX(a2, v5, 3299, "Smb2DereferenceHandleCleanup", v9);
    }
    ZwClose(*((HANDLE *)P + 11));
    if ( a2 )
    {
      LOBYTE(v8) = 1;
      SRV2_PERF_ENTER_EX(a2, 0, 3306, "Smb2DereferenceHandleCleanup", v8);
    }
    if ( *((_QWORD *)P + 10) && v4 >= 0 )
      Smb2Revert();
  }
  v6 = (void *)*((_QWORD *)P + 12);
  if ( v6 )
    ObfDereferenceObject(v6);
  v7 = *((_QWORD *)P + 10);
  if ( v7 )
    Smb2DereferenceSecurityContext(v7);
  ExFreePoolWithTag(P, 0x6232534Cu);
}

```

## disassembly

```asm
0x140091d10  mov     [rsp+arg_0], rbx
0x140091d15  mov     [rsp+arg_8], rsi
0x140091d1a  push    rdi
0x140091d1b  sub     rsp, 30h
0x140091d1f  cmp     qword ptr [rcx+58h], 0
0x140091d24  mov     rdi, rdx
0x140091d27  mov     rbx, rcx
0x140091d2a  jz      loc_140091DC7
0x140091d30  mov     esi, 0C0000001h
0x140091d35  call    Smb2RundownAndReleaseRdmaMappingsForRefHandle
0x140091d3a  cmp     qword ptr [rbx+50h], 0
0x140091d3f  jz      short loc_140091D65
0x140091d41  mov     rcx, gs:188h
0x140091d4a  call    cs:__imp_PsIsThreadImpersonating
0x140091d51  nop     dword ptr [rax+rax+00h]
0x140091d56  test    al, al
0x140091d58  jnz     short loc_140091D65
0x140091d5a  mov     rcx, [rbx+50h]
0x140091d5e  call    Smb2ImpersonateSecurityContext
0x140091d63  mov     esi, eax
0x140091d65  test    rdi, rdi
0x140091d68  jz      short loc_140091D86
0x140091d6a  lea     r9, aSmb2dereferenc; "Smb2DereferenceHandleCleanup"
0x140091d71  mov     byte ptr [rsp+38h+var_18], 1
0x140091d76  mov     r8d, 0CE3h
0x140091d7c  mov     dl, 3
0x140091d7e  mov     rcx, rdi
0x140091d81  call    SRV2_PERF_ENTER_EX
0x140091d86  mov     rcx, [rbx+58h]; Handle
0x140091d8a  call    cs:__imp_ZwClose
0x140091d91  nop     dword ptr [rax+rax+00h]
0x140091d96  test    rdi, rdi
0x140091d99  jz      short loc_140091DB7
0x140091d9b  lea     r9, aSmb2dereferenc; "Smb2DereferenceHandleCleanup"
0x140091da2  mov     byte ptr [rsp+38h+var_18], 1
0x140091da7  xor     edx, edx
0x140091da9  mov     r8d, 0CEAh
0x140091daf  mov     rcx, rdi
0x140091db2  call    SRV2_PERF_ENTER_EX
0x140091db7  cmp     qword ptr [rbx+50h], 0
0x140091dbc  jz      short loc_140091DC7
0x140091dbe  test    esi, esi
0x140091dc0  js      short loc_140091DC7
0x140091dc2  call    Smb2Revert
0x140091dc7  mov     rcx, [rbx+60h]; Object
0x140091dcb  test    rcx, rcx
0x140091dce  jz      short loc_140091DDC
0x140091dd0  call    cs:__imp_ObfDereferenceObject
0x140091dd7  nop     dword ptr [rax+rax+00h]
0x140091ddc  mov     rcx, [rbx+50h]
0x140091de0  test    rcx, rcx
0x140091de3  jz      short loc_140091DEA
0x140091de5  call    Smb2DereferenceSecurityContext
0x140091dea  mov     edx, 6232534Ch; Tag
0x140091def  mov     rcx, rbx; P
0x140091df2  call    cs:__imp_ExFreePoolWithTag
0x140091df9  nop     dword ptr [rax+rax+00h]
0x140091dfe  mov     rbx, [rsp+38h+arg_0]
0x140091e03  mov     rsi, [rsp+38h+arg_8]
0x140091e08  add     rsp, 30h
0x140091e0c  pop     rdi
0x140091e0d  retn
```
