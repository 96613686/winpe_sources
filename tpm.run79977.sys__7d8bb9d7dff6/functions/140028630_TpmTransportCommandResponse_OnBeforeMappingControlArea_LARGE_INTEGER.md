# TpmTransportCommandResponse::OnBeforeMappingControlArea(_LARGE_INTEGER)

- ea: `0x140028630`
- end: `0x1400287dd`
- name: `?OnBeforeMappingControlArea@TpmTransportCommandResponse@@MEAAJT_LARGE_INTEGER@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(TpmTransportCommandResponse *__hidden this, union _LARGE_INTEGER)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003208`
- `0x1400078b8`
- `0x140009278`
- `0x140028630`
- `0x140039780`

## import_xrefs

- `ntoskrnl!MmUnmapIoSpace` at `0x1400287b0`
- `ntoskrnl!MmUnmapIoSpace` at `0x1400287b0`
- `ntoskrnl!MmMapIoSpaceEx` at `0x14002869d`
- `ntoskrnl!MmMapIoSpaceEx` at `0x14002869d`

## pseudocode

```c
__int64 __fastcall TpmTransportCommandResponse::OnBeforeMappingControlArea(
        TpmTransportCommandResponse *this,
        union _LARGE_INTEGER a2)
{
  int v4; // esi
  char v5; // bp
  __int64 v6; // rax
  __int64 v7; // r8
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdx
  void *v14; // rcx
  __int64 v16; // [rsp+50h] [rbp+8h]

  v4 = 0;
  v5 = 1;
  if ( !(*(unsigned int (__fastcall **)(TpmTransportCommandResponse *))(*(_QWORD *)this + 128LL))(this)
    || (a2.LowPart & 0xFFF) != 0x40 )
  {
    goto LABEL_23;
  }
  HIDWORD(v16) = a2.HighPart;
  if ( *((_QWORD *)this + 42) )
  {
    v4 = -1073741823;
LABEL_19:
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v13 = 13;
      v12 = (unsigned int)v4;
      goto LABEL_22;
    }
    goto LABEL_23;
  }
  LODWORD(v16) = a2.LowPart & 0xFFFFF000;
  v6 = MmMapIoSpaceEx(v16, 64, 516);
  *((_QWORD *)this + 42) = v6;
  if ( !v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_23;
    v9 = 10;
    goto LABEL_9;
  }
  *((_DWORD *)this + 86) = 64;
  v10 = *(unsigned __int8 *)(v6 + 48);
  if ( (*(_BYTE *)(v6 + 48) & 0xF) == 1 )
  {
    if ( (v10 & 0xF0) != 0 )
    {
      v5 = 0;
      v4 = TpmTransportCommandResponse::CheckRequestPttLocalityZero(this, v10, v7);
      if ( v4 >= 0 )
        goto LABEL_23;
      goto LABEL_19;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_23;
    v9 = 12;
LABEL_9:
    WPP_SF_(v8->AttachedDevice, v9, WPP_2fc68934a9f83936555335448f322e27_Traceguids);
    goto LABEL_23;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v12 = *(unsigned __int8 *)(v6 + 48);
    v13 = 11;
LABEL_22:
    WPP_SF_d(v11->AttachedDevice, v13, WPP_2fc68934a9f83936555335448f322e27_Traceguids, v12);
  }
LABEL_23:
  v14 = (void *)*((_QWORD *)this + 42);
  if ( v14 && v5 )
  {
    MmUnmapIoSpace(v14, *((unsigned int *)this + 86));
    *((_QWORD *)this + 42) = 0;
    *((_DWORD *)this + 86) = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140028630  push    rbx
0x140028632  push    rbp
0x140028633  push    rsi
0x140028634  push    rdi
0x140028635  sub     rsp, 28h
0x140028639  mov     rax, [rcx]
0x14002863c  mov     rbx, rdx
0x14002863f  mov     rdi, rcx
0x140028642  xor     esi, esi
0x140028644  mov     bpl, 1
0x140028647  mov     rax, [rax+80h]
0x14002864e  call    _guard_dispatch_icall
0x140028653  test    eax, eax
0x140028655  jz      loc_140028799
0x14002865b  mov     eax, ebx
0x14002865d  and     eax, 0FFFh
0x140028662  cmp     eax, 40h ; '@'
0x140028665  jnz     loc_140028799
0x14002866b  mov     [rsp+48h+arg_0], rbx
0x140028670  and     ebx, 0FFFFF000h
0x140028676  mov     dword ptr [rsp+48h+arg_0], ebx
0x14002867a  cmp     [rdi+150h], rsi
0x140028681  jz      short loc_14002868D
0x140028683  mov     esi, 0C0000001h
0x140028688  jmp     loc_140028766
0x14002868d  mov     rcx, [rsp+48h+arg_0]
0x140028692  mov     edx, 40h ; '@'
0x140028697  mov     r8d, 204h
0x14002869d  call    cs:__imp_MmMapIoSpaceEx
0x1400286a4  nop     dword ptr [rax+rax+00h]
0x1400286a9  mov     [rdi+150h], rax
0x1400286b0  test    rax, rax
0x1400286b3  jnz     short loc_1400286F2
0x1400286b5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400286bc  lea     rax, WPP_GLOBAL_Control
0x1400286c3  cmp     rcx, rax
0x1400286c6  jz      loc_140028799
0x1400286cc  mov     eax, [rcx+2Ch]
0x1400286cf  test    bpl, al
0x1400286d2  jz      loc_140028799
0x1400286d8  mov     edx, 0Ah
0x1400286dd  mov     rcx, [rcx+18h]
0x1400286e1  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x1400286e8  call    WPP_SF_
0x1400286ed  jmp     loc_140028799
0x1400286f2  mov     dword ptr [rdi+158h], 40h ; '@'
0x1400286fc  movzx   edx, byte ptr [rax+30h]
0x140028700  mov     al, dl
0x140028702  and     al, 0Fh
0x140028704  cmp     al, bpl
0x140028707  jz      short loc_14002872E
0x140028709  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028710  lea     rax, WPP_GLOBAL_Control
0x140028717  cmp     rcx, rax
0x14002871a  jz      short loc_140028799
0x14002871c  mov     eax, [rcx+2Ch]
0x14002871f  test    bpl, al
0x140028722  jz      short loc_140028799
0x140028724  mov     r9d, edx
0x140028727  mov     edx, 0Bh
0x14002872c  jmp     short loc_140028789
0x14002872e  test    dl, 0F0h
0x140028731  jnz     short loc_140028755
0x140028733  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002873a  lea     rax, WPP_GLOBAL_Control
0x140028741  cmp     rcx, rax
0x140028744  jz      short loc_140028799
0x140028746  mov     eax, [rcx+2Ch]
0x140028749  test    bpl, al
0x14002874c  jz      short loc_140028799
0x14002874e  mov     edx, 0Ch
0x140028753  jmp     short loc_1400286DD
0x140028755  xor     bpl, bpl
0x140028758  mov     rcx, rdi; this
0x14002875b  call    ?CheckRequestPttLocalityZero@TpmTransportCommandResponse@@AEAAJXZ; TpmTransportCommandResponse::CheckRequestPttLocalityZero(void)
0x140028760  mov     esi, eax
0x140028762  test    eax, eax
0x140028764  jns     short loc_140028799
0x140028766  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002876d  lea     rax, WPP_GLOBAL_Control
0x140028774  cmp     rcx, rax
0x140028777  jz      short loc_140028799
0x140028779  mov     edx, [rcx+2Ch]
0x14002877c  test    dl, 1
0x14002877f  jz      short loc_140028799
0x140028781  mov     edx, 0Dh
0x140028786  mov     r9d, esi
0x140028789  mov     rcx, [rcx+18h]
0x14002878d  lea     r8, WPP_2fc68934a9f83936555335448f322e27_Traceguids
0x140028794  call    WPP_SF_d
0x140028799  mov     rcx, [rdi+150h]; BaseAddress
0x1400287a0  test    rcx, rcx
0x1400287a3  jz      short loc_1400287D1
0x1400287a5  test    bpl, bpl
0x1400287a8  jz      short loc_1400287D1
0x1400287aa  mov     edx, [rdi+158h]; NumberOfBytes
0x1400287b0  call    cs:__imp_MmUnmapIoSpace
0x1400287b7  nop     dword ptr [rax+rax+00h]
0x1400287bc  mov     qword ptr [rdi+150h], 0
0x1400287c7  mov     dword ptr [rdi+158h], 0
0x1400287d1  mov     eax, esi
0x1400287d3  add     rsp, 28h
0x1400287d7  pop     rdi
0x1400287d8  pop     rsi
0x1400287d9  pop     rbp
0x1400287da  pop     rbx
0x1400287db  retn
```
