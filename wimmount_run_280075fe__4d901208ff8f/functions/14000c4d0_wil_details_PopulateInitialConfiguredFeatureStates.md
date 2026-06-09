# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14000c4d0`
- end: `0x14000c680`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000c2d0`

## callees

- `0x140002bb0`
- `0x140002c90`
- `0x14000c4d0`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c566`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000c566`

## string_xrefs

- `0x14000c54f`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
void wil_details_PopulateInitialConfiguredFeatureStates()
{
  int **i; // rbx
  unsigned int v1; // esi
  __int64 (__fastcall *SystemRoutineAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
  BOOL v3; // edi
  int v4; // eax
  _QWORD *v5; // rcx
  int *v6; // rcx
  __int64 v7; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+38h] [rbp-28h] BYREF
  __int64 v9; // [rsp+48h] [rbp-18h] BYREF
  int v10; // [rsp+50h] [rbp-10h]

  for ( i = wil_details_featureDescriptors_a; ; ++i )
  {
    if ( i >= (int **)wil_details_featureDescriptors_z )
      return;
    if ( *i )
      break;
  }
LABEL_24:
  if ( !i )
    return;
  v9 = 0;
  v10 = 0;
  v7 = 0;
  if ( *((_BYTE *)i + 29) || *((_BYTE *)i + 30) )
    goto LABEL_18;
  v1 = *((_DWORD *)i + 6);
  SystemRoutineAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  v3 = (unsigned __int8)(*((_BYTE *)i + 28) - 2) > 1u;
  if ( g_wil_details_pfnRtlQueryFeatureConfiguration
    || (*(_QWORD *)&SystemRoutineName.Length = 3801144,
        SystemRoutineName.Buffer = L"RtlQueryFeatureConfiguration",
        SystemRoutineAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))MmGetSystemRoutineAddress(&SystemRoutineName),
        (g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)SystemRoutineAddress) != 0) )
  {
    v4 = SystemRoutineAddress(v1, v3, &v7, &v9);
  }
  else
  {
    v4 = -1073741511;
  }
  if ( v4 != -2147483614 )
  {
    if ( v4 != -1073741275 )
    {
      if ( !v4 )
      {
        v7 = (8 * (BYTE4(v9) & 0xB0 | (4 * (BYTE4(v9) & 0x40u)))) | 0x206LL;
        goto LABEL_19;
      }
      if ( v4 == 279 )
      {
        v7 = (8 * (BYTE4(v9) & 0x80u)) | 0x206LL;
        goto LABEL_19;
      }
    }
LABEL_18:
    v7 = 518;
LABEL_19:
    v5 = *i;
    i += 7;
    *v5 = v7;
    while ( i < (int **)wil_details_featureDescriptors_z )
    {
      if ( *i )
        goto LABEL_24;
      ++i;
    }
    return;
  }
  v7 = 518;
LABEL_27:
  v6 = *i;
  i += 7;
  *(_QWORD *)v6 = 518;
  while ( i < (int **)wil_details_featureDescriptors_z )
  {
    if ( *i )
    {
      if ( i )
        goto LABEL_27;
      return;
    }
    ++i;
  }
}

```

## disassembly

