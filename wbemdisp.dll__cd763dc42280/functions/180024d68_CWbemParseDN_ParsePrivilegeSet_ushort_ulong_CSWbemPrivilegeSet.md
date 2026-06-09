# CWbemParseDN::ParsePrivilegeSet(ushort *,ulong *,CSWbemPrivilegeSet &)

- ea: `0x180024d68`
- end: `0x180024fec`
- name: `?ParsePrivilegeSet@CWbemParseDN@@CA_NPEAGPEAKAEAVCSWbemPrivilegeSet@@@Z`
- size: `644`
- prototype: `bool __fastcall(unsigned __int16 *, unsigned int *, struct CSWbemPrivilegeSet *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000fe0c`

## callees

- `0x18001bed4`
- `0x180024d68`
- `0x180036010`

## import_xrefs

- `msvcrt!iswspace` at `0x180024db1`
- `msvcrt!iswspace` at `0x180024e01`
- `msvcrt!iswspace` at `0x180024e44`
- `msvcrt!iswspace` at `0x180024f17`
- `msvcrt!iswspace` at `0x180024f5f`
- `msvcrt!iswspace` at `0x180024f91`
- `msvcrt!iswspace` at `0x180024db1`
- `msvcrt!iswspace` at `0x180024e01`
- `msvcrt!iswspace` at `0x180024e44`
- `msvcrt!iswspace` at `0x180024f17`
- `msvcrt!iswspace` at `0x180024f5f`
- `msvcrt!iswspace` at `0x180024f91`
- `msvcrt!_wcsnicmp` at `0x180024de4`
- `msvcrt!_wcsnicmp` at `0x180024e28`
- `msvcrt!_wcsnicmp` at `0x180024e9b`
- `msvcrt!_wcsnicmp` at `0x180024f3e`
- `msvcrt!_wcsnicmp` at `0x180024de4`
- `msvcrt!_wcsnicmp` at `0x180024e28`
- `msvcrt!_wcsnicmp` at `0x180024e9b`
- `msvcrt!_wcsnicmp` at `0x180024f3e`

## pseudocode

