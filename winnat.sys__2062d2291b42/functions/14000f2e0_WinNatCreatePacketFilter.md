# WinNatCreatePacketFilter

- ea: `0x14000f2e0`
- end: `0x14000f478`
- name: `WinNatCreatePacketFilter`
- size: `408`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140011420`

## callees

- `0x14000e4b0`
- `0x14000ee3c`
- `0x14000f2e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000f303`
- `ntoskrnl!ExAllocatePool2` at `0x14000f303`

## pseudocode

```c
__int64 __fastcall WinNatCreatePacketFilter(__int64 a1, __int64 a2)
{
  __int64 Pool2; // rax
  __int64 v5; // r8
  __int64 v6; // r11
  unsigned int v8; // ecx
  unsigned int v9; // r8d
  __int64 v10; // rcx
  __int16 v11; // ax
  unsigned int v12; // r9d
  __int64 v13; // r11
  unsigned int v14; // r9d
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
      WinNatCopyPrefix(v15 + 72, a1 + 576, *(unsigned __int8 *)(a1 + 580), 4u);
    *(_BYTE *)(v15 + 76) = *(_BYTE *)(a1 + 580);
    *(_QWORD *)(v15 + 88) = *(_QWORD *)(a1 + 568);
    *(_QWORD *)v15 = 1;
    if ( _InterlockedIncrement64((volatile signed __int64 *)(a2 + 320)) <= 1 )
      __fastfail(0xEu);
    v16 = *(unsigned __int8 *)(v15 + 48) + ((unsigned __int64)*(unsigned __int8 *)(v15 + 68) << 16);
    *(_QWORD *)(v15 + 80) = a2;
    *(_QWORD *)(v15 + 104) = v16;
    v17 = (_QWORD *)qword_140027AB8;
    if ( *(__int64 **)qword_140027AB8 != &qword_140027AB0 )
      __fastfail(3u);
    *(_QWORD *)(v15 + 16) = &qword_140027AB0;
    *(_QWORD *)(v15 + 24) = v17;
    *v17 = v15 + 16;
    qword_140027AB8 = v15 + 16;
    if ( _InterlockedIncrement64((volatile signed __int64 *)v15) <= 1 )
      __fastfail(0xEu);
    return v15;
  }
  else
  {
    if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x20) != 0 )
      McTemplateK0z_EtwWriteTransfer(&MICROSOFT_WINNAT_ETW_PROVIDER_Context, 1, v5, L"Packet filter allocation failed");
    return 0;
  }
}

