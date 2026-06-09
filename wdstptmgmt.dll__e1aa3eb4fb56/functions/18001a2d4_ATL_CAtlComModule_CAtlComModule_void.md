# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18001a2d4`
- end: `0x18001a345`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001f310`

## callees

- `0x18001a2d4`
- `0x180020010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001a325`
- `KERNEL32!DeleteCriticalSection` at `0x18001a325`

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
0x18001a2d4  mov     [rsp+arg_0], rbx
0x18001a2d9  mov     [rsp+arg_8], rsi
0x18001a2de  push    rdi
0x18001a2df  sub     rsp, 20h
0x18001a2e3  cmp     dword ptr [rcx], 0
0x18001a2e6  mov     rbx, rcx
0x18001a2e9  jz      short loc_18001A334
0x18001a2eb  mov     rdi, [rcx+10h]
0x18001a2ef  cmp     rdi, [rcx+18h]
0x18001a2f3  jnb     short loc_18001A321
0x18001a2f5  mov     rsi, [rdi]
0x18001a2f8  test    rsi, rsi
0x18001a2fb  jz      short loc_18001A317
0x18001a2fd  mov     rcx, [rsi+20h]
0x18001a301  test    rcx, rcx
0x18001a304  jz      short loc_18001A312
0x18001a306  mov     rax, [rcx]
0x18001a309  mov     rax, [rax+10h]
0x18001a30d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a312  and     qword ptr [rsi+20h], 0
0x18001a317  add     rdi, 8
0x18001a31b  cmp     rdi, [rbx+18h]
0x18001a31f  jb      short loc_18001A2F5
0x18001a321  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001a325  call    cs:__imp_DeleteCriticalSection
0x18001a32c  nop     dword ptr [rax+rax+00h]
0x18001a331  and     dword ptr [rbx], 0
0x18001a334  mov     rbx, [rsp+28h+arg_0]
0x18001a339  mov     rsi, [rsp+28h+arg_8]
0x18001a33e  add     rsp, 20h
0x18001a342  pop     rdi
0x18001a343  retn
```
