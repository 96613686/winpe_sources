# GetConnectionPointer

- ea: `0x18000cda0`
- end: `0x18000ce36`
- name: `GetConnectionPointer`
- size: `150`
- prototype: ``
- caller_count: `102`
- callee_count: `1`
- tags: ``

## callers

- `0x1800013c0`
- `0x18000b760`
- `0x18000b860`
- `0x18000b990`
- `0x18000bb00`
- `0x18000bbf0`
- `0x18000bf40`
- `0x1800153c0`
- `0x180016360`
- `0x180017780`
- `0x1800188d0`
- `0x18001b0d4`
- `0x18001b970`
- `0x18001f1d0`
- `0x180028a60`
- `0x180029e70`
- `0x180029f50`
- `0x18002a4f0`
- `0x18002ae10`
- `0x18002bd70`
- `0x18002c860`
- `0x18002c940`
- `0x18002cc80`
- `0x18002cdd0`
- `0x18002cea0`
- `0x18002dd90`
- `0x18002e180`
- `0x18002e6d4`
- `0x180030cd0`
- `0x180039ac0`
- `0x18003a640`
- `0x18003a750`
- `0x18003a8b0`
- `0x18003a9b0`
- `0x18003abb0`
- `0x18003bd34`
- `0x18003bf50`
- `0x18003c070`
- `0x18003c170`
- `0x18003c9e0`
- `0x18003caf0`
- `0x18003cd20`
- `0x18003ce30`
- `0x18003d0d0`
- `0x18003e7f0`
- `0x18003e950`
- `0x18003ea40`
- `0x18003ec30`
- `0x18003f420`
- `0x18003f500`

## callees

- `0x18000cda0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cdc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cdc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cde0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cde0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce15`

## pseudocode

```c
__int64 __fastcall GetConnectionPointer(__int64 a1)
{
  __int64 v1; // rbx
  struct _RTL_CRITICAL_SECTION *v2; // rcx

  if ( !a1 )
    return 0;
  v1 = a1 - 904;
  if ( *(_QWORD *)(a1 - 904 + 448) != a1 )
    return 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 512));
  v2 = (struct _RTL_CRITICAL_SECTION *)(v1 + 512);
  if ( *(_DWORD *)v1 && *(_BYTE *)(v1 + 552) == 1 )
  {
    ++*(_DWORD *)v1;
    LeaveCriticalSection(v2);
    return v1;
  }
  else
  {
    LeaveCriticalSection(v2);
    return 0;
  }
}

```

## disassembly

```asm
0x18000cda0  push    rbx
0x18000cda2  sub     rsp, 30h
0x18000cda6  test    rcx, rcx
0x18000cda9  jz      short loc_18000CE0D
0x18000cdab  lea     rbx, [rcx-388h]
0x18000cdb2  mov     [rsp+38h+var_18], rbx
0x18000cdb7  cmp     [rbx+1C0h], rcx
0x18000cdbe  jnz     short loc_18000CE09
0x18000cdc0  lea     rcx, [rbx+200h]; lpCriticalSection
0x18000cdc7  call    cs:__imp_EnterCriticalSection
0x18000cdce  nop     dword ptr [rax+rax+00h]
0x18000cdd3  mov     eax, [rbx]
0x18000cdd5  lea     rcx, [rbx+200h]; lpCriticalSection
0x18000cddc  test    eax, eax
0x18000cdde  jnz     short loc_18000CDF0
0x18000cde0  call    cs:__imp_LeaveCriticalSection
0x18000cde7  nop     dword ptr [rax+rax+00h]
0x18000cdec  xor     eax, eax
0x18000cdee  jmp     short loc_18000CE25
0x18000cdf0  cmp     byte ptr [rbx+228h], 1
0x18000cdf7  jz      short loc_18000CE11
0x18000cdf9  call    cs:__imp_LeaveCriticalSection
0x18000ce00  nop     dword ptr [rax+rax+00h]
0x18000ce05  xor     eax, eax
0x18000ce07  jmp     short loc_18000CE25
0x18000ce09  xor     eax, eax
0x18000ce0b  jmp     short loc_18000CE25
0x18000ce0d  xor     eax, eax
0x18000ce0f  jmp     short loc_18000CE25
0x18000ce11  inc     eax
0x18000ce13  mov     [rbx], eax
0x18000ce15  call    cs:__imp_LeaveCriticalSection
0x18000ce1c  nop     dword ptr [rax+rax+00h]
0x18000ce21  jmp     short loc_18000CE2C
0x18000ce23  xor     eax, eax
0x18000ce25  add     rsp, 30h
0x18000ce29  pop     rbx
0x18000ce2a  retn
0x18000ce2c  mov     rax, rbx
0x18000ce2f  add     rsp, 30h
0x18000ce33  pop     rbx
0x18000ce34  retn
```
