# FileExistsInPath(ushort *,ushort const *,ushort *,ulong)

- ea: `0x18002d714`
- end: `0x18002d76d`
- name: `?FileExistsInPath@@YAHPEAGPEBG0K@Z`
- size: `89`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR lpPath, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002da70`

## callees

- `0x18002d5c8`
- `0x18002d714`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002d745`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18002d745`

## pseudocode

```c
__int64 __fastcall FileExistsInPath(LPCWSTR lpFileName, LPCWSTR lpPath, unsigned __int16 *a3)
{
  unsigned __int64 v4; // rdx
  LPWSTR v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  if ( SearchPathW(lpPath, lpFileName, 0, 0x105u, a3, &v6) - 1 > 0x104 )
    return 0;
  else
    return FileExists(a3, v4);
}

```

## disassembly

```asm
0x18002d714  mov     r11, rsp
0x18002d717  push    rbx
0x18002d718  sub     rsp, 40h
0x18002d71c  mov     rax, rdx
0x18002d71f  mov     qword ptr [r11-18h], 0
0x18002d727  lea     rdx, [r11-18h]
0x18002d72b  mov     rbx, r8
0x18002d72e  mov     [r11-20h], rdx
0x18002d732  mov     r9d, 105h; nBufferLength
0x18002d738  mov     rdx, rcx; lpFileName
0x18002d73b  mov     [r11-28h], rbx
0x18002d73f  mov     rcx, rax; lpPath
0x18002d742  xor     r8d, r8d; lpExtension
0x18002d745  call    cs:__imp_SearchPathW
0x18002d74c  nop     dword ptr [rax+rax+00h]
0x18002d751  dec     eax
0x18002d753  cmp     eax, 104h
0x18002d758  ja      short loc_18002D764
0x18002d75a  mov     rcx, rbx; unsigned __int16 *
0x18002d75d  call    ?FileExists@@YAHPEAG_K@Z; FileExists(ushort *,unsigned __int64)
0x18002d762  jmp     short loc_18002D766
0x18002d764  xor     eax, eax
0x18002d766  add     rsp, 40h
0x18002d76a  pop     rbx
0x18002d76b  retn
```
