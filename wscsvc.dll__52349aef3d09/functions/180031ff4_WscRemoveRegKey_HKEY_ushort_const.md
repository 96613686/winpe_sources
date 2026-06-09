# WscRemoveRegKey(HKEY__ *,ushort const *)

- ea: `0x180031ff4`
- end: `0x18003204b`
- name: `?WscRemoveRegKey@@YAXPEAUHKEY__@@PEBG@Z`
- size: `87`
- prototype: `void __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001d9e0`

## callees

- `0x180029158`
- `0x180031ff4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003200a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003200a`

## pseudocode

```c
void __fastcall WscRemoveRegKey(HKEY a1, const unsigned __int16 *a2)
{
  if ( RegDeleteKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0)
    && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids, a2);
  }
}

```

## disassembly

```asm
0x180031ff4  push    rbx
0x180031ff6  sub     rsp, 20h
0x180031ffa  xor     r9d, r9d; Reserved
0x180031ffd  xor     r8d, r8d; samDesired
0x180032000  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032007  mov     rbx, rdx
0x18003200a  call    cs:__imp_RegDeleteKeyExW
0x180032010  test    eax, eax
0x180032012  jz      short loc_180032045
0x180032014  mov     rcx, cs:WPP_GLOBAL_Control
0x18003201b  lea     rax, WPP_GLOBAL_Control
0x180032022  cmp     rcx, rax
0x180032025  jz      short loc_180032045
0x180032027  test    byte ptr [rcx+1Ch], 1
0x18003202b  jz      short loc_180032045
0x18003202d  mov     rcx, [rcx+10h]
0x180032031  lea     r8, WPP_feddbfd1be3833cbefac86bf41ce1941_Traceguids
0x180032038  mov     edx, 1Ch
0x18003203d  mov     r9, rbx
0x180032040  call    WPP_SF_S
0x180032045  add     rsp, 20h
0x180032049  pop     rbx
0x18003204a  retn
```
