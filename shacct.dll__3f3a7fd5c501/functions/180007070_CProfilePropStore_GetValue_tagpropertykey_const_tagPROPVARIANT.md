# CProfilePropStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180007070`
- end: `0x1800072ec`
- name: `?GetValue@CProfilePropStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `636`
- prototype: `__int64 __fastcall(struct IPropertyStore *this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180007070`
- `0x18000b410`
- `0x18000b960`
- `0x18000cb6c`
- `0x180010a3c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000725e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000725e`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180007203`
- `PROPSYS!InitPropVariantFromCLSID` at `0x180007203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007187`

## pseudocode

```c
__int64 __fastcall CProfilePropStore::GetValue(
        struct IPropertyStore *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3)
{
  unsigned int v5; // esi
  unsigned int i; // r8d
  __int64 v7; // rax
  unsigned int j; // r8d
  __int64 v9; // rax
  DWORD pid; // eax
  __int64 v11; // rcx
  struct IPropertyStoreVtbl *lpVtbl; // rbx
  __int64 v13; // rax
  __int64 v15; // rbp
  void *v16; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  BYTE *v20; // rbx
  PSID v21; // rcx
  __int64 v22; // rcx
  bool v23; // al
  __int64 v24; // rax
  PSID pSid; // [rsp+40h] [rbp+18h] BYREF

  v5 = -2147024809;
  if ( a3 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 2 )
      {
        for ( j = 0; j < 3; ++j )
        {
          if ( a2->pid == dword_18001FA60[9 * j] )
          {
            v9 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)((char *)&xmmword_18001FA50 + 36 * (int)j);
            if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)((char *)&xmmword_18001FA50 + 36 * (int)j) )
              v9 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)((char *)&xmmword_18001FA50 + 36 * (int)j + 8);
            if ( !v9 )
              goto LABEL_16;
          }
        }
        return v5;
      }
      if ( a2->pid == dword_18001FA10[9 * i] )
      {
        v7 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)((char *)&xmmword_18001FA00 + 36 * (int)i);
        if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)((char *)&xmmword_18001FA00 + 36 * (int)i) )
          v7 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)((char *)&xmmword_18001FA00 + 36 * (int)i + 8);
        if ( !v7 )
          break;
      }
    }
LABEL_16:
    *(_OWORD *)a3 = 0;
    a3[2] = 0;
    pid = a2->pid;
    if ( pid == 500 )
    {
      v11 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_PROFILE_Path;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_PROFILE_Path )
        v11 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_PROFILE_Path + 1);
      if ( !v11 )
      {
        lpVtbl = this[2].lpVtbl;
        if ( lpVtbl )
        {
          v13 = -1;
          while ( *((_WORD *)&lpVtbl->QueryInterface + ++v13) != 0 )
            ;
          v15 = 2 * v13 + 2;
          v16 = CoTaskMemAlloc(v15);
          a3[1] = v16;
          if ( v16 )
          {
            v5 = 0;
            memcpy_s(v16, v15, lpVtbl, v15);
            *(_WORD *)a3 = 31;
            return v5;
          }
          v5 = -2147024882;
        }
        *(_OWORD *)a3 = 0;
        a3[2] = 0;
        return v5;
      }
    }
    if ( pid == 501 )
    {
      v18 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_PROFILE_GUID;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_PROFILE_GUID )
        v18 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_PROFILE_GUID + 1);
      if ( !v18 )
        return (unsigned int)InitPropVariantFromCLSID((const IID *const)&this[3], a3);
    }
    if ( pid != 18 )
      goto LABEL_42;
    v19 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_SecurityID;
    if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_SecurityID )
      v19 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_SecurityID + 1);
    if ( v19 )
    {
LABEL_42:
      if ( pid != 2 )
        goto LABEL_47;
      v22 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_AllowedLogon;
      if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_AllowedLogon )
        v22 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_AllowedLogon + 1);
      if ( v22 )
      {
LABEL_47:
        if ( pid != 3 )
          return v5;
        v24 = *(_QWORD *)&a2->fmtid.Data1 - PKEY_SAM_DontEnumerateForLogon;
        if ( *(_QWORD *)&a2->fmtid.Data1 == (_QWORD)PKEY_SAM_DontEnumerateForLogon )
          v24 = *(_QWORD *)a2->fmtid.Data4 - *((_QWORD *)&PKEY_SAM_DontEnumerateForLogon + 1);
        if ( v24 )
          return v5;
        v23 = DontEnumerateForLogon(this);
      }
      else
      {
        v23 = IsUserAllowedLogon(this);
      }
      *(_WORD *)a3 = 11;
      v5 = 0;
      *((_WORD *)a3 + 4) = !v23 - 1;
      return v5;
    }
    pSid = 0;
    v5 = DupSID(this[5].lpVtbl, &pSid);
    if ( (v5 & 0x80000000) == 0 )
    {
      v20 = (BYTE *)pSid;
      v21 = pSid;
      *(_WORD *)a3 = 65;
      *((_DWORD *)a3 + 2) = GetLengthSid(v21);
      a3[2] = v20;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180007070  mov     [rsp+arg_18], rsi
0x180007075  push    rdi
0x180007076  sub     rsp, 20h
0x18000707a  mov     rdi, r8
0x18000707d  mov     r9, rcx
0x180007080  mov     esi, 80070057h
0x180007085  test    r8, r8
0x180007088  jz      loc_1800072DF
0x18000708e  xor     r8d, r8d
0x180007091  lea     r10, __ImageBase
0x180007098  cmp     r8d, 2
0x18000709c  jnb     short loc_1800070D5
0x18000709e  movsxd  rax, r8d
0x1800070a1  lea     rcx, [rax+rax*8]
0x1800070a5  mov     eax, rva dword_18001FA10[r10+rcx*4]
0x1800070ad  cmp     [rdx+10h], eax
0x1800070b0  jnz     short loc_1800070D0
0x1800070b2  mov     rax, [rdx]
0x1800070b5  sub     rax, qword ptr rva xmmword_18001FA00[r10+rcx*4]
0x1800070bd  jnz     short loc_1800070CB
0x1800070bf  mov     rax, [rdx+8]
0x1800070c3  sub     rax, qword ptr (rva xmmword_18001FA00+8)[r10+rcx*4]
0x1800070cb  test    rax, rax
0x1800070ce  jz      short loc_180007119
0x1800070d0  inc     r8d
0x1800070d3  jmp     short loc_180007098
0x1800070d5  xor     r8d, r8d
0x1800070d8  cmp     r8d, 3
0x1800070dc  jnb     loc_1800072DF
0x1800070e2  movsxd  rax, r8d
0x1800070e5  lea     rcx, [rax+rax*8]
0x1800070e9  mov     eax, rva dword_18001FA60[r10+rcx*4]
0x1800070f1  cmp     [rdx+10h], eax
0x1800070f4  jnz     short loc_180007114
0x1800070f6  mov     rax, [rdx]
0x1800070f9  sub     rax, qword ptr rva xmmword_18001FA50[r10+rcx*4]
0x180007101  jnz     short loc_18000710F
0x180007103  mov     rax, [rdx+8]
0x180007107  sub     rax, qword ptr (rva xmmword_18001FA50+8)[r10+rcx*4]
0x18000710f  test    rax, rax
0x180007112  jz      short loc_180007119
0x180007114  inc     r8d
0x180007117  jmp     short loc_1800070D8
0x180007119  xor     eax, eax
0x18000711b  mov     [rsp+28h+arg_0], rbx
0x180007120  xorps   xmm0, xmm0
0x180007123  movups  xmmword ptr [rdi], xmm0
0x180007126  mov     [rdi+10h], rax
0x18000712a  mov     eax, [rdx+10h]
0x18000712d  cmp     eax, cs:dword_18001A8E8
0x180007133  jnz     loc_1800071D8
0x180007139  mov     rcx, [rdx]
0x18000713c  sub     rcx, qword ptr cs:PKEY_PROFILE_Path
0x180007143  jnz     short loc_180007150
0x180007145  mov     rcx, [rdx+8]
0x180007149  sub     rcx, qword ptr cs:PKEY_PROFILE_Path+8
0x180007150  test    rcx, rcx
0x180007153  jnz     loc_1800071D8
0x180007159  mov     rbx, [r9+10h]
0x18000715d  mov     [rsp+28h+arg_8], rbp
0x180007162  test    rbx, rbx
0x180007165  jz      short loc_1800071B5
0x180007167  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000716e  xchg    ax, ax
0x180007170  cmp     word ptr [rbx+rax*2+2], 0
0x180007176  lea     rax, [rax+1]
0x18000717a  jnz     short loc_180007170
0x18000717c  lea     rbp, ds:2[rax*2]
0x180007184  mov     rcx, rbp; cb
0x180007187  call    cs:__imp_CoTaskMemAlloc
0x18000718d  mov     [rdi+8], rax
0x180007191  test    rax, rax
0x180007194  jz      short loc_1800071B0
0x180007196  xor     esi, esi
0x180007198  mov     r9, rbp; SourceSize
0x18000719b  mov     r8, rbx; Source
0x18000719e  mov     rdx, rbp; DestinationSize
0x1800071a1  mov     rcx, rax; Destination
0x1800071a4  call    memcpy_s
0x1800071a9  mov     word ptr [rdi], 1Fh
0x1800071ae  jmp     short loc_1800071C1
0x1800071b0  mov     esi, 8007000Eh
0x1800071b5  xorps   xmm0, xmm0
0x1800071b8  xor     eax, eax
0x1800071ba  movups  xmmword ptr [rdi], xmm0
0x1800071bd  mov     [rdi+10h], rax
0x1800071c1  mov     rbp, [rsp+28h+arg_8]
0x1800071c6  mov     eax, esi
0x1800071c8  mov     rbx, [rsp+28h+arg_0]
0x1800071cd  mov     rsi, [rsp+28h+arg_18]
0x1800071d2  add     rsp, 20h
0x1800071d6  pop     rdi
0x1800071d7  retn
0x1800071d8  cmp     eax, cs:dword_18001A8D0
0x1800071de  jnz     short loc_180007210
0x1800071e0  mov     rcx, [rdx]
0x1800071e3  sub     rcx, qword ptr cs:PKEY_PROFILE_GUID
0x1800071ea  jnz     short loc_1800071F7
0x1800071ec  mov     rcx, [rdx+8]
0x1800071f0  sub     rcx, qword ptr cs:PKEY_PROFILE_GUID+8
0x1800071f7  test    rcx, rcx
0x1800071fa  jnz     short loc_180007210
0x1800071fc  lea     rcx, [r9+18h]; clsid
0x180007200  mov     rdx, rdi; ppropvar
0x180007203  call    cs:__imp_InitPropVariantFromCLSID
0x180007209  mov     esi, eax
0x18000720b  jmp     loc_1800072DA
0x180007210  cmp     eax, cs:dword_18001AC60
0x180007216  jnz     short loc_18000726D
0x180007218  mov     rcx, [rdx]
0x18000721b  sub     rcx, qword ptr cs:PKEY_SAM_SecurityID
0x180007222  jnz     short loc_18000722F
0x180007224  mov     rcx, [rdx+8]
0x180007228  sub     rcx, qword ptr cs:PKEY_SAM_SecurityID+8
0x18000722f  test    rcx, rcx
0x180007232  jnz     short loc_18000726D
0x180007234  mov     [rsp+28h+pSid], rcx
0x180007239  lea     rdx, [rsp+28h+pSid]; void **
0x18000723e  mov     rcx, [r9+28h]; pSourceSid
0x180007242  call    ?DupSID@@YAJPEAXPEAPEAX@Z; DupSID(void *,void * *)
0x180007247  mov     esi, eax
0x180007249  test    eax, eax
0x18000724b  js      loc_1800072DA
0x180007251  mov     rbx, [rsp+28h+pSid]
0x180007256  mov     rcx, rbx; pSid
0x180007259  mov     word ptr [rdi], 41h ; 'A'
0x18000725e  call    cs:__imp_GetLengthSid
0x180007264  mov     [rdi+8], eax
0x180007267  mov     [rdi+10h], rbx
0x18000726b  jmp     short loc_1800072DA
0x18000726d  cmp     eax, cs:dword_18001A930
0x180007273  jnz     short loc_18000729B
0x180007275  mov     rcx, [rdx]
0x180007278  sub     rcx, qword ptr cs:PKEY_SAM_AllowedLogon
0x18000727f  jnz     short loc_18000728C
0x180007281  mov     rcx, [rdx+8]
0x180007285  sub     rcx, qword ptr cs:PKEY_SAM_AllowedLogon+8
0x18000728c  test    rcx, rcx
0x18000728f  jnz     short loc_18000729B
0x180007291  mov     rcx, r9; struct IPropertyStore *
0x180007294  call    ?IsUserAllowedLogon@@YA_NPEAUIPropertyStore@@@Z; IsUserAllowedLogon(IPropertyStore *)
0x180007299  jmp     short loc_1800072C7
0x18000729b  cmp     eax, cs:dword_18001AA50
0x1800072a1  jnz     short loc_1800072DA
0x1800072a3  mov     rax, [rdx]
0x1800072a6  sub     rax, qword ptr cs:PKEY_SAM_DontEnumerateForLogon
0x1800072ad  jnz     short loc_1800072BA
0x1800072af  mov     rax, [rdx+8]
0x1800072b3  sub     rax, qword ptr cs:PKEY_SAM_DontEnumerateForLogon+8
0x1800072ba  test    rax, rax
0x1800072bd  jnz     short loc_1800072DA
0x1800072bf  mov     rcx, r9; struct IPropertyStore *
0x1800072c2  call    ?DontEnumerateForLogon@@YA_NPEAUIPropertyStore@@@Z; DontEnumerateForLogon(IPropertyStore *)
0x1800072c7  xor     al, 1
0x1800072c9  mov     word ptr [rdi], 0Bh
0x1800072ce  movzx   eax, al
0x1800072d1  dec     ax
0x1800072d4  xor     esi, esi
0x1800072d6  mov     [rdi+8], ax
0x1800072da  mov     rbx, [rsp+28h+arg_0]
0x1800072df  mov     eax, esi
0x1800072e1  mov     rsi, [rsp+28h+arg_18]
0x1800072e6  add     rsp, 20h
0x1800072ea  pop     rdi
0x1800072eb  retn
```
