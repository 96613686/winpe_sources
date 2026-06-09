# SamrRidToSid

- ea: `0x180013b90`
- end: `0x180013df9`
- name: `SamrRidToSid`
- size: `617`
- prototype: `__int64 __fastcall(int, char)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180003760`
- `0x180008590`
- `0x1800096c0`
- `0x180013b90`
- `0x180013e00`
- `0x180016240`
- `0x180024dc0`
- `0x180027e24`
- `0x180061b18`
- `0x180061b88`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180013ca9`
- `ntdll!RtlSubAuthorityCountSid` at `0x180013cf0`
- `ntdll!RtlSubAuthorityCountSid` at `0x180013ca9`
- `ntdll!RtlSubAuthorityCountSid` at `0x180013cf0`
- `ntdll!RtlSubAuthoritySid` at `0x180013cfe`
- `ntdll!RtlSubAuthoritySid` at `0x180013cfe`
- `ntdll!RtlLengthRequiredSid` at `0x180013cb9`
- `ntdll!RtlLengthRequiredSid` at `0x180013cb9`
- `ntdll!RtlCopySid` at `0x180013ce7`
- `ntdll!RtlCopySid` at `0x180013ce7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013cc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013cc9`

## pseudocode

```c
__int64 __fastcall SamrRidToSid(__int64 a1, ULONG a2, PSID *a3)
{
  PUNICODE_STRING v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned __int8 v10; // r14
  unsigned int v11; // eax
  void *v12; // r15
  ULONG v13; // ebx
  ULONG v14; // r12d
  HLOCAL v15; // rax
  PULONG v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  int v20; // [rsp+70h] [rbp+8h] BYREF

  v20 = 0;
  if ( !a3 )
  {
    v6 = WPP_GLOBAL_Control;
    v7 = -1073741811;
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    {
      v8 = 10;
      v9 = 3221225485LL;
LABEL_33:
      WPP_SF_Dd(v6[3].Buffer, v8, WPP_da56f533e82b395e0b3d642362ca7a68_Traceguids, v9, v7);
      return v7;
    }
    return v7;
  }
  if ( !a1 )
    goto LABEL_9;
  v10 = 0;
  if ( (int)SampValidateContext((struct _SAMP_OBJECT *)a1) < 0 )
    goto LABEL_10;
  if ( (*(_BYTE *)(a1 + 192) & 2) != 0 && (*(_BYTE *)(a1 + 28) & 1) != 0 )
  {
    SampIncrementActiveThreads();
  }
  else
  {
LABEL_9:
    SampAcquireReadLock();
    v10 = 1;
  }
LABEL_10:
  v11 = SampLookupContextEx(a1, 0, 0, 5, &v20);
  v7 = v11;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids, v11, v11);
  if ( (v7 & 0x80000000) != 0 )
  {
    SampMaybeReleaseReadLock(v10);
  }
  else
  {
    if ( v20 == 4 || v20 == 1 || (unsigned int)(v20 - 2) < 2 )
    {
      v12 = (void *)*((_QWORD *)SampDefinedDomains + 170 * *(unsigned int *)(a1 + 200) + 1);
      v13 = (unsigned __int8)(*RtlSubAuthorityCountSid(v12) + 1);
      v14 = RtlLengthRequiredSid(v13);
      v15 = LocalAlloc(0x40u, v14);
      *a3 = v15;
      if ( v15 )
      {
        RtlCopySid(v14, v15, v12);
        *RtlSubAuthorityCountSid(*a3) = v13;
        v16 = RtlSubAuthoritySid(*a3, v13 - 1);
        v7 = 0;
        *v16 = a2;
      }
      else
      {
        v7 = -1073741670;
      }
      if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 126, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v7, v7);
    }
    else
    {
      v7 = -1073741811;
    }
    SampDeReferenceContext(a1, 0);
    SampMaybeReleaseReadLock(v10);
    if ( (v7 & 0x80000000) == 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 5u )
      {
        WPP_SF_qDd_sid_((int)WPP_GLOBAL_Control[3].Buffer, v17, v18, a1, a2, a2, *a3);
LABEL_30:
        v6 = WPP_GLOBAL_Control;
        goto LABEL_31;
      }
      goto LABEL_31;
    }
  }
  v6 = WPP_GLOBAL_Control;
  if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 2u )
  {
    WPP_SF_qDdD(WPP_GLOBAL_Control[3].Buffer, v17, v18, a1, a2, a2, v7);
    goto LABEL_30;
  }
