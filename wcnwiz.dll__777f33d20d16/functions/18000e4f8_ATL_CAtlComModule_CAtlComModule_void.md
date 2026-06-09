# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000e4f8`
- end: `0x18000e568`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800303f0`

## callees

- `0x18000e4f8`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e54c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e54c`

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
0x18000e4f8  mov     [rsp+arg_0], rbx
0x18000e4fd  mov     [rsp+arg_8], rsi
0x18000e502  push    rdi
0x18000e503  sub     rsp, 20h
0x18000e507  cmp     dword ptr [rcx], 0
0x18000e50a  mov     rbx, rcx
0x18000e50d  jz      short loc_18000E558
0x18000e50f  mov     rdi, [rcx+10h]
0x18000e513  cmp     rdi, [rcx+18h]
0x18000e517  jnb     short loc_18000E548
0x18000e519  mov     rsi, [rdi]
0x18000e51c  test    rsi, rsi
0x18000e51f  jz      short loc_18000E53E
0x18000e521  mov     rcx, [rsi+20h]
0x18000e525  test    rcx, rcx
0x18000e528  jz      short loc_18000E536
0x18000e52a  mov     rax, [rcx]
0x18000e52d  mov     rax, [rax+10h]
0x18000e531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e536  mov     qword ptr [rsi+20h], 0
0x18000e53e  add     rdi, 8
0x18000e542  cmp     rdi, [rbx+18h]
0x18000e546  jb      short loc_18000E519
0x18000e548  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000e54c  call    cs:__imp_DeleteCriticalSection
0x18000e552  mov     dword ptr [rbx], 0
0x18000e558  mov     rbx, [rsp+28h+arg_0]
0x18000e55d  mov     rsi, [rsp+28h+arg_8]
0x18000e562  add     rsp, 20h
0x18000e566  pop     rdi
0x18000e567  retn
```
