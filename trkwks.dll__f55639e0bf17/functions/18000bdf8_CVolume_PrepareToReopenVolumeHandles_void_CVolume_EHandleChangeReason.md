# CVolume::PrepareToReopenVolumeHandles(void *,CVolume::EHandleChangeReason)

- ea: `0x18000bdf8`
- end: `0x18000be3d`
- name: `?PrepareToReopenVolumeHandles@CVolume@@AEAAXPEAXW4EHandleChangeReason@1@@Z`
- size: `69`
- prototype: `BOOL __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bd24`

## callees

- `0x18000bdf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000be31`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000be31`

## pseudocode

```c
BOOL __fastcall CVolume::PrepareToReopenVolumeHandles(__int64 a1, __int64 a2, int a3)
{
  BOOL result; // eax

  if ( *(_QWORD *)(a1 + 2872) == a2 )
  {
    if ( a3 )
    {
      if ( a3 == 1 )
        *(_DWORD *)(a1 + 16) &= ~0x10u;
    }
    else
    {
      *(_DWORD *)(a1 + 16) &= ~8u;
    }
    if ( (*(_BYTE *)(a1 + 16) & 8) == 0 && (*(_BYTE *)(a1 + 16) & 0x10) == 0 )
      return SetEvent(*(HANDLE *)(*(_QWORD *)(a1 + 40) + 168LL));
  }
  return result;
}

```

## disassembly

```asm
0x18000bdf8  sub     rsp, 28h
0x18000bdfc  cmp     [rcx+0B38h], rdx
0x18000be03  jnz     short loc_18000BE38
0x18000be05  test    r8d, r8d
0x18000be08  jnz     short loc_18000BE10
0x18000be0a  and     dword ptr [rcx+10h], 0FFFFFFF7h
0x18000be0e  jmp     short loc_18000BE1A
0x18000be10  cmp     r8d, 1
0x18000be14  jnz     short loc_18000BE1A
0x18000be16  and     dword ptr [rcx+10h], 0FFFFFFEFh
0x18000be1a  test    byte ptr [rcx+10h], 8
0x18000be1e  jnz     short loc_18000BE38
0x18000be20  test    byte ptr [rcx+10h], 10h
0x18000be24  jnz     short loc_18000BE38
0x18000be26  mov     rcx, [rcx+28h]
0x18000be2a  mov     rcx, [rcx+0A8h]; hEvent
0x18000be31  call    cs:__imp_SetEvent
0x18000be37  nop
0x18000be38  add     rsp, 28h
0x18000be3c  retn
0x1800117be  push    rbp
0x1800117c0  sub     rsp, 20h
0x1800117c4  mov     rbp, rdx
0x1800117c7  add     rsp, 20h
0x1800117cb  pop     rbp
0x1800117cc  retn
```
