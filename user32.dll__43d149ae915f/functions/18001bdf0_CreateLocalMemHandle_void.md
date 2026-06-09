# CreateLocalMemHandle(void *)

- ea: `0x18001bdf0`
- end: `0x18001be63`
- name: `?CreateLocalMemHandle@@YAPEAXPEAX@Z`
- size: `115`
- prototype: `void *__fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001af90`

## callees

- `0x18001bdf0`

## import_xrefs

- `win32u!NtUserCreateLocalMemHandle` at `0x18001be0f`
- `win32u!NtUserCreateLocalMemHandle` at `0x18001be3e`
- `win32u!NtUserCreateLocalMemHandle` at `0x18001be0f`
- `win32u!NtUserCreateLocalMemHandle` at `0x18001be3e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001be59`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001be59`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001be22`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001be22`

## pseudocode

```c
void *__fastcall CreateLocalMemHandle(void *a1)
{
  HGLOBAL v2; // rax
  void *v3; // rbx
  SIZE_T dwBytes; // [rsp+38h] [rbp+10h] BYREF

  LODWORD(dwBytes) = 0;
  if ( (unsigned int)NtUserCreateLocalMemHandle(a1, 0, 0, &dwBytes) != -1073741789 )
    return 0;
  v2 = GlobalAlloc(0, (unsigned int)dwBytes);
  v3 = v2;
  if ( !v2 )
    return 0;
  if ( (int)NtUserCreateLocalMemHandle(a1, v2, (unsigned int)dwBytes, 0) < 0 )
  {
    GlobalFree(v3);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18001bdf0  mov     [rsp+arg_0], rbx
0x18001bdf5  push    rdi
0x18001bdf6  sub     rsp, 20h
0x18001bdfa  lea     r9, [rsp+28h+dwBytes]
0x18001bdff  mov     dword ptr [rsp+28h+dwBytes], 0
0x18001be07  xor     r8d, r8d
0x18001be0a  xor     edx, edx
0x18001be0c  mov     rdi, rcx
0x18001be0f  call    cs:__imp_NtUserCreateLocalMemHandle
0x18001be15  cmp     eax, 0C0000023h
0x18001be1a  jnz     short loc_18001BE5F
0x18001be1c  mov     edx, dword ptr [rsp+28h+dwBytes]; dwBytes
0x18001be20  xor     ecx, ecx; uFlags
0x18001be22  call    cs:__imp_GlobalAlloc
0x18001be28  mov     rbx, rax
0x18001be2b  test    rax, rax
0x18001be2e  jz      short loc_18001BE5F
0x18001be30  mov     r8d, dword ptr [rsp+28h+dwBytes]
0x18001be35  xor     r9d, r9d
0x18001be38  mov     rdx, rax
0x18001be3b  mov     rcx, rdi
0x18001be3e  call    cs:__imp_NtUserCreateLocalMemHandle
0x18001be44  test    eax, eax
0x18001be46  js      short loc_18001BE56
0x18001be48  mov     rax, rbx
0x18001be4b  mov     rbx, [rsp+28h+arg_0]
0x18001be50  add     rsp, 20h
0x18001be54  pop     rdi
0x18001be55  retn
0x18001be56  mov     rcx, rbx; hMem
0x18001be59  call    cs:__imp_GlobalFree
0x18001be5f  xor     ebx, ebx
0x18001be61  jmp     short loc_18001BE48
```
