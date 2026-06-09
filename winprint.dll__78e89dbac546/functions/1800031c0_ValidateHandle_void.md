# ValidateHandle(void *)

- ea: `0x1800031c0`
- end: `0x1800031ed`
- name: `?ValidateHandle@@YAPEAU_PRINTPROCESSORDATA@@PEAX@Z`
- size: `45`
- prototype: `struct _PRINTPROCESSORDATA *__fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003130`
- `0x1800061f0`

## callees

- `0x1800031c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031e3`

## pseudocode

```c
struct _PRINTPROCESSORDATA *__fastcall ValidateHandle(char *a1)
{
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && *(_DWORD *)a1 == 20561 )
    return (struct _PRINTPROCESSORDATA *)a1;
  SetLastError(6u);
  return 0;
}

```

## disassembly

```asm
0x1800031c0  sub     rsp, 28h
0x1800031c4  lea     rax, [rcx-1]
0x1800031c8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800031cc  ja      short loc_1800031DE
0x1800031ce  cmp     dword ptr [rcx], 5051h
0x1800031d4  jnz     short loc_1800031DE
0x1800031d6  mov     rax, rcx
0x1800031d9  add     rsp, 28h
0x1800031dd  retn
0x1800031de  mov     ecx, 6; dwErrCode
0x1800031e3  call    cs:__imp_SetLastError
0x1800031e9  xor     eax, eax
0x1800031eb  jmp     short loc_1800031D9
```
