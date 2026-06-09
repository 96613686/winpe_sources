# CShareEnumerator::_AbsoluteSDHelper(void * const,void * *,ulong *,_ACL * *,ulong *,_ACL * *,ulong *,void * *,ulong *,void * *,ulong *)

- ea: `0x180010498`
- end: `0x180010631`
- name: `?_AbsoluteSDHelper@CShareEnumerator@@AEAAXQEAXPEAPEAXPEAKPEAPEAU_ACL@@2321212@Z`
- size: `409`
- prototype: `void __fastcall(CShareEnumerator *this, void *const, void **, unsigned int *, struct _ACL **, LPDWORD, struct _ACL **, LPDWORD, void **, LPDWORD, void **, LPDWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010638`

## callees

- `0x18000d038`
- `0x180010420`
- `0x180010498`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001060b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001060b`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180010575`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180010575`

## pseudocode

```c
void __fastcall CShareEnumerator::_AbsoluteSDHelper(
        CShareEnumerator *this,
        void *const a2,
        void **a3,
        unsigned int *a4,
        struct _ACL **a5,
        LPDWORD a6,
        struct _ACL **a7,
        LPDWORD a8,
        void **a9,
        LPDWORD a10,
        void **a11,
        LPDWORD a12)
{
  void *v16; // r10
  int v18; // ebx
  DWORD LastError; // eax
  DWORD v21; // [rsp+A0h] [rbp+8h]
  DWORD v23; // [rsp+C8h] [rbp+30h]
  DWORD v24; // [rsp+D8h] [rbp+40h]
  DWORD v25; // [rsp+E8h] [rbp+50h]
  DWORD v26; // [rsp+F8h] [rbp+60h]

  v16 = a2;
  v18 = 0;
  v21 = *a4;
  v23 = *a6;
  v24 = *a8;
  v25 = *a10;
  v26 = *a12;
  while ( v18 < 2 )
  {
    if ( !MakeAbsoluteSD(v16, *a3, a4, *a5, a6, *a7, a8, *a9, a10, *a11, a12) )
    {
      if ( v18 > 0 || GetLastError() != 122 )
      {
        LastError = GetLastError();
        TrkRaiseWin32Error(LastError);
      }
      SDAllocHelper(a3, v21, *a4);
      SDAllocHelper(a5, v23, *a6);
      SDAllocHelper(a7, v24, *a8);
      SDAllocHelper(a9, v25, *a10);
      SDAllocHelper(a11, v26, *a12);
    }
    v16 = a2;
    ++v18;
  }
}

