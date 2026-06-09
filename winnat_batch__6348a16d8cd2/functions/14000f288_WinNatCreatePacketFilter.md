# WinNatCreatePacketFilter

- ea: `0x14000f288`
- end: `0x14000f420`
- name: `WinNatCreatePacketFilter`
- size: `408`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400113c0`

## callees

- `0x14000e488`
- `0x14000ede4`
- `0x14000f288`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f2ab`
- `ntoskrnl!ExAllocatePool2` at `0x14000f2ab`

## pseudocode

```c
__int64 __fastcall WinNatCreatePacketFilter(__int64 a1, __int64 a2)
{
  __int64 Pool2; // rax
  __int64 v5; // r8
  __int64 v6; // r11
  unsigned int v8; // ecx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int16 v11; // ax
  __int64 v12; // r9
  __int64 v13; // r11
  __int64 v14; // r9
  __int64 v15; // r11
  unsigned __int64 v16; // rcx
  _QWORD *v17; // rcx

  Pool2 = ExAllocatePool2(64, 120, 1718636119);
  v6 = Pool2;
  if ( Pool2 )
  {
    v8 = *(unsigned __int8 *)(a1 + 560);
    *(_BYTE *)(Pool2 + 68) = v8;
    v9 = v8;
    *(_BYTE *)(Pool2 + 48) = *(_BYTE *)(a1 + 540);
    v10 = Pool2 + 52;
    v11 = *(_WORD *)(a1 + 542);
    *(_WORD *)(v6 + 8) = v11;
    v12 = 4;
    if ( v11 != 2 )
      v12 = 16;
    WinNatCopyPrefix(v10, a1 + 544, v9, v12);
    v14 = 4;
    if ( *(_WORD *)(v13 + 8) != 2 )
      v14 = 16;
    WinNatCopyPrefix(v13 + 32, a1 + 524, *(unsigned __int8 *)(v13 + 48), v14);
    if ( *(_BYTE *)(a1 + 580) != 0xFF )
      WinNatCopyPrefix(v15 + 72, a1 + 576, *(unsigned __int8 *)(a1 + 580), 4);
    *(_BYTE *)(v15 + 76) = *(_BYTE *)(a1 + 580);
    *(_QWORD *)(v15 + 88) = *(_QWORD *)(a1 + 568);
    *(_QWORD *)v15 = 1;
    if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 320)) <= 1 )
      __fastfail(0xEu);
    v16 = *(unsigned __int8 *)(v15 + 48) + ((unsigned __int64)*(unsigned __int8 *)(v15 + 68) << 16);
    *(_QWORD *)(v15 + 80) = a2;
    *(_QWORD *)(v15 + 104) = v16;
    v17 = (_QWORD *)qword_140026AB8;
    if ( *(__int64 **)qword_140026AB8 != &qword_140026AB0 )
      __fastfail(3u);
    *(_QWORD *)(v15 + 16) = &qword_140026AB0;
    *(_QWORD *)(v15 + 24) = v17;
    *v17 = v15 + 16;
    qword_140026AB8 = v15 + 16;
    if ( _InterlockedIncrement64((volatile signed __int64 *)v15) <= 1 )
      __fastfail(0xEu);
    return v15;
  }
  else
  {
    if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, 1, v5, L"Packet filter allocation failed");
    return 0;
  }
}

```

## disassembly

