# CVolume::DeleteLogAndReInitializeVolume(void)

- ea: `0x18000d060`
- end: `0x18000d09b`
- name: `?DeleteLogAndReInitializeVolume@CVolume@@AEAAXXZ`
- size: `59`
- prototype: `void __fastcall(CVolume *this, int)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180002b50`
- `0x180003798`
- `0x180006a80`
- `0x18000c430`
- `0x18000cd40`
- `0x18000f22c`

## callees

- `0x180002488`
- `0x18000d038`
- `0x18000d060`

## pseudocode

```c
void __fastcall CVolume::DeleteLogAndReInitializeVolume(CVolume *this, int a2)
{
  int v3; // eax
  int v4; // eax

  v3 = *((_DWORD *)this + 4);
  if ( (v3 & 0x40) != 0 )
    TrkRaiseWin32Error(110);
  v4 = v3 | 0x40;
  *((_DWORD *)this + 4) = v4;
  *((_DWORD *)this + 4) = v4 | 2;
  CVolume::VolumeSanityCheck(this, a2);
  *((_DWORD *)this + 4) &= ~0x40u;
}

```

## disassembly

```asm
0x18000d060  mov     [rsp+arg_0], rcx
0x18000d065  push    rbx
0x18000d066  sub     rsp, 20h
0x18000d06a  mov     rbx, rcx
0x18000d06d  mov     eax, [rcx+10h]
0x18000d070  test    al, 40h
0x18000d072  jz      short loc_18000D07F
0x18000d074  mov     ecx, 6Eh ; 'n'; int
0x18000d079  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000d07f  or      eax, 40h
0x18000d082  mov     [rcx+10h], eax
0x18000d085  or      eax, 2
0x18000d088  mov     [rcx+10h], eax
0x18000d08b  call    ?VolumeSanityCheck@CVolume@@AEAAXH@Z; CVolume::VolumeSanityCheck(int)
0x18000d090  nop
0x18000d091  and     dword ptr [rbx+10h], 0FFFFFFBFh
0x18000d095  add     rsp, 20h
0x18000d099  pop     rbx
0x18000d09a  retn
0x180011896  push    rbp
0x180011898  sub     rsp, 20h
0x18001189c  mov     rbp, rdx
0x18001189f  mov     rcx, [rbp+30h]
0x1800118a3  and     dword ptr [rcx+10h], 0FFFFFFBFh
0x1800118a7  add     rsp, 20h
0x1800118ab  pop     rbp
0x1800118ac  retn
```
