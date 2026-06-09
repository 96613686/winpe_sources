# VidFileObjectCreate

- ea: `0x140009194`
- end: `0x1400094af`
- name: `VidFileObjectCreate`
- size: `795`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x140011b20`
- `0x140084f50`

## callees

- `0x140007898`
- `0x140009194`
- `0x1400094b8`
- `0x140009850`
- `0x140012524`
- `0x140013df4`
- `0x140021c60`
- `0x140021db0`
- `0x140035470`
- `0x1400386a0`
- `0x14007496c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000945a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000945a`

## string_xrefs

- `0x1400092cf`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x14000937d`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x1400093f2`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x1400092d6`: `VidFileObjectCreate`
- `0x140009384`: `VidFileObjectCreate`
- `0x1400093f9`: `VidFileObjectCreate`

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
  __int128 Buf2; // [rsp+58h] [rbp-20h] BYREF

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
      (unsigned int)WPP_aa41be93fb723da9ffb444b0ddb124c7_Traceguids,
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
    v13 = VidPartitionNameParse(v10, P, &Buf2);
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
0x140009194  push    rbp
0x140009196  push    rbx
0x140009197  push    rsi
0x140009198  push    rdi
0x140009199  push    r12
0x14000919b  push    r13
0x14000919d  push    r14
0x14000919f  push    r15
0x1400091a1  mov     rbp, rsp
0x1400091a4  sub     rsp, 78h
0x1400091a8  mov     rax, cs:__security_cookie
0x1400091af  xor     rax, rsp
0x1400091b2  mov     [rbp+var_10], rax
0x1400091b6  mov     rax, cs:WdfFunctions_01015
0x1400091bd  xorps   xmm0, xmm0
0x1400091c0  xorps   xmm1, xmm1
0x1400091c3  mov     [rbp+var_28], rcx
0x1400091c7  mov     rcx, cs:WdfDriverGlobals
0x1400091ce  mov     r15b, r9b
0x1400091d1  movups  xmmword ptr [rbp+P], xmm0
0x1400091d5  mov     rdi, r8
0x1400091d8  mov     r12, rdx
0x1400091db  movups  [rbp+Buf2], xmm1
0x1400091df  mov     rax, [rax+8E8h]
0x1400091e6  call    _guard_dispatch_icall
0x1400091eb  mov     rcx, cs:WdfFunctions_01015
0x1400091f2  mov     r13, rax
0x1400091f5  mov     rdx, rdi
0x1400091f8  movsx   r14, byte ptr [rax+40h]
0x1400091fd  mov     rax, [rcx+460h]
0x140009204  mov     rcx, cs:WdfDriverGlobals
0x14000920b  call    _guard_dispatch_icall
0x140009210  mov     rsi, rax
0x140009213  lea     rbx, [rax+58h]
0x140009217  mov     rdx, cs:WPP_GLOBAL_Control
0x14000921e  lea     rax, WPP_GLOBAL_Control
0x140009225  mov     r8d, 2
0x14000922b  cmp     rdx, rax
0x14000922e  jz      short loc_140009270
0x140009230  mov     ecx, [rdx+2Ch]
0x140009233  test    r8b, cl
0x140009236  jz      short loc_140009270
0x140009238  cmp     byte ptr [rdx+29h], 4
0x14000923c  jb      short loc_140009270
0x14000923e  mov     rax, [rbx+8]
0x140009242  lea     r8, WPP_aa41be93fb723da9ffb444b0ddb124c7_Traceguids
0x140009249  mov     r9, [rbp+var_28]
0x14000924d  mov     rcx, [rdx+18h]
0x140009251  mov     [rsp+78h+var_40], rax
0x140009256  mov     [rsp+78h+var_48], rsi
0x14000925b  mov     [rsp+78h+var_50], rdi
0x140009260  mov     qword ptr [rsp+78h+var_58], r12
0x140009265  call    WPP_SF_qqqqS
0x14000926a  mov     r8d, 2
0x140009270  xor     ecx, ecx
0x140009272  xorps   xmm0, xmm0
0x140009275  movups  xmmword ptr [rbp+P], xmm0
0x140009279  test    r15b, r15b
0x14000927c  jz      loc_14000933E
0x140009282  mov     rax, [rsi+40h]
0x140009286  test    rax, rax
0x140009289  jz      loc_14000933E
0x14000928f  lea     edi, [rcx+1]
0x140009292  cmp     r14b, dil
0x140009295  jnz     loc_140009334
0x14000929b  cmp     [rbx], cx
0x14000929e  jnz     loc_140009334
0x1400092a4  mov     rbx, [rax+18h]
0x1400092a8  and     rbx, 0FFFFFFFFFFFFFFFCh
0x1400092ac  jz      loc_140009334
0x1400092b2  cmp     dword ptr [rbx], 6E747250h
0x1400092b8  jnz     short loc_140009334
0x1400092ba  mov     rcx, rbx
0x1400092bd  call    VidReferencePartition
0x1400092c2  xor     r14d, r14d
0x1400092c5  test    al, al
0x1400092c7  jnz     short loc_1400092EC
0x1400092c9  mov     r8d, 0B1h
0x1400092cf  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x1400092d6  lea     rcx, aVidfileobjectc; "VidFileObjectCreate"
0x1400092dd  call    VidTraceErrorInternal0
0x1400092e2  mov     ebx, 0C0000184h
0x1400092e7  jmp     loc_14000944C
0x1400092ec  mov     rcx, rbx
0x1400092ef  call    VidPartitionFileObjectReferenceInc
0x1400092f4  mov     rax, rdi
0x1400092f7  lock xadd [rbx+328h], rax
0x140009300  add     rax, rdi
0x140009303  mov     ecx, 0Eh
0x140009308  cmp     rax, rdi
0x14000930b  jg      short loc_14000930F
0x14000930d  int     29h; Win8: RtlFailFast(ecx)
0x14000930f  mov     rax, rdi
0x140009312  lock xadd [rbx+330h], rax
0x14000931b  add     rax, rdi
0x14000931e  cmp     rax, rdi
0x140009321  jg      short loc_140009325
0x140009323  int     29h; Win8: RtlFailFast(ecx)
0x140009325  or      rbx, rdi
0x140009328  mov     [rsi+18h], rbx
0x14000932c  mov     ebx, r14d
0x14000932f  jmp     loc_14000944C
0x140009334  mov     ebx, 0C0000033h
0x140009339  jmp     loc_140009449
0x14000933e  movzx   eax, word ptr [rbx]
0x140009341  test    ax, ax
0x140009344  jz      loc_140009423
0x14000934a  cmp     ax, r8w
0x14000934e  jnz     short loc_14000935E
0x140009350  mov     rax, [rbx+8]
0x140009354  cmp     word ptr [rax], 5Ch ; '\'
0x140009358  jz      loc_140009423
0x14000935e  lea     r8, [rbp+Buf2]
0x140009362  mov     rcx, rbx
0x140009365  lea     rdx, [rbp+P]
0x140009369  call    VidPartitionNameParse
0x14000936e  xor     r14d, r14d
0x140009371  mov     ebx, eax
0x140009373  test    eax, eax
0x140009375  jns     short loc_140009395
0x140009377  mov     r8d, 0EFh
0x14000937d  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140009384  lea     rcx, aVidfileobjectc; "VidFileObjectCreate"
0x14000938b  call    VidTraceErrorInternal0
0x140009390  jmp     loc_14000944C
0x140009395  mov     edi, 1
0x14000939a  cmp     [r13+40h], dil
0x14000939e  jnz     short loc_140009407
0x1400093a0  mov     rcx, cs:VidDeviceExtension
0x1400093a7  lea     rdx, [rbp+Buf2]
0x1400093ab  call    VidPartitionTableLookup
0x1400093b0  mov     rbx, rax
0x1400093b3  test    rax, rax
0x1400093b6  jz      short loc_140009407
0x1400093b8  cmp     dword ptr [rax+21B8h], 2
0x1400093bf  jnz     short loc_1400093E7
0x1400093c1  cmp     [rax+21D1h], dil
0x1400093c8  jnz     short loc_1400093E7
0x1400093ca  mov     rcx, rax
0x1400093cd  call    VidPartitionAttach
0x1400093d2  mov     [rsi+18h], rbx
0x1400093d6  movsx   rcx, byte ptr [r13+40h]
0x1400093db  or      rcx, rbx
0x1400093de  mov     [rsi+18h], rcx
0x1400093e2  jmp     loc_14000932C
0x1400093e7  mov     ebx, 0C0000184h
0x1400093ec  mov     r8d, 106h
0x1400093f2  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x1400093f9  lea     rcx, aVidfileobjectc; "VidFileObjectCreate"
0x140009400  call    VidTraceErrorInternal0
0x140009405  jmp     short loc_14000944C
0x140009407  mov     r9, r12
0x14000940a  mov     [rsp+78h+var_58], r15b; char
0x14000940f  mov     r8, rsi
0x140009412  lea     rdx, [rbp+Buf2]; Buf2
0x140009416  lea     rcx, [rbp+P]; SourceString
0x14000941a  call    VidPartitionCreate
0x14000941f  mov     ebx, eax
0x140009421  jmp     short loc_14000944C
0x140009423  test    r15b, r15b
0x140009426  jz      short loc_140009447
0x140009428  test    r14b, r14b
0x14000942b  jnz     short loc_140009434
0x14000942d  mov     ebx, 0C0000022h
0x140009432  jmp     short loc_140009449
0x140009434  lea     rcx, VidExoDeviceContext
0x14000943b  mov     rax, r14
0x14000943e  or      rax, rcx
0x140009441  mov     [rsi+18h], rax
0x140009445  xor     ecx, ecx
0x140009447  mov     ebx, ecx
0x140009449  xor     r14d, r14d
0x14000944c  mov     rcx, [rbp+P+8]; P
0x140009450  test    rcx, rcx
0x140009453  jz      short loc_140009471
0x140009455  mov     edx, 72446456h; Tag
0x14000945a  call    cs:__imp_ExFreePoolWithTag
0x140009461  nop     dword ptr [rax+rax+00h]
0x140009466  mov     [rbp+P+8], r14
0x14000946a  mov     dword ptr [rbp+P], 0
0x140009471  mov     rax, cs:WdfFunctions_01015
0x140009478  mov     r8d, ebx
0x14000947b  mov     rcx, cs:WdfDriverGlobals
0x140009482  mov     rdx, r12
0x140009485  mov     rax, [rax+838h]
0x14000948c  call    _guard_dispatch_icall
0x140009491  mov     rcx, [rbp+var_10]
0x140009495  xor     rcx, rsp; StackCookie
0x140009498  call    __security_check_cookie
0x14000949d  add     rsp, 78h
0x1400094a1  pop     r15
0x1400094a3  pop     r14
0x1400094a5  pop     r13
0x1400094a7  pop     r12
0x1400094a9  pop     rdi
0x1400094aa  pop     rsi
0x1400094ab  pop     rbx
0x1400094ac  pop     rbp
0x1400094ad  retn
```
