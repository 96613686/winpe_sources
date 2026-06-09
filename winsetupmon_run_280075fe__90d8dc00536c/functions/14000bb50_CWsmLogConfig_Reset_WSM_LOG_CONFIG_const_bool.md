# CWsmLogConfig::Reset(_WSM_LOG_CONFIG * const,bool)

- ea: `0x14000bb50`
- end: `0x14000bbf3`
- name: `?Reset@CWsmLogConfig@@IEAAJQEAU_WSM_LOG_CONFIG@@_N@Z`
- size: `163`
- prototype: `int(CWsmLogConfig *__hidden this, struct _WSM_LOG_CONFIG *const, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000bc00`
- `0x14000bc70`
- `0x14000bf50`

## callees

- `0x140008a18`
- `0x140008f60`
- `0x140009298`
- `0x14000b064`
- `0x14000bb50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbdb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bbdb`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::Reset(CWsmLogConfig *this, const unsigned __int16 **a2, char a3)
{
  CWsmLogConfig *v6; // rbx
  int v8; // esi
  __int64 v9; // rax
  CWsmLogConfig::CLogConfig *v10; // rdi
  PVOID P; // [rsp+68h] [rbp+20h] BYREF

  utl::make_unique<CWsmLogConfig,,0>(&P);
  v6 = (CWsmLogConfig *)P;
  if ( !P )
    return 3221225626LL;
  v8 = CWsmLogConfig::Read((CWsmLogConfig *)P, a2, a3);
  if ( v8 >= 0 )
  {
    v9 = *((_QWORD *)v6 + 5);
    *((_QWORD *)v6 + 5) = 0;
    v10 = (CWsmLogConfig::CLogConfig *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v9;
    if ( v10 )
    {
      CWsmLogConfig::CLogConfig::~CLogConfig(v10);
      ExFreePoolWithTag(v10, 0x6E6D7377u);
    }
  }
  if ( v6 )
  {
    CWsmLogConfig::~CWsmLogConfig(v6);
    ExFreePoolWithTag(v6, 0x6E6D7377u);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000bb50  push    rbx
0x14000bb52  push    rbp
0x14000bb53  push    rsi
0x14000bb54  push    rdi
0x14000bb55  sub     rsp, 28h
0x14000bb59  mov     rbp, rcx
0x14000bb5c  mov     dil, r8b
0x14000bb5f  lea     rcx, [rsp+48h+P]
0x14000bb64  mov     rsi, rdx
0x14000bb67  call    ??$make_unique@VCWsmLogConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCWsmLogConfig@@U?$default_delete@VCWsmLogConfig@@@utl@@@0@XZ; utl::make_unique<CWsmLogConfig,,0>(void)
0x14000bb6c  mov     rbx, [rsp+48h+P]
0x14000bb71  test    rbx, rbx
0x14000bb74  jnz     short loc_14000BB7D
0x14000bb76  mov     eax, 0C000009Ah
0x14000bb7b  jmp     short loc_14000BBE9
0x14000bb7d  mov     r8b, dil; bool
0x14000bb80  mov     rdx, rsi; struct _WSM_LOG_CONFIG *
0x14000bb83  mov     rcx, rbx; this
0x14000bb86  call    ?Read@CWsmLogConfig@@IEAAJQEAU_WSM_LOG_CONFIG@@_N@Z; CWsmLogConfig::Read(_WSM_LOG_CONFIG * const,bool)
0x14000bb8b  mov     esi, eax
0x14000bb8d  test    eax, eax
0x14000bb8f  js      short loc_14000BBC6
0x14000bb91  mov     rax, [rbx+28h]
0x14000bb95  mov     qword ptr [rbx+28h], 0
0x14000bb9d  mov     rdi, [rbp+28h]
0x14000bba1  mov     [rbp+28h], rax
0x14000bba5  test    rdi, rdi
0x14000bba8  jz      short loc_14000BBC6
0x14000bbaa  mov     rcx, rdi; this
0x14000bbad  call    ??1CLogConfig@CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::CLogConfig::~CLogConfig(void)
0x14000bbb2  mov     edx, 6E6D7377h; Tag
0x14000bbb7  mov     rcx, rdi; P
0x14000bbba  call    cs:__imp_ExFreePoolWithTag
0x14000bbc1  nop     dword ptr [rax+rax+00h]
0x14000bbc6  test    rbx, rbx
0x14000bbc9  jz      short loc_14000BBE7
0x14000bbcb  mov     rcx, rbx; this
0x14000bbce  call    ??1CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::~CWsmLogConfig(void)
0x14000bbd3  mov     edx, 6E6D7377h; Tag
0x14000bbd8  mov     rcx, rbx; P
0x14000bbdb  call    cs:__imp_ExFreePoolWithTag
0x14000bbe2  nop     dword ptr [rax+rax+00h]
0x14000bbe7  mov     eax, esi
0x14000bbe9  add     rsp, 28h
0x14000bbed  pop     rdi
0x14000bbee  pop     rsi
0x14000bbef  pop     rbp
0x14000bbf0  pop     rbx
0x14000bbf1  retn
```
