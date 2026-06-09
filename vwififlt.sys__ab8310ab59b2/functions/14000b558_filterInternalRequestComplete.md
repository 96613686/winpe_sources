# filterInternalRequestComplete

- ea: `0x14000b558`
- end: `0x14000b5f5`
- name: `filterInternalRequestComplete`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000aef0`

## callees

- `0x14000b558`
- `0x14000d8ec`
- `0x14000d91c`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x14000b58d`
- `NDIS!NdisSetEvent` at `0x14000b58d`

## pseudocode

```c
void __fastcall filterInternalRequestComplete(__int64 a1, __int64 a2, int a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 239, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  *(_DWORD *)(a2 + 272) = a3;
  NdisSetEvent((PNDIS_EVENT)(a2 + 248));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 240, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
}

```

## disassembly

```asm
0x14000b558  mov     [rsp+arg_0], rbx
0x14000b55d  mov     [rsp+arg_8], rsi
0x14000b562  push    rdi
0x14000b563  sub     rsp, 20h
0x14000b567  mov     edi, r8d
0x14000b56a  mov     rbx, rdx
0x14000b56d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b574  lea     rsi, WPP_GLOBAL_Control
0x14000b57b  cmp     rcx, rsi
0x14000b57e  jnz     short loc_14000B5BD
0x14000b580  lea     rcx, [rbx+0F8h]; Event
0x14000b587  mov     [rbx+110h], edi
0x14000b58d  call    cs:__imp_NdisSetEvent
0x14000b594  nop     dword ptr [rax+rax+00h]
0x14000b599  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b5a0  cmp     rcx, rsi
0x14000b5a3  jz      short loc_14000B5AC
0x14000b5a5  mov     eax, [rcx+2Ch]
0x14000b5a8  test    al, 20h
0x14000b5aa  jnz     short loc_14000B5DB
0x14000b5ac  mov     rbx, [rsp+28h+arg_0]
0x14000b5b1  mov     rsi, [rsp+28h+arg_8]
0x14000b5b6  add     rsp, 20h
0x14000b5ba  pop     rdi
0x14000b5bb  retn
0x14000b5bd  mov     eax, [rcx+2Ch]
0x14000b5c0  test    al, 20h
0x14000b5c2  jz      short loc_14000B580
0x14000b5c4  mov     rcx, [rcx+18h]
0x14000b5c8  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000b5cf  mov     edx, 0EFh
0x14000b5d4  call    WPP_SF_
0x14000b5d9  jmp     short loc_14000B580
0x14000b5db  mov     rcx, [rcx+18h]
0x14000b5df  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000b5e6  mov     edx, 0F0h
0x14000b5eb  xor     r9d, r9d
0x14000b5ee  call    WPP_SF_d
0x14000b5f3  jmp     short loc_14000B5AC
```
