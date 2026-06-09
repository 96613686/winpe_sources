# SecpFileNameFromPath(ushort *)

- ea: `0x18000e148`
- end: `0x18000e170`
- name: `?SecpFileNameFromPath@@YAPEAGPEAG@Z`
- size: `40`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d8ac`
- `0x18001caa0`

## callees

- `0x18000e148`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!wcsrchr` at `0x18000e156`
- `api-ms-win-core-crt-l1-1-0!wcsrchr` at `0x18000e156`

## pseudocode

```c
unsigned __int16 *__fastcall SecpFileNameFromPath(unsigned __int16 *a1)
{
  unsigned __int16 *v1; // rbx
  wchar_t *v2; // rax

  v1 = a1;
  v2 = wcsrchr(a1, 0x5Cu);
  if ( v2 )
    return v2 + 1;
  return v1;
}

```

## disassembly

```asm
0x18000e148  push    rbx
0x18000e14a  sub     rsp, 20h
0x18000e14e  mov     edx, 5Ch ; '\'; Ch
0x18000e153  mov     rbx, rcx
0x18000e156  call    cs:__imp_wcsrchr
0x18000e15c  test    rax, rax
0x18000e15f  jnz     short loc_18000E16A
0x18000e161  mov     rax, rbx
0x18000e164  add     rsp, 20h
0x18000e168  pop     rbx
0x18000e169  retn
0x18000e16a  lea     rbx, [rax+2]
0x18000e16e  jmp     short loc_18000E161
```
