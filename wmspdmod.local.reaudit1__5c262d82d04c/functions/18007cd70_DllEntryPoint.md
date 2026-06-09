# DllEntryPoint

- ea: `0x18007cd70`
- end: `0x18007cdcd`
- name: `DllEntryPoint`
- size: `93`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18007cd70`
- `0x18007cf00`
- `0x18007cf40`
- `0x1800c6090`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  __int64 v3; // rbp
  int v7; // ebx

  v3 = (unsigned int)dword_18010F3A0;
  if ( fdwReason == 1 && (int)sub_18007CF40() < 0 )
  {
    sub_18007CF00();
    return 0;
  }
  else
  {
    v7 = ((__int64 (__fastcall *)(HINSTANCE, _QWORD, LPVOID))(v3 + 0x180000000LL))(hinstDLL, fdwReason, lpReserved);
    if ( !fdwReason )
      sub_18007CF00();
  }
  return v7;
}

```

## disassembly

```asm
0x18007cd70  push    rbx
0x18007cd72  push    rbp
0x18007cd73  push    rsi
0x18007cd74  push    rdi
0x18007cd75  sub     rsp, 28h
0x18007cd79  mov     ebp, cs:dword_18010F3A0
0x18007cd7f  mov     rbx, r8
0x18007cd82  mov     edi, edx
0x18007cd84  mov     rsi, rcx
0x18007cd87  cmp     edx, 1
0x18007cd8a  jnz     short loc_18007CD9E
0x18007cd8c  call    sub_18007CF40
0x18007cd91  test    eax, eax
0x18007cd93  jns     short loc_18007CD9E
0x18007cd95  call    sub_18007CF00
0x18007cd9a  xor     ebx, ebx
0x18007cd9c  jmp     short loc_18007CDC1
0x18007cd9e  lea     rax, cs:180000000h
0x18007cda5  mov     r8, rbx
0x18007cda8  add     rax, rbp
0x18007cdab  mov     edx, edi
0x18007cdad  mov     rcx, rsi
0x18007cdb0  call    cs:__guard_dispatch_icall_fptr
0x18007cdb6  mov     ebx, eax
0x18007cdb8  test    edi, edi
0x18007cdba  jnz     short loc_18007CDC1
0x18007cdbc  call    sub_18007CF00
0x18007cdc1  mov     eax, ebx
0x18007cdc3  add     rsp, 28h
0x18007cdc7  pop     rdi
0x18007cdc8  pop     rsi
0x18007cdc9  pop     rbp
0x18007cdca  pop     rbx
0x18007cdcb  retn
```
