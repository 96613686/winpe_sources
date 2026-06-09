# CreateInstance(uchar const *,ulong,IWsmStableLogConfig * *)

- ea: `0x14000a4b0`
- end: `0x14000a590`
- name: `?CreateInstance@@YAJPEBEKPEAPEAVIWsmStableLogConfig@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(const unsigned __int8 *, unsigned int, struct IWsmStableLogConfig **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140001380`

## callees

- `0x140008a18`
- `0x140009298`
- `0x14000a4b0`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a562`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a562`

## pseudocode

```c
__int64 __fastcall CreateInstance(
        const unsigned __int8 *a1,
        const struct std::nothrow_t *a2,
        struct IWsmStableLogConfig **a3)
{
  int v4; // ebx
  struct IWsmStableLogConfig *v6; // rdi
  int v7; // ebx
  __int64 v8; // r14
  const unsigned __int8 *v10; // [rsp+20h] [rbp-28h] BYREF
  int v11; // [rsp+28h] [rbp-20h]
  int v12; // [rsp+2Ch] [rbp-1Ch]
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  v4 = (int)a2;
  if ( a1 && (_DWORD)a2 && a3 )
  {
    utl::make_unique<CWsmLogConfig,,0>(&P, a2);
    v6 = (struct IWsmStableLogConfig *)P;
    if ( P )
    {
      v8 = *((_QWORD *)P + 5);
      v10 = a1;
      v11 = v4;
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
        CWsmLogConfig::~CWsmLogConfig(v6);
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
0x14000a4b0  mov     [rsp+arg_8], rbx
0x14000a4b5  mov     [rsp+arg_10], rbp
0x14000a4ba  push    rsi
0x14000a4bb  push    rdi
0x14000a4bc  push    r14
0x14000a4be  sub     rsp, 30h
0x14000a4c2  mov     rsi, r8
0x14000a4c5  mov     ebx, edx
0x14000a4c7  mov     rbp, rcx
0x14000a4ca  test    rcx, rcx
0x14000a4cd  jz      loc_14000A575
0x14000a4d3  test    edx, edx
0x14000a4d5  jz      loc_14000A575
0x14000a4db  test    r8, r8
0x14000a4de  jz      loc_14000A575
0x14000a4e4  lea     rcx, [rsp+48h+P]
0x14000a4e9  call    ??$make_unique@VCWsmLogConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCWsmLogConfig@@U?$default_delete@VCWsmLogConfig@@@utl@@@0@XZ; utl::make_unique<CWsmLogConfig,,0>(void)
0x14000a4ee  mov     rdi, [rsp+48h+P]
0x14000a4f3  test    rdi, rdi
0x14000a4f6  jnz     short loc_14000A4FF
0x14000a4f8  mov     ebx, 0C000009Ah
0x14000a4fd  jmp     short loc_14000A57A
0x14000a4ff  mov     r14, [rdi+28h]
0x14000a503  lea     rdx, [rsp+48h+var_28]
0x14000a508  mov     rcx, r14
0x14000a50b  mov     [rsp+48h+var_28], rbp
0x14000a510  mov     [rsp+48h+var_20], ebx
0x14000a514  mov     [rsp+48h+var_1C], 0
0x14000a51c  mov     rax, [r14]
0x14000a51f  mov     rax, [rax+8]
0x14000a523  call    _guard_dispatch_icall
0x14000a528  mov     ebx, eax
0x14000a52a  test    eax, eax
0x14000a52c  js      short loc_14000A549
0x14000a52e  lea     rdx, [rdi+10h]
0x14000a532  mov     rcx, r14
0x14000a535  mov     rax, [rdx]
0x14000a538  mov     [rdx+8], rax
0x14000a53c  mov     rax, [r14]
0x14000a53f  mov     rax, [rax]
0x14000a542  call    _guard_dispatch_icall
0x14000a547  mov     ebx, eax
0x14000a549  test    ebx, ebx
0x14000a54b  jns     short loc_14000A570
0x14000a54d  test    rdi, rdi
0x14000a550  jz      short loc_14000A57A
0x14000a552  mov     rcx, rdi; this
0x14000a555  call    ??1CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::~CWsmLogConfig(void)
0x14000a55a  mov     edx, 6E6D7377h; Tag
0x14000a55f  mov     rcx, rdi; P
0x14000a562  call    cs:__imp_ExFreePoolWithTag
0x14000a569  nop     dword ptr [rax+rax+00h]
0x14000a56e  jmp     short loc_14000A57A
0x14000a570  mov     [rsi], rdi
0x14000a573  jmp     short loc_14000A57A
0x14000a575  mov     ebx, 0C000000Dh
0x14000a57a  mov     rbp, [rsp+48h+arg_10]
0x14000a57f  mov     eax, ebx
0x14000a581  mov     rbx, [rsp+48h+arg_8]
0x14000a586  add     rsp, 30h
0x14000a58a  pop     r14
0x14000a58c  pop     rdi
0x14000a58d  pop     rsi
0x14000a58e  retn
```
