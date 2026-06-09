# ScLookupServerName(ushort const *)

- ea: `0x18003b3a0`
- end: `0x18003b42b`
- name: `?ScLookupServerName@@YAHPEBG@Z`
- size: `139`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003addc`

## callees

- `0x18003b3a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b413`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b413`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b3c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b3c9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003b3f8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003b3f8`

## pseudocode

```c
__int64 __fastcall ScLookupServerName(LPCWCH lpString2)
{
  unsigned int v3; // edi
  __int64 i; // rbx
  const WCHAR *v5; // rcx

  if ( !qword_18007C600 )
    return 0;
  v3 = 0;
  EnterCriticalSection(&SccCritsec);
  for ( i = 0; (unsigned int)i < 0x10; i = (unsigned int)(i + 1) )
  {
    v5 = *(const WCHAR **)(qword_18007C600 + 8 * i);
    if ( !v5 )
      break;
    if ( CompareStringOrdinal(v5, -1, lpString2, -1, 1) == 2 )
    {
      v3 = 1;
      break;
    }
  }
  LeaveCriticalSection(&SccCritsec);
  return v3;
}

```

## disassembly

```asm
0x18003b3a0  mov     [rsp+arg_0], rbx
0x18003b3a5  mov     [rsp+arg_8], rsi
0x18003b3aa  push    rdi
0x18003b3ab  sub     rsp, 30h
0x18003b3af  cmp     cs:qword_18007C600, 0
0x18003b3b7  mov     rsi, rcx
0x18003b3ba  jnz     short loc_18003B3C0
0x18003b3bc  xor     eax, eax
0x18003b3be  jmp     short loc_18003B41B
0x18003b3c0  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003b3c7  xor     edi, edi
0x18003b3c9  call    cs:__imp_EnterCriticalSection
0x18003b3cf  xor     ebx, ebx
0x18003b3d1  cmp     ebx, 10h
0x18003b3d4  jnb     short loc_18003B40C
0x18003b3d6  mov     rax, cs:qword_18007C600
0x18003b3dd  mov     rcx, [rax+rbx*8]; lpString1
0x18003b3e1  test    rcx, rcx
0x18003b3e4  jz      short loc_18003B40C
0x18003b3e6  or      r9d, 0FFFFFFFFh; cchCount2
0x18003b3ea  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18003b3f2  or      edx, r9d; cchCount1
0x18003b3f5  mov     r8, rsi; lpString2
0x18003b3f8  call    cs:__imp_CompareStringOrdinal
0x18003b3fe  cmp     eax, 2
0x18003b401  jz      short loc_18003B407
0x18003b403  inc     ebx
0x18003b405  jmp     short loc_18003B3D1
0x18003b407  mov     edi, 1
0x18003b40c  lea     rcx, ?SccCritsec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003b413  call    cs:__imp_LeaveCriticalSection
0x18003b419  mov     eax, edi
0x18003b41b  mov     rbx, [rsp+38h+arg_0]
0x18003b420  mov     rsi, [rsp+38h+arg_8]
0x18003b425  add     rsp, 30h
0x18003b429  pop     rdi
0x18003b42a  retn
```
