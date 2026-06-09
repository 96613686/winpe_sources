# SAL2::CreateACL(SAL2::CW32Sid *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * *,_SECURITY_DESCRIPTOR * *)

- ea: `0x180085360`
- end: `0x1800854f7`
- name: `?CreateACL@SAL2@@YAKPEAVCW32Sid@1@W4_ACCESS_MODE@@K1KPEAPEAU_ACL@@PEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `407`
- prototype: `unsigned int __fastcall(SAL2 *__hidden this, struct SAL2::CW32Sid *, enum _ACCESS_MODE, unsigned int, enum _ACCESS_MODE, PACL *NewAcl, struct _ACL **, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180080a48`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x18000256c`
- `0x180060e40`
- `0x180085360`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800854db`
- `KERNEL32!GetLastError` at `0x1800854db`
- `KERNEL32!LocalAlloc` at `0x1800854a7`
- `KERNEL32!LocalAlloc` at `0x1800854a7`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800854bb`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800854bb`
- `ADVAPI32!SetEntriesInAclW` at `0x180085491`
- `ADVAPI32!SetEntriesInAclW` at `0x180085491`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800854d1`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800854d1`

## pseudocode

```c
__int64 __fastcall SAL2::CreateACL(
        SAL2 *this,
        struct SAL2::CW32Sid *a2,
        struct _SECURITY_DESCRIPTOR *a3,
        __int64 a4,
        enum _ACCESS_MODE a5,
        PACL *NewAcl,
        struct _ACL **a7)
{
  unsigned __int64 v7; // rbp
  int v8; // r12d
  char *v10; // rdi
  DWORD LastError; // ebx
  unsigned __int64 v12; // rdx
  char *v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rdx
  struct _ACL *v19; // rax

  v7 = *((unsigned int *)this + 6);
  v8 = (int)a3;
  *NewAcl = 0;
  *a7 = 0;
  if ( !*((_DWORD *)this + 6) )
  {
    v10 = 0;
    LastError = 87;
LABEL_3:
    SBECoreUtil::FreeSecurityDescriptors((SBECoreUtil *)*NewAcl, *a7, a3);
    *NewAcl = 0;
    *a7 = 0;
    goto LABEL_4;
  }
  v14 = (char *)operator new[](saturated_mul(v7, 0x30u));
  v10 = v14;
  if ( !v14 )
  {
    LastError = 8;
    goto LABEL_3;
  }
  memset_0(v14, 0, 48 * v7);
  *(_DWORD *)v10 = v8;
  *(_QWORD *)(v10 + 4) = 2;
  *((_DWORD *)v10 + 7) = 0;
  *((_DWORD *)v10 + 8) = 5;
  *((_QWORD *)v10 + 5) = **((_QWORD **)this + 2);
  v15 = 1;
  if ( (unsigned int)v7 > 1 )
  {
    v16 = 1;
    do
    {
      ++v15;
      v17 = 6 * v16;
      *(_DWORD *)&v10[8 * v17] = a5;
      *(_QWORD *)&v10[8 * v17 + 4] = 2;
      *(_DWORD *)&v10[8 * v17 + 28] = 0;
      *(_DWORD *)&v10[8 * v17 + 32] = 2;
      v18 = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v16++);
      *(_QWORD *)&v10[8 * v17 + 40] = v18;
    }
    while ( v15 < (unsigned int)v7 );
  }
  LastError = SetEntriesInAclW(v7, (PEXPLICIT_ACCESS_W)v10, 0, NewAcl);
  if ( LastError )
    goto LABEL_3;
  v19 = (struct _ACL *)LocalAlloc(0x40u, 0x28u);
  *a7 = v19;
  if ( v19 && InitializeSecurityDescriptor(v19, 1u) && SetSecurityDescriptorDacl(*a7, 1, *NewAcl, 0) )
  {
    LastError = 0;
    goto LABEL_4;
  }
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_3;
LABEL_4:
  operator delete(v10, v12);
  return LastError;
}

