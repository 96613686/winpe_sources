# AddEvent

- ea: `0x180009c88`
- end: `0x180009ce3`
- name: `AddEvent`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004704`
- `0x180005d60`

## callees

- `0x180009c88`

## import_xrefs

- `USER32!keybd_event` at `0x180009cbd`
- `USER32!keybd_event` at `0x180009cd5`
- `USER32!keybd_event` at `0x180009cbd`
- `USER32!keybd_event` at `0x180009cd5`

## pseudocode

```c
__int64 __fastcall AddEvent(int a1, BYTE a2)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  DWORD v8; // r8d

  v3 = a1 - 256;
  if ( !v3 )
    goto LABEL_9;
  v4 = v3 - 1;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      v6 = v5 - 2;
      if ( v6 )
      {
        if ( v6 != 1 )
          return 2147500037LL;
        goto LABEL_8;
      }
LABEL_9:
      v8 = 0;
      goto LABEL_10;
    }
    keybd_event(a2, 0, 0, 0);
  }
LABEL_8:
  v8 = 2;
LABEL_10:
  keybd_event(a2, 0, v8, 0);
  return 0;
}

```

## disassembly

```asm
0x180009c88  push    rbx
0x180009c8a  sub     rsp, 20h
0x180009c8e  mov     ebx, edx
0x180009c90  sub     ecx, 100h
0x180009c96  jz      short loc_180009CCB
0x180009c98  sub     ecx, 1
0x180009c9b  jz      short loc_180009CC3
0x180009c9d  sub     ecx, 1
0x180009ca0  jz      short loc_180009CB3
0x180009ca2  sub     ecx, 2
0x180009ca5  jz      short loc_180009CCB
0x180009ca7  cmp     ecx, 1
0x180009caa  jz      short loc_180009CC3
0x180009cac  mov     eax, 80004005h
0x180009cb1  jmp     short loc_180009CDD
0x180009cb3  xor     r9d, r9d; dwExtraInfo
0x180009cb6  xor     r8d, r8d; dwFlags
0x180009cb9  xor     edx, edx; bScan
0x180009cbb  mov     cl, bl; bVk
0x180009cbd  call    cs:__imp_keybd_event
0x180009cc3  mov     r8d, 2
0x180009cc9  jmp     short loc_180009CCE
0x180009ccb  xor     r8d, r8d; dwFlags
0x180009cce  xor     r9d, r9d; dwExtraInfo
0x180009cd1  xor     edx, edx; bScan
0x180009cd3  mov     cl, bl; bVk
0x180009cd5  call    cs:__imp_keybd_event
0x180009cdb  xor     eax, eax
0x180009cdd  add     rsp, 20h
0x180009ce1  pop     rbx
0x180009ce2  retn
```
