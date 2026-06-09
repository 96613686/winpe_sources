# CTimer::Start(ulong)

- ea: `0x14000e534`
- end: `0x14000e570`
- name: `?Start@CTimer@@QEAAJK@Z`
- size: `60`
- prototype: `int(CTimer *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140007dc8`
- `0x14000c740`
- `0x140010420`

## callees

- `0x14000e534`

## import_xrefs

- `USER32!SendMessageA` at `0x14000e555`
- `USER32!SendMessageA` at `0x14000e555`

## pseudocode

```c
__int64 __fastcall CTimer::Start(HWND *this, unsigned int a2)
{
  HWND v3; // rcx
  __int64 result; // rax

  v3 = *this;
  if ( !v3 )
    return 1;
  SendMessageA(v3, 0x401u, a2, 0);
  result = *((unsigned int *)this + 6);
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14000e534  push    rbx
0x14000e536  sub     rsp, 20h
0x14000e53a  mov     rbx, rcx
0x14000e53d  mov     rcx, [rcx]; hWnd
0x14000e540  test    rcx, rcx
0x14000e543  jnz     short loc_14000E54A
0x14000e545  lea     eax, [rcx+1]
0x14000e548  jmp     short loc_14000E56A
0x14000e54a  mov     r8d, edx; wParam
0x14000e54d  xor     r9d, r9d; lParam
0x14000e550  mov     edx, 401h; Msg
0x14000e555  call    cs:__imp_SendMessageA
0x14000e55b  mov     eax, [rbx+18h]
0x14000e55e  test    eax, eax
0x14000e560  jle     short loc_14000E56A
0x14000e562  movzx   eax, ax
0x14000e565  or      eax, 80070000h
0x14000e56a  add     rsp, 20h
0x14000e56e  pop     rbx
0x14000e56f  retn
```
