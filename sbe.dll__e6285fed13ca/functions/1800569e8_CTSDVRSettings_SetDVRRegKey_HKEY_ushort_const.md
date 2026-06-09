# CTSDVRSettings::SetDVRRegKey(HKEY__ *,ushort const *)

- ea: `0x1800569e8`
- end: `0x180056b0a`
- name: `?SetDVRRegKey@CTSDVRSettings@@QEAAJPEAUHKEY__@@PEBG@Z`
- size: `290`
- prototype: `__int64 __fastcall(CTSDVRSettings *__hidden this, HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800085b0`
- `0x18000c400`
- `0x180011040`
- `0x180055a24`

## callees

- `0x18002d050`
- `0x180055e94`
- `0x1800569e8`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180056aea`
- `KERNEL32!LeaveCriticalSection` at `0x180056aea`
- `KERNEL32!EnterCriticalSection` at `0x180056a00`
- `KERNEL32!EnterCriticalSection` at `0x180056a00`
- `ADVAPI32!RegCreateKeyExW` at `0x180056a49`
- `ADVAPI32!RegCreateKeyExW` at `0x180056a8c`
- `ADVAPI32!RegCreateKeyExW` at `0x180056a49`
- `ADVAPI32!RegCreateKeyExW` at `0x180056a8c`

## pseudocode

```c
__int64 __fastcall CTSDVRSettings::SetDVRRegKey(CTSDVRSettings *this, HKEY hKey, LPCWSTR lpSubKey)
{
  LSTATUS Key; // ebx
  int v7; // r8d
  __int64 i; // rax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CTSDVRSettings::CloseRegKeys_(this);
  Key = RegCreateKeyExW(hKey, L"DVR", 0, 0, 0, 0x2001Fu, 0, (PHKEY)this + 1, 0);
  if ( Key || (Key = RegCreateKeyExW(*((HKEY *)this + 1), lpSubKey, 0, 0, 0, 0x2001Fu, 0, (PHKEY)this + 2, 0)) != 0 )
  {
    CTSDVRSettings::CloseRegKeys_(this);
  }
  else
  {
    for ( i = 0; i != 88; ++i )
      *((_DWORD *)this + 2 * i + 146) = 0;
    CTSDVRSettings::DVRGetVal_(
      (_DWORD)this,
      (unsigned int)L"WMPacketSizeBytes",
      v7,
      0xFFFF,
      0x2000,
      0xFFFF,
      (__int64)this + 640);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  if ( Key > 0 )
    return (unsigned __int16)Key | 0x80070000;
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x1800569e8  push    rbx
0x1800569ea  push    rbp
0x1800569eb  push    rsi
0x1800569ec  push    rdi
0x1800569ed  push    r14
0x1800569ef  sub     rsp, 50h
0x1800569f3  mov     rdi, rcx
0x1800569f6  mov     rbp, r8
0x1800569f9  add     rcx, 18h; lpCriticalSection
0x1800569fd  mov     rbx, rdx
0x180056a00  call    cs:__imp_EnterCriticalSection
0x180056a06  mov     rcx, rdi; this
0x180056a09  call    ?CloseRegKeys_@CTSDVRSettings@@AEAAXXZ; CTSDVRSettings::CloseRegKeys_(void)
0x180056a0e  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180056a17  lea     r14, [rdi+8]
0x180056a1b  mov     [rsp+78h+phkResult], r14; phkResult
0x180056a20  lea     rdx, aDvr; "DVR"
0x180056a27  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180056a30  xor     r9d, r9d; lpClass
0x180056a33  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180056a3b  xor     r8d, r8d; Reserved
0x180056a3e  mov     rcx, rbx; hKey
0x180056a41  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180056a49  call    cs:__imp_RegCreateKeyExW
0x180056a4f  mov     ebx, eax
0x180056a51  test    eax, eax
0x180056a53  jnz     loc_180056ADE
0x180056a59  mov     rcx, [r14]; hKey
0x180056a5c  lea     rax, [rdi+10h]
0x180056a60  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180056a69  xor     r9d, r9d; lpClass
0x180056a6c  mov     [rsp+78h+phkResult], rax; phkResult
0x180056a71  xor     r8d, r8d; Reserved
0x180056a74  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180056a7d  mov     rdx, rbp; lpSubKey
0x180056a80  mov     [rsp+78h+samDesired], 2001Fh; samDesired
0x180056a88  mov     [rsp+78h+dwOptions], ebx; dwOptions
0x180056a8c  call    cs:__imp_RegCreateKeyExW
0x180056a92  mov     ebx, eax
0x180056a94  test    eax, eax
0x180056a96  jnz     short loc_180056ADE
0x180056a98  xor     eax, eax
0x180056a9a  mov     dword ptr [rdi+rax*8+248h], 0
0x180056aa5  inc     rax
0x180056aa8  cmp     rax, 58h ; 'X'
0x180056aac  jnz     short loc_180056A9A
0x180056aae  lea     rax, [rdi+280h]
0x180056ab5  mov     r9d, 0FFFFh
0x180056abb  mov     [rsp+78h+lpSecurityAttributes], rax
0x180056ac0  lea     rdx, aWmpacketsizeby; "WMPacketSizeBytes"
0x180056ac7  mov     [rsp+78h+samDesired], r9d
0x180056acc  mov     rcx, rdi
0x180056acf  mov     [rsp+78h+dwOptions], 2000h
0x180056ad7  call    ?DVRGetVal_@CTSDVRSettings@@AEAAKPEBGHKKKPEAU?$CTRegVal@K@1@@Z; CTSDVRSettings::DVRGetVal_(ushort const *,int,ulong,ulong,ulong,CTSDVRSettings::CTRegVal<ulong> *)
0x180056adc  jmp     short loc_180056AE6
0x180056ade  mov     rcx, rdi; this
0x180056ae1  call    ?CloseRegKeys_@CTSDVRSettings@@AEAAXXZ; CTSDVRSettings::CloseRegKeys_(void)
0x180056ae6  lea     rcx, [rdi+18h]; lpCriticalSection
0x180056aea  call    cs:__imp_LeaveCriticalSection
0x180056af0  test    ebx, ebx
0x180056af2  jle     short loc_180056AFD
0x180056af4  movzx   ebx, bx
0x180056af7  or      ebx, 80070000h
0x180056afd  mov     eax, ebx
0x180056aff  add     rsp, 50h
0x180056b03  pop     r14
0x180056b05  pop     rdi
0x180056b06  pop     rsi
0x180056b07  pop     rbp
0x180056b08  pop     rbx
0x180056b09  retn
```
