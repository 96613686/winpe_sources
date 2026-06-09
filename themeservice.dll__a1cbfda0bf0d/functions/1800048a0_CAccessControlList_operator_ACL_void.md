# CAccessControlList::operator _ACL *(void)

- ea: `0x1800048a0`
- end: `0x18000496e`
- name: `??BCAccessControlList@@QEAAPEAU_ACL@@XZ`
- size: `206`
- prototype: `struct _ACL *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000461c`
- `0x180004848`

## callees

- `0x1800048a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180004914`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180004914`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004950`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180004950`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800048f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800048f7`

## pseudocode

```c
struct _ACL *__fastcall CAccessControlList::operator _ACL *(__int64 a1)
{
  struct _ACL *v1; // rbx
  unsigned int v3; // r10d
  int v4; // edx
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  DWORD v8; // esi
  struct _ACL *v9; // rax
  unsigned int v10; // esi
  __int64 v11; // r9
  __int64 v12; // r9

  v1 = *(struct _ACL **)(a1 + 24);
  if ( !v1 )
  {
    v3 = *(_DWORD *)(a1 + 8);
    v4 = 0;
    v5 = v3 - 1;
    if ( (int)v5 >= 0 )
    {
      v6 = *(_QWORD *)(a1 + 16);
      do
      {
        if ( v6 )
        {
          if ( (unsigned int)v5 < v3 )
          {
            v7 = *(_QWORD *)(v6 + 8 * v5);
            if ( v7 )
              v4 += *(unsigned __int16 *)(v7 + 2);
          }
        }
        v5 = (unsigned int)(v5 - 1);
      }
      while ( (int)v5 >= 0 );
    }
    v8 = v4 + 8;
    v9 = (struct _ACL *)LocalAlloc(0, (unsigned int)(v4 + 8));
    *(_QWORD *)(a1 + 24) = v9;
    v1 = v9;
    if ( v9 )
    {
      InitializeAcl(v9, v8, 2u);
      v10 = *(_DWORD *)(a1 + 8);
      while ( (--v10 & 0x80000000) == 0 )
      {
        v11 = *(_QWORD *)(a1 + 16);
        if ( v11 )
        {
          if ( v10 < *(_DWORD *)(a1 + 8) )
          {
            v12 = *(_QWORD *)(v11 + 8LL * v10);
            if ( v12 )
              AddAccessAllowedAceEx(v1, 2u, *(unsigned __int8 *)(v12 + 1), *(_DWORD *)(v12 + 4), (PSID)(v12 + 8));
          }
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800048a0  mov     [rsp+arg_0], rbx
0x1800048a5  mov     [rsp+arg_8], rsi
0x1800048aa  push    rdi
0x1800048ab  sub     rsp, 30h
0x1800048af  mov     rbx, [rcx+18h]
0x1800048b3  mov     rdi, rcx
0x1800048b6  test    rbx, rbx
0x1800048b9  jnz     loc_18000495B
0x1800048bf  mov     r10d, [rcx+8]
0x1800048c3  xor     edx, edx
0x1800048c5  lea     ecx, [r10-1]
0x1800048c9  test    ecx, ecx
0x1800048cb  js      short loc_1800048F0
0x1800048cd  mov     r9, [rdi+10h]
0x1800048d1  test    r9, r9
0x1800048d4  jz      short loc_1800048EB
0x1800048d6  cmp     ecx, r10d
0x1800048d9  jnb     short loc_1800048EB
0x1800048db  mov     r8, [r9+rcx*8]
0x1800048df  test    r8, r8
0x1800048e2  jz      short loc_1800048EB
0x1800048e4  movzx   eax, word ptr [r8+2]
0x1800048e9  add     edx, eax
0x1800048eb  sub     ecx, 1
0x1800048ee  jns     short loc_1800048D1
0x1800048f0  lea     esi, [rdx+8]
0x1800048f3  xor     ecx, ecx; uFlags
0x1800048f5  mov     edx, esi; uBytes
0x1800048f7  call    cs:__imp_LocalAlloc
0x1800048fd  mov     [rdi+18h], rax
0x180004901  mov     rbx, rax
0x180004904  test    rax, rax
0x180004907  jz      short loc_18000495B
0x180004909  mov     r8d, 2; dwAclRevision
0x18000490f  mov     edx, esi; nAclLength
0x180004911  mov     rcx, rax; pAcl
0x180004914  call    cs:__imp_InitializeAcl
0x18000491a  mov     esi, [rdi+8]
0x18000491d  jmp     short loc_180004956
0x18000491f  mov     r9, [rdi+10h]
0x180004923  test    r9, r9
0x180004926  jz      short loc_180004956
0x180004928  cmp     esi, [rdi+8]
0x18000492b  jnb     short loc_180004956
0x18000492d  mov     r9, [r9+rsi*8]
0x180004931  test    r9, r9
0x180004934  jz      short loc_180004956
0x180004936  movzx   r8d, byte ptr [r9+1]; AceFlags
0x18000493b  lea     rax, [r9+8]
0x18000493f  mov     r9d, [r9+4]; AccessMask
0x180004943  mov     edx, 2; dwAceRevision
0x180004948  mov     rcx, rbx; pAcl
0x18000494b  mov     [rsp+38h+pSid], rax; pSid
0x180004950  call    cs:__imp_AddAccessAllowedAceEx
0x180004956  sub     esi, 1
0x180004959  jns     short loc_18000491F
0x18000495b  mov     rsi, [rsp+38h+arg_8]
0x180004960  mov     rax, rbx
0x180004963  mov     rbx, [rsp+38h+arg_0]
0x180004968  add     rsp, 30h
0x18000496c  pop     rdi
0x18000496d  retn
```
