# MIME_MAP::Initialize(INativeConfigurationElement *,int)

- ea: `0x1800054f0`
- end: `0x1800055e0`
- name: `?Initialize@MIME_MAP@@QEAAJPEAVINativeConfigurationElement@@H@Z`
- size: `240`
- prototype: `int(MIME_MAP *__hidden this, struct INativeConfigurationElement *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180004704`

## callees

- `0x180001010`
- `0x180001358`
- `0x18000455c`
- `0x1800054f0`
- `0x180005700`
- `0x1800067c6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000554e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000554e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005524`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005524`

## pseudocode

```c
__int64 __fastcall MIME_MAP::Initialize(MIME_MAP *this, struct INativeConfigurationElement *a2, int a3)
{
  struct MIME_MAP_TABLE **v4; // rbx
  bool v6; // zf
  _DWORD *v7; // rax
  struct MIME_MAP_TABLE *v8; // rdi
  int v9; // edi

  *((_DWORD *)this + 2) = a3;
  v4 = (struct MIME_MAP_TABLE **)((char *)this + 16);
  if ( a3 )
  {
    v6 = MIME_MAP_TABLE::sm_pGlobalTable == 0;
    *v4 = 0;
    if ( !v6 )
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
  v7 = operator new(0x430u);
  v8 = (struct MIME_MAP_TABLE *)v7;
  if ( !v7 )
  {
    v9 = -2147024888;
    goto LABEL_14;
  }
  v7[264] = 0;
  memset_0(v7 + 2, 0, 0x418u);
  *((_DWORD *)v8 + 266) = 1;
  *(_QWORD *)v8 = &MIME_MAP_TABLE::`vftable';
  *v4 = v8;
  v9 = MIME_MAP_TABLE::Initialize(v8, a2);
  if ( v9 >= 0 )
  {
    if ( a3 )
      MIME_MAP_TABLE::SetGlobalTable(v4);
    return 0;
  }
  MIME_MAP_TABLE::Dereference(*v4);
LABEL_14:
  *v4 = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800054f0  push    rbx
0x1800054f2  push    rbp
0x1800054f3  push    rsi
0x1800054f4  push    rdi
0x1800054f5  sub     rsp, 28h
0x1800054f9  mov     [rcx+8], r8d
0x1800054fd  mov     esi, r8d
0x180005500  lea     rbx, [rcx+10h]
0x180005504  mov     rbp, rdx
0x180005507  test    r8d, r8d
0x18000550a  jz      short loc_18000555A
0x18000550c  cmp     cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA, 0; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180005514  mov     qword ptr [rbx], 0
0x18000551b  jz      short loc_180005554
0x18000551d  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180005524  call    cs:__imp_AcquireSRWLockShared
0x18000552a  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180005531  test    rax, rax
0x180005534  jz      short loc_180005547
0x180005536  lock inc dword ptr [rax+428h]
0x18000553d  mov     rax, cs:?sm_pGlobalTable@MIME_MAP_TABLE@@0PEAV1@EA; MIME_MAP_TABLE * MIME_MAP_TABLE::sm_pGlobalTable
0x180005544  mov     [rbx], rax
0x180005547  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x18000554e  call    cs:__imp_ReleaseSRWLockShared
0x180005554  cmp     qword ptr [rbx], 0
0x180005558  jnz     short loc_1800055C5
0x18000555a  mov     ecx, 430h; Size
0x18000555f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005564  mov     rdi, rax
0x180005567  test    rax, rax
0x18000556a  jz      short loc_1800055C9
0x18000556c  lea     rcx, [rax+8]; void *
0x180005570  xor     edx, edx; Val
0x180005572  mov     r8d, 418h; Size
0x180005578  mov     dword ptr [rcx+418h], 0
0x180005582  call    memset_0
0x180005587  lea     rax, ??_7MIME_MAP_TABLE@@6B@; const MIME_MAP_TABLE::`vftable'
0x18000558e  mov     dword ptr [rdi+428h], 1
0x180005598  mov     [rdi], rax
0x18000559b  mov     rdx, rbp; struct INativeConfigurationElement *
0x18000559e  mov     rcx, rdi; this
0x1800055a1  mov     [rbx], rdi
0x1800055a4  call    ?Initialize@MIME_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@@Z; MIME_MAP_TABLE::Initialize(INativeConfigurationElement *)
0x1800055a9  mov     edi, eax
0x1800055ab  test    eax, eax
0x1800055ad  jns     short loc_1800055B9
0x1800055af  mov     rcx, [rbx]; this
0x1800055b2  call    ?Dereference@MIME_MAP_TABLE@@QEAAXXZ; MIME_MAP_TABLE::Dereference(void)
0x1800055b7  jmp     short loc_1800055CE
0x1800055b9  test    esi, esi
0x1800055bb  jz      short loc_1800055C5
0x1800055bd  mov     rcx, rbx; struct MIME_MAP_TABLE **
0x1800055c0  call    ?SetGlobalTable@MIME_MAP_TABLE@@SAXPEAPEAV1@@Z; MIME_MAP_TABLE::SetGlobalTable(MIME_MAP_TABLE * *)
0x1800055c5  xor     eax, eax
0x1800055c7  jmp     short loc_1800055D7
0x1800055c9  mov     edi, 80070008h
0x1800055ce  mov     qword ptr [rbx], 0
0x1800055d5  mov     eax, edi
0x1800055d7  add     rsp, 28h
0x1800055db  pop     rdi
0x1800055dc  pop     rsi
0x1800055dd  pop     rbp
0x1800055de  pop     rbx
0x1800055df  retn
```
