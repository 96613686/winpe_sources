# SlbNatCreateExternalAddressWithLock

- ea: `0x14001448c`
- end: `0x1400148a5`
- name: `SlbNatCreateExternalAddressWithLock`
- size: `1049`
- prototype: `__int64 __fastcall(__int64, __int16 *, __int64, char, int)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000975c`
- `0x14003005c`
- `0x140030fe8`

## callees

- `0x1400085d0`
- `0x14000caa0`
- `0x14000d678`
- `0x14000d7f8`
- `0x140013ef0`
- `0x14001448c`
- `0x140018e40`
- `0x14001ede0`
- `0x14001f140`
- `0x14002d008`
- `0x14002d040`
- `0x14002d108`
- `0x140032f48`
- `0x1400331e8`
- `0x1400344f8`
- `0x140034638`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140014606`
- `ntoskrnl!ExAllocatePool2` at `0x140014606`

## string_xrefs

- `0x140014854`: `Create external address`

## pseudocode

```c
__int64 __fastcall SlbNatCreateExternalAddressWithLock(__int64 a1, __int16 *a2, __int64 a3, char a4, int a5)
{
  __int64 v5; // rbp
  __int64 Instance; // rsi
  __int64 v11; // rdx
  __int64 v12; // r8
  int Address; // ebx
  char v14; // r15
  char v15; // r12
  int v16; // eax
  __int64 v17; // rcx
  __int16 v18; // bx
  size_t v19; // r8
  unsigned __int8 v20; // al
  __int64 Pool2; // rax
  __int64 v22; // rcx
  __int64 v23; // rdi
  __int64 v24; // xmm1_8
  __int64 *v25; // rax
  PVOID *v26; // rcx
  _QWORD *v27; // rbx
  _DWORD *v28; // r9
  __int16 v29; // cx
  int v30; // ecx
  int v31; // eax
  _QWORD v33[4]; // [rsp+50h] [rbp-68h] BYREF

  v5 = 0;
  v33[0] = 0;
  if ( a3 )
  {
    Instance = a3;
    if ( a4 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2);
  }
  else
  {
    Instance = SlbNatFindInstance((wchar_t *)a1);
    if ( !Instance )
    {
      Address = -1073741275;
      goto LABEL_56;
    }
  }
  if ( SlbNatFindExternalAddress(Instance, *(unsigned int *)(a1 + 80)) )
  {
    Address = -1073741635;
LABEL_56:
    if ( dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
      McTemplateK0qzqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
        v11,
        v12,
        3005,
        (__int64)L"Create external address",
        0,
        Address);
    return (unsigned int)Address;
  }
  if ( *a2 != 2 && *a2 != 23 || (unsigned __int16)a2[10] > (unsigned __int16)a2[11] )
  {
    Address = -1073741811;
    goto LABEL_56;
  }
  v14 = 0;
  v15 = 4;
  if ( a3 )
  {
LABEL_23:
    Pool2 = ExAllocatePool2(256, 96, 1634029139);
    v23 = Pool2;
    if ( !Pool2 )
    {
      Address = -1073741670;
      if ( v14 )
      {
        if ( *a2 != 2 )
          v15 = 16;
        LOBYTE(v12) = v15;
        WinNatLibDeleteAddress((_DWORD)qword_1400263D8, (_DWORD)a2 + 4, v12, (unsigned __int16)a2[10], a2[11]);
      }
      goto LABEL_53;
    }
    *(_DWORD *)(Pool2 + 48) = *(_DWORD *)(a1 + 80);
    *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
    *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
    if ( *(_DWORD *)(Pool2 + 32) )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v22, v11);
    *(_OWORD *)(v23 + 52) = *(_OWORD *)a2;
    v24 = *((_QWORD *)a2 + 2);
    *(_QWORD *)(v23 + 40) = v5;
    v5 = 0;
    *(_QWORD *)(v23 + 68) = v24;
    *(_DWORD *)(v23 + 88) = a5;
    if ( (xmmword_1400262E0 & 2) != 0 )
      WPP_SF_d(1025, 10, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids, *(unsigned int *)(v23 + 56));
    if ( *(_DWORD *)(v23 + 56) )
    {
      v26 = *(PVOID **)(Instance + 32);
      if ( *v26 == (PVOID)(Instance + 24) )
      {
        *(_QWORD *)v23 = Instance + 24;
        *(_QWORD *)(v23 + 8) = v26;
        *v26 = (PVOID)v23;
        *(_QWORD *)(Instance + 32) = v23;
        ++*(_DWORD *)(Instance + 40);
        goto LABEL_38;
      }
    }
    else
    {
      v25 = (__int64 *)qword_140026360;
      v26 = &qword_140026358;
      if ( *(PVOID **)qword_140026360 == &qword_140026358 )
      {
        *(_QWORD *)v23 = &qword_140026358;
        *(_QWORD *)(v23 + 8) = v25;
        *v25 = v23;
        ++dword_140026368;
        qword_140026360 = v23;
LABEL_38:
        if ( (xmmword_1400262E0 & 2) != 0 )
          WPP_SF_(1025, 11, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids);
        v27 = *(_QWORD **)(Instance + 24);
        while ( v27 != (_QWORD *)(Instance + 24) )
        {
          v28 = v27;
          v27 = (_QWORD *)*v27;
          if ( (xmmword_1400262E0 & 2) != 0 )
            WPP_SF_ddD(v26, 12, v12, (unsigned int)v28[22], v28[12], v28[14]);
        }
        Address = 0;
        if ( (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
        {
          v29 = *(_WORD *)(v23 + 52);
          memset(v33, 0, 28);
          INETADDR_SETSOCKADDR(v29, (__int64)v33, (IN6_ADDR *)(v23 + 56), 0, 0);
          if ( dword_140026104 == 1 && (Microsoft_Windows_WinNatEnableBits & 0x10) != 0 )
          {
            v30 = 28;
            if ( LOWORD(v33[0]) == 2 )
              v30 = 16;
            McTemplateK0zqbr1hh_EtwWriteTransfer(
              (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
              (unsigned int)WINNATM_EXTERNAL_ADDRESS_ADDITION,
              v12,
              Instance + 80,
              v30,
              (__int64)v33,
              *(_WORD *)(v23 + 72),
              *(_WORD *)(v23 + 74));
          }
        }
        v31 = *(_DWORD *)(a1 + 80);
        if ( *(_DWORD *)(Instance + 256) >= (unsigned int)(v31 + 1) && v31 != -1 )
          return (unsigned int)Address;
        *(_DWORD *)(Instance + 256) = v31 + 1;
        goto LABEL_53;
      }
    }
    __fastfail(3u);
  }
  if ( a4 )
  {
    v16 = SlbNatWfpBlockExternalAddressPortRange(a2, v33);
    v5 = v33[0];
    Address = v16;
    if ( v16 < 0 )
      goto LABEL_53;
    if ( !v33[0] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v17, v11);
  }
  v18 = *a2;
  v19 = 4;
  if ( *a2 != 2 )
    v19 = 16;
  memmove(v33, a2 + 2, v19);
  v20 = 4;
  if ( v18 != 2 )
    v20 = 16;
  Address = WinNatLibCreateAddress(
              (__int64)qword_1400263D8,
              *(_QWORD *)(Instance + 16),
              1,
              a2[10],
              a2[11],
              v33,
              v20,
              0,
              0,
              0);
  if ( Address >= 0 )
  {
    v14 = 1;
    goto LABEL_23;
  }
LABEL_53:
  if ( v5 )
    SlbNatWfpUnblockExternalAddressPortRange(v5);
  if ( Address < 0 )
    goto LABEL_56;
  return (unsigned int)Address;
}

```

## disassembly

```asm
0x14001448c  mov     [rsp+arg_18], rbx
0x140014491  push    rbp
0x140014492  push    rsi
0x140014493  push    rdi
0x140014494  push    r12
0x140014496  push    r13
0x140014498  push    r14
0x14001449a  push    r15
0x14001449c  sub     rsp, 80h
0x1400144a3  mov     rax, cs:__security_cookie
0x1400144aa  xor     rax, rsp
0x1400144ad  mov     [rsp+0B8h+var_48], rax
0x1400144b2  xor     ebp, ebp
0x1400144b4  mov     dil, r9b
0x1400144b7  mov     [rsp+0B8h+var_68], rbp
0x1400144bc  mov     rbx, r8
0x1400144bf  mov     r14, rdx
0x1400144c2  mov     r13, rcx
0x1400144c5  lea     r15d, [rbp+10h]
0x1400144c9  test    r8, r8
0x1400144cc  jz      short loc_1400144F6
0x1400144ce  mov     rsi, rbx
0x1400144d1  test    r9b, r9b
0x1400144d4  jz      short loc_1400144DB
0x1400144d6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400144db  mov     edx, [r13+50h]
0x1400144df  mov     rcx, rsi
0x1400144e2  call    SlbNatFindExternalAddress
0x1400144e7  test    rax, rax
0x1400144ea  jz      short loc_14001450D
0x1400144ec  mov     ebx, 0C00000BDh
0x1400144f1  jmp     loc_14001483E
0x1400144f6  call    SlbNatFindInstance
0x1400144fb  mov     rsi, rax
0x1400144fe  test    rax, rax
0x140014501  jnz     short loc_1400144DB
0x140014503  mov     ebx, 0C0000225h
0x140014508  jmp     loc_14001483E
0x14001450d  movzx   eax, word ptr [r14]
0x140014511  cmp     ax, 2
0x140014515  jz      short loc_140014527
0x140014517  cmp     ax, 17h
0x14001451b  jz      short loc_140014527
0x14001451d  mov     ebx, 0C000000Dh
0x140014522  jmp     loc_14001483E
0x140014527  movzx   eax, word ptr [r14+16h]
0x14001452c  cmp     [r14+14h], ax
0x140014531  ja      short loc_14001451D
0x140014533  xor     r15b, r15b
0x140014536  mov     r12d, 4
0x14001453c  test    rbx, rbx
0x14001453f  jnz     loc_1400145F6
0x140014545  test    dil, dil
0x140014548  jz      short loc_140014570
0x14001454a  lea     rdx, [rsp+0B8h+var_68]
0x14001454f  mov     rcx, r14
0x140014552  call    SlbNatWfpBlockExternalAddressPortRange
0x140014557  mov     rbp, [rsp+0B8h+var_68]
0x14001455c  mov     ebx, eax
0x14001455e  test    eax, eax
0x140014560  js      loc_140014827
0x140014566  test    rbp, rbp
0x140014569  jnz     short loc_140014570
0x14001456b  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140014570  movzx   ebx, word ptr [r14]
0x140014574  lea     rdx, [r14+4]; Src
0x140014578  cmp     bx, 2
0x14001457c  lea     rcx, [rsp+0B8h+var_68]; void *
0x140014581  mov     r8, r12
0x140014584  mov     r15d, 10h
0x14001458a  cmovnz  r8, r15; Size
0x14001458e  call    memmove
0x140014593  movzx   r9d, word ptr [r14+14h]
0x140014598  mov     eax, r12d
0x14001459b  mov     rdx, [rsi+10h]
0x14001459f  cmp     bx, 2
0x1400145a3  mov     rcx, cs:qword_1400263D8
0x1400145aa  mov     r8b, 1
0x1400145ad  mov     [rsp+0B8h+var_70], 0
0x1400145b6  cmovnz  eax, r15d
0x1400145ba  mov     [rsp+0B8h+var_78], 0
0x1400145c3  mov     [rsp+0B8h+var_80], 0
0x1400145cc  mov     byte ptr [rsp+0B8h+var_88], al
0x1400145d0  lea     rax, [rsp+0B8h+var_68]
0x1400145d5  mov     [rsp+0B8h+var_90], rax
0x1400145da  movzx   eax, word ptr [r14+16h]
0x1400145df  mov     word ptr [rsp+0B8h+var_98], ax
0x1400145e4  call    WinNatLibCreateAddress
0x1400145e9  mov     ebx, eax
0x1400145eb  test    eax, eax
0x1400145ed  js      loc_14001482D
0x1400145f3  mov     r15b, 1
0x1400145f6  mov     edx, 60h ; '`'
0x1400145fb  mov     ecx, 100h
0x140014600  mov     r8d, 61654E53h
0x140014606  call    cs:__imp_ExAllocatePool2
0x14001460d  nop     dword ptr [rax+rax+00h]
0x140014612  mov     rdi, rax
0x140014615  test    rax, rax
0x140014618  jnz     short loc_14001465C
0x14001461a  mov     ebx, 0C000009Ah
0x14001461f  test    r15b, r15b
0x140014622  jz      loc_140014827
0x140014628  cmp     word ptr [r14], 2
0x14001462d  lea     r15d, [rax+10h]
0x140014631  movzx   eax, word ptr [r14+16h]
0x140014636  lea     rdx, [r14+4]
0x14001463a  movzx   r9d, word ptr [r14+14h]
0x14001463f  cmovnz  r12d, r15d
0x140014643  mov     rcx, cs:qword_1400263D8
0x14001464a  mov     r8b, r12b
0x14001464d  mov     word ptr [rsp+0B8h+var_98], ax
0x140014652  call    WinNatLibDeleteAddress
0x140014657  jmp     loc_14001482D
0x14001465c  mov     eax, [r13+50h]
0x140014660  mov     [rdi+30h], eax
0x140014663  lea     rax, [rdi+10h]
0x140014667  mov     [rax+8], rax
0x14001466b  mov     [rax], rax
0x14001466e  cmp     dword ptr [rdi+20h], 0
0x140014672  jz      short loc_140014679
0x140014674  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140014679  movups  xmm0, xmmword ptr [r14]
0x14001467d  mov     eax, [rsp+0B8h+arg_20]
0x140014684  movups  xmmword ptr [rdi+34h], xmm0
0x140014688  movsd   xmm1, qword ptr [r14+10h]
0x14001468e  mov     [rdi+28h], rbp
0x140014692  xor     ebp, ebp
0x140014694  movsd   qword ptr [rdi+44h], xmm1
0x140014699  mov     [rdi+58h], eax
0x14001469c  mov     r12w, 2
0x1400146a1  mov     ebx, 401h
0x1400146a6  test    byte ptr cs:xmmword_1400262E0, r12b
0x1400146ad  jz      short loc_1400146C4
0x1400146af  mov     r9d, [rdi+38h]
0x1400146b3  lea     edx, [rbp+0Ah]
0x1400146b6  mov     ecx, ebx
0x1400146b8  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x1400146bf  call    WPP_SF_d
0x1400146c4  cmp     [rdi+38h], ebp
0x1400146c7  jnz     short loc_1400146F5
0x1400146c9  mov     rax, cs:qword_140026360
0x1400146d0  lea     rcx, qword_140026358
0x1400146d7  cmp     [rax], rcx
0x1400146da  jnz     short loc_140014702
0x1400146dc  mov     [rdi], rcx
0x1400146df  mov     [rdi+8], rax
0x1400146e3  mov     [rax], rdi
0x1400146e6  inc     cs:dword_140026368
0x1400146ec  mov     cs:qword_140026360, rdi
0x1400146f3  jmp     short loc_14001471A
0x1400146f5  lea     rax, [rsi+18h]
0x1400146f9  mov     rcx, [rax+8]
0x1400146fd  cmp     [rcx], rax
0x140014700  jz      short loc_140014709
0x140014702  mov     ecx, 3
0x140014707  int     29h; Win8: RtlFailFast(ecx)
0x140014709  mov     [rdi], rax
0x14001470c  mov     [rdi+8], rcx
0x140014710  mov     [rcx], rdi
0x140014713  mov     [rax+8], rdi
0x140014717  inc     dword ptr [rsi+28h]
0x14001471a  test    byte ptr cs:xmmword_1400262E0, r12b
0x140014721  jz      short loc_140014736
0x140014723  mov     edx, 0Bh
0x140014728  lea     r8, WPP_8c825d3abc323f3846bedd3bd48df164_Traceguids
0x14001472f  mov     ecx, ebx
0x140014731  call    WPP_SF_
0x140014736  lea     r14, [rsi+18h]
0x14001473a  mov     rbx, [r14]
0x14001473d  jmp     short loc_14001476C
0x14001473f  lea     r9, [rbx]
0x140014742  mov     rbx, [rbx]
0x140014745  test    byte ptr cs:xmmword_1400262E0, r12b
0x14001474c  jz      short loc_14001476C
0x14001474e  mov     eax, [r9+38h]
0x140014752  mov     edx, 0Ch
0x140014757  mov     dword ptr [rsp+0B8h+var_90], eax
0x14001475b  mov     eax, [r9+30h]
0x14001475f  mov     r9d, [r9+58h]
0x140014763  mov     dword ptr [rsp+0B8h+var_98], eax
0x140014767  call    WPP_SF_ddD
0x14001476c  cmp     rbx, r14
0x14001476f  jnz     short loc_14001473F
0x140014771  xor     ebx, ebx
0x140014773  test    cs:Microsoft_Windows_WinNatEnableBits, 10h
0x14001477a  jz      loc_140014805
0x140014780  movzx   ecx, word ptr [rdi+34h]
0x140014784  lea     r8, [rdi+38h]
0x140014788  xorps   xmm0, xmm0
0x14001478b  lea     rdx, [rsp+0B8h+var_68]
0x140014790  xor     eax, eax
0x140014792  xor     r9d, r9d
0x140014795  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x14001479a  mov     word ptr [rsp+0B8h+var_98], ax
0x14001479f  movups  xmmword ptr [rsp+0B8h+var_68+0Ch], xmm0
0x1400147a4  call    INETADDR_SETSOCKADDR
0x1400147a9  cmp     cs:dword_140026104, 1
0x1400147b0  lea     r15d, [rbx+10h]
0x1400147b4  jnz     short loc_14001480B
0x1400147b6  test    cs:Microsoft_Windows_WinNatEnableBits, r15b
0x1400147bd  jz      short loc_14001480B
0x1400147bf  movzx   eax, word ptr [rdi+4Ah]
0x1400147c3  lea     ecx, [rbx+1Ch]
0x1400147c6  cmp     word ptr [rsp+0B8h+var_68], r12w
0x1400147cc  lea     r9, [rsi+50h]
0x1400147d0  mov     word ptr [rsp+0B8h+var_80], ax
0x1400147d5  lea     rdx, WINNATM_EXTERNAL_ADDRESS_ADDITION
0x1400147dc  movzx   eax, word ptr [rdi+48h]
0x1400147e0  cmovz   ecx, r15d
0x1400147e4  mov     word ptr [rsp+0B8h+var_88], ax
0x1400147e9  lea     rax, [rsp+0B8h+var_68]
0x1400147ee  mov     [rsp+0B8h+var_90], rax
0x1400147f3  mov     dword ptr [rsp+0B8h+var_98], ecx
0x1400147f7  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400147fe  call    McTemplateK0zqbr1hh_EtwWriteTransfer
0x140014803  jmp     short loc_14001480B
0x140014805  mov     r15d, 10h
0x14001480b  mov     eax, [r13+50h]
0x14001480f  lea     ecx, [rax+1]
0x140014812  cmp     [rsi+100h], ecx
0x140014818  jb      short loc_14001481F
0x14001481a  cmp     eax, 0FFFFFFFFh
0x14001481d  jnz     short loc_14001487A
0x14001481f  mov     [rsi+100h], ecx
0x140014825  jmp     short loc_14001482D
0x140014827  mov     r15d, 10h
0x14001482d  test    rbp, rbp
0x140014830  jz      short loc_14001483A
0x140014832  mov     rcx, rbp
0x140014835  call    SlbNatWfpUnblockExternalAddressPortRange
0x14001483a  test    ebx, ebx
0x14001483c  jns     short loc_14001487A
0x14001483e  cmp     cs:dword_140026104, 1
0x140014845  jnz     short loc_14001487A
0x140014847  test    cs:byte_140026BED, r15b
0x14001484e  jz      short loc_14001487A
0x140014850  mov     [rsp+0B8h+var_88], ebx
0x140014854  lea     rax, aCreateExternal; "Create external address"
0x14001485b  mov     dword ptr [rsp+0B8h+var_90], 0
0x140014863  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x14001486a  mov     r9d, 0BBDh
0x140014870  mov     [rsp+0B8h+var_98], rax
0x140014875  call    McTemplateK0qzqq_EtwWriteTransfer
0x14001487a  mov     eax, ebx
0x14001487c  mov     rcx, [rsp+0B8h+var_48]
0x140014881  xor     rcx, rsp; StackCookie
0x140014884  call    __security_check_cookie
0x140014889  mov     rbx, [rsp+0B8h+arg_18]
0x140014891  add     rsp, 80h
0x140014898  pop     r15
0x14001489a  pop     r14
0x14001489c  pop     r13
0x14001489e  pop     r12
0x1400148a0  pop     rdi
0x1400148a1  pop     rsi
0x1400148a2  pop     rbp
0x1400148a3  retn
```
