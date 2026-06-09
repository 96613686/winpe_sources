# ATL::CAtlModule::~CAtlModule(void)

- ea: `0x180008920`
- end: `0x1800089c0`
- name: `??1CAtlModule@ATL@@UEAA@XZ`
- size: `160`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008700`
- `0x180016110`

## callees

- `0x180008904`
- `0x180008920`
- `0x1800150b8`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000899b`
- `KERNEL32!DeleteCriticalSection` at `0x18000899b`

## pseudocode

```c
void __fastcall ATL::CAtlModule::~CAtlModule(ATL::CAtlModule *this, unsigned int a2)
{
  char *v2; // rsi
  _QWORD *v4; // r14
  _QWORD *v5; // rbx
  __int64 v6; // rcx

  v2 = (char *)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      if ( this == (ATL::CAtlModule *)-8LL )
      {
        ATL::_AtlRaiseException(0xFFFFFFF8, a2);
        JUMPOUT(0x1800089BFLL);
      }
      v4 = (_QWORD *)*((_QWORD *)this + 2);
      if ( v4 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD))*v4)(v4[1]);
          v5 = (_QWORD *)v4[2];
          operator delete(v4);
          v4 = v5;
        }
        while ( v5 );
      }
      *((_QWORD *)v2 + 1) = 0;
      *((_QWORD *)this + 2) = 0;
    }
    v6 = *((_QWORD *)this + 8);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180008920  mov     [rsp+arg_0], rbx
0x180008925  mov     [rsp+arg_8], rsi
0x18000892a  mov     [rsp+arg_10], rdi
0x18000892f  push    r14
0x180008931  sub     rsp, 20h
0x180008935  lea     rsi, [rcx+8]
0x180008939  mov     rdi, rcx
0x18000893c  cmp     dword ptr [rsi], 0
0x18000893f  jz      short loc_1800089A4
0x180008941  cmp     qword ptr [rcx+10h], 0
0x180008946  jz      short loc_180008981
0x180008948  test    rsi, rsi
0x18000894b  jz      short loc_1800089BA
0x18000894d  mov     r14, [rsi+8]
0x180008951  test    r14, r14
0x180008954  jz      short loc_180008977
0x180008956  mov     rcx, [r14+8]
0x18000895a  mov     rax, [r14]
0x18000895d  call    cs:__guard_dispatch_icall_fptr
0x180008963  mov     rbx, [r14+10h]
0x180008967  mov     rcx, r14; Block
0x18000896a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000896f  mov     r14, rbx
0x180008972  test    rbx, rbx
0x180008975  jnz     short loc_180008956
0x180008977  and     qword ptr [rsi+8], 0
0x18000897c  and     qword ptr [rdi+10h], 0
0x180008981  mov     rcx, [rdi+40h]
0x180008985  test    rcx, rcx
0x180008988  jz      short loc_180008997
0x18000898a  mov     rax, [rcx]
0x18000898d  mov     rax, [rax+10h]
0x180008991  call    cs:__guard_dispatch_icall_fptr
0x180008997  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000899b  call    cs:__imp_DeleteCriticalSection
0x1800089a1  and     dword ptr [rsi], 0
0x1800089a4  mov     rbx, [rsp+28h+arg_0]
0x1800089a9  mov     rsi, [rsp+28h+arg_8]
0x1800089ae  mov     rdi, [rsp+28h+arg_10]
0x1800089b3  add     rsp, 20h
0x1800089b7  pop     r14
0x1800089b9  retn
0x1800089ba  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
