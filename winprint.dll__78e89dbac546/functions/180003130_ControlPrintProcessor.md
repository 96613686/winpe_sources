# ControlPrintProcessor

- ea: `0x180003130`
- end: `0x1800031b7`
- name: `ControlPrintProcessor`
- size: `135`
- prototype: `BOOL __stdcall(HANDLE hPrintProcessor, DWORD Command)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003130`
- `0x1800031c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000319d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000319d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003169`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180003169`
- `GDI32!CancelDC` at `0x18000318d`
- `GDI32!CancelDC` at `0x18000318d`

## pseudocode

```c
BOOL __stdcall ControlPrintProcessor(HANDLE hPrintProcessor, DWORD Command)
{
  struct _PRINTPROCESSORDATA *v3; // rax
  struct _PRINTPROCESSORDATA *v4; // rbx
  DWORD v5; // edi

  v3 = ValidateHandle(hPrintProcessor);
  v4 = v3;
  if ( !v3 )
    return 0;
  if ( Command == 3 )
  {
    *((_DWORD *)v3 + 4) |= 1u;
    if ( (unsigned int)(*((_DWORD *)v3 + 8) - 4) <= 2 )
      CancelDC(*((HDC *)v3 + 13));
  }
  else
  {
    v5 = Command - 1;
    if ( !v5 )
    {
      ResetEvent(*((HANDLE *)v3 + 3));
      *((_DWORD *)v4 + 4) |= 8u;
      return 1;
    }
    if ( v5 != 1 )
      return 0;
  }
  if ( (*((_BYTE *)v4 + 16) & 8) != 0 )
  {
    SetEvent(*((HANDLE *)v4 + 3));
    *((_DWORD *)v4 + 4) &= ~8u;
  }
  return 1;
}

```

## disassembly

```asm
0x180003130  mov     [rsp+arg_0], rbx
0x180003135  push    rdi
0x180003136  sub     rsp, 20h
0x18000313a  mov     edi, edx
0x18000313c  call    ?ValidateHandle@@YAPEAU_PRINTPROCESSORDATA@@PEAX@Z; ValidateHandle(void *)
0x180003141  mov     rbx, rax
0x180003144  test    rax, rax
0x180003147  jz      short loc_180003158
0x180003149  cmp     edi, 3
0x18000314c  jz      short loc_18000317A
0x18000314e  sub     edi, 1
0x180003151  jz      short loc_180003165
0x180003153  cmp     edi, 1
0x180003156  jz      short loc_180003193
0x180003158  xor     eax, eax
0x18000315a  mov     rbx, [rsp+28h+arg_0]
0x18000315f  add     rsp, 20h
0x180003163  pop     rdi
0x180003164  retn
0x180003165  mov     rcx, [rax+18h]; hEvent
0x180003169  call    cs:__imp_ResetEvent
0x18000316f  or      dword ptr [rbx+10h], 8
0x180003173  mov     eax, 1
0x180003178  jmp     short loc_18000315A
0x18000317a  or      dword ptr [rax+10h], 1
0x18000317e  mov     eax, [rax+20h]
0x180003181  sub     eax, 4
0x180003184  cmp     eax, 2
0x180003187  ja      short loc_180003193
0x180003189  mov     rcx, [rbx+68h]; hdc
0x18000318d  call    cs:__imp_CancelDC
0x180003193  test    byte ptr [rbx+10h], 8
0x180003197  jz      short loc_1800031A7
0x180003199  mov     rcx, [rbx+18h]; hEvent
0x18000319d  call    cs:__imp_SetEvent
0x1800031a3  and     dword ptr [rbx+10h], 0FFFFFFF7h
0x1800031a7  mov     rbx, [rsp+28h+arg_0]
0x1800031ac  mov     eax, 1
0x1800031b1  add     rsp, 20h
0x1800031b5  pop     rdi
0x1800031b6  retn
```
