# UdfCommonDirControl

- ea: `0x14003f440`
- end: `0x14003f4c2`
- name: `UdfCommonDirControl`
- size: `130`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400077f0`
- `0x1400094c0`

## callees

- `0x1400030e0`
- `0x14002e198`
- `0x14003f440`
- `0x14003f4c8`

## pseudocode

```c
__int64 __fastcall UdfCommonDirControl(void *a1, IRP *a2)
{
  __int64 CurrentStackLocation; // r11
  __int64 v3; // r9
  __int64 v4; // r8
  unsigned int v5; // ebx
  _DWORD *v6; // r8

  CurrentStackLocation = (__int64)a2->Tail.Overlay.CurrentStackLocation;
  v3 = *(_QWORD *)(CurrentStackLocation + 48);
  v4 = *(_QWORD *)(v3 + 32);
  *(_QWORD *)(v3 + 32) = v4;
  if ( (v4 & 7) == 3 )
  {
    v6 = (_DWORD *)(v4 & 0xFFFFFFFFFFFFFFF8uLL);
    if ( *(_BYTE *)(CurrentStackLocation + 1) == 1 )
    {
      return (unsigned int)UdfQueryDirectory(
                             (__int64)a1,
                             (__int64)a2,
                             CurrentStackLocation,
                             *(_QWORD *)(v3 + 24),
                             (__int64)v6);
    }
    else
    {
      if ( *(_BYTE *)(CurrentStackLocation + 1) != 2 )
      {
        v5 = -1073741808;
        goto LABEL_6;
      }
      return (unsigned int)UdfNotifyChangeDirectory((__int64)a1, a2, CurrentStackLocation, v6);
    }
  }
  v5 = -1073741811;
LABEL_6:
  UdfCompleteRequest(a1, a2, v5);
  return v5;
}

```

## disassembly

```asm
0x14003f440  push    rbx
0x14003f442  sub     rsp, 30h
0x14003f446  mov     r11, [rdx+0B8h]
0x14003f44d  mov     r10, rcx
0x14003f450  mov     r9, [r11+30h]
0x14003f454  mov     r8, [r9+20h]
0x14003f458  mov     ecx, r8d
0x14003f45b  mov     [r9+20h], r8
0x14003f45f  and     ecx, 7
0x14003f462  cmp     ecx, 3
0x14003f465  jz      short loc_14003F471
0x14003f467  mov     ebx, 0C000000Dh
0x14003f46c  mov     rcx, r10
0x14003f46f  jmp     short loc_14003F48C
0x14003f471  movzx   ecx, byte ptr [r11+1]
0x14003f476  and     r8, 0FFFFFFFFFFFFFFF8h
0x14003f47a  sub     ecx, 1
0x14003f47d  jz      short loc_14003F4A3
0x14003f47f  cmp     ecx, 1
0x14003f482  mov     rcx, r10
0x14003f485  jz      short loc_14003F496
0x14003f487  mov     ebx, 0C0000010h
0x14003f48c  mov     r8d, ebx
0x14003f48f  call    UdfCompleteRequest
0x14003f494  jmp     short loc_14003F4B9
0x14003f496  mov     r9, r8
0x14003f499  mov     r8, r11
0x14003f49c  call    UdfNotifyChangeDirectory
0x14003f4a1  jmp     short loc_14003F4B7
0x14003f4a3  mov     r9, [r9+18h]
0x14003f4a7  mov     rcx, r10; int
0x14003f4aa  mov     [rsp+38h+var_18], r8; __int64
0x14003f4af  mov     r8, r11
0x14003f4b2  call    UdfQueryDirectory
0x14003f4b7  mov     ebx, eax
0x14003f4b9  mov     eax, ebx
0x14003f4bb  add     rsp, 30h
0x14003f4bf  pop     rbx
0x14003f4c0  retn
```