```

## disassembly

```asm
0x180085360  push    rbx
0x180085362  push    rbp
0x180085363  push    rsi
0x180085364  push    rdi
0x180085365  push    r12
0x180085367  push    r14
0x180085369  push    r15
0x18008536b  sub     rsp, 20h
0x18008536f  mov     ebp, [rcx+18h]
0x180085372  mov     r12d, r8d
0x180085375  mov     r14, [rsp+58h+NewAcl]
0x18008537d  mov     rbx, rcx
0x180085380  mov     rsi, [rsp+58h+arg_30]
0x180085388  mov     qword ptr [r14], 0
0x18008538f  mov     qword ptr [rsi], 0
0x180085396  cmp     dword ptr [rcx+18h], 0
0x18008539a  jnz     short loc_1800853D3
0x18008539c  xor     edi, edi
0x18008539e  lea     ebx, [rdi+57h]
0x1800853a1  mov     rdx, [rsi]; struct _ACL *
0x1800853a4  mov     rcx, [r14]; this
0x1800853a7  call    ?FreeSecurityDescriptors@SBECoreUtil@@YAXPEAU_ACL@@PEAU_SECURITY_DESCRIPTOR@@@Z; SBECoreUtil::FreeSecurityDescriptors(_ACL *,_SECURITY_DESCRIPTOR *)
0x1800853ac  mov     qword ptr [r14], 0
0x1800853b3  mov     qword ptr [rsi], 0
0x1800853ba  mov     rcx, rdi; void *
0x1800853bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800853c2  mov     eax, ebx
0x1800853c4  add     rsp, 20h
0x1800853c8  pop     r15
0x1800853ca  pop     r14
0x1800853cc  pop     r12
0x1800853ce  pop     rdi
0x1800853cf  pop     rsi
0x1800853d0  pop     rbp
0x1800853d1  pop     rbx
0x1800853d2  retn
0x1800853d3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800853da  mov     eax, 30h ; '0'
0x1800853df  mul     rbp
0x1800853e2  cmovb   rax, rcx
0x1800853e6  mov     rcx, rax; unsigned __int64
0x1800853e9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800853ee  mov     rdi, rax
0x1800853f1  test    rax, rax
0x1800853f4  jnz     short loc_1800853FB
0x1800853f6  lea     ebx, [rax+8]
0x1800853f9  jmp     short loc_1800853A1
0x1800853fb  lea     r8, ds:0[rbp*2]
0x180085403  xor     edx, edx; Val
0x180085405  add     r8, rbp
0x180085408  mov     rcx, rdi; void *
0x18008540b  shl     r8, 4; Size
0x18008540f  call    memset_0
0x180085414  mov     r11d, 2
0x18008541a  mov     [rdi], r12d
0x18008541d  mov     [rdi+4], r11
0x180085421  mov     dword ptr [rdi+1Ch], 0
0x180085428  mov     dword ptr [rdi+20h], 5
0x18008542f  mov     rax, [rbx+10h]
0x180085433  lea     r15d, [r11-1]
0x180085437  mov     rcx, [rax]
0x18008543a  mov     [rdi+28h], rcx
0x18008543e  mov     ecx, r15d
0x180085441  cmp     ebp, r15d
0x180085444  jbe     short loc_180085486
0x180085446  mov     r10d, [rsp+58h+arg_20]
0x18008544e  mov     r9d, r15d
0x180085451  lea     r8, [r9+r9*2]
0x180085455  add     ecx, r15d
0x180085458  add     r8, r8
0x18008545b  mov     [rdi+r8*8], r10d
0x18008545f  mov     [rdi+r8*8+4], r11
0x180085464  mov     dword ptr [rdi+r8*8+1Ch], 0
0x18008546d  mov     [rdi+r8*8+20h], r11d
0x180085472  mov     rax, [rbx+10h]
0x180085476  mov     rdx, [rax+r9*8]
0x18008547a  add     r9, r15
0x18008547d  mov     [rdi+r8*8+28h], rdx
0x180085482  cmp     ecx, ebp
0x180085484  jb      short loc_180085451
0x180085486  mov     r9, r14; NewAcl
0x180085489  xor     r8d, r8d; OldAcl
0x18008548c  mov     rdx, rdi; pListOfExplicitEntries
0x18008548f  mov     ecx, ebp; cCountOfExplicitEntries
0x180085491  call    cs:__imp_SetEntriesInAclW
0x180085497  mov     ebx, eax
0x180085499  test    eax, eax
0x18008549b  jnz     loc_1800853A1
0x1800854a1  lea     edx, [rax+28h]; uBytes
0x1800854a4  lea     ecx, [rax+40h]; uFlags
0x1800854a7  call    cs:__imp_LocalAlloc
0x1800854ad  mov     [rsi], rax
0x1800854b0  test    rax, rax
0x1800854b3  jz      short loc_1800854DB
0x1800854b5  mov     edx, r15d; dwRevision
0x1800854b8  mov     rcx, rax; pSecurityDescriptor
0x1800854bb  call    cs:__imp_InitializeSecurityDescriptor
0x1800854c1  test    eax, eax
0x1800854c3  jz      short loc_1800854DB
0x1800854c5  mov     r8, [r14]; pDacl
0x1800854c8  xor     r9d, r9d; bDaclDefaulted
0x1800854cb  mov     rcx, [rsi]; pSecurityDescriptor
0x1800854ce  mov     edx, r15d; bDaclPresent
0x1800854d1  call    cs:__imp_SetSecurityDescriptorDacl
0x1800854d7  test    eax, eax
0x1800854d9  jnz     short loc_1800854F0
0x1800854db  call    cs:__imp_GetLastError
0x1800854e1  mov     ebx, eax
0x1800854e3  test    eax, eax
0x1800854e5  jz      loc_1800853BA
0x1800854eb  jmp     loc_1800853A1
0x1800854f0  xor     ebx, ebx
0x1800854f2  jmp     loc_1800853BA
```
