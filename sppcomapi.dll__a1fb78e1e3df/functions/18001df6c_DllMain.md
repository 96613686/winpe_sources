# DllMain

- ea: `0x18001df6c`
- end: `0x18001df9a`
- name: `DllMain`
- size: `46`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001a04`

## callees

- `0x18001bd4c`
- `0x18001df6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001df80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001df80`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // eax
  int v4; // ebx

  v3 = CSrvDllModuleT<CEmptyType>::DllMain(hinstDLL, fdwReason, lpvReserved);
  v4 = v3;
  if ( v3 < 0 )
    SetLastError((unsigned __int16)v3);
  return v4 >= 0;
}

```

## disassembly

```asm
0x18001df6c  push    rbx
0x18001df6e  sub     rsp, 20h
0x18001df72  call    ?DllMain@?$CSrvDllModuleT@VCEmptyType@@@@SAJPEAUHINSTANCE__@@KPEAX@Z; CSrvDllModuleT<CEmptyType>::DllMain(HINSTANCE__ *,ulong,void *)
0x18001df77  mov     ebx, eax
0x18001df79  test    eax, eax
0x18001df7b  jns     short loc_18001DF8C
0x18001df7d  movzx   ecx, bx; dwErrCode
0x18001df80  call    cs:__imp_SetLastError
0x18001df87  nop     dword ptr [rax+rax+00h]
0x18001df8c  not     ebx
0x18001df8e  shr     ebx, 1Fh
0x18001df91  mov     eax, ebx
0x18001df93  add     rsp, 20h
0x18001df97  pop     rbx
0x18001df98  retn
```
