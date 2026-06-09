# META_SCRIPT_MAP::Initialize(INativeConfigurationElement *,int,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x180018d28`
- end: `0x180018e22`
- name: `?Initialize@META_SCRIPT_MAP@@QEAAJPEAVINativeConfigurationElement@@HPEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `250`
- prototype: `int(META_SCRIPT_MAP *__hidden this, struct INativeConfigurationElement *, int, struct IHttpServer *, int, struct LANG_STRING *, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180017cc8`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x1800189dc`
- `0x180018d28`
- `0x180018e28`
- `0x180019498`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018d85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180018d85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018d5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018d5f`

## pseudocode

```c
__int64 __fastcall META_SCRIPT_MAP::Initialize(
        META_SCRIPT_MAP *this,
        struct INativeConfigurationElement *a2,
        int a3,
        struct IHttpServer *a4)
{
  volatile signed __int32 **v5; // rbx
  bool v8; // zf
  volatile signed __int32 *v9; // rax
  struct IHttpServer *v10; // r8
  int v11; // r9d
  int v12; // esi
  META_SCRIPT_MAP_TABLE *v13; // rdi
  __int64 result; // rax
  struct LANG_STRING *v15; // [rsp+20h] [rbp-58h]
  const char *v16; // [rsp+28h] [rbp-50h]
  unsigned int v17; // [rsp+30h] [rbp-48h]
  struct STRU *v18; // [rsp+38h] [rbp-40h]
  struct IHttpTraceContext *v19; // [rsp+40h] [rbp-38h]

  *(_DWORD *)this = a3;
  v5 = (volatile signed __int32 **)((char *)this + 8);
  if ( a3 )
  {
    v8 = META_SCRIPT_MAP_TABLE::sm_pGlobalTable == 0;
    *v5 = 0;
    if ( !v8 )
    {
      AcquireSRWLockShared(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
      if ( META_SCRIPT_MAP_TABLE::sm_pGlobalTable )
      {
        _InterlockedIncrement((volatile signed __int32 *)META_SCRIPT_MAP_TABLE::sm_pGlobalTable);
        *v5 = (volatile signed __int32 *)META_SCRIPT_MAP_TABLE::sm_pGlobalTable;
      }
      ReleaseSRWLockShared(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
    }
    if ( *v5 )
      return 0;
  }
  v9 = (volatile signed __int32 *)operator new(0x28u);
  if ( v9 )
  {
    *v9 = 1;
    *((_QWORD *)v9 + 2) = v9 + 2;
    *((_QWORD *)v9 + 1) = v9 + 2;
    *((_QWORD *)v9 + 4) = v9 + 6;
    *((_QWORD *)v9 + 3) = v9 + 6;
    *v5 = v9;
    v12 = META_SCRIPT_MAP_TABLE::Initialize((META_SCRIPT_MAP_TABLE *)v9, a2, v10, v11, v15, v16, v17, v18, v19);
    if ( v12 < 0 )
    {
      v13 = (META_SCRIPT_MAP_TABLE *)*v5;
      if ( _InterlockedExchangeAdd(*v5, 0xFFFFFFFF) == 1 )
      {
        if ( v13 )
        {
          META_SCRIPT_MAP_TABLE::~META_SCRIPT_MAP_TABLE(v13);
          operator delete(v13);
          v5 = (volatile signed __int32 **)((char *)this + 8);
        }
      }
      result = (unsigned int)v12;
      goto LABEL_17;
    }
    if ( a3 )
      META_SCRIPT_MAP_TABLE::SetGlobalTable((struct META_SCRIPT_MAP_TABLE **)v5);
    return 0;
  }
  result = 2147942408LL;
LABEL_17:
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x180018d28  push    rbx
0x180018d2a  push    rsi
0x180018d2b  push    rdi
0x180018d2c  push    r14
0x180018d2e  sub     rsp, 58h
0x180018d32  mov     [rcx], r8d
0x180018d35  mov     edi, r8d
0x180018d38  lea     rbx, [rcx+8]
0x180018d3c  mov     rsi, rdx
0x180018d3f  mov     r14, rcx
0x180018d42  test    r8d, r8d
0x180018d45  jz      short loc_180018D91
0x180018d47  cmp     cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA, 0; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180018d4f  mov     qword ptr [rbx], 0
0x180018d56  jz      short loc_180018D8B
0x180018d58  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180018d5f  call    cs:__imp_AcquireSRWLockShared
0x180018d65  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180018d6c  test    rax, rax
0x180018d6f  jz      short loc_180018D7E
0x180018d71  lock inc dword ptr [rax]
0x180018d74  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180018d7b  mov     [rbx], rax
0x180018d7e  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180018d85  call    cs:__imp_ReleaseSRWLockShared
0x180018d8b  cmp     qword ptr [rbx], 0
0x180018d8f  jnz     short loc_180018E08
0x180018d91  mov     ecx, 28h ; '('; Size
0x180018d96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018d9b  test    rax, rax
0x180018d9e  jz      short loc_180018E0C
0x180018da0  lea     rcx, [rax+8]
0x180018da4  mov     dword ptr [rax], 1
0x180018daa  mov     [rcx+8], rcx
0x180018dae  mov     rdx, rsi; struct INativeConfigurationElement *
0x180018db1  mov     [rcx], rcx
0x180018db4  lea     rcx, [rax+18h]
0x180018db8  mov     [rcx+8], rcx
0x180018dbc  mov     [rcx], rcx
0x180018dbf  mov     rcx, rax; this
0x180018dc2  mov     [rbx], rax
0x180018dc5  call    ?Initialize@META_SCRIPT_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@PEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z; META_SCRIPT_MAP_TABLE::Initialize(INativeConfigurationElement *,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)
0x180018dca  mov     esi, eax
0x180018dcc  test    eax, eax
0x180018dce  jns     short loc_180018DFC
0x180018dd0  mov     rdi, [rbx]
0x180018dd3  or      edx, 0FFFFFFFFh
0x180018dd6  lock xadd [rdi], edx
0x180018dda  cmp     edx, 1
0x180018ddd  jnz     short loc_180018DF8
0x180018ddf  test    rdi, rdi
0x180018de2  jz      short loc_180018DF8
0x180018de4  mov     rcx, rdi; this
0x180018de7  call    ??1META_SCRIPT_MAP_TABLE@@AEAA@XZ; META_SCRIPT_MAP_TABLE::~META_SCRIPT_MAP_TABLE(void)
0x180018dec  mov     rcx, rdi; Block
0x180018def  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180018df4  lea     rbx, [r14+8]
0x180018df8  mov     eax, esi
0x180018dfa  jmp     short loc_180018E11
0x180018dfc  test    edi, edi
0x180018dfe  jz      short loc_180018E08
0x180018e00  mov     rcx, rbx; struct META_SCRIPT_MAP_TABLE **
0x180018e03  call    ?SetGlobalTable@META_SCRIPT_MAP_TABLE@@SAXPEAPEAV1@@Z; META_SCRIPT_MAP_TABLE::SetGlobalTable(META_SCRIPT_MAP_TABLE * *)
0x180018e08  xor     eax, eax
0x180018e0a  jmp     short loc_180018E18
0x180018e0c  mov     eax, 80070008h
0x180018e11  mov     qword ptr [rbx], 0
0x180018e18  add     rsp, 58h
0x180018e1c  pop     r14
0x180018e1e  pop     rdi
0x180018e1f  pop     rsi
0x180018e20  pop     rbx
0x180018e21  retn
```