```c
char __fastcall CWbemParseDN::ParsePrivilegeSet(unsigned __int16 *a1, unsigned int *a2, struct CSWbemPrivilegeSet *a3)
{
  __int64 v3; // rax
  unsigned __int16 v4; // r12
  char v5; // si
  char v9; // r14
  char ii; // bp
  __int64 i; // rcx
  __int64 j; // rcx
  const wchar_t *v13; // r14
  unsigned int k; // ebp
  size_t v15; // r8
  const wchar_t *v16; // rdx
  enum WbemPrivilegeEnum v17; // ebp
  __int64 v18; // rax
  unsigned __int16 *MonikerNameFromId; // rax
  __int64 v20; // rcx
  __int64 m; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  char n; // [rsp+70h] [rbp+8h]
  __int64 v27; // [rsp+78h] [rbp+10h] BYREF
  __int64 v28; // [rsp+88h] [rbp+20h]

  v3 = *a2;
  v4 = -1;
  v28 = v3;
  v5 = 1;
  n = 0;
  v9 = 0;
  ii = 1;
  if ( a1[v3] )
  {
    while ( iswspace(a1[v3]) )
    {
      v3 = ++*a2;
      if ( !a1[v3] )
        goto LABEL_4;
    }
    goto LABEL_10;
  }
LABEL_4:
  if ( !v9 )
  {
    if ( !ii )
    {
      if ( _wcsnicmp(&a1[*a2], L",", 1u) )
      {
LABEL_37:
        v24 = *(_QWORD *)a3;
        v5 = 0;
        *a2 = v28;
        (*(void (__fastcall **)(struct CSWbemPrivilegeSet *))(v24 + 96))(a3);
        return v5;
      }
      for ( i = ++*a2; a1[i]; i = ++*a2 )
      {
        if ( !iswspace(a1[i]) )
          break;
      }
    }
LABEL_10:
    if ( !_wcsnicmp(&a1[*a2], L"!", 1u) )
    {
      ++*a2;
      v4 = 0;
      for ( j = *a2; a1[j]; j = ++*a2 )
      {
        if ( !iswspace(a1[j]) )
          break;
      }
    }
    v13 = &a1[*a2];
    if ( v13 )
    {
      for ( k = 0; k < 0x1B; ++k )
      {
        v15 = -1;
        v16 = (const wchar_t *)qword_180045020[3 * k + 2];
        do
          ++v15;
        while ( v16[v15] );
        if ( !_wcsnicmp(v13, v16, v15) )
        {
          v17 = qword_180045020[3 * k];
          v18 = *(_QWORD *)a3;
          v27 = 0;
          if ( (*(int (__fastcall **)(struct CSWbemPrivilegeSet *, _QWORD, _QWORD, __int64 *))(v18 + 80))(
                 a3,
                 (unsigned int)v17,
                 v4,
                 &v27) < 0 )
            goto LABEL_37;
          MonikerNameFromId = CSWbemPrivilege::GetMonikerNameFromId(v17);
          v4 = -1;
          v20 = -1;
          do
            ++v20;
          while ( MonikerNameFromId[v20] );
          *a2 += v20;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          for ( m = *a2; a1[m]; m = ++*a2 )
          {
            if ( !iswspace(a1[m]) )
              break;
          }
          if ( _wcsnicmp(&a1[*a2], L")", 1u) )
          {
            v9 = n;
          }
          else
          {
            ++*a2;
            v9 = 1;
            v22 = *a2;
            for ( n = 1; a1[v22]; v22 = ++*a2 )
            {
              if ( !iswspace(a1[v22]) )
                break;
            }
          }
          v23 = *a2;
          for ( ii = 0; a1[v23]; v23 = ++*a2 )
          {
            if ( !iswspace(a1[v23]) )
              break;
          }
          goto LABEL_4;
        }
      }
    }
    goto LABEL_37;
  }
  return v5;
}

```

## disassembly

