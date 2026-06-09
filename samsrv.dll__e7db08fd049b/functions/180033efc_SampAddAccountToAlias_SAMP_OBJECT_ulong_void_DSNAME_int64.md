# SampAddAccountToAlias(_SAMP_OBJECT *,ulong,void *,_DSNAME *,__int64)

- ea: `0x180033efc`
- end: `0x1800341fc`
- name: `?SampAddAccountToAlias@@YAJPEAU_SAMP_OBJECT@@KPEAXPEAU_DSNAME@@_J@Z`
- size: `768`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, __int64, void *Src, struct _DSNAME *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180034520`

## callees

- `0x180021460`
- `0x180026cf0`
- `0x180027e24`
- `0x180033efc`
- `0x1800372ac`
- `0x18003aca0`
- `0x1800747e8`
- `0x180076a54`
- `0x180076abc`
- `0x180077420`
- `0x1800afd00`
- `0x1800bb788`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180034146`
- `ntdll!RtlCopySid` at `0x180034146`
- `ntdll!RtlLengthSid` at `0x1800340df`
- `ntdll!RtlLengthSid` at `0x1800340fe`
- `ntdll!RtlLengthSid` at `0x1800340df`
- `ntdll!RtlLengthSid` at `0x1800340fe`
- `ntdll!RtlEqualSid` at `0x1800340d2`
- `ntdll!RtlEqualSid` at `0x1800340d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034113`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034113`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003416e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800341b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003416e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800341b7`

## pseudocode

```c
__int64 __fastcall SampAddAccountToAlias(
        struct _SAMP_OBJECT *a1,
        __int64 a2,
        void *Src,
        struct _DSNAME *a4,
        __int64 a5)
{
  __int64 v5; // rbx
  unsigned int v8; // r13d
  int IsAccountBuiltIn; // eax
  NTSTATUS SidArrayAttribute; // ebx
  PUNICODE_STRING v12; // rcx
  __int64 v13; // rdx
  const unsigned __int16 *v14; // r12
  _BYTE *v15; // rsi
  NTSTATUS v16; // eax
  char v17; // al
  PSID v18; // r12
  unsigned int v19; // esi
  unsigned int v20; // r14d
  char *v21; // rbx
  unsigned int v22; // ebx
  unsigned __int8 *v23; // rax
  unsigned __int8 *v24; // rsi
  unsigned int v25; // r14d
  unsigned int v27[2]; // [rsp+48h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-18h] BYREF
  PSID Sid1; // [rsp+58h] [rbp-10h]

  v5 = a5;
  v27[0] = 0;
  v27[1] = 0;
  v8 = a2;
  Sid1 = 0;
  hMem = 0;
  if ( a5 && (int)SampSplitSid(Src) >= 0 )
  {
    IsAccountBuiltIn = SampIsAccountBuiltIn(0);
    SidArrayAttribute = IsAccountBuiltIn;
    if ( IsAccountBuiltIn < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (*(_BYTE *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 8) != 0 && HIBYTE(WPP_GLOBAL_Control[4].Length) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[3].Buffer,
          44,
          &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids,
          (unsigned int)IsAccountBuiltIn);
        v12 = WPP_GLOBAL_Control;
      }
      if ( (*(_DWORD *)(&v12[4].MaximumLength + 1) & 0x20000) != 0 )
      {
        v13 = 45;
LABEL_44:
        WPP_SF_Dd(
          v12[3].Buffer,
          v13,
          &WPP_799c13f926ef3db95a69a5604490dfde_Traceguids,
          (unsigned int)SidArrayAttribute,
          SidArrayAttribute);
        return (unsigned int)SidArrayAttribute;
      }
      return (unsigned int)SidArrayAttribute;
    }
    v5 = a5;
  }
  if ( (*((_BYTE *)a1 + 192) & 2) == 0 )
  {
    SidArrayAttribute = SampGetSidArrayAttribute(a1, v8, (__int64)&v27[1], (__int64)v27);
    if ( SidArrayAttribute < 0 )
      goto LABEL_40;
    v18 = Sid1;
    v19 = 0;
    v20 = v27[0];
    v21 = (char *)Sid1;
    while ( v19 < v20 )
    {
      if ( RtlEqualSid(v21, Src) )
      {
        SidArrayAttribute = -1073741485;
        goto LABEL_40;
      }
      v21 += RtlLengthSid(v21);
      ++v19;
    }
    v22 = (_DWORD)v21 - (_DWORD)v18;
    v27[1] = RtlLengthSid(Src);
    v27[0] = v22 + v27[1];
    v23 = (unsigned __int8 *)LocalAlloc(0x40u, v22 + v27[1]);
    v24 = v23;
    if ( !v23 )
    {
      SidArrayAttribute = -1073741670;
      goto LABEL_40;
    }
    memcpy_0(v23, v18, v22);
    v25 = v20 + 1;
    SidArrayAttribute = RtlCopySid(v27[1], &v24[v22], Src);
    if ( SidArrayAttribute >= 0 )
      SidArrayAttribute = SampSetSidArrayAttribute(a1, v8, v24, v27[0], v25);
    LocalFree(v24);
    v14 = 0;
LABEL_36:
    v17 = 0;
    if ( SidArrayAttribute < 0 )
      goto LABEL_40;
    goto LABEL_37;
  }
  if ( !*((_DWORD *)a4 + 13) || a4 == (struct _DSNAME *)-56LL )
  {
    if ( (int)SampExtLookupObjectBySidDs(
                *(struct _DSNAME **)(*((_QWORD *)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50)) + 176LL),
                Src,
                (struct _DSNAME **)&hMem,
                (unsigned int)a4) < 0 )
      v14 = 0;
    else
      v14 = (const unsigned __int16 *)((char *)hMem + 56);
  }
  else
  {
    v14 = (const unsigned __int16 *)((char *)a4 + 56);
  }
  v15 = (char *)a1 + 29;
  if ( (*((_BYTE *)a1 + 28) & 0x10) == 0 || (*v15 & 8) != 0 )
    v16 = SampExtAddMembershipAttributeDs(*((_QWORD *)a1 + 22), a2, v8, 3, a4, v5);
  else
    v16 = SampExtAddMembershipOperationToCacheDs(a1, v8, 3u, a4, v5);
  SidArrayAttribute = v16;
  if ( v16 != -1073741148 )
    goto LABEL_36;
  if ( (*v15 & 8) == 0 )
  {
    SidArrayAttribute = -1073741485;
    goto LABEL_36;
  }
  SidArrayAttribute = 0;
  v17 = 1;
LABEL_37:
  if ( SampSuccessAccountAuditingEnabled == 1 && !v17 )
    SampAuditGroupMemberChange(a1, 1u, v14, 0, Src, v8, a5);
LABEL_40:
  if ( hMem )
    LocalFree(hMem);
  v12 = WPP_GLOBAL_Control;
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    v13 = 46;
    goto LABEL_44;
  }
  return (unsigned int)SidArrayAttribute;
}

```

