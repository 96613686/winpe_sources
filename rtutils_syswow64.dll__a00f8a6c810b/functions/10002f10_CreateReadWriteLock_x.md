# CreateReadWriteLock(x)

- ea: `0x10002f10`
- end: `0x10002f90`
- name: `_CreateReadWriteLock@4`
- size: `128`
- prototype: `int __thiscall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x10002610`
- `0x10002e60`
- `0x100031ff`

## callees

- `0x10002f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10002f56`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x10002f56`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10005790`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10005790`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10002f6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x10002f6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10005796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10005796`

## pseudocode

```c
DWORD __thiscall CreateReadWriteLock(LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE EventA; // eax

  lpCriticalSection[1].DebugInfo = 0;
  InitializeCriticalSection(lpCriticalSection);
  EventA = CreateEventA(0, 0, 0, 0);
  lpCriticalSection[1].LockCount = (LONG)EventA;
  if ( EventA )
    return 0;
  DeleteCriticalSection(lpCriticalSection);
  return GetLastError();
}

```

## disassembly

```asm
0x10002f10  mov     edi, edi
0x10002f12  push    ebp
0x10002f13  mov     ebp, esp
0x10002f15  push    0FFFFFFFEh
0x10002f17  push    offset stru_1000A6D0
0x10002f1c  push    offset __except_handler4
0x10002f21  mov     eax, large fs:0
0x10002f27  push    eax
0x10002f28  sub     esp, 0Ch
0x10002f2b  push    ebx
0x10002f2c  push    esi
0x10002f2d  push    edi
0x10002f2e  mov     eax, ___security_cookie
0x10002f33  xor     [ebp+ms_exc.registration.ScopeTable], eax
0x10002f36  xor     eax, ebp
0x10002f38  push    eax
0x10002f39  lea     eax, [ebp+ms_exc.registration]
0x10002f3c  mov     large fs:0, eax
0x10002f42  mov     [ebp+ms_exc.old_esp], esp
0x10002f45  mov     esi, ecx
0x10002f47  mov     dword ptr [esi+18h], 0
0x10002f4e  mov     [ebp+ms_exc.registration.TryLevel], 0
0x10002f55  push    esi; lpCriticalSection
0x10002f56  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10002f5c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x10002f63  push    0; lpName
0x10002f65  push    0; bInitialState
0x10002f67  push    0; bManualReset
0x10002f69  push    0; lpEventAttributes
0x10002f6b  call    ds:__imp__CreateEventA@16; CreateEventA(x,x,x,x)
0x10002f71  mov     [esi+1Ch], eax
0x10002f74  test    eax, eax
0x10002f76  jz      loc_1000578F
0x10002f7c  xor     eax, eax
0x10002f7e  mov     ecx, [ebp+ms_exc.registration.Next]
0x10002f81  mov     large fs:0, ecx
0x10002f88  pop     ecx
0x10002f89  pop     edi
0x10002f8a  pop     esi
0x10002f8b  pop     ebx
0x10002f8c  mov     esp, ebp
0x10002f8e  pop     ebp
0x10002f8f  retn
0x1000578f  push    esi; lpCriticalSection
0x10005790  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10005796  call    ds:__imp__GetLastError@0; GetLastError()
0x1000579c  jmp     loc_10002F7E
0x100057a1  mov     eax, [ebp+ms_exc.exc_ptr]
0x100057a4  mov     eax, [eax]
0x100057a6  mov     eax, [eax]
0x100057a8  mov     [ebp+var_1C], eax
0x100057ab  mov     eax, 1
0x100057b0  retn
0x100057b1  mov     esp, [ebp+ms_exc.old_esp]
0x100057b4  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100057bb  mov     eax, [ebp+var_1C]
0x100057be  jmp     loc_10002F7E
```
