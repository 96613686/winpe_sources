# ConvertNtStatusToHResult

- ea: `0x18001a5e4`
- end: `0x18001aa0b`
- name: `ConvertNtStatusToHResult`
- size: `1063`
- prototype: `signed int __fastcall(NTSTATUS Status)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800020d0`
- `0x1800022c4`
- `0x180002500`
- `0x18000a384`
- `0x18000a570`
- `0x1800118a4`
- `0x1800119e8`
- `0x1800134c0`
- `0x1800136a0`
- `0x18001a17c`
- `0x18001a260`

## callees

- `0x18001a5e4`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a9d2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a9d2`

## pseudocode

```c
signed int __fastcall ConvertNtStatusToHResult(NTSTATUS Status)
{
  signed int result; // eax
  int v3; // ecx
  int v4; // eax
  unsigned int v6; // ebx

  if ( Status > -1073740757 )
  {
    if ( Status > -1072365540 )
    {
      if ( Status > -1072365532 )
      {
        switch ( Status )
        {
          case -1072365531:
            return -2147010788;
          case -1072365530:
            return -2147010787;
          case -1072365529:
            return -2147010786;
          case 0:
            return 0;
        }
      }
      else
      {
        switch ( Status )
        {
          case -1072365532:
            return -2147010789;
          case -1072365539:
            return -2147010794;
          case -1072365538:
            return -2147010793;
          case -1072365537:
            return -2147010792;
          case -1072365536:
            return -2147010797;
          case -1072365535:
            return -2147010796;
        }
      }
    }
    else
    {
      if ( Status == -1072365540 )
        return -2147010795;
      if ( Status > -1072365546 )
      {
        switch ( Status )
        {
          case -1072365545:
            return -2147010805;
          case -1072365544:
            return -2147010804;
          case -1072365543:
            return -2147010803;
          case -1072365542:
            return -2147010798;
        }
        return -2147010868;
      }
      switch ( Status )
      {
        case -1072365546:
          return -2147010806;
        case -1073700733:
          return -2147023431;
        case -1073700732:
          return -2147023430;
        case -1072365564:
          return -2147010893;
        case -1072365556:
          return -2147010815;
        case -1072365547:
          return -2147010813;
      }
    }
  }
  else
  {
    if ( Status == -1073740757 )
      return -2147023604;
    if ( Status > -1073741757 )
    {
      if ( Status > -1073741511 )
      {
        switch ( Status )
        {
          case -1073741471:
            return -2147024314;
          case -1073741469:
            return -2147024313;
          case -1073741197:
            return -2147024270;
          case -1073740759:
            return -2147024121;
          case -1073740758:
            return -2147024120;
        }
      }
      else
      {
        switch ( Status )
        {
          case -1073741511:
            return -2147024769;
          case -1073741735:
            return -2147023590;
          case -1073741697:
            return -2147024784;
          case -1073741675:
            return -2147024362;
          case -1073741595:
            return -2147023537;
          case -1073741515:
            return -2147024770;
        }
      }
    }
    else
    {
      if ( Status == -1073741757 )
        return -2147024864;
      if ( Status > -1073741790 )
      {
        switch ( Status )
        {
          case -1073741789:
            return -2147024774;
          case -1073741773:
            return -2147024773;
          case -1073741772:
            return -2147024894;
          case -1073741767:
            return -2147024735;
          case -1073741766:
            return -2147024893;
        }
      }
      else
      {
        switch ( Status )
        {
          case -1073741790:
            return -2147024891;
          case -2147483643:
            return -2147024662;
          case -1073741823:
            return -2147467259;
          case -1073741822:
            return -2147467263;
          case -1073741811:
            return -2147024809;
          case -1073741801:
            return -2147024882;
        }
      }
    }
  }
  v3 = 589824;
  v4 = Status & 0xFFF0000;
  if ( (Status & 0xFFF0000) == 0x90000 )
  {
    if ( !Status )
      return 0;
    v6 = Status & 0xC009FFFF;
    return v3 | v6;
  }
  if ( v4 == 0x80000 )
  {
    if ( Status )
      return Status & 0xC000FFFF | 0xB0000;
    return 0;
  }
  v3 = 1572864;
  if ( v4 == 1572864 )
  {
    if ( !Status )
      return 0;
    v6 = Status & 0xC018FFFF;
    return v3 | v6;
  }
  v3 = 983040;
  if ( v4 == 983040 )
  {
    if ( !Status )
      return 0;
    v6 = Status & 0xC00FFFFF;
    return v3 | v6;
  }
  if ( v4 == 458752 )
  {
    result = (unsigned __int16)Status;
    if ( !(_WORD)Status )
      return result;
    return result | 0x80070000;
  }
  result = RtlNtStatusToDosErrorNoTeb(Status);
  if ( result == 317 )
    return Status | 0x10000000;
  if ( result > 0 )
  {
    result = (unsigned __int16)result;
    return result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001a5e4  push    rbx
0x18001a5e6  sub     rsp, 20h
0x18001a5ea  mov     eax, 0C000042Bh
0x18001a5ef  mov     ebx, ecx
0x18001a5f1  cmp     ecx, eax
0x18001a5f3  jg      loc_18001A7C8
0x18001a5f9  jz      loc_18001A7BE
0x18001a5ff  mov     eax, 0C0000043h
0x18001a604  cmp     ecx, eax
0x18001a606  jg      loc_18001A6ED
0x18001a60c  jz      loc_18001A6E3
0x18001a612  mov     eax, 0C0000022h
0x18001a617  cmp     ecx, eax
0x18001a619  jg      short loc_18001A685
0x18001a61b  jz      short loc_18001A67B
0x18001a61d  cmp     ecx, 80000005h
0x18001a623  jz      short loc_18001A671
0x18001a625  cmp     ecx, 0C0000001h
0x18001a62b  jz      short loc_18001A667
0x18001a62d  cmp     ecx, 0C0000002h
0x18001a633  jz      short loc_18001A65D
0x18001a635  cmp     ecx, 0C000000Dh
0x18001a63b  jz      short loc_18001A653
0x18001a63d  cmp     ecx, 0C0000017h
0x18001a643  jnz     loc_18001A951
0x18001a649  mov     eax, 8007000Eh
0x18001a64e  jmp     loc_18001AA05
0x18001a653  mov     eax, 80070057h
0x18001a658  jmp     loc_18001AA05
0x18001a65d  mov     eax, 80004001h
0x18001a662  jmp     loc_18001AA05
0x18001a667  mov     eax, 80004005h
0x18001a66c  jmp     loc_18001AA05
0x18001a671  mov     eax, 800700EAh
0x18001a676  jmp     loc_18001AA05
0x18001a67b  mov     eax, 80070005h
0x18001a680  jmp     loc_18001AA05
0x18001a685  cmp     ebx, 0C0000023h
0x18001a68b  jz      short loc_18001A6D9
0x18001a68d  cmp     ebx, 0C0000033h
0x18001a693  jz      short loc_18001A6CF
0x18001a695  cmp     ebx, 0C0000034h
0x18001a69b  jz      short loc_18001A6C5
0x18001a69d  cmp     ebx, 0C0000039h
0x18001a6a3  jz      short loc_18001A6BB
0x18001a6a5  cmp     ebx, 0C000003Ah
0x18001a6ab  jnz     loc_18001A951
0x18001a6b1  mov     eax, 80070003h
0x18001a6b6  jmp     loc_18001AA05
0x18001a6bb  mov     eax, 800700A1h
0x18001a6c0  jmp     loc_18001AA05
0x18001a6c5  mov     eax, 80070002h
0x18001a6ca  jmp     loc_18001AA05
0x18001a6cf  mov     eax, 8007007Bh
0x18001a6d4  jmp     loc_18001AA05
0x18001a6d9  mov     eax, 8007007Ah
0x18001a6de  jmp     loc_18001AA05
0x18001a6e3  mov     eax, 80070020h
0x18001a6e8  jmp     loc_18001AA05
0x18001a6ed  mov     eax, 0C0000139h
0x18001a6f2  cmp     ebx, eax
0x18001a6f4  jg      short loc_18001A760
0x18001a6f6  jz      short loc_18001A756
0x18001a6f8  cmp     ebx, 0C0000059h
0x18001a6fe  jz      short loc_18001A74C
0x18001a700  cmp     ebx, 0C000007Fh
0x18001a706  jz      short loc_18001A742
0x18001a708  cmp     ebx, 0C0000095h
0x18001a70e  jz      short loc_18001A738
0x18001a710  cmp     ebx, 0C00000E5h
0x18001a716  jz      short loc_18001A72E
0x18001a718  cmp     ebx, 0C0000135h
0x18001a71e  jnz     loc_18001A951
0x18001a724  mov     eax, 8007007Eh
0x18001a729  jmp     loc_18001AA05
0x18001a72e  mov     eax, 8007054Fh
0x18001a733  jmp     loc_18001AA05
0x18001a738  mov     eax, 80070216h
0x18001a73d  jmp     loc_18001AA05
0x18001a742  mov     eax, 80070070h
0x18001a747  jmp     loc_18001AA05
0x18001a74c  mov     eax, 8007051Ah
0x18001a751  jmp     loc_18001AA05
0x18001a756  mov     eax, 8007007Fh
0x18001a75b  jmp     loc_18001AA05
0x18001a760  cmp     ebx, 0C0000161h
0x18001a766  jz      short loc_18001A7B4
0x18001a768  cmp     ebx, 0C0000163h
0x18001a76e  jz      short loc_18001A7AA
0x18001a770  cmp     ebx, 0C0000273h
0x18001a776  jz      short loc_18001A7A0
0x18001a778  cmp     ebx, 0C0000429h
0x18001a77e  jz      short loc_18001A796
0x18001a780  cmp     ebx, 0C000042Ah
0x18001a786  jnz     loc_18001A951
0x18001a78c  mov     eax, 80070308h
0x18001a791  jmp     loc_18001AA05
0x18001a796  mov     eax, 80070307h
0x18001a79b  jmp     loc_18001AA05
0x18001a7a0  mov     eax, 80070272h
0x18001a7a5  jmp     loc_18001AA05
0x18001a7aa  mov     eax, 80070247h
0x18001a7af  jmp     loc_18001AA05
0x18001a7b4  mov     eax, 80070246h
0x18001a7b9  jmp     loc_18001AA05
0x18001a7be  mov     eax, 8007050Ch
0x18001a7c3  jmp     loc_18001AA05
0x18001a7c8  mov     eax, 0C015001Ch
0x18001a7cd  cmp     ebx, eax
0x18001a7cf  jg      loc_18001A8B6
0x18001a7d5  jz      loc_18001A8AC
0x18001a7db  mov     eax, 0C0150016h
0x18001a7e0  cmp     ebx, eax
0x18001a7e2  jg      short loc_18001A84E
0x18001a7e4  jz      short loc_18001A844
0x18001a7e6  cmp     ebx, 0C000A083h
0x18001a7ec  jz      short loc_18001A83A
0x18001a7ee  cmp     ebx, 0C000A084h
0x18001a7f4  jz      short loc_18001A830
0x18001a7f6  cmp     ebx, 0C0150004h
0x18001a7fc  jz      short loc_18001A826
0x18001a7fe  cmp     ebx, 0C015000Ch
0x18001a804  jz      short loc_18001A81C
0x18001a806  cmp     ebx, 0C0150015h
0x18001a80c  jnz     loc_18001A951
0x18001a812  mov     eax, 80073703h
0x18001a817  jmp     loc_18001AA05
0x18001a81c  mov     eax, 80073701h
0x18001a821  jmp     loc_18001AA05
0x18001a826  mov     eax, 800736B3h
0x18001a82b  jmp     loc_18001AA05
0x18001a830  mov     eax, 800705BAh
0x18001a835  jmp     loc_18001AA05
0x18001a83a  mov     eax, 800705B9h
0x18001a83f  jmp     loc_18001AA05
0x18001a844  mov     eax, 8007370Ah
0x18001a849  jmp     loc_18001AA05
0x18001a84e  cmp     ebx, 0C0150017h
0x18001a854  jz      short loc_18001A8A2
0x18001a856  cmp     ebx, 0C0150018h
0x18001a85c  jz      short loc_18001A898
0x18001a85e  cmp     ebx, 0C0150019h
0x18001a864  jz      short loc_18001A88E
0x18001a866  cmp     ebx, 0C015001Ah
0x18001a86c  jz      short loc_18001A884
0x18001a86e  cmp     ebx, 0C015001Bh
0x18001a874  jnz     loc_18001A951
0x18001a87a  mov     eax, 800736CCh
0x18001a87f  jmp     loc_18001AA05
0x18001a884  mov     eax, 80073712h
0x18001a889  jmp     loc_18001AA05
0x18001a88e  mov     eax, 8007370Dh
0x18001a893  jmp     loc_18001AA05
0x18001a898  mov     eax, 8007370Ch
0x18001a89d  jmp     loc_18001AA05
0x18001a8a2  mov     eax, 8007370Bh
0x18001a8a7  jmp     loc_18001AA05
0x18001a8ac  mov     eax, 80073715h
0x18001a8b1  jmp     loc_18001AA05
0x18001a8b6  mov     eax, 0C0150024h
0x18001a8bb  cmp     ebx, eax
0x18001a8bd  jg      short loc_18001A925
0x18001a8bf  jz      short loc_18001A91B
0x18001a8c1  cmp     ebx, 0C015001Dh
0x18001a8c7  jz      short loc_18001A911
0x18001a8c9  cmp     ebx, 0C015001Eh
0x18001a8cf  jz      short loc_18001A907
0x18001a8d1  cmp     ebx, 0C015001Fh
0x18001a8d7  jz      short loc_18001A8FD
0x18001a8d9  cmp     ebx, 0C0150020h
0x18001a8df  jz      short loc_18001A8F3
0x18001a8e1  cmp     ebx, 0C0150021h
0x18001a8e7  jnz     short loc_18001A951
0x18001a8e9  mov     eax, 80073714h
0x18001a8ee  jmp     loc_18001AA05
0x18001a8f3  mov     eax, 80073713h
0x18001a8f8  jmp     loc_18001AA05
0x18001a8fd  mov     eax, 80073718h
0x18001a902  jmp     loc_18001AA05
0x18001a907  mov     eax, 80073717h
0x18001a90c  jmp     loc_18001AA05
0x18001a911  mov     eax, 80073716h
0x18001a916  jmp     loc_18001AA05
0x18001a91b  mov     eax, 8007371Bh
0x18001a920  jmp     loc_18001AA05
0x18001a925  cmp     ebx, 0C0150025h
0x18001a92b  jz      loc_18001AA00
0x18001a931  cmp     ebx, 0C0150026h
0x18001a937  jz      loc_18001A9F9
0x18001a93d  cmp     ebx, 0C0150027h
0x18001a943  jz      loc_18001A9F2
0x18001a949  test    ebx, ebx
0x18001a94b  jz      loc_18001A9EE
0x18001a951  mov     eax, ebx
0x18001a953  mov     ecx, 90000h
0x18001a958  and     eax, 0FFF0000h
0x18001a95d  cmp     eax, ecx
0x18001a95f  jnz     short loc_18001A978
0x18001a961  test    ebx, ebx
0x18001a963  jnz     short loc_18001A969
0x18001a965  xor     ebx, ebx
0x18001a967  jmp     short loc_18001A971
0x18001a969  and     ebx, 0C009FFFFh
0x18001a96f  or      ebx, ecx
0x18001a971  mov     eax, ebx
0x18001a973  jmp     loc_18001AA05
0x18001a978  cmp     eax, 80000h
0x18001a97d  jnz     short loc_18001A991
0x18001a97f  test    ebx, ebx
0x18001a981  jz      short loc_18001A965
0x18001a983  and     ebx, 0C00BFFFFh
0x18001a989  or      ebx, 0B0000h
0x18001a98f  jmp     short loc_18001A971
0x18001a991  mov     ecx, 180000h
0x18001a996  cmp     eax, ecx
0x18001a998  jnz     short loc_18001A9A6
0x18001a99a  test    ebx, ebx
0x18001a99c  jz      short loc_18001A965
0x18001a99e  and     ebx, 0C018FFFFh
0x18001a9a4  jmp     short loc_18001A96F
0x18001a9a6  mov     ecx, 0F0000h
0x18001a9ab  cmp     eax, ecx
0x18001a9ad  jnz     short loc_18001A9BB
0x18001a9af  test    ebx, ebx
0x18001a9b1  jz      short loc_18001A965
0x18001a9b3  and     ebx, 0C00FFFFFh
0x18001a9b9  jmp     short loc_18001A96F
0x18001a9bb  cmp     eax, 70000h
0x18001a9c0  jnz     short loc_18001A9D0
0x18001a9c2  movzx   eax, bx
0x18001a9c5  test    eax, eax
0x18001a9c7  jz      short loc_18001AA05
0x18001a9c9  or      eax, 80070000h
0x18001a9ce  jmp     short loc_18001AA05
0x18001a9d0  mov     ecx, ebx; Status
0x18001a9d2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001a9d8  cmp     eax, 13Dh
0x18001a9dd  jnz     short loc_18001A9E5
0x18001a9df  bts     ebx, 1Ch
0x18001a9e3  jmp     short loc_18001A971
0x18001a9e5  test    eax, eax
0x18001a9e7  jle     short loc_18001AA05
0x18001a9e9  movzx   eax, ax
0x18001a9ec  jmp     short loc_18001A9C9
0x18001a9ee  xor     eax, eax
0x18001a9f0  jmp     short loc_18001AA05
0x18001a9f2  mov     eax, 8007371Eh
0x18001a9f7  jmp     short loc_18001AA05
0x18001a9f9  mov     eax, 8007371Dh
0x18001a9fe  jmp     short loc_18001AA05
0x18001aa00  mov     eax, 8007371Ch
0x18001aa05  add     rsp, 20h
0x18001aa09  pop     rbx
0x18001aa0a  retn
```
