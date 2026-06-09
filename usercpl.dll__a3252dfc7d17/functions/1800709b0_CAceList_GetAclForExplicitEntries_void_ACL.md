# CAceList::GetAclForExplicitEntries(void *,_ACL * *)

- ea: `0x1800709b0`
- end: `0x180070c1a`
- name: `?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(CAceList *__hidden this, void *, struct _ACL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180070c20`

## callees

- `0x1800709b0`
- `0x180070dac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180070ae7`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180070b55`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180070ae7`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x180070b55`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180070aa1`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180070aa1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070a84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180070a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070c02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070c02`

## pseudocode

```c
__int64 __fastcall CAceList::GetAclForExplicitEntries(CAceList *this, void *a2, struct _ACL **a3)
{
  int *v3; // rdx
  int v4; // r9d
  int v7; // edi
  int v8; // r11d
  __int64 i; // rcx
  __int64 v10; // r8
  int *v11; // rdx
  int v12; // r8d
  __int64 j; // rcx
  __int64 v14; // r10
  DWORD v15; // esi
  int *v16; // rdx
  __int64 k; // rcx
  __int64 v18; // r8
  struct _ACL *v19; // rax
  struct _ACL *v20; // rbp
  __int64 m; // rsi
  int *v22; // rcx
  __int64 v23; // r9
  __int64 v24; // rsi
  int *v25; // rcx
  __int64 v26; // r9
  __int64 n; // rsi
  int *v28; // rcx
  struct CAce *v29; // rdx
  __int64 v30; // rsi
  int *v31; // rcx
  struct CAce *v32; // rdx

  v3 = *(int **)this;
  v4 = 8;
  v7 = -2147024882;
  v8 = 8;
  if ( *(_QWORD *)this )
  {
    for ( i = 0; i < *v3; ++i )
    {
      if ( i >= 0 )
      {
        v10 = *(_QWORD *)(*((_QWORD *)v3 + 1) + 8 * i);
        if ( v10 )
          v8 += *(unsigned __int16 *)(v10 + 2);
      }
    }
  }
  v11 = (int *)*((_QWORD *)this + 1);
  v12 = 8;
  if ( v11 )
  {
    for ( j = 0; j < *v11; ++j )
    {
      if ( j >= 0 )
      {
        v14 = *(_QWORD *)(*((_QWORD *)v11 + 1) + 8 * j);
        if ( v14 )
          v12 += *(unsigned __int16 *)(v14 + 2);
      }
    }
  }
  v15 = v8 + v12 + 8;
  if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
  {
    v16 = (int *)*((_QWORD *)this + 2);
    if ( v16 )
    {
      for ( k = 0; k < *v16; ++k )
      {
        if ( k >= 0 )
        {
          v18 = *(_QWORD *)(*((_QWORD *)v16 + 1) + 8 * k);
          if ( v18 )
            v4 += *(unsigned __int16 *)(v18 + 2);
        }
      }
    }
    v15 += v4;
  }
  v19 = (struct _ACL *)LocalAlloc(0x40u, v15);
  v20 = v19;
  if ( !v19 )
    goto LABEL_67;
  InitializeAcl(v19, v15, 2u);
  for ( m = 0; ; ++m )
  {
    v22 = *(int **)this;
    v7 = 0;
    if ( !*(_QWORD *)this || m >= *v22 )
      break;
    if ( m < 0 )
      v23 = 0;
    else
      v23 = *(_QWORD *)(*((_QWORD *)v22 + 1) + 8 * m);
    if ( !AddAccessDeniedAceEx(v20, 2u, *(unsigned __int8 *)(v23 + 1), *(_DWORD *)(v23 + 4), *(PSID *)(v23 + 8)) )
    {
      v7 = -2147024882;
      break;
    }
  }
  if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
  {
    v24 = 0;
    if ( v7 >= 0 )
    {
      while ( 1 )
      {
        v25 = (int *)*((_QWORD *)this + 2);
        if ( !v25 || v24 >= *v25 )
          break;
        if ( v24 < 0 )
          v26 = 0;
        else
          v26 = *(_QWORD *)(*((_QWORD *)v25 + 1) + 8 * v24);
        if ( (*(_BYTE *)(v26 + 28) & 1) == 0
          && !AddAccessDeniedAceEx(v20, 2u, *(_BYTE *)(v26 + 1) & 0xEF, *(_DWORD *)(v26 + 4), *(PSID *)(v26 + 8)) )
        {
          v7 = -2147024882;
          goto LABEL_54;
        }
        ++v24;
      }
    }
  }
  for ( n = 0; v7 >= 0; v7 = CAceList::_AddAllowedAceToAcl(this, v29, 0, v20) )
  {
    v28 = (int *)*((_QWORD *)this + 1);
    if ( !v28 || n >= *v28 )
      break;
    v29 = n < 0 ? 0LL : *(struct CAce **)(*((_QWORD *)v28 + 1) + 8 * n);
    ++n;
  }
LABEL_54:
  if ( *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
  {
LABEL_65:
    if ( v7 >= 0 )
      goto LABEL_67;
LABEL_66:
    LocalFree(v20);
    v20 = 0;
    goto LABEL_67;
  }
  v30 = 0;
  if ( v7 < 0 )
    goto LABEL_66;
  while ( 1 )
  {
    v31 = (int *)*((_QWORD *)this + 2);
    if ( !v31 )
      break;
    if ( v30 < *v31 )
    {
      if ( v30 < 0 )
        v32 = 0;
      else
        v32 = *(struct CAce **)(*((_QWORD *)v31 + 1) + 8 * v30);
      if ( (*((_BYTE *)v32 + 28) & 1) != 0 )
        v7 = CAceList::_AddAllowedAceToAcl(this, v32, 1, v20);
      ++v30;
      if ( v7 >= 0 )
        continue;
    }
    goto LABEL_65;
  }
LABEL_67:
  *a3 = v20;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800709b0  push    rbx
0x1800709b2  push    rbp
0x1800709b3  push    rsi
0x1800709b4  push    rdi
0x1800709b5  push    r14
0x1800709b7  sub     rsp, 30h
0x1800709bb  mov     rdx, [rcx]
0x1800709be  mov     r9d, 8
0x1800709c4  mov     r14, r8
0x1800709c7  mov     rbx, rcx
0x1800709ca  mov     edi, 8007000Eh
0x1800709cf  mov     r11d, r9d
0x1800709d2  test    rdx, rdx
0x1800709d5  jz      short loc_180070A00
0x1800709d7  xor     ecx, ecx
0x1800709d9  movsxd  rax, dword ptr [rdx]
0x1800709dc  cmp     rcx, rax
0x1800709df  jge     short loc_180070A00
0x1800709e1  test    rcx, rcx
0x1800709e4  js      short loc_1800709FB
0x1800709e6  mov     rax, [rdx+8]
0x1800709ea  mov     r8, [rax+rcx*8]
0x1800709ee  test    r8, r8
0x1800709f1  jz      short loc_1800709FB
0x1800709f3  movzx   eax, word ptr [r8+2]
0x1800709f8  add     r11d, eax
0x1800709fb  inc     rcx
0x1800709fe  jmp     short loc_1800709D9
0x180070a00  mov     rdx, [rbx+8]
0x180070a04  mov     r8d, r9d
0x180070a07  test    rdx, rdx
0x180070a0a  jz      short loc_180070A35
0x180070a0c  xor     ecx, ecx
0x180070a0e  movsxd  rax, dword ptr [rdx]
0x180070a11  cmp     rcx, rax
0x180070a14  jge     short loc_180070A35
0x180070a16  test    rcx, rcx
0x180070a19  js      short loc_180070A30
0x180070a1b  mov     rax, [rdx+8]
0x180070a1f  mov     r10, [rax+rcx*8]
0x180070a23  test    r10, r10
0x180070a26  jz      short loc_180070A30
0x180070a28  movzx   eax, word ptr [r10+2]
0x180070a2d  add     r8d, eax
0x180070a30  inc     rcx
0x180070a33  jmp     short loc_180070A0E
0x180070a35  lea     esi, [r8+8]
0x180070a39  add     esi, r11d
0x180070a3c  cmp     dword ptr [rbx+18h], 0
0x180070a40  jnz     short loc_180070A7D
0x180070a42  cmp     dword ptr [rbx+1Ch], 0
0x180070a46  jnz     short loc_180070A7D
0x180070a48  mov     rdx, [rbx+10h]
0x180070a4c  test    rdx, rdx
0x180070a4f  jz      short loc_180070A7A
0x180070a51  xor     ecx, ecx
0x180070a53  movsxd  rax, dword ptr [rdx]
0x180070a56  cmp     rcx, rax
0x180070a59  jge     short loc_180070A7A
0x180070a5b  test    rcx, rcx
0x180070a5e  js      short loc_180070A75
0x180070a60  mov     rax, [rdx+8]
0x180070a64  mov     r8, [rax+rcx*8]
0x180070a68  test    r8, r8
0x180070a6b  jz      short loc_180070A75
0x180070a6d  movzx   eax, word ptr [r8+2]
0x180070a72  add     r9d, eax
0x180070a75  inc     rcx
0x180070a78  jmp     short loc_180070A53
0x180070a7a  add     esi, r9d
0x180070a7d  mov     edx, esi; uBytes
0x180070a7f  mov     ecx, 40h ; '@'; uFlags
0x180070a84  call    cs:__imp_LocalAlloc
0x180070a8a  mov     rbp, rax
0x180070a8d  test    rax, rax
0x180070a90  jz      loc_180070C0A
0x180070a96  mov     r8d, 2; dwAclRevision
0x180070a9c  mov     edx, esi; nAclLength
0x180070a9e  mov     rcx, rax; pAcl
0x180070aa1  call    cs:__imp_InitializeAcl
0x180070aa7  xor     esi, esi
0x180070aa9  mov     rcx, [rbx]
0x180070aac  xor     edi, edi
0x180070aae  test    rcx, rcx
0x180070ab1  jz      short loc_180070AFB
0x180070ab3  movsxd  rax, dword ptr [rcx]
0x180070ab6  cmp     rsi, rax
0x180070ab9  jge     short loc_180070AFB
0x180070abb  test    rsi, rsi
0x180070abe  js      short loc_180070ACA
0x180070ac0  mov     rax, [rcx+8]
0x180070ac4  mov     r9, [rax+rsi*8]
0x180070ac8  jmp     short loc_180070ACD
0x180070aca  xor     r9d, r9d
0x180070acd  mov     rax, [r9+8]
0x180070ad1  mov     edx, 2; dwAceRevision
0x180070ad6  movzx   r8d, byte ptr [r9+1]; AceFlags
0x180070adb  mov     rcx, rbp; pAcl
0x180070ade  mov     r9d, [r9+4]; AccessMask
0x180070ae2  mov     [rsp+58h+pSid], rax; pSid
0x180070ae7  call    cs:__imp_AddAccessDeniedAceEx
0x180070aed  test    eax, eax
0x180070aef  jz      short loc_180070AF6
0x180070af1  inc     rsi
0x180070af4  jmp     short loc_180070AA9
0x180070af6  mov     edi, 8007000Eh
0x180070afb  cmp     dword ptr [rbx+18h], 0
0x180070aff  jnz     short loc_180070B6B
0x180070b01  cmp     dword ptr [rbx+1Ch], 0
0x180070b05  jnz     short loc_180070B6B
0x180070b07  xor     esi, esi
0x180070b09  test    edi, edi
0x180070b0b  js      short loc_180070B6B
0x180070b0d  mov     rcx, [rbx+10h]
0x180070b11  test    rcx, rcx
0x180070b14  jz      short loc_180070B6B
0x180070b16  movsxd  rax, dword ptr [rcx]
0x180070b19  cmp     rsi, rax
0x180070b1c  jge     short loc_180070B6B
0x180070b1e  test    rsi, rsi
0x180070b21  js      short loc_180070B2D
0x180070b23  mov     rax, [rcx+8]
0x180070b27  mov     r9, [rax+rsi*8]
0x180070b2b  jmp     short loc_180070B30
0x180070b2d  xor     r9d, r9d
0x180070b30  test    byte ptr [r9+1Ch], 1
0x180070b35  jnz     short loc_180070B5F
0x180070b37  movzx   r8d, byte ptr [r9+1]
0x180070b3c  mov     edx, 2; dwAceRevision
0x180070b41  mov     rax, [r9+8]
0x180070b45  and     r8d, 0FFFFFFEFh; AceFlags
0x180070b49  mov     r9d, [r9+4]; AccessMask
0x180070b4d  mov     rcx, rbp; pAcl
0x180070b50  mov     [rsp+58h+pSid], rax; pSid
0x180070b55  call    cs:__imp_AddAccessDeniedAceEx
0x180070b5b  test    eax, eax
0x180070b5d  jz      short loc_180070B64
0x180070b5f  inc     rsi
0x180070b62  jmp     short loc_180070B0D
0x180070b64  mov     edi, 8007000Eh
0x180070b69  jmp     short loc_180070BAA
0x180070b6b  xor     esi, esi
0x180070b6d  test    edi, edi
0x180070b6f  js      short loc_180070BAA
0x180070b71  mov     rcx, [rbx+8]
0x180070b75  test    rcx, rcx
0x180070b78  jz      short loc_180070BAA
0x180070b7a  movsxd  rax, dword ptr [rcx]
0x180070b7d  cmp     rsi, rax
0x180070b80  jge     short loc_180070BAA
0x180070b82  test    rsi, rsi
0x180070b85  js      short loc_180070B91
0x180070b87  mov     rax, [rcx+8]
0x180070b8b  mov     rdx, [rax+rsi*8]
0x180070b8f  jmp     short loc_180070B93
0x180070b91  xor     edx, edx; struct CAce *
0x180070b93  mov     r9, rbp; struct _ACL *
0x180070b96  xor     r8d, r8d; bool
0x180070b99  mov     rcx, rbx; this
0x180070b9c  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x180070ba1  inc     rsi
0x180070ba4  mov     edi, eax
0x180070ba6  test    eax, eax
0x180070ba8  jns     short loc_180070B71
0x180070baa  cmp     dword ptr [rbx+18h], 0
0x180070bae  jnz     short loc_180070BFB
0x180070bb0  cmp     dword ptr [rbx+1Ch], 0
0x180070bb4  jnz     short loc_180070BFB
0x180070bb6  xor     esi, esi
0x180070bb8  test    edi, edi
0x180070bba  js      short loc_180070BFF
0x180070bbc  mov     rcx, [rbx+10h]
0x180070bc0  test    rcx, rcx
0x180070bc3  jz      short loc_180070C0A
0x180070bc5  movsxd  rax, dword ptr [rcx]
0x180070bc8  cmp     rsi, rax
0x180070bcb  jge     short loc_180070BFB
0x180070bcd  test    rsi, rsi
0x180070bd0  js      short loc_180070BDC
0x180070bd2  mov     rax, [rcx+8]
0x180070bd6  mov     rdx, [rax+rsi*8]
0x180070bda  jmp     short loc_180070BDE
0x180070bdc  xor     edx, edx; struct CAce *
0x180070bde  test    byte ptr [rdx+1Ch], 1
0x180070be2  jz      short loc_180070BF4
0x180070be4  mov     r9, rbp; struct _ACL *
0x180070be7  mov     r8b, 1; bool
0x180070bea  mov     rcx, rbx; this
0x180070bed  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x180070bf2  mov     edi, eax
0x180070bf4  inc     rsi
0x180070bf7  test    edi, edi
0x180070bf9  jns     short loc_180070BBC
0x180070bfb  test    edi, edi
0x180070bfd  jns     short loc_180070C0A
0x180070bff  mov     rcx, rbp; hMem
0x180070c02  call    cs:__imp_LocalFree
0x180070c08  xor     ebp, ebp
0x180070c0a  mov     [r14], rbp
0x180070c0d  mov     eax, edi
0x180070c0f  add     rsp, 30h
0x180070c13  pop     r14
0x180070c15  pop     rdi
0x180070c16  pop     rsi
0x180070c17  pop     rbp
0x180070c18  pop     rbx
0x180070c19  retn
```
