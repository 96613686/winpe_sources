# KeyMgrSetPortParams(MSMSEC_PORT_CONTEXT *,MSMSEC_HOST_DESC *,DOT11_MSMSEC_CONNECTION_PROFILE const *)

- ea: `0x180016f74`
- end: `0x180017331`
- name: `?KeyMgrSetPortParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUMSMSEC_HOST_DESC@@PEBUDOT11_MSMSEC_CONNECTION_PROFILE@@@Z`
- size: `957`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *, struct MSMSEC_HOST_DESC *, const struct DOT11_MSMSEC_CONNECTION_PROFILE *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800166b4`

## callees

- `0x18000431c`
- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x180016f74`
- `0x18001b020`
- `0x18001baac`
- `0x18002d554`
- `0x180064d5c`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180017025`
- `MobileNetworking!ReleaseWriteLock` at `0x180017025`
- `MobileNetworking!AcquireWriteLock` at `0x180016fe0`
- `MobileNetworking!AcquireWriteLock` at `0x180016fe0`

## pseudocode

```c
__int64 __fastcall KeyMgrSetPortParams(
        struct MSMSEC_PORT_CONTEXT *a1,
        struct MSMSEC_HOST_DESC *a2,
        const struct DOT11_MSMSEC_CONNECTION_PROFILE *a3)
{
  PVOID *v6; // rcx
  _DWORD *v7; // rdi
  __int64 v8; // r9
  int IsKeyHandshakeOffloaded; // ebx
  __int64 v10; // r9
  int v11; // r8d
  _QWORD *v12; // rcx
  int v13; // edx
  unsigned int McastCipherFromAssocParamsWPA; // eax
  unsigned int v15; // ebx
  PVOID *v16; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // ecx

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 108, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 68) & 2) != 0 )
      WPP_SF_(v6[7], 109, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids);
  }
  v7 = (_DWORD *)((char *)a1 + 1000);
  TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), ">>> Locking >>>");
  AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "KeyMgrSetPortParams", 1373);
  IsKeyHandshakeOffloaded = SecMgrIsKeyHandshakeOffloaded(*((struct MSMSEC_INTF_CONTEXT **)a1 + 3));
  TraceAdapterId(*(_DWORD *)(v8 + 2496), "<<< Unlocking <<<");
  ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "KeyMgrSetPortParams", 1377);
  *((_DWORD *)a1 + 255) = IsKeyHandshakeOffloaded;
  SetKeyMgrKeyExStatus((char *)a1 + 1000, 0);
  if ( *((_DWORD *)a3 + 4) == 1 )
  {
    v10 = **((unsigned int **)a3 + 3);
    *((_DWORD *)a1 + 251) = v10;
    v11 = *(_DWORD *)(*((_QWORD *)a3 + 3) + 4LL);
    *((_DWORD *)a1 + 252) = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      v18 = 110;
LABEL_33:
      WPP_SF_dd(v12[7], v18, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v10, v11);
    }
  }
  else
  {
    v10 = *(unsigned int *)(*((_QWORD *)a1 + 61) + 52LL);
    *((_DWORD *)a1 + 251) = v10;
    v11 = *(_DWORD *)(*((_QWORD *)a1 + 61) + 56LL);
    *((_DWORD *)a1 + 252) = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
    {
      v18 = 111;
      goto LABEL_33;
    }
  }
  v13 = *((_DWORD *)a1 + 251);
  if ( v13 == 1 )
  {
    if ( *((_DWORD *)a3 + 8) )
    {
      *v7 = 2;
      goto LABEL_43;
    }
    goto LABEL_12;
  }
  if ( *((_DWORD *)a1 + 251) == 3 || *((_DWORD *)a1 + 251) == 4 )
  {
    *v7 = 3;
    goto LABEL_43;
  }
  if ( *((_DWORD *)a1 + 251) != 6
    && *((_DWORD *)a1 + 251) != 7
    && *((_DWORD *)a1 + 251) != 8
    && *((_DWORD *)a1 + 251) != 9
    && (unsigned int)(*((_DWORD *)a1 + 251) - 10) >= 2 )
  {
LABEL_12:
    *v7 = 1;
LABEL_43:
    v20 = *((_DWORD *)a1 + 252);
    if ( v20 == 2 )
    {
      *((_BYTE *)a1 + 1184) = 1;
    }
    else if ( v20 == 4 || v20 == 8 )
    {
      *((_BYTE *)a1 + 1184) = 2;
    }
    else
    {
      *((_BYTE *)a1 + 1184) = (v20 != 257) + 1;
    }
    if ( (unsigned int)(v13 - 3) >= 2 )
    {
      v15 = 0;
      *((_DWORD *)a1 + 253) = v20;
      goto LABEL_16;
    }
    McastCipherFromAssocParamsWPA = GetMcastCipherFromAssocParamsWPA(a1, (enum _DOT11_CIPHER_ALGORITHM *)a1 + 253);
    v15 = McastCipherFromAssocParamsWPA;
    if ( !McastCipherFromAssocParamsWPA )
      goto LABEL_16;
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v15;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_18;
    v19 = 113;
LABEL_39:
    WPP_SF_d(v16[7], v19, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, McastCipherFromAssocParamsWPA);
    goto LABEL_17;
  }
  *v7 = 4;
  if ( *((_DWORD *)a1 + 252) == 2 )
    *((_BYTE *)a1 + 1184) = 1;
  else
    *((_BYTE *)a1 + 1184) = (unsigned int)(v13 - 6) > 1 ? 0 : 2;
  McastCipherFromAssocParamsWPA = GetMcastCipherFromAssocParamsRsn(
                                    a1,
                                    (enum _DOT11_CIPHER_ALGORITHM *)a1 + 253,
                                    (enum _DOT11_CIPHER_ALGORITHM *)a1 + 254);
  v15 = McastCipherFromAssocParamsWPA;
  if ( !McastCipherFromAssocParamsWPA )
    goto LABEL_16;
  if ( *((_DWORD *)a2 + 1) )
  {
    v15 = 0;
    *((_DWORD *)a1 + 253) = *((_DWORD *)a1 + 252);
LABEL_16:
    *((_DWORD *)a1 + 491) = 1;
    *((_QWORD *)a1 + 247) = 0;
    *((_QWORD *)a1 + 248) = 0;
    *((_QWORD *)a1 + 237) = 0;
    *((_QWORD *)a1 + 244) = 0;
    *((_DWORD *)a1 + 490) = 0;
    *((_DWORD *)a1 + 492) = 0;
LABEL_17:
    v16 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v15;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v19 = 112;
    goto LABEL_39;
  }
