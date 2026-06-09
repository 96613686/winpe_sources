# SC_PACKET::operator delete(void *)

- ea: `0x1400151a0`
- end: `0x14001521d`
- name: `??3SC_PACKET@@SAXPEAX@Z`
- size: `125`
- prototype: `void __fastcall(PVOID Buffer)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140014f90`
- `0x140015050`
- `0x14002f850`
- `0x14003e880`
- `0x14003e900`

## callees

- `0x1400151a0`
- `0x140015fd0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400151e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400151fd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400151e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400151fd`

## pseudocode

```c
void __fastcall SC_PACKET::operator delete(_BYTE *Buffer)
{
  char v2; // cl
  unsigned __int64 v3; // r8

  v2 = Buffer[172];
  if ( v2 || !Buffer[173] )
  {
    if ( Buffer[171] == 0xFF )
    {
      SP_CONTROL::FreePacket(Buffer);
    }
    else
    {
      v3 = (unsigned __int64)(unsigned __int8)Buffer[171] << 7;
      if ( v2 )
        ExFreeToNPagedLookasideList(
          (PNPAGED_LOOKASIDE_LIST)(v3 + *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 44)),
          Buffer);
      else
        ExFreeToNPagedLookasideList(
          (PNPAGED_LOOKASIDE_LIST)(v3 + *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 43)),
          Buffer);
    }
  }
}

```

## disassembly

```asm
0x1400151a0  sub     rsp, 28h
0x1400151a4  mov     rdx, rcx; Entry
0x1400151a7  movzx   ecx, byte ptr [rcx+0ACh]
0x1400151ae  test    cl, cl
0x1400151b0  jnz     short loc_1400151BA
0x1400151b2  cmp     [rdx+0ADh], cl
0x1400151b8  jnz     short loc_140015217
0x1400151ba  movzx   eax, byte ptr [rdx+0ABh]
0x1400151c1  cmp     al, 0FFh
0x1400151c3  jz      short loc_14001520F
0x1400151c5  mov     r8d, eax
0x1400151c8  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1400151cf  shl     r8, 7
0x1400151d3  test    cl, cl
0x1400151d5  jz      short loc_1400151F3
0x1400151d7  mov     rcx, [rax+160h]
0x1400151de  add     rcx, r8; Lookaside
0x1400151e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400151e8  nop     dword ptr [rax+rax+00h]
0x1400151ed  add     rsp, 28h
0x1400151f1  retn
0x1400151f3  mov     rcx, [rax+158h]
0x1400151fa  add     rcx, r8; Lookaside
0x1400151fd  call    cs:__imp_ExFreeToNPagedLookasideList
0x140015204  nop     dword ptr [rax+rax+00h]
0x140015209  add     rsp, 28h
0x14001520d  retn
0x14001520f  mov     rcx, rdx; Buffer
0x140015212  call    ?FreePacket@SP_CONTROL@@SAXPEAX@Z; SP_CONTROL::FreePacket(void *)
0x140015217  add     rsp, 28h
0x14001521b  retn
```
