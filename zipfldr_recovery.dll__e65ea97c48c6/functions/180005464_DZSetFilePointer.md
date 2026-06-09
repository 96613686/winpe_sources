# DZSetFilePointer

- ea: `0x180005464`
- end: `0x1800054d4`
- name: `DZSetFilePointer`
- size: `112`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000496c`
- `0x18000501c`
- `0x180005080`
- `0x1800054dc`
- `0x180015520`
- `0x180015950`
- `0x1800170f0`
- `0x180019008`
- `0x18001b658`
- `0x18001b920`
- `0x18001e3b0`
- `0x180025fd4`
- `0x1800269f0`
- `0x18002f584`

## callees

- `0x180005464`
- `0x180036f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054c8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180005490`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180005490`

## pseudocode

```c
__int64 __fastcall DZSetFilePointer(void *a1, __int64 a2, DWORD a3)
{
  DWORD v3; // eax
  __int64 v4; // rdi
  __int64 v5; // rbx
  LONG DistanceToMoveHigh; // [rsp+20h] [rbp-18h] BYREF

  DistanceToMoveHigh = HIDWORD(a2);
  v3 = SetFilePointer(a1, a2, &DistanceToMoveHigh, a3);
  v4 = v3;
  if ( v3 != -1 )
    return v4 + ((__int64)DistanceToMoveHigh << 32);
  v5 = -1;
  if ( !GetLastError() )
    return v4 + ((__int64)DistanceToMoveHigh << 32);
  return v5;
}

```

## disassembly

```asm
0x180005464  mov     [rsp+arg_18], rbx
0x180005469  push    rdi
0x18000546a  sub     rsp, 30h
0x18000546e  mov     rax, cs:__security_cookie
0x180005475  xor     rax, rsp
0x180005478  mov     [rsp+38h+var_10], rax
0x18000547d  mov     rax, rdx
0x180005480  mov     r9d, r8d; dwMoveMethod
0x180005483  sar     rax, 20h
0x180005487  lea     r8, [rsp+38h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x18000548c  mov     [rsp+38h+DistanceToMoveHigh], eax
0x180005490  call    cs:__imp_SetFilePointer
0x180005496  mov     edi, eax
0x180005498  cmp     eax, 0FFFFFFFFh
0x18000549b  jz      short loc_1800054C4
0x18000549d  movsxd  rbx, [rsp+38h+DistanceToMoveHigh]
0x1800054a2  shl     rbx, 20h
0x1800054a6  add     rbx, rdi
0x1800054a9  mov     rax, rbx
0x1800054ac  mov     rcx, [rsp+38h+var_10]
0x1800054b1  xor     rcx, rsp; StackCookie
0x1800054b4  call    __security_check_cookie
0x1800054b9  mov     rbx, [rsp+38h+arg_18]
0x1800054be  add     rsp, 30h
0x1800054c2  pop     rdi
0x1800054c3  retn
0x1800054c4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800054c8  call    cs:__imp_GetLastError
0x1800054ce  test    eax, eax
0x1800054d0  jnz     short loc_1800054A9
0x1800054d2  jmp     short loc_18000549D
```
