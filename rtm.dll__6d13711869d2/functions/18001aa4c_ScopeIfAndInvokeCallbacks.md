# ScopeIfAndInvokeCallbacks

- ea: `0x18001aa4c`
- end: `0x18001acfe`
- name: `ScopeIfAndInvokeCallbacks`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180019de0`

## callees

- `0x180019a1c`
- `0x18001aa4c`
- `0x18001b548`
- `0x18001dcbc`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001abd8`
- `KERNEL32!HeapFree` at `0x18001abd8`

## string_xrefs

- `0x18001aae4`: `Protocol (%d, %d) not present for interface %d`
- `0x18001ab84`: `Interface (%d, %d) already present in the scoped list for (%x, %x)`
- `0x18001ac2f`: `Invoked Local Leave Alert for protocol %x, %x`

## pseudocode

```c
int __fastcall ScopeIfAndInvokeCallbacks(__int64 a1, _DWORD *a2, __int64 *a3)
{
  __int64 ProtocolEntry; // rax
  unsigned int v7; // edx
  unsigned int v8; // r8d
  __int64 v9; // rsi
  int v10; // eax
  __int64 v11; // rax
  __int64 **v12; // rcx
  unsigned int v13; // r8d
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 *v16; // rax
  __int64 **v17; // rcx
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  char v24[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v21 = 0;
  v22 = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, *((unsigned int *)a3 + 6), *((unsigned int *)a3 + 7));
  v9 = ProtocolEntry;
  if ( !ProtocolEntry )
  {
    if ( qword_18002B8A8 )
    {
      v10 = *((_DWORD *)a3 + 4);
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"Protocol (%d, %d) not present for interface %d", v7, v8, v10);
      LODWORD(ProtocolEntry) = ((__int64 (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(
                                 gMgmEtwContext,
                                 qword_18002B8A8,
                                 &v23);
    }
    return ProtocolEntry;
  }
  v11 = *a3;
  if ( a3 != (__int64 *)*a3 )
  {
    if ( *(__int64 **)(v11 + 8) != a3 )
      goto LABEL_15;
    v12 = (__int64 **)a3[1];
    if ( *v12 != a3 )
      goto LABEL_15;
    *v12 = (__int64 *)v11;
    *(_QWORD *)(v11 + 8) = v12;
    *a3 = (__int64)a3;
    a3[1] = (__int64)a3;
  }
  if ( (unsigned int)FindOutInterfaceEntry(
                       (int)a2 + 64,
                       *((_DWORD *)a3 + 4),
                       *((_DWORD *)a3 + 5),
                       *((_DWORD *)a3 + 6),
                       *((_DWORD *)a3 + 7),
                       (__int64)&v21,
                       (__int64)&v22) )
  {
    if ( qword_18002B8A8 )
    {
      LODWORD(v20) = *(_DWORD *)(a1 + 32);
      v14 = v13;
      v15 = *((unsigned int *)a3 + 4);
      LODWORD(v19) = a2[26];
      LOWORD(v23) = 0;
      FormatRRASErrorString(
        &v23,
        L"Interface (%d, %d) already present in the scoped list for (%x, %x)",
        v15,
        v14,
        v19,
        v20);
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v23);
    }
    LODWORD(ProtocolEntry) = HeapFree(hHeap, 0, a3);
    return ProtocolEntry;
  }
  v16 = v22;
  if ( !v22 )
    v16 = (__int64 *)(a2 + 16);
  v17 = (__int64 **)v16[1];
  if ( *v17 != v16 )
LABEL_15:
    __fastfail(3u);
  *a3 = (__int64)v16;
  a3[1] = (__int64)v17;
  *v17 = a3;
  v16[1] = (__int64)a3;
  if ( *((__int16 *)a3 + 17) < 0 && *(_DWORD *)(v9 + 16) != 10 && *(_QWORD *)(v9 + 88) )
  {
    if ( qword_18002B8A8 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(
        &v23,
        L"Invoked Local Leave Alert for protocol %x, %x",
        *(unsigned int *)(v9 + 16),
        *(unsigned int *)(v9 + 20));
      ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v23);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(v9 + 88))(
      (unsigned int)a2[26],
      (unsigned int)a2[27],
      *(unsigned int *)(a1 + 32),
      *(unsigned int *)(a1 + 36),
      *((_DWORD *)a3 + 4),
      *((_DWORD *)a3 + 5));
  }
  LODWORD(ProtocolEntry) = FindOutInterfaceEntry(
                             (int)a2 + 48,
                             *((_DWORD *)a3 + 4),
                             *((_DWORD *)a3 + 5),
                             *((_DWORD *)a3 + 6),
                             *((_DWORD *)a3 + 7),
                             (__int64)&v21,
                             (__int64)&v22);
  if ( v21 )
  {
    --a2[10];
    LODWORD(ProtocolEntry) = InvokePruneAlertCallbacks(a1, (_DWORD)a2, *((_DWORD *)a3 + 4), *((_DWORD *)a3 + 5), v9);
  }
  return ProtocolEntry;
}

```

