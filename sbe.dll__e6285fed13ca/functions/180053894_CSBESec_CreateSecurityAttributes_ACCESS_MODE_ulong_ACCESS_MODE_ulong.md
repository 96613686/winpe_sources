# CSBESec::CreateSecurityAttributes(_ACCESS_MODE,ulong,_ACCESS_MODE,ulong)

- ea: `0x180053894`
- end: `0x180053a49`
- name: `?CreateSecurityAttributes@CSBESec@@IEAAJW4_ACCESS_MODE@@K0K@Z`
- size: `437`
- prototype: `__int64 __fastcall(CSBESec *__hidden this, enum _ACCESS_MODE, unsigned int, enum _ACCESS_MODE, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000ac70`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x18000256c`
- `0x180053894`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800539d6`
- `KERNEL32!GetLastError` at `0x1800539d6`
- `KERNEL32!LocalAlloc` at `0x1800539c7`
- `KERNEL32!LocalAlloc` at `0x1800539c7`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x180053931`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18005398c`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x180053931`
- `ADVAPI32!BuildTrusteeWithSidW` at `0x18005398c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800539ea`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800539ea`
- `ADVAPI32!SetEntriesInAclW` at `0x1800539a2`
- `ADVAPI32!SetEntriesInAclW` at `0x1800539a2`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180053a03`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180053a03`

## pseudocode

```c
__int64 __fastcall CSBESec::CreateSecurityAttributes(
        CSBESec *this,
        unsigned __int64 a2,
        __int64 a3,
        enum _ACCESS_MODE a4)
{
  struct _EXPLICIT_ACCESS_W *v5; // rsi
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rbx
  __int64 v9; // rax
  signed int LastError; // eax
  bool v11; // cc
  HLOCAL v12; // rax
  __int64 v13; // rax

  if ( !*((_QWORD *)this + 6) || !*((_QWORD *)this + 8) )
  {
    v5 = 0;
    v6 = -2147418113;
    goto LABEL_16;
  }
  v5 = (struct _EXPLICIT_ACCESS_W *)operator new[](saturated_mul(*((unsigned __int8 *)this + 56) + 1LL, 0x30u));
  if ( v5 )
  {
    memset_0(v5, 0, 48 * (*((unsigned __int8 *)this + 56) + 1LL));
    LOBYTE(v7) = *((_BYTE *)this + 56);
    v8 = 0;
    if ( (_BYTE)v7 )
    {
      do
      {
        v9 = v8;
        v5[v9].grfAccessPermissions = 983047;
        *(_QWORD *)&v5[v9].grfAccessMode = 2;
        BuildTrusteeWithSidW(&v5[v8].Trustee, *((PSID *)this + v8 + 6));
        v7 = *((unsigned __int8 *)this + 56);
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (unsigned int)v8 < v7 );
    }
    v5[(unsigned __int8)v7].grfAccessPermissions = 983071;
    *(_QWORD *)&v5[*((unsigned __int8 *)this + 56)].grfAccessMode = 2;
    BuildTrusteeWithSidW(&v5[*((unsigned __int8 *)this + 56)].Trustee, *((PSID *)this + 8));
    LastError = SetEntriesInAclW(*((unsigned __int8 *)this + 56) + 1, v5, 0, (PACL *)this + 9);
    v6 = LastError;
    v11 = LastError <= 0;
    if ( !LastError )
    {
      v12 = LocalAlloc(0x40u, 0x28u);
      *((_QWORD *)this + 1) = v12;
      if ( v12
        && InitializeSecurityDescriptor(v12, 1u)
        && SetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), 1, *((PACL *)this + 9), 0) )
      {
        v13 = *((_QWORD *)this + 1);
        *((_DWORD *)this + 4) = 24;
        v6 = 0;
        *((_QWORD *)this + 3) = v13;
        *((_QWORD *)this + 5) = (char *)this + 16;
        *((_DWORD *)this + 8) = 0;
        goto LABEL_16;
      }
      LastError = GetLastError();
      v6 = LastError;
      v11 = LastError <= 0;
    }
    if ( !v11 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v6 = -2147024882;
  }
LABEL_16:
  operator delete(v5, a2);
  return v6;
}

```

## disassembly

