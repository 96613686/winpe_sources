# VMX_DISK_HEADER::Unformat(uchar * *,ulong)

- ea: `0x1400468ac`
- end: `0x140046abe`
- name: `?Unformat@VMX_DISK_HEADER@@QEAAJPEAPEAEK@Z`
- size: `530`
- prototype: `__int64 __fastcall(VMX_DISK_HEADER *this, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140045ed0`

## callees

- `0x14001ae08`
- `0x1400468ac`
- `0x140046dcc`
- `0x140047924`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400468d3`
- `ntoskrnl!RtlCompareMemory` at `0x1400468d3`

## pseudocode

```c
__int64 __fastcall VMX_DISK_HEADER::Unformat(VMX_DISK_HEADER *this, unsigned __int8 **a2)
{
  const void *v2; // rdi
  unsigned __int8 *v5; // rbp
  unsigned __int8 *v6; // r10
  unsigned int v7; // eax
  int v8; // r9d
  int v9; // r11d
  int v10; // edi
  unsigned __int8 *v11; // r9
  unsigned __int8 *v12; // rax
  unsigned __int8 *v13; // rdx
  unsigned __int8 *v14; // rdx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r8
  unsigned __int64 v18; // r9
  unsigned __int64 v19; // r10

  v2 = *a2;
  if ( RtlCompareMemory(*a2, &qword_14001FB90, 8u) != 8 )
    return 3221225485LL;
  v5 = *a2 + 12;
  VmxpCheckSum(v5, 0x1F4u);
  v7 = VmxpCheckSum(v6, 8u);
  if ( v8 + v7 + (v8 + v7) / 0xFFFFFFFF != v9 )
    return 3221225485LL;
  v10 = (_DWORD)v2 + 512;
  v11 = VmxpUnformatTable((const struct VMX_FIELD *)qword_14001FC70, 2u, (char *)this, v5, v10 - (int)v5);
  if ( !v11 )
    return 3221225485LL;
  if ( *(_WORD *)this != 2 )
    return 3221225485LL;
  v12 = VmxpUnformatTable((const struct VMX_FIELD *)qword_14001F8D0, 0x16u, (char *)this, v11, v10 - (int)v11);
  v13 = v12;
  if ( !v12 )
    return 3221225485LL;
  if ( *((_WORD *)this + 1) >= 0xAu )
  {
    v13 = VmxpUnformatTable((const struct VMX_FIELD *)qword_14001FBE8, 1u, (char *)this, v12, v10 - (int)v12);
    if ( !v13 )
      return 3221225485LL;
  }
  if ( *((_WORD *)this + 1) >= 0xBu )
  {
    v13 = VmxpUnformatTable((const struct VMX_FIELD *)qword_14001FBA0, 2u, (char *)this, v13, v10 - (int)v13);
    if ( !v13 )
      return 3221225485LL;
  }
  if ( *((_WORD *)this + 1) >= 0xCu
    && !VmxpUnformatTable((const struct VMX_FIELD *)qword_14001FC10, 3u, (char *)this, v13, v10 - (int)v13) )
  {
    return 3221225485LL;
  }
  if ( !VmxpSupportedBytesPerSector(*((_DWORD *)this + 30)) )
    return 3221225485LL;
  v15 = *((_QWORD *)this + 20);
  v16 = *((_QWORD *)this + 3);
  if ( v16 >= v15 )
    return 3221225485LL;
  v17 = *((_QWORD *)this + 4);
  if ( v17 >= v15 )
    return 3221225485LL;
  v18 = *((_QWORD *)this + 21);
  if ( v18 >= v15 )
    return 3221225485LL;
  v19 = *((_QWORD *)this + 22);
  if ( v19 >= v15
    || v15 > 0xFFFFFFFF
    || v16 > 0xFFFFFFFF
    || v17 > 0xFFFFFFFF
    || v18 > 0xFFFFFFFF
    || v19 > 0xFFFFFFFF
    || *((_QWORD *)this + 24) > 0xFFFFFFFF
    || *((_QWORD *)this + 25) > 0xFFFFFFFF )
  {
    return 3221225485LL;
  }
  *a2 = v14;
  return 0;
}

