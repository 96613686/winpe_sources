# CreateInstance(uchar const *,ulong,IWsmStableTrackingConfig * *)

- ea: `0x14000a598`
- end: `0x14000a678`
- name: `?CreateInstance@@YAJPEBEKPEAPEAVIWsmStableTrackingConfig@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, struct IWsmStableTrackingConfig **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140001380`

## callees

- `0x140008a8c`
- `0x140009300`
- `0x14000a598`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a64a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a64a`

## pseudocode

```c
__int64 __fastcall CreateInstance(const unsigned __int8 *a1, int a2, struct IWsmStableTrackingConfig **a3)
{
  struct IWsmStableTrackingConfig *v6; // rdi
  int v7; // ebx
  __int64 v8; // r14
  const unsigned __int8 *v10; // [rsp+20h] [rbp-28h] BYREF
  int v11; // [rsp+28h] [rbp-20h]
  int v12; // [rsp+2Ch] [rbp-1Ch]
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  if ( a1 && a2 && a3 )
  {
    utl::make_unique<CWsmTrackingConfig,,0>(&P);
    v6 = (struct IWsmStableTrackingConfig *)P;
    if ( P )
    {
      v8 = *((_QWORD *)P + 5);
      v10 = a1;
      v11 = a2;
      v12 = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, const unsigned __int8 **))(*(_QWORD *)v8 + 8LL))(v8, &v10);
      if ( v7 >= 0 )
      {
        *((_QWORD *)v6 + 3) = *((_QWORD *)v6 + 2);
        v7 = (**(__int64 (__fastcall ***)(__int64))v8)(v8);
      }
      if ( v7 >= 0 )
      {
        *a3 = v6;
      }
      else if ( v6 )
      {
        CWsmTrackingConfig::~CWsmTrackingConfig(v6);
        ExFreePoolWithTag(v6, 0x6E6D7377u);
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000a598  mov     [rsp+arg_8], rbx
0x14000a59d  mov     [rsp+arg_10], rbp
0x14000a5a2  push    rsi
0x14000a5a3  push    rdi
0x14000a5a4  push    r14
0x14000a5a6  sub     rsp, 30h
0x14000a5aa  mov     rsi, r8
0x14000a5ad  mov     ebx, edx
0x14000a5af  mov     rbp, rcx
0x14000a5b2  test    rcx, rcx
0x14000a5b5  jz      loc_14000A65D
0x14000a5bb  test    edx, edx
0x14000a5bd  jz      loc_14000A65D
0x14000a5c3  test    r8, r8
0x14000a5c6  jz      loc_14000A65D
0x14000a5cc  lea     rcx, [rsp+48h+P]
0x14000a5d1  call    ??$make_unique@VCWsmTrackingConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCWsmTrackingConfig@@U?$default_delete@VCWsmTrackingConfig@@@utl@@@0@XZ; utl::make_unique<CWsmTrackingConfig,,0>(void)
0x14000a5d6  mov     rdi, [rsp+48h+P]
0x14000a5db  test    rdi, rdi
0x14000a5de  jnz     short loc_14000A5E7
0x14000a5e0  mov     ebx, 0C000009Ah
0x14000a5e5  jmp     short loc_14000A662
0x14000a5e7  mov     r14, [rdi+28h]
0x14000a5eb  lea     rdx, [rsp+48h+var_28]
0x14000a5f0  mov     rcx, r14
0x14000a5f3  mov     [rsp+48h+var_28], rbp
0x14000a5f8  mov     [rsp+48h+var_20], ebx
0x14000a5fc  mov     [rsp+48h+var_1C], 0
0x14000a604  mov     rax, [r14]
0x14000a607  mov     rax, [rax+8]
0x14000a60b  call    _guard_dispatch_icall
0x14000a610  mov     ebx, eax
0x14000a612  test    eax, eax
0x14000a614  js      short loc_14000A631
0x14000a616  lea     rdx, [rdi+10h]
0x14000a61a  mov     rcx, r14
0x14000a61d  mov     rax, [rdx]
0x14000a620  mov     [rdx+8], rax
0x14000a624  mov     rax, [r14]
0x14000a627  mov     rax, [rax]
0x14000a62a  call    _guard_dispatch_icall
0x14000a62f  mov     ebx, eax
0x14000a631  test    ebx, ebx
0x14000a633  jns     short loc_14000A658
0x14000a635  test    rdi, rdi
0x14000a638  jz      short loc_14000A662
0x14000a63a  mov     rcx, rdi; this
0x14000a63d  call    ??1CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::~CWsmTrackingConfig(void)
0x14000a642  mov     edx, 6E6D7377h; Tag
0x14000a647  mov     rcx, rdi; P
0x14000a64a  call    cs:__imp_ExFreePoolWithTag
0x14000a651  nop     dword ptr [rax+rax+00h]
0x14000a656  jmp     short loc_14000A662
0x14000a658  mov     [rsi], rdi
0x14000a65b  jmp     short loc_14000A662
0x14000a65d  mov     ebx, 0C000000Dh
0x14000a662  mov     rbp, [rsp+48h+arg_10]
0x14000a667  mov     eax, ebx
0x14000a669  mov     rbx, [rsp+48h+arg_8]
0x14000a66e  add     rsp, 30h
0x14000a672  pop     r14
0x14000a674  pop     rdi
0x14000a675  pop     rsi
0x14000a676  retn
```
