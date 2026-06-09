# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180008c7c`
- end: `0x180008cf3`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ce60`

## callees

- `0x180008c7c`
- `0x18000d010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008cd0`
- `KERNEL32!DeleteCriticalSection` at `0x180008cd0`

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
0x180008c7c  mov     [rsp+arg_0], rbx
0x180008c81  mov     [rsp+arg_8], rsi
0x180008c86  push    rdi
0x180008c87  sub     rsp, 20h
0x180008c8b  cmp     dword ptr [rcx], 0
0x180008c8e  mov     rbx, rcx
0x180008c91  jz      short loc_180008CE2
0x180008c93  mov     rdi, [rcx+10h]
0x180008c97  cmp     rdi, [rcx+18h]
0x180008c9b  jnb     short loc_180008CCC
0x180008c9d  mov     rsi, [rdi]
0x180008ca0  test    rsi, rsi
0x180008ca3  jz      short loc_180008CC2
0x180008ca5  mov     rcx, [rsi+20h]
0x180008ca9  test    rcx, rcx
0x180008cac  jz      short loc_180008CBA
0x180008cae  mov     rax, [rcx]
0x180008cb1  mov     rax, [rax+10h]
0x180008cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cba  mov     qword ptr [rsi+20h], 0
0x180008cc2  add     rdi, 8
0x180008cc6  cmp     rdi, [rbx+18h]
0x180008cca  jb      short loc_180008C9D
0x180008ccc  lea     rcx, [rbx+20h]; lpCriticalSection
0x180008cd0  call    cs:__imp_DeleteCriticalSection
0x180008cd7  nop     dword ptr [rax+rax+00h]
0x180008cdc  mov     dword ptr [rbx], 0
0x180008ce2  mov     rbx, [rsp+28h+arg_0]
0x180008ce7  mov     rsi, [rsp+28h+arg_8]
0x180008cec  add     rsp, 20h
0x180008cf0  pop     rdi
0x180008cf1  retn
```