## disassembly

```asm
0x180033efc  push    rbp
0x180033efe  push    rbx
0x180033eff  push    rsi
0x180033f00  push    rdi
0x180033f01  push    r12
0x180033f03  push    r13
0x180033f05  push    r14
0x180033f07  push    r15
0x180033f09  mov     rbp, rsp
0x180033f0c  sub     rsp, 68h
0x180033f10  mov     rbx, [rbp+arg_20]
0x180033f14  mov     r14, r9
0x180033f17  mov     [rbp+var_20], 0
0x180033f1e  mov     r15, r8
0x180033f21  mov     [rbp+var_20+4], 0
0x180033f28  mov     r13d, edx
0x180033f2b  mov     [rbp+Sid1], 0
0x180033f33  mov     rdi, rcx
0x180033f36  mov     [rbp+hMem], 0
0x180033f3e  mov     dword ptr [rbp+var_28], 0
0x180033f45  test    rbx, rbx
0x180033f48  jz      short loc_180033FB7
0x180033f4a  lea     r8, [rbp+var_28]
0x180033f4e  xor     edx, edx
0x180033f50  mov     rcx, r15; Src
0x180033f53  call    SampSplitSid
0x180033f58  test    eax, eax
0x180033f5a  js      short loc_180033FB7
0x180033f5c  mov     ecx, dword ptr [rbp+var_28]
0x180033f5f  call    SampIsAccountBuiltIn
0x180033f64  mov     ebx, eax
0x180033f66  test    eax, eax
0x180033f68  jns     short loc_180033FB3
0x180033f6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f71  test    byte ptr [rcx+44h], 8
0x180033f75  jz      short loc_180033F9C
0x180033f77  cmp     byte ptr [rcx+41h], 4
0x180033f7b  jb      short loc_180033F9C
0x180033f7d  mov     rcx, [rcx+38h]
0x180033f81  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x180033f88  mov     edx, 2Ch ; ','
0x180033f8d  mov     r9d, eax
0x180033f90  call    WPP_SF_d
0x180033f95  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f9c  test    dword ptr [rcx+44h], 20000h
0x180033fa3  jz      loc_1800341E9
0x180033fa9  mov     edx, 2Dh ; '-'
0x180033fae  jmp     loc_1800341D2
0x180033fb3  mov     rbx, [rbp+arg_20]
0x180033fb7  test    byte ptr [rdi+0C0h], 2
0x180033fbe  mov     [rbp+var_28], 0
0x180033fc6  jz      loc_18003408C
0x180033fcc  cmp     dword ptr [r14+34h], 0
0x180033fd1  jz      short loc_180033FE1
0x180033fd3  lea     rax, [r14+38h]
0x180033fd7  test    rax, rax
0x180033fda  jz      short loc_180033FE1
0x180033fdc  mov     r12, rax
0x180033fdf  jmp     short loc_18003401E
0x180033fe1  mov     eax, [rdi+0C8h]
0x180033fe7  lea     r8, [rbp+hMem]; struct _DSNAME **
0x180033feb  imul    rcx, rax, 550h
0x180033ff2  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180033ff9  mov     rdx, r15; void *
0x180033ffc  mov     rcx, [rcx+rax]
0x180034000  mov     rcx, [rcx+0B0h]; struct _DSNAME *
0x180034007  call    ?SampExtLookupObjectBySidDs@@YAJPEAU_DSNAME@@PEAXPEAPEAU1@K@Z; SampExtLookupObjectBySidDs(_DSNAME *,void *,_DSNAME * *,ulong)
0x18003400c  test    eax, eax
0x18003400e  js      short loc_18003401A
0x180034010  mov     r12, [rbp+hMem]
0x180034014  add     r12, 38h ; '8'
0x180034018  jmp     short loc_18003401E
0x18003401a  mov     r12, [rbp+var_28]
0x18003401e  test    byte ptr [rdi+1Ch], 10h
0x180034022  lea     rsi, [rdi+1Dh]
0x180034026  jz      short loc_180034048
0x180034028  test    byte ptr [rsi], 8
0x18003402b  jnz     short loc_180034048
0x18003402d  mov     r9, r14; struct _DSNAME *
0x180034030  mov     [rsp+68h+var_48], rbx; __int64
0x180034035  mov     r8d, 3; unsigned int
0x18003403b  mov     edx, r13d; unsigned int
0x18003403e  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180034041  call    ?SampExtAddMembershipOperationToCacheDs@@YAJPEAU_SAMP_OBJECT@@KKPEAU_DSNAME@@_J@Z; SampExtAddMembershipOperationToCacheDs(_SAMP_OBJECT *,ulong,ulong,_DSNAME *,__int64)
0x180034046  jmp     short loc_180034067
0x180034048  mov     rcx, [rdi+0B0h]
0x18003404f  mov     r9d, 3
0x180034055  mov     qword ptr [rsp+68h+var_40], rbx
0x18003405a  mov     r8d, r13d
0x18003405d  mov     [rsp+68h+var_48], r14
0x180034062  call    ?SampExtAddMembershipAttributeDs@@YAJPEAU_DSNAME@@KKW4_SAMP_OBJECT_TYPE@@0_J@Z; SampExtAddMembershipAttributeDs(_DSNAME *,ulong,ulong,_SAMP_OBJECT_TYPE,_DSNAME *,__int64)
0x180034067  mov     ebx, eax
0x180034069  cmp     eax, 0C00002A4h
0x18003406e  jnz     loc_180034178
0x180034074  test    byte ptr [rsi], 8
0x180034077  jz      short loc_180034082
0x180034079  xor     ebx, ebx
0x18003407b  mov     al, 1
0x18003407d  jmp     loc_18003417E
0x180034082  mov     ebx, 0C0000153h
0x180034087  jmp     loc_180034178
0x18003408c  lea     rax, [rbp+var_20]
0x180034090  xor     r8d, r8d
0x180034093  mov     qword ptr [rsp+68h+var_40], rax; __int64
0x180034098  lea     r9, [rbp+Sid1]
0x18003409c  lea     rax, [rbp+var_20+4]
0x1800340a0  mov     edx, r13d; unsigned int
0x1800340a3  mov     rcx, rdi; struct _SAMP_OBJECT *
0x1800340a6  mov     [rsp+68h+var_48], rax; __int64
0x1800340ab  call    SampGetSidArrayAttribute
0x1800340b0  mov     ebx, eax
0x1800340b2  test    eax, eax
0x1800340b4  js      loc_1800341AE
0x1800340ba  mov     r12, [rbp+Sid1]
0x1800340be  xor     esi, esi
0x1800340c0  mov     r14d, [rbp+var_20]
0x1800340c4  mov     rbx, r12
0x1800340c7  cmp     esi, r14d
0x1800340ca  jnb     short loc_1800340F8
0x1800340cc  mov     rdx, r15; Sid2
0x1800340cf  mov     rcx, rbx; Sid1
0x1800340d2  call    cs:__imp_RtlEqualSid
0x1800340d8  test    al, al
0x1800340da  jnz     short loc_1800340EE
0x1800340dc  mov     rcx, rbx; Sid
0x1800340df  call    cs:__imp_RtlLengthSid
0x1800340e5  mov     eax, eax
0x1800340e7  add     rbx, rax
0x1800340ea  inc     esi
0x1800340ec  jmp     short loc_1800340C7
0x1800340ee  mov     ebx, 0C0000153h
0x1800340f3  jmp     loc_1800341AE
0x1800340f8  mov     rcx, r15; Sid
0x1800340fb  sub     ebx, r12d
0x1800340fe  call    cs:__imp_RtlLengthSid
0x180034104  mov     [rbp+var_20+4], eax
0x180034107  mov     ecx, 40h ; '@'; uFlags
0x18003410c  add     eax, ebx
0x18003410e  mov     edx, eax; uBytes
0x180034110  mov     [rbp+var_20], eax
0x180034113  call    cs:__imp_LocalAlloc
0x180034119  mov     rsi, rax
0x18003411c  test    rax, rax
0x18003411f  jnz     short loc_18003412B
0x180034121  mov     ebx, 0C000009Ah
0x180034126  jmp     loc_1800341AE
0x18003412b  mov     r8, rbx; Size
0x18003412e  mov     rdx, r12; Src
0x180034131  mov     rcx, rsi; void *
0x180034134  call    memcpy_0
0x180034139  mov     ecx, [rbp+var_20+4]; DestinationSidLength
0x18003413c  lea     rdx, [rbx+rsi]; DestinationSid
0x180034140  mov     r8, r15; SourceSid
0x180034143  inc     r14d
0x180034146  call    cs:__imp_RtlCopySid
0x18003414c  mov     ebx, eax
0x18003414e  test    eax, eax
0x180034150  js      short loc_18003416B
0x180034152  mov     r9d, [rbp+var_20]; unsigned int
0x180034156  mov     r8, rsi; unsigned __int8 *
0x180034159  mov     edx, r13d; unsigned int
0x18003415c  mov     dword ptr [rsp+68h+var_48], r14d; unsigned int
0x180034161  mov     rcx, rdi; struct _SAMP_OBJECT *
0x180034164  call    ?SampSetSidArrayAttribute@@YAJPEAU_SAMP_OBJECT@@KPEAXKK@Z; SampSetSidArrayAttribute(_SAMP_OBJECT *,ulong,void *,ulong,ulong)
0x180034169  mov     ebx, eax
0x18003416b  mov     rcx, rsi; hMem
0x18003416e  call    cs:__imp_LocalFree
0x180034174  mov     r12, [rbp+var_28]
0x180034178  xor     al, al
0x18003417a  test    ebx, ebx
0x18003417c  js      short loc_1800341AE
0x18003417e  cmp     cs:?SampSuccessAccountAuditingEnabled@@3EA, 1; uchar SampSuccessAccountAuditingEnabled
0x180034185  jnz     short loc_1800341AE
0x180034187  test    al, al
0x180034189  jnz     short loc_1800341AE
0x18003418b  mov     rax, [rbp+arg_20]
0x18003418f  xor     r9d, r9d; unsigned int *
0x180034192  mov     [rsp+68h+var_38], rax; __int64
0x180034197  mov     r8, r12; unsigned __int16 *
0x18003419a  mov     [rsp+68h+var_40], r13d; unsigned int
0x18003419f  mov     dl, 1; unsigned __int8
0x1800341a1  mov     rcx, rdi; struct _SAMP_OBJECT *
0x1800341a4  mov     [rsp+68h+var_48], r15; void *
0x1800341a9  call    ?SampAuditGroupMemberChange@@YAXPEAU_SAMP_OBJECT@@EPEBGPEAKPEAXK_J@Z; SampAuditGroupMemberChange(_SAMP_OBJECT *,uchar,ushort const *,ulong *,void *,ulong,__int64)
0x1800341ae  mov     rcx, [rbp+hMem]; hMem
0x1800341b2  test    rcx, rcx
0x1800341b5  jz      short loc_1800341BD
0x1800341b7  call    cs:__imp_LocalFree
0x1800341bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800341c4  test    dword ptr [rcx+44h], 20000h
0x1800341cb  jz      short loc_1800341E9
0x1800341cd  mov     edx, 2Eh ; '.'
0x1800341d2  mov     rcx, [rcx+38h]
0x1800341d6  lea     r8, WPP_799c13f926ef3db95a69a5604490dfde_Traceguids
0x1800341dd  mov     r9d, ebx
0x1800341e0  mov     dword ptr [rsp+68h+var_48], ebx
0x1800341e4  call    WPP_SF_Dd
0x1800341e9  mov     eax, ebx
0x1800341eb  add     rsp, 68h
0x1800341ef  pop     r15
0x1800341f1  pop     r14
0x1800341f3  pop     r13
0x1800341f5  pop     r12
0x1800341f7  pop     rdi
0x1800341f8  pop     rsi
0x1800341f9  pop     rbx
0x1800341fa  pop     rbp
0x1800341fb  retn
```
