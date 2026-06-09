# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180001ac0`
- end: `0x180001b31`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b350`

## callees

- `0x180001ac0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001b1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180001b1a`

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
0x180001ac0  push    rbx
0x180001ac2  sub     rsp, 20h
0x180001ac6  cmp     dword ptr [rcx], 0
0x180001ac9  mov     rbx, rcx
0x180001acc  jz      short loc_180001B2B
0x180001ace  mov     [rsp+28h+arg_8], rdi
0x180001ad3  mov     rdi, [rcx+10h]
0x180001ad7  cmp     rdi, [rcx+18h]
0x180001adb  jnb     short loc_180001B16
0x180001add  mov     [rsp+28h+arg_0], rsi
0x180001ae2  mov     rsi, [rdi]
0x180001ae5  test    rsi, rsi
0x180001ae8  jz      short loc_180001B07
0x180001aea  mov     rcx, [rsi+20h]
0x180001aee  test    rcx, rcx
0x180001af1  jz      short loc_180001AFF
0x180001af3  mov     rax, [rcx]
0x180001af6  mov     rax, [rax+10h]
0x180001afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001aff  mov     qword ptr [rsi+20h], 0
0x180001b07  add     rdi, 8
0x180001b0b  cmp     rdi, [rbx+18h]
0x180001b0f  jb      short loc_180001AE2
0x180001b11  mov     rsi, [rsp+28h+arg_0]
0x180001b16  lea     rcx, [rbx+20h]; lpCriticalSection
0x180001b1a  call    cs:__imp_DeleteCriticalSection
0x180001b20  mov     rdi, [rsp+28h+arg_8]
0x180001b25  mov     dword ptr [rbx], 0
0x180001b2b  add     rsp, 20h
0x180001b2f  pop     rbx
0x180001b30  retn
```
