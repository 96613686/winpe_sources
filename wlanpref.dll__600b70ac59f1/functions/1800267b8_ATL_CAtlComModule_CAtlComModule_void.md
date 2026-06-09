# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800267b8`
- end: `0x180026828`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002f270`

## callees

- `0x1800267b8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002680c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002680c`

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
0x1800267b8  mov     [rsp+arg_0], rbx
0x1800267bd  mov     [rsp+arg_8], rsi
0x1800267c2  push    rdi
0x1800267c3  sub     rsp, 20h
0x1800267c7  cmp     dword ptr [rcx], 0
0x1800267ca  mov     rbx, rcx
0x1800267cd  jz      short loc_180026818
0x1800267cf  mov     rdi, [rcx+10h]
0x1800267d3  cmp     rdi, [rcx+18h]
0x1800267d7  jnb     short loc_180026808
0x1800267d9  mov     rsi, [rdi]
0x1800267dc  test    rsi, rsi
0x1800267df  jz      short loc_1800267FE
0x1800267e1  mov     rcx, [rsi+20h]
0x1800267e5  test    rcx, rcx
0x1800267e8  jz      short loc_1800267F6
0x1800267ea  mov     rax, [rcx]
0x1800267ed  mov     rax, [rax+10h]
0x1800267f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267f6  mov     qword ptr [rsi+20h], 0
0x1800267fe  add     rdi, 8
0x180026802  cmp     rdi, [rbx+18h]
0x180026806  jb      short loc_1800267D9
0x180026808  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002680c  call    cs:__imp_DeleteCriticalSection
0x180026812  mov     dword ptr [rbx], 0
0x180026818  mov     rbx, [rsp+28h+arg_0]
0x18002681d  mov     rsi, [rsp+28h+arg_8]
0x180026822  add     rsp, 20h
0x180026826  pop     rdi
0x180026827  retn
```