```asm
0x14000f288  mov     [rsp+arg_0], rbx
0x14000f28d  mov     [rsp+arg_8], rsi
0x14000f292  push    rdi
0x14000f293  sub     rsp, 20h
0x14000f297  mov     rdi, rdx
0x14000f29a  mov     rbx, rcx
0x14000f29d  mov     edx, 78h ; 'x'
0x14000f2a2  mov     r8d, 66704E57h
0x14000f2a8  lea     ecx, [rdx-38h]
0x14000f2ab  call    cs:__imp_ExAllocatePool2
0x14000f2b2  nop     dword ptr [rax+rax+00h]
0x14000f2b7  mov     r11, rax
0x14000f2ba  test    rax, rax
0x14000f2bd  jnz     short loc_14000F2ED
0x14000f2bf  lea     edx, [rax+1]
0x14000f2c2  cmp     cs:dword_140026104, edx
0x14000f2c8  jnz     short loc_14000F2E6
0x14000f2ca  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14000f2d1  jz      short loc_14000F2E6
0x14000f2d3  lea     r9, aPacketFilterAl; "Packet filter allocation failed"
0x14000f2da  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f2e1  call    McTemplateK0z_EtwWriteTransfer
0x14000f2e6  xor     eax, eax
0x14000f2e8  jmp     loc_14000F40F
0x14000f2ed  movzx   ecx, byte ptr [rbx+230h]
0x14000f2f4  lea     rdx, [rbx+220h]
0x14000f2fb  mov     [rax+44h], cl
0x14000f2fe  mov     esi, 10h
0x14000f303  mov     al, [rbx+21Ch]
0x14000f309  mov     r8d, ecx
0x14000f30c  mov     [r11+30h], al
0x14000f310  lea     rcx, [r11+34h]
0x14000f314  movzx   eax, word ptr [rbx+21Eh]
0x14000f31b  cmp     ax, 2
0x14000f31f  mov     [r11+8], ax
0x14000f324  lea     r9d, [rsi-0Ch]
0x14000f328  cmovnz  r9d, esi
0x14000f32c  call    WinNatCopyPrefix
0x14000f331  cmp     word ptr [r11+8], 2
0x14000f337  lea     r9d, [rsi-0Ch]
0x14000f33b  movzx   r8d, byte ptr [r11+30h]
0x14000f340  lea     rdx, [rbx+20Ch]
0x14000f347  cmovnz  r9d, esi
0x14000f34b  lea     rcx, [r11+20h]
0x14000f34f  call    WinNatCopyPrefix
0x14000f354  movzx   eax, byte ptr [rbx+244h]
0x14000f35b  cmp     al, 0FFh
0x14000f35d  jz      short loc_14000F376
0x14000f35f  mov     r8d, eax
0x14000f362  lea     rdx, [rbx+240h]
0x14000f369  lea     rcx, [r11+48h]
0x14000f36d  lea     r9d, [rsi-0Ch]
0x14000f371  call    WinNatCopyPrefix
0x14000f376  mov     al, [rbx+244h]
0x14000f37c  mov     edx, 1
0x14000f381  mov     [r11+4Ch], al
0x14000f385  mov     rax, [rbx+238h]
0x14000f38c  mov     [r11+58h], rax
0x14000f390  mov     eax, edx
0x14000f392  mov     [r11], rdx
0x14000f395  lock xadd [rdi+140h], rax
0x14000f39e  add     rax, rdx
0x14000f3a1  lea     r8d, [rdx+0Dh]
0x14000f3a5  cmp     rax, rdx
0x14000f3a8  jg      short loc_14000F3AF
0x14000f3aa  mov     ecx, r8d
0x14000f3ad  int     29h; Win8: RtlFailFast(ecx)
0x14000f3af  movzx   ecx, byte ptr [r11+44h]
0x14000f3b4  lea     r9, qword_140026AB0
0x14000f3bb  movzx   eax, byte ptr [r11+30h]
0x14000f3c0  shl     rcx, 10h
0x14000f3c4  add     rcx, rax
0x14000f3c7  mov     [r11+50h], rdi
0x14000f3cb  mov     [r11+68h], rcx
0x14000f3cf  mov     rcx, cs:qword_140026AB8
0x14000f3d6  cmp     [rcx], r9
0x14000f3d9  jz      short loc_14000F3E2
0x14000f3db  mov     ecx, 3
0x14000f3e0  int     29h; Win8: RtlFailFast(ecx)
0x14000f3e2  lea     rax, [r11+10h]
0x14000f3e6  mov     [rax], r9
0x14000f3e9  mov     [rax+8], rcx
0x14000f3ed  mov     [rcx], rax
0x14000f3f0  mov     cs:qword_140026AB8, rax
0x14000f3f7  mov     rax, rdx
0x14000f3fa  lock xadd [r11], rax
0x14000f3ff  add     rax, rdx
0x14000f402  cmp     rax, rdx
0x14000f405  jg      short loc_14000F40C
0x14000f407  mov     rcx, r8
0x14000f40a  int     29h; Win8: RtlFailFast(ecx)
0x14000f40c  mov     rax, r11
0x14000f40f  mov     rbx, [rsp+28h+arg_0]
0x14000f414  mov     rsi, [rsp+28h+arg_8]
0x14000f419  add     rsp, 20h
0x14000f41d  pop     rdi
0x14000f41e  retn
```
