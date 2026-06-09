# DriverCallback_0

- ea: `0x180002500`
- end: `0x180002590`
- name: `DriverCallback_0`
- size: `144`
- prototype: `BOOL __stdcall(DWORD_PTR dwCallback, DWORD dwFlags, HDRVR hDevice, DWORD dwMsg, DWORD_PTR dwUser, DWORD_PTR dwParam1, DWORD_PTR dwParam2)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000f320`

## callees

- `0x180002500`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002560`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002560`
- `WINMMBASE!mmTaskSignal` at `0x180002578`
- `WINMMBASE!mmTaskSignal` at `0x180002578`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageA` at `0x180002588`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageA` at `0x180002588`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x180002570`
- `ext-ms-win-ntuser-message-l1-1-0!PostThreadMessageA` at `0x180002570`

## pseudocode

```c
BOOL __stdcall DriverCallback_0(
        DWORD_PTR dwCallback,
        DWORD dwFlags,
        HDRVR hDevice,
        DWORD dwMsg,
        DWORD_PTR dwUser,
        DWORD_PTR dwParam1,
        DWORD_PTR dwParam2)
{
  DWORD v7; // ebx
  DWORD v8; // edx
  DWORD v10; // edx
  DWORD v11; // edx

  v7 = dwCallback;
  if ( !dwCallback )
    return 0;
  v8 = dwFlags & 7;
  if ( v8 == 3 )
  {
    ((void (__fastcall *)(HDRVR, _QWORD, DWORD_PTR, DWORD_PTR, DWORD_PTR))dwCallback)(
      hDevice,
      dwMsg,
      dwUser,
      dwParam1,
      dwParam2);
    return 1;
  }
  v10 = v8 - 1;
  if ( !v10 )
    return PostMessageA((HWND)dwCallback, dwMsg, (WPARAM)hDevice, dwParam1);
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 3 )
    {
      SetEvent((HANDLE)dwCallback);
      return 1;
    }
    return 0;
  }
  PostThreadMessageA(dwCallback, dwMsg, (WPARAM)hDevice, dwParam1);
  return mmTaskSignal(v7);
}

```

## disassembly

```asm
0x180002500  push    rbx
0x180002502  sub     rsp, 30h
0x180002506  mov     r10d, r9d
0x180002509  mov     r11, r8
0x18000250c  mov     rbx, rcx
0x18000250f  test    rcx, rcx
0x180002512  jz      short loc_180002558
0x180002514  and     edx, 7
0x180002517  cmp     edx, 3
0x18000251a  jnz     short loc_180002549
0x18000251c  mov     rax, [rsp+38h+dwParam2]
0x180002521  mov     edx, r10d
0x180002524  mov     r9, [rsp+38h+dwParam1]
0x180002529  mov     rcx, r11
0x18000252c  mov     r8, [rsp+38h+dwUser]
0x180002531  mov     [rsp+38h+var_18], rax
0x180002536  mov     rax, rbx
0x180002539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000253e  mov     eax, 1
0x180002543  add     rsp, 30h
0x180002547  pop     rbx
0x180002548  retn
0x180002549  sub     edx, 1
0x18000254c  jz      short loc_180002580
0x18000254e  sub     edx, 1
0x180002551  jz      short loc_180002568
0x180002553  cmp     edx, 3
0x180002556  jz      short loc_180002560
0x180002558  xor     eax, eax
0x18000255a  add     rsp, 30h
0x18000255e  pop     rbx
0x18000255f  retn
0x180002560  call    cs:__imp_SetEvent
0x180002566  jmp     short loc_18000253E
0x180002568  mov     r9, [rsp+38h+dwParam1]; lParam
0x18000256d  mov     edx, r10d; Msg
0x180002570  call    cs:__imp_PostThreadMessageA
0x180002576  mov     ecx, ebx; h
0x180002578  call    cs:__imp_mmTaskSignal
0x18000257e  jmp     short loc_180002543
0x180002580  mov     r9, [rsp+38h+dwParam1]; lParam
0x180002585  mov     edx, r10d; Msg
0x180002588  call    cs:__imp_PostMessageA
0x18000258e  jmp     short loc_180002543
```
