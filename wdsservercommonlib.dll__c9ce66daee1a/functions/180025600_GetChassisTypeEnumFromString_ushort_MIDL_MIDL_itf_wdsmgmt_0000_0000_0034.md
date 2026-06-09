# GetChassisTypeEnumFromString(ushort *,__MIDL___MIDL_itf_wdsmgmt_0000_0000_0034 *)

- ea: `0x180025600`
- end: `0x180025a07`
- name: `?GetChassisTypeEnumFromString@@YAKPEAGPEAW4__MIDL___MIDL_itf_wdsmgmt_0000_0000_0034@@@Z`
- size: `1031`
- prototype: `unsigned int __fastcall(wchar_t *String1, enum __MIDL___MIDL_itf_wdsmgmt_0000_0000_0034 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025600`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002561e`
- `msvcrt!_wcsicmp` at `0x180025643`
- `msvcrt!_wcsicmp` at `0x180025668`
- `msvcrt!_wcsicmp` at `0x18002568d`
- `msvcrt!_wcsicmp` at `0x1800256b2`
- `msvcrt!_wcsicmp` at `0x1800256d7`
- `msvcrt!_wcsicmp` at `0x1800256fc`
- `msvcrt!_wcsicmp` at `0x180025721`
- `msvcrt!_wcsicmp` at `0x180025746`
- `msvcrt!_wcsicmp` at `0x18002576b`
- `msvcrt!_wcsicmp` at `0x180025790`
- `msvcrt!_wcsicmp` at `0x1800257b5`
- `msvcrt!_wcsicmp` at `0x1800257da`
- `msvcrt!_wcsicmp` at `0x1800257ff`
- `msvcrt!_wcsicmp` at `0x180025824`
- `msvcrt!_wcsicmp` at `0x180025849`
- `msvcrt!_wcsicmp` at `0x18002586e`
- `msvcrt!_wcsicmp` at `0x180025893`
- `msvcrt!_wcsicmp` at `0x1800258b8`
- `msvcrt!_wcsicmp` at `0x1800258dd`
- `msvcrt!_wcsicmp` at `0x180025902`
- `msvcrt!_wcsicmp` at `0x180025927`
- `msvcrt!_wcsicmp` at `0x18002594c`
- `msvcrt!_wcsicmp` at `0x180025971`
- `msvcrt!_wcsicmp` at `0x180025993`
- `msvcrt!_wcsicmp` at `0x1800259b5`
- `msvcrt!_wcsicmp` at `0x1800259d7`
- `msvcrt!_wcsicmp` at `0x18002561e`
- `msvcrt!_wcsicmp` at `0x180025643`
- `msvcrt!_wcsicmp` at `0x180025668`
- `msvcrt!_wcsicmp` at `0x18002568d`
- `msvcrt!_wcsicmp` at `0x1800256b2`
- `msvcrt!_wcsicmp` at `0x1800256d7`
- `msvcrt!_wcsicmp` at `0x1800256fc`
- `msvcrt!_wcsicmp` at `0x180025721`
- `msvcrt!_wcsicmp` at `0x180025746`
- `msvcrt!_wcsicmp` at `0x18002576b`
- `msvcrt!_wcsicmp` at `0x180025790`
- `msvcrt!_wcsicmp` at `0x1800257b5`
- `msvcrt!_wcsicmp` at `0x1800257da`
- `msvcrt!_wcsicmp` at `0x1800257ff`
- `msvcrt!_wcsicmp` at `0x180025824`
- `msvcrt!_wcsicmp` at `0x180025849`
- `msvcrt!_wcsicmp` at `0x18002586e`
- `msvcrt!_wcsicmp` at `0x180025893`
- `msvcrt!_wcsicmp` at `0x1800258b8`
- `msvcrt!_wcsicmp` at `0x1800258dd`
- `msvcrt!_wcsicmp` at `0x180025902`
- `msvcrt!_wcsicmp` at `0x180025927`
- `msvcrt!_wcsicmp` at `0x18002594c`
- `msvcrt!_wcsicmp` at `0x180025971`
- `msvcrt!_wcsicmp` at `0x180025993`
- `msvcrt!_wcsicmp` at `0x1800259b5`
- `msvcrt!_wcsicmp` at `0x1800259d7`

## string_xrefs

- `0x180025942`: `rackmountchassis`
- `0x180025967`: `sealedcasecomputer`
- `0x1800259ab`: `compactpci`

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
0x180025600  mov     [rsp+arg_0], rbx
0x180025605  mov     [rsp+arg_8], rsi
0x18002560a  push    rdi
0x18002560b  sub     rsp, 20h
0x18002560f  mov     rbx, rdx
0x180025612  mov     rsi, rcx
0x180025615  lea     rdx, aOther; "other"
0x18002561c  xor     edi, edi
0x18002561e  call    cs:__imp__wcsicmp
0x180025625  nop     dword ptr [rax+rax+00h]
0x18002562a  test    eax, eax
0x18002562c  jnz     short loc_180025639
0x18002562e  mov     dword ptr [rbx], 1
0x180025634  jmp     loc_1800259F4
0x180025639  lea     rdx, aUnknownchassis; "unknownchassis"
0x180025640  mov     rcx, rsi; String1
0x180025643  call    cs:__imp__wcsicmp
0x18002564a  nop     dword ptr [rax+rax+00h]
0x18002564f  test    eax, eax
0x180025651  jnz     short loc_18002565E
0x180025653  mov     dword ptr [rbx], 2
0x180025659  jmp     loc_1800259F4
0x18002565e  lea     rdx, aDesktop; "desktop"
0x180025665  mov     rcx, rsi; String1
0x180025668  call    cs:__imp__wcsicmp
0x18002566f  nop     dword ptr [rax+rax+00h]
0x180025674  test    eax, eax
0x180025676  jnz     short loc_180025683
0x180025678  mov     dword ptr [rbx], 3
0x18002567e  jmp     loc_1800259F4
0x180025683  lea     rdx, aLowprofiledesk; "lowprofiledesktop"
0x18002568a  mov     rcx, rsi; String1
0x18002568d  call    cs:__imp__wcsicmp
0x180025694  nop     dword ptr [rax+rax+00h]
0x180025699  test    eax, eax
0x18002569b  jnz     short loc_1800256A8
0x18002569d  mov     dword ptr [rbx], 4
0x1800256a3  jmp     loc_1800259F4
0x1800256a8  lea     rdx, aPizzabox; "pizzabox"
0x1800256af  mov     rcx, rsi; String1
0x1800256b2  call    cs:__imp__wcsicmp
0x1800256b9  nop     dword ptr [rax+rax+00h]
0x1800256be  test    eax, eax
0x1800256c0  jnz     short loc_1800256CD
0x1800256c2  mov     dword ptr [rbx], 5
0x1800256c8  jmp     loc_1800259F4
0x1800256cd  lea     rdx, aMinitower; "minitower"
0x1800256d4  mov     rcx, rsi; String1
0x1800256d7  call    cs:__imp__wcsicmp
0x1800256de  nop     dword ptr [rax+rax+00h]
0x1800256e3  test    eax, eax
0x1800256e5  jnz     short loc_1800256F2
0x1800256e7  mov     dword ptr [rbx], 6
0x1800256ed  jmp     loc_1800259F4
0x1800256f2  lea     rdx, aTower; "tower"
0x1800256f9  mov     rcx, rsi; String1
0x1800256fc  call    cs:__imp__wcsicmp
0x180025703  nop     dword ptr [rax+rax+00h]
0x180025708  test    eax, eax
0x18002570a  jnz     short loc_180025717
0x18002570c  mov     dword ptr [rbx], 7
0x180025712  jmp     loc_1800259F4
0x180025717  lea     rdx, aPortable; "portable"
0x18002571e  mov     rcx, rsi; String1
0x180025721  call    cs:__imp__wcsicmp
0x180025728  nop     dword ptr [rax+rax+00h]
0x18002572d  test    eax, eax
0x18002572f  jnz     short loc_18002573C
0x180025731  mov     dword ptr [rbx], 8
0x180025737  jmp     loc_1800259F4
0x18002573c  lea     rdx, aLaptop; "laptop"
0x180025743  mov     rcx, rsi; String1
0x180025746  call    cs:__imp__wcsicmp
0x18002574d  nop     dword ptr [rax+rax+00h]
0x180025752  test    eax, eax
0x180025754  jnz     short loc_180025761
0x180025756  mov     dword ptr [rbx], 9
0x18002575c  jmp     loc_1800259F4
0x180025761  lea     rdx, aNotebook; "notebook"
0x180025768  mov     rcx, rsi; String1
0x18002576b  call    cs:__imp__wcsicmp
0x180025772  nop     dword ptr [rax+rax+00h]
0x180025777  test    eax, eax
0x180025779  jnz     short loc_180025786
0x18002577b  mov     dword ptr [rbx], 0Ah
0x180025781  jmp     loc_1800259F4
0x180025786  lea     rdx, aHandheld; "handheld"
0x18002578d  mov     rcx, rsi; String1
0x180025790  call    cs:__imp__wcsicmp
0x180025797  nop     dword ptr [rax+rax+00h]
0x18002579c  test    eax, eax
0x18002579e  jnz     short loc_1800257AB
0x1800257a0  mov     dword ptr [rbx], 0Bh
0x1800257a6  jmp     loc_1800259F4
0x1800257ab  lea     rdx, aDockingstation; "dockingstation"
0x1800257b2  mov     rcx, rsi; String1
0x1800257b5  call    cs:__imp__wcsicmp
0x1800257bc  nop     dword ptr [rax+rax+00h]
0x1800257c1  test    eax, eax
0x1800257c3  jnz     short loc_1800257D0
0x1800257c5  mov     dword ptr [rbx], 0Ch
0x1800257cb  jmp     loc_1800259F4
0x1800257d0  lea     rdx, aAllinone; "allinone"
0x1800257d7  mov     rcx, rsi; String1
0x1800257da  call    cs:__imp__wcsicmp
0x1800257e1  nop     dword ptr [rax+rax+00h]
0x1800257e6  test    eax, eax
0x1800257e8  jnz     short loc_1800257F5
0x1800257ea  mov     dword ptr [rbx], 0Dh
0x1800257f0  jmp     loc_1800259F4
0x1800257f5  lea     rdx, aSubnotebook; "subnotebook"
0x1800257fc  mov     rcx, rsi; String1
0x1800257ff  call    cs:__imp__wcsicmp
0x180025806  nop     dword ptr [rax+rax+00h]
0x18002580b  test    eax, eax
0x18002580d  jnz     short loc_18002581A
0x18002580f  mov     dword ptr [rbx], 0Eh
0x180025815  jmp     loc_1800259F4
0x18002581a  lea     rdx, aSpacesaving; "spacesaving"
0x180025821  mov     rcx, rsi; String1
0x180025824  call    cs:__imp__wcsicmp
0x18002582b  nop     dword ptr [rax+rax+00h]
0x180025830  test    eax, eax
0x180025832  jnz     short loc_18002583F
0x180025834  mov     dword ptr [rbx], 0Fh
0x18002583a  jmp     loc_1800259F4
0x18002583f  lea     rdx, aLunchbox; "lunchbox"
0x180025846  mov     rcx, rsi; String1
0x180025849  call    cs:__imp__wcsicmp
0x180025850  nop     dword ptr [rax+rax+00h]
0x180025855  test    eax, eax
0x180025857  jnz     short loc_180025864
0x180025859  mov     dword ptr [rbx], 10h
0x18002585f  jmp     loc_1800259F4
0x180025864  lea     rdx, aMainsystemchas; "mainsystemchassis"
0x18002586b  mov     rcx, rsi; String1
0x18002586e  call    cs:__imp__wcsicmp
0x180025875  nop     dword ptr [rax+rax+00h]
0x18002587a  test    eax, eax
0x18002587c  jnz     short loc_180025889
0x18002587e  mov     dword ptr [rbx], 11h
0x180025884  jmp     loc_1800259F4
0x180025889  lea     rdx, aExpansionchass; "expansionchassis"
0x180025890  mov     rcx, rsi; String1
0x180025893  call    cs:__imp__wcsicmp
0x18002589a  nop     dword ptr [rax+rax+00h]
0x18002589f  test    eax, eax
0x1800258a1  jnz     short loc_1800258AE
0x1800258a3  mov     dword ptr [rbx], 12h
0x1800258a9  jmp     loc_1800259F4
0x1800258ae  lea     rdx, aSubchassis; "subchassis"
0x1800258b5  mov     rcx, rsi; String1
0x1800258b8  call    cs:__imp__wcsicmp
0x1800258bf  nop     dword ptr [rax+rax+00h]
0x1800258c4  test    eax, eax
0x1800258c6  jnz     short loc_1800258D3
0x1800258c8  mov     dword ptr [rbx], 13h
0x1800258ce  jmp     loc_1800259F4
0x1800258d3  lea     rdx, aBusexpansionch; "busexpansionchassis"
0x1800258da  mov     rcx, rsi; String1
0x1800258dd  call    cs:__imp__wcsicmp
0x1800258e4  nop     dword ptr [rax+rax+00h]
0x1800258e9  test    eax, eax
0x1800258eb  jnz     short loc_1800258F8
0x1800258ed  mov     dword ptr [rbx], 14h
0x1800258f3  jmp     loc_1800259F4
0x1800258f8  lea     rdx, aPeripheralchas; "peripheralchassis"
0x1800258ff  mov     rcx, rsi; String1
0x180025902  call    cs:__imp__wcsicmp
0x180025909  nop     dword ptr [rax+rax+00h]
0x18002590e  test    eax, eax
0x180025910  jnz     short loc_18002591D
0x180025912  mov     dword ptr [rbx], 15h
0x180025918  jmp     loc_1800259F4
0x18002591d  lea     rdx, aStoragechassis; "storagechassis"
0x180025924  mov     rcx, rsi; String1
0x180025927  call    cs:__imp__wcsicmp
0x18002592e  nop     dword ptr [rax+rax+00h]
0x180025933  test    eax, eax
0x180025935  jnz     short loc_180025942
0x180025937  mov     dword ptr [rbx], 16h
0x18002593d  jmp     loc_1800259F4
0x180025942  lea     rdx, aRackmountchass; "rackmountchassis"
0x180025949  mov     rcx, rsi; String1
0x18002594c  call    cs:__imp__wcsicmp
0x180025953  nop     dword ptr [rax+rax+00h]
0x180025958  test    eax, eax
0x18002595a  jnz     short loc_180025967
0x18002595c  mov     dword ptr [rbx], 17h
0x180025962  jmp     loc_1800259F4
0x180025967  lea     rdx, aSealedcasecomp; "sealedcasecomputer"
0x18002596e  mov     rcx, rsi; String1
0x180025971  call    cs:__imp__wcsicmp
0x180025978  nop     dword ptr [rax+rax+00h]
0x18002597d  test    eax, eax
0x18002597f  jnz     short loc_180025989
0x180025981  mov     dword ptr [rbx], 18h
0x180025987  jmp     short loc_1800259F4
0x180025989  lea     rdx, aMultisystemcha; "multisystemchassis"
0x180025990  mov     rcx, rsi; String1
0x180025993  call    cs:__imp__wcsicmp
0x18002599a  nop     dword ptr [rax+rax+00h]
0x18002599f  test    eax, eax
0x1800259a1  jnz     short loc_1800259AB
0x1800259a3  mov     dword ptr [rbx], 19h
0x1800259a9  jmp     short loc_1800259F4
0x1800259ab  lea     rdx, aCompactpci; "compactpci"
0x1800259b2  mov     rcx, rsi; String1
0x1800259b5  call    cs:__imp__wcsicmp
0x1800259bc  nop     dword ptr [rax+rax+00h]
0x1800259c1  test    eax, eax
0x1800259c3  jnz     short loc_1800259CD
0x1800259c5  mov     dword ptr [rbx], 1Ah
0x1800259cb  jmp     short loc_1800259F4
0x1800259cd  lea     rdx, aAdvancedtca; "advancedtca"
0x1800259d4  mov     rcx, rsi; String1
0x1800259d7  call    cs:__imp__wcsicmp
0x1800259de  nop     dword ptr [rax+rax+00h]
0x1800259e3  test    eax, eax
0x1800259e5  jnz     short loc_1800259EF
0x1800259e7  mov     dword ptr [rbx], 1Bh
0x1800259ed  jmp     short loc_1800259F4
0x1800259ef  mov     edi, 57h ; 'W'
0x1800259f4  mov     rbx, [rsp+28h+arg_0]
0x1800259f9  mov     eax, edi
0x1800259fb  mov     rsi, [rsp+28h+arg_8]
0x180025a00  add     rsp, 20h
0x180025a04  pop     rdi
0x180025a05  retn
```
