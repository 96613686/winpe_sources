# QueryDomainInfo(ushort * *,ushort * *,int *)

- ea: `0x1800127a0`
- end: `0x1800129c1`
- name: `?QueryDomainInfo@@YAKPEAPEAG0PEAH@Z`
- size: `545`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180014640`

## callees

- `0x18000179c`
- `0x1800127a0`
- `0x18002e468`

## import_xrefs

- `ADVAPI32!LsaClose` at `0x18001296b`
- `ADVAPI32!LsaClose` at `0x18001296b`
- `ADVAPI32!LsaFreeMemory` at `0x180012956`
- `ADVAPI32!LsaFreeMemory` at `0x180012956`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001281d`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18001281d`
- `ADVAPI32!LsaOpenPolicy` at `0x1800127fc`
- `ADVAPI32!LsaOpenPolicy` at `0x1800127fc`

## pseudocode

```c
__int64 __fastcall QueryDomainInfo(unsigned __int16 **a1, unsigned __int16 **a2, int *a3)
{
  unsigned int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rcx
  __int64 v11; // r8
  unsigned __int16 v12; // ax
  unsigned __int16 *v13; // rax
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rax
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // rcx
  __int64 v18; // r8
  unsigned __int16 v19; // ax
  unsigned __int16 *v20; // rax
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+80h] [rbp+30h] BYREF
  PVOID PolicyHandle; // [rsp+88h] [rbp+38h] BYREF

  PolicyHandle = 0;
  Buffer = 0;
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v6 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( !v6 )
  {
    v6 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( !v6 )
    {
      if ( a2 && *(_WORD *)Buffer )
      {
        v7 = ((unsigned __int64)*(unsigned __int16 *)Buffer >> 1) + 1;
        v8 = 2 * v7;
        if ( !is_mul_ok(v7, 2u) )
          v8 = -1;
        v9 = (unsigned __int16 *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
        *a2 = v9;
        v10 = v9;
        if ( !v9 )
          goto LABEL_12;
        v11 = *((_QWORD *)Buffer + 1) - (_QWORD)v9;
        while ( v7 != 1 )
        {
          v12 = *(unsigned __int16 *)((char *)v10 + v11);
          if ( !v12 )
            break;
          *v10 = v12;
          --v7;
          ++v10;
        }
        v13 = v10 - 1;
        if ( v7 )
          v13 = v10;
        *v13 = 0;
      }
      if ( a1 && *((_WORD *)Buffer + 8) )
      {
        v14 = ((unsigned __int64)*((unsigned __int16 *)Buffer + 8) >> 1) + 1;
        v15 = 2 * v14;
        if ( !is_mul_ok(v14, 2u) )
          v15 = -1;
        v16 = (unsigned __int16 *)operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
        *a1 = v16;
        v17 = v16;
        if ( !v16 )
        {
LABEL_12:
          v6 = 8;
          goto LABEL_35;
        }
        v18 = *((_QWORD *)Buffer + 3) - (_QWORD)v16;
        while ( v14 != 1 )
        {
          v19 = *(unsigned __int16 *)((char *)v17 + v18);
          if ( !v19 )
            break;
          *v17 = v19;
          --v14;
          ++v17;
        }
        v20 = v17 - 1;
        if ( v14 )
          v20 = v17;
        *v20 = 0;
      }
      if ( a3 )
        *a3 = *((_QWORD *)Buffer + 8) == 0;
      v6 = 0;
    }
  }
LABEL_35:
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v6 )
  {
    if ( a1 && *a1 )
    {
      operator delete(*a1);
      *a1 = 0;
    }
    if ( a2 && *a2 )
    {
      operator delete(*a2);
      *a2 = 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800127a0  mov     [rsp-28h+arg_10], rbx
0x1800127a5  mov     [rsp-28h+arg_18], rsi
0x1800127aa  push    rbp
0x1800127ab  push    rdi
0x1800127ac  push    r13
0x1800127ae  push    r14
0x1800127b0  push    r15
0x1800127b2  mov     rbp, rsp
0x1800127b5  sub     rsp, 50h
0x1800127b9  xor     r15d, r15d
0x1800127bc  mov     r14, r8
0x1800127bf  mov     [rbp+PolicyHandle], r15
0x1800127c3  mov     rdi, rdx
0x1800127c6  mov     [rbp+Buffer], r15
0x1800127ca  mov     rsi, rcx
0x1800127cd  test    rcx, rcx
0x1800127d0  jz      short loc_1800127D5
0x1800127d2  mov     [rcx], r15
0x1800127d5  test    rdi, rdi
0x1800127d8  jz      short loc_1800127DD
0x1800127da  mov     [rdx], r15
0x1800127dd  xorps   xmm0, xmm0
0x1800127e0  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800127e4  mov     r8d, 1; DesiredAccess
0x1800127ea  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800127ee  xor     ecx, ecx; SystemName
0x1800127f0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800127f4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800127f8  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800127fc  call    cs:__imp_LsaOpenPolicy
0x180012803  nop     dword ptr [rax+rax+00h]
0x180012808  mov     ebx, eax
0x18001280a  test    eax, eax
0x18001280c  jnz     loc_18001294D
0x180012812  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180012816  lea     r8, [rbp+Buffer]; Buffer
0x18001281a  lea     edx, [rax+0Ch]; InformationClass
0x18001281d  call    cs:__imp_LsaQueryInformationPolicy
0x180012824  nop     dword ptr [rax+rax+00h]
0x180012829  mov     ebx, eax
0x18001282b  test    eax, eax
0x18001282d  jnz     loc_18001294D
0x180012833  or      r13, 0FFFFFFFFFFFFFFFFh
0x180012837  test    rdi, rdi
0x18001283a  jz      short loc_1800128B7
0x18001283c  mov     rax, [rbp+Buffer]
0x180012840  cmp     [rax], r15w
0x180012844  jbe     short loc_1800128B7
0x180012846  movzx   ebx, word ptr [rax]
0x180012849  lea     eax, [r13+3]
0x18001284d  shr     rbx, 1
0x180012850  inc     rbx
0x180012853  mul     rbx
0x180012856  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001285d  cmovo   rax, r13
0x180012861  mov     rcx, rax; unsigned __int64
0x180012864  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012869  mov     [rdi], rax
0x18001286c  mov     rcx, rax
0x18001286f  test    rax, rax
0x180012872  jnz     short loc_18001287E
0x180012874  mov     ebx, 8
0x180012879  jmp     loc_18001294D
0x18001287e  mov     rax, [rbp+Buffer]
0x180012882  mov     r8, [rax+8]
0x180012886  sub     r8, rcx
0x180012889  lea     rdx, [rbx-1]
0x18001288d  test    rdx, rdx
0x180012890  jz      short loc_1800128A8
0x180012892  movzx   eax, word ptr [r8+rcx]
0x180012897  test    ax, ax
0x18001289a  jz      short loc_1800128A8
0x18001289c  mov     [rcx], ax
0x18001289f  mov     rbx, rdx
0x1800128a2  add     rcx, 2
0x1800128a6  jmp     short loc_180012889
0x1800128a8  test    rbx, rbx
0x1800128ab  lea     rax, [rcx-2]
0x1800128af  cmovnz  rax, rcx
0x1800128b3  mov     [rax], r15w
0x1800128b7  test    rsi, rsi
0x1800128ba  jz      short loc_180012934
0x1800128bc  mov     rax, [rbp+Buffer]
0x1800128c0  cmp     [rax+10h], r15w
0x1800128c5  jbe     short loc_180012934
0x1800128c7  movzx   ebx, word ptr [rax+10h]
0x1800128cb  mov     eax, 2
0x1800128d0  shr     rbx, 1
0x1800128d3  inc     rbx
0x1800128d6  mul     rbx
0x1800128d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800128e0  cmovo   rax, r13
0x1800128e4  mov     rcx, rax; unsigned __int64
0x1800128e7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800128ec  mov     [rsi], rax
0x1800128ef  mov     rcx, rax
0x1800128f2  test    rax, rax
0x1800128f5  jz      loc_180012874
0x1800128fb  mov     rax, [rbp+Buffer]
0x1800128ff  mov     r8, [rax+18h]
0x180012903  sub     r8, rcx
0x180012906  lea     rdx, [rbx-1]
0x18001290a  test    rdx, rdx
0x18001290d  jz      short loc_180012925
0x18001290f  movzx   eax, word ptr [r8+rcx]
0x180012914  test    ax, ax
0x180012917  jz      short loc_180012925
0x180012919  mov     [rcx], ax
0x18001291c  mov     rbx, rdx
0x18001291f  add     rcx, 2
0x180012923  jmp     short loc_180012906
0x180012925  test    rbx, rbx
0x180012928  lea     rax, [rcx-2]
0x18001292c  cmovnz  rax, rcx
0x180012930  mov     [rax], r15w
0x180012934  test    r14, r14
0x180012937  jz      short loc_18001294A
0x180012939  mov     rax, [rbp+Buffer]
0x18001293d  mov     ecx, r15d
0x180012940  cmp     [rax+40h], r15
0x180012944  setz    cl
0x180012947  mov     [r14], ecx
0x18001294a  mov     ebx, r15d
0x18001294d  mov     rcx, [rbp+Buffer]; Buffer
0x180012951  test    rcx, rcx
0x180012954  jz      short loc_180012962
0x180012956  call    cs:__imp_LsaFreeMemory
0x18001295d  nop     dword ptr [rax+rax+00h]
0x180012962  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180012966  test    rcx, rcx
0x180012969  jz      short loc_180012977
0x18001296b  call    cs:__imp_LsaClose
0x180012972  nop     dword ptr [rax+rax+00h]
0x180012977  test    ebx, ebx
0x180012979  jz      short loc_1800129A5
0x18001297b  test    rsi, rsi
0x18001297e  jz      short loc_180012990
0x180012980  mov     rcx, [rsi]; lpMem
0x180012983  test    rcx, rcx
0x180012986  jz      short loc_180012990
0x180012988  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001298d  mov     [rsi], r15
0x180012990  test    rdi, rdi
0x180012993  jz      short loc_1800129A5
0x180012995  mov     rcx, [rdi]; lpMem
0x180012998  test    rcx, rcx
0x18001299b  jz      short loc_1800129A5
0x18001299d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800129a2  mov     [rdi], r15
0x1800129a5  lea     r11, [rsp+50h+var_s0]
0x1800129aa  mov     eax, ebx
0x1800129ac  mov     rbx, [r11+40h]
0x1800129b0  mov     rsi, [r11+48h]
0x1800129b4  mov     rsp, r11
0x1800129b7  pop     r15
0x1800129b9  pop     r14
0x1800129bb  pop     r13
0x1800129bd  pop     rdi
0x1800129be  pop     rbp
0x1800129bf  retn
```
