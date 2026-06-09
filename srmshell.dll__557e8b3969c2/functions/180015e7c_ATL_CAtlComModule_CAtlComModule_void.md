# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180015e7c`
- end: `0x180015eec`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f360`

## callees

- `0x180015e7c`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015ed0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015ed0`

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
0x180015e7c  mov     [rsp+arg_0], rbx
0x180015e81  mov     [rsp+arg_8], rsi
0x180015e86  push    rdi
0x180015e87  sub     rsp, 20h
0x180015e8b  cmp     dword ptr [rcx], 0
0x180015e8e  mov     rbx, rcx
0x180015e91  jz      short loc_180015EDC
0x180015e93  mov     rdi, [rcx+10h]
0x180015e97  cmp     rdi, [rcx+18h]
0x180015e9b  jnb     short loc_180015ECC
0x180015e9d  mov     rsi, [rdi]
0x180015ea0  test    rsi, rsi
0x180015ea3  jz      short loc_180015EC2
0x180015ea5  mov     rcx, [rsi+20h]
0x180015ea9  test    rcx, rcx
0x180015eac  jz      short loc_180015EBA
0x180015eae  mov     rax, [rcx]
0x180015eb1  mov     rax, [rax+10h]
0x180015eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eba  mov     qword ptr [rsi+20h], 0
0x180015ec2  add     rdi, 8
0x180015ec6  cmp     rdi, [rbx+18h]
0x180015eca  jb      short loc_180015E9D
0x180015ecc  lea     rcx, [rbx+20h]; lpCriticalSection
0x180015ed0  call    cs:__imp_DeleteCriticalSection
0x180015ed6  mov     dword ptr [rbx], 0
0x180015edc  mov     rbx, [rsp+28h+arg_0]
0x180015ee1  mov     rsi, [rsp+28h+arg_8]
0x180015ee6  add     rsp, 20h
0x180015eea  pop     rdi
0x180015eeb  retn
```
