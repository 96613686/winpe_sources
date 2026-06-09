# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800410d0`
- end: `0x180041140`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180057420`

## callees

- `0x1800410d0`
- `0x180058010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180041124`
- `KERNEL32!DeleteCriticalSection` at `0x180041124`

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
0x1800410d0  mov     [rsp+arg_0], rbx
0x1800410d5  mov     [rsp+arg_8], rsi
0x1800410da  push    rdi
0x1800410db  sub     rsp, 20h
0x1800410df  cmp     dword ptr [rcx], 0
0x1800410e2  mov     rbx, rcx
0x1800410e5  jz      short loc_180041130
0x1800410e7  mov     rdi, [rcx+10h]
0x1800410eb  cmp     rdi, [rcx+18h]
0x1800410ef  jnb     short loc_180041120
0x1800410f1  mov     rsi, [rdi]
0x1800410f4  test    rsi, rsi
0x1800410f7  jz      short loc_180041116
0x1800410f9  mov     rcx, [rsi+20h]
0x1800410fd  test    rcx, rcx
0x180041100  jz      short loc_18004110E
0x180041102  mov     rax, [rcx]
0x180041105  mov     rax, [rax+10h]
0x180041109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004110e  mov     qword ptr [rsi+20h], 0
0x180041116  add     rdi, 8
0x18004111a  cmp     rdi, [rbx+18h]
0x18004111e  jb      short loc_1800410F1
0x180041120  lea     rcx, [rbx+20h]; lpCriticalSection
0x180041124  call    cs:__imp_DeleteCriticalSection
0x18004112a  mov     dword ptr [rbx], 0
0x180041130  mov     rbx, [rsp+28h+arg_0]
0x180041135  mov     rsi, [rsp+28h+arg_8]
0x18004113a  add     rsp, 20h
0x18004113e  pop     rdi
0x18004113f  retn
```