```asm
0x14000c4d0  push    rbp
0x14000c4d2  push    rbx
0x14000c4d3  push    rsi
0x14000c4d4  push    rdi
0x14000c4d5  push    r15
0x14000c4d7  mov     rbp, rsp
0x14000c4da  sub     rsp, 60h
0x14000c4de  mov     rax, cs:__security_cookie
0x14000c4e5  xor     rax, rsp
0x14000c4e8  mov     [rbp+var_8], rax
0x14000c4ec  lea     rbx, wil_details_featureDescriptors_a
0x14000c4f3  lea     r15, wil_details_featureDescriptors_z
0x14000c4fa  jmp     short loc_14000C50A
0x14000c4fc  cmp     qword ptr [rbx], 0
0x14000c500  jnz     loc_14000C628
0x14000c506  add     rbx, 8
0x14000c50a  cmp     rbx, r15
0x14000c50d  jb      short loc_14000C4FC
0x14000c50f  jmp     loc_14000C668
0x14000c514  xor     eax, eax
0x14000c516  mov     [rbp+var_18], rax
0x14000c51a  mov     [rbp+var_10], eax
0x14000c51d  mov     [rbp+var_30], rax
0x14000c521  cmp     [rbx+1Dh], al
0x14000c524  jnz     loc_14000C5F8
0x14000c52a  cmp     [rbx+1Eh], al
0x14000c52d  jnz     loc_14000C5F8
0x14000c533  mov     al, [rbx+1Ch]
0x14000c536  xor     edi, edi
0x14000c538  mov     esi, [rbx+18h]
0x14000c53b  sub     al, 2
0x14000c53d  cmp     al, 1
0x14000c53f  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000c546  setnbe  dil
0x14000c54a  test    rax, rax
0x14000c54d  jnz     short loc_14000C585
0x14000c54f  lea     rax, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000c556  mov     qword ptr [rbp+SystemRoutineName.Length], 3A0038h
0x14000c55e  lea     rcx, [rbp+SystemRoutineName]; SystemRoutineName
0x14000c562  mov     [rbp+SystemRoutineName.Buffer], rax
0x14000c566  call    cs:__imp_MmGetSystemRoutineAddress
0x14000c56d  nop     dword ptr [rax+rax+00h]
0x14000c572  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000c579  test    rax, rax
0x14000c57c  jnz     short loc_14000C585
0x14000c57e  mov     eax, 0C0000139h
0x14000c583  jmp     short loc_14000C596
0x14000c585  lea     r9, [rbp+var_18]
0x14000c589  mov     edx, edi
0x14000c58b  lea     r8, [rbp+var_30]
0x14000c58f  mov     ecx, esi
0x14000c591  call    _guard_dispatch_icall
0x14000c596  cmp     eax, 80000022h
0x14000c59b  jz      loc_14000C633
0x14000c5a1  cmp     eax, 0C0000225h
0x14000c5a6  jz      short loc_14000C5F8
0x14000c5a8  test    eax, eax
0x14000c5aa  jz      short loc_14000C5D0
0x14000c5ac  cmp     eax, 117h
0x14000c5b1  jnz     short loc_14000C5F8
0x14000c5b3  mov     eax, dword ptr [rbp+var_18+4]
0x14000c5b6  and     eax, 80h
0x14000c5bb  mov     [rbp+var_30], 0
0x14000c5c3  shl     eax, 3
0x14000c5c6  or      eax, 206h
0x14000c5cb  mov     dword ptr [rbp+var_30], eax
0x14000c5ce  jmp     short loc_14000C607
0x14000c5d0  mov     eax, dword ptr [rbp+var_18+4]
0x14000c5d3  mov     ecx, eax
0x14000c5d5  and     ecx, 40h
0x14000c5d8  mov     [rbp+var_30], 0
0x14000c5e0  shl     ecx, 2
0x14000c5e3  and     eax, 0B0h
0x14000c5e8  or      ecx, eax
0x14000c5ea  shl     ecx, 3
0x14000c5ed  or      ecx, 206h
0x14000c5f3  mov     dword ptr [rbp+var_30], ecx
0x14000c5f6  jmp     short loc_14000C607
0x14000c5f8  mov     [rbp+var_30], 0
0x14000c600  mov     dword ptr [rbp+var_30], 206h
0x14000c607  mov     rcx, [rbx]
0x14000c60a  add     rbx, 38h ; '8'
0x14000c60e  mov     rax, [rbp+var_30]
0x14000c612  mov     [rcx], rax
0x14000c615  jmp     short loc_14000C621
0x14000c617  cmp     qword ptr [rbx], 0
0x14000c61b  jnz     short loc_14000C628
0x14000c61d  add     rbx, 8
0x14000c621  cmp     rbx, r15
0x14000c624  jb      short loc_14000C617
0x14000c626  jmp     short loc_14000C668
0x14000c628  test    rbx, rbx
0x14000c62b  jnz     loc_14000C514
0x14000c631  jmp     short loc_14000C668
0x14000c633  mov     [rbp+var_30], 0
0x14000c63b  mov     dword ptr [rbp+var_30], 206h
0x14000c642  mov     rax, [rbp+var_30]
0x14000c646  mov     rcx, [rbx]
0x14000c649  add     rbx, 38h ; '8'
0x14000c64d  mov     [rcx], rax
0x14000c650  jmp     short loc_14000C65C
0x14000c652  cmp     qword ptr [rbx], 0
0x14000c656  jnz     short loc_14000C663
0x14000c658  add     rbx, 8
0x14000c65c  cmp     rbx, r15
0x14000c65f  jb      short loc_14000C652
0x14000c661  jmp     short loc_14000C668
0x14000c663  test    rbx, rbx
0x14000c666  jnz     short loc_14000C646
0x14000c668  mov     rcx, [rbp+var_8]
0x14000c66c  xor     rcx, rsp; StackCookie
0x14000c66f  call    __security_check_cookie
0x14000c674  add     rsp, 60h
0x14000c678  pop     r15
0x14000c67a  pop     rdi
0x14000c67b  pop     rsi
0x14000c67c  pop     rbx
0x14000c67d  pop     rbp
0x14000c67e  retn
```