```

## disassembly

```asm
0x180010498  mov     [rsp+arg_10], rbx
0x18001049d  mov     [rsp+arg_8], rdx
0x1800104a2  mov     [rsp+arg_0], rcx
0x1800104a7  push    rbp
0x1800104a8  push    rsi
0x1800104a9  push    rdi
0x1800104aa  push    r12
0x1800104ac  push    r13
0x1800104ae  push    r14
0x1800104b0  push    r15
0x1800104b2  sub     rsp, 60h
0x1800104b6  mov     rsi, [rsp+98h+arg_28]
0x1800104be  mov     rdi, r9
0x1800104c1  mov     r14, [rsp+98h+arg_38]
0x1800104c9  mov     r12, r8
0x1800104cc  mov     eax, [r9]
0x1800104cf  mov     r10, rdx
0x1800104d2  mov     r15, [rsp+98h+arg_48]
0x1800104da  xor     ebx, ebx
0x1800104dc  mov     rbp, [rsp+98h+arg_58]
0x1800104e4  mov     r13, [rsp+98h+arg_50]
0x1800104ec  mov     dword ptr [rsp+98h+arg_0], eax
0x1800104f3  mov     eax, [rsi]
0x1800104f5  mov     dword ptr [rsp+98h+arg_28], eax
0x1800104fc  mov     eax, [r14]
0x1800104ff  mov     dword ptr [rsp+98h+arg_38], eax
0x180010506  mov     eax, [r15]
0x180010509  mov     dword ptr [rsp+98h+arg_48], eax
0x180010510  mov     eax, [rbp+0]
0x180010513  mov     dword ptr [rsp+98h+arg_58], eax
0x18001051a  cmp     ebx, 2
0x18001051d  jge     loc_180010619
0x180010523  mov     rax, [r13+0]
0x180010527  mov     r8, rdi; lpdwAbsoluteSecurityDescriptorSize
0x18001052a  mov     rdx, [r12]; pAbsoluteSecurityDescriptor
0x18001052e  mov     rcx, r10; pSelfRelativeSecurityDescriptor
0x180010531  mov     [rsp+98h+lpdwPrimaryGroupSize], rbp; lpdwPrimaryGroupSize
0x180010536  mov     [rsp+98h+pPrimaryGroup], rax; pPrimaryGroup
0x18001053b  mov     rax, [rsp+98h+arg_40]
0x180010543  mov     [rsp+98h+lpdwOwnerSize], r15; lpdwOwnerSize
0x180010548  mov     rax, [rax]
0x18001054b  mov     [rsp+98h+pOwner], rax; pOwner
0x180010550  mov     rax, [rsp+98h+arg_30]
0x180010558  mov     [rsp+98h+lpdwSaclSize], r14; lpdwSaclSize
0x18001055d  mov     rax, [rax]
0x180010560  mov     [rsp+98h+pSacl], rax; pSacl
0x180010565  mov     rax, [rsp+98h+arg_20]
0x18001056d  mov     [rsp+98h+lpdwDaclSize], rsi; lpdwDaclSize
0x180010572  mov     r9, [rax]; pDacl
0x180010575  call    cs:__imp_MakeAbsoluteSD
0x18001057b  test    eax, eax
0x18001057d  jnz     short loc_1800105FC
0x18001057f  test    ebx, ebx
0x180010581  jg      loc_18001060B
0x180010587  call    cs:__imp_GetLastError
0x18001058d  cmp     eax, 7Ah ; 'z'
0x180010590  jnz     short loc_18001060B
0x180010592  mov     r8d, [rdi]
0x180010595  mov     rcx, r12
0x180010598  mov     edx, dword ptr [rsp+98h+arg_0]
0x18001059f  call    SDAllocHelper
0x1800105a4  mov     r8d, [rsi]
0x1800105a7  mov     edx, dword ptr [rsp+98h+arg_28]
0x1800105ae  mov     rcx, [rsp+98h+arg_20]
0x1800105b6  call    SDAllocHelper
0x1800105bb  mov     r8d, [r14]
0x1800105be  mov     edx, dword ptr [rsp+98h+arg_38]
0x1800105c5  mov     rcx, [rsp+98h+arg_30]
0x1800105cd  call    SDAllocHelper
0x1800105d2  mov     r8d, [r15]
0x1800105d5  mov     edx, dword ptr [rsp+98h+arg_48]
0x1800105dc  mov     rcx, [rsp+98h+arg_40]
0x1800105e4  call    SDAllocHelper
0x1800105e9  mov     r8d, [rbp+0]
0x1800105ed  mov     rcx, r13
0x1800105f0  mov     edx, dword ptr [rsp+98h+arg_58]
0x1800105f7  call    SDAllocHelper
0x1800105fc  mov     r10, [rsp+98h+arg_8]
0x180010604  inc     ebx
0x180010606  jmp     loc_18001051A
0x18001060b  call    cs:__imp_GetLastError
0x180010611  mov     ecx, eax; int
0x180010613  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180010619  mov     rbx, [rsp+98h+arg_10]
0x180010621  add     rsp, 60h
0x180010625  pop     r15
0x180010627  pop     r14
0x180010629  pop     r13
0x18001062b  pop     r12
0x18001062d  pop     rdi
0x18001062e  pop     rsi
0x18001062f  pop     rbp
0x180010630  retn
```
