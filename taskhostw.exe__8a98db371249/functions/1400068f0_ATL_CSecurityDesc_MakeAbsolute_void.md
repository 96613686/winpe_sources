# ATL::CSecurityDesc::MakeAbsolute(void)

- ea: `0x1400068f0`
- end: `0x140006b03`
- name: `?MakeAbsolute@CSecurityDesc@ATL@@QEAAXXZ`
- size: `531`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022d0`

## callees

- `0x1400068f0`
- `0x140007298`
- `0x1400072bc`
- `0x140007468`
- `0x14000c010`

## import_xrefs

- `msvcrt!free` at `0x140006a92`
- `msvcrt!free` at `0x140006a9b`
- `msvcrt!free` at `0x140006aa4`
- `msvcrt!free` at `0x140006aad`
- `msvcrt!free` at `0x140006ab6`
- `msvcrt!free` at `0x140006a92`
- `msvcrt!free` at `0x140006a9b`
- `msvcrt!free` at `0x140006aa4`
- `msvcrt!free` at `0x140006aad`
- `msvcrt!free` at `0x140006ab6`
- `msvcrt!malloc` at `0x1400069bb`
- `msvcrt!malloc` at `0x1400069d2`
- `msvcrt!malloc` at `0x1400069f7`
- `msvcrt!malloc` at `0x140006a13`
- `msvcrt!malloc` at `0x140006a2f`
- `msvcrt!malloc` at `0x1400069bb`
- `msvcrt!malloc` at `0x1400069d2`
- `msvcrt!malloc` at `0x1400069f7`
- `msvcrt!malloc` at `0x140006a13`
- `msvcrt!malloc` at `0x140006a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400069a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400069a7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140006935`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140006935`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400069a1`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140006a7e`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x1400069a1`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x140006a7e`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::MakeAbsolute(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  struct _ACL *pSacl; // rsi
  void *v4; // rcx
  void *v5; // rdi
  void *pOwner; // r12
  void *pPrimaryGroup; // r15
  struct _ACL *v8; // r14
  signed int Error; // ebx
  DWORD dwDaclSize; // [rsp+68h] [rbp+17h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize; // [rsp+6Ch] [rbp+1Bh] BYREF
  DWORD dwRevision[2]; // [rsp+70h] [rbp+1Fh] BYREF
  WORD pControl; // [rsp+B8h] [rbp+67h] BYREF
  DWORD dwPrimaryGroupSize; // [rsp+C0h] [rbp+6Fh] BYREF
  DWORD dwOwnerSize; // [rsp+C8h] [rbp+77h] BYREF
  DWORD dwSaclSize; // [rsp+D0h] [rbp+7Fh] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    pSacl = 0;
    dwRevision[0] = 0;
    pControl = 0;
    if ( !GetSecurityDescriptorControl(v2, &pControl, dwRevision) )
      goto LABEL_9;
    if ( (pControl & 0x8000u) != 0 )
    {
      v4 = (void *)*((_QWORD *)this + 1);
      dwSaclSize = 0;
      dwDaclSize = 0;
      dwPrimaryGroupSize = 0;
      dwOwnerSize = 0;
      dwAbsoluteSecurityDescriptorSize = 0;
      MakeAbsoluteSD(
        v4,
        0,
        &dwAbsoluteSecurityDescriptorSize,
        0,
        &dwDaclSize,
        0,
        &dwSaclSize,
        0,
        &dwOwnerSize,
        0,
        &dwPrimaryGroupSize);
      if ( GetLastError() != 122 )
        ATL::AtlThrowLastWin32();
      v5 = malloc(dwAbsoluteSecurityDescriptorSize);
      if ( !v5 )
        goto LABEL_9;
      if ( dwOwnerSize )
      {
        pOwner = malloc(dwOwnerSize);
        if ( !pOwner )
          goto LABEL_9;
      }
      else
      {
        pOwner = 0;
      }
      if ( dwPrimaryGroupSize )
      {
        pPrimaryGroup = malloc(dwPrimaryGroupSize);
        if ( !pPrimaryGroup )
          goto LABEL_9;
      }
      else
      {
        pPrimaryGroup = 0;
      }
      if ( dwDaclSize )
      {
        v8 = (struct _ACL *)malloc(dwDaclSize);
        if ( !v8 )
          goto LABEL_9;
      }
      else
      {
        v8 = 0;
      }
      if ( dwSaclSize )
      {
        pSacl = (struct _ACL *)malloc(dwSaclSize);
        if ( !pSacl )
LABEL_9:
          ATL::PrivateAtlThrow(-2147467259);
      }
      if ( !MakeAbsoluteSD(
              *((PSECURITY_DESCRIPTOR *)this + 1),
              v5,
              &dwAbsoluteSecurityDescriptorSize,
              v8,
              &dwDaclSize,
              pSacl,
              &dwSaclSize,
              pOwner,
              &dwOwnerSize,
              pPrimaryGroup,
              &dwPrimaryGroupSize) )
      {
        Error = ATL::AtlHresultFromLastError();
        free(v5);
        free(pOwner);
        free(pPrimaryGroup);
        free(v8);
        free(pSacl);
        ATL::PrivateAtlThrow(Error);
      }
      (*(void (__fastcall **)(ATL::CSecurityDesc *))(*(_QWORD *)this + 8LL))(this);
      *((_QWORD *)this + 1) = v5;
    }
  }
}

