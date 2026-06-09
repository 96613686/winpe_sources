# VidTriggerpCreatePort

- ea: `0x140097c54`
- end: `0x140097e6d`
- name: `VidTriggerpCreatePort`
- size: `537`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400973f8`

## callees

- `0x140008fd8`
- `0x140021650`
- `0x140038630`
- `0x140097c54`

## import_xrefs

- `winhvr!WinHvConnectPort` at `0x140097de1`
- `winhvr!WinHvConnectPort` at `0x140097de1`
- `winhvr!WinHvDeletePort` at `0x140097e42`
- `winhvr!WinHvDeletePort` at `0x140097e42`
- `winhvr!WinHvCreatePort` at `0x140097cd9`
- `winhvr!WinHvCreatePort` at `0x140097cd9`
- `winhvr!WinHvFreePortId` at `0x140097e24`
- `winhvr!WinHvFreePortId` at `0x140097e24`
- `winhvr!WinHvAllocatePortId` at `0x140097d16`
- `winhvr!WinHvAllocatePortId` at `0x140097d16`

## string_xrefs

- `0x140097cfb`: `VidTriggerpCreatePort`
- `0x140097d35`: `VidTriggerpCreatePort`
- `0x140097e00`: `VidTriggerpCreatePort`

## pseudocode

```c
__int64 __fastcall VidTriggerpCreatePort(__int64 *a1)
{
  __int64 v2; // r8
  unsigned int v3; // r14d
  char v4; // al
  __int64 v5; // rcx
  int v6; // edi
  char v7; // si
  __int64 v8; // r9
  __int64 v9; // r8
  int v11; // [rsp+20h] [rbp-59h]
  int v12; // [rsp+30h] [rbp-49h]
  int v13; // [rsp+40h] [rbp-39h] BYREF
  __int64 v14; // [rsp+48h] [rbp-31h] BYREF
  int v15; // [rsp+50h] [rbp-29h]
  int v16; // [rsp+54h] [rbp-25h]
  __int64 v17; // [rsp+58h] [rbp-21h]
  _OWORD v18[2]; // [rsp+60h] [rbp-19h] BYREF
  __int128 v19; // [rsp+80h] [rbp+7h] BYREF

  v2 = *((unsigned int *)a1 + 31);
  v3 = *((unsigned __int8 *)a1 + 120) | 0x80000000;
  v15 = *((unsigned __int8 *)a1 + 117);
  v16 = *((_DWORD *)a1 + 28);
  v4 = *((_BYTE *)a1 + 116);
  v5 = *a1;
  memset(v18, 0, sizeof(v18));
  v14 = 2;
  v17 = 0x8000000;
  v13 = 0xFFFFFF;
  v6 = WinHvCreatePort(v5, v3, v2, -1, &v14, v4, 0);
  if ( v6 >= 0 )
  {
    v7 = 1;
    v6 = WinHvAllocatePortId(a1, &v13);
    if ( v6 >= 0 )
    {
      *((_DWORD *)a1 + 34) = a1[17] & 0xFF000000 | v13 & 0xFFFFFF;
      v19 = 0;
      HviGetHypervisorFeatures(&v19);
      if ( (v19 & 0x100000000LL) != 0 )
      {
        v19 = 0;
        HviGetHypervisorFeatures(&v19);
        if ( (v19 & 0x100000000000LL) == 0 )
          *((_DWORD *)a1 + 34) = a1[17] & 0x3FFFFFFF | 0x40000000;
      }
      v8 = *a1;
      v9 = *((unsigned int *)a1 + 34);
      LOBYTE(v12) = 0;
      v11 = *((_DWORD *)a1 + 31);
      LODWORD(v18[0]) = 2;
      v6 = WinHvConnectPort(-1, v3, v9, v8, v11, v18, v12);
      if ( v6 >= 0 )
      {
        v13 |= 0xFFFFFFu;
        v7 = 0;
        v6 = 0;
      }
      else
      {
        VidTraceErrorInternal0("VidTriggerpCreatePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 898);
      }
    }
    else
    {
      VidTraceErrorInternal0("VidTriggerpCreatePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 869);
    }
  }
  else
  {
    v7 = 0;
    VidTraceErrorInternal0("VidTriggerpCreatePort", "onecore\\vm\\vid\\sys\\driver\\vidtrigger.c", 858);
  }
  if ( (v13 & 0xFFFFFF) != 0xFFFFFF )
  {
    WinHvFreePortId();
    *((_DWORD *)a1 + 34) |= 0xFFFFFFu;
  }
  if ( v7 )
    WinHvDeletePort(*a1, *((unsigned int *)a1 + 31));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140097c54  push    rbp
0x140097c56  push    rbx
0x140097c57  push    rsi
0x140097c58  push    rdi
0x140097c59  push    r12
0x140097c5b  push    r14
0x140097c5d  lea     rbp, [rsp-2Fh]
0x140097c62  sub     rsp, 0A8h
0x140097c69  mov     rax, cs:__security_cookie
0x140097c70  xor     rax, rsp
0x140097c73  mov     [rbp+57h+var_40], rax
0x140097c77  movzx   eax, byte ptr [rcx+75h]
0x140097c7b  xorps   xmm0, xmm0
0x140097c7e  movzx   r14d, byte ptr [rcx+78h]
0x140097c83  mov     rbx, rcx
0x140097c86  mov     r8d, [rcx+7Ch]
0x140097c8a  bts     r14d, 1Fh
0x140097c8f  mov     [rbp+57h+var_80], eax
0x140097c92  mov     r12d, 0FFFFFFh
0x140097c98  mov     eax, [rcx+70h]
0x140097c9b  or      r9, 0FFFFFFFFFFFFFFFFh
0x140097c9f  mov     [rbp+57h+var_7C], eax
0x140097ca2  mov     edx, r14d
0x140097ca5  mov     al, [rcx+74h]
0x140097ca8  mov     rcx, [rcx]
0x140097cab  mov     byte ptr [rsp+0D0h+var_A0], 0
0x140097cb0  mov     byte ptr [rsp+0D0h+var_A8], al
0x140097cb4  lea     rax, [rbp+57h+var_88]
0x140097cb8  mov     [rsp+0D0h+var_B0], rax
0x140097cbd  movups  [rbp+57h+var_70], xmm0
0x140097cc1  mov     [rbp+57h+var_88], 2
0x140097cc9  movups  [rbp+57h+var_60], xmm0
0x140097ccd  mov     [rbp+57h+var_78], 8000000h
0x140097cd5  mov     [rbp+57h+var_90], r12d
0x140097cd9  call    cs:__imp_WinHvCreatePort
0x140097ce0  nop     dword ptr [rax+rax+00h]
0x140097ce5  mov     edi, eax
0x140097ce7  test    eax, eax
0x140097ce9  jns     short loc_140097D0C
0x140097ceb  xor     sil, sil
0x140097cee  mov     r8d, 35Ah
0x140097cf4  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097cfb  lea     rcx, aVidtriggerpcre; "VidTriggerpCreatePort"
0x140097d02  call    VidTraceErrorInternal0
0x140097d07  jmp     loc_140097E17
0x140097d0c  lea     rdx, [rbp+57h+var_90]
0x140097d10  mov     rcx, rbx
0x140097d13  mov     sil, 1
0x140097d16  call    cs:__imp_WinHvAllocatePortId
0x140097d1d  nop     dword ptr [rax+rax+00h]
0x140097d22  mov     edi, eax
0x140097d24  test    eax, eax
0x140097d26  jns     short loc_140097D46
0x140097d28  mov     r8d, 365h
0x140097d2e  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097d35  lea     rcx, aVidtriggerpcre; "VidTriggerpCreatePort"
0x140097d3c  call    VidTraceErrorInternal0
0x140097d41  jmp     loc_140097E17
0x140097d46  mov     ecx, [rbp+57h+var_90]
0x140097d49  xorps   xmm0, xmm0
0x140097d4c  mov     eax, [rbx+88h]
0x140097d52  and     ecx, r12d
0x140097d55  and     eax, 0FF000000h
0x140097d5a  or      ecx, eax
0x140097d5c  mov     [rbx+88h], ecx
0x140097d62  lea     rcx, [rbp+57h+var_50]
0x140097d66  movups  [rbp+57h+var_50], xmm0
0x140097d6a  call    HviGetHypervisorFeatures
0x140097d6f  mov     rax, 100000000h
0x140097d79  test    qword ptr [rbp+57h+var_50], rax
0x140097d7d  jz      short loc_140097DB4
0x140097d7f  xorps   xmm0, xmm0
0x140097d82  lea     rcx, [rbp+57h+var_50]
0x140097d86  movups  [rbp+57h+var_50], xmm0
0x140097d8a  call    HviGetHypervisorFeatures
0x140097d8f  mov     rax, 100000000000h
0x140097d99  test    qword ptr [rbp+57h+var_50], rax
0x140097d9d  jnz     short loc_140097DB4
0x140097d9f  mov     eax, [rbx+88h]
0x140097da5  and     eax, 3FFFFFFFh
0x140097daa  bts     eax, 1Eh
0x140097dae  mov     [rbx+88h], eax
0x140097db4  mov     r9, [rbx]
0x140097db7  lea     rax, [rbp+57h+var_70]
0x140097dbb  mov     r8d, [rbx+88h]
0x140097dc2  mov     edx, r14d
0x140097dc5  mov     byte ptr [rsp+0D0h+var_A0], 0
0x140097dca  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140097dce  mov     [rsp+0D0h+var_A8], rax
0x140097dd3  mov     eax, [rbx+7Ch]
0x140097dd6  mov     dword ptr [rsp+0D0h+var_B0], eax
0x140097dda  mov     dword ptr [rbp+57h+var_70], 2
0x140097de1  call    cs:__imp_WinHvConnectPort
0x140097de8  nop     dword ptr [rax+rax+00h]
0x140097ded  mov     edi, eax
0x140097def  test    eax, eax
0x140097df1  jns     short loc_140097E0E
0x140097df3  mov     r8d, 382h
0x140097df9  lea     rdx, aOnecoreVmVidSy_50; "onecore\\vm\\vid\\sys\\driver\\vidtrigg"...
0x140097e00  lea     rcx, aVidtriggerpcre; "VidTriggerpCreatePort"
0x140097e07  call    VidTraceErrorInternal0
0x140097e0c  jmp     short loc_140097E17
0x140097e0e  or      [rbp+57h+var_90], r12d
0x140097e12  xor     sil, sil
0x140097e15  xor     edi, edi
0x140097e17  mov     ecx, [rbp+57h+var_90]
0x140097e1a  mov     eax, ecx
0x140097e1c  and     eax, r12d
0x140097e1f  cmp     eax, r12d
0x140097e22  jz      short loc_140097E37
0x140097e24  call    cs:__imp_WinHvFreePortId
0x140097e2b  nop     dword ptr [rax+rax+00h]
0x140097e30  or      [rbx+88h], r12d
0x140097e37  test    sil, sil
0x140097e3a  jz      short loc_140097E4E
0x140097e3c  mov     edx, [rbx+7Ch]
0x140097e3f  mov     rcx, [rbx]
0x140097e42  call    cs:__imp_WinHvDeletePort
0x140097e49  nop     dword ptr [rax+rax+00h]
0x140097e4e  mov     eax, edi
0x140097e50  mov     rcx, [rbp+57h+var_40]
0x140097e54  xor     rcx, rsp; StackCookie
0x140097e57  call    __security_check_cookie
0x140097e5c  add     rsp, 0A8h
0x140097e63  pop     r14
0x140097e65  pop     r12
0x140097e67  pop     rdi
0x140097e68  pop     rsi
0x140097e69  pop     rbx
0x140097e6a  pop     rbp
0x140097e6b  retn
```
