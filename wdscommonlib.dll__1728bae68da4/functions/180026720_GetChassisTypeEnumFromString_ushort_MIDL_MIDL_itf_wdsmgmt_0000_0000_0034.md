# GetChassisTypeEnumFromString(ushort *,__MIDL___MIDL_itf_wdsmgmt_0000_0000_0034 *)

- ea: `0x180026720`
- end: `0x180026b27`
- name: `?GetChassisTypeEnumFromString@@YAKPEAGPEAW4__MIDL___MIDL_itf_wdsmgmt_0000_0000_0034@@@Z`
- size: `1031`
- prototype: `unsigned int __fastcall(wchar_t *String1, enum __MIDL___MIDL_itf_wdsmgmt_0000_0000_0034 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026720`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002673e`
- `msvcrt!_wcsicmp` at `0x180026763`
- `msvcrt!_wcsicmp` at `0x180026788`
- `msvcrt!_wcsicmp` at `0x1800267ad`
- `msvcrt!_wcsicmp` at `0x1800267d2`
- `msvcrt!_wcsicmp` at `0x1800267f7`
- `msvcrt!_wcsicmp` at `0x18002681c`
- `msvcrt!_wcsicmp` at `0x180026841`
- `msvcrt!_wcsicmp` at `0x180026866`
- `msvcrt!_wcsicmp` at `0x18002688b`
- `msvcrt!_wcsicmp` at `0x1800268b0`
- `msvcrt!_wcsicmp` at `0x1800268d5`
- `msvcrt!_wcsicmp` at `0x1800268fa`
- `msvcrt!_wcsicmp` at `0x18002691f`
- `msvcrt!_wcsicmp` at `0x180026944`
- `msvcrt!_wcsicmp` at `0x180026969`
- `msvcrt!_wcsicmp` at `0x18002698e`
- `msvcrt!_wcsicmp` at `0x1800269b3`
- `msvcrt!_wcsicmp` at `0x1800269d8`
- `msvcrt!_wcsicmp` at `0x1800269fd`
- `msvcrt!_wcsicmp` at `0x180026a22`
- `msvcrt!_wcsicmp` at `0x180026a47`
- `msvcrt!_wcsicmp` at `0x180026a6c`
- `msvcrt!_wcsicmp` at `0x180026a91`
- `msvcrt!_wcsicmp` at `0x180026ab3`
- `msvcrt!_wcsicmp` at `0x180026ad5`
- `msvcrt!_wcsicmp` at `0x180026af7`
- `msvcrt!_wcsicmp` at `0x18002673e`
- `msvcrt!_wcsicmp` at `0x180026763`
- `msvcrt!_wcsicmp` at `0x180026788`
- `msvcrt!_wcsicmp` at `0x1800267ad`
- `msvcrt!_wcsicmp` at `0x1800267d2`
- `msvcrt!_wcsicmp` at `0x1800267f7`
- `msvcrt!_wcsicmp` at `0x18002681c`
- `msvcrt!_wcsicmp` at `0x180026841`
- `msvcrt!_wcsicmp` at `0x180026866`
- `msvcrt!_wcsicmp` at `0x18002688b`
- `msvcrt!_wcsicmp` at `0x1800268b0`
- `msvcrt!_wcsicmp` at `0x1800268d5`
- `msvcrt!_wcsicmp` at `0x1800268fa`
- `msvcrt!_wcsicmp` at `0x18002691f`
- `msvcrt!_wcsicmp` at `0x180026944`
- `msvcrt!_wcsicmp` at `0x180026969`
- `msvcrt!_wcsicmp` at `0x18002698e`
- `msvcrt!_wcsicmp` at `0x1800269b3`
- `msvcrt!_wcsicmp` at `0x1800269d8`
- `msvcrt!_wcsicmp` at `0x1800269fd`
- `msvcrt!_wcsicmp` at `0x180026a22`
- `msvcrt!_wcsicmp` at `0x180026a47`
- `msvcrt!_wcsicmp` at `0x180026a6c`
- `msvcrt!_wcsicmp` at `0x180026a91`
- `msvcrt!_wcsicmp` at `0x180026ab3`
- `msvcrt!_wcsicmp` at `0x180026ad5`
- `msvcrt!_wcsicmp` at `0x180026af7`

## string_xrefs

- `0x180026a62`: `rackmountchassis`
- `0x180026a87`: `sealedcasecomputer`
- `0x180026acb`: `compactpci`

## pseudocode

```c
__int64 __fastcall GetChassisTypeEnumFromString(wchar_t *String1, enum __MIDL___MIDL_itf_wdsmgmt_0000_0000_0034 *a2)
{
  unsigned int v4; // edi

  v4 = 0;
  if ( _wcsicmp(String1, L"other") )
  {
    if ( _wcsicmp(String1, L"unknownchassis") )
    {
      if ( _wcsicmp(String1, L"desktop") )
      {
        if ( _wcsicmp(String1, L"lowprofiledesktop") )
        {
          if ( _wcsicmp(String1, L"pizzabox") )
          {
            if ( _wcsicmp(String1, L"minitower") )
            {
              if ( _wcsicmp(String1, L"tower") )
              {
                if ( _wcsicmp(String1, L"portable") )
                {
                  if ( _wcsicmp(String1, L"laptop") )
                  {
                    if ( _wcsicmp(String1, L"notebook") )
                    {
                      if ( _wcsicmp(String1, L"handheld") )
                      {
                        if ( _wcsicmp(String1, L"dockingstation") )
                        {
                          if ( _wcsicmp(String1, L"allinone") )
                          {
                            if ( _wcsicmp(String1, L"subnotebook") )
                            {
                              if ( _wcsicmp(String1, L"spacesaving") )
                              {
                                if ( _wcsicmp(String1, L"lunchbox") )
                                {
                                  if ( _wcsicmp(String1, L"mainsystemchassis") )
                                  {
                                    if ( _wcsicmp(String1, L"expansionchassis") )
                                    {
                                      if ( _wcsicmp(String1, L"subchassis") )
                                      {
                                        if ( _wcsicmp(String1, L"busexpansionchassis") )
                                        {
                                          if ( _wcsicmp(String1, L"peripheralchassis") )
                                          {
                                            if ( _wcsicmp(String1, L"storagechassis") )
                                            {
                                              if ( _wcsicmp(String1, L"rackmountchassis") )
                                              {
                                                if ( _wcsicmp(String1, L"sealedcasecomputer") )
                                                {
                                                  if ( _wcsicmp(String1, L"multisystemchassis") )
                                                  {
                                                    if ( _wcsicmp(String1, L"compactpci") )
                                                    {
                                                      if ( _wcsicmp(String1, L"advancedtca") )
                                                        return 87;
                                                      else
                                                        *(_DWORD *)a2 = 27;
                                                    }
                                                    else
                                                    {
                                                      *(_DWORD *)a2 = 26;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    *(_DWORD *)a2 = 25;
                                                  }
                                                }
                                                else
                                                {
                                                  *(_DWORD *)a2 = 24;
                                                }
                                              }
                                              else
                                              {
                                                *(_DWORD *)a2 = 23;
                                              }
                                            }
                                            else
                                            {
                                              *(_DWORD *)a2 = 22;
                                            }
                                          }
                                          else
                                          {
                                            *(_DWORD *)a2 = 21;
                                          }
                                        }
                                        else
                                        {
                                          *(_DWORD *)a2 = 20;
                                        }
                                      }
                                      else
                                      {
                                        *(_DWORD *)a2 = 19;
                                      }
                                    }
                                    else
                                    {
                                      *(_DWORD *)a2 = 18;
                                    }
                                  }
                                  else
                                  {
                                    *(_DWORD *)a2 = 17;
                                  }
                                }
                                else
                                {
                                  *(_DWORD *)a2 = 16;
                                }
                              }
                              else
                              {
                                *(_DWORD *)a2 = 15;
                              }
                            }
                            else
                            {
                              *(_DWORD *)a2 = 14;
                            }
                          }
                          else
                          {
                            *(_DWORD *)a2 = 13;
                          }
                        }
                        else
                        {
                          *(_DWORD *)a2 = 12;
                        }
                      }
                      else
                      {
                        *(_DWORD *)a2 = 11;
                      }
                    }
                    else
                    {
                      *(_DWORD *)a2 = 10;
                    }
                  }
                  else
                  {
                    *(_DWORD *)a2 = 9;
                  }
                }
                else
                {
                  *(_DWORD *)a2 = 8;
                }
              }
              else
              {
                *(_DWORD *)a2 = 7;
              }
            }
            else
            {
              *(_DWORD *)a2 = 6;
            }
          }
          else
          {
            *(_DWORD *)a2 = 5;
          }
        }
        else
        {
          *(_DWORD *)a2 = 4;
        }
      }
      else
      {
        *(_DWORD *)a2 = 3;
      }
    }
    else
    {
      *(_DWORD *)a2 = 2;
    }
  }
  else
  {
    *(_DWORD *)a2 = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x180026720  mov     [rsp+arg_0], rbx
0x180026725  mov     [rsp+arg_8], rsi
0x18002672a  push    rdi
0x18002672b  sub     rsp, 20h
0x18002672f  mov     rbx, rdx
0x180026732  mov     rsi, rcx
0x180026735  lea     rdx, aOther; "other"
0x18002673c  xor     edi, edi
0x18002673e  call    cs:__imp__wcsicmp
0x180026745  nop     dword ptr [rax+rax+00h]
0x18002674a  test    eax, eax
0x18002674c  jnz     short loc_180026759
0x18002674e  mov     dword ptr [rbx], 1
0x180026754  jmp     loc_180026B14
0x180026759  lea     rdx, aUnknownchassis; "unknownchassis"
0x180026760  mov     rcx, rsi; String1
0x180026763  call    cs:__imp__wcsicmp
0x18002676a  nop     dword ptr [rax+rax+00h]
0x18002676f  test    eax, eax
0x180026771  jnz     short loc_18002677E
0x180026773  mov     dword ptr [rbx], 2
0x180026779  jmp     loc_180026B14
0x18002677e  lea     rdx, aDesktop; "desktop"
0x180026785  mov     rcx, rsi; String1
0x180026788  call    cs:__imp__wcsicmp
0x18002678f  nop     dword ptr [rax+rax+00h]
0x180026794  test    eax, eax
0x180026796  jnz     short loc_1800267A3
0x180026798  mov     dword ptr [rbx], 3
0x18002679e  jmp     loc_180026B14
0x1800267a3  lea     rdx, aLowprofiledesk; "lowprofiledesktop"
0x1800267aa  mov     rcx, rsi; String1
0x1800267ad  call    cs:__imp__wcsicmp
0x1800267b4  nop     dword ptr [rax+rax+00h]
0x1800267b9  test    eax, eax
0x1800267bb  jnz     short loc_1800267C8
0x1800267bd  mov     dword ptr [rbx], 4
0x1800267c3  jmp     loc_180026B14
0x1800267c8  lea     rdx, aPizzabox; "pizzabox"
0x1800267cf  mov     rcx, rsi; String1
0x1800267d2  call    cs:__imp__wcsicmp
0x1800267d9  nop     dword ptr [rax+rax+00h]
0x1800267de  test    eax, eax
0x1800267e0  jnz     short loc_1800267ED
0x1800267e2  mov     dword ptr [rbx], 5
0x1800267e8  jmp     loc_180026B14
0x1800267ed  lea     rdx, aMinitower; "minitower"
0x1800267f4  mov     rcx, rsi; String1
0x1800267f7  call    cs:__imp__wcsicmp
0x1800267fe  nop     dword ptr [rax+rax+00h]
0x180026803  test    eax, eax
0x180026805  jnz     short loc_180026812
0x180026807  mov     dword ptr [rbx], 6
0x18002680d  jmp     loc_180026B14
0x180026812  lea     rdx, aTower; "tower"
0x180026819  mov     rcx, rsi; String1
0x18002681c  call    cs:__imp__wcsicmp
0x180026823  nop     dword ptr [rax+rax+00h]
0x180026828  test    eax, eax
0x18002682a  jnz     short loc_180026837
0x18002682c  mov     dword ptr [rbx], 7
0x180026832  jmp     loc_180026B14
0x180026837  lea     rdx, aPortable; "portable"
0x18002683e  mov     rcx, rsi; String1
0x180026841  call    cs:__imp__wcsicmp
0x180026848  nop     dword ptr [rax+rax+00h]
0x18002684d  test    eax, eax
0x18002684f  jnz     short loc_18002685C
0x180026851  mov     dword ptr [rbx], 8
0x180026857  jmp     loc_180026B14
0x18002685c  lea     rdx, aLaptop; "laptop"
0x180026863  mov     rcx, rsi; String1
0x180026866  call    cs:__imp__wcsicmp
0x18002686d  nop     dword ptr [rax+rax+00h]
0x180026872  test    eax, eax
0x180026874  jnz     short loc_180026881
0x180026876  mov     dword ptr [rbx], 9
0x18002687c  jmp     loc_180026B14
0x180026881  lea     rdx, aNotebook; "notebook"
0x180026888  mov     rcx, rsi; String1
0x18002688b  call    cs:__imp__wcsicmp
0x180026892  nop     dword ptr [rax+rax+00h]
0x180026897  test    eax, eax
0x180026899  jnz     short loc_1800268A6
0x18002689b  mov     dword ptr [rbx], 0Ah
0x1800268a1  jmp     loc_180026B14
0x1800268a6  lea     rdx, aHandheld; "handheld"
0x1800268ad  mov     rcx, rsi; String1
0x1800268b0  call    cs:__imp__wcsicmp
0x1800268b7  nop     dword ptr [rax+rax+00h]
0x1800268bc  test    eax, eax
0x1800268be  jnz     short loc_1800268CB
0x1800268c0  mov     dword ptr [rbx], 0Bh
0x1800268c6  jmp     loc_180026B14
0x1800268cb  lea     rdx, aDockingstation; "dockingstation"
0x1800268d2  mov     rcx, rsi; String1
0x1800268d5  call    cs:__imp__wcsicmp
0x1800268dc  nop     dword ptr [rax+rax+00h]
0x1800268e1  test    eax, eax
0x1800268e3  jnz     short loc_1800268F0
0x1800268e5  mov     dword ptr [rbx], 0Ch
0x1800268eb  jmp     loc_180026B14
0x1800268f0  lea     rdx, aAllinone; "allinone"
0x1800268f7  mov     rcx, rsi; String1
0x1800268fa  call    cs:__imp__wcsicmp
0x180026901  nop     dword ptr [rax+rax+00h]
0x180026906  test    eax, eax
0x180026908  jnz     short loc_180026915
0x18002690a  mov     dword ptr [rbx], 0Dh
0x180026910  jmp     loc_180026B14
0x180026915  lea     rdx, aSubnotebook; "subnotebook"
0x18002691c  mov     rcx, rsi; String1
0x18002691f  call    cs:__imp__wcsicmp
0x180026926  nop     dword ptr [rax+rax+00h]
0x18002692b  test    eax, eax
0x18002692d  jnz     short loc_18002693A
0x18002692f  mov     dword ptr [rbx], 0Eh
0x180026935  jmp     loc_180026B14
0x18002693a  lea     rdx, aSpacesaving; "spacesaving"
0x180026941  mov     rcx, rsi; String1
0x180026944  call    cs:__imp__wcsicmp
0x18002694b  nop     dword ptr [rax+rax+00h]
0x180026950  test    eax, eax
0x180026952  jnz     short loc_18002695F
0x180026954  mov     dword ptr [rbx], 0Fh
0x18002695a  jmp     loc_180026B14
0x18002695f  lea     rdx, aLunchbox; "lunchbox"
0x180026966  mov     rcx, rsi; String1
0x180026969  call    cs:__imp__wcsicmp
0x180026970  nop     dword ptr [rax+rax+00h]
0x180026975  test    eax, eax
0x180026977  jnz     short loc_180026984
0x180026979  mov     dword ptr [rbx], 10h
0x18002697f  jmp     loc_180026B14
0x180026984  lea     rdx, aMainsystemchas; "mainsystemchassis"
0x18002698b  mov     rcx, rsi; String1
0x18002698e  call    cs:__imp__wcsicmp
0x180026995  nop     dword ptr [rax+rax+00h]
0x18002699a  test    eax, eax
0x18002699c  jnz     short loc_1800269A9
0x18002699e  mov     dword ptr [rbx], 11h
0x1800269a4  jmp     loc_180026B14
0x1800269a9  lea     rdx, aExpansionchass; "expansionchassis"
0x1800269b0  mov     rcx, rsi; String1
0x1800269b3  call    cs:__imp__wcsicmp
0x1800269ba  nop     dword ptr [rax+rax+00h]
0x1800269bf  test    eax, eax
0x1800269c1  jnz     short loc_1800269CE
0x1800269c3  mov     dword ptr [rbx], 12h
0x1800269c9  jmp     loc_180026B14
0x1800269ce  lea     rdx, aSubchassis; "subchassis"
0x1800269d5  mov     rcx, rsi; String1
0x1800269d8  call    cs:__imp__wcsicmp
0x1800269df  nop     dword ptr [rax+rax+00h]
0x1800269e4  test    eax, eax
0x1800269e6  jnz     short loc_1800269F3
0x1800269e8  mov     dword ptr [rbx], 13h
0x1800269ee  jmp     loc_180026B14
0x1800269f3  lea     rdx, aBusexpansionch; "busexpansionchassis"
0x1800269fa  mov     rcx, rsi; String1
0x1800269fd  call    cs:__imp__wcsicmp
0x180026a04  nop     dword ptr [rax+rax+00h]
0x180026a09  test    eax, eax
0x180026a0b  jnz     short loc_180026A18
0x180026a0d  mov     dword ptr [rbx], 14h
0x180026a13  jmp     loc_180026B14
0x180026a18  lea     rdx, aPeripheralchas; "peripheralchassis"
0x180026a1f  mov     rcx, rsi; String1
0x180026a22  call    cs:__imp__wcsicmp
0x180026a29  nop     dword ptr [rax+rax+00h]
0x180026a2e  test    eax, eax
0x180026a30  jnz     short loc_180026A3D
0x180026a32  mov     dword ptr [rbx], 15h
0x180026a38  jmp     loc_180026B14
0x180026a3d  lea     rdx, aStoragechassis; "storagechassis"
0x180026a44  mov     rcx, rsi; String1
0x180026a47  call    cs:__imp__wcsicmp
0x180026a4e  nop     dword ptr [rax+rax+00h]
0x180026a53  test    eax, eax
0x180026a55  jnz     short loc_180026A62
0x180026a57  mov     dword ptr [rbx], 16h
0x180026a5d  jmp     loc_180026B14
0x180026a62  lea     rdx, aRackmountchass; "rackmountchassis"
0x180026a69  mov     rcx, rsi; String1
0x180026a6c  call    cs:__imp__wcsicmp
0x180026a73  nop     dword ptr [rax+rax+00h]
0x180026a78  test    eax, eax
0x180026a7a  jnz     short loc_180026A87
0x180026a7c  mov     dword ptr [rbx], 17h
0x180026a82  jmp     loc_180026B14
0x180026a87  lea     rdx, aSealedcasecomp; "sealedcasecomputer"
0x180026a8e  mov     rcx, rsi; String1
0x180026a91  call    cs:__imp__wcsicmp
0x180026a98  nop     dword ptr [rax+rax+00h]
0x180026a9d  test    eax, eax
0x180026a9f  jnz     short loc_180026AA9
0x180026aa1  mov     dword ptr [rbx], 18h
0x180026aa7  jmp     short loc_180026B14
0x180026aa9  lea     rdx, aMultisystemcha; "multisystemchassis"
0x180026ab0  mov     rcx, rsi; String1
0x180026ab3  call    cs:__imp__wcsicmp
0x180026aba  nop     dword ptr [rax+rax+00h]
0x180026abf  test    eax, eax
0x180026ac1  jnz     short loc_180026ACB
0x180026ac3  mov     dword ptr [rbx], 19h
0x180026ac9  jmp     short loc_180026B14
0x180026acb  lea     rdx, aCompactpci; "compactpci"
0x180026ad2  mov     rcx, rsi; String1
0x180026ad5  call    cs:__imp__wcsicmp
0x180026adc  nop     dword ptr [rax+rax+00h]
0x180026ae1  test    eax, eax
0x180026ae3  jnz     short loc_180026AED
0x180026ae5  mov     dword ptr [rbx], 1Ah
0x180026aeb  jmp     short loc_180026B14
0x180026aed  lea     rdx, aAdvancedtca; "advancedtca"
0x180026af4  mov     rcx, rsi; String1
0x180026af7  call    cs:__imp__wcsicmp
0x180026afe  nop     dword ptr [rax+rax+00h]
0x180026b03  test    eax, eax
0x180026b05  jnz     short loc_180026B0F
0x180026b07  mov     dword ptr [rbx], 1Bh
0x180026b0d  jmp     short loc_180026B14
0x180026b0f  mov     edi, 57h ; 'W'
0x180026b14  mov     rbx, [rsp+28h+arg_0]
0x180026b19  mov     eax, edi
0x180026b1b  mov     rsi, [rsp+28h+arg_8]
0x180026b20  add     rsp, 20h
0x180026b24  pop     rdi
0x180026b25  retn
```
