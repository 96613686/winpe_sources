# SampContextOwnerIsCurrentCaller(_SAMP_OBJECT *)

- ea: `0x18001e1b0`
- end: `0x18001e41b`
- name: `?SampContextOwnerIsCurrentCaller@@YAEPEAU_SAMP_OBJECT@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800096c0`

## callees

- `0x18001ce50`
- `0x18001e1b0`
- `0x180027e24`
- `0x180037284`
- `0x1800372ac`
- `0x18004e3d0`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001e2b5`
- `ntdll!RtlLengthSid` at `0x18001e2b5`
- `ntdll!RtlEqualSid` at `0x18001e268`
- `ntdll!RtlEqualSid` at `0x18001e268`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e2c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001e2c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e27b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e330`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e27b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e330`
- `LSASRV!LsaIRetrieveCurrentUserSid` at `0x18001e201`
- `LSASRV!LsaIRetrieveCurrentUserSid` at `0x18001e201`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001e240`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001e240`

## pseudocode

```c
__int64 __fastcall SampContextOwnerIsCurrentCaller(struct _SAMP_OBJECT *a1)
{
  void **v1; // rax
  unsigned __int8 v2; // bl
  void *v3; // r12
  int v4; // ebp
  struct _TOKEN_USER *v5; // r14
  void *v6; // rdi
  int v7; // esi
  PUNICODE_STRING v8; // rcx
  SIZE_T v10; // r15
  HLOCAL v11; // rax
  int CurrentUser; // eax
  int v13; // [rsp+70h] [rbp+8h] BYREF
  PVOID Buffer; // [rsp+78h] [rbp+10h] BYREF
  struct _TOKEN_USER *v15; // [rsp+80h] [rbp+18h] BYREF

  v1 = (void **)*((_QWORD *)a1 + 23);
  v2 = 1;
  if ( !v1 )
    goto LABEL_14;
  v3 = *v1;
  v2 = 0;
  v4 = 1;
  Buffer = 0;
  v5 = 0;
  v15 = 0;
  v6 = 0;
  v7 = LsaIRetrieveCurrentUserSid(&Buffer);
  if ( v7 < 0 )
  {
    v13 = 0;
    CurrentUser = SampGetCurrentUser(0, &v15, &v13);
    v5 = v15;
    v7 = CurrentUser;
    if ( CurrentUser >= 0 )
    {
      v4 = 0;
      Buffer = v15->User.Sid;
    }
  }
  if ( Buffer )
  {
    v10 = RtlLengthSid(Buffer);
    v11 = LocalAlloc(0x40u, v10);
    v6 = v11;
    if ( v11 )
      memcpy_0(v11, Buffer, v10);
    else
      v7 = -1073741670;
  }
  if ( v5 )
    LocalFree(v5);
  if ( v4 )
    LsaFreeMemory(Buffer);
  v8 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 75, WPP_5505de3e48bd33375e96ca021b170945_Traceguids, (unsigned int)v7, v7);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v7 >= 0 )
  {
    if ( RtlEqualSid(v3, v6) )
    {
      v2 = 1;
    }
    else if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20) != 0
           && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
    {
      WPP_SF__sid__sid_(WPP_GLOBAL_Control[3].Buffer, 11, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v3, v6);
    }
    LocalFree(v6);
    if ( v2 )
      goto LABEL_14;
    goto LABEL_29;
  }
  if ( (*(_BYTE *)(&v8[4].MaximumLength + 1) & 0x20) == 0 )
    goto LABEL_15;
  if ( HIBYTE(v8[4].Length) >= 2u )
  {
    WPP_SF_d(v8[3].Buffer, 12, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, (unsigned int)v7);
LABEL_29:
    v8 = WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)(&v8[4].MaximumLength + 1) & 0x20) != 0 && HIBYTE(v8[4].Length) >= 2u )
  {
    WPP_SF_(v8[3].Buffer, 13, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids);
LABEL_14:
    v8 = WPP_GLOBAL_Control;
  }
