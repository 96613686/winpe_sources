# ProbeCommitSetHandler

- ea: `0x14000a4b4`
- end: `0x14000a878`
- name: `ProbeCommitSetHandler`
- size: `964`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char)`
- caller_count: `6`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009f34`
- `0x14000b57c`
- `0x14002b690`
- `0x14002b8e0`
- `0x14002bb20`
- `0x14002bd60`

## callees

- `0x140009dc8`
- `0x14000a4b4`
- `0x14000ba98`
- `0x14001d0cc`
- `0x140023848`
- `0x140024ec4`
- `0x140024fb0`
- `0x140040962`
- `0x140040a30`
- `0x140040a70`

## pseudocode

```c
__int64 __fastcall ProbeCommitSetHandler(int a1, __int64 a2, __int64 a3, __int64 a4, char a5)
{
  char v5; // al
  _OWORD *v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rbx
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int64 v12; // rcx
  unsigned int v13; // eax
  int SetInterfaceControl; // r12d
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  unsigned __int8 v21; // r15
  unsigned int v22; // eax
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm2
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-79h]
  SIZE_T NumberOfBytesa; // [rsp+28h] [rbp-79h]
  SIZE_T NumberOfBytesb; // [rsp+28h] [rbp-79h]
  __int64 v32; // [rsp+80h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+88h] [rbp-19h] BYREF
  __int128 v34; // [rsp+98h] [rbp-9h]
  __int128 v35; // [rsp+A8h] [rbp+7h]

  v5 = *(_BYTE *)(a3 + 76);
  v6 = *(_OWORD **)(a2 + 432);
  v7 = a3;
  v8 = a2;
  v10 = *(_OWORD *)(a2 + 200);
  Buf1 = *(_OWORD *)(a2 + 184);
  BYTE2(Buf1) = v5;
  BYTE3(Buf1) = *(_BYTE *)(a3 + 77);
  v11 = *(_OWORD *)(a2 + 216);
  v34 = v10;
  v35 = v11;
  if ( a4 )
  {
    v12 = *(_QWORD *)(a2 + 392);
    v32 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v12 + 104LL))(v12, a4, 0, &v32);
    DWORD1(Buf1) = bestMatchedFrameRate(*(unsigned int *)(v7 + 48), *(_QWORD *)(v7 + 40), v13);
  }
  if ( *(_DWORD *)(v8 + 104) )
    *(_DWORD *)((char *)&v34 + 6) = *(_DWORD *)(v8 + 28);
  else
    *(_DWORD *)((char *)&v34 + 6) = 0;
  if ( *(_BYTE *)(v8 + 386) )
  {
    SetInterfaceControl = CombineProbeCommitControls(&Buf1, v6);
    if ( SetInterfaceControl < 0 )
      goto LABEL_26;
  }
  LOBYTE(a3) = 1;
  LOBYTE(a4) = *(_BYTE *)(v8 + 177);
  LOBYTE(a2) = 1;
  LODWORD(NumberOfBytes) = *(_DWORD *)(v8 + 180);
  SetInterfaceControl = GetSetInterfaceControl(*(_QWORD *)(v8 + 424), a2, a3, a4, &Buf1, NumberOfBytes);
  if ( SetInterfaceControl < 0
    || (LOBYTE(v16) = 1,
        LOBYTE(v17) = *(_BYTE *)(v8 + 177),
        LOBYTE(v15) = -127,
        LODWORD(NumberOfBytesa) = *(_DWORD *)(v8 + 180),
        SetInterfaceControl = GetSetInterfaceControl(*(_QWORD *)(v8 + 424), v15, v16, v17, &Buf1, NumberOfBytesa),
        SetInterfaceControl < 0) )
  {
LABEL_26:
    v21 = a5;
  }
  else
  {
    if ( *(_BYTE *)(v8 + 386) )
    {
      if ( !memcmp_0(&Buf1, (const void *)(v8 + 328), 0x30u) )
      {
        v21 = 0;
LABEL_25:
        v26 = v34;
        *(_OWORD *)(v8 + 184) = Buf1;
        v27 = v35;
        *(_OWORD *)(v8 + 200) = v26;
        *(_OWORD *)(v8 + 216) = v27;
        goto LABEL_27;
      }
      v21 = 1;
    }
    else
    {
      v21 = a5;
      if ( !a5 )
        goto LABEL_25;
      v22 = *(_DWORD *)(v8 + 202);
      if ( v22 && *(_DWORD *)((char *)&v34 + 2) > v22 )
      {
        SetInterfaceControl = -1073741823;
        goto LABEL_27;
      }
    }
    LOBYTE(v19) = 2;
    LOBYTE(v20) = *(_BYTE *)(v8 + 177);
    LOBYTE(v18) = 1;
    LODWORD(NumberOfBytesb) = *(_DWORD *)(v8 + 180);
    SetInterfaceControl = GetSetInterfaceControl(a1, v18, v19, v20, &Buf1, NumberOfBytesb);
    if ( SetInterfaceControl >= 0 )
    {
      if ( *(_BYTE *)(v8 + 386) )
      {
        v23 = Buf1;
        v24 = v34;
        v25 = v35;
        *(_OWORD *)(v8 + 328) = Buf1;
        *(_OWORD *)(v8 + 344) = v24;
        *(_OWORD *)(v8 + 360) = v25;
        if ( v6 )
        {
          v6[5] = v23;
          v6[6] = v24;
          v6[7] = v25;
        }
      }
      goto LABEL_25;
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return (unsigned int)SetInterfaceControl;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v6, v8);
  }
LABEL_27:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, v6, v8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_DDDDDDDDDDDD(
          WPP_GLOBAL_Control->AttachedDevice,
          (unsigned __int16)v34,
          HIWORD(Buf1),
          v21,
          Buf1,
          SBYTE2(Buf1),
          SBYTE3(Buf1),
          SBYTE4(Buf1),
          SBYTE8(Buf1),
          SBYTE10(Buf1),
          SBYTE12(Buf1),
          SBYTE14(Buf1),
          v34,
          SBYTE2(v34),
          SBYTE6(v34));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_DDDDDDDDDDi(
          WPP_GLOBAL_Control->AttachedDevice,
          WORD3(v35),
          BYTE5(v35),
          *(_DWORD *)((char *)&v34 + 10),
          SBYTE14(v34),
          SHIBYTE(v34),
          v35,
          SBYTE1(v35),
          SBYTE2(v35),
          SBYTE3(v35),
          SBYTE4(v35),
          SBYTE5(v35),
          SBYTE6(v35),
          SBYTE8(v35));
    }
  }
  return (unsigned int)SetInterfaceControl;
}

```