```

## disassembly

```asm
0x1400068f0  mov     rax, rsp
0x1400068f3  push    rbp
0x1400068f4  push    rbx
0x1400068f5  lea     rbp, [rax-5Fh]
0x1400068f9  sub     rsp, 98h
0x140006900  mov     rbx, rcx
0x140006903  mov     rcx, [rcx+8]; pSecurityDescriptor
0x140006907  test    rcx, rcx
0x14000690a  jz      loc_140006AF9
0x140006910  mov     [rax-18h], rsi
0x140006914  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x140006918  mov     [rax-20h], rdi
0x14000691c  lea     rdx, [rbp+57h+pControl]; pControl
0x140006920  mov     [rax-28h], r12
0x140006924  xor     esi, esi
0x140006926  mov     [rax-30h], r14
0x14000692a  mov     [rax-38h], r15
0x14000692e  mov     [rbp+57h+dwRevision], esi
0x140006931  mov     [rbp+57h+pControl], si
0x140006935  call    cs:__imp_GetSecurityDescriptorControl
0x14000693b  test    eax, eax
0x14000693d  jz      loc_1400069E0
0x140006943  mov     eax, 8000h
0x140006948  test    [rbp+57h+pControl], ax
0x14000694c  jz      loc_140006AD7
0x140006952  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x140006956  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x14000695a  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x14000695f  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140006963  mov     [rsp+0A0h+pPrimaryGroup], rsi; pPrimaryGroup
0x140006968  lea     rax, [rbp+57h+dwOwnerSize]
0x14000696c  mov     [rsp+0A0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140006971  xor     r9d, r9d; pDacl
0x140006974  mov     [rsp+0A0h+pOwner], rsi; pOwner
0x140006979  lea     rax, [rbp+57h+dwSaclSize]
0x14000697d  mov     [rsp+0A0h+lpdwSaclSize], rax; lpdwSaclSize
0x140006982  xor     edx, edx; pAbsoluteSecurityDescriptor
0x140006984  lea     rax, [rbp+57h+dwDaclSize]
0x140006988  mov     [rsp+0A0h+pSacl], rsi; pSacl
0x14000698d  mov     [rsp+0A0h+lpdwDaclSize], rax; lpdwDaclSize
0x140006992  mov     [rbp+57h+dwSaclSize], esi
0x140006995  mov     [rbp+57h+dwDaclSize], esi
0x140006998  mov     [rbp+57h+dwPrimaryGroupSize], esi
0x14000699b  mov     [rbp+57h+dwOwnerSize], esi
0x14000699e  mov     [rbp+57h+dwAbsoluteSecurityDescriptorSize], esi
0x1400069a1  call    cs:__imp_MakeAbsoluteSD
0x1400069a7  call    cs:__imp_GetLastError
0x1400069ad  cmp     eax, 7Ah ; 'z'
0x1400069b0  jz      short loc_1400069B8
0x1400069b2  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x1400069b8  mov     ecx, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; Size
0x1400069bb  call    cs:__imp_malloc
0x1400069c1  mov     rdi, rax
0x1400069c4  test    rax, rax
0x1400069c7  jz      short loc_1400069E0
0x1400069c9  mov     eax, [rbp+57h+dwOwnerSize]
0x1400069cc  test    eax, eax
0x1400069ce  jz      short loc_1400069EB
0x1400069d0  mov     ecx, eax; Size
0x1400069d2  call    cs:__imp_malloc
0x1400069d8  mov     r12, rax
0x1400069db  test    rax, rax
0x1400069de  jnz     short loc_1400069EE
0x1400069e0  mov     ecx, 80004005h; int
0x1400069e5  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x1400069eb  mov     r12, rsi
0x1400069ee  mov     eax, [rbp+57h+dwPrimaryGroupSize]
0x1400069f1  test    eax, eax
0x1400069f3  jz      short loc_140006A07
0x1400069f5  mov     ecx, eax; Size
0x1400069f7  call    cs:__imp_malloc
0x1400069fd  mov     r15, rax
0x140006a00  test    rax, rax
0x140006a03  jnz     short loc_140006A0A
0x140006a05  jmp     short loc_1400069E0
0x140006a07  mov     r15, rsi
0x140006a0a  mov     eax, [rbp+57h+dwDaclSize]
0x140006a0d  test    eax, eax
0x140006a0f  jz      short loc_140006A23
0x140006a11  mov     ecx, eax; Size
0x140006a13  call    cs:__imp_malloc
0x140006a19  mov     r14, rax
0x140006a1c  test    rax, rax
0x140006a1f  jnz     short loc_140006A26
0x140006a21  jmp     short loc_1400069E0
0x140006a23  mov     r14, rsi
0x140006a26  mov     eax, [rbp+57h+dwSaclSize]
0x140006a29  test    eax, eax
0x140006a2b  jz      short loc_140006A3D
0x140006a2d  mov     ecx, eax; Size
0x140006a2f  call    cs:__imp_malloc
0x140006a35  mov     rsi, rax
0x140006a38  test    rax, rax
0x140006a3b  jz      short loc_1400069E0
0x140006a3d  mov     rcx, [rbx+8]; pSelfRelativeSecurityDescriptor
0x140006a41  lea     rax, [rbp+57h+dwPrimaryGroupSize]
0x140006a45  mov     [rsp+50h], rax; lpdwPrimaryGroupSize
0x140006a4a  lea     r8, [rbp+57h+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x140006a4e  mov     [rsp+0A0h+pPrimaryGroup], r15; pPrimaryGroup
0x140006a53  lea     rax, [rbp+57h+dwOwnerSize]
0x140006a57  mov     [rsp+0A0h+lpdwOwnerSize], rax; lpdwOwnerSize
0x140006a5c  mov     r9, r14; pDacl
0x140006a5f  mov     [rsp+0A0h+pOwner], r12; pOwner
0x140006a64  lea     rax, [rbp+57h+dwSaclSize]
0x140006a68  mov     [rsp+0A0h+lpdwSaclSize], rax; lpdwSaclSize
0x140006a6d  mov     rdx, rdi; pAbsoluteSecurityDescriptor
0x140006a70  lea     rax, [rbp+57h+dwDaclSize]
0x140006a74  mov     [rsp+0A0h+pSacl], rsi; pSacl
0x140006a79  mov     [rsp+0A0h+lpdwDaclSize], rax; lpdwDaclSize
0x140006a7e  call    cs:__imp_MakeAbsoluteSD
0x140006a84  test    eax, eax
0x140006a86  jnz     short loc_140006AC4
0x140006a88  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140006a8d  mov     rcx, rdi; Block
0x140006a90  mov     ebx, eax
0x140006a92  call    cs:__imp_free
0x140006a98  mov     rcx, r12; Block
0x140006a9b  call    cs:__imp_free
0x140006aa1  mov     rcx, r15; Block
0x140006aa4  call    cs:__imp_free
0x140006aaa  mov     rcx, r14; Block
0x140006aad  call    cs:__imp_free
0x140006ab3  mov     rcx, rsi; Block
0x140006ab6  call    cs:__imp_free
0x140006abc  mov     ecx, ebx; int
0x140006abe  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x140006ac4  mov     rax, [rbx]
0x140006ac7  mov     rcx, rbx
0x140006aca  mov     rax, [rax+8]
0x140006ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ad3  mov     [rbx+8], rdi
0x140006ad7  mov     r14, [rsp+0A0h+var_28]
0x140006adc  mov     r12, [rsp+0A0h+var_20]
0x140006ae4  mov     rdi, [rsp+0A0h+var_18]
0x140006aec  mov     r15, [rsp+0A0h+var_30]
0x140006af1  mov     rsi, [rsp+90h]
0x140006af9  add     rsp, 98h
0x140006b00  pop     rbx
0x140006b01  pop     rbp
0x140006b02  retn
```
