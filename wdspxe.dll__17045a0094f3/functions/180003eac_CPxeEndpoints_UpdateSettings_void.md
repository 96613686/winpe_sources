# CPxeEndpoints::UpdateSettings(void)

- ea: `0x180003eac`
- end: `0x180003f2c`
- name: `?UpdateSettings@CPxeEndpoints@@QEAAKXZ`
- size: `128`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180002bc0`
- `0x180003050`

## callees

- `0x180003384`
- `0x180003924`
- `0x180003eac`
- `0x180003f34`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003ebe`
- `KERNEL32!EnterCriticalSection` at `0x180003ebe`
- `KERNEL32!LeaveCriticalSection` at `0x180003f0d`
- `KERNEL32!LeaveCriticalSection` at `0x180003f0d`

## pseudocode

```c
__int64 __fastcall CPxeEndpoints::UpdateSettings(LPCRITICAL_SECTION lpCriticalSection)
{
  unsigned int Parameters; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8
  LONG v5; // esi
  __int64 v6; // rdx
  __int64 v7; // r8

  EnterCriticalSection(lpCriticalSection);
  Parameters = CPxeEndpoints::ReadParameters(lpCriticalSection);
  v5 = 0;
  if ( !(unsigned int)ElValidateWin32_0(Parameters, v3, v4, 565) )
  {
    Parameters = CPxeEndpoints::OpenEndpoints(lpCriticalSection);
    ElValidateWin32_0(Parameters, v6, v7, 571);
  }
  LOBYTE(v5) = Parameters != 0;
  lpCriticalSection[4].RecursionCount = v5;
  LeaveCriticalSection(lpCriticalSection);
  return Parameters;
}

```

## disassembly

```asm
0x180003eac  mov     [rsp+arg_0], rbx
0x180003eb1  mov     [rsp+arg_8], rsi
0x180003eb6  push    rdi
0x180003eb7  sub     rsp, 20h
0x180003ebb  mov     rdi, rcx
0x180003ebe  call    cs:__imp_EnterCriticalSection
0x180003ec5  nop     dword ptr [rax+rax+00h]
0x180003eca  mov     rcx, rdi; lpCriticalSection
0x180003ecd  call    ?ReadParameters@CPxeEndpoints@@AEAAKXZ; CPxeEndpoints::ReadParameters(void)
0x180003ed2  mov     r9d, 235h
0x180003ed8  mov     ecx, eax
0x180003eda  mov     ebx, eax
0x180003edc  call    ElValidateWin32_0
0x180003ee1  xor     esi, esi
0x180003ee3  test    eax, eax
0x180003ee5  jnz     short loc_180003EFE
0x180003ee7  mov     rcx, rdi; lpCriticalSection
0x180003eea  call    ?OpenEndpoints@CPxeEndpoints@@AEAAKXZ; CPxeEndpoints::OpenEndpoints(void)
0x180003eef  mov     r9d, 23Bh
0x180003ef5  mov     ecx, eax
0x180003ef7  mov     ebx, eax
0x180003ef9  call    ElValidateWin32_0
0x180003efe  test    ebx, ebx
0x180003f00  mov     rcx, rdi; lpCriticalSection
0x180003f03  setnz   sil
0x180003f07  mov     [rdi+0ACh], esi
0x180003f0d  call    cs:__imp_LeaveCriticalSection
0x180003f14  nop     dword ptr [rax+rax+00h]
0x180003f19  mov     rsi, [rsp+28h+arg_8]
0x180003f1e  mov     eax, ebx
0x180003f20  mov     rbx, [rsp+28h+arg_0]
0x180003f25  add     rsp, 20h
0x180003f29  pop     rdi
0x180003f2a  retn
```