## disassembly

```asm
0x18001aa4c  push    rbp
0x18001aa4e  push    rbx
0x18001aa4f  push    rsi
0x18001aa50  push    rdi
0x18001aa51  push    r12
0x18001aa53  push    r14
0x18001aa55  push    r15
0x18001aa57  lea     rbp, [rsp-760h]
0x18001aa5f  sub     rsp, 860h
0x18001aa66  mov     rax, cs:__security_cookie
0x18001aa6d  xor     rax, rsp
0x18001aa70  mov     [rbp+790h+var_40], rax
0x18001aa77  xor     r12d, r12d
0x18001aa7a  mov     rbx, r8
0x18001aa7d  mov     rdi, rdx
0x18001aa80  mov     [rsp+890h+var_850], r12d
0x18001aa85  mov     r14, rcx
0x18001aa88  mov     [rsp+890h+var_848], r12
0x18001aa8d  xor     edx, edx; Val
0x18001aa8f  mov     [rsp+890h+var_840], r12d
0x18001aa94  mov     r8d, 7FCh; Size
0x18001aa9a  lea     rcx, [rsp+890h+var_83C]; void *
0x18001aa9f  call    memset_0
0x18001aaa4  mov     r8d, [rbx+1Ch]
0x18001aaa8  lea     rcx, qword_18002B9A8
0x18001aaaf  mov     edx, [rbx+18h]
0x18001aab2  call    GetProtocolEntry
0x18001aab7  mov     rsi, rax
0x18001aaba  test    rax, rax
0x18001aabd  jnz     short loc_18001AB14
0x18001aabf  cmp     cs:qword_18002B8A8, r12
0x18001aac6  jz      loc_18001ACDD
0x18001aacc  mov     eax, [rbx+10h]
0x18001aacf  lea     rcx, [rsp+890h+var_840]
0x18001aad4  mov     r9d, r8d
0x18001aad7  mov     word ptr [rsp+890h+var_840], r12w
0x18001aadd  mov     r8d, edx
0x18001aae0  mov     dword ptr [rsp+890h+var_870], eax
0x18001aae4  lea     rdx, aProtocolDDNotP; "Protocol (%d, %d) not present for inter"...
0x18001aaeb  call    FormatRRASErrorString
0x18001aaf0  mov     rdx, cs:qword_18002B8A8
0x18001aaf7  lea     r8, [rsp+890h+var_840]
0x18001aafc  mov     rcx, cs:gMgmEtwContext
0x18001ab03  mov     rax, cs:gMgmTemplateFunc
0x18001ab0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab0f  jmp     loc_18001ACDD
0x18001ab14  mov     rax, [rbx]
0x18001ab17  cmp     rbx, rax
0x18001ab1a  jz      short loc_18001AB41
0x18001ab1c  cmp     [rax+8], rbx
0x18001ab20  jnz     loc_18001ABF8
0x18001ab26  mov     rcx, [rbx+8]
0x18001ab2a  cmp     [rcx], rbx
0x18001ab2d  jnz     loc_18001ABF8
0x18001ab33  mov     [rcx], rax
0x18001ab36  mov     [rax+8], rcx
0x18001ab3a  mov     [rbx], rbx
0x18001ab3d  mov     [rbx+8], rbx
0x18001ab41  mov     r9d, [rbx+18h]
0x18001ab45  lea     rax, [rsp+890h+var_848]
0x18001ab4a  mov     edx, [rbx+10h]
0x18001ab4d  lea     r15, [rdi+40h]
0x18001ab51  mov     r8d, [rbx+14h]
0x18001ab55  mov     rcx, r15
0x18001ab58  mov     [rsp+890h+var_860], rax
0x18001ab5d  lea     rax, [rsp+890h+var_850]
0x18001ab62  mov     [rsp+890h+var_868], rax
0x18001ab67  mov     eax, [rbx+1Ch]
0x18001ab6a  mov     dword ptr [rsp+890h+var_870], eax
0x18001ab6e  call    FindOutInterfaceEntry
0x18001ab73  test    eax, eax
0x18001ab75  jz      short loc_18001ABE3
0x18001ab77  cmp     cs:qword_18002B8A8, r12
0x18001ab7e  jz      short loc_18001ABCC
0x18001ab80  mov     eax, [r14+20h]
0x18001ab84  lea     rdx, aInterfaceDDAlr; "Interface (%d, %d) already present in t"...
0x18001ab8b  mov     dword ptr [rsp+890h+var_868], eax
0x18001ab8f  lea     rcx, [rsp+890h+var_840]
0x18001ab94  mov     eax, [rdi+68h]
0x18001ab97  mov     r9d, r8d
0x18001ab9a  mov     r8d, [rbx+10h]
0x18001ab9e  mov     dword ptr [rsp+890h+var_870], eax
0x18001aba2  mov     word ptr [rsp+890h+var_840], r12w
0x18001aba8  call    FormatRRASErrorString
0x18001abad  mov     rdx, cs:qword_18002B8A8
0x18001abb4  lea     r8, [rsp+890h+var_840]
0x18001abb9  mov     rcx, cs:gMgmEtwContext
0x18001abc0  mov     rax, cs:gMgmTemplateFunc
0x18001abc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abcc  mov     rcx, cs:hHeap; hHeap
0x18001abd3  mov     r8, rbx; lpMem
0x18001abd6  xor     edx, edx; dwFlags
0x18001abd8  call    cs:__imp_HeapFree
0x18001abde  jmp     loc_18001ACDD
0x18001abe3  mov     rax, [rsp+890h+var_848]
0x18001abe8  test    rax, rax
0x18001abeb  cmovz   rax, r15
0x18001abef  mov     rcx, [rax+8]
0x18001abf3  cmp     [rcx], rax
0x18001abf6  jz      short loc_18001ABFF
0x18001abf8  mov     ecx, 3
0x18001abfd  int     29h; Win8: RtlFailFast(ecx)
0x18001abff  mov     [rbx], rax
0x18001ac02  mov     [rbx+8], rcx
0x18001ac06  mov     [rcx], rbx
0x18001ac09  mov     [rax+8], rbx
0x18001ac0d  cmp     [rbx+22h], r12w
0x18001ac12  jge     short loc_18001AC8C
0x18001ac14  cmp     dword ptr [rsi+10h], 0Ah
0x18001ac18  jz      short loc_18001AC8C
0x18001ac1a  cmp     [rsi+58h], r12
0x18001ac1e  jz      short loc_18001AC8C
0x18001ac20  cmp     cs:qword_18002B8A8, r12
0x18001ac27  jz      short loc_18001AC67
0x18001ac29  mov     word ptr [rsp+890h+var_840], r12w
0x18001ac2f  lea     rdx, aInvokedLocalLe; "Invoked Local Leave Alert for protocol "...
0x18001ac36  mov     r9d, [rsi+14h]
0x18001ac3a  lea     rcx, [rsp+890h+var_840]
0x18001ac3f  mov     r8d, [rsi+10h]
0x18001ac43  call    FormatRRASErrorString
0x18001ac48  mov     rdx, cs:qword_18002B8A8
0x18001ac4f  lea     r8, [rsp+890h+var_840]
0x18001ac54  mov     rcx, cs:gMgmEtwContext
0x18001ac5b  mov     rax, cs:gMgmTemplateFunc
0x18001ac62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac67  mov     ecx, [rbx+14h]
0x18001ac6a  mov     r9d, [r14+24h]
0x18001ac6e  mov     r8d, [r14+20h]
0x18001ac72  mov     edx, [rdi+6Ch]
0x18001ac75  mov     rax, [rsi+58h]
0x18001ac79  mov     dword ptr [rsp+890h+var_868], ecx
0x18001ac7d  mov     ecx, [rbx+10h]
0x18001ac80  mov     dword ptr [rsp+890h+var_870], ecx
0x18001ac84  mov     ecx, [rdi+68h]
0x18001ac87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac8c  mov     r9d, [rbx+18h]
0x18001ac90  lea     rax, [rsp+890h+var_848]
0x18001ac95  mov     edx, [rbx+10h]
0x18001ac98  lea     rcx, [rdi+30h]
0x18001ac9c  mov     r8d, [rbx+14h]
0x18001aca0  mov     [rsp+890h+var_860], rax
0x18001aca5  lea     rax, [rsp+890h+var_850]
0x18001acaa  mov     [rsp+890h+var_868], rax
0x18001acaf  mov     eax, [rbx+1Ch]
0x18001acb2  mov     dword ptr [rsp+890h+var_870], eax
0x18001acb6  call    FindOutInterfaceEntry
0x18001acbb  cmp     [rsp+890h+var_850], r12d
0x18001acc0  jz      short loc_18001ACDD
0x18001acc2  dec     dword ptr [rdi+28h]
0x18001acc5  mov     rdx, rdi
0x18001acc8  mov     r9d, [rbx+14h]
0x18001accc  mov     rcx, r14
0x18001accf  mov     r8d, [rbx+10h]
0x18001acd3  mov     [rsp+890h+var_870], rsi
0x18001acd8  call    InvokePruneAlertCallbacks
0x18001acdd  mov     rcx, [rbp+790h+var_40]
0x18001ace4  xor     rcx, rsp; StackCookie
0x18001ace7  call    __security_check_cookie
0x18001acec  add     rsp, 860h
0x18001acf3  pop     r15
0x18001acf5  pop     r14
0x18001acf7  pop     r12
0x18001acf9  pop     rdi
0x18001acfa  pop     rsi
0x18001acfb  pop     rbx
0x18001acfc  pop     rbp
0x18001acfd  retn
```
