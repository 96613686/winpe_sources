# CNtAcl::Resize(ulong)

- ea: `0x18001b490`
- end: `0x18001b5b8`
- name: `?Resize@CNtAcl@@QEAAHK@Z`
- size: `296`
- prototype: `__int64 __fastcall(CNtAcl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x18001b8a0`

## callees

- `0x18000a290`
- `0x18000ab30`
- `0x18001b490`
- `0x18001b780`
- `0x18001b8a0`
- `0x18001bfac`
- `0x18001c130`
- `0x18001c1e0`
- `0x18001c290`
- `0x18001c6f0`
- `0x18001c990`
- `0x18001d204`
- `0x18001d250`
- `0x18001d360`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b598`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtAcl::Resize(struct _ACL **this, unsigned int a2)
{
  struct _ACL *v4; // rcx
  CNtAcl *v6; // rax
  unsigned int v7; // edx
  CNtAcl *v8; // rbx
  int i; // ebp
  struct CNtAce *Ace; // rax
  CNtAce *v11; // rsi
  CNtAcl *v12; // rcx
  unsigned int v13; // edx
  CNtAcl *v14; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+50h] [rbp+18h] BYREF

  v4 = *this;
  if ( !v4 )
    return 0;
  if ( *((_DWORD *)this + 2) )
    return 0;
  if ( !(unsigned int)DLIsValidAcl(v4) )
    return 0;
  LODWORD(v14) = 0;
  v15 = 0;
  if ( !(unsigned int)CNtAcl::GetAclSizeInfo((CNtAcl *)this, (unsigned int *)&v14, &v15) )
    return 0;
  if ( a2 == 1 )
    a2 = (unsigned int)v14;
  if ( a2 < (unsigned int)v14 )
    return 0;
  v6 = (CNtAcl *)CWin32DefaultArena::WbemMemAlloc(0x10u);
  v14 = v6;
  v8 = v6 ? CNtAcl::CNtAcl(v6, a2) : 0LL;
  if ( !v8 )
    return 0;
  if ( *((_DWORD *)v8 + 2) )
  {
LABEL_22:
    v12 = v8;
LABEL_23:
    CNtAcl::`scalar deleting destructor'(v12, v7);
    return 0;
  }
  for ( i = 0; i < (int)CNtAcl::GetNumAces((CNtAcl *)this); ++i )
  {
    Ace = CNtAcl::GetAce((CNtAcl *)this, i);
    v11 = Ace;
    v12 = v8;
    if ( !Ace )
      goto LABEL_23;
    if ( !(unsigned int)CNtAcl::AddAce(v8, Ace) )
    {
      GetLastError();
      CNtAce::`scalar deleting destructor'(v11, 1u);
      goto LABEL_22;
    }
    CNtAce::~CNtAce(v11);
    CMUILocale::_Free(v11);
  }
  if ( !(unsigned int)CNtAcl::IsValid((CNtAcl *)this) )
    goto LABEL_22;
  CNtAcl::operator=(this, v8);
  CNtAcl::`scalar deleting destructor'(v8, v13);
  return 1;
}

```

## disassembly

```asm
0x18001b490  mov     [rsp+arg_8], rbx
0x18001b495  push    rbp
0x18001b496  push    rsi
0x18001b497  push    rdi
0x18001b498  sub     rsp, 20h
0x18001b49c  mov     ebx, edx
0x18001b49e  mov     rdi, rcx
0x18001b4a1  mov     rcx, [rcx]; struct _ACL *
0x18001b4a4  test    rcx, rcx
0x18001b4a7  jz      short loc_18001B4EC
0x18001b4a9  cmp     dword ptr [rdi+8], 0
0x18001b4ad  jnz     short loc_18001B4EC
0x18001b4af  call    ?DLIsValidAcl@@YAHPEAU_ACL@@@Z; DLIsValidAcl(_ACL *)
0x18001b4b4  test    eax, eax
0x18001b4b6  jz      short loc_18001B4EC
0x18001b4b8  mov     dword ptr [rsp+38h+arg_0], 0
0x18001b4c0  mov     [rsp+38h+arg_10], 0
0x18001b4c8  lea     r8, [rsp+38h+arg_10]; unsigned int *
0x18001b4cd  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x18001b4d2  mov     rcx, rdi; this
0x18001b4d5  call    ?GetAclSizeInfo@CNtAcl@@QEAAHPEAK0@Z; CNtAcl::GetAclSizeInfo(ulong *,ulong *)
0x18001b4da  test    eax, eax
0x18001b4dc  jz      short loc_18001B4EC
0x18001b4de  cmp     ebx, 1
0x18001b4e1  cmovz   ebx, dword ptr [rsp+38h+arg_0]
0x18001b4e6  cmp     ebx, dword ptr [rsp+38h+arg_0]
0x18001b4ea  jnb     short loc_18001B4FB
0x18001b4ec  xor     eax, eax
0x18001b4ee  mov     rbx, [rsp+38h+arg_8]
0x18001b4f3  add     rsp, 20h
0x18001b4f7  pop     rdi
0x18001b4f8  pop     rsi
0x18001b4f9  pop     rbp
0x18001b4fa  retn
0x18001b4fb  mov     ecx, 10h; unsigned __int64
0x18001b500  call    ?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001b505  mov     [rsp+38h+arg_0], rax
0x18001b50a  test    rax, rax
0x18001b50d  jz      short loc_18001B56E
0x18001b50f  mov     edx, ebx; unsigned int
0x18001b511  mov     rcx, rax; this
0x18001b514  call    ??0CNtAcl@@QEAA@K@Z; CNtAcl::CNtAcl(ulong)
0x18001b519  mov     rbx, rax
0x18001b51c  test    rbx, rbx
0x18001b51f  jz      short loc_18001B4EC
0x18001b521  cmp     dword ptr [rbx+8], 0
0x18001b525  jnz     loc_18001B5AB
0x18001b52b  xor     ebp, ebp
0x18001b52d  mov     rcx, rdi; this
0x18001b530  call    ?GetNumAces@CNtAcl@@QEAAHXZ; CNtAcl::GetNumAces(void)
0x18001b535  mov     rcx, rdi; this
0x18001b538  cmp     ebp, eax
0x18001b53a  jge     short loc_18001B572
0x18001b53c  mov     edx, ebp; int
0x18001b53e  call    ?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z; CNtAcl::GetAce(int)
0x18001b543  mov     rsi, rax
0x18001b546  mov     rcx, rbx; this
0x18001b549  test    rax, rax
0x18001b54c  jz      short loc_18001B5AE
0x18001b54e  mov     rdx, rax; struct CNtAce *
0x18001b551  call    ?AddAce@CNtAcl@@QEAAHPEAVCNtAce@@@Z; CNtAcl::AddAce(CNtAce *)
0x18001b556  test    eax, eax
0x18001b558  jz      short loc_18001B598
0x18001b55a  mov     rcx, rsi; this
0x18001b55d  call    ??1CNtAce@@UEAA@XZ; CNtAce::~CNtAce(void)
0x18001b562  mov     rcx, rsi; void *
0x18001b565  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001b56a  inc     ebp
0x18001b56c  jmp     short loc_18001B52D
0x18001b56e  xor     ebx, ebx
0x18001b570  jmp     short loc_18001B51C
0x18001b572  call    ?IsValid@CNtAcl@@QEAAHXZ; CNtAcl::IsValid(void)
0x18001b577  test    eax, eax
0x18001b579  jz      short loc_18001B5AB
0x18001b57b  mov     rdx, rbx
0x18001b57e  mov     rcx, rdi
0x18001b581  call    ??4CNtAcl@@QEAAAEAV0@AEBV0@@Z; CNtAcl::operator=(CNtAcl const &)
0x18001b586  mov     rcx, rbx; this
0x18001b589  call    ??_GCNtAcl@@QEAAPEAXI@Z; CNtAcl::`scalar deleting destructor'(uint)
0x18001b58e  mov     eax, 1
0x18001b593  jmp     loc_18001B4EE
0x18001b598  call    cs:__imp_GetLastError
0x18001b59e  mov     edx, 1; unsigned int
0x18001b5a3  mov     rcx, rsi; this
0x18001b5a6  call    ??_GCNtAce@@UEAAPEAXI@Z; CNtAce::`scalar deleting destructor'(uint)
0x18001b5ab  mov     rcx, rbx; this
0x18001b5ae  call    ??_GCNtAcl@@QEAAPEAXI@Z; CNtAcl::`scalar deleting destructor'(uint)
0x18001b5b3  jmp     loc_18001B4EC
```