## disassembly

```asm
0x14000a4b4  push    rbp
0x14000a4b6  push    rbx
0x14000a4b7  push    rsi
0x14000a4b8  push    rdi
0x14000a4b9  push    r12
0x14000a4bb  push    r14
0x14000a4bd  push    r15
0x14000a4bf  lea     rbp, [rsp-1Fh]
0x14000a4c4  sub     rsp, 0C0h
0x14000a4cb  mov     rax, cs:__security_cookie
0x14000a4d2  xor     rax, rsp
0x14000a4d5  mov     [rbp+4Fh+var_38], rax
0x14000a4d9  mov     al, [r8+4Ch]
0x14000a4dd  mov     r10, r9
0x14000a4e0  mov     rdi, [rdx+1B0h]
0x14000a4e7  mov     rsi, r8
0x14000a4ea  mov     rbx, rdx
0x14000a4ed  mov     r14, rcx
0x14000a4f0  movups  xmm0, xmmword ptr [rdx+0B8h]
0x14000a4f7  movups  xmm1, xmmword ptr [rdx+0C8h]
0x14000a4fe  movups  [rbp+4Fh+Buf1], xmm0
0x14000a502  mov     byte ptr [rbp+4Fh+Buf1+2], al
0x14000a505  mov     al, [r8+4Dh]
0x14000a509  mov     byte ptr [rbp+4Fh+Buf1+3], al
0x14000a50c  movups  xmm0, xmmword ptr [rdx+0D8h]
0x14000a513  movups  [rbp+4Fh+var_58], xmm1
0x14000a517  movups  [rbp+4Fh+var_48], xmm0
0x14000a51b  test    r9, r9
0x14000a51e  jz      short loc_14000A557
0x14000a520  mov     rcx, [rdx+188h]
0x14000a527  lea     r9, [rbp+4Fh+var_70]
0x14000a52b  mov     [rbp+4Fh+var_70], 0
0x14000a533  xor     r8d, r8d
0x14000a536  mov     rdx, r10
0x14000a539  mov     rax, [rcx]
0x14000a53c  mov     rax, [rax+68h]
0x14000a540  call    _guard_dispatch_icall
0x14000a545  mov     rdx, [rsi+28h]
0x14000a549  mov     r8d, eax
0x14000a54c  mov     ecx, [rsi+30h]
0x14000a54f  call    bestMatchedFrameRate
0x14000a554  mov     dword ptr [rbp+4Fh+Buf1+4], eax
0x14000a557  cmp     dword ptr [rbx+68h], 0
0x14000a55b  jz      short loc_14000A565
0x14000a55d  mov     eax, [rbx+1Ch]
0x14000a560  mov     dword ptr [rbp+4Fh+var_58+6], eax
0x14000a563  jmp     short loc_14000A56C
0x14000a565  mov     dword ptr [rbp+4Fh+var_58+6], 0
0x14000a56c  cmp     byte ptr [rbx+182h], 0
0x14000a573  lea     rsi, WPP_GLOBAL_Control
0x14000a57a  jz      short loc_14000A593
0x14000a57c  mov     rdx, rdi
0x14000a57f  lea     rcx, [rbp+4Fh+Buf1]
0x14000a583  call    CombineProbeCommitControls
0x14000a588  mov     r12d, eax
0x14000a58b  test    eax, eax
0x14000a58d  js      loc_14000A71E
0x14000a593  mov     eax, [rbx+0B4h]
0x14000a599  mov     r8b, 1; int
0x14000a59c  mov     r9b, [rbx+0B1h]; int
0x14000a5a3  mov     dl, r8b; int
0x14000a5a6  mov     rcx, [rbx+1A8h]; int
0x14000a5ad  mov     dword ptr [rsp+0F0h+NumberOfBytes], eax; NumberOfBytes
0x14000a5b1  lea     rax, [rbp+4Fh+Buf1]
0x14000a5b5  mov     [rsp+0F0h+Src], rax; Src
0x14000a5ba  call    GetSetInterfaceControl
0x14000a5bf  mov     r12d, eax
0x14000a5c2  test    eax, eax
0x14000a5c4  js      loc_14000A71E
0x14000a5ca  mov     eax, [rbx+0B4h]
0x14000a5d0  mov     r8b, 1; int
0x14000a5d3  mov     r9b, [rbx+0B1h]; int
0x14000a5da  mov     dl, 81h; int
0x14000a5dc  mov     rcx, [rbx+1A8h]; int
0x14000a5e3  mov     dword ptr [rsp+0F0h+NumberOfBytes], eax; NumberOfBytes
0x14000a5e7  lea     rax, [rbp+4Fh+Buf1]
0x14000a5eb  mov     [rsp+0F0h+Src], rax; Src
0x14000a5f0  call    GetSetInterfaceControl
0x14000a5f5  mov     r12d, eax
0x14000a5f8  test    eax, eax
0x14000a5fa  js      loc_14000A71E
0x14000a600  cmp     byte ptr [rbx+182h], 0
0x14000a607  jz      loc_14000A69C
0x14000a60d  lea     rdx, [rbx+148h]; Buf2
0x14000a614  mov     r8d, 30h ; '0'; Size
0x14000a61a  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x14000a61e  call    memcmp_0
0x14000a623  test    eax, eax
0x14000a625  jnz     short loc_14000A62F
0x14000a627  xor     r15b, r15b
0x14000a62a  jmp     loc_14000A6FB
0x14000a62f  mov     r15b, 1
0x14000a632  mov     eax, [rbx+0B4h]
0x14000a638  mov     r8b, 2; int
0x14000a63b  mov     r9b, [rbx+0B1h]; int
0x14000a642  mov     dl, 1; int
0x14000a644  mov     dword ptr [rsp+0F0h+NumberOfBytes], eax; NumberOfBytes
0x14000a648  mov     rcx, r14; int
0x14000a64b  lea     rax, [rbp+4Fh+Buf1]
0x14000a64f  mov     [rsp+0F0h+Src], rax; Src
0x14000a654  call    GetSetInterfaceControl
0x14000a659  mov     r12d, eax
0x14000a65c  test    eax, eax
0x14000a65e  jns     short loc_14000A6C0
0x14000a660  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a667  cmp     rcx, rsi
0x14000a66a  jz      loc_14000A856
0x14000a670  cmp     byte ptr [rcx+29h], 3
0x14000a674  jb      loc_14000A722
0x14000a67a  mov     rcx, [rcx+18h]
0x14000a67e  lea     r8, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x14000a685  mov     edx, 0Ch
0x14000a68a  mov     [rsp+0F0h+Src], rbx
0x14000a68f  mov     r9, rdi
0x14000a692  call    WPP_SF_qq
0x14000a697  jmp     loc_14000A722
0x14000a69c  mov     r15b, [rbp+4Fh+arg_20]
0x14000a6a0  test    r15b, r15b
0x14000a6a3  jz      short loc_14000A6FB
0x14000a6a5  mov     eax, [rbx+0CAh]
0x14000a6ab  test    eax, eax
0x14000a6ad  jz      short loc_14000A632
0x14000a6af  cmp     dword ptr [rbp+4Fh+var_58+2], eax
0x14000a6b2  jbe     loc_14000A632
0x14000a6b8  mov     r12d, 0C0000001h
0x14000a6be  jmp     short loc_14000A722
0x14000a6c0  cmp     byte ptr [rbx+182h], 0
0x14000a6c7  jz      short loc_14000A6FB
0x14000a6c9  movups  xmm0, [rbp+4Fh+Buf1]
0x14000a6cd  movups  xmm1, [rbp+4Fh+var_58]
0x14000a6d1  movups  xmm2, [rbp+4Fh+var_48]
0x14000a6d5  movups  xmmword ptr [rbx+148h], xmm0
0x14000a6dc  movups  xmmword ptr [rbx+158h], xmm1
0x14000a6e3  movups  xmmword ptr [rbx+168h], xmm2
0x14000a6ea  test    rdi, rdi
0x14000a6ed  jz      short loc_14000A6FB
0x14000a6ef  movups  xmmword ptr [rdi+50h], xmm0
0x14000a6f3  movups  xmmword ptr [rdi+60h], xmm1
0x14000a6f7  movups  xmmword ptr [rdi+70h], xmm2
0x14000a6fb  movups  xmm0, [rbp+4Fh+Buf1]
0x14000a6ff  movups  xmm1, [rbp+4Fh+var_58]
0x14000a703  movups  xmmword ptr [rbx+0B8h], xmm0
0x14000a70a  movups  xmm0, [rbp+4Fh+var_48]
0x14000a70e  movups  xmmword ptr [rbx+0C8h], xmm1
0x14000a715  movups  xmmword ptr [rbx+0D8h], xmm0
0x14000a71c  jmp     short loc_14000A722
0x14000a71e  mov     r15b, [rbp+4Fh+arg_20]
0x14000a722  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a729  cmp     rcx, rsi
0x14000a72c  jz      loc_14000A856
0x14000a732  cmp     byte ptr [rcx+29h], 4
0x14000a736  jb      short loc_14000A755
0x14000a738  mov     rcx, [rcx+18h]
0x14000a73c  lea     r8, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x14000a743  mov     edx, 0Dh
0x14000a748  mov     [rsp+0F0h+Src], rbx
0x14000a74d  mov     r9, rdi
0x14000a750  call    WPP_SF_qq
0x14000a755  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a75c  cmp     rcx, rsi
0x14000a75f  jz      loc_14000A856
0x14000a765  cmp     byte ptr [rcx+29h], 4
0x14000a769  jb      short loc_14000A7DC
0x14000a76b  mov     eax, dword ptr [rbp+4Fh+var_58+6]
0x14000a76e  movzx   edx, word ptr [rbp+4Fh+var_58]
0x14000a772  movzx   r8d, word ptr [rbp+4Fh+Buf1+0Eh]
0x14000a777  movzx   r10d, word ptr [rbp+4Fh+Buf1+0Ch]
0x14000a77c  movzx   r11d, word ptr [rbp+4Fh+Buf1+0Ah]
0x14000a781  movzx   ebx, word ptr [rbp+4Fh+Buf1+8]
0x14000a785  movzx   edi, byte ptr [rbp+4Fh+Buf1+3]
0x14000a789  movzx   esi, byte ptr [rbp+4Fh+Buf1+2]
0x14000a78d  movzx   r14d, word ptr [rbp+4Fh+Buf1]
0x14000a792  mov     rcx, [rcx+18h]
0x14000a796  mov     [rsp+0F0h+var_80], eax
0x14000a79a  mov     eax, dword ptr [rbp+4Fh+var_58+2]
0x14000a79d  mov     dword ptr [rsp+0F0h+var_88], eax
0x14000a7a1  mov     eax, dword ptr [rbp+4Fh+Buf1+4]
0x14000a7a4  mov     [rsp+0F0h+var_90], edx
0x14000a7a8  mov     [rsp+0F0h+var_98], r8d
0x14000a7ad  mov     [rsp+0F0h+var_A0], r10d
0x14000a7b2  mov     [rsp+0F0h+var_A8], r11d
0x14000a7b7  mov     [rsp+0F0h+var_B0], ebx
0x14000a7bb  mov     [rsp+0F0h+var_B8], eax
0x14000a7bf  mov     [rsp+0F0h+var_C0], edi
0x14000a7c3  mov     dword ptr [rsp+0F0h+NumberOfBytes], esi
0x14000a7c7  movzx   r9d, r15b
0x14000a7cb  mov     dword ptr [rsp+0F0h+Src], r14d
0x14000a7d0  call    WPP_SF_DDDDDDDDDDDD
0x14000a7d5  lea     rsi, WPP_GLOBAL_Control
0x14000a7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7e3  cmp     rcx, rsi
0x14000a7e6  jz      short loc_14000A856
0x14000a7e8  cmp     byte ptr [rcx+29h], 4
0x14000a7ec  jb      short loc_14000A856
0x14000a7ee  movzx   r9d, byte ptr [rbp+4Fh+var_48+4]
0x14000a7f3  mov     rax, qword ptr [rbp+4Fh+var_48+8]
0x14000a7f7  movzx   edx, word ptr [rbp+4Fh+var_48+6]
0x14000a7fb  movzx   r8d, byte ptr [rbp+4Fh+var_48+5]
0x14000a800  movzx   r10d, byte ptr [rbp+4Fh+var_48+3]
0x14000a805  movzx   r11d, byte ptr [rbp+4Fh+var_48+2]
0x14000a80a  movzx   ebx, byte ptr [rbp+4Fh+var_48+1]
0x14000a80e  movzx   edi, byte ptr [rbp+4Fh+var_48]
0x14000a812  movzx   esi, byte ptr [rbp+4Fh+var_58+0Fh]
0x14000a816  movzx   r14d, byte ptr [rbp+4Fh+var_58+0Eh]
0x14000a81b  mov     rcx, [rcx+18h]
0x14000a81f  mov     [rsp+0F0h+var_88], rax
0x14000a824  mov     [rsp+0F0h+var_90], edx
0x14000a828  mov     [rsp+0F0h+var_98], r8d
0x14000a82d  mov     [rsp+0F0h+var_A0], r9d
0x14000a832  mov     r9d, dword ptr [rbp+4Fh+var_58+0Ah]
0x14000a836  mov     [rsp+0F0h+var_A8], r10d
0x14000a83b  mov     [rsp+0F0h+var_B0], r11d
0x14000a840  mov     [rsp+0F0h+var_B8], ebx
0x14000a844  mov     [rsp+0F0h+var_C0], edi
0x14000a848  mov     dword ptr [rsp+0F0h+NumberOfBytes], esi
0x14000a84c  mov     dword ptr [rsp+0F0h+Src], r14d
0x14000a851  call    WPP_SF_DDDDDDDDDDi
0x14000a856  mov     eax, r12d
0x14000a859  mov     rcx, [rbp+4Fh+var_38]
0x14000a85d  xor     rcx, rsp; StackCookie
0x14000a860  call    __security_check_cookie
0x14000a865  add     rsp, 0C0h
0x14000a86c  pop     r15
0x14000a86e  pop     r14
0x14000a870  pop     r12
0x14000a872  pop     rdi
0x14000a873  pop     rsi
0x14000a874  pop     rbx
0x14000a875  pop     rbp
0x14000a876  retn
```
