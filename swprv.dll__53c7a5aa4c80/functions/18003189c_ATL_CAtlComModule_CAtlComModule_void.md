# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18003189c`
- end: `0x18003190c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004af90`

## callees

- `0x18003189c`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800318f0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800318f0`

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
0x18003189c  mov     [rsp+arg_0], rbx
0x1800318a1  mov     [rsp+arg_8], rsi
0x1800318a6  push    rdi
0x1800318a7  sub     rsp, 20h
0x1800318ab  cmp     dword ptr [rcx], 0
0x1800318ae  mov     rbx, rcx
0x1800318b1  jz      short loc_1800318FC
0x1800318b3  mov     rdi, [rcx+10h]
0x1800318b7  cmp     rdi, [rcx+18h]
0x1800318bb  jnb     short loc_1800318EC
0x1800318bd  mov     rsi, [rdi]
0x1800318c0  test    rsi, rsi
0x1800318c3  jz      short loc_1800318E2
0x1800318c5  mov     rcx, [rsi+20h]
0x1800318c9  test    rcx, rcx
0x1800318cc  jz      short loc_1800318DA
0x1800318ce  mov     rax, [rcx]
0x1800318d1  mov     rax, [rax+10h]
0x1800318d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318da  mov     qword ptr [rsi+20h], 0
0x1800318e2  add     rdi, 8
0x1800318e6  cmp     rdi, [rbx+18h]
0x1800318ea  jb      short loc_1800318BD
0x1800318ec  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800318f0  call    cs:__imp_DeleteCriticalSection
0x1800318f6  mov     dword ptr [rbx], 0
0x1800318fc  mov     rbx, [rsp+28h+arg_0]
0x180031901  mov     rsi, [rsp+28h+arg_8]
0x180031906  add     rsp, 20h
0x18003190a  pop     rdi
0x18003190b  retn
```
