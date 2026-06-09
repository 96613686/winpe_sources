# MIME_MAP::Initialize(INativeConfigurationElement *,int)

- ea: `0x18001863c`
- end: `0x18001876f`
- name: `?Initialize@MIME_MAP@@QEAAJPEAVINativeConfigurationElement@@H@Z`
- size: `307`
- prototype: `int(MIME_MAP *__hidden this, struct INativeConfigurationElement *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180017cc8`

## callees

- `0x1800011d4`
- `0x18001863c`
- `0x180018778`
- `0x180018908`
- `0x1800224c2`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800186a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800186a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001867c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001867c`

## pseudocode

```c
__int64 __fastcall MIME_MAP::Initialize(MIME_MAP *this, struct INativeConfigurationElement *a2, int a3)
{
  struct MIME_MAP_TABLE **v4; // rbx
  bool v7; // zf
  _DWORD *v8; // rax
  struct MIME_MAP_TABLE *v9; // rdi
  int v10; // edi
  struct MIME_MAP_TABLE *v11; // rcx
  __int64 result; // rax

  *((_DWORD *)this + 2) = a3;
  v4 = (struct MIME_MAP_TABLE **)((char *)this + 16);
  if ( a3 )
  {
    v7 = MIME_MAP_TABLE::sm_pGlobalTable == 0;
    *v4 = 0;
    if ( !v7 )
    {
      AcquireSRWLockShared(&MIME_MAP_TABLE::sm_GlobalLock);
      if ( MIME_MAP_TABLE::sm_pGlobalTable )
      {
        _InterlockedIncrement((volatile signed __int32 *)MIME_MAP_TABLE::sm_pGlobalTable + 266);
        *v4 = MIME_MAP_TABLE::sm_pGlobalTable;
      }
      ReleaseSRWLockShared(&MIME_MAP_TABLE::sm_GlobalLock);
    }
    if ( *v4 )
      return 0;
  }
  v8 = operator new(0x430u);
  v9 = (struct MIME_MAP_TABLE *)v8;
  if ( v8 )
  {
    v8[264] = 0;
    memset_0(v8 + 2, 0, 0x418u);
    *((_DWORD *)v9 + 266) = 1;
    *(_QWORD *)v9 = &MIME_MAP_TABLE::`vftable';
    *v4 = v9;
    v10 = MIME_MAP_TABLE::Initialize(v9, a2);
    if ( v10 < 0 )
    {
      v11 = *v4;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v4 + 266, 0xFFFFFFFF) == 1 )
      {
        if ( v11 )
        {
          (**(void (__fastcall ***)(struct MIME_MAP_TABLE *, __int64))v11)(v11, 1);
          v4 = (struct MIME_MAP_TABLE **)((char *)this + 16);
        }
      }
      result = (unsigned int)v10;
      goto LABEL_17;
    }
    if ( a3 )
      MIME_MAP_TABLE::SetGlobalTable(v4);
    return 0;
  }
  result = 2147942408LL;
LABEL_17:
  *v4 = 0;
  return result;
}

```

## disassembly

```asm
0x18001863c  mov     [rsp+arg_0], rbx
0x180018641  mov     [rsp+arg_8], rbp
0x180018646  push    rsi
0x180018647  push    rdi
0x180018648  push    r14
0x18001864a  sub     rsp, 20h
0x18001864e  mov     [rcx+8], r8d
0x180018652  mov     esi, r8d
0x180018655  lea     rbx, [rcx+10h]
0x180018659  mov     r14, rdx
0x18001865c  mov     rbp, rcx
0x18001865f  test    r8d, r8d
0x180018662  jz      short loc_1800186B6
0x180018664  cmp     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x18001866c  mov     qword ptr [rbx], 0
0x180018673  jz      short loc_1800186AC
0x180018675  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x18001867c  call    cs:__imp_AcquireSRWLockShared
0x180018682  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180018689  test    rax, rax
0x18001868c  jz      short loc_18001869F
0x18001868e  lock inc dword ptr [rax+428h]
0x180018695  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x18001869c  mov     [rbx], rax
0x18001869f  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x1800186a6  call    cs:__imp_ReleaseSRWLockShared
0x1800186ac  cmp     qword ptr [rbx], 0
0x1800186b0  jnz     loc_18001874C
0x1800186b6  mov     ecx, 430h; Size
0x1800186bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800186c0  mov     rdi, rax
0x1800186c3  test    rax, rax
0x1800186c6  jz      loc_180018750
0x1800186cc  lea     rcx, [rax+8]; void *
0x1800186d0  xor     edx, edx; Val
0x1800186d2  mov     r8d, 418h; Size
0x1800186d8  mov     dword ptr [rcx+418h], 0
0x1800186e2  call    memset_0
0x1800186e7  lea     rax, ??_7MIME_MAP_TABLE@@6B@; const MIME_MAP_TABLE::`vftable'
0x1800186ee  mov     dword ptr [rdi+428h], 1
0x1800186f8  mov     [rdi], rax
0x1800186fb  mov     rdx, r14; struct INativeConfigurationElement *
0x1800186fe  mov     rcx, rdi; this
0x180018701  mov     [rbx], rdi
0x180018704  call    ?Initialize@MIME_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@@Z; MIME_MAP_TABLE::Initialize(INativeConfigurationElement *)
0x180018709  mov     edi, eax
0x18001870b  test    eax, eax
0x18001870d  jns     short loc_180018740
0x18001870f  mov     rcx, [rbx]
0x180018712  or      r8d, 0FFFFFFFFh
0x180018716  lock xadd [rcx+428h], r8d
0x18001871f  cmp     r8d, 1
0x180018723  jnz     short loc_18001873C
0x180018725  test    rcx, rcx
0x180018728  jz      short loc_18001873C
0x18001872a  mov     rax, [rcx]
0x18001872d  mov     edx, r8d
0x180018730  mov     rax, [rax]
0x180018733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018738  lea     rbx, [rbp+10h]
0x18001873c  mov     eax, edi
0x18001873e  jmp     short loc_180018755
0x180018740  test    esi, esi
0x180018742  jz      short loc_18001874C
0x180018744  mov     rcx, rbx; struct MIME_MAP_TABLE **
0x180018747  call    ?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z; MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)
0x18001874c  xor     eax, eax
0x18001874e  jmp     short loc_18001875C
0x180018750  mov     eax, 80070008h
0x180018755  mov     qword ptr [rbx], 0
0x18001875c  mov     rbx, [rsp+38h+arg_0]
0x180018761  mov     rbp, [rsp+38h+arg_8]
0x180018766  add     rsp, 20h
0x18001876a  pop     r14
0x18001876c  pop     rdi
0x18001876d  pop     rsi
0x18001876e  retn
```
