# _get_image_app_type

- ea: `0x1400015d4`
- end: `0x14000161a`
- name: `_get_image_app_type`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001010`

## callees

- `0x14000157c`
- `0x1400015d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400015de`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400015de`

## pseudocode

```c
__int64 __fastcall get_image_app_type(unsigned int a1)
{
  HMODULE ModuleHandleW; // rax
  __int64 v3; // rax

  ModuleHandleW = GetModuleHandleW(0);
  if ( ModuleHandleW )
  {
    v3 = RtlpImageNtHeader((__int64)ModuleHandleW);
    if ( v3 )
    {
      if ( *(_WORD *)(v3 + 92) == 2 )
        return 2;
      if ( *(_WORD *)(v3 + 92) == 3 )
        return 1;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400015d4  push    rbx
0x1400015d6  sub     rsp, 20h
0x1400015da  mov     ebx, ecx
0x1400015dc  xor     ecx, ecx; lpModuleName
0x1400015de  call    cs:__imp_GetModuleHandleW
0x1400015e4  test    rax, rax
0x1400015e7  jz      short loc_140001612
0x1400015e9  mov     rcx, rax
0x1400015ec  call    RtlpImageNtHeader
0x1400015f1  test    rax, rax
0x1400015f4  jz      short loc_140001612
0x1400015f6  mov     ecx, 2
0x1400015fb  cmp     [rax+5Ch], cx
0x1400015ff  jnz     short loc_140001605
0x140001601  mov     eax, ecx
0x140001603  jmp     short loc_140001614
0x140001605  cmp     word ptr [rax+5Ch], 3
0x14000160a  mov     ecx, 1
0x14000160f  cmovz   ebx, ecx
0x140001612  mov     eax, ebx
0x140001614  add     rsp, 20h
0x140001618  pop     rbx
0x140001619  retn
```
