# CUwfProvider::~CUwfProvider(void)

- ea: `0x180017ac4`
- end: `0x180017b2e`
- name: `??1CUwfProvider@@EEAA@XZ`
- size: `106`
- prototype: `void __fastcall(CUwfProvider *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180017b40`
- `0x18001b5d0`

## callees

- `0x180006200`
- `0x180006240`
- `0x180014b40`
- `0x180014d30`
- `0x180017ac4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017b1a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017b1a`

## pseudocode

```c
void __fastcall CUwfProvider::~CUwfProvider(CUwfProvider *this)
{
  CUwfStaticConfiguration *v2; // rcx
  CUwfStaticConfiguration *v3; // rcx
  CUwfConfiguration *v4; // rcx

  *(_QWORD *)this = &CUwfProvider::`vftable';
  v2 = (CUwfStaticConfiguration *)*((_QWORD *)this + 29);
  if ( v2 )
    CUwfStaticConfiguration::Close(v2);
  v3 = (CUwfStaticConfiguration *)*((_QWORD *)this + 30);
  if ( v3 )
    CUwfStaticConfiguration::Close(v3);
  v4 = (CUwfConfiguration *)*((_QWORD *)this + 28);
  if ( v4 )
    CUwfConfiguration::Close(v4);
  CUwfManagement::Close((CUwfProvider *)((char *)this + 8));
  DeleteCriticalSection(&CUwfProvider::s_CritSec);
  CUwfManagement::~CUwfManagement((CUwfProvider *)((char *)this + 8));
}

```

## disassembly

```asm
0x180017ac4  push    rbx
0x180017ac6  sub     rsp, 20h
0x180017aca  lea     rax, ??_7CUwfProvider@@6B@; const CUwfProvider::`vftable'
0x180017ad1  mov     rbx, rcx
0x180017ad4  mov     [rcx], rax
0x180017ad7  mov     rcx, [rcx+0E8h]; this
0x180017ade  test    rcx, rcx
0x180017ae1  jz      short loc_180017AE8
0x180017ae3  call    ?Close@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::Close(void)
0x180017ae8  mov     rcx, [rbx+0F0h]; this
0x180017aef  test    rcx, rcx
0x180017af2  jz      short loc_180017AF9
0x180017af4  call    ?Close@CUwfStaticConfiguration@@QEAAXXZ; CUwfStaticConfiguration::Close(void)
0x180017af9  mov     rcx, [rbx+0E0h]; this
0x180017b00  test    rcx, rcx
0x180017b03  jz      short loc_180017B0A
0x180017b05  call    ?Close@CUwfConfiguration@@QEAAXXZ; CUwfConfiguration::Close(void)
0x180017b0a  lea     rcx, [rbx+8]; this
0x180017b0e  call    ?Close@CUwfManagement@@QEAAXXZ; CUwfManagement::Close(void)
0x180017b13  lea     rcx, ?s_CritSec@CUwfProvider@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180017b1a  call    cs:__imp_DeleteCriticalSection
0x180017b20  lea     rcx, [rbx+8]; this
0x180017b24  add     rsp, 20h
0x180017b28  pop     rbx
0x180017b29  jmp     ??1CUwfManagement@@UEAA@XZ; CUwfManagement::~CUwfManagement(void)
```
