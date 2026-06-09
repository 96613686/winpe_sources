# CAceList::GetAclForExplicitEntries(void *,_ACL * *)

- ea: `0x1800dbbf8`
- end: `0x1800dbdf9`
- name: `?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(CAceList *__hidden this, void *, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800dbe00`

## callees

- `0x1800dbbf8`
- `0x1800dc1d4`
- `0x1800dc418`
- `0x1800e18a0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbdd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbdd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dbc46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dbc46`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800dbcb0`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800dbd23`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800dbcb0`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800dbd23`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800dbc69`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800dbc69`

## pseudocode

```c
__int64 __fastcall CAceList::GetAclForExplicitEntries(CAceList *this, void *a2, struct _ACL **a3)
{
  int v5; // edi
  int RequiredExplictAclSize; // ebp
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  DWORD v11; // ebp
  struct _ACL *v12; // rax
  struct _ACL *v13; // rbx
  INT_PTR i; // rbp
  struct _DPA *v15; // rcx
  unsigned __int8 *Ptr; // rax
  INT_PTR v17; // rbp
  struct _DPA *v18; // rcx
  PVOID v19; // rax
  INT_PTR j; // rbp
  struct _DPA *v21; // rcx
  struct CAce *v22; // rax
  INT_PTR v23; // rbp
  struct _DPA *v24; // rcx
  struct CAce *v25; // rax

  v5 = -2147024882;
  RequiredExplictAclSize = CAceList::_GetRequiredExplictAclSize(this, a2, this);
  v11 = CAceList::_GetRequiredExplictAclSize(v8, v7, (char *)this + 8) + RequiredExplictAclSize + 8;
  if ( !*((_QWORD *)this + 3) )
    v11 += CAceList::_GetRequiredExplictAclSize(v10, v9, (char *)this + 16);
  v12 = (struct _ACL *)LocalAlloc(0x40u, v11);
  v13 = v12;
  if ( !v12 )
    goto LABEL_33;
  InitializeAcl(v12, v11, 2u);
  for ( i = 0; ; ++i )
  {
    v15 = *(struct _DPA **)this;
    v5 = 0;
    if ( !*(_QWORD *)this || i >= *(int *)v15 )
      break;
    Ptr = (unsigned __int8 *)g_pfn_DPA_GetPtr(v15, i);
    if ( !AddAccessDeniedAceEx(v13, 2u, Ptr[1], *((_DWORD *)Ptr + 1), *((PSID *)Ptr + 1)) )
    {
      v5 = -2147024882;
      break;
    }
  }
  if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
  {
    v17 = 0;
    if ( v5 >= 0 )
    {
      while ( 1 )
      {
        v18 = (struct _DPA *)*((_QWORD *)this + 2);
        if ( !v18 || v17 >= *(int *)v18 )
          break;
        v19 = g_pfn_DPA_GetPtr(v18, v17);
        if ( (*((_BYTE *)v19 + 28) & 1) == 0
          && !AddAccessDeniedAceEx(v13, 2u, *((_BYTE *)v19 + 1) & 0xEF, *((_DWORD *)v19 + 1), *((PSID *)v19 + 1)) )
        {
          v5 = -2147024882;
          goto LABEL_23;
        }
        ++v17;
      }
    }
  }
  for ( j = 0; v5 >= 0; v5 = CAceList::_AddAllowedAceToAcl(this, v22, 0, v13) )
  {
    v21 = (struct _DPA *)*((_QWORD *)this + 1);
    if ( !v21 )
      break;
    if ( j >= *(int *)v21 )
      break;
    v22 = (struct CAce *)g_pfn_DPA_GetPtr(v21, j++);
  }
LABEL_23:
  if ( *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
  {
LABEL_31:
    if ( v5 >= 0 )
      goto LABEL_33;
LABEL_32:
    LocalFree(v13);
    v13 = 0;
    goto LABEL_33;
  }
  v23 = 0;
  if ( v5 < 0 )
    goto LABEL_32;
  while ( 1 )
  {
    v24 = (struct _DPA *)*((_QWORD *)this + 2);
    if ( !v24 )
      break;
    if ( v23 < *(int *)v24 )
    {
      v25 = (struct CAce *)g_pfn_DPA_GetPtr(v24, v23);
      if ( (*((_BYTE *)v25 + 28) & 1) != 0 )
        v5 = CAceList::_AddAllowedAceToAcl(this, v25, 1, v13);
      ++v23;
      if ( v5 >= 0 )
        continue;
    }
    goto LABEL_31;
  }
LABEL_33:
  *a3 = v13;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800dbbf8  push    rbx
0x1800dbbfa  push    rbp
0x1800dbbfb  push    rsi
0x1800dbbfc  push    rdi
0x1800dbbfd  push    r14
0x1800dbbff  push    r15
0x1800dbc01  sub     rsp, 38h
0x1800dbc05  mov     r15, r8
0x1800dbc08  mov     rsi, rcx
0x1800dbc0b  mov     r8, rcx
0x1800dbc0e  mov     edi, 8007000Eh
0x1800dbc13  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x1800dbc18  lea     r8, [rsi+8]
0x1800dbc1c  mov     ebp, eax
0x1800dbc1e  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x1800dbc23  add     ebp, 8
0x1800dbc26  add     ebp, eax
0x1800dbc28  cmp     dword ptr [rsi+18h], 0
0x1800dbc2c  jnz     short loc_1800DBC3F
0x1800dbc2e  cmp     dword ptr [rsi+1Ch], 0
0x1800dbc32  jnz     short loc_1800DBC3F
0x1800dbc34  lea     r8, [rsi+10h]
0x1800dbc38  call    ?_GetRequiredExplictAclSize@CAceList@@AEAAKPEAXAEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@@Z; CAceList::_GetRequiredExplictAclSize(void *,CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &)
0x1800dbc3d  add     ebp, eax
0x1800dbc3f  mov     edx, ebp; uBytes
0x1800dbc41  mov     ecx, 40h ; '@'; uFlags
0x1800dbc46  call    cs:__imp_LocalAlloc
0x1800dbc4d  nop     dword ptr [rax+rax+00h]
0x1800dbc52  mov     rbx, rax
0x1800dbc55  test    rax, rax
0x1800dbc58  jz      loc_1800DBDE6
0x1800dbc5e  mov     r8d, 2; dwAclRevision
0x1800dbc64  mov     edx, ebp; nAclLength
0x1800dbc66  mov     rcx, rax; pAcl
0x1800dbc69  call    cs:__imp_InitializeAcl
0x1800dbc70  nop     dword ptr [rax+rax+00h]
0x1800dbc75  xor     ebp, ebp
0x1800dbc77  mov     rcx, [rsi]; hdpa
0x1800dbc7a  xor     edi, edi
0x1800dbc7c  test    rcx, rcx
0x1800dbc7f  jz      short loc_1800DBCCA
0x1800dbc81  movsxd  rax, dword ptr [rcx]
0x1800dbc84  cmp     rbp, rax
0x1800dbc87  jge     short loc_1800DBCCA
0x1800dbc89  mov     rdx, rbp; i
0x1800dbc8c  call    cs:g_pfn_DPA_GetPtr
0x1800dbc93  nop     dword ptr [rax+rax+00h]
0x1800dbc98  lea     edx, [rdi+2]; dwAceRevision
0x1800dbc9b  mov     rcx, rbx; pAcl
0x1800dbc9e  mov     r9d, [rax+4]; AccessMask
0x1800dbca2  movzx   r8d, byte ptr [rax+1]; AceFlags
0x1800dbca7  mov     rax, [rax+8]
0x1800dbcab  mov     [rsp+68h+pSid], rax; pSid
0x1800dbcb0  call    cs:__imp_AddAccessDeniedAceEx
0x1800dbcb7  nop     dword ptr [rax+rax+00h]
0x1800dbcbc  test    eax, eax
0x1800dbcbe  jz      short loc_1800DBCC5
0x1800dbcc0  inc     rbp
0x1800dbcc3  jmp     short loc_1800DBC77
0x1800dbcc5  mov     edi, 8007000Eh
0x1800dbcca  cmp     dword ptr [rsi+18h], 0
0x1800dbcce  jnz     short loc_1800DBD3F
0x1800dbcd0  cmp     dword ptr [rsi+1Ch], 0
0x1800dbcd4  jnz     short loc_1800DBD3F
0x1800dbcd6  xor     ebp, ebp
0x1800dbcd8  test    edi, edi
0x1800dbcda  js      short loc_1800DBD3F
0x1800dbcdc  mov     rcx, [rsi+10h]; hdpa
0x1800dbce0  test    rcx, rcx
0x1800dbce3  jz      short loc_1800DBD3F
0x1800dbce5  movsxd  rax, dword ptr [rcx]
0x1800dbce8  cmp     rbp, rax
0x1800dbceb  jge     short loc_1800DBD3F
0x1800dbced  mov     rdx, rbp; i
0x1800dbcf0  call    cs:g_pfn_DPA_GetPtr
0x1800dbcf7  nop     dword ptr [rax+rax+00h]
0x1800dbcfc  mov     r9, rax
0x1800dbcff  test    byte ptr [rax+1Ch], 1
0x1800dbd03  jnz     short loc_1800DBD33
0x1800dbd05  movzx   r8d, byte ptr [rax+1]
0x1800dbd0a  mov     edx, 2; dwAceRevision
0x1800dbd0f  mov     rax, [rax+8]
0x1800dbd13  and     r8d, 0FFFFFFEFh; AceFlags
0x1800dbd17  mov     r9d, [r9+4]; AccessMask
0x1800dbd1b  mov     rcx, rbx; pAcl
0x1800dbd1e  mov     [rsp+68h+pSid], rax; pSid
0x1800dbd23  call    cs:__imp_AddAccessDeniedAceEx
0x1800dbd2a  nop     dword ptr [rax+rax+00h]
0x1800dbd2f  test    eax, eax
0x1800dbd31  jz      short loc_1800DBD38
0x1800dbd33  inc     rbp
0x1800dbd36  jmp     short loc_1800DBCDC
0x1800dbd38  mov     edi, 8007000Eh
0x1800dbd3d  jmp     short loc_1800DBD7F
0x1800dbd3f  xor     ebp, ebp
0x1800dbd41  test    edi, edi
0x1800dbd43  js      short loc_1800DBD7F
0x1800dbd45  mov     rcx, [rsi+8]; hdpa
0x1800dbd49  test    rcx, rcx
0x1800dbd4c  jz      short loc_1800DBD7F
0x1800dbd4e  movsxd  rax, dword ptr [rcx]
0x1800dbd51  cmp     rbp, rax
0x1800dbd54  jge     short loc_1800DBD7F
0x1800dbd56  mov     rdx, rbp; i
0x1800dbd59  call    cs:g_pfn_DPA_GetPtr
0x1800dbd60  nop     dword ptr [rax+rax+00h]
0x1800dbd65  mov     r9, rbx; struct _ACL *
0x1800dbd68  xor     r8d, r8d; bool
0x1800dbd6b  mov     rdx, rax; struct CAce *
0x1800dbd6e  mov     rcx, rsi; this
0x1800dbd71  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x1800dbd76  inc     rbp
0x1800dbd79  mov     edi, eax
0x1800dbd7b  test    eax, eax
0x1800dbd7d  jns     short loc_1800DBD45
0x1800dbd7f  cmp     dword ptr [rsi+18h], 0
0x1800dbd83  jnz     short loc_1800DBDD1
0x1800dbd85  cmp     dword ptr [rsi+1Ch], 0
0x1800dbd89  jnz     short loc_1800DBDD1
0x1800dbd8b  xor     ebp, ebp
0x1800dbd8d  test    edi, edi
0x1800dbd8f  js      short loc_1800DBDD5
0x1800dbd91  mov     rcx, [rsi+10h]; hdpa
0x1800dbd95  test    rcx, rcx
0x1800dbd98  jz      short loc_1800DBDE6
0x1800dbd9a  movsxd  rax, dword ptr [rcx]
0x1800dbd9d  cmp     rbp, rax
0x1800dbda0  jge     short loc_1800DBDD1
0x1800dbda2  mov     rdx, rbp; i
0x1800dbda5  call    cs:g_pfn_DPA_GetPtr
0x1800dbdac  nop     dword ptr [rax+rax+00h]
0x1800dbdb1  test    byte ptr [rax+1Ch], 1
0x1800dbdb5  jz      short loc_1800DBDCA
0x1800dbdb7  mov     r9, rbx; struct _ACL *
0x1800dbdba  mov     r8b, 1; bool
0x1800dbdbd  mov     rdx, rax; struct CAce *
0x1800dbdc0  mov     rcx, rsi; this
0x1800dbdc3  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x1800dbdc8  mov     edi, eax
0x1800dbdca  inc     rbp
0x1800dbdcd  test    edi, edi
0x1800dbdcf  jns     short loc_1800DBD91
0x1800dbdd1  test    edi, edi
0x1800dbdd3  jns     short loc_1800DBDE6
0x1800dbdd5  mov     rcx, rbx; hMem
0x1800dbdd8  call    cs:__imp_LocalFree
0x1800dbddf  nop     dword ptr [rax+rax+00h]
0x1800dbde4  xor     ebx, ebx
0x1800dbde6  mov     [r15], rbx
0x1800dbde9  mov     eax, edi
0x1800dbdeb  add     rsp, 38h
0x1800dbdef  pop     r15
0x1800dbdf1  pop     r14
0x1800dbdf3  pop     rdi
0x1800dbdf4  pop     rsi
0x1800dbdf5  pop     rbp
0x1800dbdf6  pop     rbx
0x1800dbdf7  retn
```
