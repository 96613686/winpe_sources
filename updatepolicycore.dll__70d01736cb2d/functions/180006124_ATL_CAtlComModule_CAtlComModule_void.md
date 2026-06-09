# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180006124`
- end: `0x1800061a2`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `126`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180039560`

## callees

- `0x180006124`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006186`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006186`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006159`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180006159`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  unsigned __int64 i; // rdi
  PVOID *v3; // rsi
  PVOID v4; // rax

  if ( *(_DWORD *)this )
  {
    for ( i = *((_QWORD *)this + 2); i < *((_QWORD *)this + 3); i += 8LL )
    {
      if ( *(_QWORD *)i )
      {
        v3 = *(PVOID **)(*(_QWORD *)i + 32LL);
        if ( *v3 )
        {
          v4 = DecodePointer(*v3);
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v4 + 16LL))(v4);
          *v3 = 0;
        }
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180006124  mov     [rsp+arg_0], rbx
0x180006129  mov     [rsp+arg_8], rsi
0x18000612e  push    rdi
0x18000612f  sub     rsp, 20h
0x180006133  mov     rbx, rcx
0x180006136  cmp     dword ptr [rcx], 0
0x180006139  jz      short loc_180006192
0x18000613b  mov     rdi, [rcx+10h]
0x18000613f  cmp     rdi, [rcx+18h]
0x180006143  jnb     short loc_180006182
0x180006145  mov     rax, [rdi]
0x180006148  test    rax, rax
0x18000614b  jz      short loc_180006178
0x18000614d  mov     rsi, [rax+20h]
0x180006151  mov     rcx, [rsi]; Ptr
0x180006154  test    rcx, rcx
0x180006157  jz      short loc_180006178
0x180006159  call    cs:__imp_DecodePointer
0x18000615f  mov     rdx, rax
0x180006162  mov     rcx, [rax]
0x180006165  mov     rax, [rcx+10h]
0x180006169  mov     rcx, rdx
0x18000616c  call    _guard_dispatch_icall
0x180006171  mov     qword ptr [rsi], 0
0x180006178  add     rdi, 8
0x18000617c  cmp     rdi, [rbx+18h]
0x180006180  jb      short loc_180006145
0x180006182  lea     rcx, [rbx+20h]; lpCriticalSection
0x180006186  call    cs:__imp_DeleteCriticalSection
0x18000618c  mov     dword ptr [rbx], 0
0x180006192  mov     rbx, [rsp+28h+arg_0]
0x180006197  mov     rsi, [rsp+28h+arg_8]
0x18000619c  add     rsp, 20h
0x1800061a0  pop     rdi
0x1800061a1  retn
```
