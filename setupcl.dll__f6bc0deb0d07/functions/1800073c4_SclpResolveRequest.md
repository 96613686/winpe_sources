# SclpResolveRequest

- ea: `0x1800073c4`
- end: `0x18000778f`
- name: `SclpResolveRequest`
- size: `971`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005a90`
- `0x180006024`
- `0x1800061b0`

## callees

- `0x18000163c`
- `0x1800016e4`
- `0x180001848`
- `0x180001a18`
- `0x180001cd4`
- `0x180001f70`
- `0x1800073c4`
- `0x18000952c`
- `0x18000a524`
- `0x180015130`
- `0x1800179c5`

## string_xrefs

- `0x180007477`: `\REGISTRY\MACHINE\SECURITY\POLICY\POLACDMS`
- `0x18000748b`: `\REGISTRY\MACHINE\SECURITY\POLICY\POLACDMS`
- `0x18000742e`: `Requests to replace the account domain SID that don't provide an explicit 'old' SID require access to the SECURITY hive.`
- `0x180007570`: `PATHNAME`
- `0x1800074f7`: `\REGISTRY\MACHINE\SOFTWARE\MICROSOFT\WINDOWS NT\CURRENTVERSION`
- `0x180007537`: `Requests to replace the OS drive path that don't provide an explicit 'old' path require access to the SOFTWARE hive.`
- `0x180007601`: `Requests to replace the OS drive path that don't provide an explicit 'new' path require access to the SOFTWARE hive.`

## pseudocode

