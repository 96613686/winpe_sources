# SampRemoveAccountFromAlias(_SAMP_OBJECT *,ulong,void *,_DSNAME *,__int64)

- ea: `0x1800348f4`
- end: `0x180034b65`
- name: `?SampRemoveAccountFromAlias@@YAJPEAU_SAMP_OBJECT@@KPEAXPEAU_DSNAME@@_J@Z`
- size: `625`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, unsigned int, void *, struct _DSNAME *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180034b6c`
- `0x18003526c`

## callees

- `0x180026cf0`
- `0x180027e24`
- `0x1800348f4`
- `0x18003aca0`
- `0x1800747e8`
- `0x180076abc`
- `0x180077420`
- `0x1800775fc`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18003493a`
- `ntdll!RtlLengthSid` at `0x180034a5d`
- `ntdll!RtlLengthSid` at `0x18003493a`
- `ntdll!RtlLengthSid` at `0x180034a5d`
- `ntdll!RtlEqualSid` at `0x180034a6f`
- `ntdll!RtlEqualSid` at `0x180034a6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034ac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034ac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034b19`

## pseudocode

```c
__int64 __fastcall SampRemoveAccountFromAlias(
        struct _SAMP_OBJECT *a1,
        unsigned int a2,
        void *a3,
        struct _DSNAME *a4,
        __int64 a5)
{
  PSID v7; // r12
  unsigned int v8; // r14d
  ULONG v9; // eax
  unsigned int v10; // r9d
  const unsigned __int16 *v11; // r15
  _BYTE *v12; // rdi
  int v13; // eax
  int SidArrayAttribute; // ebx
  char v15; // al
  unsigned __int8 *v16; // r15
  unsigned int v17; // r14d
  unsigned int v18; // r13d
  _BYTE *v19; // rdi
  __int64 v20; // r12
  bool v21; // zf
  unsigned __int8 *v22; // rbx
  unsigned int v24; // [rsp+40h] [rbp-20h] BYREF
  ULONG v25; // [rsp+44h] [rbp-1Ch]
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  PSID Sid; // [rsp+50h] [rbp-10h]
  const unsigned __int16 *v28; // [rsp+58h] [rbp-8h]
  __int64 v29; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v30; // [rsp+A8h] [rbp+48h]
  PSID Sid2; // [rsp+B0h] [rbp+50h]

  Sid2 = a3;
  v30 = a2;
  LODWORD(v29) = 0;
  v24 = 0;
  Sid = 0;
  v7 = a3;
  v28 = 0;
  v8 = a2;
  hMem = 0;
  v9 = RtlLengthSid(a3);
  v21 = (*((_BYTE *)a1 + 192) & 2) == 0;
  v25 = v9;
  if ( v21 )
  {
    SidArrayAttribute = SampGetSidArrayAttribute(a1, v8, (__int64)&v24, (__int64)&v29);
    if ( SidArrayAttribute < 0 )
      goto LABEL_33;
    v16 = (unsigned __int8 *)Sid;
    v17 = 0;
    v18 = v29;
    v19 = Sid;
    while ( 1 )
    {
      v20 = v24;
      v21 = v17 == v18;
      if ( v17 >= v18 )
        break;
      v22 = &v19[RtlLengthSid(v19)];
      if ( RtlEqualSid(v19, Sid2) )
      {
        while ( v22 < &v16[v20] )
          *v19++ = *v22++;
        v21 = v17 == v18;
        break;
      }
      v19 = v22;
      ++v17;
    }
    v8 = v30;
    if ( v21 )
      SidArrayAttribute = -1073741486;
    else
      SidArrayAttribute = SampSetSidArrayAttribute(a1, v30, v16, (unsigned int)v20 - v25, v18 - 1);
    LocalFree(v16);
    v11 = v28;
    v7 = Sid2;
LABEL_29:
    v15 = 0;
    if ( SidArrayAttribute < 0 )
      goto LABEL_33;
    goto LABEL_30;
  }
  if ( !*((_DWORD *)a4 + 13) || a4 == (struct _DSNAME *)-56LL )
  {
    if ( (int)SampExtLookupObjectBySidDs(
                *(struct _DSNAME **)(*((_QWORD *)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50)) + 176LL),
                v7,
                (struct _DSNAME **)&hMem,
                v10) < 0 )
      v11 = 0;
    else
      v11 = (const unsigned __int16 *)((char *)hMem + 56);
  }
  else
  {
    v11 = (const unsigned __int16 *)((char *)a4 + 56);
  }
  v12 = (char *)a1 + 29;
  if ( (*((_BYTE *)a1 + 28) & 0x10) == 0 || (*v12 & 8) != 0 )
    v13 = SampExtRemoveMembershipAttributeDs(*((_QWORD *)a1 + 22), v8, 3, a4, a5);
  else
    v13 = SampExtAddMembershipOperationToCacheDs(a1, v8, 4u, a4, a5);
  SidArrayAttribute = v13;
  if ( v13 != -1073741151 )
    goto LABEL_29;
  if ( (*v12 & 8) == 0 )
  {
    SidArrayAttribute = -1073741486;
    goto LABEL_29;
  }
  SidArrayAttribute = 0;
  v15 = 1;
LABEL_30:
  if ( SampSuccessAccountAuditingEnabled == 1 && !v15 )
    SampAuditGroupMemberChange(a1, 0, v11, 0, v7, v8, a5);
LABEL_33:
  if ( hMem )
    LocalFree(hMem);
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control[3].Buffer,
      47,
      &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids,
      (unsigned int)SidArrayAttribute,
      SidArrayAttribute);
  return (unsigned int)SidArrayAttribute;
}

```

