# LdapGoToFirstAttribute(ldap_connection *,CLdapBer *)

- ea: `0x180002770`
- end: `0x1800030e9`
- name: `?LdapGoToFirstAttribute@@YAKPEAUldap_connection@@PEAVCLdapBer@@@Z`
- size: `2425`
- prototype: `unsigned int(struct ldap_connection *, struct CLdapBer *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005170`
- `0x18001ba9c`

## callees

- `0x1800014e0`
- `0x180001790`
- `0x180002770`
- `0x1800030f0`
- `0x180003570`
- `0x1800037a8`
- `0x180027530`

## string_xrefs

- `0x180002c7a`: `ldapFirstAttr 1 connection 0x%x received protocol error 0x%x .\n`
- `0x180002b49`: `ldapFirstAttr 2 connection 0x%x received protocol error 0x%x .\n`
- `0x180002d2c`: `ldapFirstAttr 8 connection 0x%x received protocol error 0x%x .\n`
- `0x180002eed`: `ldapFirstAttr 3 connection 0x%x received protocol error 0x%x .\n`
- `0x18000300a`: `ldapFirstAttr 4 connection 0x%x received protocol error 0x%x .\n`
- `0x180002ccc`: `ldapFirstAttr 5 connection 0x%x received protocol error 0x%x .\n`
- `0x180002ba8`: `ldapFirstAttr 6 connection 0x%x received protocol error 0x%x .\n`
- `0x180002afb`: `ldapFirstAttr 7 connection 0x%x received protocol error 0x%x .\n`
- `0x180002db8`: `HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n`
- `0x180002f30`: `HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n`
- `0x180003054`: `HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n`
- `0x180002de0`: `HrStartReadSequence expected tag of 0x%x, received 0x%x.\n`
- `0x180002f70`: `HrStartReadSequence expected tag of 0x%x, received 0x%x.\n`
- `0x180003073`: `HrStartReadSequence expected tag of 0x%x, received 0x%x.\n`
- `0x180002df5`: `HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n`
- `0x180002f7c`: `HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n`
- `0x18000307c`: `HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n`

## pseudocode

