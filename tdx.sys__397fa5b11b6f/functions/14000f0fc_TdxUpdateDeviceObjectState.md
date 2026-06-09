# TdxUpdateDeviceObjectState

- ea: `0x14000f0fc`
- end: `0x14000f31d`
- name: `TdxUpdateDeviceObjectState`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000eba0`

## callees

- `0x14000f0fc`
- `0x14000f324`
- `0x14000f364`
- `0x14000f438`
- `0x140010998`
- `0x140012b8c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000f12f`
- `ntoskrnl!KeReleaseMutex` at `0x14000f19b`
- `ntoskrnl!KeReleaseMutex` at `0x14000f1ca`
- `ntoskrnl!KeReleaseMutex` at `0x14000f26d`
- `ntoskrnl!KeReleaseMutex` at `0x14000f12f`
- `ntoskrnl!KeReleaseMutex` at `0x14000f19b`
- `ntoskrnl!KeReleaseMutex` at `0x14000f1ca`
- `ntoskrnl!KeReleaseMutex` at `0x14000f26d`

## string_xrefs

- `0x14000f21e`: `TdxUpdateDeviceObjectState`

## pseudocode

```c
int __fastcall TdxUpdateDeviceObjectState(_DWORD *a1, int a2, const UCHAR *a3)
{
  int v3; // r10d
  char v5; // bp
  PDEVICE_OBJECT *v8; // rax
  __int64 v9; // rdx
  int v10; // r8d
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // r10d
  int v14; // r11d
  __int64 v15; // rdx
  __int64 v16; // r8

  v3 = a1[76];
  v5 = v3 & 1;
  if ( (v3 & 4) != 0 )
  {
    LODWORD(v8) = KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
    if ( !v5 )
    {
      if ( !a2 && (LODWORD(v8) = Ipv4UnicastAddressScope(a3), (_DWORD)v8 == 14)
        || a2 == 41 && (LODWORD(v8) = Ipv6UnicastAddressScope(a3), (_DWORD)v8 == 14) )
      {
        v9 = 614;
LABEL_20:
        LODWORD(v8) = TdxNaTryToOverlapDelayedBinds("TdxUpdateDeviceObjectState", v9);
      }
    }
  }
  else if ( (v3 & 1) != 0 )
  {
    v10 = a1[5];
    if ( !v10 && Ipv4UnicastAddressScope(a3) >= ScopeLevelSubnet || v10 == 41 && (int)Ipv6UnicastAddressScope(a3) >= 3 )
    {
      a1[72] = v14;
      a1[76] = v13 | 4;
      KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
      TdxDecrementNotReadyInterfaceCount(0x279u, v15, v16);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids, a1);
      }
      v9 = 639;
      goto LABEL_20;
    }
    LODWORD(v8) = KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
  }
  else
  {
    if ( !a1[72] )
      a1[72] = 1;
    a1[76] = v3 | 4;
    KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.Dpc.DpcListEntry, 0);
    TdxDecrementNotReadyInterfaceCount(0x287u, v11, v12);
    v8 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      LODWORD(v8) = WPP_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      19,
                      WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids,
                      a1);
    }
    if ( !a2 && (LODWORD(v8) = Ipv4UnicastAddressScope(a3), (_DWORD)v8 == 14)
      || a2 == 41 && (LODWORD(v8) = Ipv6UnicastAddressScope(a3), (_DWORD)v8 == 14) )
    {
      v9 = 657;
      goto LABEL_20;
    }
  }
  return (int)v8;
}