LABEL_18:
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 17) & 0x100) != 0 )
    WPP_SF_d(v16[7], 114, &WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180016f74  push    rbx
0x180016f76  push    rbp
0x180016f77  push    rsi
0x180016f78  push    rdi
0x180016f79  push    r12
0x180016f7b  push    r13
0x180016f7d  push    r14
0x180016f7f  push    r15
0x180016f81  sub     rsp, 38h
0x180016f85  mov     rbp, r8
0x180016f88  mov     r15, rdx
0x180016f8b  mov     rsi, rcx
0x180016f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f95  lea     r12, WPP_GLOBAL_Control
0x180016f9c  mov     r14d, 2
0x180016fa2  cmp     rcx, r12
0x180016fa5  jnz     loc_1800171B4
0x180016fab  mov     rcx, [rsi+18h]
0x180016faf  lea     rdx, aLocking; ">>> Locking >>>"
0x180016fb6  lea     rdi, [rsi+3E8h]
0x180016fbd  mov     ecx, [rcx+9C0h]; unsigned int
0x180016fc3  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180016fc8  mov     rcx, [rsi+18h]
0x180016fcc  lea     r8, aKeymgrsetportp; "KeyMgrSetPortParams"
0x180016fd3  mov     r9d, 55Dh
0x180016fd9  lea     rdx, [rcx+9D0h]
0x180016fe0  call    cs:__imp_AcquireWriteLock
0x180016fe7  nop     dword ptr [rax+rax+00h]
0x180016fec  mov     r9, [rsi+18h]
0x180016ff0  mov     rcx, r9; struct MSMSEC_INTF_CONTEXT *
0x180016ff3  call    ?SecMgrIsKeyHandshakeOffloaded@@YAHPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrIsKeyHandshakeOffloaded(MSMSEC_INTF_CONTEXT *)
0x180016ff8  mov     ecx, [r9+9C0h]; unsigned int
0x180016fff  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180017006  mov     ebx, eax
0x180017008  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18001700d  mov     rcx, [rsi+18h]
0x180017011  lea     r8, aKeymgrsetportp; "KeyMgrSetPortParams"
0x180017018  mov     r9d, 561h
0x18001701e  lea     rdx, [rcx+9D0h]
0x180017025  call    cs:__imp_ReleaseWriteLock
0x18001702c  nop     dword ptr [rax+rax+00h]
0x180017031  xor     edx, edx
0x180017033  mov     [rdi+14h], ebx
0x180017036  mov     rcx, rdi
0x180017039  call    ?SetKeyMgrKeyExStatus@@YAXPEAUMSMSEC_PORT_KEY_CONTEXT@@W4MSMSEC_PORT_KEY_EXCHANGE_STATUS@@@Z; SetKeyMgrKeyExStatus(MSMSEC_PORT_KEY_CONTEXT *,MSMSEC_PORT_KEY_EXCHANGE_STATUS)
0x18001703e  mov     r13d, 1
0x180017044  cmp     [rbp+10h], r13d
0x180017048  jz      loc_1800171DB
0x18001704e  mov     rax, [rsi+1E8h]
0x180017055  mov     r9d, [rax+34h]
0x180017059  mov     [rdi+4], r9d
0x18001705d  mov     rax, [rsi+1E8h]
0x180017064  mov     r8d, [rax+38h]
0x180017068  mov     [rdi+8], r8d
0x18001706c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017073  cmp     rcx, r12
0x180017076  jnz     loc_180017213
0x18001707c  mov     edx, [rdi+4]
0x18001707f  xor     r12d, r12d
0x180017082  mov     ecx, edx
0x180017084  sub     ecx, r13d
0x180017087  jz      loc_18001729D
0x18001708d  sub     ecx, r14d
0x180017090  jz      loc_180017295
0x180017096  sub     ecx, r13d
0x180017099  jz      loc_180017295
0x18001709f  sub     ecx, r14d
0x1800170a2  jz      short loc_1800170C5
0x1800170a4  sub     ecx, r13d
0x1800170a7  jz      short loc_1800170C5
0x1800170a9  sub     ecx, r13d
0x1800170ac  jz      short loc_1800170C5
0x1800170ae  sub     ecx, r13d
0x1800170b1  jz      short loc_1800170C5
0x1800170b3  sub     ecx, r13d
0x1800170b6  jz      short loc_1800170C5
0x1800170b8  cmp     ecx, r13d
0x1800170bb  jz      short loc_1800170C5
0x1800170bd  mov     [rdi], r13d
0x1800170c0  jmp     loc_1800172AA
0x1800170c5  mov     dword ptr [rdi], 4
0x1800170cb  cmp     [rdi+8], r14d
0x1800170cf  jnz     short loc_18001714A
0x1800170d1  mov     [rdi+0B8h], r13b
0x1800170d8  lea     r8, [rdi+10h]; enum _DOT11_CIPHER_ALGORITHM *
0x1800170dc  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x1800170df  lea     rdx, [rdi+0Ch]; enum _DOT11_CIPHER_ALGORITHM *
0x1800170e3  call    ?GetMcastCipherFromAssocParamsRsn@@YAKPEBUMSMSEC_PORT_CONTEXT@@PEAW4_DOT11_CIPHER_ALGORITHM@@1@Z; GetMcastCipherFromAssocParamsRsn(MSMSEC_PORT_CONTEXT const *,_DOT11_CIPHER_ALGORITHM *,_DOT11_CIPHER_ALGORITHM *)
0x1800170e8  mov     ebx, eax
0x1800170ea  test    eax, eax
0x1800170ec  jnz     loc_18001723C
0x1800170f2  mov     [rsi+7ACh], r13d
0x1800170f9  lea     rdi, WPP_GLOBAL_Control
0x180017100  mov     [rsi+7B8h], r12
0x180017107  mov     [rsi+7C0h], r12
0x18001710e  mov     [rsi+768h], r12
0x180017115  mov     [rsi+7A0h], r12
0x18001711c  mov     [rsi+7A8h], r12d
0x180017123  mov     [rsi+7B0h], r12d
0x18001712a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017131  cmp     rcx, rdi
0x180017134  jnz     short loc_180017164
0x180017136  mov     eax, ebx
0x180017138  add     rsp, 38h
0x18001713c  pop     r15
0x18001713e  pop     r14
0x180017140  pop     r13
0x180017142  pop     r12
0x180017144  pop     rdi
0x180017145  pop     rsi
0x180017146  pop     rbp
0x180017147  pop     rbx
0x180017148  retn
0x18001714a  lea     eax, [rdx-6]
0x18001714d  cmp     eax, r13d
0x180017150  setnbe  al
0x180017153  sub     al, r13b
0x180017156  and     al, r14b
0x180017159  mov     [rdi+0B8h], al
0x18001715f  jmp     loc_1800170D8
0x180017164  test    dword ptr [rcx+44h], 100h
0x18001716b  jz      short loc_180017136
0x18001716d  mov     rcx, [rcx+38h]
0x180017171  lea     r8, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x180017178  mov     edx, 72h ; 'r'
0x18001717d  mov     r9d, ebx
0x180017180  call    WPP_SF_d
0x180017185  jmp     short loc_180017136
0x180017187  cmp     rcx, r12
0x18001718a  jz      loc_180016FAB
0x180017190  test    [rcx+44h], r14b
0x180017194  jz      loc_180016FAB
0x18001719a  mov     rcx, [rcx+38h]
0x18001719e  lea     r8, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x1800171a5  mov     edx, 6Dh ; 'm'
0x1800171aa  call    WPP_SF_
0x1800171af  jmp     loc_180016FAB
0x1800171b4  test    dword ptr [rcx+44h], 100h
0x1800171bb  jz      short loc_180017187
0x1800171bd  mov     rcx, [rcx+38h]
0x1800171c1  lea     r8, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x1800171c8  mov     edx, 6Ch ; 'l'
0x1800171cd  call    WPP_SF_
0x1800171d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171d9  jmp     short loc_180017187
0x1800171db  mov     rax, [rbp+18h]
0x1800171df  mov     r9d, [rax]
0x1800171e2  mov     [rdi+4], r9d
0x1800171e6  mov     rax, [rbp+18h]
0x1800171ea  mov     r8d, [rax+4]
0x1800171ee  mov     [rdi+8], r8d
0x1800171f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800171f9  cmp     rcx, r12
0x1800171fc  jz      loc_18001707C
0x180017202  test    [rcx+44h], r14b
0x180017206  jz      loc_18001707C
0x18001720c  mov     edx, 6Eh ; 'n'
0x180017211  jmp     short loc_180017222
0x180017213  test    [rcx+44h], r14b
0x180017217  jz      loc_18001707C
0x18001721d  mov     edx, 6Fh ; 'o'
0x180017222  mov     rcx, [rcx+38h]
0x180017226  mov     [rsp+78h+var_58], r8d
0x18001722b  lea     r8, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x180017232  call    WPP_SF_dd
0x180017237  jmp     loc_18001707C
0x18001723c  cmp     [r15+4], r12d
0x180017240  jz      short loc_180017250
0x180017242  mov     eax, [rdi+8]
0x180017245  mov     ebx, r12d
0x180017248  mov     [rdi+0Ch], eax
0x18001724b  jmp     loc_1800170F2
0x180017250  mov     rcx, cs:WPP_GLOBAL_Control
0x180017257  lea     rdi, WPP_GLOBAL_Control
0x18001725e  cmp     rcx, rdi
0x180017261  jz      loc_180017136
0x180017267  test    [rcx+44h], r13b
0x18001726b  jz      loc_180017131
0x180017271  mov     edx, 70h ; 'p'
0x180017276  jmp     short loc_18001727D
0x180017278  mov     edx, 71h ; 'q'
0x18001727d  mov     rcx, [rcx+38h]
0x180017281  lea     r8, WPP_9d4f9556006c3610c238b9c0f997e02f_Traceguids
0x180017288  mov     r9d, eax
0x18001728b  call    WPP_SF_d
0x180017290  jmp     loc_18001712A
0x180017295  mov     dword ptr [rdi], 3
0x18001729b  jmp     short loc_1800172AA
0x18001729d  cmp     [rbp+20h], r12d
0x1800172a1  jz      loc_1800170BD
0x1800172a7  mov     [rdi], r14d
0x1800172aa  mov     ecx, [rdi+8]
0x1800172ad  cmp     ecx, r14d
0x1800172b0  jz      short loc_1800172D9
0x1800172b2  cmp     ecx, 4
0x1800172b5  jz      short loc_1800172D0
0x1800172b7  cmp     ecx, 8
0x1800172ba  jz      short loc_1800172D0
0x1800172bc  cmp     ecx, 101h
0x1800172c2  setnz   al
0x1800172c5  add     al, r13b
0x1800172c8  mov     [rdi+0B8h], al
0x1800172ce  jmp     short loc_1800172E0
0x1800172d0  mov     [rdi+0B8h], r14b
0x1800172d7  jmp     short loc_1800172E0
0x1800172d9  mov     [rdi+0B8h], r13b
0x1800172e0  sub     edx, 3
0x1800172e3  jz      short loc_1800172F5
0x1800172e5  cmp     edx, r13d
0x1800172e8  jz      short loc_1800172F5
0x1800172ea  mov     ebx, r12d
0x1800172ed  mov     [rdi+0Ch], ecx
0x1800172f0  jmp     loc_1800170F2
0x1800172f5  lea     rdx, [rdi+0Ch]; enum _DOT11_CIPHER_ALGORITHM *
0x1800172f9  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x1800172fc  call    ?GetMcastCipherFromAssocParamsWPA@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAW4_DOT11_CIPHER_ALGORITHM@@@Z; GetMcastCipherFromAssocParamsWPA(MSMSEC_PORT_CONTEXT *,_DOT11_CIPHER_ALGORITHM *)
0x180017301  mov     ebx, eax
0x180017303  test    eax, eax
0x180017305  jz      loc_1800170F2
0x18001730b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017312  lea     rdi, WPP_GLOBAL_Control
0x180017319  cmp     rcx, rdi
0x18001731c  jz      loc_180017136
0x180017322  test    [rcx+44h], r13b
0x180017326  jz      loc_180017131
0x18001732c  jmp     loc_180017278
```
