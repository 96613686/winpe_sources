# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x140012bfc`
- end: `0x140012d7b`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `383`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140012a94`

## callees

- `0x140002750`
- `0x140012bfc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140012c78`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140012c78`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 **i; // rbx
  int v1; // eax
  __int64 *v2; // rcx
  __int64 *v3; // rcx
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h] BYREF
  int v6; // [rsp+30h] [rbp-18h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= (__int64 **)wil_details_featureDescriptors_z )
      return;
    if ( *i )
      break;
  }
LABEL_20:
  if ( !i )
    return;
  v5 = 0;
  v6 = 0;
  v4 = 0;
  if ( *((_BYTE *)i + 29) || *((_BYTE *)i + 30) )
    goto LABEL_14;
  v1 = ((__int64 (__fastcall *)(_QWORD, bool, __int64 *, __int64 *))RtlQueryFeatureConfiguration)(
         *((unsigned int *)i + 6),
         (unsigned __int8)(*((_BYTE *)i + 28) - 2) > 1u,
         &v4,
         &v5);
  if ( v1 != -2147483614 )
  {
    if ( v1 != -1073741275 )
    {
      if ( !v1 )
      {
        v4 = (8 * (BYTE4(v5) & 0xB0 | (4 * (BYTE4(v5) & 0x40u)))) | 0x206LL;
        goto LABEL_15;
      }
      if ( v1 == 279 )
      {
        v4 = (8 * (BYTE4(v5) & 0x80u)) | 0x206LL;
        goto LABEL_15;
      }
    }
LABEL_14:
    v4 = 518;
LABEL_15:
    v2 = *i;
    i += 7;
    *v2 = v4;
    while ( i < (__int64 **)wil_details_featureDescriptors_z )
    {
      if ( *i )
        goto LABEL_20;
      ++i;
    }
    return;
  }
  v4 = 518;
LABEL_23:
  v3 = *i;
  i += 7;
  *v3 = 518;
  while ( i < (__int64 **)wil_details_featureDescriptors_z )
  {
    if ( *i )
    {
      if ( i )
        goto LABEL_23;
      return;
    }
    ++i;
  }
}

```

## disassembly

```asm
0x140012bfc  mov     [rsp+arg_0], rbx
0x140012c01  push    rsi
0x140012c02  sub     rsp, 40h
0x140012c06  mov     rax, cs:__security_cookie
0x140012c0d  xor     rax, rsp
0x140012c10  mov     [rsp+48h+var_10], rax
0x140012c15  lea     rbx, wil_details_featureDescriptors_a
0x140012c1c  lea     rsi, wil_details_featureDescriptors_z
0x140012c23  jmp     short loc_140012C33
0x140012c25  cmp     qword ptr [rbx], 0
0x140012c29  jnz     loc_140012D1F
0x140012c2f  add     rbx, 8
0x140012c33  cmp     rbx, rsi
0x140012c36  jb      short loc_140012C25
0x140012c38  jmp     loc_140012D62
0x140012c3d  xor     eax, eax
0x140012c3f  mov     [rsp+48h+var_20], rax
0x140012c44  mov     [rsp+48h+var_18], eax
0x140012c48  mov     [rsp+48h+var_28], rax
0x140012c4d  cmp     [rbx+1Dh], al
0x140012c50  jnz     loc_140012CEC
0x140012c56  cmp     [rbx+1Eh], al
0x140012c59  jnz     loc_140012CEC
0x140012c5f  mov     al, [rbx+1Ch]
0x140012c62  lea     r9, [rsp+48h+var_20]
0x140012c67  mov     ecx, [rbx+18h]
0x140012c6a  lea     r8, [rsp+48h+var_28]
0x140012c6f  xor     edx, edx
0x140012c71  sub     al, 2
0x140012c73  cmp     al, 1
0x140012c75  setnbe  dl
0x140012c78  call    cs:__imp_RtlQueryFeatureConfiguration
0x140012c7f  nop     dword ptr [rax+rax+00h]
0x140012c84  cmp     eax, 80000022h
0x140012c89  jz      loc_140012D2A
0x140012c8f  cmp     eax, 0C0000225h
0x140012c94  jz      short loc_140012CEC
0x140012c96  test    eax, eax
0x140012c98  jz      short loc_140012CC1
0x140012c9a  cmp     eax, 117h
0x140012c9f  jnz     short loc_140012CEC
0x140012ca1  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140012ca5  and     eax, 80h
0x140012caa  mov     [rsp+48h+var_28], 0
0x140012cb3  shl     eax, 3
0x140012cb6  or      eax, 206h
0x140012cbb  mov     dword ptr [rsp+48h+var_28], eax
0x140012cbf  jmp     short loc_140012CFD
0x140012cc1  mov     eax, dword ptr [rsp+48h+var_20+4]
0x140012cc5  mov     ecx, eax
0x140012cc7  and     ecx, 40h
0x140012cca  mov     [rsp+48h+var_28], 0
0x140012cd3  shl     ecx, 2
0x140012cd6  and     eax, 0B0h
0x140012cdb  or      ecx, eax
0x140012cdd  shl     ecx, 3
0x140012ce0  or      ecx, 206h
0x140012ce6  mov     dword ptr [rsp+48h+var_28], ecx
0x140012cea  jmp     short loc_140012CFD
0x140012cec  mov     [rsp+48h+var_28], 0
0x140012cf5  mov     dword ptr [rsp+48h+var_28], 206h
0x140012cfd  mov     rcx, [rbx]
0x140012d00  add     rbx, 38h ; '8'
0x140012d04  mov     rax, [rsp+48h+var_28]
0x140012d09  mov     [rcx], rax
0x140012d0c  jmp     short loc_140012D18
0x140012d0e  cmp     qword ptr [rbx], 0
0x140012d12  jnz     short loc_140012D1F
0x140012d14  add     rbx, 8
0x140012d18  cmp     rbx, rsi
0x140012d1b  jb      short loc_140012D0E
0x140012d1d  jmp     short loc_140012D62
0x140012d1f  test    rbx, rbx
0x140012d22  jnz     loc_140012C3D
0x140012d28  jmp     short loc_140012D62
0x140012d2a  mov     [rsp+48h+var_28], 0
0x140012d33  mov     dword ptr [rsp+48h+var_28], 206h
0x140012d3b  mov     rax, [rsp+48h+var_28]
0x140012d40  mov     rcx, [rbx]
0x140012d43  add     rbx, 38h ; '8'
0x140012d47  mov     [rcx], rax
0x140012d4a  jmp     short loc_140012D56
0x140012d4c  cmp     qword ptr [rbx], 0
0x140012d50  jnz     short loc_140012D5D
0x140012d52  add     rbx, 8
0x140012d56  cmp     rbx, rsi
0x140012d59  jb      short loc_140012D4C
0x140012d5b  jmp     short loc_140012D62
0x140012d5d  test    rbx, rbx
0x140012d60  jnz     short loc_140012D40
0x140012d62  mov     rcx, [rsp+48h+var_10]
0x140012d67  xor     rcx, rsp; StackCookie
0x140012d6a  call    __security_check_cookie
0x140012d6f  mov     rbx, [rsp+48h+arg_0]
0x140012d74  add     rsp, 40h
0x140012d78  pop     rsi
0x140012d79  retn
```
