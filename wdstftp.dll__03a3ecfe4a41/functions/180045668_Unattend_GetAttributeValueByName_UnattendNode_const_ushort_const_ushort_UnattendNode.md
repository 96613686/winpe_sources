# Unattend::GetAttributeValueByName(UnattendNode const &,ushort const *,ushort * *,UnattendNode *)

- ea: `0x180045668`
- end: `0x180045800`
- name: `?GetAttributeValueByName@Unattend@@QEAAJAEBVUnattendNode@@PEBGPEAPEAGPEAV2@@Z`
- size: `408`
- prototype: `__int64 __usercall@<rax>(Unattend *__hidden this@<rcx>, const struct UnattendNode *@<rdx>, PCNZWCH lpString1@<r8>, unsigned __int16 **@<r9>, struct UnattendNode *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180043710`

## callees

- `0x18004537c`
- `0x180045448`
- `0x180045668`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180045772`
- `KERNEL32!HeapFree` at `0x1800457a3`
- `KERNEL32!HeapFree` at `0x180045772`
- `KERNEL32!HeapFree` at `0x1800457a3`
- `KERNEL32!GetProcessHeap` at `0x18004575e`
- `KERNEL32!GetProcessHeap` at `0x18004578f`
- `KERNEL32!GetProcessHeap` at `0x18004575e`
- `KERNEL32!GetProcessHeap` at `0x18004578f`
- `KERNEL32!CompareStringW` at `0x180045719`
- `KERNEL32!CompareStringW` at `0x180045719`

## pseudocode

```c
__int64 __fastcall Unattend::GetAttributeValueByName(
        Unattend *this,
        const struct UnattendNode *a2,
        PCNZWCH lpString1,
        unsigned __int16 **a4,
        struct UnattendNode *a5)
{
  char v5; // r12
  const struct UnattendNode *v8; // rdi
  Unattend *v9; // r15
  int AttributeInfo; // ebx
  unsigned __int64 v11; // rsi
  WCHAR *v12; // r15
  unsigned __int16 *v13; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v15; // rax
  unsigned __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  PCNZWCH lpString2; // [rsp+38h] [rbp-18h] BYREF
  __int128 v19; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v22; // [rsp+A8h] [rbp+58h] BYREF

  v5 = 0;
  v8 = a2;
  v9 = this;
  if ( !a4 || !lpString1 )
    return 2147942487LL;
  AttributeInfo = Unattend::CountAttributes(this, a2, &v17);
  if ( AttributeInfo >= 0 )
  {
    v11 = 0;
    do
    {
      if ( v11 >= v17 )
        break;
      AttributeInfo = Unattend::GetAttributeInfo(
                        v9,
                        v8,
                        v11,
                        (unsigned __int16 **)&lpString2,
                        &v22,
                        (struct UnattendNode *)&v19);
      if ( AttributeInfo >= 0 )
      {
        v12 = (WCHAR *)lpString2;
        if ( CompareStringW(0x409u, 1u, lpString1, -1, lpString2, -1) == 2 )
        {
          v5 = 1;
          *a4 = v22;
          v13 = 0;
          v22 = 0;
          if ( a5 )
            *(_OWORD *)a5 = v19;
          v11 = v17;
          AttributeInfo = 0;
        }
        else
        {
          v13 = v22;
        }
        if ( v12 )
        {
          ProcessHeap = GetProcessHeap();
          if ( HeapFree(ProcessHeap, 0, v12) )
            v12 = 0;
          lpString2 = v12;
        }
        if ( v13 )
        {
          v15 = GetProcessHeap();
          if ( HeapFree(v15, 0, v13) )
            v13 = 0;
          v22 = v13;
        }
        v9 = this;
        v8 = a2;
      }
      ++v11;
    }
    while ( AttributeInfo >= 0 );
    if ( !v5 && AttributeInfo >= 0 )
    {
      AttributeInfo = 1;
      *a4 = 0;
    }
  }
  return (unsigned int)AttributeInfo;
}

