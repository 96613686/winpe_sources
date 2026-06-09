# CService::Initialize(ushort const *)

- ea: `0x18001e140`
- end: `0x18001e1eb`
- name: `?Initialize@CService@@QEAAKPEBG@Z`
- size: `171`
- prototype: `unsigned int(CService *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180002158`
- `0x18001e140`
- `0x18001e310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e1bb`
- `KERNEL32!GetLastError` at `0x18001e1bb`
- `ADVAPI32!OpenSCManagerW` at `0x18001e1a7`
- `ADVAPI32!OpenSCManagerW` at `0x18001e1a7`
- `ADVAPI32!CloseServiceHandle` at `0x18001e188`
- `ADVAPI32!CloseServiceHandle` at `0x18001e188`

## string_xrefs

- `0x18001e19d`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CService::Initialize(CService *this, const unsigned __int16 *a2)
{
  SC_HANDLE *v4; // rax
  unsigned int v5; // ebx
  SC_HANDLE *v6; // rdi
  SC_HANDLE v7; // rax

  CService::Shutdown(this);
  v4 = (SC_HANDLE *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = 0;
  v6 = v4;
  if ( v4 )
  {
    *v4 = 0;
    *(_QWORD *)this = v4;
    if ( *v4 )
    {
      CloseServiceHandle(*v4);
      *v6 = 0;
    }
    v7 = OpenSCManagerW(a2, L"ServicesActive", 0xF003Fu);
    *v6 = v7;
    if ( !v7 )
      return GetLastError();
  }
  else
  {
    *(_QWORD *)this = 0;
    return 8;
  }
  return v5;
}

```

## disassembly

```asm
0x18001e140  mov     [rsp+arg_0], rbx
0x18001e145  mov     [rsp+arg_8], rbp
0x18001e14a  mov     [rsp+arg_10], rsi
0x18001e14f  push    rdi
0x18001e150  sub     rsp, 20h
0x18001e154  mov     rbp, rdx
0x18001e157  mov     rsi, rcx
0x18001e15a  call    ?Shutdown@CService@@QEAAKXZ; CService::Shutdown(void)
0x18001e15f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e166  mov     ecx, 8; unsigned __int64
0x18001e16b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e170  xor     ebx, ebx
0x18001e172  mov     rdi, rax
0x18001e175  test    rax, rax
0x18001e178  jz      short loc_18001E1CB
0x18001e17a  mov     [rax], rbx
0x18001e17d  mov     [rsi], rax
0x18001e180  cmp     [rax], rbx
0x18001e183  jz      short loc_18001E197
0x18001e185  mov     rcx, [rax]; hSCObject
0x18001e188  call    cs:__imp_CloseServiceHandle
0x18001e18f  nop     dword ptr [rax+rax+00h]
0x18001e194  mov     [rdi], rbx
0x18001e197  mov     r8d, 0F003Fh; dwDesiredAccess
0x18001e19d  lea     rdx, DatabaseName; "ServicesActive"
0x18001e1a4  mov     rcx, rbp; lpMachineName
0x18001e1a7  call    cs:__imp_OpenSCManagerW
0x18001e1ae  nop     dword ptr [rax+rax+00h]
0x18001e1b3  mov     [rdi], rax
0x18001e1b6  test    rax, rax
0x18001e1b9  jnz     short loc_18001E1D3
0x18001e1bb  call    cs:__imp_GetLastError
0x18001e1c2  nop     dword ptr [rax+rax+00h]
0x18001e1c7  mov     ebx, eax
0x18001e1c9  jmp     short loc_18001E1D3
0x18001e1cb  mov     [rsi], rbx
0x18001e1ce  mov     ebx, 8
0x18001e1d3  mov     rbp, [rsp+28h+arg_8]
0x18001e1d8  mov     eax, ebx
0x18001e1da  mov     rbx, [rsp+28h+arg_0]
0x18001e1df  mov     rsi, [rsp+28h+arg_10]
0x18001e1e4  add     rsp, 20h
0x18001e1e8  pop     rdi
0x18001e1e9  retn
```
