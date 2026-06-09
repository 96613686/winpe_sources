# VMX_RAW_RECORD::UnformatRecordFragment(uchar * *,ulong,ulong,VMX_CONFIG *)

- ea: `0x14005a37c`
- end: `0x14005a4c2`
- name: `?UnformatRecordFragment@VMX_RAW_RECORD@@QEAAJPEAPEAEKKPEAVVMX_CONFIG@@@Z`
- size: `326`
- prototype: `__int64 __fastcall(VMX_RAW_RECORD *this, unsigned __int8 **, unsigned int, unsigned int, struct VMX_CONFIG *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14005e110`

## callees

- `0x1400099d8`
- `0x14001bb80`
- `0x140042c04`
- `0x14005a37c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005a3b7`
- `ntoskrnl!ExAllocatePool2` at `0x14005a3b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a45a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a45a`

## pseudocode

```c
__int64 __fastcall VMX_RAW_RECORD::UnformatRecordFragment(
        VMX_RAW_RECORD *this,
        unsigned __int8 **a2,
        unsigned int a3,
        unsigned int a4,
        struct VMX_CONFIG *a5)
{
  __int64 v5; // r12
  size_t v7; // rsi
  unsigned __int8 **v9; // rdi
  __int64 Pool2; // rax
  char *v12; // r15
  unsigned int v13; // r8d
  int v14; // ebp
  unsigned __int8 *v15; // [rsp+20h] [rbp-48h] BYREF

  v5 = a4;
  v7 = a3;
  v15 = 0;
  v9 = (unsigned __int8 **)((char *)this + 48);
  if ( !a4 )
  {
    Pool2 = ExAllocatePool2(258, *((unsigned int *)this + 7), 1649569110);
    *v9 = (unsigned __int8 *)Pool2;
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 19, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids, 3221225626LL);
      }
      return 3221225626LL;
    }
  }
  v12 = (char *)*a2;
  memmove(&(*v9)[v5], *a2, v7);
  if ( (*((_BYTE *)this + 24) & 2) == 0 )
  {
    *a2 = (unsigned __int8 *)&v12[v7];
    return 0;
  }
  v13 = *((_DWORD *)this + 7);
  v15 = *v9;
  v14 = VMX_CONFIG::UnformatRecord(a5, &v15, v13, this);
  ExFreePoolWithTag(*v9, 0);
  *v9 = 0;
  if ( v14 >= 0 )
  {
    *a2 += v7;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      20,
      WPP_36c7d132267136af2220cbe73d2245a2_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14005a37c  push    rbx
0x14005a37e  push    rbp
0x14005a37f  push    rsi
0x14005a380  push    rdi
0x14005a381  push    r12
0x14005a383  push    r14
0x14005a385  push    r15
0x14005a387  sub     rsp, 30h
0x14005a38b  mov     r12d, r9d
0x14005a38e  mov     rbx, rdx
0x14005a391  mov     esi, r8d
0x14005a394  mov     rbp, rcx
0x14005a397  mov     [rsp+68h+var_48], 0
0x14005a3a0  lea     rdi, [rcx+30h]
0x14005a3a4  test    r9d, r9d
0x14005a3a7  jnz     short loc_14005A40F
0x14005a3a9  mov     edx, [rcx+1Ch]
0x14005a3ac  mov     r8d, 62526D56h
0x14005a3b2  mov     ecx, 102h
0x14005a3b7  call    cs:__imp_ExAllocatePool2
0x14005a3be  nop     dword ptr [rax+rax+00h]
0x14005a3c3  mov     [rdi], rax
0x14005a3c6  test    rax, rax
0x14005a3c9  jnz     short loc_14005A40F
0x14005a3cb  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a3d2  lea     rax, WPP_GLOBAL_Control
0x14005a3d9  mov     ebx, 0C000009Ah
0x14005a3de  cmp     rcx, rax
0x14005a3e1  jz      short loc_14005A408
0x14005a3e3  mov     eax, [rcx+2Ch]
0x14005a3e6  test    al, 40h
0x14005a3e8  jz      short loc_14005A408
0x14005a3ea  cmp     byte ptr [rcx+29h], 2
0x14005a3ee  jb      short loc_14005A408
0x14005a3f0  mov     rcx, [rcx+18h]
0x14005a3f4  lea     r8, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids
0x14005a3fb  mov     edx, 13h
0x14005a400  mov     r9d, ebx
0x14005a403  call    WPP_SF_d
0x14005a408  mov     eax, ebx
0x14005a40a  jmp     loc_14005A4B2
0x14005a40f  mov     r15, [rbx]
0x14005a412  mov     rcx, r12
0x14005a415  add     rcx, [rdi]; void *
0x14005a418  mov     rdx, r15; Src
0x14005a41b  mov     r8, rsi; Size
0x14005a41e  call    memmove
0x14005a423  test    byte ptr [rbp+18h], 2
0x14005a427  jnz     short loc_14005A432
0x14005a429  lea     rax, [r15+rsi]
0x14005a42d  mov     [rbx], rax
0x14005a430  jmp     short loc_14005A4B0
0x14005a432  mov     rax, [rdi]
0x14005a435  lea     rdx, [rsp+68h+var_48]; unsigned __int8 **
0x14005a43a  mov     r8d, [rbp+1Ch]; unsigned int
0x14005a43e  mov     r9, rbp; struct VMX_RAW_RECORD *
0x14005a441  mov     rcx, [rsp+68h+arg_20]; this
0x14005a449  mov     [rsp+68h+var_48], rax
0x14005a44e  call    ?UnformatRecord@VMX_CONFIG@@QEAAJPEAPEAEKPEAVVMX_RAW_RECORD@@@Z; VMX_CONFIG::UnformatRecord(uchar * *,ulong,VMX_RAW_RECORD *)
0x14005a453  mov     rcx, [rdi]; P
0x14005a456  xor     edx, edx; Tag
0x14005a458  mov     ebp, eax
0x14005a45a  call    cs:__imp_ExFreePoolWithTag
0x14005a461  nop     dword ptr [rax+rax+00h]
0x14005a466  mov     qword ptr [rdi], 0
0x14005a46d  test    ebp, ebp
0x14005a46f  jns     short loc_14005A4AD
0x14005a471  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a478  lea     rax, WPP_GLOBAL_Control
0x14005a47f  cmp     rcx, rax
0x14005a482  jz      short loc_14005A4A9
0x14005a484  mov     eax, [rcx+2Ch]
0x14005a487  test    al, 40h
0x14005a489  jz      short loc_14005A4A9
0x14005a48b  cmp     byte ptr [rcx+29h], 2
0x14005a48f  jb      short loc_14005A4A9
0x14005a491  mov     rcx, [rcx+18h]
0x14005a495  lea     r8, WPP_36c7d132267136af2220cbe73d2245a2_Traceguids
0x14005a49c  mov     edx, 14h
0x14005a4a1  mov     r9d, ebp
0x14005a4a4  call    WPP_SF_d
0x14005a4a9  mov     eax, ebp
0x14005a4ab  jmp     short loc_14005A4B2
0x14005a4ad  add     [rbx], rsi
0x14005a4b0  xor     eax, eax
0x14005a4b2  add     rsp, 30h
0x14005a4b6  pop     r15
0x14005a4b8  pop     r14
0x14005a4ba  pop     r12
0x14005a4bc  pop     rdi
0x14005a4bd  pop     rsi
0x14005a4be  pop     rbp
0x14005a4bf  pop     rbx
0x14005a4c0  retn
```
