# DigestFreeMemory

- ea: `0x180009770`
- end: `0x180009816`
- name: `DigestFreeMemory`
- size: `166`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `53`
- callee_count: `3`
- tags: ``

## callers

- `0x180002ef0`
- `0x180004cb0`
- `0x180006260`
- `0x180008498`
- `0x1800085dc`
- `0x1800087f4`
- `0x180008c40`
- `0x180010510`
- `0x1800109f8`
- `0x18001721c`
- `0x1800179f4`
- `0x180017ee0`
- `0x1800192e8`
- `0x1800195dc`
- `0x180019bd0`
- `0x18001a4b4`
- `0x18001ad3c`
- `0x18001b4b0`
- `0x18001bcec`
- `0x18001bf40`
- `0x18001c8e0`
- `0x18001d5e8`
- `0x18001e4b0`
- `0x1800206d0`
- `0x180022bb8`
- `0x180022f38`
- `0x18002357c`
- `0x180023c70`
- `0x180023fa0`
- `0x180026020`
- `0x180026970`
- `0x1800272f0`
- `0x1800277a0`
- `0x180028190`
- `0x180028ff0`
- `0x180029bd0`
- `0x180029c98`
- `0x18002ab18`
- `0x18002ac54`
- `0x18002af40`
- `0x18002b2b8`
- `0x18002ba20`
- `0x18002bd34`
- `0x18002c364`
- `0x180030628`
- `0x180031080`
- `0x1800328a0`
- `0x180036c10`
- `0x180036ddc`
- `0x180036fac`

## callees

- `0x180009770`
- `0x1800192a8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800097d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800097d1`

## pseudocode

```c
HLOCAL __fastcall DigestFreeMemory(HLOCAL hMem)
{
  HLOCAL result; // rax

  if ( hMem )
  {
    if ( g_NtDigestState == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, hMem);
      return (HLOCAL)(*(__int64 (__fastcall **)(HLOCAL))(*(_QWORD *)&g_LsaFunctions + 48LL))(hMem);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, hMem);
      return LocalFree(hMem);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009770  test    rcx, rcx
0x180009773  jz      short locret_1800097BA
0x180009775  push    rbx
0x180009776  sub     rsp, 20h
0x18000977a  cmp     cs:g_NtDigestState, 1
0x180009781  mov     rbx, rcx
0x180009784  jnz     short loc_1800097BB
0x180009786  mov     rcx, cs:WPP_GLOBAL_Control
0x18000978d  lea     rax, WPP_GLOBAL_Control
0x180009794  cmp     rcx, rax
0x180009797  jz      short loc_1800097A2
0x180009799  test    dword ptr [rcx+1Ch], 100h
0x1800097a0  jnz     short loc_1800097D9
0x1800097a2  mov     rax, cs:g_LsaFunctions
0x1800097a9  mov     rcx, rbx
0x1800097ac  mov     rax, [rax+30h]
0x1800097b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800097b5  add     rsp, 20h
0x1800097b9  pop     rbx
0x1800097ba  retn
0x1800097bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097c2  lea     rax, WPP_GLOBAL_Control
0x1800097c9  cmp     rcx, rax
0x1800097cc  jnz     short loc_1800097F3
0x1800097ce  mov     rcx, rbx; hMem
0x1800097d1  call    cs:__imp_LocalFree
0x1800097d7  jmp     short loc_1800097B5
0x1800097d9  mov     rcx, [rcx+10h]
0x1800097dd  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x1800097e4  mov     edx, 1Eh
0x1800097e9  mov     r9, rbx
0x1800097ec  call    WPP_SF_q
0x1800097f1  jmp     short loc_1800097A2
0x1800097f3  test    dword ptr [rcx+1Ch], 100h
0x1800097fa  jz      short loc_1800097CE
0x1800097fc  mov     rcx, [rcx+10h]
0x180009800  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180009807  mov     edx, 1Fh
0x18000980c  mov     r9, rbx
0x18000980f  call    WPP_SF_q
0x180009814  jmp     short loc_1800097CE
```
