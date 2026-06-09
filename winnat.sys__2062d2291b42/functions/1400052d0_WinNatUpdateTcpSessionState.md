# WinNatUpdateTcpSessionState

- ea: `0x1400052d0`
- end: `0x14000570e`
- name: `WinNatUpdateTcpSessionState`
- size: `1086`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140004ed0`

## callees

- `0x1400052d0`
- `0x14001a0c8`
- `0x14001b050`
- `0x14001f320`

## pseudocode

```c
unsigned __int64 __fastcall WinNatUpdateTcpSessionState(__int64 a1, char a2, char a3)
{
  unsigned __int64 result; // rax
  int v5; // edx
  bool v7; // r10
  char v9; // r11
  int v10; // r9d
  int v11; // r8d
  __int16 *v12; // rcx
  int v13; // r8d
  char v14; // dl
  int v15; // r9d
  int v16; // ecx
  __int16 v17[16]; // [rsp+70h] [rbp-A8h] BYREF
  __int16 v18[16]; // [rsp+90h] [rbp-88h] BYREF
  __int16 v19[16]; // [rsp+B0h] [rbp-68h] BYREF
  __int16 v20[16]; // [rsp+D0h] [rbp-48h] BYREF

  result = *(int *)(a1 + 248);
  v5 = a2 & 2;
  v7 = v5 != 0;
  v9 = a2 & 1;
  v10 = a2 & 4;
  if ( (_DWORD)result == 3 )
  {
    if ( v9 )
    {
      result = 5 - (unsigned int)(a3 != 0);
      *(_DWORD *)(a1 + 248) = result;
      goto LABEL_7;
    }
    if ( v10 )
    {
      v11 = *(_DWORD *)(a1 + 124);
      *(_DWORD *)(a1 + 248) = 7;
    }
    else
    {
      v11 = *(_DWORD *)(a1 + 128);
    }
  }
  else
  {
    v11 = 0;
    switch ( (int)result )
    {
      case 0:
        if ( v5 )
        {
          if ( a3 )
          {
            v11 = *(_DWORD *)(a1 + 124);
            result = 1;
          }
          else
          {
            v11 = 6;
            if ( *(_DWORD *)(*(_QWORD *)(a1 + 80) + 112LL) != 1 )
              v11 = *(_DWORD *)(a1 + 124);
            result = 2;
          }
          *(_DWORD *)(a1 + 248) = result;
          break;
        }
        if ( v9 || v10 )
          goto LABEL_7;
        if ( a3 )
        {
          if ( !*(_BYTE *)(a1 + 258) )
          {
            *(_BYTE *)(a1 + 257) = 1;
            goto LABEL_7;
          }
          v7 = 1;
        }
        else
        {
          if ( !*(_BYTE *)(a1 + 257) )
          {
            *(_BYTE *)(a1 + 258) = 1;
            goto LABEL_7;
          }
          v7 = 1;
        }
LABEL_37:
        *(_DWORD *)(a1 + 248) = 3;
        goto LABEL_38;
      case 1:
        if ( !v5 )
          break;
        if ( !a3 )
          goto LABEL_37;
        goto LABEL_45;
      case 2:
        if ( !v5 || !a3 )
          break;
        goto LABEL_37;
      case 4:
        if ( !v9 || a3 )
          goto LABEL_46;
        v11 = *(_DWORD *)(a1 + 124);
        *(_DWORD *)(a1 + 248) = 6;
        break;
      case 5:
        if ( v9 && a3 )
        {
          *(_DWORD *)(a1 + 248) = 6;
LABEL_45:
          v11 = *(_DWORD *)(a1 + 124);
        }
        else
        {
LABEL_46:
          if ( v10 )
          {
            v11 = *(_DWORD *)(a1 + 124);
            *(_DWORD *)(a1 + 248) = 7;
          }
          else
          {
LABEL_38:
            v11 = *(_DWORD *)(a1 + 128);
          }
        }
        break;
      case 6:
        if ( v5 )
        {
          if ( a3 )
          {
            v11 = *(_DWORD *)(a1 + 124);
            *(_DWORD *)(a1 + 248) = 1;
          }
          else
          {
            result = *(_QWORD *)(a1 + 80);
            v11 = 6;
            if ( *(_DWORD *)(result + 112) != 1 )
              v11 = *(_DWORD *)(a1 + 124);
            *(_DWORD *)(a1 + 248) = 2;
          }
        }
        break;
      case 7:
        if ( v10 )
          goto LABEL_7;
        v11 = *(_DWORD *)(a1 + 128);
        *(_DWORD *)(a1 + 248) = 3;
        break;
      default:
        goto LABEL_7;
    }
  }
  if ( v11 )
  {
    result = 0x624DD2F1A9FBE77LL * (MEMORY[0xFFFFF78000000008] / 0x2710uLL);
    *(_DWORD *)(a1 + 136) = v11 + MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
  }
LABEL_7:
  if ( (v7 || v9 || v10) && (Microsoft_Windows_WinNatEnableBits & 1) != 0 )
  {
    if ( dword_140027104 )
    {
      v12 = *(__int16 **)(a1 + 88);
      memset(v18, 0, 28);
      memset(v20, 0, 28);
      memset(v17, 0, 28);
      memset(v19, 0, 28);
      WinNatCopyTransportAddrToSockAddr(v12, v18);
      WinNatCopyTransportAddrToSockAddr(*(__int16 **)(a1 + 96), v20);
      WinNatCopyTransportAddrToSockAddr(*(__int16 **)(a1 + 104), v17);
      result = (unsigned __int64)WinNatCopyTransportAddrToSockAddr(*(__int16 **)(a1 + 112), v19);
      if ( dword_140027104 == 1 && (Microsoft_Windows_WinNatEnableBits & 1) != 0 )
      {
        if ( (*(_BYTE *)(a1 + 132) & 1) != 0 )
          v14 = 0;
        else
          v14 = *(_DWORD *)(a1 + 136) - MEMORY[0xFFFFF78000000008] / 0x2710uLL / 0x3E8;
        v15 = 28;
        v16 = 28;
        if ( v17[0] == 2 )
          v16 = 16;
        if ( v18[0] == 2 )
          v15 = 16;
        return McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer(
                 (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
                 (unsigned int)WINNAT_SESSION_TCPSTATE_UPDATE,
                 v13,
                 v15,
                 (__int64)v18,
                 (__int64)v20,
                 v16,
                 (__int64)v17,
                 (__int64)v19,
                 *(_DWORD *)(a1 + 120),
                 v14,
                 *(_DWORD *)(a1 + 248),
                 *(_DWORD *)(a1 + 8));
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400052d0  mov     [rsp+arg_18], rbx
0x1400052d5  push    rbp
0x1400052d6  push    r14
0x1400052d8  push    r15
0x1400052da  sub     rsp, 100h
0x1400052e1  mov     rax, cs:__security_cookie
0x1400052e8  xor     rax, rsp
0x1400052eb  mov     [rsp+118h+var_28], rax
0x1400052f3  movsxd  rax, dword ptr [rcx+0F8h]
0x1400052fa  mov     r9d, edx
0x1400052fd  and     edx, 2
0x140005300  mov     [rsp+118h+arg_10], rdi
0x140005308  movzx   r11d, r9b
0x14000530c  movzx   edi, r8b
0x140005310  setnz   r10b
0x140005314  mov     rbx, rcx
0x140005317  and     r11b, 1
0x14000531b  and     r9d, 4
0x14000531f  mov     rbp, 346DC5D63886594Bh
0x140005329  mov     r15, 0FFFFF78000000008h
0x140005333  mov     r14, 624DD2F1A9FBE77h
0x14000533d  cmp     eax, 3
0x140005340  jnz     loc_140005497
0x140005346  test    r11b, r11b
0x140005349  jnz     loc_1400054CA
0x14000534f  test    r9d, r9d
0x140005352  jz      loc_14000564A
0x140005358  mov     r8d, [rcx+7Ch]
0x14000535c  mov     dword ptr [rcx+0F8h], 7
0x140005366  test    r8d, r8d
0x140005369  jz      short def_1400054C4; jumptable 00000001400054C4 default case, case 3
0x14000536b  mov     rcx, [r15]
0x14000536e  mov     rax, rbp
0x140005371  mul     rcx
0x140005374  mov     rax, r14
0x140005377  mov     rcx, rdx
0x14000537a  shr     rcx, 0Bh
0x14000537e  mul     rcx
0x140005381  sub     rcx, rdx
0x140005384  shr     rcx, 1
0x140005387  add     rcx, rdx
0x14000538a  shr     rcx, 9
0x14000538e  add     ecx, r8d
0x140005391  mov     [rbx+88h], ecx
0x140005397  mov     rdi, [rsp+118h+arg_10]; jumptable 00000001400054C4 default case, case 3
0x14000539f  test    r10b, r10b
0x1400053a2  jnz     short loc_1400053D4
0x1400053a4  test    r11b, r11b
0x1400053a7  jnz     short loc_1400053D4
0x1400053a9  test    r9d, r9d
0x1400053ac  jnz     short loc_1400053D4
0x1400053ae  mov     rcx, [rsp+118h+var_28]
0x1400053b6  xor     rcx, rsp; StackCookie
0x1400053b9  call    __security_check_cookie
0x1400053be  mov     rbx, [rsp+118h+arg_18]
0x1400053c6  add     rsp, 100h
0x1400053cd  pop     r15
0x1400053cf  pop     r14
0x1400053d1  pop     rbp
0x1400053d2  retn
0x1400053d4  test    cs:Microsoft_Windows_WinNatEnableBits, 1
0x1400053db  jz      short loc_1400053AE
0x1400053dd  cmp     cs:dword_140027104, 0
0x1400053e4  jz      short loc_1400053AE
0x1400053e6  mov     rcx, [rbx+58h]
0x1400053ea  lea     rdx, [rsp+118h+var_88]
0x1400053f2  xorps   xmm0, xmm0
0x1400053f5  xorps   xmm1, xmm1
0x1400053f8  movups  xmmword ptr [rsp+118h+var_88], xmm0
0x140005400  xor     eax, eax
0x140005402  movups  xmmword ptr [rsp+118h+var_48], xmm1
0x14000540a  movups  xmmword ptr [rsp+118h+var_A8], xmm0
0x14000540f  movups  xmmword ptr [rsp+118h+var_68], xmm1
0x140005417  movups  xmmword ptr [rsp+118h+var_88+0Ch], xmm0
0x14000541f  movups  xmmword ptr [rsp+118h+var_48+0Ch], xmm1
0x140005427  movups  xmmword ptr [rsp+118h+var_A8+0Ch], xmm0
0x14000542c  movups  xmmword ptr [rsp+118h+var_68+0Ch], xmm1
0x140005434  call    WinNatCopyTransportAddrToSockAddr
0x140005439  mov     rcx, [rbx+60h]
0x14000543d  lea     rdx, [rsp+118h+var_48]
0x140005445  call    WinNatCopyTransportAddrToSockAddr
0x14000544a  mov     rcx, [rbx+68h]
0x14000544e  lea     rdx, [rsp+118h+var_A8]
0x140005453  call    WinNatCopyTransportAddrToSockAddr
0x140005458  mov     rcx, [rbx+70h]
0x14000545c  lea     rdx, [rsp+118h+var_68]
0x140005464  call    WinNatCopyTransportAddrToSockAddr
0x140005469  cmp     cs:dword_140027104, 1
0x140005470  jnz     loc_1400053AE
0x140005476  test    cs:Microsoft_Windows_WinNatEnableBits, 1
0x14000547d  jz      loc_1400053AE
0x140005483  test    byte ptr [rbx+84h], 1
0x14000548a  jz      loc_140005656
0x140005490  xor     edx, edx
0x140005492  jmp     loc_140005681
0x140005497  cmp     eax, 7; switch 8 cases
0x14000549a  ja      def_1400054C4; jumptable 00000001400054C4 default case, case 3
0x1400054a0  mov     [rsp+118h+arg_8], rsi
0x1400054a8  xor     r8d, r8d
0x1400054ab  lea     rsi, cs:140000000h
0x1400054b2  mov     ecx, ds:(jpt_1400054C4 - 140000000h)[rsi+rax*4]
0x1400054b9  add     rcx, rsi
0x1400054bc  mov     rsi, [rsp+118h+arg_8]
0x1400054c4  jmp     rcx; switch jump
0x1400054ca  neg     dil
0x1400054cd  sbb     eax, eax
0x1400054cf  add     eax, 5
0x1400054d2  mov     [rcx+0F8h], eax
0x1400054d8  jmp     def_1400054C4; jumptable 00000001400054C4 default case, case 3
0x1400054dd  test    edx, edx; jumptable 00000001400054C4 case 0
0x1400054df  jz      short loc_140005515
0x1400054e1  test    dil, dil
0x1400054e4  jz      short loc_1400054F1
0x1400054e6  mov     r8d, [rbx+7Ch]
0x1400054ea  mov     eax, 1
0x1400054ef  jmp     short loc_14000550A
0x1400054f1  mov     rax, [rbx+50h]
0x1400054f5  mov     r8d, 6
0x1400054fb  cmp     dword ptr [rax+70h], 1
0x1400054ff  jz      short loc_140005505
0x140005501  mov     r8d, [rbx+7Ch]
0x140005505  mov     eax, 2
0x14000550a  mov     [rbx+0F8h], eax
0x140005510  jmp     loc_140005366
0x140005515  test    r11b, r11b
0x140005518  jnz     def_1400054C4; jumptable 00000001400054C4 default case, case 3
0x14000551e  test    r9d, r9d
0x140005521  jnz     def_1400054C4; jumptable 00000001400054C4 default case, case 3
0x140005527  test    dil, dil
0x14000552a  jz      short loc_140005546
0x14000552c  cmp     [rbx+102h], r8b
0x140005533  jz      short loc_14000553A
0x140005535  mov     r10b, 1
0x140005538  jmp     short loc_140005571
0x14000553a  mov     byte ptr [rbx+101h], 1
0x140005541  jmp     def_1400054C4; jumptable 00000001400054C4 default case, case 3
0x140005546  cmp     [rbx+101h], r8b
0x14000554d  jz      short loc_140005554
0x14000554f  mov     r10b, 1
0x140005552  jmp     short loc_140005571
0x140005554  mov     byte ptr [rbx+102h], 1
0x14000555b  jmp     def_1400054C4; jumptable 00000001400054C4 default case, case 3
0x140005560  test    edx, edx; jumptable 00000001400054C4 case 2
0x140005562  jz      loc_140005366
0x140005568  test    dil, dil
0x14000556b  jz      loc_140005366
0x140005571  mov     dword ptr [rbx+0F8h], 3
0x14000557b  mov     r8d, [rbx+80h]
0x140005582  jmp     loc_140005366
0x140005587  test    edx, edx; jumptable 00000001400054C4 case 1
0x140005589  jz      loc_140005366
0x14000558f  test    dil, dil
0x140005592  jnz     short loc_1400055AA
0x140005594  jmp     short loc_140005571
0x140005596  test    r11b, r11b; jumptable 00000001400054C4 case 5
0x140005599  jz      short loc_1400055B3
0x14000559b  test    dil, dil
0x14000559e  jz      short loc_1400055B3
0x1400055a0  mov     dword ptr [rbx+0F8h], 6
0x1400055aa  mov     r8d, [rbx+7Ch]
0x1400055ae  jmp     loc_140005366
0x1400055b3  test    r9d, r9d
0x1400055b6  jz      short loc_14000557B
0x1400055b8  mov     r8d, [rbx+7Ch]
0x1400055bc  mov     dword ptr [rbx+0F8h], 7
0x1400055c6  jmp     loc_140005366
0x1400055cb  test    r11b, r11b; jumptable 00000001400054C4 case 4
0x1400055ce  jz      short loc_1400055B3
0x1400055d0  test    dil, dil
0x1400055d3  jnz     short loc_1400055B3
0x1400055d5  mov     r8d, [rbx+7Ch]
0x1400055d9  mov     dword ptr [rbx+0F8h], 6
0x1400055e3  jmp     loc_140005366
0x1400055e8  test    edx, edx; jumptable 00000001400054C4 case 6
0x1400055ea  jz      loc_140005366
0x1400055f0  test    dil, dil
0x1400055f3  jz      short loc_140005608
0x1400055f5  mov     r8d, [rbx+7Ch]
0x1400055f9  mov     dword ptr [rbx+0F8h], 1
0x140005603  jmp     loc_140005366
0x140005608  mov     rax, [rbx+50h]
0x14000560c  mov     r8d, 6
0x140005612  cmp     dword ptr [rax+70h], 1
0x140005616  jz      short loc_14000561C
0x140005618  mov     r8d, [rbx+7Ch]
0x14000561c  mov     dword ptr [rbx+0F8h], 2
0x140005626  jmp     loc_140005366
0x14000562b  test    r9d, r9d; jumptable 00000001400054C4 case 7
0x14000562e  jnz     def_1400054C4; jumptable 00000001400054C4 default case, case 3
0x140005634  mov     r8d, [rbx+80h]
0x14000563b  mov     dword ptr [rbx+0F8h], 3
0x140005645  jmp     loc_140005366
0x14000564a  mov     r8d, [rcx+80h]
0x140005651  jmp     loc_140005366
0x140005656  mov     rcx, [r15]
0x140005659  mov     rax, rbp
0x14000565c  mul     rcx
0x14000565f  mov     rax, r14
0x140005662  mov     rcx, rdx
0x140005665  shr     rcx, 0Bh
0x140005669  mul     rcx
0x14000566c  sub     rcx, rdx
0x14000566f  shr     rcx, 1
0x140005672  add     rcx, rdx
0x140005675  mov     edx, [rbx+88h]
0x14000567b  shr     rcx, 9
0x14000567f  sub     edx, ecx
0x140005681  cmp     [rsp+118h+var_A8], 2
0x140005687  mov     eax, 10h
0x14000568c  mov     r9d, 1Ch
0x140005692  mov     ecx, r9d
0x140005695  cmovz   ecx, eax
0x140005698  cmp     [rsp+118h+var_88], 2
0x1400056a1  cmovz   r9d, eax
0x1400056a5  mov     eax, [rbx+8]
0x1400056a8  mov     [rsp+118h+var_B8], eax
0x1400056ac  mov     eax, [rbx+0F8h]
0x1400056b2  mov     [rsp+118h+var_C0], eax
0x1400056b6  mov     eax, [rbx+78h]
0x1400056b9  mov     [rsp+118h+var_C8], edx
0x1400056bd  lea     rdx, WINNAT_SESSION_TCPSTATE_UPDATE
0x1400056c4  mov     [rsp+118h+var_D0], eax
0x1400056c8  lea     rax, [rsp+118h+var_68]
0x1400056d0  mov     [rsp+118h+var_D8], rax
0x1400056d5  lea     rax, [rsp+118h+var_A8]
0x1400056da  mov     [rsp+118h+var_E0], rax
0x1400056df  lea     rax, [rsp+118h+var_48]
0x1400056e7  mov     [rsp+118h+var_E8], ecx
0x1400056eb  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400056f2  mov     [rsp+118h+var_F0], rax
0x1400056f7  lea     rax, [rsp+118h+var_88]
0x1400056ff  mov     [rsp+118h+var_F8], rax
0x140005704  call    McTemplateK0qbr0br0qbr3br3qqqq_EtwWriteTransfer
0x140005709  jmp     loc_1400053AE
```
