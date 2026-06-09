# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x140006274`
- end: `0x1400062e4`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007850`

## callees

- `0x140006274`
- `0x140008010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400062c8`
- `KERNEL32!DeleteCriticalSection` at `0x1400062c8`

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
0x140006274  mov     [rsp+arg_0], rbx
0x140006279  mov     [rsp+arg_8], rsi
0x14000627e  push    rdi
0x14000627f  sub     rsp, 20h
0x140006283  cmp     dword ptr [rcx], 0
0x140006286  mov     rbx, rcx
0x140006289  jz      short loc_1400062D4
0x14000628b  mov     rdi, [rcx+10h]
0x14000628f  cmp     rdi, [rcx+18h]
0x140006293  jnb     short loc_1400062C4
0x140006295  mov     rsi, [rdi]
0x140006298  test    rsi, rsi
0x14000629b  jz      short loc_1400062BA
0x14000629d  mov     rcx, [rsi+20h]
0x1400062a1  test    rcx, rcx
0x1400062a4  jz      short loc_1400062B2
0x1400062a6  mov     rax, [rcx]
0x1400062a9  mov     rax, [rax+10h]
0x1400062ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400062b2  mov     qword ptr [rsi+20h], 0
0x1400062ba  add     rdi, 8
0x1400062be  cmp     rdi, [rbx+18h]
0x1400062c2  jb      short loc_140006295
0x1400062c4  lea     rcx, [rbx+20h]; lpCriticalSection
0x1400062c8  call    cs:__imp_DeleteCriticalSection
0x1400062ce  mov     dword ptr [rbx], 0
0x1400062d4  mov     rbx, [rsp+28h+arg_0]
0x1400062d9  mov     rsi, [rsp+28h+arg_8]
0x1400062de  add     rsp, 20h
0x1400062e2  pop     rdi
0x1400062e3  retn
```
