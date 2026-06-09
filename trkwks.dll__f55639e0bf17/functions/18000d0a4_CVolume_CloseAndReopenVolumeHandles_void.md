# CVolume::CloseAndReopenVolumeHandles(void)

- ea: `0x18000d0a4`
- end: `0x18000d125`
- name: `?CloseAndReopenVolumeHandles@CVolume@@QEAAXXZ`
- size: `129`
- prototype: `void __fastcall(CVolume *__hidden this)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x180002b50`
- `0x180003798`
- `0x180006a80`
- `0x18000c430`
- `0x18000cd40`
- `0x18000f22c`

## callees

- `0x18000131c`
- `0x1800073a0`
- `0x18000756c`
- `0x18000d038`
- `0x18000d0a4`
- `0x18000f6bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d0b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d0b8`

## pseudocode

```c
void __fastcall CVolume::CloseAndReopenVolumeHandles(CVolume *this)
{
  int v2; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  ++*((_DWORD *)this + 13);
  v2 = *((_DWORD *)this + 4);
  if ( (v2 & 0x80u) != 0 )
    TrkRaiseWin32Error(110);
  *((_DWORD *)this + 4) = v2 | 0x80;
  CVolume::CloseVolumeHandles(this, 0, 2);
  CVolume::ReopenVolumeHandles(this);
  *((_DWORD *)this + 4) &= ~0x80u;
  CVolume::Unlock(this);
}

```

## disassembly

```asm
0x18000d0a4  mov     [rsp+arg_0], rcx
0x18000d0a9  push    rbx
0x18000d0aa  sub     rsp, 30h
0x18000d0ae  mov     rbx, rcx
0x18000d0b1  add     rcx, 0A8h; lpCriticalSection
0x18000d0b8  call    cs:__imp_EnterCriticalSection
0x18000d0be  inc     dword ptr [rbx+34h]
0x18000d0c1  mov     eax, [rbx+10h]
0x18000d0c4  test    al, al
0x18000d0c6  jns     short loc_18000D0D2
0x18000d0c8  mov     ecx, 6Eh ; 'n'; int
0x18000d0cd  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000d0d2  bts     eax, 7
0x18000d0d6  mov     [rbx+10h], eax
0x18000d0d9  xor     edx, edx
0x18000d0db  lea     r8d, [rdx+2]
0x18000d0df  mov     rcx, rbx
0x18000d0e2  call    ?CloseVolumeHandles@CVolume@@QEAAXPEAXW4EHandleChangeReason@1@@Z; CVolume::CloseVolumeHandles(void *,CVolume::EHandleChangeReason)
0x18000d0e7  mov     rcx, rbx; this
0x18000d0ea  call    ?ReopenVolumeHandles@CVolume@@QEAAHXZ; CVolume::ReopenVolumeHandles(void)
0x18000d0ef  jmp     short loc_18000D112
0x18000d0f1  mov     rcx, cs:?g_ptrkwks@@3PEAVCTrkWksSvc@@EA; CTrkWksSvc * g_ptrkwks
0x18000d0f8  test    byte ptr [rcx+254h], 1
0x18000d0ff  jz      short loc_18000D10D
0x18000d101  add     rcx, 258h; this
0x18000d108  call    ?SetRecurring@CNewTimer@@QEAAXXZ; CNewTimer::SetRecurring(void)
0x18000d10d  mov     rbx, [rsp+38h+arg_0]
0x18000d112  btr     dword ptr [rbx+10h], 7
0x18000d117  mov     rcx, rbx; this
0x18000d11a  call    ?Unlock@CVolume@@AEAAKXZ; CVolume::Unlock(void)
0x18000d11f  add     rsp, 30h
0x18000d123  pop     rbx
0x18000d124  retn
0x1800118b4  push    rbp
0x1800118b6  sub     rsp, 20h
0x1800118ba  mov     rbp, rdx
0x1800118bd  mov     eax, 1
0x1800118c2  add     rsp, 20h
0x1800118c6  pop     rbp
0x1800118c7  retn
```