LABEL_31:
  if ( (*(_DWORD *)(&v6[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v8 = 13;
    v9 = v7;
    goto LABEL_33;
  }
  return v7;
}

```

## disassembly

```asm
0x180013b90  push    rbx
0x180013b92  push    rbp
0x180013b93  push    rsi
0x180013b94  push    rdi
0x180013b95  sub     rsp, 48h
0x180013b99  mov     [rsp+68h+arg_0], 0
0x180013ba1  mov     rdi, r8
0x180013ba4  mov     ebp, edx
0x180013ba6  mov     rsi, rcx
0x180013ba9  test    r8, r8
0x180013bac  jnz     short loc_180013BD7
0x180013bae  mov     rcx, cs:WPP_GLOBAL_Control; struct _SAMP_OBJECT *
0x180013bb5  mov     ebx, 0C000000Dh
0x180013bba  test    dword ptr [rcx+44h], 20000h
0x180013bc1  jz      loc_180013DEE
0x180013bc7  mov     edx, 0Ah
0x180013bcc  mov     r9d, 0C000000Dh
0x180013bd2  jmp     loc_180013DDA
0x180013bd7  mov     [rsp+68h+arg_10], r14
0x180013bdf  test    rsi, rsi
0x180013be2  jz      short loc_180013C06
0x180013be4  xor     r14b, r14b
0x180013be7  call    ?SampValidateContext@@YAJPEAU_SAMP_OBJECT@@@Z; SampValidateContext(_SAMP_OBJECT *)
0x180013bec  test    eax, eax
0x180013bee  js      short loc_180013C0E
0x180013bf0  test    byte ptr [rsi+0C0h], 2
0x180013bf7  jz      short loc_180013C06
0x180013bf9  test    byte ptr [rsi+1Ch], 1
0x180013bfd  jz      short loc_180013C06
0x180013bff  call    SampIncrementActiveThreads
0x180013c04  jmp     short loc_180013C0E
0x180013c06  call    SampAcquireReadLock
0x180013c0b  mov     r14b, 1
0x180013c0e  lea     rax, [rsp+68h+arg_0]
0x180013c13  mov     r9d, 5
0x180013c19  xor     r8d, r8d
0x180013c1c  mov     qword ptr [rsp+68h+var_48], rax
0x180013c21  xor     edx, edx
0x180013c23  mov     rcx, rsi
0x180013c26  call    ?SampLookupContextEx@@YAJPEAU_SAMP_OBJECT@@KPEAU_RTL_BITMAP@@W4_SAMP_OBJECT_TYPE@@PEAW43@@Z; SampLookupContextEx(_SAMP_OBJECT *,ulong,_RTL_BITMAP *,_SAMP_OBJECT_TYPE,_SAMP_OBJECT_TYPE *)
0x180013c2b  mov     ebx, eax
0x180013c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c34  test    dword ptr [rcx+44h], 20000h
0x180013c3b  jz      short loc_180013C59
0x180013c3d  mov     rcx, [rcx+38h]
0x180013c41  lea     r8, WPP_16cad3e18f1834c4d3a59fb2d3abb5df_Traceguids
0x180013c48  mov     edx, 10h
0x180013c4d  mov     dword ptr [rsp+68h+var_48], eax
0x180013c51  mov     r9d, eax
0x180013c54  call    WPP_SF_Dd
0x180013c59  test    ebx, ebx
0x180013c5b  js      loc_180013D86
0x180013c61  mov     ecx, [rsp+68h+arg_0]
0x180013c65  cmp     ecx, 4
0x180013c68  jz      short loc_180013C83
0x180013c6a  sub     ecx, 1
0x180013c6d  jz      short loc_180013C83
0x180013c6f  sub     ecx, 1
0x180013c72  jz      short loc_180013C83
0x180013c74  cmp     ecx, 1
0x180013c77  jz      short loc_180013C83
0x180013c79  mov     ebx, 0C000000Dh
0x180013c7e  jmp     loc_180013D3E
0x180013c83  mov     eax, [rsi+0C8h]
0x180013c89  imul    rcx, rax, 550h
0x180013c90  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180013c97  mov     [rsp+68h+arg_8], r12
0x180013c9c  mov     [rsp+68h+var_28], r15
0x180013ca1  mov     r15, [rcx+rax+8]
0x180013ca6  mov     rcx, r15; Sid
0x180013ca9  call    cs:__imp_RtlSubAuthorityCountSid
0x180013caf  movzx   ecx, byte ptr [rax]
0x180013cb2  inc     cl
0x180013cb4  movzx   ebx, cl
0x180013cb7  mov     ecx, ebx; SubAuthorityCount
0x180013cb9  call    cs:__imp_RtlLengthRequiredSid
0x180013cbf  mov     edx, eax; uBytes
0x180013cc1  mov     ecx, 40h ; '@'; uFlags
0x180013cc6  mov     r12d, eax
0x180013cc9  call    cs:__imp_LocalAlloc
0x180013ccf  mov     [rdi], rax
0x180013cd2  test    rax, rax
0x180013cd5  jnz     short loc_180013CDE
0x180013cd7  mov     ebx, 0C000009Ah
0x180013cdc  jmp     short loc_180013D08
0x180013cde  mov     r8, r15; SourceSid
0x180013ce1  mov     rdx, rax; DestinationSid
0x180013ce4  mov     ecx, r12d; DestinationSidLength
0x180013ce7  call    cs:__imp_RtlCopySid
0x180013ced  mov     rcx, [rdi]; Sid
0x180013cf0  call    cs:__imp_RtlSubAuthorityCountSid
0x180013cf6  lea     edx, [rbx-1]; SubAuthority
0x180013cf9  mov     [rax], bl
0x180013cfb  mov     rcx, [rdi]; Sid
0x180013cfe  call    cs:__imp_RtlSubAuthoritySid
0x180013d04  xor     ebx, ebx
0x180013d06  mov     [rax], ebp
0x180013d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d0f  mov     r15, [rsp+68h+var_28]
0x180013d14  mov     r12, [rsp+68h+arg_8]
0x180013d19  test    dword ptr [rcx+44h], 20000h
0x180013d20  jz      short loc_180013D3E
0x180013d22  mov     rcx, [rcx+38h]
0x180013d26  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180013d2d  mov     edx, 7Eh ; '~'
0x180013d32  mov     dword ptr [rsp+68h+var_48], ebx
0x180013d36  mov     r9d, ebx
0x180013d39  call    WPP_SF_Dd
0x180013d3e  xor     edx, edx
0x180013d40  mov     rcx, rsi
0x180013d43  call    SampDeReferenceContext
0x180013d48  movzx   ecx, r14b; unsigned __int8
0x180013d4c  call    ?SampMaybeReleaseReadLock@@YAXE@Z; SampMaybeReleaseReadLock(uchar)
0x180013d51  test    ebx, ebx
0x180013d53  js      short loc_180013D8F
0x180013d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d5c  test    byte ptr [rcx+44h], 8
0x180013d60  jz      short loc_180013DC1
0x180013d62  cmp     byte ptr [rcx+41h], 5
0x180013d66  jb      short loc_180013DC1
0x180013d68  mov     rax, [rdi]
0x180013d6b  mov     r9, rsi; int
0x180013d6e  mov     rcx, [rcx+38h]; int
0x180013d72  mov     [rsp+68h+pSid], rax; pSid
0x180013d77  mov     dword ptr [rsp+68h+var_40], ebp; char
0x180013d7b  mov     dword ptr [rsp+68h+var_48], ebp; char
0x180013d7f  call    WPP_SF_qDd_sid_
0x180013d84  jmp     short loc_180013DBA
0x180013d86  movzx   ecx, r14b; unsigned __int8
0x180013d8a  call    ?SampMaybeReleaseReadLock@@YAXE@Z; SampMaybeReleaseReadLock(uchar)
0x180013d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d96  test    byte ptr [rcx+44h], 8
0x180013d9a  jz      short loc_180013DC1
0x180013d9c  cmp     byte ptr [rcx+41h], 2
0x180013da0  jb      short loc_180013DC1
0x180013da2  mov     rcx, [rcx+38h]
0x180013da6  mov     r9, rsi
0x180013da9  mov     dword ptr [rsp+68h+pSid], ebx
0x180013dad  mov     dword ptr [rsp+68h+var_40], ebp
0x180013db1  mov     dword ptr [rsp+68h+var_48], ebp
0x180013db5  call    WPP_SF_qDdD
0x180013dba  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dc1  test    dword ptr [rcx+44h], 20000h
0x180013dc8  mov     r14, [rsp+68h+arg_10]
0x180013dd0  jz      short loc_180013DEE
0x180013dd2  mov     edx, 0Dh
0x180013dd7  mov     r9d, ebx
0x180013dda  mov     rcx, [rcx+38h]
0x180013dde  lea     r8, WPP_da56f533e82b395e0b3d642362ca7a68_Traceguids
0x180013de5  mov     dword ptr [rsp+68h+var_48], ebx
0x180013de9  call    WPP_SF_Dd
0x180013dee  mov     eax, ebx
0x180013df0  add     rsp, 48h
0x180013df4  pop     rdi
0x180013df5  pop     rsi
0x180013df6  pop     rbp
0x180013df7  pop     rbx
0x180013df8  retn
```