```asm
0x180053894  push    rbx
0x180053896  push    rsi
0x180053897  push    rdi
0x180053898  push    r14
0x18005389a  sub     rsp, 28h
0x18005389e  cmp     qword ptr [rcx+30h], 0
0x1800538a3  mov     rdi, rcx
0x1800538a6  jz      loc_180053A2E
0x1800538ac  cmp     qword ptr [rcx+40h], 0
0x1800538b1  jz      loc_180053A2E
0x1800538b7  movzx   edx, byte ptr [rcx+38h]
0x1800538bb  mov     eax, 30h ; '0'
0x1800538c0  inc     rdx
0x1800538c3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800538ca  mul     rdx
0x1800538cd  cmovb   rax, rcx
0x1800538d1  mov     rcx, rax; unsigned __int64
0x1800538d4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800538d9  mov     rsi, rax
0x1800538dc  test    rax, rax
0x1800538df  jnz     short loc_1800538EB
0x1800538e1  mov     ebx, 8007000Eh
0x1800538e6  jmp     loc_180053A35
0x1800538eb  movzx   eax, byte ptr [rdi+38h]
0x1800538ef  xor     edx, edx; Val
0x1800538f1  inc     rax
0x1800538f4  mov     rcx, rsi; void *
0x1800538f7  lea     r8, [rax+rax*2]
0x1800538fb  shl     r8, 4; Size
0x1800538ff  call    memset_0
0x180053904  mov     al, [rdi+38h]
0x180053907  xor     ebx, ebx
0x180053909  lea     r14d, [rbx+2]
0x18005390d  test    al, al
0x18005390f  jz      short loc_180053941
0x180053911  lea     rax, [rbx+rbx*2]
0x180053915  shl     rax, 4
0x180053919  lea     rcx, [rsi+10h]
0x18005391d  add     rcx, rax; pTrustee
0x180053920  mov     dword ptr [rax+rsi], 0F0007h
0x180053927  mov     [rax+rsi+4], r14
0x18005392c  mov     rdx, [rdi+rbx*8+30h]; pSid
0x180053931  call    cs:__imp_BuildTrusteeWithSidW
0x180053937  movzx   eax, byte ptr [rdi+38h]
0x18005393b  inc     ebx
0x18005393d  cmp     ebx, eax
0x18005393f  jb      short loc_180053911
0x180053941  movzx   eax, al
0x180053944  lea     rcx, [rax+rax*2]
0x180053948  add     rcx, rcx
0x18005394b  mov     dword ptr [rsi+rcx*8], 0F001Fh
0x180053952  movzx   eax, byte ptr [rdi+38h]
0x180053956  lea     rcx, [rax+rax*2]
0x18005395a  add     rcx, rcx
0x18005395d  mov     [rsi+rcx*8+4], r14d
0x180053962  movzx   eax, byte ptr [rdi+38h]
0x180053966  lea     rcx, [rax+rax*2]
0x18005396a  add     rcx, rcx
0x18005396d  mov     dword ptr [rsi+rcx*8+8], 0
0x180053975  movzx   eax, byte ptr [rdi+38h]
0x180053979  mov     rdx, [rdi+40h]; pSid
0x18005397d  lea     rcx, [rax+rax*2]
0x180053981  shl     rcx, 4
0x180053985  add     rcx, 10h
0x180053989  add     rcx, rsi; pTrustee
0x18005398c  call    cs:__imp_BuildTrusteeWithSidW
0x180053992  movzx   ecx, byte ptr [rdi+38h]
0x180053996  lea     r9, [rdi+48h]; NewAcl
0x18005399a  inc     ecx; cCountOfExplicitEntries
0x18005399c  xor     r8d, r8d; OldAcl
0x18005399f  mov     rdx, rsi; pListOfExplicitEntries
0x1800539a2  call    cs:__imp_SetEntriesInAclW
0x1800539a8  mov     ebx, eax
0x1800539aa  test    eax, eax
0x1800539ac  jz      short loc_1800539BF
0x1800539ae  jle     loc_180053A35
0x1800539b4  movzx   ebx, ax
0x1800539b7  or      ebx, 80070000h
0x1800539bd  jmp     short loc_180053A35
0x1800539bf  mov     edx, 28h ; '('; uBytes
0x1800539c4  lea     ecx, [rdx+18h]; uFlags
0x1800539c7  call    cs:__imp_LocalAlloc
0x1800539cd  mov     [rdi+8], rax
0x1800539d1  test    rax, rax
0x1800539d4  jnz     short loc_1800539E2
0x1800539d6  call    cs:__imp_GetLastError
0x1800539dc  mov     ebx, eax
0x1800539de  test    eax, eax
0x1800539e0  jmp     short loc_1800539AE
0x1800539e2  mov     edx, 1; dwRevision
0x1800539e7  mov     rcx, rax; pSecurityDescriptor
0x1800539ea  call    cs:__imp_InitializeSecurityDescriptor
0x1800539f0  test    eax, eax
0x1800539f2  jz      short loc_1800539D6
0x1800539f4  mov     r8, [rdi+48h]; pDacl
0x1800539f8  xor     r9d, r9d; bDaclDefaulted
0x1800539fb  mov     rcx, [rdi+8]; pSecurityDescriptor
0x1800539ff  lea     edx, [r9+1]; bDaclPresent
0x180053a03  call    cs:__imp_SetSecurityDescriptorDacl
0x180053a09  test    eax, eax
0x180053a0b  jz      short loc_1800539D6
0x180053a0d  mov     rax, [rdi+8]
0x180053a11  lea     rcx, [rdi+10h]
0x180053a15  mov     dword ptr [rcx], 18h
0x180053a1b  xor     ebx, ebx
0x180053a1d  mov     [rdi+18h], rax
0x180053a21  mov     [rdi+28h], rcx
0x180053a25  mov     dword ptr [rdi+20h], 0
0x180053a2c  jmp     short loc_180053A35
0x180053a2e  xor     esi, esi
0x180053a30  mov     ebx, 8000FFFFh
0x180053a35  mov     rcx, rsi; void *
0x180053a38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180053a3d  mov     eax, ebx
0x180053a3f  add     rsp, 28h
0x180053a43  pop     r14
0x180053a45  pop     rdi
0x180053a46  pop     rsi
0x180053a47  pop     rbx
0x180053a48  retn
```