```

## disassembly

```asm
0x1400468ac  push    rbx
0x1400468ae  push    rbp
0x1400468af  push    rsi
0x1400468b0  push    rdi
0x1400468b1  push    r14
0x1400468b3  sub     rsp, 30h
0x1400468b7  mov     rdi, [rdx]
0x1400468ba  mov     rsi, rdx
0x1400468bd  mov     rbx, rcx
0x1400468c0  lea     rdx, qword_14001FB90; Source2
0x1400468c7  mov     r14d, 8
0x1400468cd  mov     rcx, rdi; Source1
0x1400468d0  mov     r8d, r14d; Length
0x1400468d3  call    cs:__imp_RtlCompareMemory
0x1400468da  nop     dword ptr [rax+rax+00h]
0x1400468df  cmp     rax, r14
0x1400468e2  jnz     loc_140046AAD
0x1400468e8  mov     r10, [rsi]
0x1400468eb  mov     edx, 1F4h; unsigned int
0x1400468f0  movzx   eax, byte ptr [r10+9]
0x1400468f5  lea     rcx, [r10+0Ch]; unsigned __int8 *
0x1400468f9  movzx   r11d, byte ptr [r10+8]
0x1400468fe  lea     rbp, [r10+0Ch]
0x140046902  shl     r11d, 8
0x140046906  or      r11d, eax
0x140046909  movzx   eax, byte ptr [r10+0Ah]
0x14004690e  shl     r11d, 8
0x140046912  or      r11d, eax
0x140046915  movzx   eax, byte ptr [r10+0Bh]
0x14004691a  shl     r11d, 8
0x14004691e  or      r11d, eax
0x140046921  call    ?VmxpCheckSum@@YAKPEAEK@Z; VmxpCheckSum(uchar *,ulong)
0x140046926  mov     edx, r14d; unsigned int
0x140046929  mov     rcx, r10; unsigned __int8 *
0x14004692c  mov     r9d, eax
0x14004692f  call    ?VmxpCheckSum@@YAKPEAEK@Z; VmxpCheckSum(uchar *,ulong)
0x140046934  xor     edx, edx
0x140046936  mov     r14d, 0FFFFFFFFh
0x14004693c  lea     ecx, [r9+rax]
0x140046940  mov     eax, ecx
0x140046942  div     r14d
0x140046945  add     eax, ecx
0x140046947  cmp     eax, r11d
0x14004694a  jnz     loc_140046AAD
0x140046950  mov     r9, rbp; unsigned __int8 *
0x140046953  lea     rcx, qword_14001FC70; struct VMX_FIELD *
0x14004695a  add     edi, 200h
0x140046960  mov     r8, rbx; void *
0x140046963  mov     eax, edi
0x140046965  sub     eax, ebp
0x140046967  mov     ebp, 2
0x14004696c  mov     edx, ebp; unsigned int
0x14004696e  mov     [rsp+58h+var_38], eax; unsigned int
0x140046972  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x140046977  mov     r9, rax; unsigned __int8 *
0x14004697a  test    rax, rax
0x14004697d  jz      loc_140046AAD
0x140046983  cmp     [rbx], bp
0x140046986  jnz     loc_140046AAD
0x14004698c  mov     eax, edi
0x14004698e  lea     edx, [rbp+14h]; unsigned int
0x140046991  sub     eax, r9d
0x140046994  lea     rcx, qword_14001F8D0; struct VMX_FIELD *
0x14004699b  mov     r8, rbx; void *
0x14004699e  mov     [rsp+58h+var_38], eax; unsigned int
0x1400469a2  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x1400469a7  mov     rdx, rax
0x1400469aa  test    rax, rax
0x1400469ad  jz      loc_140046AAD
0x1400469b3  cmp     word ptr [rbx+2], 0Ah
0x1400469b8  jb      short loc_1400469E3
0x1400469ba  mov     eax, edi
0x1400469bc  lea     rcx, qword_14001FBE8; struct VMX_FIELD *
0x1400469c3  sub     eax, edx
0x1400469c5  mov     r9, rdx; unsigned __int8 *
0x1400469c8  lea     edx, [rbp-1]; unsigned int
0x1400469cb  mov     [rsp+58h+var_38], eax; unsigned int
0x1400469cf  mov     r8, rbx; void *
0x1400469d2  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x1400469d7  mov     rdx, rax
0x1400469da  test    rax, rax
0x1400469dd  jz      loc_140046AAD
0x1400469e3  cmp     word ptr [rbx+2], 0Bh
0x1400469e8  jb      short loc_140046A12
0x1400469ea  mov     eax, edi
0x1400469ec  lea     rcx, qword_14001FBA0; struct VMX_FIELD *
0x1400469f3  sub     eax, edx
0x1400469f5  mov     r9, rdx; unsigned __int8 *
0x1400469f8  mov     edx, ebp; unsigned int
0x1400469fa  mov     [rsp+58h+var_38], eax; unsigned int
0x1400469fe  mov     r8, rbx; void *
0x140046a01  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x140046a06  mov     rdx, rax
0x140046a09  test    rax, rax
0x140046a0c  jz      loc_140046AAD
0x140046a12  cmp     word ptr [rbx+2], 0Ch
0x140046a17  jb      short loc_140046A3E
0x140046a19  sub     edi, edx
0x140046a1b  lea     rcx, qword_14001FC10; struct VMX_FIELD *
0x140046a22  mov     r9, rdx; unsigned __int8 *
0x140046a25  mov     [rsp+58h+var_38], edi; unsigned int
0x140046a29  mov     edx, 3; unsigned int
0x140046a2e  mov     r8, rbx; void *
0x140046a31  call    ?VmxpUnformatTable@@YAPEAEPEBVVMX_FIELD@@KPEAXPEAEK@Z; VmxpUnformatTable(VMX_FIELD const *,ulong,void *,uchar *,ulong)
0x140046a36  mov     rdx, rax
0x140046a39  test    rax, rax
0x140046a3c  jz      short loc_140046AAD
0x140046a3e  mov     ecx, [rbx+78h]; unsigned int
0x140046a41  call    ?VmxpSupportedBytesPerSector@@YAEK@Z; VmxpSupportedBytesPerSector(ulong)
0x140046a46  test    al, al
0x140046a48  jz      short loc_140046AAD
0x140046a4a  mov     rax, [rbx+0A0h]
0x140046a51  mov     rcx, [rbx+18h]
0x140046a55  cmp     rcx, rax
0x140046a58  jnb     short loc_140046AAD
0x140046a5a  mov     r8, [rbx+20h]
0x140046a5e  cmp     r8, rax
0x140046a61  jnb     short loc_140046AAD
0x140046a63  mov     r9, [rbx+0A8h]
0x140046a6a  cmp     r9, rax
0x140046a6d  jnb     short loc_140046AAD
0x140046a6f  mov     r10, [rbx+0B0h]
0x140046a76  cmp     r10, rax
0x140046a79  jnb     short loc_140046AAD
0x140046a7b  cmp     rax, r14
0x140046a7e  ja      short loc_140046AAD
0x140046a80  cmp     rcx, r14
0x140046a83  ja      short loc_140046AAD
0x140046a85  cmp     r8, r14
0x140046a88  ja      short loc_140046AAD
0x140046a8a  cmp     r9, r14
0x140046a8d  ja      short loc_140046AAD
0x140046a8f  cmp     r10, r14
0x140046a92  ja      short loc_140046AAD
0x140046a94  cmp     [rbx+0C0h], r14
0x140046a9b  ja      short loc_140046AAD
0x140046a9d  cmp     [rbx+0C8h], r14
0x140046aa4  ja      short loc_140046AAD
0x140046aa6  mov     [rsi], rdx
0x140046aa9  xor     eax, eax
0x140046aab  jmp     short loc_140046AB2
0x140046aad  mov     eax, 0C000000Dh
0x140046ab2  add     rsp, 30h
0x140046ab6  pop     r14
0x140046ab8  pop     rdi
0x140046ab9  pop     rsi
0x140046aba  pop     rbp
0x140046abb  pop     rbx
0x140046abc  retn
```
