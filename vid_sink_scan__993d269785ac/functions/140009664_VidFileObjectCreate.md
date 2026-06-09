# VidFileObjectCreate

- ea: `0x140009664`
- end: `0x14000997f`
- name: `VidFileObjectCreate`
- size: `795`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x140011cd0`
- `0x140083dd0`

## callees

- `0x140008178`
- `0x140009664`
- `0x140009988`
- `0x140009d20`
- `0x1400126cc`
- `0x140013fa4`
- `0x140021650`
- `0x1400217a0`
- `0x140035400`
- `0x140038630`
- `0x140073a4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000992a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000992a`

## string_xrefs

- `0x14000979f`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x14000984d`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x1400098c2`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x1400097a6`: `VidFileObjectCreate`
- `0x140009854`: `VidFileObjectCreate`
- `0x1400098c9`: `VidFileObjectCreate`

## pseudocode

```c
__int64 __fastcall VidFileObjectCreate(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v7; // r13
  __int64 v8; // r14
  _QWORD *v9; // rsi
  _WORD *v10; // rbx
  __int64 v11; // rax
  unsigned __int64 v12; // rbx
  int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rbx
  PVOID P[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v18; // [rsp+50h] [rbp-28h]
  GUID Buf2; // [rsp+58h] [rbp-20h] BYREF

  v18 = a1;
  *(_OWORD *)P = 0;
  Buf2 = 0;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2280))(WdfDriverGlobals);
  v8 = *(char *)(v7 + 64);
  v9 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1120))(
                   WdfDriverGlobals,
                   a3);
  v10 = v9 + 11;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqqS(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)WPP_GLOBAL_Control,
      (unsigned int)WPP_7131c11f79c23006fa34e4c5742df606_Traceguids,
      v18,
      a2,
      a3,
      (char)v9,
      v9[12]);
  }
  *(_OWORD *)P = 0;
  if ( a4 && (v11 = v9[8]) != 0 )
  {
    if ( (_BYTE)v8 == 1 && !*v10 )
    {
      v12 = *(_QWORD *)(v11 + 24) & 0xFFFFFFFFFFFFFFFCuLL;
      if ( v12 )
      {
        if ( *(_DWORD *)v12 == 1853125200 )
        {
          if ( !(unsigned __int8)VidReferencePartition(*(_QWORD *)(v11 + 24) & 0xFFFFFFFFFFFFFFFCuLL) )
          {
            VidTraceErrorInternal0("VidFileObjectCreate", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 177);
            v13 = -1073741436;
            goto LABEL_37;
          }
          VidPartitionFileObjectReferenceInc(v12);
          if ( _InterlockedIncrement64((volatile signed __int64 *)(v12 + 808)) <= 1 )
            __fastfail(0xEu);
          if ( _InterlockedIncrement64((volatile signed __int64 *)(v12 + 816)) <= 1 )
            __fastfail(0xEu);
          v9[3] = v12 | 1;
          goto LABEL_18;
        }
      }
    }
    v13 = -1073741773;
  }
  else if ( !*v10 || *v10 == 2 && *(_WORD *)v9[12] == 92 )
  {
    if ( a4 )
    {
      if ( !(_BYTE)v8 )
      {
        v13 = -1073741790;
        goto LABEL_37;
      }
      v9[3] = (unsigned __int64)VidExoDeviceContext | v8;
    }
    v13 = 0;
  }
  else
  {
    v13 = VidPartitionNameParse((__int64)v10, (__int64)P, &Buf2);
    if ( v13 >= 0 )
    {
      if ( *(_BYTE *)(v7 + 64) == 1 && (v14 = VidPartitionTableLookup(VidDeviceExtension, &Buf2), (v15 = v14) != 0) )
      {
        if ( *(_DWORD *)(v14 + 8632) == 2 && *(_BYTE *)(v14 + 8657) == 1 )
        {
          VidPartitionAttach(v14);
          v9[3] = v15;
          v9[3] = v15 | *(char *)(v7 + 64);
LABEL_18:
          v13 = 0;
          goto LABEL_37;
        }
        v13 = -1073741436;
        VidTraceErrorInternal0("VidFileObjectCreate", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 262);
      }
      else
      {
        v13 = VidPartitionCreate((PCUNICODE_STRING)P, &Buf2, (__int64)v9, a2, a4);
      }
    }
    else
    {
      VidTraceErrorInternal0("VidFileObjectCreate", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 239);
    }
  }
LABEL_37:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x72446456u);
    P[1] = 0;
    LODWORD(P[0]) = 0;
  }
  return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2104))(
           WdfDriverGlobals,
           a2,
           (unsigned int)v13);
}

```

## disassembly

