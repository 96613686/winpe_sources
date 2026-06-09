# Smb2DereferenceHandleCleanup

- ea: `0x140091cc0`
- end: `0x140091dbf`
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
- `0x140077340`
- `0x140077600`
- `0x140091cc0`
- `0x140091dc8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140091d3a`
- `ntoskrnl!ZwClose` at `0x140091d3a`
- `ntoskrnl!ObfDereferenceObject` at `0x140091d80`
- `ntoskrnl!ObfDereferenceObject` at `0x140091d80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091da2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140091da2`
- `ntoskrnl!PsIsThreadImpersonating` at `0x140091cfa`
- `ntoskrnl!PsIsThreadImpersonating` at `0x140091cfa`

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
0x140091cc0  mov     [rsp+arg_0], rbx
0x140091cc5  mov     [rsp+arg_8], rsi
0x140091cca  push    rdi
0x140091ccb  sub     rsp, 30h
0x140091ccf  cmp     qword ptr [rcx+58h], 0
0x140091cd4  mov     rdi, rdx
0x140091cd7  mov     rbx, rcx
0x140091cda  jz      loc_140091D77
0x140091ce0  mov     esi, 0C0000001h
0x140091ce5  call    Smb2RundownAndReleaseRdmaMappingsForRefHandle
0x140091cea  cmp     qword ptr [rbx+50h], 0
0x140091cef  jz      short loc_140091D15
0x140091cf1  mov     rcx, gs:188h
0x140091cfa  call    cs:__imp_PsIsThreadImpersonating
0x140091d01  nop     dword ptr [rax+rax+00h]
0x140091d06  test    al, al
0x140091d08  jnz     short loc_140091D15
0x140091d0a  mov     rcx, [rbx+50h]
0x140091d0e  call    Smb2ImpersonateSecurityContext
0x140091d13  mov     esi, eax
0x140091d15  test    rdi, rdi
0x140091d18  jz      short loc_140091D36
0x140091d1a  lea     r9, aSmb2dereferenc; "Smb2DereferenceHandleCleanup"
0x140091d21  mov     byte ptr [rsp+38h+var_18], 1
0x140091d26  mov     r8d, 0CE3h
0x140091d2c  mov     dl, 3
0x140091d2e  mov     rcx, rdi
0x140091d31  call    SRV2_PERF_ENTER_EX
0x140091d36  mov     rcx, [rbx+58h]; Handle
0x140091d3a  call    cs:__imp_ZwClose
0x140091d41  nop     dword ptr [rax+rax+00h]
0x140091d46  test    rdi, rdi
0x140091d49  jz      short loc_140091D67
0x140091d4b  lea     r9, aSmb2dereferenc; "Smb2DereferenceHandleCleanup"
0x140091d52  mov     byte ptr [rsp+38h+var_18], 1
0x140091d57  xor     edx, edx
0x140091d59  mov     r8d, 0CEAh
0x140091d5f  mov     rcx, rdi
0x140091d62  call    SRV2_PERF_ENTER_EX
0x140091d67  cmp     qword ptr [rbx+50h], 0
0x140091d6c  jz      short loc_140091D77
0x140091d6e  test    esi, esi
0x140091d70  js      short loc_140091D77
0x140091d72  call    Smb2Revert
0x140091d77  mov     rcx, [rbx+60h]; Object
0x140091d7b  test    rcx, rcx
0x140091d7e  jz      short loc_140091D8C
0x140091d80  call    cs:__imp_ObfDereferenceObject
0x140091d87  nop     dword ptr [rax+rax+00h]
0x140091d8c  mov     rcx, [rbx+50h]
0x140091d90  test    rcx, rcx
0x140091d93  jz      short loc_140091D9A
0x140091d95  call    Smb2DereferenceSecurityContext
0x140091d9a  mov     edx, 6232534Ch; Tag
0x140091d9f  mov     rcx, rbx; P
0x140091da2  call    cs:__imp_ExFreePoolWithTag
0x140091da9  nop     dword ptr [rax+rax+00h]
0x140091dae  mov     rbx, [rsp+38h+arg_0]
0x140091db3  mov     rsi, [rsp+38h+arg_8]
0x140091db8  add     rsp, 30h
0x140091dbc  pop     rdi
0x140091dbd  retn
```
