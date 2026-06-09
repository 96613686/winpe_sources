# DllMain

- ea: `0x1800145ec`
- end: `0x18001461b`
- name: `DllMain`
- size: `47`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180001c34`

## callees

- `0x1800145ec`
- `0x1800157c8`
- `0x180015800`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx

  if ( fdwReason )
  {
    v3 = fdwReason - 1;
    if ( !(_DWORD)v3 )
    {
      g_hInst = hinstDLL;
      McGenEventRegister_EventRegister(hinstDLL, v3, lpvReserved);
    }
  }
  else if ( !lpvReserved )
  {
    McGenEventUnregister_EventUnregister(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x1800145ec  sub     rsp, 28h
0x1800145f0  test    edx, edx
0x1800145f2  jz      short loc_180014607
0x1800145f4  sub     edx, 1
0x1800145f7  jnz     short loc_180014611
0x1800145f9  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x180014600  call    McGenEventRegister_EventRegister
0x180014605  jmp     short loc_180014611
0x180014607  test    r8, r8
0x18001460a  jnz     short loc_180014611
0x18001460c  call    McGenEventUnregister_EventUnregister
0x180014611  mov     eax, 1
0x180014616  add     rsp, 28h
0x18001461a  retn
```