```c
__int64 __fastcall LdapGoToFirstAttribute(struct ldap_connection *a1, struct CLdapBer *a2)
{
  __int64 v2; // r8
  unsigned int *v3; // r14
  unsigned int *v4; // rsi
  unsigned int v7; // edi
  unsigned __int8 *v8; // rcx
  char v9; // cl
  int v10; // eax
  unsigned int Length; // r10d
  unsigned int v12; // eax
  unsigned int v13; // r8d
  unsigned int v14; // ecx
  unsigned int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // ecx
  __int64 v18; // r9
  __int64 v19; // r8
  char v20; // r9
  int v21; // r9d
  __int64 v22; // rax
  unsigned int v23; // edx
  unsigned int v24; // ecx
  unsigned int v25; // eax
  unsigned int v26; // r8d
  unsigned int v27; // eax
  unsigned int v28; // r8d
  unsigned int v29; // ecx
  __int64 v30; // r9
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // r9
  char v34; // r8
  int v35; // r8d
  __int64 v36; // rax
  unsigned int v37; // edx
  unsigned int v38; // ecx
  const char *v40; // rdx
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int Sequence; // eax
  unsigned int v44; // [rsp+68h] [rbp+10h] BYREF
  unsigned int v45; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v46; // [rsp+78h] [rbp+20h] BYREF

  v2 = *(unsigned int *)a2;
  v3 = (unsigned int *)((char *)a2 + 836);
  v4 = (unsigned int *)((char *)a2 + 840);
  v44 = 0;
  *((_DWORD *)a2 + 1) = 0;
  *((_DWORD *)a2 + 209) = 0;
  v7 = 0;
  *((_DWORD *)a2 + 210) = 0;
  *((_DWORD *)a2 + 8) = 0;
  if ( !(_DWORD)v2 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n", 0, 0);
    Length = 16;
    goto LABEL_83;
  }
  v8 = (unsigned __int8 *)*((_QWORD *)a2 + 2);
  if ( *v8 != 48 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrStartReadSequence expected tag of 0x%x, received 0x%x.\n", 48, *v8);
    goto LABEL_48;
  }
  *((_DWORD *)a2 + 1) = 1;
  if ( (unsigned int)v2 <= 1 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n", v2, 1);
    goto LABEL_48;
  }
  v9 = v8[1];
  v10 = 1;
  *((_DWORD *)a2 + 9) = 1;
  if ( v9 < 0 )
    v10 = (v9 & 0x7F) + 1;
  *((_DWORD *)a2 + 10) = v10;
  *(_QWORD *)((char *)a2 + 44) = 0;
  *((_DWORD *)a2 + 8) = 1;
  Length = CLdapBer::HrGetLength(a2, v3);
  if ( Length )
    CLdapBer::HrPopSeqStack(a2, &v46, &v45, v4, v3);
  else
    *v4 = *((_DWORD *)a2 + 1);
  v12 = *((_DWORD *)a2 + 1);
  v13 = *(_DWORD *)a2;
  if ( v12 > *(_DWORD *)a2 )
  {
LABEL_48:
    Length = -2147024809;
LABEL_83:
    if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
      return 84;
    v40 = "ldapFirstAttr 1 connection 0x%x received protocol error 0x%x .\n";
    goto LABEL_58;
  }
  if ( Length )
    goto LABEL_83;
  v45 = 0;
  if ( v13 <= v12 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrSkipElement ran out of data, length 0x%x, offset 0x%x.\n", v13, v12);
    Length = 16;
    goto LABEL_61;
  }
  *((_DWORD *)a2 + 1) = v12 + 1;
  Length = CLdapBer::HrGetLength(a2, &v45);
  if ( Length )
  {
LABEL_61:
    if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
      return 84;
    v40 = "ldapFirstAttr 2 connection 0x%x received protocol error 0x%x .\n";
    goto LABEL_58;
  }
  v14 = *((_DWORD *)a2 + 1);
  if ( v14 < *(_DWORD *)a2 )
    *((_DWORD *)a2 + 1) = v45 + v14;
  v15 = *((_DWORD *)a2 + 1);
  if ( *(_DWORD *)a2 <= v15 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrPeekTag ran out of data, length 0x%x, offset 0x%x.\n", *(_DWORD *)a2, v15);
  }
  else
  {
    v7 = *(unsigned __int8 *)(v15 + *((_QWORD *)a2 + 2));
    v44 = v7;
  }
  if ( *((_QWORD *)a1 + 120) != -1 && *((_DWORD *)a1 + 250) == 2 && v7 == 4 )
  {
    v42 = CLdapBer::HrSkipElement(a2);
    if ( v42 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldapFirstAttr 8 connection 0x%x received protocol error 0x%x .\n", a1, v42);
      return 84;
    }
    CLdapBer::HrPeekTag(a2, &v44);
    v7 = v44;
  }
  if ( v7 == 48 )
  {
    Sequence = CLdapBer::HrStartReadSequence(a2, 0x30u, 0);
    if ( Sequence )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldapFirstAttr 3 connection 0x%x received protocol error 0x%x .\n", a1, Sequence);
      return 84;
    }
    CLdapBer::HrPeekTag(a2, &v44);
    v7 = v44;
  }
  v16 = *((unsigned int *)a2 + 1);
  v17 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 <= (unsigned int)v16 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n", v17, v16);
    Length = 16;
    goto LABEL_67;
  }
  v18 = *((_QWORD *)a2 + 2);
  if ( *(_BYTE *)(v16 + v18) != 100 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(
        0x2000,
        "HrStartReadSequence expected tag of 0x%x, received 0x%x.\n",
        100,
        *(unsigned __int8 *)(v16 + v18));
    goto LABEL_50;
  }
  v19 = (unsigned int)(v16 + 1);
  *((_DWORD *)a2 + 1) = v19;
  if ( v17 <= (unsigned int)v19 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(
        0x2000,
        "HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n",
        v17,
        (unsigned int)v19);
    goto LABEL_50;
  }
  v20 = *(_BYTE *)(v19 + v18);
  if ( v20 >= 0 )
    v21 = 1;
  else
    v21 = (v20 & 0x7F) + 1;
  v22 = *((unsigned int *)a2 + 8);
  if ( (unsigned int)v22 >= 0x32 )
  {
    Length = -2147024882;
  }
  else
  {
    v23 = *v3;
    v24 = *v4;
    *((_DWORD *)a2 + 4 * v22 + 9) = v19;
    *((_DWORD *)a2 + 4 * *((unsigned int *)a2 + 8) + 10) = v21;
    *((_DWORD *)a2 + 4 * *((unsigned int *)a2 + 8) + 11) = v24;
    *((_DWORD *)a2 + 4 * (unsigned int)(*((_DWORD *)a2 + 8))++ + 12) = v23;
    Length = CLdapBer::HrGetLength(a2, v3);
    if ( Length )
      CLdapBer::HrPopSeqStack(a2, &v45, &v44, v4, v3);
    else
      *v4 = *((_DWORD *)a2 + 1);
  }
  v25 = *((_DWORD *)a2 + 1);
  v26 = *(_DWORD *)a2;
  if ( v25 > *(_DWORD *)a2 )
  {
LABEL_50:
    Length = -2147024809;
LABEL_67:
    if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
      return 84;
    v40 = "ldapFirstAttr 4 connection 0x%x received protocol error 0x%x .\n";
    goto LABEL_58;
  }
  if ( Length )
    goto LABEL_67;
  if ( v26 <= v25 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrPeekTag ran out of data, length 0x%x, offset 0x%x.\n", v26, v25);
  }
  else
  {
    v7 = *(unsigned __int8 *)(v25 + *((_QWORD *)a2 + 2));
  }
  if ( v7 == 48 )
  {
    v41 = CLdapBer::HrStartReadSequence(a2, 0x30u, 0);
    if ( v41 )
    {
      if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x400000) != 0 )
        LDAPClientPrint(0x400000, "ldapFirstAttr 5 connection 0x%x received protocol error 0x%x .\n", a1, v41);
      return 84;
    }
  }
  v27 = *((_DWORD *)a2 + 1);
  v28 = *(_DWORD *)a2;
  v44 = 0;
  if ( v28 <= v27 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrSkipElement ran out of data, length 0x%x, offset 0x%x.\n", v28, v27);
    Length = 16;
    goto LABEL_69;
  }
  *((_DWORD *)a2 + 1) = v27 + 1;
  Length = CLdapBer::HrGetLength(a2, &v44);
  if ( Length )
  {
LABEL_69:
    if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
      return 84;
    v40 = "ldapFirstAttr 6 connection 0x%x received protocol error 0x%x .\n";
    goto LABEL_58;
  }
  v29 = *((_DWORD *)a2 + 1);
  if ( v29 < *(_DWORD *)a2 )
    *((_DWORD *)a2 + 1) = v44 + v29;
  v30 = *((unsigned int *)a2 + 1);
  v31 = *(unsigned int *)a2;
  if ( (unsigned int)v31 <= (unsigned int)v30 )
  {
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
      LDAPClientPrint(0x2000, "HrStartReadSequence ran out of data, length 0x%x, offset 0x%x.\n", v31, v30);
    Length = 16;
  }
  else
  {
    v32 = *((_QWORD *)a2 + 2);
    if ( *(_BYTE *)(v30 + v32) == 48 )
    {
      v33 = (unsigned int)(v30 + 1);
      *((_DWORD *)a2 + 1) = v33;
      if ( (unsigned int)v31 <= (unsigned int)v33 )
      {
        if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
          LDAPClientPrint(0x2000, "HrStartReadSequence 2 ran out of data, length 0x%x, offset 0x%x.\n", v31, v33);
      }
      else
      {
        v34 = *(_BYTE *)(v33 + v32);
        if ( v34 >= 0 )
          v35 = 1;
        else
          v35 = (v34 & 0x7F) + 1;
        v36 = *((unsigned int *)a2 + 8);
        if ( (unsigned int)v36 >= 0x32 )
        {
          Length = -2147024882;
        }
        else
        {
          v37 = *v3;
          v38 = *v4;
          *((_DWORD *)a2 + 4 * v36 + 9) = v33;
          *((_DWORD *)a2 + 4 * *((unsigned int *)a2 + 8) + 10) = v35;
          *((_DWORD *)a2 + 4 * *((unsigned int *)a2 + 8) + 11) = v38;
          *((_DWORD *)a2 + 4 * (unsigned int)(*((_DWORD *)a2 + 8))++ + 12) = v37;
          Length = CLdapBer::HrGetLength(a2, v3);
          if ( Length )
            CLdapBer::HrPopSeqStack(a2, &v45, &v44, v4, v3);
          else
            *v4 = *((_DWORD *)a2 + 1);
        }
        if ( *((_DWORD *)a2 + 1) <= *(_DWORD *)a2 )
        {
          if ( !Length )
            return 0;
          goto LABEL_54;
        }
      }
    }
    else if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x2000) != 0 )
    {
      LDAPClientPrint(
        0x2000,
        "HrStartReadSequence expected tag of 0x%x, received 0x%x.\n",
        48,
        *(unsigned __int8 *)(v30 + v32));
    }
    Length = -2147024809;
  }
LABEL_54:
  if ( !g_fTracingOn || !g_fProviderEnabled || (g_ulTraceFlags & 0x400000) == 0 )
    return 84;
  v40 = "ldapFirstAttr 7 connection 0x%x received protocol error 0x%x .\n";
LABEL_58:
  LDAPClientPrint(0x400000, v40, a1, Length);
  return 84;
}

```