```

## disassembly

```asm
0x14000f2e0  mov     [rsp+arg_0], rbx
0x14000f2e5  mov     [rsp+arg_8], rsi
0x14000f2ea  push    rdi
0x14000f2eb  sub     rsp, 20h
0x14000f2ef  mov     rdi, rdx
0x14000f2f2  mov     rbx, rcx
0x14000f2f5  mov     edx, 78h ; 'x'
0x14000f2fa  mov     r8d, 66704E57h
0x14000f300  lea     ecx, [rdx-38h]
0x14000f303  call    cs:__imp_ExAllocatePool2
0x14000f30a  nop     dword ptr [rax+rax+00h]
0x14000f30f  mov     r11, rax
0x14000f312  test    rax, rax
0x14000f315  jnz     short loc_14000F345
0x14000f317  lea     edx, [rax+1]
0x14000f31a  cmp     cs:dword_140027104, edx
0x14000f320  jnz     short loc_14000F33E
0x14000f322  test    cs:Microsoft_Windows_WinNatEnableBits, 20h
0x14000f329  jz      short loc_14000F33E
0x14000f32b  lea     r9, aPacketFilterAl; "Packet filter allocation failed"
0x14000f332  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14000f339  call    McTemplateK0z_EtwWriteTransfer
0x14000f33e  xor     eax, eax
0x14000f340  jmp     loc_14000F467
0x14000f345  movzx   ecx, byte ptr [rbx+230h]
0x14000f34c  lea     rdx, [rbx+220h]
0x14000f353  mov     [rax+44h], cl
0x14000f356  mov     esi, 10h
0x14000f35b  mov     al, [rbx+21Ch]
0x14000f361  mov     r8d, ecx
0x14000f364  mov     [r11+30h], al
0x14000f368  lea     rcx, [r11+34h]
0x14000f36c  movzx   eax, word ptr [rbx+21Eh]
0x14000f373  cmp     ax, 2
0x14000f377  mov     [r11+8], ax
0x14000f37c  lea     r9d, [rsi-0Ch]
0x14000f380  cmovnz  r9d, esi
0x14000f384  call    WinNatCopyPrefix
0x14000f389  cmp     word ptr [r11+8], 2
0x14000f38f  lea     r9d, [rsi-0Ch]
0x14000f393  movzx   r8d, byte ptr [r11+30h]
0x14000f398  lea     rdx, [rbx+20Ch]
0x14000f39f  cmovnz  r9d, esi
0x14000f3a3  lea     rcx, [r11+20h]
0x14000f3a7  call    WinNatCopyPrefix
0x14000f3ac  movzx   eax, byte ptr [rbx+244h]
0x14000f3b3  cmp     al, 0FFh
0x14000f3b5  jz      short loc_14000F3CE
0x14000f3b7  mov     r8d, eax
0x14000f3ba  lea     rdx, [rbx+240h]
0x14000f3c1  lea     rcx, [r11+48h]
0x14000f3c5  lea     r9d, [rsi-0Ch]
0x14000f3c9  call    WinNatCopyPrefix
0x14000f3ce  mov     al, [rbx+244h]
0x14000f3d4  mov     edx, 1
0x14000f3d9  mov     [r11+4Ch], al
0x14000f3dd  mov     rax, [rbx+238h]
0x14000f3e4  mov     [r11+58h], rax
0x14000f3e8  mov     eax, edx
0x14000f3ea  mov     [r11], rdx
0x14000f3ed  lock xadd [rdi+140h], rax
0x14000f3f6  add     rax, rdx
0x14000f3f9  lea     r8d, [rdx+0Dh]
0x14000f3fd  cmp     rax, rdx
0x14000f400  jg      short loc_14000F407
0x14000f402  mov     ecx, r8d
0x14000f405  int     29h; Win8: RtlFailFast(ecx)
0x14000f407  movzx   ecx, byte ptr [r11+44h]
0x14000f40c  lea     r9, qword_140027AB0
0x14000f413  movzx   eax, byte ptr [r11+30h]
0x14000f418  shl     rcx, 10h
0x14000f41c  add     rcx, rax
0x14000f41f  mov     [r11+50h], rdi
0x14000f423  mov     [r11+68h], rcx
0x14000f427  mov     rcx, cs:qword_140027AB8
0x14000f42e  cmp     [rcx], r9
0x14000f431  jz      short loc_14000F43A
0x14000f433  mov     ecx, 3
0x14000f438  int     29h; Win8: RtlFailFast(ecx)
0x14000f43a  lea     rax, [r11+10h]
0x14000f43e  mov     [rax], r9
0x14000f441  mov     [rax+8], rcx
0x14000f445  mov     [rcx], rax
0x14000f448  mov     cs:qword_140027AB8, rax
0x14000f44f  mov     rax, rdx
0x14000f452  lock xadd [r11], rax
0x14000f457  add     rax, rdx
0x14000f45a  cmp     rax, rdx
0x14000f45d  jg      short loc_14000F464
0x14000f45f  mov     rcx, r8
0x14000f462  int     29h; Win8: RtlFailFast(ecx)
0x14000f464  mov     rax, r11
0x14000f467  mov     rbx, [rsp+28h+arg_0]
0x14000f46c  mov     rsi, [rsp+28h+arg_8]
0x14000f471  add     rsp, 20h
0x14000f475  pop     rdi
0x14000f476  retn
```
