# mciSendStringW

- ea: `0x180012060`
- end: `0x1800120b8`
- name: `mciSendStringW`
- size: `88`
- prototype: `MCIERROR __stdcall(LPCWSTR lpstrCommand, LPWSTR lpstrReturnString, UINT uReturnLength, HWND hwndCallback)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800100b0`
- `0x180011e90`

## callees

- `0x18000b42c`
- `0x180010504`
- `0x180012060`

## pseudocode

```c
MCIERROR __stdcall mciSendStringW(
        LPCWSTR lpstrCommand,
        LPWSTR lpstrReturnString,
        UINT uReturnLength,
        HWND hwndCallback)
{
  MCIERROR result; // eax

  if ( !MCI_bDeviceListInitialized && !(unsigned int)mciInitDeviceList() )
    return 264;
  do
    result = mciSendStringInternal(lpstrCommand, lpstrReturnString, uReturnLength, hwndCallback, 0);
  while ( result == -16777216 );
  return result;
}

```

## disassembly

```asm
0x180012060  push    rbx
0x180012062  push    rbp
0x180012063  push    rsi
0x180012064  push    rdi
0x180012065  sub     rsp, 38h
0x180012069  cmp     cs:MCI_bDeviceListInitialized, 0
0x180012070  mov     rbx, r9
0x180012073  mov     edi, r8d
0x180012076  mov     rsi, rdx
0x180012079  mov     rbp, rcx
0x18001207c  jnz     short loc_18001208E
0x18001207e  call    mciInitDeviceList
0x180012083  test    eax, eax
0x180012085  jnz     short loc_18001208E
0x180012087  mov     eax, 108h
0x18001208c  jmp     short loc_1800120AF
0x18001208e  mov     r9, rbx; void *
0x180012091  mov     [rsp+58h+var_38], 0; struct tagMCI_SYSTEM_MESSAGE *
0x18001209a  mov     r8d, edi; unsigned int
0x18001209d  mov     rdx, rsi; unsigned __int16 *
0x1800120a0  mov     rcx, rbp; unsigned __int16 *
0x1800120a3  call    ?mciSendStringInternal@@YAKPEBGPEAGIPEAXPEAUtagMCI_SYSTEM_MESSAGE@@@Z; mciSendStringInternal(ushort const *,ushort *,uint,void *,tagMCI_SYSTEM_MESSAGE *)
0x1800120a8  cmp     eax, 0FF000000h
0x1800120ad  jz      short loc_18001208E
0x1800120af  add     rsp, 38h
0x1800120b3  pop     rdi
0x1800120b4  pop     rsi
0x1800120b5  pop     rbp
0x1800120b6  pop     rbx
0x1800120b7  retn
```
