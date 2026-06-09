# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180011e28`
- end: `0x180011e9f`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013360`

## callees

- `0x180011e28`
- `0x180014010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011e7c`
- `KERNEL32!DeleteCriticalSection` at `0x180011e7c`

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
0x180011e28  mov     [rsp+arg_0], rbx
0x180011e2d  mov     [rsp+arg_8], rsi
0x180011e32  push    rdi
0x180011e33  sub     rsp, 20h
0x180011e37  cmp     dword ptr [rcx], 0
0x180011e3a  mov     rbx, rcx
0x180011e3d  jz      short loc_180011E8E
0x180011e3f  mov     rdi, [rcx+10h]
0x180011e43  cmp     rdi, [rcx+18h]
0x180011e47  jnb     short loc_180011E78
0x180011e49  mov     rsi, [rdi]
0x180011e4c  test    rsi, rsi
0x180011e4f  jz      short loc_180011E6E
0x180011e51  mov     rcx, [rsi+20h]
0x180011e55  test    rcx, rcx
0x180011e58  jz      short loc_180011E66
0x180011e5a  mov     rax, [rcx]
0x180011e5d  mov     rax, [rax+10h]
0x180011e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e66  mov     qword ptr [rsi+20h], 0
0x180011e6e  add     rdi, 8
0x180011e72  cmp     rdi, [rbx+18h]
0x180011e76  jb      short loc_180011E49
0x180011e78  lea     rcx, [rbx+20h]; lpCriticalSection
0x180011e7c  call    cs:__imp_DeleteCriticalSection
0x180011e83  nop     dword ptr [rax+rax+00h]
0x180011e88  mov     dword ptr [rbx], 0
0x180011e8e  mov     rbx, [rsp+28h+arg_0]
0x180011e93  mov     rsi, [rsp+28h+arg_8]
0x180011e98  add     rsp, 20h
0x180011e9c  pop     rdi
0x180011e9d  retn
```
