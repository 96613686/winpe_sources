# SmpExecuteCommand

- ea: `0x140003450`
- end: `0x1400036c2`
- name: `SmpExecuteCommand`
- size: `626`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006f30`
- `0x140007420`
- `0x14000c638`
- `0x1400150f0`
- `0x140016190`

## callees

- `0x1400010ec`
- `0x140003450`
- `0x140004610`
- `0x1400050a0`
- `0x1400053e0`
- `0x140005998`
- `0x140014fc4`
- `0x1400151e0`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x14000350b`
- `ntdll!RtlFreeUnicodeString` at `0x140003516`
- `ntdll!RtlFreeUnicodeString` at `0x140003599`
- `ntdll!RtlFreeUnicodeString` at `0x14000350b`
- `ntdll!RtlFreeUnicodeString` at `0x140003516`
- `ntdll!RtlFreeUnicodeString` at `0x140003599`

## string_xrefs

- `0x1400035cc`: `SmpExecuteCommand`
- `0x14000367d`: `SmpExecuteCommand`
- `0x1400036ac`: `SmpExecuteCommand`

## pseudocode

```c
__int64 __fastcall SmpExecuteCommand(__int64 a1, unsigned int a2, __int64 a3, int a4, _OWORD *a5)
{
  _OWORD *v5; // rbp
  struct _UNICODE_STRING *v8; // rdi
  int v9; // ebx
  __int64 v10; // r9
  int SubSystem; // eax
  _WORD *v13; // rdi
  __int64 v14; // rcx
  char *v15; // rax
  __int64 v16; // rdx
  char *v17; // rcx
  __int64 v18; // r8
  int v19; // [rsp+20h] [rbp-168h]
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-148h] BYREF
  struct _UNICODE_STRING v21; // [rsp+50h] [rbp-138h] BYREF
  struct _UNICODE_STRING v22; // [rsp+60h] [rbp-128h] BYREF
  _BYTE v23[64]; // [rsp+70h] [rbp-118h] BYREF
  char v24; // [rsp+B0h] [rbp-D8h] BYREF
  int v25; // [rsp+1A8h] [rbp+20h] BYREF

  v25 = a4;
  v5 = a5;
  UnicodeString = 0;
  v22 = 0;
  v21 = 0;
  if ( (a4 & 1) == 0 )
  {
    v8 = &v22;
    if ( (a4 & 0x400) != 0 )
      v8 = 0;
    v9 = SmpParseCommandLine(a1, &v25, &UnicodeString, v8, &v21);
    if ( v9 < 0 )
    {
      if ( a1 )
        v13 = *(_WORD **)(a1 + 8);
      else
        v13 = 0;
      memset_0(v23, 0, 0xE0u);
      if ( v13 )
      {
        v14 = 2147483646;
        v15 = &v24;
        v16 = 64;
        do
        {
          if ( !v14 )
            break;
          if ( !*v13 )
            break;
          *(_WORD *)v15 = *v13++;
          v15 += 2;
          --v14;
          --v16;
        }
        while ( v16 );
        v17 = v15 - 2;
        if ( v16 )
          v17 = v15;
        *(_WORD *)v17 = 0;
      }
      SmpInternalLogFailure("SmpExecuteCommand", 10151, (unsigned int)v9, v23);
      return (unsigned int)v9;
    }
    if ( (v25 & 4) != 0 )
    {
      if ( SmpSoftBoot && !SmpBugcheckRecovery )
        goto LABEL_8;
      SubSystem = SmpInvokeAutoChk(&UnicodeString);
    }
    else if ( (v25 & 8) != 0 )
    {
      if ( SmpPrimarySmss )
        SubSystem = SmpLoadSubSystem((__int64)&UnicodeString, (__int64)v8, a1, a2, v19, v25);
      else
        SubSystem = SmscpLoadSubSystem(&UnicodeString.Length, (__int64)v8, a1, a2, v25);
    }
    else
    {
      if ( (v25 & 0x10) != 0 )
      {
        v9 = -1073741772;
        SmpLogFailureString("SmpExecuteCommand", 10189, UnicodeString.Buffer, 3221225524LL);
        goto LABEL_8;
      }
      SubSystem = SmpExecuteImage((__int64)&UnicodeString, (__int64)v8, a1, v10, 0, v25, v5);
    }
    v9 = SubSystem;
LABEL_8:
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v21);
    if ( v8 )
      RtlFreeUnicodeString(&v22);
    if ( v9 < 0 )
    {
      if ( a1 )
        v18 = *(_QWORD *)(a1 + 8);
      else
        v18 = 0;
      SmpLogFailureString("SmpExecuteCommand", 10217, v18, (unsigned int)v9);
    }
    return (unsigned int)v9;
  }
  return 0;
}

```

