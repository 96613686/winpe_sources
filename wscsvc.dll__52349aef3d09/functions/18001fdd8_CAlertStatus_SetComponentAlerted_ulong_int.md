# CAlertStatus::SetComponentAlerted(ulong,int)

- ea: `0x18001fdd8`
- end: `0x18001fe3a`
- name: `?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z`
- size: `98`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int, int)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d9e0`
- `0x180024b40`
- `0x1800250c0`
- `0x180025520`
- `0x180026450`
- `0x180038a1c`
- `0x180038b20`

## callees

- `0x18001fdd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fe11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fe11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fdfa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fdfa`

## pseudocode

```c
__int64 __fastcall CAlertStatus::SetComponentAlerted(LPCRITICAL_SECTION lpCriticalSection, unsigned int a2, int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int DebugInfo_high; // eax
  int v9; // eax

  if ( a2 <= 8 && (v6 = 278, _bittest(&v6, a2)) )
  {
    v7 = 0;
    EnterCriticalSection(lpCriticalSection);
    DebugInfo_high = HIDWORD(lpCriticalSection[1].DebugInfo);
    if ( a3 )
      v9 = a2 | DebugInfo_high;
    else
      v9 = ~a2 & DebugInfo_high;
    HIDWORD(lpCriticalSection[1].DebugInfo) = v9;
    LeaveCriticalSection(lpCriticalSection);
  }
  else
  {
    v7 = 87;
  }
  if ( v7 )
    v7 |= 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x18001fdd8  push    rbx
0x18001fdda  push    rbp
0x18001fddb  push    rsi
0x18001fddc  push    rdi
0x18001fddd  sub     rsp, 28h
0x18001fde1  mov     ebp, r8d
0x18001fde4  mov     edi, edx
0x18001fde6  mov     rsi, rcx
0x18001fde9  cmp     edx, 8
0x18001fdec  ja      short loc_18001FE2F
0x18001fdee  mov     eax, 116h
0x18001fdf3  bt      eax, edx
0x18001fdf6  jnb     short loc_18001FE2F
0x18001fdf8  xor     ebx, ebx
0x18001fdfa  call    cs:__imp_EnterCriticalSection
0x18001fe00  mov     eax, [rsi+2Ch]
0x18001fe03  test    ebp, ebp
0x18001fe05  jnz     short loc_18001FE36
0x18001fe07  not     edi
0x18001fe09  and     eax, edi
0x18001fe0b  mov     rcx, rsi; lpCriticalSection
0x18001fe0e  mov     [rsi+2Ch], eax
0x18001fe11  call    cs:__imp_LeaveCriticalSection
0x18001fe17  mov     ecx, ebx
0x18001fe19  or      ecx, 80070000h
0x18001fe1f  test    ebx, ebx
0x18001fe21  cmovnz  ebx, ecx
0x18001fe24  mov     eax, ebx
0x18001fe26  add     rsp, 28h
0x18001fe2a  pop     rdi
0x18001fe2b  pop     rsi
0x18001fe2c  pop     rbp
0x18001fe2d  pop     rbx
0x18001fe2e  retn
0x18001fe2f  mov     ebx, 57h ; 'W'
0x18001fe34  jmp     short loc_18001FE17
0x18001fe36  or      eax, edi
0x18001fe38  jmp     short loc_18001FE0B
```
