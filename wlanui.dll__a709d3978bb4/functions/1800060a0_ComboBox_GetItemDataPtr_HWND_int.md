# ComboBox_GetItemDataPtr(HWND__ *,int)

- ea: `0x1800060a0`
- end: `0x1800060cb`
- name: `?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z`
- size: `43`
- prototype: `void *__fastcall(HWND, int)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007604`
- `0x180007ae4`
- `0x180008074`
- `0x18000833c`
- `0x180008388`
- `0x180009380`
- `0x18000a194`
- `0x18000b078`
- `0x18000b6f8`
- `0x18000c824`
- `0x180013af0`

## callees

- `0x1800060a0`

## import_xrefs

- `USER32!SendMessageW` at `0x1800060b3`
- `USER32!SendMessageW` at `0x1800060b3`

## pseudocode

```c
void *__fastcall ComboBox_GetItemDataPtr(HWND a1, int a2)
{
  void *result; // rax

  if ( a2 < 0 )
    return 0;
  result = (void *)SendMessageW(a1, 0x150u, a2, 0);
  if ( (__int64)result < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800060a0  sub     rsp, 28h
0x1800060a4  test    edx, edx
0x1800060a6  js      short loc_1800060C4
0x1800060a8  movsxd  r8, edx; wParam
0x1800060ab  xor     r9d, r9d; lParam
0x1800060ae  mov     edx, 150h; Msg
0x1800060b3  call    cs:__imp_SendMessageW
0x1800060b9  xor     ecx, ecx
0x1800060bb  test    rax, rax
0x1800060be  cmovs   rax, rcx
0x1800060c2  jmp     short loc_1800060C6
0x1800060c4  xor     eax, eax
0x1800060c6  add     rsp, 28h
0x1800060ca  retn
```
