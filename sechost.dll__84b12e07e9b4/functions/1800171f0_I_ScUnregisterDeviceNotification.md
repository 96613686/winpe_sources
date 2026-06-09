# I_ScUnregisterDeviceNotification

- ea: `0x1800171f0`
- end: `0x180017269`
- name: `I_ScUnregisterDeviceNotification`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800171f0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017233`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180017233`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180017224`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180017224`
- `ntdll!RtlDllShutdownInProgress` at `0x180017216`
- `ntdll!RtlDllShutdownInProgress` at `0x180017216`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001724c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001724c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001723d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001723d`

## pseudocode

```c
_BOOL8 __fastcall I_ScUnregisterDeviceNotification(__int64 a1)
{
  DWORD v2; // esi

  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *(_DWORD *)a1 == 1450748877 )
  {
    v2 = 0;
    if ( !RtlDllShutdownInProgress() )
    {
      RtlAcquireSRWLockExclusive(a1 + 8);
      *(_DWORD *)a1 = 0;
      *(_DWORD *)(a1 + 20) = 0;
      RtlReleaseSRWLockExclusive(a1 + 8);
      SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 64));
    }
  }
  else
  {
    v2 = 6;
  }
  SetLastError(v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x1800171f0  mov     [rsp+arg_0], rbx
0x1800171f5  mov     [rsp+arg_8], rsi
0x1800171fa  push    rdi
0x1800171fb  sub     rsp, 20h
0x1800171ff  lea     rax, [rcx-1]
0x180017203  mov     rdi, rcx
0x180017206  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001720a  ja      short loc_180017245
0x18001720c  cmp     dword ptr [rcx], 5678ABCDh
0x180017212  jnz     short loc_180017245
0x180017214  xor     esi, esi
0x180017216  call    cs:__imp_RtlDllShutdownInProgress
0x18001721c  test    al, al
0x18001721e  jnz     short loc_18001724A
0x180017220  lea     rcx, [rdi+8]
0x180017224  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001722a  lea     rcx, [rdi+8]
0x18001722e  mov     [rdi], esi
0x180017230  mov     [rdi+14h], esi
0x180017233  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180017239  mov     rcx, [rdi+40h]; pwk
0x18001723d  call    cs:__imp_SubmitThreadpoolWork
0x180017243  jmp     short loc_18001724A
0x180017245  mov     esi, 6
0x18001724a  mov     ecx, esi; dwErrCode
0x18001724c  call    cs:__imp_SetLastError
0x180017252  mov     rbx, [rsp+28h+arg_0]
0x180017257  xor     eax, eax
0x180017259  test    esi, esi
0x18001725b  mov     rsi, [rsp+28h+arg_8]
0x180017260  setz    al
0x180017263  add     rsp, 20h
0x180017267  pop     rdi
0x180017268  retn
```