LABEL_15:
  if ( (*(_DWORD *)(&v8[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_d(v8[3].Buffer, 14, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x18001e1b0  mov     r11, rsp
0x18001e1b3  push    rbx
0x18001e1b4  sub     rsp, 60h
0x18001e1b8  mov     rax, [rcx+0B8h]
0x18001e1bf  mov     bl, 1
0x18001e1c1  mov     [r11-18h], rsi
0x18001e1c5  mov     [r11-20h], rdi
0x18001e1c9  mov     [r11-28h], r12
0x18001e1cd  test    rax, rax
0x18001e1d0  jz      loc_18001E289
0x18001e1d6  mov     r12, [rax]
0x18001e1d9  lea     rcx, [r11+10h]
0x18001e1dd  mov     [r11-10h], rbp
0x18001e1e1  xor     bl, bl
0x18001e1e3  mov     [r11-30h], r14
0x18001e1e7  mov     ebp, 1
0x18001e1ec  mov     [r11-38h], r15
0x18001e1f0  xor     r15d, r15d
0x18001e1f3  mov     [r11+10h], r15
0x18001e1f7  mov     r14d, r15d
0x18001e1fa  mov     [r11+18h], r15
0x18001e1fe  mov     edi, r15d
0x18001e201  call    cs:__imp_LsaIRetrieveCurrentUserSid
0x18001e207  mov     esi, eax
0x18001e209  test    eax, eax
0x18001e20b  js      loc_18001E2F2
0x18001e211  mov     rcx, [rsp+68h+Buffer]; Sid
0x18001e216  test    rcx, rcx
0x18001e219  jnz     loc_18001E2B5
0x18001e21f  mov     r15, [rsp+68h+var_38]
0x18001e224  test    r14, r14
0x18001e227  jnz     loc_18001E32D
0x18001e22d  mov     r14, [rsp+68h+var_30]
0x18001e232  test    ebp, ebp
0x18001e234  mov     rbp, [rsp+68h+var_10]
0x18001e239  jz      short loc_18001E246
0x18001e23b  mov     rcx, [rsp+68h+Buffer]; Buffer
0x18001e240  call    cs:__imp_LsaFreeMemory
0x18001e246  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e24d  test    dword ptr [rcx+44h], 20000h
0x18001e254  jnz     loc_18001E33B
0x18001e25a  test    esi, esi
0x18001e25c  js      loc_18001E3A0
0x18001e262  mov     rdx, rdi; Sid2
0x18001e265  mov     rcx, r12; Sid1
0x18001e268  call    cs:__imp_RtlEqualSid
0x18001e26e  test    al, al
0x18001e270  jz      loc_18001E363
0x18001e276  mov     bl, 1
0x18001e278  mov     rcx, rdi; hMem
0x18001e27b  call    cs:__imp_LocalFree
0x18001e281  test    bl, bl
0x18001e283  jz      loc_18001E3C8
0x18001e289  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e290  test    dword ptr [rcx+44h], 20000h
0x18001e297  mov     r12, [rsp+68h+var_28]
0x18001e29c  mov     rdi, [rsp+68h+var_20]
0x18001e2a1  mov     rsi, [rsp+68h+var_18]
0x18001e2a6  jnz     loc_18001E3FD
0x18001e2ac  movzx   eax, bl
0x18001e2af  add     rsp, 60h
0x18001e2b3  pop     rbx
0x18001e2b4  retn
0x18001e2b5  call    cs:__imp_RtlLengthSid
0x18001e2bb  mov     edx, eax; uBytes
0x18001e2bd  mov     ecx, 40h ; '@'; uFlags
0x18001e2c2  mov     r15d, eax
0x18001e2c5  call    cs:__imp_LocalAlloc
0x18001e2cb  mov     rdi, rax
0x18001e2ce  test    rax, rax
0x18001e2d1  jnz     short loc_18001E2DD
0x18001e2d3  mov     esi, 0C000009Ah
0x18001e2d8  jmp     loc_18001E21F
0x18001e2dd  mov     rdx, [rsp+68h+Buffer]; Src
0x18001e2e2  mov     r8, r15; Size
0x18001e2e5  mov     rcx, rax; void *
0x18001e2e8  call    memcpy_0
0x18001e2ed  jmp     loc_18001E21F
0x18001e2f2  lea     r8, [rsp+68h+arg_0]; int *
0x18001e2f7  mov     [rsp+68h+arg_0], r15d
0x18001e2fc  lea     rdx, [rsp+68h+arg_10]; struct _TOKEN_USER **
0x18001e304  xor     ecx, ecx; TokenHandle
0x18001e306  call    ?SampGetCurrentUser@@YAJPEAXPEAPEAU_TOKEN_USER@@PEAH@Z; SampGetCurrentUser(void *,_TOKEN_USER * *,int *)
0x18001e30b  mov     r14, [rsp+68h+arg_10]
0x18001e313  mov     esi, eax
0x18001e315  test    eax, eax
0x18001e317  js      loc_18001E211
0x18001e31d  mov     rax, [r14]
0x18001e320  mov     ebp, r15d
0x18001e323  mov     [rsp+68h+Buffer], rax
0x18001e328  jmp     loc_18001E211
0x18001e32d  mov     rcx, r14; hMem
0x18001e330  call    cs:__imp_LocalFree
0x18001e336  jmp     loc_18001E22D
0x18001e33b  mov     rcx, [rcx+38h]
0x18001e33f  lea     r8, WPP_5505de3e48bd33375e96ca021b170945_Traceguids
0x18001e346  mov     edx, 4Bh ; 'K'
0x18001e34b  mov     dword ptr [rsp+68h+var_48], esi
0x18001e34f  mov     r9d, esi
0x18001e352  call    WPP_SF_Dd
0x18001e357  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e35e  jmp     loc_18001E25A
0x18001e363  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e36a  test    byte ptr [rcx+44h], 20h
0x18001e36e  jz      loc_18001E278
0x18001e374  cmp     byte ptr [rcx+41h], 2
0x18001e378  jb      loc_18001E278
0x18001e37e  mov     rcx, [rcx+38h]
0x18001e382  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18001e389  mov     edx, 0Bh
0x18001e38e  mov     [rsp+68h+var_48], rdi
0x18001e393  mov     r9, r12
0x18001e396  call    WPP_SF__sid__sid_
0x18001e39b  jmp     loc_18001E278
0x18001e3a0  test    byte ptr [rcx+44h], 20h
0x18001e3a4  jz      loc_18001E290
0x18001e3aa  cmp     byte ptr [rcx+41h], 2
0x18001e3ae  jb      short loc_18001E3CF
0x18001e3b0  mov     rcx, [rcx+38h]
0x18001e3b4  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18001e3bb  mov     edx, 0Ch
0x18001e3c0  mov     r9d, esi
0x18001e3c3  call    WPP_SF_d
0x18001e3c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3cf  test    byte ptr [rcx+44h], 20h
0x18001e3d3  jz      loc_18001E290
0x18001e3d9  cmp     byte ptr [rcx+41h], 2
0x18001e3dd  jb      loc_18001E290
0x18001e3e3  mov     rcx, [rcx+38h]
0x18001e3e7  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18001e3ee  mov     edx, 0Dh
0x18001e3f3  call    WPP_SF_
0x18001e3f8  jmp     loc_18001E289
0x18001e3fd  mov     rcx, [rcx+38h]
0x18001e401  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x18001e408  movzx   r9d, bl
0x18001e40c  mov     edx, 0Eh
0x18001e411  call    WPP_SF_d
0x18001e416  jmp     loc_18001E2AC
```