```

## disassembly

```asm
0x14000f0fc  push    rbx
0x14000f0fe  push    rbp
0x14000f0ff  push    rsi
0x14000f100  push    rdi
0x14000f101  sub     rsp, 28h
0x14000f105  mov     r10d, [rcx+130h]
0x14000f10c  mov     r11d, 1
0x14000f112  mov     ebp, r10d
0x14000f115  mov     rdi, r8
0x14000f118  and     ebp, r11d
0x14000f11b  mov     esi, edx
0x14000f11d  mov     rbx, rcx
0x14000f120  test    r10b, 4
0x14000f124  jz      short loc_14000F177
0x14000f126  xor     edx, edx; Wait
0x14000f128  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000f12f  call    cs:__imp_KeReleaseMutex
0x14000f136  nop     dword ptr [rax+rax+00h]
0x14000f13b  test    bpl, bpl
0x14000f13e  jz      short loc_14000F14A
0x14000f140  add     rsp, 28h
0x14000f144  pop     rdi
0x14000f145  pop     rsi
0x14000f146  pop     rbp
0x14000f147  pop     rbx
0x14000f148  retn
0x14000f14a  test    esi, esi
0x14000f14c  jnz     short loc_14000F15B
0x14000f14e  mov     rcx, rdi; Address
0x14000f151  call    Ipv4UnicastAddressScope
0x14000f156  cmp     eax, 0Eh
0x14000f159  jz      short loc_14000F16D
0x14000f15b  cmp     esi, 29h ; ')'
0x14000f15e  jnz     short loc_14000F140
0x14000f160  mov     rcx, rdi
0x14000f163  call    Ipv6UnicastAddressScope
0x14000f168  cmp     eax, 0Eh
0x14000f16b  jnz     short loc_14000F140
0x14000f16d  mov     edx, 266h
0x14000f172  jmp     loc_14000F21E
0x14000f177  test    ebp, ebp
0x14000f179  jz      short loc_14000F1A9
0x14000f17b  mov     r8d, [rcx+14h]
0x14000f17f  test    r8d, r8d
0x14000f182  jz      loc_14000F22F
0x14000f188  cmp     r8d, 29h ; ')'
0x14000f18c  jz      loc_14000F241
0x14000f192  xor     edx, edx; Wait
0x14000f194  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000f19b  call    cs:__imp_KeReleaseMutex
0x14000f1a2  nop     dword ptr [rax+rax+00h]
0x14000f1a7  jmp     short loc_14000F140
0x14000f1a9  cmp     dword ptr [rcx+120h], 0
0x14000f1b0  jz      loc_14000F2C7
0x14000f1b6  or      r10d, 4
0x14000f1ba  xor     edx, edx; Wait
0x14000f1bc  mov     [rcx+130h], r10d
0x14000f1c3  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000f1ca  call    cs:__imp_KeReleaseMutex
0x14000f1d1  nop     dword ptr [rax+rax+00h]
0x14000f1d6  mov     ecx, 287h
0x14000f1db  call    TdxDecrementNotReadyInterfaceCount
0x14000f1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f1e7  lea     rax, WPP_GLOBAL_Control
0x14000f1ee  cmp     rcx, rax
0x14000f1f1  jnz     loc_14000F2D3
0x14000f1f7  test    esi, esi
0x14000f1f9  jz      loc_14000F307
0x14000f1ff  cmp     esi, 29h ; ')'
0x14000f202  jnz     loc_14000F140
0x14000f208  mov     rcx, rdi
0x14000f20b  call    Ipv6UnicastAddressScope
0x14000f210  cmp     eax, 0Eh
0x14000f213  jnz     loc_14000F140
0x14000f219  mov     edx, 291h
0x14000f21e  lea     rcx, aTdxupdatedevic; "TdxUpdateDeviceObjectState"
0x14000f225  call    TdxNaTryToOverlapDelayedBinds
0x14000f22a  jmp     loc_14000F140
0x14000f22f  mov     rcx, rdi; Address
0x14000f232  call    Ipv4UnicastAddressScope
0x14000f237  cmp     eax, 3
0x14000f23a  jge     short loc_14000F252
0x14000f23c  jmp     loc_14000F188
0x14000f241  mov     rcx, rdi
0x14000f244  call    Ipv6UnicastAddressScope
0x14000f249  cmp     eax, 3
0x14000f24c  jl      loc_14000F192
0x14000f252  or      r10d, 4
0x14000f256  mov     [rbx+120h], r11d
0x14000f25d  xor     edx, edx; Wait
0x14000f25f  mov     [rbx+130h], r10d
0x14000f266  lea     rcx, WPP_MAIN_CB.Dpc.DpcListEntry; Mutex
0x14000f26d  call    cs:__imp_KeReleaseMutex
0x14000f274  nop     dword ptr [rax+rax+00h]
0x14000f279  mov     ecx, 279h
0x14000f27e  call    TdxDecrementNotReadyInterfaceCount
0x14000f283  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f28a  lea     rax, WPP_GLOBAL_Control
0x14000f291  cmp     rcx, rax
0x14000f294  jz      short loc_14000F2BD
0x14000f296  cmp     byte ptr [rcx+29h], 4
0x14000f29a  jb      short loc_14000F2BD
0x14000f29c  test    dword ptr [rcx+2Ch], 200h
0x14000f2a3  jz      short loc_14000F2BD
0x14000f2a5  mov     rcx, [rcx+18h]
0x14000f2a9  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14000f2b0  mov     edx, 12h
0x14000f2b5  mov     r9, rbx
0x14000f2b8  call    WPP_SF_q
0x14000f2bd  mov     edx, 27Fh
0x14000f2c2  jmp     loc_14000F21E
0x14000f2c7  mov     [rcx+120h], r11d
0x14000f2ce  jmp     loc_14000F1B6
0x14000f2d3  cmp     byte ptr [rcx+29h], 4
0x14000f2d7  jb      loc_14000F1F7
0x14000f2dd  test    dword ptr [rcx+2Ch], 200h
0x14000f2e4  jz      loc_14000F1F7
0x14000f2ea  mov     rcx, [rcx+18h]
0x14000f2ee  lea     r8, WPP_97be8db14fc035ddabf5f66f78f15bd4_Traceguids
0x14000f2f5  mov     edx, 13h
0x14000f2fa  mov     r9, rbx
0x14000f2fd  call    WPP_SF_q
0x14000f302  jmp     loc_14000F1F7
0x14000f307  mov     rcx, rdi; Address
0x14000f30a  call    Ipv4UnicastAddressScope
0x14000f30f  cmp     eax, 0Eh
0x14000f312  jz      loc_14000F219
0x14000f318  jmp     loc_14000F1FF
```
