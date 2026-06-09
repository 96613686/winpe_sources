# CClientUtils::StealthReadRegistryInt(ushort const *,ushort const *,int *,UT_REGREAD_LOCATION)

- ea: `0x1800097e0`
- end: `0x18000994c`
- name: `?StealthReadRegistryInt@CClientUtils@@UEAAHPEBG0PEAHW4UT_REGREAD_LOCATION@@@Z`
- size: `364`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003970`
- `0x1800053ac`
- `0x180008bc0`
- `0x1800095c8`
- `0x1800097e0`

## pseudocode

```c
__int64 __fastcall CClientUtils::StealthReadRegistryInt(__int64 a1, unsigned __int16 *a2, char *a3, BYTE *a4, int a5)
{
  unsigned int RegistryEntry; // edi
  int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v11; // eax

  RegistryEntry = 0;
  v6 = 0;
  if ( (a5 & 0xFFFFFFFD) == 0 )
  {
    if ( !(unsigned int)CClientUtils::RegistryEntryExists(HKEY_CURRENT_USER, a2, a3) )
    {
LABEL_8:
      v6 = 1;
      goto LABEL_9;
    }
    RegistryEntry = CClientUtils::ReadRegistryEntry(
                      HKEY_CURRENT_USER,
                      a2,
                      (const unsigned __int16 *)a3,
                      a4,
                      4u,
                      4,
                      0,
                      0);
    if ( !RegistryEntry )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_46feef82db693a9214302820d1cc2cac_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
      goto LABEL_8;
    }
  }
LABEL_9:
  if ( a5 == 1 || a5 == 2 && v6 )
  {
    if ( (unsigned int)CClientUtils::RegistryEntryExists(HKEY_LOCAL_MACHINE, a2, a3) )
    {
      RegistryEntry = CClientUtils::ReadRegistryEntry(
                        HKEY_LOCAL_MACHINE,
                        a2,
                        (const unsigned __int16 *)a3,
                        a4,
                        4u,
                        4,
                        0,
                        0);
      if ( !RegistryEntry
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_46feef82db693a9214302820d1cc2cac_Traceguids, v11);
      }
    }
  }
  return RegistryEntry;
}

```

## disassembly

```asm
0x1800097e0  push    rbx
0x1800097e2  push    rbp
0x1800097e3  push    rdi
0x1800097e4  push    r14
0x1800097e6  push    r15
0x1800097e8  sub     rsp, 40h
0x1800097ec  xor     edi, edi
0x1800097ee  xor     ebx, ebx
0x1800097f0  test    [rsp+68h+arg_20], 0FFFFFFFDh
0x1800097fb  mov     r15, r9
0x1800097fe  mov     rbp, r8
0x180009801  mov     r14, rdx
0x180009804  jnz     loc_18000988F
0x18000980a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009811  call    ?RegistryEntryExists@CClientUtils@@KAHPEAUHKEY__@@PEBG1@Z; CClientUtils::RegistryEntryExists(HKEY__ *,ushort const *,ushort const *)
0x180009816  test    eax, eax
0x180009818  jz      short loc_18000988A
0x18000981a  mov     [rsp+68h+var_30], ebx; int
0x18000981e  lea     eax, [rdi+4]
0x180009821  mov     [rsp+68h+var_38], rbx; unsigned int *
0x180009826  mov     r9, r15; lpData
0x180009829  mov     dword ptr [rsp+68h+var_40], eax; char
0x18000982d  mov     r8, rbp; unsigned __int16 *
0x180009830  mov     rdx, r14; unsigned __int16 *
0x180009833  mov     [rsp+68h+var_48], eax; int
0x180009837  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000983e  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x180009843  mov     edi, eax
0x180009845  test    eax, eax
0x180009847  jnz     short loc_18000988F
0x180009849  mov     rcx, cs:WPP_GLOBAL_Control
0x180009850  lea     rax, WPP_GLOBAL_Control
0x180009857  cmp     rcx, rax
0x18000985a  jz      short loc_18000988A
0x18000985c  test    byte ptr [rcx+1Ch], 1
0x180009860  jz      short loc_18000988A
0x180009862  cmp     byte ptr [rcx+19h], 4
0x180009866  jb      short loc_18000988A
0x180009868  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18000986d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009874  lea     edx, [rbx+10h]
0x180009877  mov     r9d, eax
0x18000987a  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009881  mov     rcx, [rcx+10h]
0x180009885  call    WPP_SF_D
0x18000988a  mov     ebx, 1
0x18000988f  cmp     [rsp+68h+arg_20], 1
0x180009897  jz      short loc_1800098AF
0x180009899  cmp     [rsp+68h+arg_20], 2
0x1800098a1  jnz     loc_18000993E
0x1800098a7  test    ebx, ebx
0x1800098a9  jz      loc_18000993E
0x1800098af  mov     r8, rbp; unsigned __int16 *
0x1800098b2  mov     rdx, r14; unsigned __int16 *
0x1800098b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800098bc  call    ?RegistryEntryExists@CClientUtils@@KAHPEAUHKEY__@@PEBG1@Z; CClientUtils::RegistryEntryExists(HKEY__ *,ushort const *,ushort const *)
0x1800098c1  test    eax, eax
0x1800098c3  jz      short loc_18000993E
0x1800098c5  mov     [rsp+68h+var_30], 0; int
0x1800098cd  mov     ebx, 4
0x1800098d2  mov     [rsp+68h+var_38], 0; unsigned int *
0x1800098db  mov     r9, r15; lpData
0x1800098de  mov     dword ptr [rsp+68h+var_40], ebx; char
0x1800098e2  mov     r8, rbp; unsigned __int16 *
0x1800098e5  mov     rdx, r14; unsigned __int16 *
0x1800098e8  mov     [rsp+68h+var_48], ebx; int
0x1800098ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800098f3  call    ?ReadRegistryEntry@CClientUtils@@KAHPEAUHKEY__@@PEBG1PEAEHJPEAKH@Z; CClientUtils::ReadRegistryEntry(HKEY__ *,ushort const *,ushort const *,uchar *,int,long,ulong *,int)
0x1800098f8  mov     edi, eax
0x1800098fa  test    eax, eax
0x1800098fc  jnz     short loc_18000993E
0x1800098fe  mov     rax, cs:WPP_GLOBAL_Control
0x180009905  lea     rcx, WPP_GLOBAL_Control
0x18000990c  cmp     rax, rcx
0x18000990f  jz      short loc_18000993E
0x180009911  test    byte ptr [rax+1Ch], 1
0x180009915  jz      short loc_18000993E
0x180009917  cmp     [rax+19h], bl
0x18000991a  jb      short loc_18000993E
0x18000991c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180009921  mov     rcx, cs:WPP_GLOBAL_Control
0x180009928  lea     edx, [rbx+0Dh]
0x18000992b  mov     r9d, eax
0x18000992e  lea     r8, WPP_46feef82db693a9214302820d1cc2cac_Traceguids
0x180009935  mov     rcx, [rcx+10h]
0x180009939  call    WPP_SF_D
0x18000993e  mov     eax, edi
0x180009940  add     rsp, 40h
0x180009944  pop     r15
0x180009946  pop     r14
0x180009948  pop     rdi
0x180009949  pop     rbp
0x18000994a  pop     rbx
0x18000994b  retn
```
