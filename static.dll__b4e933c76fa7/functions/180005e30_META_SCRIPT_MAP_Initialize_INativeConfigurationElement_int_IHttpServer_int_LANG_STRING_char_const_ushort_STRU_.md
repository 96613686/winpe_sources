# META_SCRIPT_MAP::Initialize(INativeConfigurationElement *,int,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x180005e30`
- end: `0x180005f12`
- name: `?Initialize@META_SCRIPT_MAP@@QEAAJPEAVINativeConfigurationElement@@HPEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `226`
- prototype: `int(META_SCRIPT_MAP *__hidden this, struct INativeConfigurationElement *, int, struct IHttpServer *, int, struct LANG_STRING *, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004704`

## callees

- `0x180001358`
- `0x180004528`
- `0x180005e30`
- `0x180005f18`
- `0x1800066b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005e8f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005e8f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005e69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005e69`

## pseudocode

```c
__int64 __fastcall META_SCRIPT_MAP::Initialize(
        META_SCRIPT_MAP *this,
        struct INativeConfigurationElement *a2,
        int a3,
        struct IHttpServer *a4)
{
  struct META_SCRIPT_MAP_TABLE **v5; // rbx
  bool v7; // zf
  struct META_SCRIPT_MAP_TABLE *v8; // rax
  struct IHttpServer *v9; // r8
  int v10; // r9d
  int v11; // edi
  struct LANG_STRING *v13; // [rsp+20h] [rbp-38h]
  const char *v14; // [rsp+28h] [rbp-30h]
  unsigned int v15; // [rsp+30h] [rbp-28h]
  struct STRU *v16; // [rsp+38h] [rbp-20h]
  struct IHttpTraceContext *v17; // [rsp+40h] [rbp-18h]

  *(_DWORD *)this = a3;
  v5 = (struct META_SCRIPT_MAP_TABLE **)((char *)this + 8);
  if ( a3 )
  {
    v7 = META_SCRIPT_MAP_TABLE::sm_pGlobalTable == 0;
    *v5 = 0;
    if ( !v7 )
    {
      AcquireSRWLockShared(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
      if ( META_SCRIPT_MAP_TABLE::sm_pGlobalTable )
      {
        _InterlockedIncrement((volatile signed __int32 *)META_SCRIPT_MAP_TABLE::sm_pGlobalTable);
        *v5 = META_SCRIPT_MAP_TABLE::sm_pGlobalTable;
      }
      ReleaseSRWLockShared(&META_SCRIPT_MAP_TABLE::sm_GlobalLock);
    }
    if ( *v5 )
      return 0;
  }
  v8 = (struct META_SCRIPT_MAP_TABLE *)operator new(0x28u);
  if ( !v8 )
  {
    v11 = -2147024888;
    goto LABEL_14;
  }
  *(_DWORD *)v8 = 1;
  *((_QWORD *)v8 + 2) = (char *)v8 + 8;
  *((_QWORD *)v8 + 1) = (char *)v8 + 8;
  *((_QWORD *)v8 + 4) = (char *)v8 + 24;
  *((_QWORD *)v8 + 3) = (char *)v8 + 24;
  *v5 = v8;
  v11 = META_SCRIPT_MAP_TABLE::Initialize(v8, a2, v9, v10, v13, v14, v15, v16, v17);
  if ( v11 >= 0 )
  {
    if ( a3 )
      META_SCRIPT_MAP_TABLE::SetGlobalTable(v5);
    return 0;
  }
  META_SCRIPT_MAP_TABLE::Dereference(*v5);
LABEL_14:
  *v5 = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005e30  mov     [rsp+arg_0], rbx
0x180005e35  mov     [rsp+arg_8], rsi
0x180005e3a  push    rdi
0x180005e3b  sub     rsp, 50h
0x180005e3f  mov     [rcx], r8d
0x180005e42  mov     esi, r8d
0x180005e45  lea     rbx, [rcx+8]
0x180005e49  mov     rdi, rdx
0x180005e4c  test    r8d, r8d
0x180005e4f  jz      short loc_180005E9B
0x180005e51  cmp     cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA, 0; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180005e59  mov     qword ptr [rbx], 0
0x180005e60  jz      short loc_180005E95
0x180005e62  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180005e69  call    cs:__imp_AcquireSRWLockShared
0x180005e6f  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180005e76  test    rax, rax
0x180005e79  jz      short loc_180005E88
0x180005e7b  lock inc dword ptr [rax]
0x180005e7e  mov     rax, cs:?sm_pGlobalTable@META_SCRIPT_MAP_TABLE@@0PEAV1@EA; META_SCRIPT_MAP_TABLE * META_SCRIPT_MAP_TABLE::sm_pGlobalTable
0x180005e85  mov     [rbx], rax
0x180005e88  lea     rcx, ?sm_GlobalLock@META_SCRIPT_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180005e8f  call    cs:__imp_ReleaseSRWLockShared
0x180005e95  cmp     qword ptr [rbx], 0
0x180005e99  jnz     short loc_180005EF0
0x180005e9b  mov     ecx, 28h ; '('; Size
0x180005ea0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ea5  test    rax, rax
0x180005ea8  jz      short loc_180005EF4
0x180005eaa  mov     dword ptr [rax], 1
0x180005eb0  lea     rcx, [rax+8]
0x180005eb4  mov     [rcx+8], rcx
0x180005eb8  mov     rdx, rdi; struct INativeConfigurationElement *
0x180005ebb  mov     [rcx], rcx
0x180005ebe  lea     rcx, [rax+18h]
0x180005ec2  mov     [rcx+8], rcx
0x180005ec6  mov     [rcx], rcx
0x180005ec9  mov     rcx, rax; this
0x180005ecc  mov     [rbx], rax
0x180005ecf  call    ?Initialize@META_SCRIPT_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@PEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z; META_SCRIPT_MAP_TABLE::Initialize(INativeConfigurationElement *,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)
0x180005ed4  mov     edi, eax
0x180005ed6  test    eax, eax
0x180005ed8  jns     short loc_180005EE4
0x180005eda  mov     rcx, [rbx]; this
0x180005edd  call    ?Dereference@META_SCRIPT_MAP_TABLE@@QEAAXXZ; META_SCRIPT_MAP_TABLE::Dereference(void)
0x180005ee2  jmp     short loc_180005EF9
0x180005ee4  test    esi, esi
0x180005ee6  jz      short loc_180005EF0
0x180005ee8  mov     rcx, rbx; struct META_SCRIPT_MAP_TABLE **
0x180005eeb  call    ?SetGlobalTable@META_SCRIPT_MAP_TABLE@@SAXPEAPEAV1@@Z; META_SCRIPT_MAP_TABLE::SetGlobalTable(META_SCRIPT_MAP_TABLE * *)
0x180005ef0  xor     eax, eax
0x180005ef2  jmp     short loc_180005F02
0x180005ef4  mov     edi, 80070008h
0x180005ef9  mov     qword ptr [rbx], 0
0x180005f00  mov     eax, edi
0x180005f02  mov     rbx, [rsp+58h+arg_0]
0x180005f07  mov     rsi, [rsp+58h+arg_8]
0x180005f0c  add     rsp, 50h
0x180005f10  pop     rdi
0x180005f11  retn
```
