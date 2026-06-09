# CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(_WSM_TRACKING_PATH_INFO * const,bool,CWsmTrackingConfig::CTrackingPathInfo * *)

- ea: `0x14000a8c4`
- end: `0x14000a976`
- name: `?CreateInstance@CTrackingPathInfo@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_PATH_INFO@@_NPEAPEAV12@@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct _WSM_TRACKING_PATH_INFO *const, bool, struct CWsmTrackingConfig::CTrackingPathInfo **)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000960c`
- `0x14000a0fc`
- `0x14000ab4c`
- `0x14000c6f0`

## callees

- `0x1400091cc`
- `0x140009368`
- `0x14000a8c4`
- `0x14000adb8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a952`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a952`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingPathInfo::CreateInstance(
        const unsigned __int16 **a1,
        const struct std::nothrow_t *a2,
        struct CWsmTrackingConfig::CTrackingPathInfo **a3)
{
  bool v5; // di
  char *v6; // rax
  struct CWsmTrackingConfig::CTrackingPathInfo *v7; // rbx
  __int64 result; // rax
  unsigned int v9; // edi

  v5 = (char)a2;
  v6 = (char *)operator new(0x60u, a2);
  v7 = (struct CWsmTrackingConfig::CTrackingPathInfo *)v6;
  if ( !v6 )
    return 3221225626LL;
  *(_QWORD *)v6 = &CWsmTrackingConfig::CTrackingPathInfo::`vftable';
  *((_QWORD *)v6 + 1) = -1;
  *((_QWORD *)v6 + 2) = -1;
  *((_QWORD *)v6 + 3) = -1;
  *((_QWORD *)v6 + 4) = &wsm_stable_path::`vftable';
  *((_QWORD *)v6 + 6) = -1;
  *((_QWORD *)v6 + 7) = -1;
  *((_QWORD *)v6 + 8) = -1;
  *((_QWORD *)v6 + 5) = 0;
  *(_OWORD *)(v6 + 72) = 0;
  *((_QWORD *)v6 + 11) = 0;
  result = CWsmTrackingConfig::CTrackingPathInfo::Initialize((CWsmTrackingConfig::CTrackingPathInfo *)v6, a1, v5);
  v9 = result;
  if ( (int)result >= 0 )
  {
    *a3 = v7;
  }
  else
  {
    CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo((void ***)v7);
    ExFreePoolWithTag(v7, 0x6E6D7377u);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x14000a8c4  push    rbx
0x14000a8c6  push    rbp
0x14000a8c7  push    rsi
0x14000a8c8  push    rdi
0x14000a8c9  sub     rsp, 28h
0x14000a8cd  mov     rbp, rcx
0x14000a8d0  mov     rsi, r8
0x14000a8d3  mov     ecx, 60h ; '`'; NumberOfBytes
0x14000a8d8  mov     dil, dl
0x14000a8db  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000a8e0  mov     rbx, rax
0x14000a8e3  test    rax, rax
0x14000a8e6  jz      short loc_14000A967
0x14000a8e8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000a8ec  lea     rax, ??_7CTrackingPathInfo@CWsmTrackingConfig@@6B@; const CWsmTrackingConfig::CTrackingPathInfo::`vftable'
0x14000a8f3  mov     [rbx], rax
0x14000a8f6  xorps   xmm0, xmm0
0x14000a8f9  mov     [rbx+8], rcx
0x14000a8fd  lea     rax, ??_7wsm_stable_path@@6B@; const wsm_stable_path::`vftable'
0x14000a904  mov     [rbx+10h], rcx
0x14000a908  mov     r8b, dil; bool
0x14000a90b  mov     [rbx+18h], rcx
0x14000a90f  mov     rdx, rbp; struct _WSM_TRACKING_PATH_INFO *
0x14000a912  mov     [rbx+20h], rax
0x14000a916  xor     eax, eax
0x14000a918  mov     [rbx+30h], rcx
0x14000a91c  mov     [rbx+38h], rcx
0x14000a920  mov     [rbx+40h], rcx
0x14000a924  mov     rcx, rbx; this
0x14000a927  mov     qword ptr [rbx+28h], 0
0x14000a92f  movups  xmmword ptr [rbx+48h], xmm0
0x14000a933  mov     [rbx+58h], rax
0x14000a937  call    ?Initialize@CTrackingPathInfo@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_PATH_INFO@@_N@Z; CWsmTrackingConfig::CTrackingPathInfo::Initialize(_WSM_TRACKING_PATH_INFO * const,bool)
0x14000a93c  mov     edi, eax
0x14000a93e  test    eax, eax
0x14000a940  jns     short loc_14000A962
0x14000a942  mov     rcx, rbx; this
0x14000a945  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x14000a94a  mov     edx, 6E6D7377h; Tag
0x14000a94f  mov     rcx, rbx; P
0x14000a952  call    cs:__imp_ExFreePoolWithTag
0x14000a959  nop     dword ptr [rax+rax+00h]
0x14000a95e  mov     eax, edi
0x14000a960  jmp     short loc_14000A96C
0x14000a962  mov     [rsi], rbx
0x14000a965  jmp     short loc_14000A96C
0x14000a967  mov     eax, 0C000009Ah
0x14000a96c  add     rsp, 28h
0x14000a970  pop     rdi
0x14000a971  pop     rsi
0x14000a972  pop     rbp
0x14000a973  pop     rbx
0x14000a974  retn
```