## disassembly

```asm
0x180002770  mov     [rsp+arg_0], rbx
0x180002775  push    rbp
0x180002776  push    rsi
0x180002777  push    rdi
0x180002778  push    r14
0x18000277a  push    r15
0x18000277c  sub     rsp, 30h
0x180002780  mov     r8d, [rdx]
0x180002783  lea     r14, [rdx+344h]
0x18000278a  xor     r15d, r15d
0x18000278d  lea     rsi, [rdx+348h]
0x180002794  mov     [rsp+58h+arg_8], r15d
0x180002799  mov     rbx, rdx
0x18000279c  mov     [rdx+4], r15d
0x1800027a0  mov     rbp, rcx
0x1800027a3  mov     [r14], r15d
0x1800027a6  mov     edi, r15d
0x1800027a9  mov     [rsi], r15d
0x1800027ac  mov     [rdx+20h], r15d
0x1800027b0  test    r8d, r8d
0x1800027b3  jz      loc_180002C3C
0x1800027b9  mov     rcx, [rdx+10h]
0x1800027bd  movzx   eax, byte ptr [rcx]
0x1800027c0  cmp     al, 30h ; '0'
0x1800027c2  jnz     loc_180002D66
0x1800027c8  mov     dword ptr [rdx+4], 1
0x1800027cf  cmp     r8d, 1
0x1800027d3  jbe     loc_180002E0B
0x1800027d9  movzx   ecx, byte ptr [rcx+1]
0x1800027dd  mov     eax, 1
0x1800027e2  mov     edx, ecx
0x1800027e4  mov     dword ptr [rbx+24h], 1
0x1800027eb  and     edx, 7Fh
0x1800027ee  inc     edx
0x1800027f0  test    cl, cl
0x1800027f2  mov     rcx, rbx; this
0x1800027f5  cmovs   eax, edx
0x1800027f8  mov     rdx, r14; unsigned int *
0x1800027fb  mov     [rbx+28h], eax
0x1800027fe  mov     [rbx+2Ch], r15
0x180002802  mov     dword ptr [rbx+20h], 1
0x180002809  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x18000280e  mov     r10d, eax
0x180002811  test    eax, eax
0x180002813  jnz     loc_180002E38
0x180002819  mov     eax, [rbx+4]
0x18000281c  mov     [rsi], eax
0x18000281e  mov     eax, [rbx+4]
0x180002821  mov     r8d, [rbx]
0x180002824  cmp     eax, r8d
0x180002827  ja      loc_180002A9A
0x18000282d  test    r10d, r10d
0x180002830  jnz     loc_180002C4F
0x180002836  mov     [rsp+58h+arg_10], r15d
0x18000283b  cmp     r8d, eax
0x18000283e  jbe     loc_180002E57
0x180002844  inc     eax
0x180002846  lea     rdx, [rsp+58h+arg_10]; unsigned int *
0x18000284b  mov     rcx, rbx; this
0x18000284e  mov     [rbx+4], eax
0x180002851  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x180002856  mov     r10d, eax
0x180002859  test    eax, eax
0x18000285b  jnz     loc_180002B2A
0x180002861  mov     ecx, [rbx+4]
0x180002864  cmp     ecx, [rbx]
0x180002866  jnb     short loc_180002871
0x180002868  add     ecx, [rsp+58h+arg_10]
0x18000286c  mov     [rbx+4], ecx
0x18000286f  jmp     short loc_180002879
0x180002871  test    eax, eax
0x180002873  jnz     loc_180002B2A
0x180002879  mov     eax, [rbx+4]
0x18000287c  mov     r8d, [rbx]
0x18000287f  cmp     r8d, eax
0x180002882  jbe     loc_180002BB4
0x180002888  mov     ecx, eax
0x18000288a  mov     rax, [rbx+10h]
0x18000288e  movzx   edi, byte ptr [rcx+rax]
0x180002892  mov     [rsp+58h+arg_8], edi
0x180002896  cmp     qword ptr [rbp+3C0h], 0FFFFFFFFFFFFFFFFh
0x18000289e  jnz     loc_180002CD8
0x1800028a4  cmp     edi, 30h ; '0'
0x1800028a7  jz      loc_180002EAB
0x1800028ad  mov     r8d, [rbx+4]
0x1800028b1  mov     ecx, [rbx]
0x1800028b3  cmp     ecx, r8d
0x1800028b6  jbe     loc_180002B52
0x1800028bc  mov     r9, [rbx+10h]
0x1800028c0  movzx   edx, byte ptr [r8+r9]
0x1800028c5  cmp     dl, 64h ; 'd'
0x1800028c8  jnz     loc_180002AA5
0x1800028ce  inc     r8d
0x1800028d1  mov     [rbx+4], r8d
0x1800028d5  cmp     ecx, r8d
0x1800028d8  jbe     loc_180002F95
0x1800028de  movzx   r9d, byte ptr [r8+r9]
0x1800028e3  test    r9b, r9b
0x1800028e6  jns     loc_180002B14
0x1800028ec  and     r9d, 7Fh
0x1800028f0  inc     r9d
0x1800028f3  mov     eax, [rbx+20h]
0x1800028f6  cmp     eax, 32h ; '2'
0x1800028f9  jnb     loc_180002FE1
0x1800028ff  mov     edx, [r14]
0x180002902  add     rax, rax
0x180002905  mov     ecx, [rsi]
0x180002907  mov     [rbx+rax*8+24h], r8d
0x18000290c  mov     eax, [rbx+20h]
0x18000290f  add     rax, rax
0x180002912  mov     [rbx+rax*8+28h], r9d
0x180002917  mov     eax, [rbx+20h]
0x18000291a  add     rax, rax
0x18000291d  mov     [rbx+rax*8+2Ch], ecx
0x180002921  mov     rcx, rbx; this
0x180002924  mov     eax, [rbx+20h]
0x180002927  add     rax, 3
0x18000292b  add     rax, rax
0x18000292e  mov     [rbx+rax*8], edx
0x180002931  mov     rdx, r14; unsigned int *
0x180002934  inc     dword ptr [rbx+20h]
0x180002937  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x18000293c  mov     r10d, eax
0x18000293f  test    eax, eax
0x180002941  jnz     loc_180002FC2
0x180002947  mov     eax, [rbx+4]
0x18000294a  mov     [rsi], eax
0x18000294c  mov     eax, [rbx+4]
0x18000294f  mov     r8d, [rbx]
0x180002952  cmp     eax, r8d
0x180002955  ja      loc_180002AB2
0x18000295b  test    r10d, r10d
0x18000295e  jnz     loc_180002B65
0x180002964  cmp     r8d, eax
0x180002967  jbe     loc_180002BF8
0x18000296d  mov     ecx, eax
0x18000296f  mov     rax, [rbx+10h]
0x180002973  movzx   edi, byte ptr [rcx+rax]
0x180002977  cmp     edi, 30h ; '0'
0x18000297a  jz      loc_180002C86
0x180002980  mov     eax, [rbx+4]
0x180002983  mov     r8d, [rbx]
0x180002986  mov     [rsp+58h+arg_8], r15d
0x18000298b  cmp     r8d, eax
0x18000298e  jbe     loc_180003016
0x180002994  inc     eax
0x180002996  lea     rdx, [rsp+58h+arg_8]; unsigned int *
0x18000299b  mov     rcx, rbx; this
0x18000299e  mov     [rbx+4], eax
0x1800029a1  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x1800029a6  mov     r10d, eax
0x1800029a9  test    eax, eax
0x1800029ab  jnz     loc_180002B89
0x1800029b1  mov     ecx, [rbx+4]
0x1800029b4  cmp     ecx, [rbx]
0x1800029b6  jnb     short loc_1800029C1
0x1800029b8  add     ecx, [rsp+58h+arg_8]
0x1800029bc  mov     [rbx+4], ecx
0x1800029bf  jmp     short loc_1800029C9
0x1800029c1  test    eax, eax
0x1800029c3  jnz     loc_180002B89
0x1800029c9  mov     r9d, [rbx+4]
0x1800029cd  mov     r8d, [rbx]
0x1800029d0  cmp     r8d, r9d
0x1800029d3  jbe     loc_180002D38
0x1800029d9  mov     rcx, [rbx+10h]
0x1800029dd  movzx   edx, byte ptr [r9+rcx]
0x1800029e2  cmp     dl, 30h ; '0'
0x1800029e5  jnz     loc_180002D85
0x1800029eb  inc     r9d
0x1800029ee  mov     [rbx+4], r9d
0x1800029f2  cmp     r8d, r9d
0x1800029f5  jbe     loc_180003092
0x1800029fb  movzx   r8d, byte ptr [r9+rcx]
0x180002a00  test    r8b, r8b
0x180002a03  jns     loc_180002B1F
0x180002a09  and     r8d, 7Fh
0x180002a0d  inc     r8d
0x180002a10  mov     eax, [rbx+20h]
0x180002a13  cmp     eax, 32h ; '2'
0x180002a16  jnb     loc_1800030DE
0x180002a1c  mov     edx, [r14]
0x180002a1f  add     rax, rax
0x180002a22  mov     ecx, [rsi]
0x180002a24  mov     [rbx+rax*8+24h], r9d
0x180002a29  mov     eax, [rbx+20h]
0x180002a2c  add     rax, rax
0x180002a2f  mov     [rbx+rax*8+28h], r8d
0x180002a34  mov     eax, [rbx+20h]
0x180002a37  add     rax, rax
0x180002a3a  mov     [rbx+rax*8+2Ch], ecx
0x180002a3e  mov     rcx, rbx; this
0x180002a41  mov     eax, [rbx+20h]
0x180002a44  add     rax, 3
0x180002a48  add     rax, rax
0x180002a4b  mov     [rbx+rax*8], edx
0x180002a4e  mov     rdx, r14; unsigned int *
0x180002a51  inc     dword ptr [rbx+20h]
0x180002a54  call    ?HrGetLength@CLdapBer@@QEAAKPEAK@Z; CLdapBer::HrGetLength(ulong *)
0x180002a59  mov     r10d, eax
0x180002a5c  test    eax, eax
0x180002a5e  jnz     loc_1800030BF
0x180002a64  mov     eax, [rbx+4]
0x180002a67  mov     [rsi], eax
0x180002a69  mov     eax, [rbx]
0x180002a6b  cmp     [rbx+4], eax
0x180002a6e  ja      short loc_180002ACE
0x180002a70  test    r10d, r10d
0x180002a73  jnz     short loc_180002AD4
0x180002a75  xor     eax, eax
0x180002a77  mov     rbx, [rsp+58h+arg_0]
0x180002a7c  add     rsp, 30h
0x180002a80  pop     r15
0x180002a82  pop     r14
0x180002a84  pop     rdi
0x180002a85  pop     rsi
0x180002a86  pop     rbp
0x180002a87  retn
0x180002a89  test    cs:g_ulTraceFlags, 2000h
0x180002a94  jnz     loc_180002DDD
0x180002a9a  mov     r10d, 80070057h
0x180002aa0  jmp     loc_180002C4F
0x180002aa5  cmp     cs:g_fTracingOn, r15d
0x180002aac  jnz     loc_180002F49
0x180002ab2  mov     r10d, 80070057h
0x180002ab8  jmp     loc_180002B65
0x180002abd  test    cs:g_ulTraceFlags, 2000h
0x180002ac8  jnz     loc_18000306A
0x180002ace  mov     r10d, 80070057h
0x180002ad4  cmp     cs:g_fTracingOn, r15d
0x180002adb  jz      loc_180002B72
0x180002ae1  cmp     cs:g_fProviderEnabled, r15d
0x180002ae8  jz      loc_180002B72
0x180002aee  test    cs:g_ulTraceFlags, 400000h
0x180002af9  jz      short loc_180002B72
0x180002afb  lea     rdx, aLdapfirstattr7; "ldapFirstAttr 7 connection 0x%x receive"...
0x180002b02  mov     r9d, r10d
0x180002b05  mov     r8, rbp
0x180002b08  mov     ecx, 400000h
0x180002b0d  call    LDAPClientPrint
0x180002b12  jmp     short loc_180002B72
0x180002b14  mov     r9d, 1
0x180002b1a  jmp     loc_1800028F3
0x180002b1f  mov     r8d, 1
0x180002b25  jmp     loc_180002A10
0x180002b2a  cmp     cs:g_fTracingOn, r15d
0x180002b31  jz      short loc_180002B72
0x180002b33  cmp     cs:g_fProviderEnabled, r15d
0x180002b3a  jz      short loc_180002B72
0x180002b3c  test    cs:g_ulTraceFlags, 400000h
0x180002b47  jz      short loc_180002B72
0x180002b49  lea     rdx, aLdapfirstattr2; "ldapFirstAttr 2 connection 0x%x receive"...
0x180002b50  jmp     short loc_180002B02
0x180002b52  cmp     cs:g_fTracingOn, r15d
0x180002b59  jnz     loc_180002F0F
0x180002b5f  mov     r10d, 10h
0x180002b65  cmp     cs:g_fTracingOn, r15d
0x180002b6c  jnz     loc_180002FEC
0x180002b72  mov     rbx, [rsp+58h+arg_0]
0x180002b77  mov     eax, 54h ; 'T'
0x180002b7c  add     rsp, 30h
0x180002b80  pop     r15
0x180002b82  pop     r14
0x180002b84  pop     rdi
0x180002b85  pop     rsi
0x180002b86  pop     rbp
0x180002b87  retn
0x180002b89  cmp     cs:g_fTracingOn, r15d
0x180002b90  jz      short loc_180002B72
0x180002b92  cmp     cs:g_fProviderEnabled, r15d
0x180002b99  jz      short loc_180002B72
0x180002b9b  test    cs:g_ulTraceFlags, 400000h
0x180002ba6  jz      short loc_180002B72
0x180002ba8  lea     rdx, aLdapfirstattr6; "ldapFirstAttr 6 connection 0x%x receive"...
0x180002baf  jmp     loc_180002B02
0x180002bb4  cmp     cs:g_fTracingOn, r15d
0x180002bbb  jz      loc_180002896
0x180002bc1  cmp     cs:g_fProviderEnabled, r15d
0x180002bc8  jz      loc_180002896
0x180002bce  test    cs:g_ulTraceFlags, 2000h
0x180002bd9  jz      loc_180002896
0x180002bdf  mov     r9d, eax
0x180002be2  lea     rdx, aHrpeektagRanOu; "HrPeekTag ran out of data, length 0x%x,"...
0x180002be9  mov     ecx, 2000h
0x180002bee  call    LDAPClientPrint
0x180002bf3  jmp     loc_180002896
0x180002bf8  cmp     cs:g_fTracingOn, r15d
0x180002bff  jz      loc_180002977
0x180002c05  cmp     cs:g_fProviderEnabled, r15d
0x180002c0c  jz      loc_180002977
0x180002c12  test    cs:g_ulTraceFlags, 2000h
0x180002c1d  jz      loc_180002977
0x180002c23  mov     r9d, eax
0x180002c26  lea     rdx, aHrpeektagRanOu; "HrPeekTag ran out of data, length 0x%x,"...
0x180002c2d  mov     ecx, 2000h
0x180002c32  call    LDAPClientPrint
0x180002c37  jmp     loc_180002977
0x180002c3c  cmp     cs:g_fTracingOn, r15d
0x180002c43  jnz     loc_180002DCE
0x180002c49  mov     r10d, 10h
  ... truncated ...
```
