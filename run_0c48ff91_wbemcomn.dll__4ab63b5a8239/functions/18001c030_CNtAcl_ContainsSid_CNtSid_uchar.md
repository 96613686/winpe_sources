# CNtAcl::ContainsSid(CNtSid &,uchar &)

- ea: `0x18001c030`
- end: `0x18001c123`
- name: `?ContainsSid@CNtAcl@@QEAAHAEAVCNtSid@@AEAE@Z`
- size: `243`
- prototype: `__int64 __fastcall(CNtAcl *__hidden this, struct CNtSid *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000ab30`
- `0x18001c030`
- `0x18001c130`
- `0x18001c1e0`
- `0x18001c290`
- `0x18001c2d0`
- `0x18001c4d0`
- `0x18001c56c`
- `0x18001c5a0`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18001c0b3`
- `ntdll!RtlEqualSid` at `0x18001c0b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNtAcl::ContainsSid(CNtAcl *this, PSID *a2, unsigned __int8 *a3)
{
  int NumAces; // r14d
  unsigned int v7; // ebp
  int i; // esi
  CNtAce *Ace; // rax
  CNtAce *v10; // rdi
  struct CNtSid *Sid; // rax
  unsigned int v12; // edx
  CNtSid *v13; // rbx
  unsigned int v14; // edx

  NumAces = CNtAcl::GetNumAces(this);
  if ( NumAces < 0 )
    return 0;
  v7 = 0;
  for ( i = 0; i < NumAces; ++i )
  {
    Ace = CNtAcl::GetAce(this, i);
    v10 = Ace;
    if ( Ace )
    {
      Sid = CNtAce::GetSid(Ace);
      v13 = Sid;
      if ( Sid && !*((_DWORD *)Sid + 2) && (unsigned int)CNtSid::IsValid(Sid) && RtlEqualSid(*a2, *(PSID *)v13) == 1 )
      {
        *a3 = CNtAce::GetFlags(v10);
        v7 = 1;
        CNtSid::`scalar deleting destructor'(v13, v14);
        CNtAce::~CNtAce(v10);
        CMUILocale::_Free(v10);
        return v7;
      }
      if ( v13 )
        CNtSid::`scalar deleting destructor'(v13, v12);
      CNtAce::~CNtAce(v10);
      CMUILocale::_Free(v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18001c030  push    rbx
0x18001c032  push    rbp
0x18001c033  push    rsi
0x18001c034  push    rdi
0x18001c035  push    r12
0x18001c037  push    r13
0x18001c039  push    r14
0x18001c03b  push    r15
0x18001c03d  sub     rsp, 38h
0x18001c041  mov     r12, r8
0x18001c044  mov     r13, rdx
0x18001c047  mov     r15, rcx
0x18001c04a  call    ?GetNumAces@CNtAcl@@QEAAHXZ; CNtAcl::GetNumAces(void)
0x18001c04f  mov     r14d, eax
0x18001c052  test    eax, eax
0x18001c054  js      loc_18001C11F
0x18001c05a  xor     ebp, ebp
0x18001c05c  xor     esi, esi
0x18001c05e  cmp     esi, r14d
0x18001c061  jge     loc_18001C0E7
0x18001c067  mov     edx, esi; int
0x18001c069  mov     rcx, r15; this
0x18001c06c  call    ?GetAce@CNtAcl@@QEAAPEAVCNtAce@@H@Z; CNtAcl::GetAce(int)
0x18001c071  mov     rdi, rax
0x18001c074  test    rax, rax
0x18001c077  jz      loc_18001C118
0x18001c07d  mov     [rsp+78h+arg_18], rax
0x18001c085  mov     rcx, rax; this
0x18001c088  call    ?GetSid@CNtAce@@QEAAPEAVCNtSid@@XZ; CNtAce::GetSid(void)
0x18001c08d  mov     rbx, rax
0x18001c090  mov     [rsp+78h+var_58], rax
0x18001c095  test    rax, rax
0x18001c098  jz      short loc_18001C0FA
0x18001c09a  cmp     dword ptr [rax+8], 0
0x18001c09e  jnz     short loc_18001C0FA
0x18001c0a0  mov     rcx, rax; this
0x18001c0a3  call    ?IsValid@CNtSid@@QEAAHXZ; CNtSid::IsValid(void)
0x18001c0a8  test    eax, eax
0x18001c0aa  jz      short loc_18001C0FA
0x18001c0ac  mov     rdx, [rbx]; Sid2
0x18001c0af  mov     rcx, [r13+0]; Sid1
0x18001c0b3  call    cs:__imp_RtlEqualSid
0x18001c0b9  cmp     al, 1
0x18001c0bb  jnz     short loc_18001C0FA
0x18001c0bd  mov     rcx, rdi; this
0x18001c0c0  call    ?GetFlags@CNtAce@@UEAAHXZ; CNtAce::GetFlags(void)
0x18001c0c5  mov     [r12], al
0x18001c0c9  mov     ebp, 1
0x18001c0ce  mov     rcx, rbx; this
0x18001c0d1  call    ??_GCNtSid@@QEAAPEAXI@Z; CNtSid::`scalar deleting destructor'(uint)
0x18001c0d6  nop
0x18001c0d7  mov     rcx, rdi; this
0x18001c0da  call    ??1CNtAce@@UEAA@XZ; CNtAce::~CNtAce(void)
0x18001c0df  mov     rcx, rdi; void *
0x18001c0e2  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001c0e7  mov     eax, ebp
0x18001c0e9  add     rsp, 38h
0x18001c0ed  pop     r15
0x18001c0ef  pop     r14
0x18001c0f1  pop     r13
0x18001c0f3  pop     r12
0x18001c0f5  pop     rdi
0x18001c0f6  pop     rsi
0x18001c0f7  pop     rbp
0x18001c0f8  pop     rbx
0x18001c0f9  retn
0x18001c0fa  test    rbx, rbx
0x18001c0fd  jz      short loc_18001C108
0x18001c0ff  mov     rcx, rbx; this
0x18001c102  call    ??_GCNtSid@@QEAAPEAXI@Z; CNtSid::`scalar deleting destructor'(uint)
0x18001c107  nop
0x18001c108  mov     rcx, rdi; this
0x18001c10b  call    ??1CNtAce@@UEAA@XZ; CNtAce::~CNtAce(void)
0x18001c110  mov     rcx, rdi; void *
0x18001c113  call    ?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18001c118  inc     esi
0x18001c11a  jmp     loc_18001C05E
0x18001c11f  xor     eax, eax
0x18001c121  jmp     short loc_18001C0E9
```
