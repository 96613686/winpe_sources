# ChangeProp(bool,HWND__ *,ushort const *)

- ea: `0x18002e200`
- end: `0x18002e236`
- name: `?ChangeProp@@YA_N_NPEAUHWND__@@PEBG@Z`
- size: `54`
- prototype: `bool(bool, HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012d70`

## callees

- `0x18002e200`

## import_xrefs

- `USER32!RemovePropW` at `0x18002e225`
- `USER32!RemovePropW` at `0x18002e225`
- `USER32!SetPropW` at `0x18002e21b`
- `USER32!SetPropW` at `0x18002e21b`

## pseudocode

```c
bool __fastcall ChangeProp(char a1, HWND a2, const unsigned __int16 *a3)
{
  bool v3; // zf

  if ( a1 )
    v3 = !SetPropW(a2, L"{811414A8-8e5f-4990-a0a3-f552222e06f7}-pin", HANDLE_FLAG_INHERIT);
  else
    v3 = RemovePropW(a2, L"{811414A8-8e5f-4990-a0a3-f552222e06f7}-pin") == 0;
  return !v3;
}

```

## disassembly

```asm
0x18002e200  sub     rsp, 28h
0x18002e204  mov     rax, rdx
0x18002e207  test    cl, cl
0x18002e209  mov     rcx, rax; hWnd
0x18002e20c  lea     rdx, a811414a88e5f49; "{811414A8-8e5f-4990-a0a3-f552222e06f7}-"...
0x18002e213  jz      short loc_18002E225
0x18002e215  mov     r8d, 1; hData
0x18002e21b  call    cs:__imp_SetPropW
0x18002e221  test    eax, eax
0x18002e223  jmp     short loc_18002E22E
0x18002e225  call    cs:__imp_RemovePropW
0x18002e22b  test    rax, rax
0x18002e22e  setnz   al
0x18002e231  add     rsp, 28h
0x18002e235  retn
```
