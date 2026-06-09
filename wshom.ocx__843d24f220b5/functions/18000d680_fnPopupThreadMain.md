# fnPopupThreadMain

- ea: `0x18000d680`
- end: `0x18000d699`
- name: `fnPopupThreadMain`
- size: `25`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `USER32!MessageBoxW` at `0x18000d692`

## pseudocode

```c
int __fastcall fnPopupThreadMain(LPCWSTR *lpThreadParameter)
{
  return MessageBoxW(0, *lpThreadParameter, lpThreadParameter[1], *((_DWORD *)lpThreadParameter + 4) | 0x10000);
}

```

## disassembly

```asm
0x18000d680  mov     r9d, [rcx+10h]
0x18000d684  mov     r8, [rcx+8]
0x18000d688  bts     r9d, 10h
0x18000d68d  mov     rdx, [rcx]
0x18000d690  xor     ecx, ecx
0x18000d692  jmp     cs:__imp_MessageBoxW
```
