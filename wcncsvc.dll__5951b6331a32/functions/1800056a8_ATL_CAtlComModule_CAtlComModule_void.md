# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800056a8`
- end: `0x180005718`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180059840`

## callees

- `0x1800056a8`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056fc`

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
0x1800056a8  mov     [rsp+arg_0], rbx
0x1800056ad  mov     [rsp+arg_8], rsi
0x1800056b2  push    rdi
0x1800056b3  sub     rsp, 20h
0x1800056b7  cmp     dword ptr [rcx], 0
0x1800056ba  mov     rbx, rcx
0x1800056bd  jz      short loc_180005708
0x1800056bf  mov     rdi, [rcx+10h]
0x1800056c3  cmp     rdi, [rcx+18h]
0x1800056c7  jnb     short loc_1800056F8
0x1800056c9  mov     rsi, [rdi]
0x1800056cc  test    rsi, rsi
0x1800056cf  jz      short loc_1800056EE
0x1800056d1  mov     rcx, [rsi+20h]
0x1800056d5  test    rcx, rcx
0x1800056d8  jz      short loc_1800056E6
0x1800056da  mov     rax, [rcx]
0x1800056dd  mov     rax, [rax+10h]
0x1800056e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056e6  mov     qword ptr [rsi+20h], 0
0x1800056ee  add     rdi, 8
0x1800056f2  cmp     rdi, [rbx+18h]
0x1800056f6  jb      short loc_1800056C9
0x1800056f8  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800056fc  call    cs:__imp_DeleteCriticalSection
0x180005702  mov     dword ptr [rbx], 0
0x180005708  mov     rbx, [rsp+28h+arg_0]
0x18000570d  mov     rsi, [rsp+28h+arg_8]
0x180005712  add     rsp, 20h
0x180005716  pop     rdi
0x180005717  retn
```