```asm
0x180024d68  mov     [rsp+arg_10], rbx
0x180024d6d  push    rbp
0x180024d6e  push    rsi
0x180024d6f  push    rdi
0x180024d70  push    r12
0x180024d72  push    r13
0x180024d74  push    r14
0x180024d76  push    r15
0x180024d78  sub     rsp, 30h
0x180024d7c  mov     eax, [rdx]
0x180024d7e  xor     r15d, r15d
0x180024d81  or      r12, 0FFFFFFFFFFFFFFFFh
0x180024d85  mov     [rsp+68h+arg_18], rax
0x180024d8d  mov     esi, 1
0x180024d92  mov     [rsp+68h+arg_0], r15b
0x180024d97  mov     r13, r8
0x180024d9a  mov     rbx, rdx
0x180024d9d  mov     rdi, rcx
0x180024da0  mov     r14b, r15b
0x180024da3  mov     bpl, sil
0x180024da6  cmp     [rcx+rax*2], r15w
0x180024dab  jz      short loc_180024DC6
0x180024dad  movzx   ecx, word ptr [rdi+rax*2]; C
0x180024db1  call    cs:__imp_iswspace
0x180024db7  test    eax, eax
0x180024db9  jz      short loc_180024E18
0x180024dbb  add     [rbx], esi
0x180024dbd  mov     eax, [rbx]
0x180024dbf  cmp     [rdi+rax*2], r15w
0x180024dc4  jnz     short loc_180024DAD
0x180024dc6  test    r14b, r14b
0x180024dc9  jnz     loc_180024FD1
0x180024dcf  test    bpl, bpl
0x180024dd2  jnz     short loc_180024E18
0x180024dd4  mov     eax, [rbx]
0x180024dd6  lea     rdx, asc_18003AFB8; ","
0x180024ddd  mov     r8, rsi; MaxCount
0x180024de0  lea     rcx, [rdi+rax*2]; String1
0x180024de4  call    cs:__imp__wcsnicmp
0x180024dea  test    eax, eax
0x180024dec  jnz     loc_180024FB4
0x180024df2  add     [rbx], esi
0x180024df4  mov     ecx, [rbx]
0x180024df6  cmp     [rdi+rcx*2], r15w
0x180024dfb  jz      short loc_180024E18
0x180024dfd  movzx   ecx, word ptr [rdi+rcx*2]; C
0x180024e01  call    cs:__imp_iswspace
0x180024e07  test    eax, eax
0x180024e09  jz      short loc_180024E18
0x180024e0b  add     [rbx], esi
0x180024e0d  mov     eax, [rbx]
0x180024e0f  mov     ecx, eax
0x180024e11  cmp     [rdi+rax*2], r15w
0x180024e16  jnz     short loc_180024DFD
0x180024e18  mov     eax, [rbx]
0x180024e1a  lea     rdx, asc_18003AEE8; "!"
0x180024e21  mov     r8, rsi; MaxCount
0x180024e24  lea     rcx, [rdi+rax*2]; String1
0x180024e28  call    cs:__imp__wcsnicmp
0x180024e2e  test    eax, eax
0x180024e30  jnz     short loc_180024E5B
0x180024e32  add     [rbx], esi
0x180024e34  mov     r12d, r15d
0x180024e37  mov     ecx, [rbx]
0x180024e39  cmp     [rdi+rcx*2], r15w
0x180024e3e  jz      short loc_180024E5B
0x180024e40  movzx   ecx, word ptr [rdi+rcx*2]; C
0x180024e44  call    cs:__imp_iswspace
0x180024e4a  test    eax, eax
0x180024e4c  jz      short loc_180024E5B
0x180024e4e  add     [rbx], esi
0x180024e50  mov     eax, [rbx]
0x180024e52  mov     ecx, eax
0x180024e54  cmp     [rdi+rax*2], r15w
0x180024e59  jnz     short loc_180024E40
0x180024e5b  mov     eax, [rbx]
0x180024e5d  lea     r14, [rdi+rax*2]
0x180024e61  test    r14, r14
0x180024e64  jz      loc_180024FB4
0x180024e6a  mov     ebp, r15d
0x180024e6d  cmp     ebp, 1Bh
0x180024e70  jnb     loc_180024FB1
0x180024e76  mov     eax, ebp
0x180024e78  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024e7c  lea     r15, [rax+rax*2]
0x180024e80  lea     rax, qword_180045020
0x180024e87  mov     rdx, [rax+r15*8+10h]; String2
0x180024e8c  xor     eax, eax
0x180024e8e  inc     r8; MaxCount
0x180024e91  cmp     [rdx+r8*2], ax
0x180024e96  jnz     short loc_180024E8E
0x180024e98  mov     rcx, r14; String1
0x180024e9b  call    cs:__imp__wcsnicmp
0x180024ea1  test    eax, eax
0x180024ea3  jz      short loc_180024EA9
0x180024ea5  add     ebp, esi
0x180024ea7  jmp     short loc_180024E6D
0x180024ea9  lea     rax, qword_180045020
0x180024eb0  movzx   r8d, r12w
0x180024eb4  mov     ebp, [rax+r15*8]
0x180024eb8  lea     r9, [rsp+68h+arg_8]
0x180024ebd  mov     rax, [r13+0]
0x180024ec1  xor     r15d, r15d
0x180024ec4  mov     edx, ebp
0x180024ec6  mov     [rsp+68h+arg_8], r15
0x180024ecb  mov     rcx, r13
0x180024ece  mov     rax, [rax+50h]
0x180024ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ed7  test    eax, eax
0x180024ed9  js      loc_180024FB4
0x180024edf  mov     ecx, ebp; enum WbemPrivilegeEnum
0x180024ee1  call    ?GetMonikerNameFromId@CSWbemPrivilege@@SAPEAGW4WbemPrivilegeEnum@@@Z; CSWbemPrivilege::GetMonikerNameFromId(WbemPrivilegeEnum)
0x180024ee6  or      r12, 0FFFFFFFFFFFFFFFFh
0x180024eea  mov     rcx, r12
0x180024eed  inc     rcx
0x180024ef0  cmp     [rax+rcx*2], r15w
0x180024ef5  jnz     short loc_180024EED
0x180024ef7  add     [rbx], ecx
0x180024ef9  mov     rcx, [rsp+68h+arg_8]
0x180024efe  mov     rax, [rcx]
0x180024f01  mov     rax, [rax+10h]
0x180024f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f0a  mov     ecx, [rbx]
0x180024f0c  cmp     [rdi+rcx*2], r15w
0x180024f11  jz      short loc_180024F2E
0x180024f13  movzx   ecx, word ptr [rdi+rcx*2]; C
0x180024f17  call    cs:__imp_iswspace
0x180024f1d  test    eax, eax
0x180024f1f  jz      short loc_180024F2E
0x180024f21  add     [rbx], esi
0x180024f23  mov     eax, [rbx]
0x180024f25  mov     ecx, eax
0x180024f27  cmp     [rdi+rax*2], r15w
0x180024f2c  jnz     short loc_180024F13
0x180024f2e  mov     eax, [rbx]
0x180024f30  lea     rdx, asc_18003B0DC; ")"
0x180024f37  mov     r8, rsi; MaxCount
0x180024f3a  lea     rcx, [rdi+rax*2]; String1
0x180024f3e  call    cs:__imp__wcsnicmp
0x180024f44  test    eax, eax
0x180024f46  jnz     short loc_180024F78
0x180024f48  add     [rbx], esi
0x180024f4a  mov     r14b, sil
0x180024f4d  mov     ecx, [rbx]
0x180024f4f  mov     [rsp+68h+arg_0], sil
0x180024f54  cmp     [rdi+rcx*2], r15w
0x180024f59  jz      short loc_180024F7D
0x180024f5b  movzx   ecx, word ptr [rdi+rcx*2]; C
0x180024f5f  call    cs:__imp_iswspace
0x180024f65  test    eax, eax
0x180024f67  jz      short loc_180024F7D
0x180024f69  add     [rbx], esi
0x180024f6b  mov     eax, [rbx]
0x180024f6d  mov     ecx, eax
0x180024f6f  cmp     [rdi+rax*2], r15w
0x180024f74  jnz     short loc_180024F5B
0x180024f76  jmp     short loc_180024F7D
0x180024f78  mov     r14b, [rsp+68h+arg_0]
0x180024f7d  mov     ecx, [rbx]
0x180024f7f  mov     bpl, r15b
0x180024f82  cmp     [rdi+rcx*2], r15w
0x180024f87  jz      loc_180024DC6
0x180024f8d  movzx   ecx, word ptr [rdi+rcx*2]; C
0x180024f91  call    cs:__imp_iswspace
0x180024f97  test    eax, eax
0x180024f99  jz      loc_180024DC6
0x180024f9f  add     [rbx], esi
0x180024fa1  mov     eax, [rbx]
0x180024fa3  mov     ecx, eax
0x180024fa5  cmp     [rdi+rax*2], r15w
0x180024faa  jnz     short loc_180024F8D
0x180024fac  jmp     loc_180024DC6
0x180024fb1  xor     r15d, r15d
0x180024fb4  mov     rcx, [r13+0]
0x180024fb8  mov     sil, r15b
0x180024fbb  mov     rax, [rsp+68h+arg_18]
0x180024fc3  mov     [rbx], eax
0x180024fc5  mov     rax, [rcx+60h]
0x180024fc9  mov     rcx, r13
0x180024fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fd1  mov     rbx, [rsp+68h+arg_10]
0x180024fd9  mov     al, sil
0x180024fdc  add     rsp, 30h
0x180024fe0  pop     r15
0x180024fe2  pop     r14
0x180024fe4  pop     r13
0x180024fe6  pop     r12
0x180024fe8  pop     rdi
0x180024fe9  pop     rsi
0x180024fea  pop     rbp
0x180024feb  retn
```
