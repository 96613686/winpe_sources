# CExec::DomainMatchesSession(ushort const *,ushort const *)

- ea: `0x1400e0654`
- end: `0x1400e0723`
- name: `?DomainMatchesSession@CExec@@YA_NPEBG0@Z`
- size: `207`
- prototype: `bool __fastcall(CExec *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400e1be8`

## callees

- `0x140005360`
- `0x140006098`
- `0x14000ddac`
- `0x1400e0654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e067e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e06d5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e067e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400e06d5`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1400e06c3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1400e06c3`

## string_xrefs

- `0x1400e0711`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
bool __fastcall CExec::DomainMatchesSession(CExec *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  const char *v6; // r9
  DWORD nSize[4]; // [rsp+20h] [rbp-B8h] BYREF
  WCHAR Buffer[72]; // [rsp+30h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  if ( !(unsigned int)_o__wcsicmp(this, a2) )
    return 1;
  if ( *a2 && (*a2 != 46 || a2[1]) )
    return 0;
  memset_0(Buffer, 0, 0x82u);
  nSize[0] = 65;
  if ( !GetComputerNameW(Buffer, nSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4B5,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v6);
  return (unsigned int)_o__wcsicmp(this, Buffer) == 0;
}

```

## disassembly

```asm
0x1400e0654  mov     [rsp+arg_10], rbx
0x1400e0659  mov     [rsp+arg_18], rsi
0x1400e065e  push    rdi
0x1400e065f  sub     rsp, 0D0h
0x1400e0666  mov     rax, cs:__security_cookie
0x1400e066d  xor     rax, rsp
0x1400e0670  mov     [rsp+0D8h+var_18], rax
0x1400e0678  mov     rbx, rdx
0x1400e067b  mov     rdi, rcx
0x1400e067e  call    cs:__imp__o__wcsicmp
0x1400e0684  xor     esi, esi
0x1400e0686  test    eax, eax
0x1400e0688  jz      short loc_1400E06E2
0x1400e068a  cmp     [rbx], si
0x1400e068d  jz      short loc_1400E069F
0x1400e068f  cmp     word ptr [rbx], 2Eh ; '.'
0x1400e0693  jnz     short loc_1400E069B
0x1400e0695  cmp     [rbx+2], si
0x1400e0699  jz      short loc_1400E069F
0x1400e069b  xor     al, al
0x1400e069d  jmp     short loc_1400E06E4
0x1400e069f  xor     edx, edx; Val
0x1400e06a1  lea     rcx, [rsp+0D8h+Buffer]; void *
0x1400e06a6  mov     r8d, 82h; Size
0x1400e06ac  call    memset_0
0x1400e06b1  lea     rdx, [rsp+0D8h+nSize]; nSize
0x1400e06b6  mov     [rsp+0D8h+nSize], 41h ; 'A'
0x1400e06be  lea     rcx, [rsp+0D8h+Buffer]; lpBuffer
0x1400e06c3  call    cs:__imp_GetComputerNameW
0x1400e06c9  test    eax, eax
0x1400e06cb  jz      short loc_1400E0709
0x1400e06cd  lea     rdx, [rsp+0D8h+Buffer]
0x1400e06d2  mov     rcx, rdi
0x1400e06d5  call    cs:__imp__o__wcsicmp
0x1400e06db  test    eax, eax
0x1400e06dd  setz    al
0x1400e06e0  jmp     short loc_1400E06E4
0x1400e06e2  mov     al, 1
0x1400e06e4  mov     rcx, [rsp+0D8h+var_18]
0x1400e06ec  xor     rcx, rsp; StackCookie
0x1400e06ef  call    __security_check_cookie
0x1400e06f4  lea     r11, [rsp+0D8h+var_8]
0x1400e06fc  mov     rbx, [r11+20h]
0x1400e0700  mov     rsi, [r11+28h]
0x1400e0704  mov     rsp, r11
0x1400e0707  pop     rdi
0x1400e0708  retn
0x1400e0709  mov     rcx, [rsp+0D8h]; this
0x1400e0711  lea     r8, aOnecoreVmCompu_27; "onecore\\vm\\compute\\service\\cexec\\l"...
0x1400e0718  mov     edx, 4B5h; void *
0x1400e071d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