```c
__int64 __fastcall SclpResolveRequest(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v6; // ebp
  int String; // ebx
  void *v8; // rcx
  int Sid; // eax
  char *v10; // rax
  int v11; // r9d
  __int64 v12; // rcx
  const wchar_t *v13; // rdx
  void *v14; // rcx
  int v15; // eax
  const wchar_t *v16; // r15
  __int64 *v17; // rdi
  const wchar_t *v18; // r11
  __int64 v19; // rcx
  const wchar_t *v20; // rdx
  __int16 v21; // cx
  _WORD *v22; // rdi
  __int64 v23; // rcx
  signed int LastErrorValue; // ecx
  struct _TEB *v25; // rax
  signed int v26; // ecx
  struct _TEB *v27; // rax
  void *v28; // rcx

  memset_0(a3, 0, 0x478u);
  *a3 = *(_DWORD *)a2;
  if ( a1 )
    v6 = *(_DWORD *)a1;
  else
    v6 = 1;
  String = 0;
  if ( (*(_DWORD *)a2 & 4) != 0 )
  {
    v8 = *(void **)(a2 + 8);
    if ( v8 )
    {
      Sid = SclDuplicateSid(v8, (_QWORD *)a3 + 1);
    }
    else
    {
      if ( v6 == 1 )
      {
        v13 = L"\\REGISTRY\\MACHINE\\SECURITY\\POLICY\\POLACDMS";
        v12 = 0;
      }
      else
      {
        if ( !*(_QWORD *)(a1 + 40) )
        {
          v10 = "Requests to replace the account domain SID that don't provide an explicit 'old' SID require access to th"
                "e SECURITY hive.";
          v11 = 997;
LABEL_10:
          String = -1073741811;
          SclLogGenericMessage(0, 3, (int)SclEvent_Generic_Error, v11, (__int64)"SclpResolveRequest", v10);
          goto LABEL_78;
        }
        v12 = *(_QWORD *)(a1 + 40);
        v13 = L"POLICY\\POLACDMS";
      }
      Sid = SclRetrieveSid(v12, v13, &pszSrc, a3 + 2);
    }
    String = Sid;
    if ( Sid < 0 )
      goto LABEL_78;
  }
  if ( (*(_DWORD *)a2 & 4) != 0 )
  {
    v14 = *(void **)(a2 + 16);
    v15 = v14 ? SclDuplicateSid(v14, (_QWORD *)a3 + 2) : SclGenerateUniqueAccountDomainSid((_QWORD *)a3 + 2);
    String = v15;
    if ( v15 < 0 )
      goto LABEL_78;
  }
  if ( (*(_BYTE *)a2 & 0xA) != 0 )
  {
    v16 = L"\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOFT\\WINDOWS NT\\CURRENTVERSION";
    if ( *(_WORD *)(a2 + 24) )
    {
      v17 = (__int64 *)(a1 + 48);
      String = RtlStringCchCopyW((_WORD *)a3 + 12, 0x104u, (_WORD *)(a2 + 24));
      if ( String < 0 )
        goto LABEL_78;
      goto LABEL_36;
    }
    v17 = (__int64 *)(a1 + 48);
    if ( v6 == 1 )
    {
      v20 = L"\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOFT\\WINDOWS NT\\CURRENTVERSION";
      LODWORD(v19) = 0;
    }
    else
    {
      if ( !*v17 )
      {
        v10 = "Requests to replace the OS drive path that don't provide an explicit 'old' path require access to the SOFTWARE hive.";
        v11 = 1075;
        goto LABEL_10;
      }
      v19 = *v17;
      v20 = L"MICROSOFT\\WINDOWS NT\\CURRENTVERSION";
    }
    String = SclRegGetString(v19, (_DWORD)v20, (unsigned int)L"PATHNAME", (int)a3 + 24, 260);
    if ( String < 0 )
      goto LABEL_78;
    v21 = *((_WORD *)a3 + 12);
    if ( ((unsigned __int16)(v21 - 97) <= 0x19u || (unsigned __int16)(v21 - 65) <= 0x19u) && *((_WORD *)a3 + 13) == 58 )
    {
      v18 = L"MICROSOFT\\WINDOWS NT\\CURRENTVERSION";
      if ( *((_WORD *)a3 + 14) == 92 )
        *((_WORD *)a3 + 15) = 0;
    }
    else
    {
      v18 = L"MICROSOFT\\WINDOWS NT\\CURRENTVERSION";
    }
LABEL_36:
    if ( *(_WORD *)(a2 + 544) )
    {
      v22 = a3 + 136;
      String = RtlStringCchCopyW((_WORD *)a3 + 272, 0x104u, (_WORD *)(a2 + 544));
      if ( String >= 0 )
        goto LABEL_50;
      goto LABEL_78;
    }
    if ( v6 == 1 )
    {
      LODWORD(v23) = 0;
    }
    else
    {
      if ( !*v17 )
      {
        v10 = "Requests to replace the OS drive path that don't provide an explicit 'new' path require access to the SOFTWARE hive.";
        v11 = 1121;
        goto LABEL_10;
      }
      v23 = *v17;
      LODWORD(v16) = (_DWORD)v18;
    }
    v22 = a3 + 136;
    String = SclRegGetString(v23, (_DWORD)v16, (unsigned int)L"SYSTEMROOT", (int)a3 + 544, 260);
    if ( String >= 0 )
    {
      if ( ((unsigned __int16)(*v22 - 97) <= 0x19u || (unsigned __int16)(*v22 - 65) <= 0x19u)
        && *((_WORD *)a3 + 273) == 58
        && *((_WORD *)a3 + 274) == 92 )
      {
        *((_WORD *)a3 + 275) = 0;
      }
LABEL_50:
      if ( !AddPathN((__int64)(a3 + 6)) )
      {
        LastErrorValue = NtCurrentTeb()->LastErrorValue;
        v25 = NtCurrentTeb();
        if ( !LastErrorValue )
          LastErrorValue = 31;
        String = v25->LastErrorValue;
        if ( LastErrorValue > 0 )
        {
          if ( !String )
            LOWORD(String) = 31;
          String = (unsigned __int16)String | 0xC0070000;
        }
        else
        {
          v22 = a3 + 136;
          if ( !String )
            String = 31;
        }
        if ( String < 0 )
          goto LABEL_78;
      }
      if ( !AddPathN((__int64)v22) )
      {
        v26 = NtCurrentTeb()->LastErrorValue;
        v27 = NtCurrentTeb();
        if ( !v26 )
          v26 = 31;
        String = v27->LastErrorValue;
        if ( v26 > 0 )
        {
          if ( !String )
            LOWORD(String) = 31;
          String = (unsigned __int16)String | 0xC0070000;
        }
        else if ( !String )
        {
          String = 31;
        }
        if ( String < 0 )
          goto LABEL_78;
      }
      goto LABEL_72;
    }
LABEL_78:
    SclFreeRequest(a3);
    return (unsigned int)String;
  }
LABEL_72:
  if ( (*(_DWORD *)a2 & 8) != 0 )
  {
    v28 = *(void **)(a2 + 1064);
    if ( v28 )
    {
      String = SclDuplicateMultiSz(v28);
      if ( String < 0 )
        goto LABEL_78;
    }
  }
  if ( (*(_DWORD *)a2 & 0x10) != 0 )
  {
    if ( *(_WORD *)(a2 + 1072) )
    {
      String = RtlStringCchCopyW((_WORD *)a3 + 536, 0x24u, (_WORD *)(a2 + 1072));
      if ( String < 0 )
        goto LABEL_78;
    }
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800073c4  push    rbx
0x1800073c6  push    rbp
0x1800073c7  push    rsi
0x1800073c8  push    rdi
0x1800073c9  push    r12
0x1800073cb  push    r14
0x1800073cd  push    r15
0x1800073cf  sub     rsp, 30h
0x1800073d3  mov     rsi, r8
0x1800073d6  mov     r14, rdx
0x1800073d9  mov     rdi, rcx
0x1800073dc  xor     edx, edx; Val
0x1800073de  mov     rcx, rsi; void *
0x1800073e1  mov     r8d, 478h; Size
0x1800073e7  call    memset_0
0x1800073ec  mov     eax, [r14]
0x1800073ef  mov     [rsi], eax
0x1800073f1  test    rdi, rdi
0x1800073f4  jz      short loc_1800073FA
0x1800073f6  mov     ebp, [rdi]
0x1800073f8  jmp     short loc_1800073FF
0x1800073fa  mov     ebp, 1
0x1800073ff  mov     eax, [r14]
0x180007402  xor     ebx, ebx
0x180007404  test    al, 4
0x180007406  jz      loc_1800074B2
0x18000740c  mov     rcx, [r14+8]; Src
0x180007410  test    rcx, rcx
0x180007413  jz      short loc_180007423
0x180007415  lea     rdx, [rsi+8]
0x180007419  call    SclDuplicateSid
0x18000741e  jmp     loc_1800074A8
0x180007423  cmp     ebp, 1
0x180007426  jz      short loc_180007484
0x180007428  cmp     [rdi+28h], rbx
0x18000742c  jnz     short loc_180007469
0x18000742e  lea     rax, aRequestsToRepl; "Requests to replace the account domain "...
0x180007435  mov     r9d, 3E5h
0x18000743b  mov     [rsp+68h+var_40], rax
0x180007440  lea     r8, SclEvent_Generic_Error
0x180007447  lea     rax, aSclpresolvereq; "SclpResolveRequest"
0x18000744e  mov     edx, 3
0x180007453  xor     ecx, ecx
0x180007455  mov     [rsp+68h+var_48], rax
0x18000745a  mov     ebx, 0C000000Dh
0x18000745f  call    SclLogGenericMessage
0x180007464  jmp     loc_180007776
0x180007469  mov     rcx, [rdi+28h]
0x18000746d  lea     rax, aPolicyPolacdms; "POLICY\\POLACDMS"
0x180007474  cmp     ebp, 1
0x180007477  lea     rdx, aRegistryMachin_7; "\\REGISTRY\\MACHINE\\SECURITY\\POLICY\\"...
0x18000747e  cmovnz  rdx, rax
0x180007482  jmp     short loc_180007498
0x180007484  lea     rax, aPolicyPolacdms; "POLICY\\POLACDMS"
0x18000748b  lea     rdx, aRegistryMachin_7; "\\REGISTRY\\MACHINE\\SECURITY\\POLICY\\"...
0x180007492  cmovnz  rdx, rax
0x180007496  xor     ecx, ecx
0x180007498  lea     r9, [rsi+8]
0x18000749c  lea     r8, pszSrc
0x1800074a3  call    SclRetrieveSid
0x1800074a8  mov     ebx, eax
0x1800074aa  test    eax, eax
0x1800074ac  js      loc_180007776
0x1800074b2  mov     eax, [r14]
0x1800074b5  test    al, 4
0x1800074b7  jz      short loc_1800074E0
0x1800074b9  mov     rcx, [r14+10h]; Src
0x1800074bd  test    rcx, rcx
0x1800074c0  jz      short loc_1800074CD
0x1800074c2  lea     rdx, [rsi+10h]
0x1800074c6  call    SclDuplicateSid
0x1800074cb  jmp     short loc_1800074D6
0x1800074cd  lea     rcx, [rsi+10h]
0x1800074d1  call    SclGenerateUniqueAccountDomainSid
0x1800074d6  mov     ebx, eax
0x1800074d8  test    eax, eax
0x1800074da  js      loc_180007776
0x1800074e0  test    byte ptr [r14], 0Ah
0x1800074e4  jz      loc_180007726
0x1800074ea  xor     eax, eax
0x1800074ec  lea     r8, [r14+18h]
0x1800074f0  lea     r11, aMicrosoftWindo; "MICROSOFT\\WINDOWS NT\\CURRENTVERSION"
0x1800074f7  lea     r15, aRegistryMachin_11; "\\REGISTRY\\MACHINE\\SOFTWARE\\MICROSOF"...
0x1800074fe  lea     r12d, [rax+3Ah]
0x180007502  cmp     ax, [r8]
0x180007506  jz      short loc_180007529
0x180007508  lea     rcx, [rsi+18h]
0x18000750c  mov     edx, 104h
0x180007511  call    RtlStringCchCopyW
0x180007516  add     rdi, 30h ; '0'
0x18000751a  mov     ebx, eax
0x18000751c  test    eax, eax
0x18000751e  jns     loc_1800075C5
0x180007524  jmp     loc_180007776
0x180007529  add     rdi, 30h ; '0'
0x18000752d  cmp     ebp, 1
0x180007530  jz      short loc_180007558
0x180007532  cmp     [rdi], rax
0x180007535  jnz     short loc_180007549
0x180007537  lea     rax, aRequestsToRepl_1; "Requests to replace the OS drive path t"...
0x18000753e  mov     r9d, 433h
0x180007544  jmp     loc_18000743B
0x180007549  mov     rcx, [rdi]
0x18000754c  cmp     ebp, 1
0x18000754f  mov     rdx, r15
0x180007552  cmovnz  rdx, r11
0x180007556  jmp     short loc_180007564
0x180007558  cmp     ebp, 1
0x18000755b  mov     rdx, r15
0x18000755e  cmovnz  rdx, r11
0x180007562  xor     ecx, ecx
0x180007564  lea     r9, [rsi+18h]
0x180007568  mov     dword ptr [rsp+68h+var_48], 104h
0x180007570  lea     r8, aPathname; "PATHNAME"
0x180007577  call    SclRegGetString
0x18000757c  mov     ebx, eax
0x18000757e  test    eax, eax
0x180007580  js      loc_180007776
0x180007586  movzx   ecx, word ptr [rsi+18h]
0x18000758a  lea     eax, [rcx-61h]
0x18000758d  cmp     ax, 19h
0x180007591  jbe     short loc_18000759D
0x180007593  sub     cx, 41h ; 'A'
0x180007597  cmp     cx, 19h
0x18000759b  ja      short loc_1800075BE
0x18000759d  cmp     r12w, [rsi+1Ah]
0x1800075a2  jnz     short loc_1800075BE
0x1800075a4  mov     eax, 5Ch ; '\'
0x1800075a9  lea     r11, aMicrosoftWindo; "MICROSOFT\\WINDOWS NT\\CURRENTVERSION"
0x1800075b0  cmp     ax, [rsi+1Ch]
0x1800075b4  jnz     short loc_1800075C5
0x1800075b6  xor     eax, eax
0x1800075b8  mov     [rsi+1Eh], ax
0x1800075bc  jmp     short loc_1800075C5
0x1800075be  lea     r11, aMicrosoftWindo; "MICROSOFT\\WINDOWS NT\\CURRENTVERSION"
0x1800075c5  lea     r8, [r14+220h]
0x1800075cc  xor     eax, eax
0x1800075ce  cmp     ax, [r8]
0x1800075d2  jz      short loc_1800075F7
0x1800075d4  lea     rdi, [rsi+220h]
0x1800075db  mov     edx, 104h
0x1800075e0  mov     rcx, rdi
0x1800075e3  call    RtlStringCchCopyW
0x1800075e8  mov     ebx, eax
0x1800075ea  test    eax, eax
0x1800075ec  js      loc_180007776
0x1800075f2  jmp     loc_180007687
0x1800075f7  cmp     ebp, 1
0x1800075fa  jz      short loc_18000761F
0x1800075fc  cmp     [rdi], rax
0x1800075ff  jnz     short loc_180007613
0x180007601  lea     rax, aRequestsToRepl_0; "Requests to replace the OS drive path t"...
0x180007608  mov     r9d, 461h
0x18000760e  jmp     loc_18000743B
0x180007613  mov     rcx, [rdi]
0x180007616  cmp     ebp, 1
0x180007619  cmovnz  r15, r11
0x18000761d  jmp     short loc_180007625
0x18000761f  cmovnz  r15, r11
0x180007623  xor     ecx, ecx
0x180007625  lea     rdi, [rsi+220h]
0x18000762c  mov     dword ptr [rsp+68h+var_48], 104h
0x180007634  mov     r9, rdi
0x180007637  lea     r8, aSystemroot_1; "SYSTEMROOT"
0x18000763e  mov     rdx, r15
0x180007641  call    SclRegGetString
0x180007646  mov     ebx, eax
0x180007648  test    eax, eax
0x18000764a  js      loc_180007776
0x180007650  movzx   ecx, word ptr [rdi]
0x180007653  lea     eax, [rcx-61h]
0x180007656  cmp     ax, 19h
0x18000765a  jbe     short loc_180007666
0x18000765c  sub     cx, 41h ; 'A'
0x180007660  cmp     cx, 19h
0x180007664  ja      short loc_180007687
0x180007666  cmp     r12w, [rsi+222h]
0x18000766e  jnz     short loc_180007687
0x180007670  mov     eax, 5Ch ; '\'
0x180007675  cmp     ax, [rsi+224h]
0x18000767c  jnz     short loc_180007687
0x18000767e  xor     eax, eax
0x180007680  mov     [rsi+226h], ax
0x180007687  lea     rcx, [rsi+18h]
0x18000768b  call    AddPathN
0x180007690  mov     ebp, 1Fh
0x180007695  mov     r15d, 0C0070000h
0x18000769b  test    rax, rax
0x18000769e  jnz     short loc_1800076E2
0x1800076a0  mov     rax, gs:30h
0x1800076a9  mov     ecx, [rax+68h]
0x1800076ac  test    ecx, ecx
0x1800076ae  mov     rax, gs:30h
0x1800076b7  cmovz   ecx, ebp
0x1800076ba  mov     ebx, [rax+68h]
0x1800076bd  test    ecx, ecx
0x1800076bf  jg      short loc_1800076CF
0x1800076c1  test    ebx, ebx
0x1800076c3  lea     rdi, [rsi+220h]
0x1800076ca  cmovz   ebx, ebp
0x1800076cd  jmp     short loc_1800076DA
0x1800076cf  test    ebx, ebx
0x1800076d1  cmovz   ebx, ebp
0x1800076d4  movzx   ebx, bx
0x1800076d7  or      ebx, r15d
0x1800076da  test    ebx, ebx
0x1800076dc  js      loc_180007776
0x1800076e2  mov     rcx, rdi
0x1800076e5  call    AddPathN
0x1800076ea  test    rax, rax
0x1800076ed  jnz     short loc_180007726
0x1800076ef  mov     rax, gs:30h
0x1800076f8  mov     ecx, [rax+68h]
0x1800076fb  test    ecx, ecx
0x1800076fd  mov     rax, gs:30h
0x180007706  cmovz   ecx, ebp
0x180007709  mov     ebx, [rax+68h]
0x18000770c  test    ecx, ecx
0x18000770e  jg      short loc_180007717
0x180007710  test    ebx, ebx
0x180007712  cmovz   ebx, ebp
0x180007715  jmp     short loc_180007722
0x180007717  test    ebx, ebx
0x180007719  cmovz   ebx, ebp
0x18000771c  movzx   ebx, bx
0x18000771f  or      ebx, r15d
0x180007722  test    ebx, ebx
0x180007724  js      short loc_180007776
0x180007726  mov     eax, [r14]
0x180007729  test    al, 8
0x18000772b  jz      short loc_18000774B
0x18000772d  mov     rcx, [r14+428h]; Src
0x180007734  test    rcx, rcx
0x180007737  jz      short loc_18000774B
0x180007739  lea     rdx, [rsi+428h]
0x180007740  call    SclDuplicateMultiSz
0x180007745  mov     ebx, eax
0x180007747  test    eax, eax
0x180007749  js      short loc_180007776
0x18000774b  mov     eax, [r14]
0x18000774e  test    al, 10h
0x180007750  jz      short loc_18000777E
0x180007752  lea     r8, [r14+430h]
0x180007759  xor     eax, eax
0x18000775b  cmp     ax, [r8]
0x18000775f  jz      short loc_18000777E
0x180007761  lea     rcx, [rsi+430h]
0x180007768  lea     edx, [rax+24h]
0x18000776b  call    RtlStringCchCopyW
0x180007770  mov     ebx, eax
0x180007772  test    eax, eax
0x180007774  jns     short loc_18000777E
0x180007776  mov     rcx, rsi; void *
0x180007779  call    SclFreeRequest
0x18000777e  mov     eax, ebx
0x180007780  add     rsp, 30h
0x180007784  pop     r15
0x180007786  pop     r14
0x180007788  pop     r12
0x18000778a  pop     rdi
0x18000778b  pop     rsi
0x18000778c  pop     rbp
0x18000778d  pop     rbx
0x18000778e  retn
```
