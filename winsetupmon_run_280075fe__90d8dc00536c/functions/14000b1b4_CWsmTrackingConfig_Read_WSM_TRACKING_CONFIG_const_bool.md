# CWsmTrackingConfig::Read(_WSM_TRACKING_CONFIG * const,bool)

- ea: `0x14000b1b4`
- end: `0x14000b277`
- name: `?Read@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z`
- size: `195`
- prototype: `int(CWsmTrackingConfig *__hidden this, struct _WSM_TRACKING_CONFIG *const, bool)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400099e0`
- `0x140009ee0`
- `0x14000a300`
- `0x14000b550`
- `0x14000b970`
- `0x14000bdf0`

## callees

- `0x140008b00`
- `0x140009018`
- `0x14000a728`
- `0x14000b1b4`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b1eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b23e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b1eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b23e`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::Read(CWsmTrackingConfig *this, struct _WSM_TRACKING_CONFIG *const a2, bool a3)
{
  _QWORD *v3; // rdi
  void ***v5; // rbx
  struct CWsmTrackingConfig::CTrackingConfig **v8; // rax
  int Instance; // esi
  void ***v10; // rbx
  void ***v12; // [rsp+20h] [rbp-48h] BYREF
  void ****v13; // [rsp+28h] [rbp-40h]

  v3 = (_QWORD *)((char *)this + 40);
  v5 = (void ***)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v5 )
  {
    CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v5);
    ExFreePoolWithTag(v5, 0x6E6D7377u);
  }
  v8 = (struct CWsmTrackingConfig::CTrackingConfig **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingConfig,utl::default_delete<CWsmTrackingConfig::CTrackingConfig>>,>(
                                                        &v12,
                                                        v3);
  Instance = CWsmTrackingConfig::CTrackingConfig::CreateInstance(a2, a3, v8);
  if ( v12 )
  {
    v10 = *v13;
    *v13 = v12;
    if ( v10 )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v10);
      ExFreePoolWithTag(v10, 0x6E6D7377u);
    }
  }
  if ( Instance < 0 )
    return (unsigned int)Instance;
  *((_QWORD *)this + 3) = *((_QWORD *)this + 2);
  return (**(__int64 (__fastcall ***)(_QWORD))*v3)(*v3);
}

```

## disassembly

```asm
0x14000b1b4  push    rbx
0x14000b1b6  push    rbp
0x14000b1b7  push    rsi
0x14000b1b8  push    rdi
0x14000b1b9  push    r14
0x14000b1bb  sub     rsp, 40h
0x14000b1bf  lea     rdi, [rcx+28h]
0x14000b1c3  mov     sil, r8b
0x14000b1c6  mov     rbx, [rdi]
0x14000b1c9  mov     r14, rdx
0x14000b1cc  mov     qword ptr [rdi], 0
0x14000b1d3  mov     rbp, rcx
0x14000b1d6  test    rbx, rbx
0x14000b1d9  jz      short loc_14000B1F7
0x14000b1db  mov     rcx, rbx; this
0x14000b1de  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000b1e3  mov     edx, 6E6D7377h; Tag
0x14000b1e8  mov     rcx, rbx; P
0x14000b1eb  call    cs:__imp_ExFreePoolWithTag
0x14000b1f2  nop     dword ptr [rax+rax+00h]
0x14000b1f7  mov     rdx, rdi
0x14000b1fa  lea     rcx, [rsp+68h+var_48]
0x14000b1ff  call    ??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000b204  mov     r8, rax; struct CWsmTrackingConfig::CTrackingConfig **
0x14000b207  mov     dl, sil; bool
0x14000b20a  mov     rcx, r14; struct _WSM_TRACKING_CONFIG *
0x14000b20d  call    ?CreateInstance@CTrackingConfig@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_CONFIG@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingConfig::CreateInstance(_WSM_TRACKING_CONFIG * const,bool,CWsmTrackingConfig::CTrackingConfig * *)
0x14000b212  mov     esi, eax
0x14000b214  mov     rax, [rsp+68h+var_48]
0x14000b219  test    rax, rax
0x14000b21c  jz      short loc_14000B24A
0x14000b21e  mov     r8, [rsp+68h+var_40]
0x14000b223  mov     rbx, [r8]
0x14000b226  mov     [r8], rax
0x14000b229  test    rbx, rbx
0x14000b22c  jz      short loc_14000B24A
0x14000b22e  mov     rcx, rbx; this
0x14000b231  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000b236  mov     edx, 6E6D7377h; Tag
0x14000b23b  mov     rcx, rbx; P
0x14000b23e  call    cs:__imp_ExFreePoolWithTag
0x14000b245  nop     dword ptr [rax+rax+00h]
0x14000b24a  test    esi, esi
0x14000b24c  jns     short loc_14000B252
0x14000b24e  mov     eax, esi
0x14000b250  jmp     short loc_14000B26B
0x14000b252  lea     rdx, [rbp+10h]
0x14000b256  mov     rax, [rdx]
0x14000b259  mov     [rdx+8], rax
0x14000b25d  mov     rcx, [rdi]
0x14000b260  mov     rax, [rcx]
0x14000b263  mov     rax, [rax]
0x14000b266  call    _guard_dispatch_icall
0x14000b26b  add     rsp, 40h
0x14000b26f  pop     r14
0x14000b271  pop     rdi
0x14000b272  pop     rsi
0x14000b273  pop     rbp
0x14000b274  pop     rbx
0x14000b275  retn
```
