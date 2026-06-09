# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x140006200`
- end: `0x140006270`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400067a0`

## callees

- `0x140006200`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006254`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006254`

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
0x140006200  mov     [rsp+arg_0], rbx
0x140006205  mov     [rsp+arg_8], rsi
0x14000620a  push    rdi
0x14000620b  sub     rsp, 20h
0x14000620f  cmp     dword ptr [rcx], 0
0x140006212  mov     rbx, rcx
0x140006215  jz      short loc_140006260
0x140006217  mov     rdi, [rcx+10h]
0x14000621b  cmp     rdi, [rcx+18h]
0x14000621f  jnb     short loc_140006250
0x140006221  mov     rsi, [rdi]
0x140006224  test    rsi, rsi
0x140006227  jz      short loc_140006246
0x140006229  mov     rcx, [rsi+20h]
0x14000622d  test    rcx, rcx
0x140006230  jz      short loc_14000623E
0x140006232  mov     rax, [rcx]
0x140006235  mov     rax, [rax+10h]
0x140006239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000623e  mov     qword ptr [rsi+20h], 0
0x140006246  add     rdi, 8
0x14000624a  cmp     rdi, [rbx+18h]
0x14000624e  jb      short loc_140006221
0x140006250  lea     rcx, [rbx+20h]; lpCriticalSection
0x140006254  call    cs:__imp_DeleteCriticalSection
0x14000625a  mov     dword ptr [rbx], 0
0x140006260  mov     rbx, [rsp+28h+arg_0]
0x140006265  mov     rsi, [rsp+28h+arg_8]
0x14000626a  add     rsp, 20h
0x14000626e  pop     rdi
0x14000626f  retn
```
