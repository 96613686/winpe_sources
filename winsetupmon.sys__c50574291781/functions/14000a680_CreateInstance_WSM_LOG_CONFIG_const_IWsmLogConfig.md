# CreateInstance(_WSM_LOG_CONFIG * const,IWsmLogConfig * *)

- ea: `0x14000a680`
- end: `0x14000a721`
- name: `?CreateInstance@@YAJQEAU_WSM_LOG_CONFIG@@PEAPEAVIWsmLogConfig@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(struct _WSM_LOG_CONFIG *const, struct IWsmLogConfig **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140001674`
- `0x140001748`

## callees

- `0x140008a18`
- `0x140009298`
- `0x14000a680`
- `0x14000b064`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a6e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a6e9`

## pseudocode

```c
__int64 __fastcall CreateInstance(const unsigned __int16 **a1, struct IWsmLogConfig **a2)
{
  CWsmLogConfig *v4; // rdi
  int v5; // ebx
  PVOID P; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 && a2 && *a1 )
  {
    utl::make_unique<CWsmLogConfig,,0>(&P, (const struct std::nothrow_t *)a2);
    v4 = (CWsmLogConfig *)P;
    if ( P )
    {
      v5 = CWsmLogConfig::Read((CWsmLogConfig *)P, a1, 0);
      if ( v5 >= 0 )
      {
        *a2 = (struct IWsmLogConfig *)(((unsigned __int64)v4 + 8) & -(__int64)(v4 != 0));
      }
      else if ( v4 )
      {
        CWsmLogConfig::~CWsmLogConfig(v4);
        ExFreePoolWithTag(v4, 0x6E6D7377u);
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000a680  mov     [rsp+arg_8], rbx
0x14000a685  mov     [rsp+arg_10], rsi
0x14000a68a  push    rdi
0x14000a68b  sub     rsp, 20h
0x14000a68f  mov     rsi, rdx
0x14000a692  mov     rbx, rcx
0x14000a695  test    rcx, rcx
0x14000a698  jz      short loc_14000A709
0x14000a69a  test    rdx, rdx
0x14000a69d  jz      short loc_14000A709
0x14000a69f  cmp     qword ptr [rcx], 0
0x14000a6a3  jz      short loc_14000A709
0x14000a6a5  lea     rcx, [rsp+28h+P]
0x14000a6aa  call    ??$make_unique@VCWsmLogConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCWsmLogConfig@@U?$default_delete@VCWsmLogConfig@@@utl@@@0@XZ; utl::make_unique<CWsmLogConfig,,0>(void)
0x14000a6af  mov     rdi, [rsp+28h+P]
0x14000a6b4  test    rdi, rdi
0x14000a6b7  jnz     short loc_14000A6C0
0x14000a6b9  mov     ebx, 0C000009Ah
0x14000a6be  jmp     short loc_14000A70E
0x14000a6c0  xor     r8d, r8d; bool
0x14000a6c3  mov     rdx, rbx; struct _WSM_LOG_CONFIG *
0x14000a6c6  mov     rcx, rdi; this
0x14000a6c9  call    ?Read@CWsmLogConfig@@IEAAJQEAU_WSM_LOG_CONFIG@@_N@Z; CWsmLogConfig::Read(_WSM_LOG_CONFIG * const,bool)
0x14000a6ce  mov     ebx, eax
0x14000a6d0  test    eax, eax
0x14000a6d2  jns     short loc_14000A6F7
0x14000a6d4  test    rdi, rdi
0x14000a6d7  jz      short loc_14000A70E
0x14000a6d9  mov     rcx, rdi; this
0x14000a6dc  call    ??1CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::~CWsmLogConfig(void)
0x14000a6e1  mov     edx, 6E6D7377h; Tag
0x14000a6e6  mov     rcx, rdi; P
0x14000a6e9  call    cs:__imp_ExFreePoolWithTag
0x14000a6f0  nop     dword ptr [rax+rax+00h]
0x14000a6f5  jmp     short loc_14000A70E
0x14000a6f7  lea     rcx, [rdi+8]
0x14000a6fb  neg     rdi
0x14000a6fe  sbb     rax, rax
0x14000a701  and     rax, rcx
0x14000a704  mov     [rsi], rax
0x14000a707  jmp     short loc_14000A70E
0x14000a709  mov     ebx, 0C000000Dh
0x14000a70e  mov     rsi, [rsp+28h+arg_10]
0x14000a713  mov     eax, ebx
0x14000a715  mov     rbx, [rsp+28h+arg_8]
0x14000a71a  add     rsp, 20h
0x14000a71e  pop     rdi
0x14000a71f  retn
```
