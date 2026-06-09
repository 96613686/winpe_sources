# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180033888`
- end: `0x1800338f8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180036c40`

## callees

- `0x180033888`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800338dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800338dc`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  __int64 *i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 2); (unsigned __int64)i < *((_QWORD *)this + 3); ++i )
    {
      v3 = *i;
      if ( *i )
      {
        v4 = *(_QWORD *)(v3 + 32);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *(_QWORD *)(v3 + 32) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180033888  mov     [rsp+arg_0], rbx
0x18003388d  mov     [rsp+arg_8], rsi
0x180033892  push    rdi
0x180033893  sub     rsp, 20h
0x180033897  cmp     dword ptr [rcx], 0
0x18003389a  mov     rbx, rcx
0x18003389d  jz      short loc_1800338E8
0x18003389f  mov     rdi, [rcx+10h]
0x1800338a3  cmp     rdi, [rcx+18h]
0x1800338a7  jnb     short loc_1800338D8
0x1800338a9  mov     rsi, [rdi]
0x1800338ac  test    rsi, rsi
0x1800338af  jz      short loc_1800338CE
0x1800338b1  mov     rcx, [rsi+20h]
0x1800338b5  test    rcx, rcx
0x1800338b8  jz      short loc_1800338C6
0x1800338ba  mov     rax, [rcx]
0x1800338bd  mov     rax, [rax+10h]
0x1800338c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338c6  mov     qword ptr [rsi+20h], 0
0x1800338ce  add     rdi, 8
0x1800338d2  cmp     rdi, [rbx+18h]
0x1800338d6  jb      short loc_1800338A9
0x1800338d8  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800338dc  call    cs:__imp_DeleteCriticalSection
0x1800338e2  mov     dword ptr [rbx], 0
0x1800338e8  mov     rbx, [rsp+28h+arg_0]
0x1800338ed  mov     rsi, [rsp+28h+arg_8]
0x1800338f2  add     rsp, 20h
0x1800338f6  pop     rdi
0x1800338f7  retn
```
