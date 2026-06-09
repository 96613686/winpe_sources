# CUwfStaticVolumeConfiguration::set_DriveLetter(ushort const *)

- ea: `0x18000bfa0`
- end: `0x18000c01b`
- name: `?set_DriveLetter@CUwfStaticVolumeConfiguration@@QEAAJPEBG@Z`
- size: `123`
- prototype: `__int64 __fastcall(CUwfStaticVolumeConfiguration *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180006c80`

## callees

- `0x18000a6e0`
- `0x18000bfa0`
- `0x18000e96c`

## pseudocode

```c
__int64 __fastcall CUwfStaticVolumeConfiguration::set_DriveLetter(
        CUwfStaticVolumeConfiguration *this,
        const unsigned __int16 *a2)
{
  int updated; // ecx
  bool v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  if ( CheckTokenMembershipHelper((enum WELL_KNOWN_SID_TYPE)this, &v6) < 0 || !v6 || *((_BYTE *)this + 9) )
  {
    updated = -2147024891;
    goto LABEL_9;
  }
  if ( !a2 )
  {
    updated = -2147467261;
LABEL_9:
    *(_DWORD *)(*((_QWORD *)this + 3) + 16LL) = updated;
    return (unsigned int)updated;
  }
  updated = CUwfConfiguration::UpdateSzValue(
              *((CUwfConfiguration **)this + 3),
              (CUwfStaticVolumeConfiguration *)((char *)this + 16),
              L"DriveLetter",
              a2,
              1);
  if ( updated < 0 )
    goto LABEL_9;
  return 0;
}

```

## disassembly

```asm
0x18000bfa0  mov     [rsp+arg_0], rbx
0x18000bfa5  push    rdi
0x18000bfa6  sub     rsp, 30h
0x18000bfaa  mov     rdi, rdx
0x18000bfad  mov     [rsp+38h+arg_10], 0
0x18000bfb2  lea     rdx, [rsp+38h+arg_10]; bool *
0x18000bfb7  mov     rbx, rcx
0x18000bfba  call    ?CheckTokenMembershipHelper@@YAJW4WELL_KNOWN_SID_TYPE@@PEA_N@Z; CheckTokenMembershipHelper(WELL_KNOWN_SID_TYPE,bool *)
0x18000bfbf  test    eax, eax
0x18000bfc1  js      short loc_18000C002
0x18000bfc3  cmp     [rsp+38h+arg_10], 1
0x18000bfc8  jnz     short loc_18000C002
0x18000bfca  cmp     byte ptr [rbx+9], 0
0x18000bfce  jnz     short loc_18000C002
0x18000bfd0  test    rdi, rdi
0x18000bfd3  jnz     short loc_18000BFDC
0x18000bfd5  mov     ecx, 80004003h
0x18000bfda  jmp     short loc_18000C007
0x18000bfdc  mov     rcx, [rbx+18h]; this
0x18000bfe0  lea     rdx, [rbx+10h]; struct CUwfRegKey *
0x18000bfe4  mov     r9, rdi; unsigned __int16 *
0x18000bfe7  mov     [rsp+38h+var_18], 1; bool
0x18000bfec  lea     r8, aDriveletter; "DriveLetter"
0x18000bff3  call    ?UpdateSzValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBG1_N@Z; CUwfConfiguration::UpdateSzValue(CUwfRegKey &,ushort const *,ushort const *,bool)
0x18000bff8  mov     ecx, eax
0x18000bffa  test    eax, eax
0x18000bffc  js      short loc_18000C007
0x18000bffe  xor     ecx, ecx
0x18000c000  jmp     short loc_18000C00E
0x18000c002  mov     ecx, 80070005h
0x18000c007  mov     rax, [rbx+18h]
0x18000c00b  mov     [rax+10h], ecx
0x18000c00e  mov     rbx, [rsp+38h+arg_0]
0x18000c013  mov     eax, ecx
0x18000c015  add     rsp, 30h
0x18000c019  pop     rdi
0x18000c01a  retn
```
