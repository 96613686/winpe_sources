# DllRelease

- ea: `0x18000366c`
- end: `0x1800036dd`
- name: `DllRelease`
- size: `113`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003080`
- `0x1800031e0`
- `0x180007e5c`
- `0x180013cbc`
- `0x180017158`

## callees

- `0x18000366c`
- `0x180003860`
- `0x180003888`

## pseudocode

```c
__int64 DllRelease()
{
  __int64 result; // rax
  __int64 v1; // r9

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6dd76389fe1d31293452cff392e3d361_Traceguids);
  v1 = (unsigned int)_InterlockedDecrement(&g_cLocks);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    return WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6dd76389fe1d31293452cff392e3d361_Traceguids, v1);
  return result;
}

```

## disassembly

```asm
0x18000366c  push    rbx
0x18000366e  sub     rsp, 20h
0x180003672  mov     rcx, cs:WPP_GLOBAL_Control
0x180003679  lea     rbx, WPP_GLOBAL_Control
0x180003680  cmp     rcx, rbx
0x180003683  jz      short loc_1800036A0
0x180003685  test    byte ptr [rcx+1Ch], 20h
0x180003689  jz      short loc_1800036A0
0x18000368b  mov     rcx, [rcx+10h]
0x18000368f  lea     r8, WPP_6dd76389fe1d31293452cff392e3d361_Traceguids
0x180003696  mov     edx, 10h
0x18000369b  call    WPP_SF_
0x1800036a0  or      r9d, 0FFFFFFFFh
0x1800036a4  lock xadd cs:?g_cLocks@@3JA, r9d; long g_cLocks
0x1800036ad  dec     r9d
0x1800036b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036b7  cmp     rcx, rbx
0x1800036ba  jz      short loc_1800036D7
0x1800036bc  test    byte ptr [rcx+1Ch], 20h
0x1800036c0  jz      short loc_1800036D7
0x1800036c2  mov     rcx, [rcx+10h]
0x1800036c6  lea     r8, WPP_6dd76389fe1d31293452cff392e3d361_Traceguids
0x1800036cd  mov     edx, 11h
0x1800036d2  call    WPP_SF_d
0x1800036d7  add     rsp, 20h
0x1800036db  pop     rbx
0x1800036dc  retn
```
