# UmpoTraceOverlaySchemeSuspend

- ea: `0x18000c658`
- end: `0x18000c6cd`
- name: `UmpoTraceOverlaySchemeSuspend`
- size: `117`
- prototype: `__int64 __fastcall(int, char)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f4f4`

## callees

- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000c6b5`
- `ntdll!EtwEventWrite` at `0x18000c6b5`

## pseudocode

```c
__int64 __fastcall UmpoTraceOverlaySchemeSuspend(int a1, char a2)
{
  BOOL v3; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v4[4]; // [rsp+28h] [rbp-30h] BYREF
  int v5; // [rsp+60h] [rbp+8h] BYREF

  v5 = a1;
  v4[1] = 4;
  v4[3] = 4;
  v3 = a2 != 0;
  v4[0] = &v5;
  v4[2] = &v3;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_OVERLAY_SUSPEND_RESUME, 2, v4);
}

```

## disassembly

```asm
0x18000c658  mov     [rsp+arg_0], ecx
0x18000c65c  mov     r11, rsp
0x18000c65f  sub     rsp, 58h
0x18000c663  mov     rax, cs:__security_cookie
0x18000c66a  xor     rax, rsp
0x18000c66d  mov     [rsp+58h+var_10], rax
0x18000c672  mov     rcx, cs:UmpoProviderHandle
0x18000c679  lea     r9, [r11-30h]
0x18000c67d  xor     eax, eax
0x18000c67f  mov     qword ptr [r11-28h], 4
0x18000c687  test    dl, dl
0x18000c689  mov     qword ptr [r11-18h], 4
0x18000c691  mov     r8d, 2
0x18000c697  lea     rdx, UMPO_EVT_OVERLAY_SUSPEND_RESUME
0x18000c69e  setnz   al
0x18000c6a1  mov     [rsp+58h+var_38], eax
0x18000c6a5  lea     rax, [r11+8]
0x18000c6a9  mov     [r11-30h], rax
0x18000c6ad  lea     rax, [r11-38h]
0x18000c6b1  mov     [r11-20h], rax
0x18000c6b5  call    cs:__imp_EtwEventWrite
0x18000c6bb  mov     rcx, [rsp+58h+var_10]
0x18000c6c0  xor     rcx, rsp; StackCookie
0x18000c6c3  call    __security_check_cookie
0x18000c6c8  add     rsp, 58h
0x18000c6cc  retn
```
