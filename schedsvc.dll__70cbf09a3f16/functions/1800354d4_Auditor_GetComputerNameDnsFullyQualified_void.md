# Auditor::GetComputerNameDnsFullyQualified(void)

- ea: `0x1800354d4`
- end: `0x180035562`
- name: `?GetComputerNameDnsFullyQualified@Auditor@@AEAAPEAGXZ`
- size: `142`
- prototype: `unsigned __int16 *__fastcall(Auditor *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800349c0`

## callees

- `0x1800354d4`

## import_xrefs

- `msvcrt!malloc` at `0x1800354eb`
- `msvcrt!malloc` at `0x1800354eb`
- `msvcrt!realloc` at `0x180035527`
- `msvcrt!realloc` at `0x180035527`
- `msvcrt!free` at `0x18003554f`
- `msvcrt!free` at `0x18003554f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035510`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035506`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035542`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035506`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180035542`

## pseudocode

```c
unsigned __int16 *__fastcall Auditor::GetComputerNameDnsFullyQualified(Auditor *this)
{
  WCHAR *v1; // rax
  WCHAR *v2; // rbx
  WCHAR *v3; // rax
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF
  int v6; // [rsp+34h] [rbp+Ch]

  v6 = HIDWORD(this);
  nSize = 256;
  v1 = (WCHAR *)malloc(0x200u);
  v2 = v1;
  if ( !v1 )
    return 0;
  if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v1, &nSize) )
  {
    if ( GetLastError() != 234 )
      goto LABEL_6;
    v3 = (WCHAR *)realloc(v2, 2LL * nSize);
    v2 = v3;
    if ( !v3 )
      return 0;
    if ( !GetComputerNameExW(ComputerNameDnsFullyQualified, v3, &nSize) )
    {
LABEL_6:
      free(v2);
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800354d4  mov     qword ptr [rsp+nSize], rcx
0x1800354d9  push    rbx
0x1800354da  sub     rsp, 20h
0x1800354de  mov     ecx, 200h; Size
0x1800354e3  mov     [rsp+28h+nSize], 100h
0x1800354eb  call    cs:__imp_malloc
0x1800354f1  mov     rbx, rax
0x1800354f4  test    rax, rax
0x1800354f7  jz      short loc_180035555
0x1800354f9  lea     r8, [rsp+28h+nSize]; nSize
0x1800354fe  mov     rdx, rax; lpBuffer
0x180035501  mov     ecx, 3; NameType
0x180035506  call    cs:__imp_GetComputerNameExW
0x18003550c  test    eax, eax
0x18003550e  jnz     short loc_18003555D
0x180035510  call    cs:__imp_GetLastError
0x180035516  cmp     eax, 0EAh
0x18003551b  jnz     short loc_18003554C
0x18003551d  mov     edx, [rsp+28h+nSize]
0x180035521  mov     rcx, rbx; Block
0x180035524  add     rdx, rdx; Size
0x180035527  call    cs:__imp_realloc
0x18003552d  mov     rbx, rax
0x180035530  test    rax, rax
0x180035533  jz      short loc_180035555
0x180035535  lea     r8, [rsp+28h+nSize]; nSize
0x18003553a  mov     rdx, rax; lpBuffer
0x18003553d  mov     ecx, 3; NameType
0x180035542  call    cs:__imp_GetComputerNameExW
0x180035548  test    eax, eax
0x18003554a  jnz     short loc_18003555D
0x18003554c  mov     rcx, rbx; Block
0x18003554f  call    cs:__imp_free
0x180035555  xor     eax, eax
0x180035557  add     rsp, 20h
0x18003555b  pop     rbx
0x18003555c  retn
0x18003555d  mov     rax, rbx
0x180035560  jmp     short loc_180035557
```
