# CPxeProviderHandler::ServiceControl(ulong)

- ea: `0x1800069c4`
- end: `0x180006ad5`
- name: `?ServiceControl@CPxeProviderHandler@@QEAAXK@Z`
- size: `273`
- prototype: `void __fastcall(CPxeProviderHandler *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180003050`

## callees

- `0x180002a30`
- `0x1800069c4`
- `0x180006f24`
- `0x180013010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800069f0`
- `KERNEL32!EnterCriticalSection` at `0x180006a00`
- `KERNEL32!EnterCriticalSection` at `0x180006a3c`
- `KERNEL32!EnterCriticalSection` at `0x1800069f0`
- `KERNEL32!EnterCriticalSection` at `0x180006a00`
- `KERNEL32!EnterCriticalSection` at `0x180006a3c`
- `KERNEL32!LeaveCriticalSection` at `0x180006a14`
- `KERNEL32!LeaveCriticalSection` at `0x180006a73`
- `KERNEL32!LeaveCriticalSection` at `0x180006a99`
- `KERNEL32!LeaveCriticalSection` at `0x180006a14`
- `KERNEL32!LeaveCriticalSection` at `0x180006a73`
- `KERNEL32!LeaveCriticalSection` at `0x180006a99`

## string_xrefs

- `0x180006a54`: `WDS PXE Provider\n----------------\nName: %s\nModule Path: %s\n`

## pseudocode

```c
void __fastcall CPxeProviderHandler::ServiceControl(CPxeProviderHandler *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rdi
  void (__fastcall *v8)(__int64, _QWORD); // r15
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  __int64 v10; // rdi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = *((_QWORD *)this + 1);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( v5 )
  {
    v6 = *((_QWORD *)this + 1);
    while ( v6 )
    {
      v7 = v6;
      v6 = *(_QWORD *)(v6 + 152);
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 112));
      if ( a2 == 130 )
        Trace(
          0x20000u,
          L"WDS PXE Provider\n----------------\nName: %s\nModule Path: %s\n",
          *(_QWORD *)v7,
          *(_QWORD *)(v7 + 8));
      v8 = *(void (__fastcall **)(__int64, _QWORD))(v7 + 80);
      v9 = (struct _RTL_CRITICAL_SECTION *)(v7 + 112);
      v10 = *(_QWORD *)(v7 + 88);
      LeaveCriticalSection(v9);
      if ( v8 )
        v8(v10, a2);
    }
  }
  LeaveCriticalSection(v2);
  if ( a2 == 128 )
    CPxeProviderHandler::UpdateSettings(this);
}

```

## disassembly

```asm
0x1800069c4  mov     rax, rsp
0x1800069c7  mov     [rax+8], rbx
0x1800069cb  mov     [rax+10h], rbp
0x1800069cf  mov     [rax+18h], rsi
0x1800069d3  mov     [rax+20h], rdi
0x1800069d7  push    r12
0x1800069d9  push    r14
0x1800069db  push    r15
0x1800069dd  sub     rsp, 20h
0x1800069e1  lea     r12, [rcx+150h]
0x1800069e8  mov     rsi, rcx
0x1800069eb  mov     rcx, r12; lpCriticalSection
0x1800069ee  mov     ebp, edx
0x1800069f0  call    cs:__imp_EnterCriticalSection
0x1800069f7  nop     dword ptr [rax+rax+00h]
0x1800069fc  lea     rcx, [rsi+18h]; lpCriticalSection
0x180006a00  call    cs:__imp_EnterCriticalSection
0x180006a07  nop     dword ptr [rax+rax+00h]
0x180006a0c  mov     rdi, [rsi+8]
0x180006a10  lea     rcx, [rsi+18h]; lpCriticalSection
0x180006a14  call    cs:__imp_LeaveCriticalSection
0x180006a1b  nop     dword ptr [rax+rax+00h]
0x180006a20  test    rdi, rdi
0x180006a23  jz      short loc_180006A96
0x180006a25  mov     rbx, [rsi+8]
0x180006a29  jmp     short loc_180006A91
0x180006a2b  lea     rdi, [rbx]
0x180006a2e  mov     rbx, [rbx+98h]
0x180006a35  lea     r14, [rdi+70h]
0x180006a39  mov     rcx, r14; lpCriticalSection
0x180006a3c  call    cs:__imp_EnterCriticalSection
0x180006a43  nop     dword ptr [rax+rax+00h]
0x180006a48  cmp     ebp, 82h
0x180006a4e  jnz     short loc_180006A68
0x180006a50  mov     r9, [rdi+8]
0x180006a54  lea     rdx, aWdsPxeProvider; "WDS PXE Provider\n----------------\nNam"...
0x180006a5b  mov     r8, [rdi]
0x180006a5e  mov     ecx, 20000h; unsigned int
0x180006a63  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x180006a68  mov     r15, [rdi+50h]
0x180006a6c  mov     rcx, r14; lpCriticalSection
0x180006a6f  mov     rdi, [rdi+58h]
0x180006a73  call    cs:__imp_LeaveCriticalSection
0x180006a7a  nop     dword ptr [rax+rax+00h]
0x180006a7f  test    r15, r15
0x180006a82  jz      short loc_180006A91
0x180006a84  mov     edx, ebp
0x180006a86  mov     rcx, rdi
0x180006a89  mov     rax, r15
0x180006a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a91  test    rbx, rbx
0x180006a94  jnz     short loc_180006A2B
0x180006a96  mov     rcx, r12; lpCriticalSection
0x180006a99  call    cs:__imp_LeaveCriticalSection
0x180006aa0  nop     dword ptr [rax+rax+00h]
0x180006aa5  cmp     ebp, 80h
0x180006aab  jnz     short loc_180006AB5
0x180006aad  mov     rcx, rsi; this
0x180006ab0  call    ?UpdateSettings@CPxeProviderHandler@@QEAAKXZ; CPxeProviderHandler::UpdateSettings(void)
0x180006ab5  mov     rbx, [rsp+38h+arg_0]
0x180006aba  mov     rbp, [rsp+38h+arg_8]
0x180006abf  mov     rsi, [rsp+38h+arg_10]
0x180006ac4  mov     rdi, [rsp+38h+arg_18]
0x180006ac9  add     rsp, 20h
0x180006acd  pop     r15
0x180006acf  pop     r14
0x180006ad1  pop     r12
0x180006ad3  retn
```
