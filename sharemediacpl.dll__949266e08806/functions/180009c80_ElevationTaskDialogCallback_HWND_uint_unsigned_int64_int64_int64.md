# ElevationTaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x180009c80`
- end: `0x180009ca3`
- name: `?ElevationTaskDialogCallback@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `35`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64, WPARAM wParam)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009c80`

## import_xrefs

- `USER32!SendMessageW` at `0x180009c96`
- `USER32!SendMessageW` at `0x180009c96`

## pseudocode

```c
__int64 __fastcall ElevationTaskDialogCallback(HWND a1, int a2, __int64 a3, __int64 a4, WPARAM wParam)
{
  if ( !a2 )
    SendMessageW(a1, 0x473u, wParam, 1);
  return 0;
}

```

## disassembly

```asm
0x180009c80  sub     rsp, 28h
0x180009c84  test    edx, edx
0x180009c86  jnz     short loc_180009C9C
0x180009c88  mov     r8, [rsp+28h+wParam]; wParam
0x180009c8d  lea     r9d, [rdx+1]; lParam
0x180009c91  mov     edx, 473h; Msg
0x180009c96  call    cs:__imp_SendMessageW
0x180009c9c  xor     eax, eax
0x180009c9e  add     rsp, 28h
0x180009ca2  retn
```
