# PrepareResolverEntry

- ea: `0x180010f3c`
- end: `0x180011029`
- name: `PrepareResolverEntry`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008c10`

## callees

- `0x180010f3c`

## import_xrefs

- `ntdll!NtClearEvent` at `0x180011007`
- `ntdll!NtClearEvent` at `0x180011007`
- `ntdll!NtCreateEvent` at `0x180010ff0`
- `ntdll!NtCreateEvent` at `0x180010ff0`
- `USER32!EnumThreadWindows` at `0x180010fb8`
- `USER32!EnumThreadWindows` at `0x180010fb8`
- `USER32!IsWindowVisible` at `0x180010f73`
- `USER32!IsWindowVisible` at `0x180010f73`
- `USER32!ShutdownBlockReasonQuery` at `0x180010f91`
- `USER32!ShutdownBlockReasonQuery` at `0x180010f91`

## pseudocode

```c
_BOOL8 __fastcall PrepareResolverEntry(__int64 a1, _QWORD *a2)
{
  HWND v3; // rbx
  DWORD v4; // esi
  void *v5; // rcx
  HWND pcchBuff; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 8) = a1;
  *(_QWORD *)a1 = a1;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = a2[3];
  v3 = (HWND)a2[4];
  v4 = *(_DWORD *)(a2[2] + 48LL);
  if ( !IsWindowVisible(v3) )
  {
    LODWORD(pcchBuff) = 0;
    if ( !ShutdownBlockReasonQuery(v3, 0, (DWORD *)&pcchBuff) )
    {
      pcchBuff = 0;
      EnumThreadWindows(v4, FindReasonOrVisibleWindowFromThread, (LPARAM)&pcchBuff);
      if ( pcchBuff )
        v3 = pcchBuff;
    }
  }
  v5 = *(void **)(a1 + 32);
  *(_QWORD *)(a1 + 16) = v3;
  if ( !v5 )
    return NtCreateEvent((PHANDLE)(a1 + 32), 0x1F0003u, 0, NotificationEvent, 0) >= 0;
  NtClearEvent(v5);
  return 1;
}

```

## disassembly

```asm
0x180010f3c  mov     [rsp+arg_8], rbx
0x180010f41  mov     [rsp+arg_10], rsi
0x180010f46  push    rdi
0x180010f47  sub     rsp, 30h
0x180010f4b  mov     [rcx+8], rcx
0x180010f4f  mov     rdi, rcx
0x180010f52  mov     [rcx], rcx
0x180010f55  mov     qword ptr [rcx+10h], 0
0x180010f5d  mov     rax, [rdx+18h]
0x180010f61  mov     [rcx+18h], rax
0x180010f65  mov     rax, [rdx+10h]
0x180010f69  mov     rbx, [rdx+20h]
0x180010f6d  mov     rcx, rbx; hWnd
0x180010f70  mov     esi, [rax+30h]
0x180010f73  call    cs:__imp_IsWindowVisible
0x180010f7a  nop     dword ptr [rax+rax+00h]
0x180010f7f  test    eax, eax
0x180010f81  jnz     short loc_180010FD0
0x180010f83  lea     r8, [rsp+38h+pcchBuff]; pcchBuff
0x180010f88  mov     dword ptr [rsp+38h+pcchBuff], eax
0x180010f8c  xor     edx, edx; pwszBuff
0x180010f8e  mov     rcx, rbx; hWnd
0x180010f91  call    cs:__imp_ShutdownBlockReasonQuery
0x180010f98  nop     dword ptr [rax+rax+00h]
0x180010f9d  test    eax, eax
0x180010f9f  jnz     short loc_180010FD0
0x180010fa1  lea     r8, [rsp+38h+pcchBuff]; lParam
0x180010fa6  mov     [rsp+38h+pcchBuff], 0
0x180010faf  lea     rdx, FindReasonOrVisibleWindowFromThread; lpfn
0x180010fb6  mov     ecx, esi; dwThreadId
0x180010fb8  call    cs:__imp_EnumThreadWindows
0x180010fbf  nop     dword ptr [rax+rax+00h]
0x180010fc4  mov     rax, [rsp+38h+pcchBuff]
0x180010fc9  test    rax, rax
0x180010fcc  cmovnz  rbx, rax
0x180010fd0  mov     rcx, [rdi+20h]; EventHandle
0x180010fd4  mov     [rdi+10h], rbx
0x180010fd8  test    rcx, rcx
0x180010fdb  jnz     short loc_180011007
0x180010fdd  mov     [rsp+38h+InitialState], cl; InitialState
0x180010fe1  xor     r9d, r9d; EventType
0x180010fe4  lea     rcx, [rdi+20h]; EventHandle
0x180010fe8  xor     r8d, r8d; ObjectAttributes
0x180010feb  mov     edx, 1F0003h; DesiredAccess
0x180010ff0  call    cs:__imp_NtCreateEvent
0x180010ff7  nop     dword ptr [rax+rax+00h]
0x180010ffc  xor     ecx, ecx
0x180010ffe  test    eax, eax
0x180011000  setns   cl
0x180011003  mov     eax, ecx
0x180011005  jmp     short loc_180011018
0x180011007  call    cs:__imp_NtClearEvent
0x18001100e  nop     dword ptr [rax+rax+00h]
0x180011013  mov     eax, 1
0x180011018  mov     rbx, [rsp+38h+arg_8]
0x18001101d  mov     rsi, [rsp+38h+arg_10]
0x180011022  add     rsp, 30h
0x180011026  pop     rdi
0x180011027  retn
```
