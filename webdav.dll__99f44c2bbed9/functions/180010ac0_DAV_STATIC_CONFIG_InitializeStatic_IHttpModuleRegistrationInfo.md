# DAV_STATIC_CONFIG::InitializeStatic(IHttpModuleRegistrationInfo *)

- ea: `0x180010ac0`
- end: `0x180010b68`
- name: `?InitializeStatic@DAV_STATIC_CONFIG@@SAJPEAVIHttpModuleRegistrationInfo@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct IHttpModuleRegistrationInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18000806c`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x18001094c`
- `0x180010ac0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010af2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010af2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010ae2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010aec`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010ae2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180010aec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010b27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010b30`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010b27`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180010b30`

## pseudocode

```c
__int64 __fastcall DAV_STATIC_CONFIG::InitializeStatic(struct IHttpModuleRegistrationInfo *a1)
{
  STRU *v2; // rax
  STRU *v3; // rbx
  DWORD CurrentProcessId; // eax
  DAV_STATIC_CONFIG *v5; // rcx
  int v6; // edi
  STRU *v7; // rbx

  v2 = (STRU *)operator new(0x78u);
  v3 = v2;
  if ( v2 )
  {
    STRU::STRU(v2);
    STRU::STRU((STRU *)((char *)v3 + 56));
    CurrentProcessId = GetCurrentProcessId();
    *((_DWORD *)v3 + 29) = 0;
    *((_DWORD *)v3 + 28) = CurrentProcessId;
    DAV_STATIC_CONFIG::sm_StaticConfig = v3;
    v6 = DAV_STATIC_CONFIG::Initialize(v5, a1);
    if ( v6 < 0 )
    {
      v7 = (STRU *)DAV_STATIC_CONFIG::sm_StaticConfig;
      if ( DAV_STATIC_CONFIG::sm_StaticConfig )
      {
        STRU::~STRU((STRU *)((char *)DAV_STATIC_CONFIG::sm_StaticConfig + 56));
        STRU::~STRU(v7);
        operator delete(v7);
      }
      DAV_STATIC_CONFIG::sm_StaticConfig = 0;
    }
    return (unsigned int)v6;
  }
  else
  {
    DAV_STATIC_CONFIG::sm_StaticConfig = 0;
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180010ac0  mov     [rsp+arg_0], rbx
0x180010ac5  push    rdi
0x180010ac6  sub     rsp, 20h
0x180010aca  mov     rdi, rcx
0x180010acd  mov     ecx, 78h ; 'x'; Size
0x180010ad2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010ad7  mov     rbx, rax
0x180010ada  test    rax, rax
0x180010add  jz      short loc_180010B4D
0x180010adf  mov     rcx, rax
0x180010ae2  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180010ae8  lea     rcx, [rbx+38h]
0x180010aec  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180010af2  call    cs:__imp_GetCurrentProcessId
0x180010af8  mov     rdx, rdi; struct IHttpModuleRegistrationInfo *
0x180010afb  mov     dword ptr [rbx+74h], 0
0x180010b02  mov     [rbx+70h], eax
0x180010b05  mov     cs:?sm_StaticConfig@DAV_STATIC_CONFIG@@0PEAV1@EA, rbx; DAV_STATIC_CONFIG * DAV_STATIC_CONFIG::sm_StaticConfig
0x180010b0c  call    ?Initialize@DAV_STATIC_CONFIG@@AEAAJPEAVIHttpModuleRegistrationInfo@@@Z; DAV_STATIC_CONFIG::Initialize(IHttpModuleRegistrationInfo *)
0x180010b11  mov     edi, eax
0x180010b13  test    eax, eax
0x180010b15  jns     short loc_180010B49
0x180010b17  mov     rbx, cs:?sm_StaticConfig@DAV_STATIC_CONFIG@@0PEAV1@EA; DAV_STATIC_CONFIG * DAV_STATIC_CONFIG::sm_StaticConfig
0x180010b1e  test    rbx, rbx
0x180010b21  jz      short loc_180010B3E
0x180010b23  lea     rcx, [rbx+38h]
0x180010b27  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010b2d  mov     rcx, rbx
0x180010b30  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180010b36  mov     rcx, rbx; Block
0x180010b39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010b3e  mov     cs:?sm_StaticConfig@DAV_STATIC_CONFIG@@0PEAV1@EA, 0; DAV_STATIC_CONFIG * DAV_STATIC_CONFIG::sm_StaticConfig
0x180010b49  mov     eax, edi
0x180010b4b  jmp     short loc_180010B5D
0x180010b4d  mov     cs:?sm_StaticConfig@DAV_STATIC_CONFIG@@0PEAV1@EA, 0; DAV_STATIC_CONFIG * DAV_STATIC_CONFIG::sm_StaticConfig
0x180010b58  mov     eax, 80070008h
0x180010b5d  mov     rbx, [rsp+28h+arg_0]
0x180010b62  add     rsp, 20h
0x180010b66  pop     rdi
0x180010b67  retn
```
