# WriteWS_File

- ea: `0x18003e750`
- end: `0x18003e790`
- name: `WriteWS_File`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003e750`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18003e772`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18003e772`

## pseudocode

```c
__int64 __fastcall WriteWS_File(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax

  result = 0;
  if ( a3 )
    return _o_fwrite(a2, a3, 1, *a1) != 1 ? 0xFFFFFF9A : 0;
  return result;
}

```

## disassembly

```asm
0x18003e750  push    rbx
0x18003e752  sub     rsp, 20h
0x18003e756  xor     eax, eax
0x18003e758  mov     r10, r8
0x18003e75b  mov     r11, rdx
0x18003e75e  test    r8, r8
0x18003e761  jz      short loc_18003E789
0x18003e763  mov     r9, [rcx]
0x18003e766  lea     ebx, [rax+1]
0x18003e769  mov     r8d, ebx
0x18003e76c  mov     rdx, r10
0x18003e76f  mov     rcx, r11
0x18003e772  call    cs:__imp__o_fwrite
0x18003e779  nop     dword ptr [rax+rax+00h]
0x18003e77e  sub     rbx, rax
0x18003e781  neg     rbx
0x18003e784  sbb     eax, eax
0x18003e786  and     eax, 0FFFFFF9Ah
0x18003e789  add     rsp, 20h
0x18003e78d  pop     rbx
0x18003e78e  retn
```