```

## disassembly

```asm
0x180045668  mov     [rsp-38h+arg_10], rbx
0x18004566d  mov     [rsp-38h+arg_8], rdx
0x180045672  mov     [rsp-38h+arg_0], rcx
0x180045677  push    rbp
0x180045678  push    rsi
0x180045679  push    rdi
0x18004567a  push    r12
0x18004567c  push    r13
0x18004567e  push    r14
0x180045680  push    r15
0x180045682  mov     rbp, rsp
0x180045685  sub     rsp, 50h
0x180045689  xor     r12b, r12b
0x18004568c  mov     r14, r9
0x18004568f  mov     r13, r8
0x180045692  mov     rdi, rdx
0x180045695  mov     r15, rcx
0x180045698  test    r9, r9
0x18004569b  jz      loc_1800457E3
0x1800456a1  test    r8, r8
0x1800456a4  jz      loc_1800457E3
0x1800456aa  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1800456ae  call    ?CountAttributes@Unattend@@QEAAJAEBVUnattendNode@@AEA_K@Z; Unattend::CountAttributes(UnattendNode const &,unsigned __int64 &)
0x1800456b3  xor     ecx, ecx
0x1800456b5  mov     ebx, eax
0x1800456b7  test    eax, eax
0x1800456b9  js      loc_1800457DF
0x1800456bf  mov     esi, ecx
0x1800456c1  cmp     rsi, [rbp+var_20]
0x1800456c5  jnb     loc_1800457CE
0x1800456cb  lea     rax, [rbp+var_10]
0x1800456cf  mov     r8, rsi; unsigned __int64
0x1800456d2  mov     qword ptr [rsp+50h+cchCount2], rax; struct UnattendNode *
0x1800456d7  lea     r9, [rbp+var_18]; unsigned __int16 **
0x1800456db  lea     rax, [rbp+arg_18]
0x1800456df  mov     rdx, rdi; struct UnattendNode *
0x1800456e2  mov     rcx, r15; this
0x1800456e5  mov     [rsp+50h+lpString2], rax; unsigned __int16 **
0x1800456ea  call    ?GetAttributeInfo@Unattend@@QEAAJAEBVUnattendNode@@_KPEAPEAG2PEAV2@@Z; Unattend::GetAttributeInfo(UnattendNode const &,unsigned __int64,ushort * *,ushort * *,UnattendNode *)
0x1800456ef  xor     ecx, ecx
0x1800456f1  mov     ebx, eax
0x1800456f3  test    eax, eax
0x1800456f5  js      loc_1800457C3
0x1800456fb  mov     r15, [rbp+var_18]
0x1800456ff  lea     edx, [rcx+1]; dwCmpFlags
0x180045702  or      eax, 0FFFFFFFFh
0x180045705  mov     r8, r13; lpString1
0x180045708  mov     [rsp+50h+cchCount2], eax; cchCount2
0x18004570c  mov     r9d, eax; cchCount1
0x18004570f  mov     ecx, 409h; Locale
0x180045714  mov     [rsp+50h+lpString2], r15; lpString2
0x180045719  call    cs:__imp_CompareStringW
0x180045720  nop     dword ptr [rax+rax+00h]
0x180045725  xor     ecx, ecx
0x180045727  cmp     eax, 2
0x18004572a  jnz     short loc_180045755
0x18004572c  mov     rax, [rbp+arg_18]
0x180045730  mov     r12b, 1
0x180045733  mov     [r14], rax
0x180045736  mov     edi, ecx
0x180045738  mov     rax, [rbp+arg_20]
0x18004573c  mov     [rbp+arg_18], rcx
0x180045740  test    rax, rax
0x180045743  jz      short loc_18004574D
0x180045745  movups  xmm0, [rbp+var_10]
0x180045749  movdqu  xmmword ptr [rax], xmm0
0x18004574d  mov     rsi, [rbp+var_20]
0x180045751  mov     ebx, ecx
0x180045753  jmp     short loc_180045759
0x180045755  mov     rdi, [rbp+arg_18]
0x180045759  test    r15, r15
0x18004575c  jz      short loc_18004578A
0x18004575e  call    cs:__imp_GetProcessHeap
0x180045765  nop     dword ptr [rax+rax+00h]
0x18004576a  mov     r8, r15; lpMem
0x18004576d  xor     edx, edx; dwFlags
0x18004576f  mov     rcx, rax; hHeap
0x180045772  call    cs:__imp_HeapFree
0x180045779  nop     dword ptr [rax+rax+00h]
0x18004577e  xor     ecx, ecx
0x180045780  test    eax, eax
0x180045782  cmovnz  r15, rcx
0x180045786  mov     [rbp+var_18], r15
0x18004578a  test    rdi, rdi
0x18004578d  jz      short loc_1800457BB
0x18004578f  call    cs:__imp_GetProcessHeap
0x180045796  nop     dword ptr [rax+rax+00h]
0x18004579b  mov     r8, rdi; lpMem
0x18004579e  xor     edx, edx; dwFlags
0x1800457a0  mov     rcx, rax; hHeap
0x1800457a3  call    cs:__imp_HeapFree
0x1800457aa  nop     dword ptr [rax+rax+00h]
0x1800457af  xor     ecx, ecx
0x1800457b1  test    eax, eax
0x1800457b3  cmovnz  rdi, rcx
0x1800457b7  mov     [rbp+arg_18], rdi
0x1800457bb  mov     r15, [rbp+arg_0]
0x1800457bf  mov     rdi, [rbp+arg_8]
0x1800457c3  inc     rsi
0x1800457c6  test    ebx, ebx
0x1800457c8  jns     loc_1800456C1
0x1800457ce  test    r12b, r12b
0x1800457d1  jnz     short loc_1800457DF
0x1800457d3  test    ebx, ebx
0x1800457d5  js      short loc_1800457DF
0x1800457d7  mov     ebx, 1
0x1800457dc  mov     [r14], rcx
0x1800457df  mov     eax, ebx
0x1800457e1  jmp     short loc_1800457E8
0x1800457e3  mov     eax, 80070057h
0x1800457e8  mov     rbx, [rsp+50h+arg_10]
0x1800457f0  add     rsp, 50h
0x1800457f4  pop     r15
0x1800457f6  pop     r14
0x1800457f8  pop     r13
0x1800457fa  pop     r12
0x1800457fc  pop     rdi
0x1800457fd  pop     rsi
0x1800457fe  pop     rbp
0x1800457ff  retn
```
