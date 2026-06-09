# SdpMoveParamSet(_SDIAG_PARAMSET *,_SDIAG_PARAMSET *)

- ea: `0x180002798`
- end: `0x1800027f1`
- name: `?SdpMoveParamSet@@YAJPEAU_SDIAG_PARAMSET@@0@Z`
- size: `89`
- prototype: `__int64 __fastcall(struct _SDIAG_PARAMSET *, struct _SDIAG_PARAMSET *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b2c`

## callees

- `0x180002798`
- `0x180026fa0`

## string_xrefs

- `0x1800027b2`: `SdpMoveParamSet`

## pseudocode

```c
__int64 __fastcall SdpMoveParamSet(struct _SDIAG_PARAMSET *a1, struct _SDIAG_PARAMSET *a2)
{
  unsigned int v2; // r8d
  unsigned int v3; // ebx

  if ( a1 )
  {
    if ( a2 )
    {
      v3 = 0;
      *(_QWORD *)a1 = *(_QWORD *)a2;
      *((_DWORD *)a1 + 2) = *((_DWORD *)a2 + 2);
      *(_QWORD *)a2 = 0;
      *((_DWORD *)a2 + 2) = 0;
      return v3;
    }
    v2 = 637;
  }
  else
  {
    v2 = 636;
  }
  v3 = -2147024809;
  SdpDebugTrace(1u, L"SdpMoveParamSet", v2, -2147024809);
  return v3;
}

```

## disassembly

```asm
0x180002798  push    rbx
0x18000279a  sub     rsp, 20h
0x18000279e  mov     rax, rcx
0x1800027a1  test    rcx, rcx
0x1800027a4  jnz     short loc_1800027C8
0x1800027a6  mov     r8d, 27Ch; int
0x1800027ac  mov     r9d, 80070057h; int
0x1800027b2  lea     rdx, aSdpmoveparamse; "SdpMoveParamSet"
0x1800027b9  mov     ecx, 1; Level
0x1800027be  mov     ebx, r9d
0x1800027c1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800027c6  jmp     short loc_1800027E9
0x1800027c8  test    rdx, rdx
0x1800027cb  jnz     short loc_1800027D5
0x1800027cd  mov     r8d, 27Dh
0x1800027d3  jmp     short loc_1800027AC
0x1800027d5  mov     rcx, [rdx]
0x1800027d8  xor     ebx, ebx
0x1800027da  mov     [rax], rcx
0x1800027dd  mov     ecx, [rdx+8]
0x1800027e0  mov     [rax+8], ecx
0x1800027e3  mov     [rdx], rbx
0x1800027e6  mov     [rdx+8], ebx
0x1800027e9  mov     eax, ebx
0x1800027eb  add     rsp, 20h
0x1800027ef  pop     rbx
0x1800027f0  retn
```