```asm
0x140009664  push    rbp
0x140009666  push    rbx
0x140009667  push    rsi
0x140009668  push    rdi
0x140009669  push    r12
0x14000966b  push    r13
0x14000966d  push    r14
0x14000966f  push    r15
0x140009671  mov     rbp, rsp
0x140009674  sub     rsp, 78h
0x140009678  mov     rax, cs:__security_cookie
0x14000967f  xor     rax, rsp
0x140009682  mov     [rbp+var_10], rax
0x140009686  mov     rax, cs:WdfFunctions_01015
0x14000968d  xorps   xmm0, xmm0
0x140009690  xorps   xmm1, xmm1
0x140009693  mov     [rbp+var_28], rcx
0x140009697  mov     rcx, cs:WdfDriverGlobals
0x14000969e  mov     r15b, r9b
0x1400096a1  movups  xmmword ptr [rbp+P], xmm0
0x1400096a5  mov     rdi, r8
0x1400096a8  mov     r12, rdx
0x1400096ab  movups  [rbp+Buf2], xmm1
0x1400096af  mov     rax, [rax+8E8h]
0x1400096b6  call    _guard_dispatch_icall
0x1400096bb  mov     rcx, cs:WdfFunctions_01015
0x1400096c2  mov     r13, rax
0x1400096c5  mov     rdx, rdi
0x1400096c8  movsx   r14, byte ptr [rax+40h]
0x1400096cd  mov     rax, [rcx+460h]
0x1400096d4  mov     rcx, cs:WdfDriverGlobals
0x1400096db  call    _guard_dispatch_icall
0x1400096e0  mov     rsi, rax
0x1400096e3  lea     rbx, [rax+58h]
0x1400096e7  mov     rdx, cs:WPP_GLOBAL_Control
0x1400096ee  lea     rax, WPP_GLOBAL_Control
0x1400096f5  mov     r8d, 2
0x1400096fb  cmp     rdx, rax
0x1400096fe  jz      short loc_140009740
0x140009700  mov     ecx, [rdx+2Ch]
0x140009703  test    r8b, cl
0x140009706  jz      short loc_140009740
0x140009708  cmp     byte ptr [rdx+29h], 4
0x14000970c  jb      short loc_140009740
0x14000970e  mov     rax, [rbx+8]
0x140009712  lea     r8, WPP_7131c11f79c23006fa34e4c5742df606_Traceguids
0x140009719  mov     r9, [rbp+var_28]
0x14000971d  mov     rcx, [rdx+18h]
0x140009721  mov     [rsp+78h+var_40], rax
0x140009726  mov     [rsp+78h+var_48], rsi
0x14000972b  mov     [rsp+78h+var_50], rdi
0x140009730  mov     qword ptr [rsp+78h+var_58], r12
0x140009735  call    WPP_SF_qqqqS
0x14000973a  mov     r8d, 2
0x140009740  xor     ecx, ecx
0x140009742  xorps   xmm0, xmm0
0x140009745  movups  xmmword ptr [rbp+P], xmm0
0x140009749  test    r15b, r15b
0x14000974c  jz      loc_14000980E
0x140009752  mov     rax, [rsi+40h]
0x140009756  test    rax, rax
0x140009759  jz      loc_14000980E
0x14000975f  lea     edi, [rcx+1]
0x140009762  cmp     r14b, dil
0x140009765  jnz     loc_140009804
0x14000976b  cmp     [rbx], cx
0x14000976e  jnz     loc_140009804
0x140009774  mov     rbx, [rax+18h]
0x140009778  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000977c  jz      loc_140009804
0x140009782  cmp     dword ptr [rbx], 6E747250h
0x140009788  jnz     short loc_140009804
0x14000978a  mov     rcx, rbx
0x14000978d  call    VidReferencePartition
0x140009792  xor     r14d, r14d
0x140009795  test    al, al
0x140009797  jnz     short loc_1400097BC
0x140009799  mov     r8d, 0B1h
0x14000979f  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x1400097a6  lea     rcx, aVidfileobjectc; "VidFileObjectCreate"
0x1400097ad  call    VidTraceErrorInternal0
0x1400097b2  mov     ebx, 0C0000184h
0x1400097b7  jmp     loc_14000991C
0x1400097bc  mov     rcx, rbx
0x1400097bf  call    VidPartitionFileObjectReferenceInc
0x1400097c4  mov     rax, rdi
0x1400097c7  lock xadd [rbx+328h], rax
0x1400097d0  add     rax, rdi
0x1400097d3  mov     ecx, 0Eh
0x1400097d8  cmp     rax, rdi
0x1400097db  jg      short loc_1400097DF
0x1400097dd  int     29h; Win8: RtlFailFast(ecx)
0x1400097df  mov     rax, rdi
0x1400097e2  lock xadd [rbx+330h], rax
0x1400097eb  add     rax, rdi
0x1400097ee  cmp     rax, rdi
0x1400097f1  jg      short loc_1400097F5
0x1400097f3  int     29h; Win8: RtlFailFast(ecx)
0x1400097f5  or      rbx, rdi
0x1400097f8  mov     [rsi+18h], rbx
0x1400097fc  mov     ebx, r14d
0x1400097ff  jmp     loc_14000991C
0x140009804  mov     ebx, 0C0000033h
0x140009809  jmp     loc_140009919
0x14000980e  movzx   eax, word ptr [rbx]
0x140009811  test    ax, ax
0x140009814  jz      loc_1400098F3
0x14000981a  cmp     ax, r8w
0x14000981e  jnz     short loc_14000982E
0x140009820  mov     rax, [rbx+8]
0x140009824  cmp     word ptr [rax], 5Ch ; '\'
0x140009828  jz      loc_1400098F3
0x14000982e  lea     r8, [rbp+Buf2]
0x140009832  mov     rcx, rbx
0x140009835  lea     rdx, [rbp+P]
0x140009839  call    VidPartitionNameParse
0x14000983e  xor     r14d, r14d
0x140009841  mov     ebx, eax
0x140009843  test    eax, eax
0x140009845  jns     short loc_140009865
0x140009847  mov     r8d, 0EFh
0x14000984d  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140009854  lea     rcx, aVidfileobjectc; "VidFileObjectCreate"
0x14000985b  call    VidTraceErrorInternal0
0x140009860  jmp     loc_14000991C
0x140009865  mov     edi, 1
0x14000986a  cmp     [r13+40h], dil
0x14000986e  jnz     short loc_1400098D7
0x140009870  mov     rcx, cs:VidDeviceExtension
0x140009877  lea     rdx, [rbp+Buf2]
0x14000987b  call    VidPartitionTableLookup
0x140009880  mov     rbx, rax
0x140009883  test    rax, rax
0x140009886  jz      short loc_1400098D7
0x140009888  cmp     dword ptr [rax+21B8h], 2
0x14000988f  jnz     short loc_1400098B7
0x140009891  cmp     [rax+21D1h], dil
0x140009898  jnz     short loc_1400098B7
0x14000989a  mov     rcx, rax
0x14000989d  call    VidPartitionAttach
0x1400098a2  mov     [rsi+18h], rbx
0x1400098a6  movsx   rcx, byte ptr [r13+40h]
0x1400098ab  or      rcx, rbx
0x1400098ae  mov     [rsi+18h], rcx
0x1400098b2  jmp     loc_1400097FC
0x1400098b7  mov     ebx, 0C0000184h
0x1400098bc  mov     r8d, 106h
0x1400098c2  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x1400098c9  lea     rcx, aVidfileobjectc; "VidFileObjectCreate"
0x1400098d0  call    VidTraceErrorInternal0
0x1400098d5  jmp     short loc_14000991C
0x1400098d7  mov     r9, r12
0x1400098da  mov     [rsp+78h+var_58], r15b; char
0x1400098df  mov     r8, rsi
0x1400098e2  lea     rdx, [rbp+Buf2]; Buf2
0x1400098e6  lea     rcx, [rbp+P]; SourceString
0x1400098ea  call    VidPartitionCreate
0x1400098ef  mov     ebx, eax
0x1400098f1  jmp     short loc_14000991C
0x1400098f3  test    r15b, r15b
0x1400098f6  jz      short loc_140009917
0x1400098f8  test    r14b, r14b
0x1400098fb  jnz     short loc_140009904
0x1400098fd  mov     ebx, 0C0000022h
0x140009902  jmp     short loc_140009919
0x140009904  lea     rcx, VidExoDeviceContext
0x14000990b  mov     rax, r14
0x14000990e  or      rax, rcx
0x140009911  mov     [rsi+18h], rax
0x140009915  xor     ecx, ecx
0x140009917  mov     ebx, ecx
0x140009919  xor     r14d, r14d
0x14000991c  mov     rcx, [rbp+P+8]; P
0x140009920  test    rcx, rcx
0x140009923  jz      short loc_140009941
0x140009925  mov     edx, 72446456h; Tag
0x14000992a  call    cs:__imp_ExFreePoolWithTag
0x140009931  nop     dword ptr [rax+rax+00h]
0x140009936  mov     [rbp+P+8], r14
0x14000993a  mov     dword ptr [rbp+P], 0
0x140009941  mov     rax, cs:WdfFunctions_01015
0x140009948  mov     r8d, ebx
0x14000994b  mov     rcx, cs:WdfDriverGlobals
0x140009952  mov     rdx, r12
0x140009955  mov     rax, [rax+838h]
0x14000995c  call    _guard_dispatch_icall
0x140009961  mov     rcx, [rbp+var_10]
0x140009965  xor     rcx, rsp; StackCookie
0x140009968  call    __security_check_cookie
0x14000996d  add     rsp, 78h
0x140009971  pop     r15
0x140009973  pop     r14
0x140009975  pop     r13
0x140009977  pop     r12
0x140009979  pop     rdi
0x14000997a  pop     rsi
0x14000997b  pop     rbx
0x14000997c  pop     rbp
0x14000997d  retn
```