## disassembly

```asm
0x1800348f4  mov     [rsp-38h+arg_18], rbx
0x1800348f9  mov     [rsp-38h+Sid2], r8
0x1800348fe  mov     [rsp-38h+arg_8], edx
0x180034902  push    rbp
0x180034903  push    rsi
0x180034904  push    rdi
0x180034905  push    r12
0x180034907  push    r13
0x180034909  push    r14
0x18003490b  push    r15
0x18003490d  mov     rbp, rsp
0x180034910  sub     rsp, 60h
0x180034914  xor     r13d, r13d
0x180034917  mov     rsi, rcx
0x18003491a  mov     rcx, r8; Sid
0x18003491d  mov     dword ptr [rbp+arg_0], r13d
0x180034921  mov     dword ptr [rbp+var_20], r13d
0x180034925  mov     rbx, r9
0x180034928  mov     [rbp+Sid], r13
0x18003492c  mov     r12, r8
0x18003492f  mov     [rbp+var_8], r13
0x180034933  mov     r14d, edx
0x180034936  mov     [rbp+hMem], r13
0x18003493a  call    cs:__imp_RtlLengthSid
0x180034940  test    byte ptr [rsi+0C0h], 2
0x180034947  mov     dword ptr [rbp+var_20+4], eax
0x18003494a  jz      loc_180034A15
0x180034950  cmp     [rbx+34h], r13d
0x180034954  jz      short loc_180034964
0x180034956  lea     rax, [rbx+38h]
0x18003495a  test    rax, rax
0x18003495d  jz      short loc_180034964
0x18003495f  mov     r15, rax
0x180034962  jmp     short loc_1800349A0
0x180034964  mov     eax, [rsi+0C8h]
0x18003496a  lea     r8, [rbp+hMem]; struct _DSNAME **
0x18003496e  imul    rcx, rax, 550h
0x180034975  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18003497c  mov     rdx, r12; void *
0x18003497f  mov     rcx, [rcx+rax]
0x180034983  mov     rcx, [rcx+0B0h]; struct _DSNAME *
0x18003498a  call    ?SampExtLookupObjectBySidDs@@YAJPEAU_DSNAME@@PEAXPEAPEAU1@K@Z; SampExtLookupObjectBySidDs(_DSNAME *,void *,_DSNAME * *,ulong)
0x18003498f  test    eax, eax
0x180034991  js      short loc_18003499D
0x180034993  mov     r15, [rbp+hMem]
0x180034997  add     r15, 38h ; '8'
0x18003499b  jmp     short loc_1800349A0
0x18003499d  mov     r15, r13
0x1800349a0  test    byte ptr [rsi+1Ch], 10h
0x1800349a4  lea     rdi, [rsi+1Dh]
0x1800349a8  jz      short loc_1800349CE
0x1800349aa  test    byte ptr [rdi], 8
0x1800349ad  jnz     short loc_1800349CE
0x1800349af  mov     rax, [rbp+arg_20]
0x1800349b3  mov     r9, rbx; struct _DSNAME *
0x1800349b6  mov     r8d, 4; unsigned int
0x1800349bc  mov     [rsp+60h+var_40], rax; __int64
0x1800349c1  mov     edx, r14d; unsigned int
0x1800349c4  mov     rcx, rsi; struct _SAMP_OBJECT *
0x1800349c7  call    ?SampExtAddMembershipOperationToCacheDs@@YAJPEAU_SAMP_OBJECT@@KKPEAU_DSNAME@@_J@Z; SampExtAddMembershipOperationToCacheDs(_SAMP_OBJECT *,ulong,ulong,_DSNAME *,__int64)
0x1800349cc  jmp     short loc_1800349EF
0x1800349ce  mov     rax, [rbp+arg_20]
0x1800349d2  mov     r9, rbx
0x1800349d5  mov     rcx, [rsi+0B0h]
0x1800349dc  mov     r8d, 3
0x1800349e2  mov     edx, r14d
0x1800349e5  mov     [rsp+60h+var_40], rax
0x1800349ea  call    ?SampExtRemoveMembershipAttributeDs@@YAJPEAU_DSNAME@@KW4_SAMP_OBJECT_TYPE@@0_J@Z; SampExtRemoveMembershipAttributeDs(_DSNAME *,ulong,_SAMP_OBJECT_TYPE,_DSNAME *,__int64)
0x1800349ef  mov     ebx, eax
0x1800349f1  cmp     eax, 0C00002A1h
0x1800349f6  jnz     loc_180034AD9
0x1800349fc  test    byte ptr [rdi], 8
0x1800349ff  jz      short loc_180034A0B
0x180034a01  mov     ebx, r13d
0x180034a04  mov     al, 1
0x180034a06  jmp     loc_180034AE0
0x180034a0b  mov     ebx, 0C0000152h
0x180034a10  jmp     loc_180034AD9
0x180034a15  lea     rax, [rbp+arg_0]
0x180034a19  mov     r8b, 1
0x180034a1c  mov     qword ptr [rsp+60h+var_38], rax; __int64
0x180034a21  lea     r9, [rbp+Sid]
0x180034a25  lea     rax, [rbp+var_20]
0x180034a29  mov     edx, r14d; unsigned int
0x180034a2c  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180034a2f  mov     [rsp+60h+var_40], rax; __int64
0x180034a34  call    SampGetSidArrayAttribute
0x180034a39  mov     ebx, eax
0x180034a3b  test    eax, eax
0x180034a3d  js      loc_180034B10
0x180034a43  mov     r15, [rbp+Sid]
0x180034a47  mov     r14d, r13d
0x180034a4a  mov     r13d, dword ptr [rbp+arg_0]
0x180034a4e  mov     rdi, r15
0x180034a51  mov     r12d, dword ptr [rbp+var_20]
0x180034a55  cmp     r14d, r13d
0x180034a58  jnb     short loc_180034A99
0x180034a5a  mov     rcx, rdi; Sid
0x180034a5d  call    cs:__imp_RtlLengthSid
0x180034a63  mov     rdx, [rbp+Sid2]; Sid2
0x180034a67  mov     rcx, rdi; Sid1
0x180034a6a  mov     ebx, eax
0x180034a6c  add     rbx, rdi
0x180034a6f  call    cs:__imp_RtlEqualSid
0x180034a75  test    al, al
0x180034a77  jnz     short loc_180034A81
0x180034a79  mov     rdi, rbx
0x180034a7c  inc     r14d
0x180034a7f  jmp     short loc_180034A51
0x180034a81  lea     rcx, [r15+r12]
0x180034a85  jmp     short loc_180034A91
0x180034a87  mov     al, [rbx]
0x180034a89  mov     [rdi], al
0x180034a8b  inc     rdi
0x180034a8e  inc     rbx
0x180034a91  cmp     rbx, rcx
0x180034a94  jb      short loc_180034A87
0x180034a96  cmp     r14d, r13d
0x180034a99  mov     r14d, [rbp+arg_8]
0x180034a9d  jnz     short loc_180034AA6
0x180034a9f  mov     ebx, 0C0000152h
0x180034aa4  jmp     short loc_180034AC5
0x180034aa6  sub     r12d, dword ptr [rbp+var_20+4]
0x180034aaa  lea     eax, [r13-1]
0x180034aae  mov     r9d, r12d; unsigned int
0x180034ab1  mov     dword ptr [rsp+60h+var_40], eax; unsigned int
0x180034ab5  mov     r8, r15; unsigned __int8 *
0x180034ab8  mov     edx, r14d; unsigned int
0x180034abb  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180034abe  call    ?SampSetSidArrayAttribute@@YAJPEAU_SAMP_OBJECT@@KPEAXKK@Z; SampSetSidArrayAttribute(_SAMP_OBJECT *,ulong,void *,ulong,ulong)
0x180034ac3  mov     ebx, eax
0x180034ac5  mov     rcx, r15; hMem
0x180034ac8  call    cs:__imp_LocalFree
0x180034ace  mov     r15, [rbp+var_8]
0x180034ad2  xor     r13d, r13d
0x180034ad5  mov     r12, [rbp+Sid2]
0x180034ad9  mov     al, r13b
0x180034adc  test    ebx, ebx
0x180034ade  js      short loc_180034B10
0x180034ae0  cmp     cs:?SampSuccessAccountAuditingEnabled@@3EA, 1; uchar SampSuccessAccountAuditingEnabled
0x180034ae7  jnz     short loc_180034B10
0x180034ae9  test    al, al
0x180034aeb  jnz     short loc_180034B10
0x180034aed  mov     rax, [rbp+arg_20]
0x180034af1  xor     r9d, r9d; unsigned int *
0x180034af4  mov     [rsp+60h+var_30], rax; __int64
0x180034af9  mov     r8, r15; unsigned __int16 *
0x180034afc  mov     [rsp+60h+var_38], r14d; unsigned int
0x180034b01  xor     edx, edx; unsigned __int8
0x180034b03  mov     rcx, rsi; struct _SAMP_OBJECT *
0x180034b06  mov     [rsp+60h+var_40], r12; void *
0x180034b0b  call    ?SampAuditGroupMemberChange@@YAXPEAU_SAMP_OBJECT@@EPEBGPEAKPEAXK_J@Z; SampAuditGroupMemberChange(_SAMP_OBJECT *,uchar,ushort const *,ulong *,void *,ulong,__int64)
0x180034b10  mov     rcx, [rbp+hMem]; hMem
0x180034b14  test    rcx, rcx
0x180034b17  jz      short loc_180034B1F
0x180034b19  call    cs:__imp_LocalFree
0x180034b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034b26  test    dword ptr [rcx+44h], 20000h
0x180034b2d  jz      short loc_180034B4B
0x180034b2f  mov     rcx, [rcx+38h]
0x180034b33  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x180034b3a  mov     edx, 2Fh ; '/'
0x180034b3f  mov     dword ptr [rsp+60h+var_40], ebx
0x180034b43  mov     r9d, ebx
0x180034b46  call    WPP_SF_Dd
0x180034b4b  mov     eax, ebx
0x180034b4d  mov     rbx, [rsp+60h+arg_18]
0x180034b55  add     rsp, 60h
0x180034b59  pop     r15
0x180034b5b  pop     r14
0x180034b5d  pop     r13
0x180034b5f  pop     r12
0x180034b61  pop     rdi
0x180034b62  pop     rsi
0x180034b63  pop     rbp
0x180034b64  retn
```
