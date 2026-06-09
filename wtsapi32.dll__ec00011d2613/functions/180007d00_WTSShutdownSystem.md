# WTSShutdownSystem

- ea: `0x180007d00`
- end: `0x180007db0`
- name: `WTSShutdownSystem`
- size: `176`
- prototype: `BOOL __stdcall(HANDLE hServer, DWORD ShutdownFlag)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d98`
- `ntdll!RtlAdjustPrivilege` at `0x180007d2e`
- `ntdll!RtlAdjustPrivilege` at `0x180007d48`
- `ntdll!RtlAdjustPrivilege` at `0x180007d2e`
- `ntdll!RtlAdjustPrivilege` at `0x180007d48`
- `WINSTA!WinStationShutdownSystem` at `0x180007d88`
- `WINSTA!WinStationShutdownSystem` at `0x180007d88`

## pseudocode

```c
BOOL __stdcall WTSShutdownSystem(HANDLE hServer, DWORD ShutdownFlag)
{
  unsigned int v4; // ebx
  NTSTATUS v5; // eax
  DWORD v6; // ecx
  unsigned __int8 OldValue; // [rsp+30h] [rbp+8h] BYREF

  v4 = 1;
  if ( hServer )
    goto LABEL_6;
  OldValue = 0;
  v5 = RtlAdjustPrivilege(0x13u, 1u, 1u, &OldValue);
  if ( v5 == -1073741700 )
    v5 = RtlAdjustPrivilege(0x13u, 1u, 0, &OldValue);
  if ( v5 >= 0 )
  {
LABEL_6:
    if ( ShutdownFlag != 1 )
    {
      switch ( ShutdownFlag )
      {
        case 2u:
          v4 = 3;
          break;
        case 4u:
          v4 = 7;
          break;
        case 8u:
          v4 = 11;
          break;
        case 0x10u:
          v4 = 20;
          break;
        default:
          v6 = 87;
          goto LABEL_17;
      }
    }
    return (unsigned __int8)WinStationShutdownSystem(hServer, v4);
  }
  v6 = 1314;
LABEL_17:
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x180007d00  mov     rax, rsp
0x180007d03  mov     [rax+10h], rbx
0x180007d07  mov     [rax+18h], rsi
0x180007d0b  push    rdi
0x180007d0c  sub     rsp, 20h
0x180007d10  mov     edi, edx
0x180007d12  mov     rsi, rcx
0x180007d15  mov     ebx, 1
0x180007d1a  test    rcx, rcx
0x180007d1d  jnz     short loc_180007D59
0x180007d1f  mov     [rax+8], cl
0x180007d22  lea     r9, [rax+8]; OldValue
0x180007d26  lea     ecx, [rsi+13h]; Privilege
0x180007d29  mov     r8b, bl; ForThread
0x180007d2c  mov     dl, bl; NewValue
0x180007d2e  call    cs:__imp_RtlAdjustPrivilege
0x180007d34  cmp     eax, 0C000007Ch
0x180007d39  jnz     short loc_180007D4E
0x180007d3b  lea     r9, [rsp+28h+OldValue]; OldValue
0x180007d40  xor     r8d, r8d; ForThread
0x180007d43  mov     dl, bl; NewValue
0x180007d45  lea     ecx, [rsi+13h]; Privilege
0x180007d48  call    cs:__imp_RtlAdjustPrivilege
0x180007d4e  test    eax, eax
0x180007d50  jns     short loc_180007D59
0x180007d52  mov     ecx, 522h
0x180007d57  jmp     short loc_180007D98
0x180007d59  cmp     edi, ebx
0x180007d5b  jz      short loc_180007D83
0x180007d5d  cmp     edi, 2
0x180007d60  jnz     short loc_180007D67
0x180007d62  lea     ebx, [rdi+1]
0x180007d65  jmp     short loc_180007D83
0x180007d67  cmp     edi, 4
0x180007d6a  jnz     short loc_180007D71
0x180007d6c  lea     ebx, [rdi+3]
0x180007d6f  jmp     short loc_180007D83
0x180007d71  cmp     edi, 8
0x180007d74  jnz     short loc_180007D7B
0x180007d76  lea     ebx, [rdi+3]
0x180007d79  jmp     short loc_180007D83
0x180007d7b  cmp     edi, 10h
0x180007d7e  jnz     short loc_180007D93
0x180007d80  lea     ebx, [rdi+4]
0x180007d83  mov     edx, ebx
0x180007d85  mov     rcx, rsi
0x180007d88  call    cs:__imp_WinStationShutdownSystem
0x180007d8e  movzx   eax, al
0x180007d91  jmp     short loc_180007DA0
0x180007d93  mov     ecx, 57h ; 'W'; dwErrCode
0x180007d98  call    cs:__imp_SetLastError
0x180007d9e  xor     eax, eax
0x180007da0  mov     rbx, [rsp+28h+arg_8]
0x180007da5  mov     rsi, [rsp+28h+arg_10]
0x180007daa  add     rsp, 20h
0x180007dae  pop     rdi
0x180007daf  retn
```
