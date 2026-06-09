# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000d2d0`
- end: `0x18000d340`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015c80`

## callees

- `0x18000d2d0`
- `0x180016010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000d324`
- `KERNEL32!DeleteCriticalSection` at `0x18000d324`

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
0x18000d2d0  mov     [rsp+arg_0], rbx
0x18000d2d5  mov     [rsp+arg_8], rsi
0x18000d2da  push    rdi
0x18000d2db  sub     rsp, 20h
0x18000d2df  cmp     dword ptr [rcx], 0
0x18000d2e2  mov     rbx, rcx
0x18000d2e5  jz      short loc_18000D330
0x18000d2e7  mov     rdi, [rcx+10h]
0x18000d2eb  cmp     rdi, [rcx+18h]
0x18000d2ef  jnb     short loc_18000D320
0x18000d2f1  mov     rsi, [rdi]
0x18000d2f4  test    rsi, rsi
0x18000d2f7  jz      short loc_18000D316
0x18000d2f9  mov     rcx, [rsi+20h]
0x18000d2fd  test    rcx, rcx
0x18000d300  jz      short loc_18000D30E
0x18000d302  mov     rax, [rcx]
0x18000d305  mov     rax, [rax+10h]
0x18000d309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d30e  mov     qword ptr [rsi+20h], 0
0x18000d316  add     rdi, 8
0x18000d31a  cmp     rdi, [rbx+18h]
0x18000d31e  jb      short loc_18000D2F1
0x18000d320  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000d324  call    cs:__imp_DeleteCriticalSection
0x18000d32a  mov     dword ptr [rbx], 0
0x18000d330  mov     rbx, [rsp+28h+arg_0]
0x18000d335  mov     rsi, [rsp+28h+arg_8]
0x18000d33a  add     rsp, 20h
0x18000d33e  pop     rdi
0x18000d33f  retn
```