## disassembly

```asm
0x140003450  mov     r11, rsp
0x140003453  mov     [r11+20h], r9d
0x140003457  push    rbp
0x140003458  push    rsi
0x140003459  push    r14
0x14000345b  sub     rsp, 170h
0x140003462  mov     rax, cs:__security_cookie
0x140003469  xor     rax, rsp
0x14000346c  mov     [rsp+188h+var_38], rax
0x140003474  mov     rbp, [rsp+188h+arg_20]
0x14000347c  xorps   xmm0, xmm0
0x14000347f  xorps   xmm1, xmm1
0x140003482  mov     r14d, edx
0x140003485  mov     rsi, rcx
0x140003488  movups  xmmword ptr [rsp+188h+UnicodeString.Length], xmm0
0x14000348d  movups  xmmword ptr [rsp+188h+var_128.Length], xmm1
0x140003492  movups  xmmword ptr [rsp+188h+var_138.Length], xmm0
0x140003497  test    r9b, 1
0x14000349b  jnz     loc_140003590
0x1400034a1  bt      r9d, 0Ah
0x1400034a6  mov     [r11-20h], rbx
0x1400034aa  mov     [r11-28h], rdi
0x1400034ae  lea     r8, [rsp+188h+UnicodeString]
0x1400034b3  mov     eax, 0
0x1400034b8  lea     rdi, [rsp+188h+var_128]
0x1400034bd  cmovb   rdi, rax
0x1400034c1  lea     rdx, [r11+20h]
0x1400034c5  lea     rax, [rsp+188h+var_138]
0x1400034ca  mov     r9, rdi
0x1400034cd  mov     [rsp+188h+var_168], rax
0x1400034d2  call    SmpParseCommandLine
0x1400034d7  mov     ebx, eax
0x1400034d9  test    eax, eax
0x1400034db  js      loc_1400035A1
0x1400034e1  mov     eax, [rsp+188h+arg_18]
0x1400034e8  test    al, 4
0x1400034ea  jz      short loc_140003557
0x1400034ec  cmp     cs:SmpSoftBoot, 0
0x1400034f3  jz      loc_14000362B
0x1400034f9  cmp     cs:SmpBugcheckRecovery, 0
0x140003500  jnz     loc_14000362B
0x140003506  lea     rcx, [rsp+188h+UnicodeString]; UnicodeString
0x14000350b  call    cs:__imp_RtlFreeUnicodeString
0x140003511  lea     rcx, [rsp+188h+var_138]; UnicodeString
0x140003516  call    cs:__imp_RtlFreeUnicodeString
0x14000351c  test    rdi, rdi
0x14000351f  jnz     short loc_140003594
0x140003521  test    ebx, ebx
0x140003523  js      loc_14000369B
0x140003529  mov     rdi, [rsp+188h+var_28]
0x140003531  mov     eax, ebx
0x140003533  mov     rbx, [rsp+188h+var_20]
0x14000353b  mov     rcx, [rsp+188h+var_38]
0x140003543  xor     rcx, rsp; StackCookie
0x140003546  call    __security_check_cookie
0x14000354b  add     rsp, 170h
0x140003552  pop     r14
0x140003554  pop     rsi
0x140003555  pop     rbp
0x140003556  retn
0x140003557  test    al, 8
0x140003559  jnz     loc_140003645
0x14000355f  test    al, 10h
0x140003561  jnz     loc_140003678
0x140003567  mov     [rsp+188h+var_158], rbp
0x14000356c  lea     rcx, [rsp+188h+UnicodeString]
0x140003571  mov     [rsp+188h+var_160], eax
0x140003575  mov     r8, rsi
0x140003578  mov     rdx, rdi
0x14000357b  mov     [rsp+188h+var_168], 0
0x140003584  call    SmpExecuteImage
0x140003589  mov     ebx, eax
0x14000358b  jmp     loc_140003506
0x140003590  xor     eax, eax
0x140003592  jmp     short loc_14000353B
0x140003594  lea     rcx, [rsp+188h+var_128]; UnicodeString
0x140003599  call    cs:__imp_RtlFreeUnicodeString
0x14000359f  jmp     short loc_140003521
0x1400035a1  test    rsi, rsi
0x1400035a4  jnz     short loc_1400035DD
0x1400035a6  xor     edi, edi
0x1400035a8  xor     edx, edx; Val
0x1400035aa  lea     rcx, [rsp+188h+var_118]; void *
0x1400035af  mov     r8d, 0E0h; Size
0x1400035b5  call    memset_0
0x1400035ba  test    rdi, rdi
0x1400035bd  jnz     short loc_1400035E3
0x1400035bf  lea     r9, [rsp+188h+var_118]
0x1400035c4  mov     r8d, ebx
0x1400035c7  mov     edx, 27A7h
0x1400035cc  lea     rcx, aSmpexecutecomm; "SmpExecuteCommand"
0x1400035d3  call    SmpInternalLogFailure
0x1400035d8  jmp     loc_140003529
0x1400035dd  mov     rdi, [rsi+8]
0x1400035e1  jmp     short loc_1400035A8
0x1400035e3  mov     ecx, 7FFFFFFEh
0x1400035e8  lea     rax, [rsp+188h+var_D8]
0x1400035f0  mov     edx, 40h ; '@'
0x1400035f5  test    rcx, rcx
0x1400035f8  jz      short loc_140003619
0x1400035fa  movzx   r8d, word ptr [rdi]
0x1400035fe  test    r8w, r8w
0x140003602  jz      short loc_140003619
0x140003604  mov     [rax], r8w
0x140003608  add     rdi, 2
0x14000360c  add     rax, 2
0x140003610  dec     rcx
0x140003613  sub     rdx, 1
0x140003617  jnz     short loc_1400035F5
0x140003619  test    rdx, rdx
0x14000361c  lea     rcx, [rax-2]
0x140003620  cmovnz  rcx, rax
0x140003624  xor     eax, eax
0x140003626  mov     [rcx], ax
0x140003629  jmp     short loc_1400035BF
0x14000362b  mov     r9d, eax
0x14000362e  lea     r8, [rsp+188h+var_138]
0x140003633  mov     rdx, rdi
0x140003636  lea     rcx, [rsp+188h+UnicodeString]; Source
0x14000363b  call    SmpInvokeAutoChk
0x140003640  jmp     loc_140003589
0x140003645  cmp     cs:SmpPrimarySmss, 0
0x14000364c  lea     rcx, [rsp+188h+UnicodeString]
0x140003651  mov     r9d, r14d
0x140003654  mov     r8, rsi
0x140003657  mov     rdx, rdi
0x14000365a  jz      short loc_14000366A
0x14000365c  mov     [rsp+188h+var_160], eax
0x140003660  call    SmpLoadSubSystem
0x140003665  jmp     loc_140003589
0x14000366a  mov     dword ptr [rsp+188h+var_168], eax
0x14000366e  call    SmscpLoadSubSystem
0x140003673  jmp     loc_140003589
0x140003678  mov     r8, [rsp+188h+UnicodeString.Buffer]
0x14000367d  lea     rcx, aSmpexecutecomm; "SmpExecuteCommand"
0x140003684  mov     ebx, 0C0000034h
0x140003689  mov     edx, 27CDh
0x14000368e  mov     r9d, ebx
0x140003691  call    SmpLogFailureString
0x140003696  jmp     loc_140003506
0x14000369b  test    rsi, rsi
0x14000369e  jz      short loc_1400036A6
0x1400036a0  mov     r8, [rsi+8]
0x1400036a4  jmp     short loc_1400036A9
0x1400036a6  xor     r8d, r8d
0x1400036a9  mov     r9d, ebx
0x1400036ac  lea     rcx, aSmpexecutecomm; "SmpExecuteCommand"
0x1400036b3  mov     edx, 27E9h
0x1400036b8  call    SmpLogFailureString
0x1400036bd  jmp     loc_140003529
```
