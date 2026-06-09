# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000bd68`
- end: `0x18000bdd8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011440`

## callees

- `0x18000bd68`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bdbc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bdbc`

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
0x18000bd68  mov     [rsp+arg_0], rbx
0x18000bd6d  mov     [rsp+arg_8], rsi
0x18000bd72  push    rdi
0x18000bd73  sub     rsp, 20h
0x18000bd77  cmp     dword ptr [rcx], 0
0x18000bd7a  mov     rbx, rcx
0x18000bd7d  jz      short loc_18000BDC8
0x18000bd7f  mov     rdi, [rcx+10h]
0x18000bd83  cmp     rdi, [rcx+18h]
0x18000bd87  jnb     short loc_18000BDB8
0x18000bd89  mov     rsi, [rdi]
0x18000bd8c  test    rsi, rsi
0x18000bd8f  jz      short loc_18000BDAE
0x18000bd91  mov     rcx, [rsi+20h]
0x18000bd95  test    rcx, rcx
0x18000bd98  jz      short loc_18000BDA6
0x18000bd9a  mov     rax, [rcx]
0x18000bd9d  mov     rax, [rax+10h]
0x18000bda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bda6  mov     qword ptr [rsi+20h], 0
0x18000bdae  add     rdi, 8
0x18000bdb2  cmp     rdi, [rbx+18h]
0x18000bdb6  jb      short loc_18000BD89
0x18000bdb8  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000bdbc  call    cs:__imp_DeleteCriticalSection
0x18000bdc2  mov     dword ptr [rbx], 0
0x18000bdc8  mov     rbx, [rsp+28h+arg_0]
0x18000bdcd  mov     rsi, [rsp+28h+arg_8]
0x18000bdd2  add     rsp, 20h
0x18000bdd6  pop     rdi
0x18000bdd7  retn
```
