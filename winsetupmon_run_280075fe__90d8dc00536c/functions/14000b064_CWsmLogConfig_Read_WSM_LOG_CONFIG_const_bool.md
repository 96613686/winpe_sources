# CWsmLogConfig::Read(_WSM_LOG_CONFIG * const,bool)

- ea: `0x14000b064`
- end: `0x14000b1ad`
- name: `?Read@CWsmLogConfig@@IEAAJQEAU_WSM_LOG_CONFIG@@_N@Z`
- size: `329`
- prototype: `__int64 __fastcall(CWsmLogConfig *__hidden this, struct _WSM_LOG_CONFIG *const, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000a680`
- `0x14000bb50`

## callees

- `0x14000894c`
- `0x140008f60`
- `0x14000b064`
- `0x14000ce88`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b098`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b0c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b157`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b19d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b098`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b0c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b157`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b19d`

## pseudocode

```c
__int64 __fastcall CWsmLogConfig::Read(CWsmLogConfig *this, const unsigned __int16 **a2, char a3)
{
  CWsmLogConfig::CLogConfig *v3; // rbx
  CWsmLogConfig::CLogConfig *v7; // rbx
  CWsmLogConfig::CLogConfig *v8; // rbx
  unsigned int v9; // esi
  const unsigned __int16 *v10; // rdx
  wsm_wstring *v11; // rcx
  int v12; // eax
  __int64 *v13; // rax
  __int64 v14; // rcx
  CWsmLogConfig::CLogConfig *v15; // rsi
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  v3 = (CWsmLogConfig::CLogConfig *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v3 )
  {
    CWsmLogConfig::CLogConfig::~CLogConfig(v3);
    ExFreePoolWithTag(v3, 0x6E6D7377u);
  }
  v7 = (CWsmLogConfig::CLogConfig *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v7 )
  {
    CWsmLogConfig::CLogConfig::~CLogConfig(v7);
    ExFreePoolWithTag(v7, 0x6E6D7377u);
  }
  utl::make_unique<CWsmLogConfig::CLogConfig,,0>(&P);
  v8 = (CWsmLogConfig::CLogConfig *)P;
  if ( !P )
    return (unsigned int)-1073741670;
  if ( a2 )
  {
    v10 = *a2;
    v11 = (wsm_wstring *)((char *)P + 24);
    if ( a3 )
      v12 = wsm_wstring::init(v11, v10);
    else
      v12 = (*(__int64 (__fastcall **)(wsm_wstring *, const unsigned __int16 *))(*(_QWORD *)v11 + 16LL))(v11, v10);
    v9 = v12;
    if ( v12 < 0 )
    {
      if ( v8 )
      {
        CWsmLogConfig::CLogConfig::~CLogConfig(v8);
        ExFreePoolWithTag(v8, 0x6E6D7377u);
      }
      return v9;
    }
    v13 = (__int64 *)*((_QWORD *)v8 + 4);
    if ( v13 )
      v14 = *v13;
    else
      v14 = 0;
    *((_QWORD *)v8 + 2) = a2[1];
    *((_QWORD *)v8 + 1) = v14;
  }
  if ( v8 )
  {
    v15 = (CWsmLogConfig::CLogConfig *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v8;
    if ( v15 )
    {
      CWsmLogConfig::CLogConfig::~CLogConfig(v15);
      ExFreePoolWithTag(v15, 0x6E6D7377u);
    }
  }
  *((_QWORD *)this + 3) = *((_QWORD *)this + 2);
  return (***((__int64 (__fastcall ****)(_QWORD))this + 5))(*((_QWORD *)this + 5));
}

```

## disassembly

```asm
0x14000b064  push    rbx
0x14000b066  push    rsi
0x14000b067  push    rdi
0x14000b068  push    r14
0x14000b06a  sub     rsp, 28h
0x14000b06e  mov     rbx, [rcx+28h]
0x14000b072  mov     sil, r8b
0x14000b075  mov     qword ptr [rcx+28h], 0
0x14000b07d  mov     r14, rdx
0x14000b080  mov     rdi, rcx
0x14000b083  test    rbx, rbx
0x14000b086  jz      short loc_14000B0A4
0x14000b088  mov     rcx, rbx; this
0x14000b08b  call    ??1CLogConfig@CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::CLogConfig::~CLogConfig(void)
0x14000b090  mov     edx, 6E6D7377h; Tag
0x14000b095  mov     rcx, rbx; P
0x14000b098  call    cs:__imp_ExFreePoolWithTag
0x14000b09f  nop     dword ptr [rax+rax+00h]
0x14000b0a4  mov     rbx, [rdi+28h]
0x14000b0a8  mov     qword ptr [rdi+28h], 0
0x14000b0b0  test    rbx, rbx
0x14000b0b3  jz      short loc_14000B0D1
0x14000b0b5  mov     rcx, rbx; this
0x14000b0b8  call    ??1CLogConfig@CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::CLogConfig::~CLogConfig(void)
0x14000b0bd  mov     edx, 6E6D7377h; Tag
0x14000b0c2  mov     rcx, rbx; P
0x14000b0c5  call    cs:__imp_ExFreePoolWithTag
0x14000b0cc  nop     dword ptr [rax+rax+00h]
0x14000b0d1  lea     rcx, [rsp+48h+P]
0x14000b0d6  call    ??$make_unique@VCLogConfig@CWsmLogConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCLogConfig@CWsmLogConfig@@U?$default_delete@VCLogConfig@CWsmLogConfig@@@utl@@@0@XZ; utl::make_unique<CWsmLogConfig::CLogConfig,,0>(void)
0x14000b0db  mov     rbx, [rsp+48h+P]
0x14000b0e0  test    rbx, rbx
0x14000b0e3  jnz     short loc_14000B0EF
0x14000b0e5  mov     esi, 0C000009Ah
0x14000b0ea  jmp     loc_14000B1A9
0x14000b0ef  test    r14, r14
0x14000b0f2  jz      short loc_14000B135
0x14000b0f4  mov     rdx, [r14]; unsigned __int16 *
0x14000b0f7  lea     rcx, [rbx+18h]; this
0x14000b0fb  test    sil, sil
0x14000b0fe  jz      short loc_14000B107
0x14000b100  call    ?init@wsm_wstring@@IEAAJPEBG@Z; wsm_wstring::init(ushort const *)
0x14000b105  jmp     short loc_14000B113
0x14000b107  mov     rax, [rcx]
0x14000b10a  mov     rax, [rax+10h]
0x14000b10e  call    _guard_dispatch_icall
0x14000b113  mov     esi, eax
0x14000b115  test    eax, eax
0x14000b117  js      short loc_14000B188
0x14000b119  mov     rax, [rbx+20h]
0x14000b11d  test    rax, rax
0x14000b120  jz      short loc_14000B127
0x14000b122  mov     rcx, [rax]
0x14000b125  jmp     short loc_14000B129
0x14000b127  xor     ecx, ecx
0x14000b129  mov     rax, [r14+8]
0x14000b12d  mov     [rbx+10h], rax
0x14000b131  mov     [rbx+8], rcx
0x14000b135  test    rbx, rbx
0x14000b138  jz      short loc_14000B163
0x14000b13a  mov     rsi, [rdi+28h]
0x14000b13e  mov     [rdi+28h], rbx
0x14000b142  test    rsi, rsi
0x14000b145  jz      short loc_14000B163
0x14000b147  mov     rcx, rsi; this
0x14000b14a  call    ??1CLogConfig@CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::CLogConfig::~CLogConfig(void)
0x14000b14f  mov     edx, 6E6D7377h; Tag
0x14000b154  mov     rcx, rsi; P
0x14000b157  call    cs:__imp_ExFreePoolWithTag
0x14000b15e  nop     dword ptr [rax+rax+00h]
0x14000b163  lea     rdx, [rdi+10h]
0x14000b167  mov     rax, [rdx]
0x14000b16a  mov     [rdx+8], rax
0x14000b16e  mov     rcx, [rdi+28h]
0x14000b172  mov     rax, [rcx]
0x14000b175  mov     rax, [rax]
0x14000b178  call    _guard_dispatch_icall
0x14000b17d  add     rsp, 28h
0x14000b181  pop     r14
0x14000b183  pop     rdi
0x14000b184  pop     rsi
0x14000b185  pop     rbx
0x14000b186  retn
0x14000b188  test    rbx, rbx
0x14000b18b  jz      short loc_14000B1A9
0x14000b18d  mov     rcx, rbx; this
0x14000b190  call    ??1CLogConfig@CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::CLogConfig::~CLogConfig(void)
0x14000b195  mov     edx, 6E6D7377h; Tag
0x14000b19a  mov     rcx, rbx; P
0x14000b19d  call    cs:__imp_ExFreePoolWithTag
0x14000b1a4  nop     dword ptr [rax+rax+00h]
0x14000b1a9  mov     eax, esi
0x14000b1ab  jmp     short loc_14000B17D
```
