# WLNotifyInit

- ea: `0x18016246c`
- end: `0x1801627a2`
- name: `WLNotifyInit`
- size: `822`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180117260`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180107330`
- `0x18016246c`
- `0x180201fe4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18016259a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801625ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18016263e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180162690`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18016259a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801625ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18016263e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180162690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801625ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801625fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180162650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801626a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801625ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801625fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180162650`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801626a2`
- `DSROLE!DsRoleFreeMemory` at `0x180162762`
- `DSROLE!DsRoleFreeMemory` at `0x180162762`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180162524`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180162524`
- `SYSNTFY!SysNotifyStartServer` at `0x180162717`
- `SYSNTFY!SysNotifyStartServer` at `0x180162717`

## pseudocode

```c
__int64 WLNotifyInit()
{
  PVOID *v0; // rcx
  unsigned int v1; // ebx
  DWORD PrimaryDomainInformation; // eax
  int v3; // edx
  __int64 v4; // rdx
  _DWORD v6[8]; // [rsp+30h] [rbp-A8h] BYREF
  __int64 (__fastcall *v7)(); // [rsp+50h] [rbp-88h]
  __int64 (__fastcall *v8)(); // [rsp+88h] [rbp-50h]
  PBYTE Buffer; // [rsp+E0h] [rbp+8h] BYREF

  memset_0(v6, 0, 0x80u);
  Buffer = 0;
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 14, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !dword_1802A31D0 )
  {
    PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
    v1 = PrimaryDomainInformation;
    if ( PrimaryDomainInformation )
    {
      v0 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*((_BYTE *)WPP_GLOBAL_Control + 105)
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
        goto LABEL_43;
      }
      v4 = 16;
    }
    else
    {
      g_bDomainJoined = (*(_DWORD *)Buffer & 0xFFFFFFFD) != 0;
      StSetTimelyKey(0, v3);
      qword_1802A31C8 = CreateEventW(0, 1, 0, 0);
      if ( qword_1802A31C8 )
      {
        qword_1802A31B8 = CreateEventW(0, 1, 0, 0);
        if ( qword_1802A31B8 )
        {
          qword_1802A31B0 = CreateEventW(0, 1, 0, 0);
          if ( qword_1802A31B0 )
          {
            qword_1802A31A0 = CreateEventW(0, 1, 0, 0);
            if ( qword_1802A31A0 )
            {
              v6[0] = 1;
              v7 = WLNotifyOnLogon;
              v8 = WLNotifyOnLogoff;
              PrimaryDomainInformation = SysNotifyStartServer("Wlansvc", 128, v6, 0, &qword_1802A31D8);
              v1 = PrimaryDomainInformation;
              if ( !PrimaryDomainInformation )
              {
                dword_1802A31D0 = 1;
                goto LABEL_42;
              }
              v0 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || !*((_BYTE *)WPP_GLOBAL_Control + 105)
                || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
              {
                goto LABEL_43;
              }
              v4 = 21;
            }
            else
            {
              PrimaryDomainInformation = GetLastError();
              v1 = PrimaryDomainInformation;
              v0 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || !*((_BYTE *)WPP_GLOBAL_Control + 105)
                || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
              {
                goto LABEL_43;
              }
              v4 = 20;
            }
          }
          else
          {
            PrimaryDomainInformation = GetLastError();
            v1 = PrimaryDomainInformation;
            v0 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || !*((_BYTE *)WPP_GLOBAL_Control + 105)
              || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
            {
              goto LABEL_43;
            }
            v4 = 19;
          }
        }
        else
        {
          PrimaryDomainInformation = GetLastError();
          v1 = PrimaryDomainInformation;
          v0 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || !*((_BYTE *)WPP_GLOBAL_Control + 105)
            || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          {
            goto LABEL_43;
          }
          v4 = 18;
        }
      }
      else
      {
        PrimaryDomainInformation = GetLastError();
        v1 = PrimaryDomainInformation;
        v0 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || !*((_BYTE *)WPP_GLOBAL_Control + 105)
          || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        {
          goto LABEL_43;
        }
        v4 = 17;
      }
    }
    WPP_SF_d(v0[12], v4, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids, PrimaryDomainInformation);
    goto LABEL_42;
  }
  v1 = 1247;
  if ( v0 != &WPP_GLOBAL_Control && *((_BYTE *)v0 + 105) && (*((_BYTE *)v0 + 108) & 1) != 0 )
  {
    WPP_SF_(v0[12], 15, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids);
LABEL_42:
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_43:
  if ( Buffer )
  {
    DsRoleFreeMemory(Buffer);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v0 != &WPP_GLOBAL_Control && *((_BYTE *)v0 + 105) >= 4u && (*((_BYTE *)v0 + 108) & 1) != 0 )
    WPP_SF_d(v0[12], 22, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18016246c  push    rbx
0x18016246e  push    rbp
0x18016246f  push    rsi
0x180162470  push    rdi
0x180162471  sub     rsp, 0B8h
0x180162478  xor     edx, edx; Val
0x18016247a  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18016247f  mov     r8d, 80h; Size
0x180162485  call    memset_0
0x18016248a  mov     [rsp+0D8h+Buffer], 0
0x180162496  mov     rcx, cs:WPP_GLOBAL_Control
0x18016249d  lea     rsi, WPP_GLOBAL_Control
0x1801624a4  lea     rbp, WPP_e6253edaf4023fbc0336011795d1ecda_Traceguids
0x1801624ab  mov     edi, 1
0x1801624b0  cmp     rcx, rsi
0x1801624b3  jz      short loc_1801624D7
0x1801624b5  cmp     byte ptr [rcx+69h], 4
0x1801624b9  jb      short loc_1801624D7
0x1801624bb  test    [rcx+6Ch], dil
0x1801624bf  jz      short loc_1801624D7
0x1801624c1  mov     rcx, [rcx+60h]
0x1801624c5  lea     edx, [rdi+0Dh]
0x1801624c8  mov     r8, rbp
0x1801624cb  call    WPP_SF_
0x1801624d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801624d7  cmp     cs:dword_1802A31D0, 0
0x1801624de  jz      short loc_180162518
0x1801624e0  mov     ebx, 4DFh
0x1801624e5  cmp     rcx, rsi
0x1801624e8  jz      loc_180162752
0x1801624ee  cmp     [rcx+69h], dil
0x1801624f2  jb      loc_180162752
0x1801624f8  test    [rcx+6Ch], dil
0x1801624fc  jz      loc_180162752
0x180162502  mov     rcx, [rcx+60h]
0x180162506  mov     edx, 0Fh
0x18016250b  mov     r8, rbp
0x18016250e  call    WPP_SF_
0x180162513  jmp     loc_18016274B
0x180162518  lea     r8, [rsp+0D8h+Buffer]; Buffer
0x180162520  mov     edx, edi; InfoLevel
0x180162522  xor     ecx, ecx; lpServer
0x180162524  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x18016252a  mov     ebx, eax
0x18016252c  test    eax, eax
0x18016252e  jz      short loc_18016256D
0x180162530  mov     rcx, cs:WPP_GLOBAL_Control
0x180162537  cmp     rcx, rsi
0x18016253a  jz      loc_180162752
0x180162540  cmp     [rcx+69h], dil
0x180162544  jb      loc_180162752
0x18016254a  test    [rcx+6Ch], dil
0x18016254e  jz      loc_180162752
0x180162554  mov     edx, 10h
0x180162559  mov     rcx, [rcx+60h]
0x18016255d  mov     r9d, eax
0x180162560  mov     r8, rbp
0x180162563  call    WPP_SF_d
0x180162568  jmp     loc_18016274B
0x18016256d  mov     rax, [rsp+0D8h+Buffer]
0x180162575  test    dword ptr [rax], 0FFFFFFFDh
0x18016257b  mov     eax, 0
0x180162580  setnz   al
0x180162583  xor     ecx, ecx; int
0x180162585  mov     cs:g_bDomainJoined, eax
0x18016258b  call    ?StSetTimelyKey@@YAKHH@Z; StSetTimelyKey(int,int)
0x180162590  xor     r9d, r9d; lpName
0x180162593  xor     r8d, r8d; bInitialState
0x180162596  mov     edx, edi; bManualReset
0x180162598  xor     ecx, ecx; lpEventAttributes
0x18016259a  call    cs:__imp_CreateEventW
0x1801625a0  mov     cs:qword_1802A31C8, rax
0x1801625a7  test    rax, rax
0x1801625aa  jnz     short loc_1801625E2
0x1801625ac  call    cs:__imp_GetLastError
0x1801625b2  mov     ebx, eax
0x1801625b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801625bb  cmp     rcx, rsi
0x1801625be  jz      loc_180162752
0x1801625c4  cmp     [rcx+69h], dil
0x1801625c8  jb      loc_180162752
0x1801625ce  test    [rcx+6Ch], dil
0x1801625d2  jz      loc_180162752
0x1801625d8  mov     edx, 11h
0x1801625dd  jmp     loc_180162559
0x1801625e2  xor     r9d, r9d; lpName
0x1801625e5  xor     r8d, r8d; bInitialState
0x1801625e8  mov     edx, edi; bManualReset
0x1801625ea  xor     ecx, ecx; lpEventAttributes
0x1801625ec  call    cs:__imp_CreateEventW
0x1801625f2  mov     cs:qword_1802A31B8, rax
0x1801625f9  test    rax, rax
0x1801625fc  jnz     short loc_180162634
0x1801625fe  call    cs:__imp_GetLastError
0x180162604  mov     ebx, eax
0x180162606  mov     rcx, cs:WPP_GLOBAL_Control
0x18016260d  cmp     rcx, rsi
0x180162610  jz      loc_180162752
0x180162616  cmp     [rcx+69h], dil
0x18016261a  jb      loc_180162752
0x180162620  test    [rcx+6Ch], dil
0x180162624  jz      loc_180162752
0x18016262a  mov     edx, 12h
0x18016262f  jmp     loc_180162559
0x180162634  xor     r9d, r9d; lpName
0x180162637  xor     r8d, r8d; bInitialState
0x18016263a  mov     edx, edi; bManualReset
0x18016263c  xor     ecx, ecx; lpEventAttributes
0x18016263e  call    cs:__imp_CreateEventW
0x180162644  mov     cs:qword_1802A31B0, rax
0x18016264b  test    rax, rax
0x18016264e  jnz     short loc_180162686
0x180162650  call    cs:__imp_GetLastError
0x180162656  mov     ebx, eax
0x180162658  mov     rcx, cs:WPP_GLOBAL_Control
0x18016265f  cmp     rcx, rsi
0x180162662  jz      loc_180162752
0x180162668  cmp     [rcx+69h], dil
0x18016266c  jb      loc_180162752
0x180162672  test    [rcx+6Ch], dil
0x180162676  jz      loc_180162752
0x18016267c  mov     edx, 13h
0x180162681  jmp     loc_180162559
0x180162686  xor     r9d, r9d; lpName
0x180162689  xor     r8d, r8d; bInitialState
0x18016268c  mov     edx, edi; bManualReset
0x18016268e  xor     ecx, ecx; lpEventAttributes
0x180162690  call    cs:__imp_CreateEventW
0x180162696  mov     cs:qword_1802A31A0, rax
0x18016269d  test    rax, rax
0x1801626a0  jnz     short loc_1801626D8
0x1801626a2  call    cs:__imp_GetLastError
0x1801626a8  mov     ebx, eax
0x1801626aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1801626b1  cmp     rcx, rsi
0x1801626b4  jz      loc_180162752
0x1801626ba  cmp     [rcx+69h], dil
0x1801626be  jb      loc_180162752
0x1801626c4  test    [rcx+6Ch], dil
0x1801626c8  jz      loc_180162752
0x1801626ce  mov     edx, 14h
0x1801626d3  jmp     loc_180162559
0x1801626d8  lea     rax, WLNotifyOnLogon
0x1801626df  mov     [rsp+0D8h+var_A8], edi
0x1801626e3  mov     [rsp+0D8h+var_88], rax
0x1801626e8  lea     r8, [rsp+0D8h+var_A8]
0x1801626ed  lea     rax, WLNotifyOnLogoff
0x1801626f4  xor     r9d, r9d
0x1801626f7  mov     [rsp+0D8h+var_50], rax
0x1801626ff  lea     rcx, aWlansvc; "Wlansvc"
0x180162706  lea     rax, qword_1802A31D8
0x18016270d  mov     edx, 80h
0x180162712  mov     [rsp+0D8h+var_B8], rax
0x180162717  call    cs:__imp_SysNotifyStartServer
0x18016271d  mov     ebx, eax
0x18016271f  test    eax, eax
0x180162721  jz      short loc_180162745
0x180162723  mov     rcx, cs:WPP_GLOBAL_Control
0x18016272a  cmp     rcx, rsi
0x18016272d  jz      short loc_180162752
0x18016272f  cmp     [rcx+69h], dil
0x180162733  jb      short loc_180162752
0x180162735  test    [rcx+6Ch], dil
0x180162739  jz      short loc_180162752
0x18016273b  mov     edx, 15h
0x180162740  jmp     loc_180162559
0x180162745  mov     cs:dword_1802A31D0, edi
0x18016274b  mov     rcx, cs:WPP_GLOBAL_Control
0x180162752  mov     rax, [rsp+0D8h+Buffer]
0x18016275a  test    rax, rax
0x18016275d  jz      short loc_18016276F
0x18016275f  mov     rcx, rax; Buffer
0x180162762  call    cs:__imp_DsRoleFreeMemory
0x180162768  mov     rcx, cs:WPP_GLOBAL_Control
0x18016276f  cmp     rcx, rsi
0x180162772  jz      short loc_180162794
0x180162774  cmp     byte ptr [rcx+69h], 4
0x180162778  jb      short loc_180162794
0x18016277a  test    [rcx+6Ch], dil
0x18016277e  jz      short loc_180162794
0x180162780  mov     rcx, [rcx+60h]
0x180162784  mov     edx, 16h
0x180162789  mov     r9d, ebx
0x18016278c  mov     r8, rbp
0x18016278f  call    WPP_SF_d
0x180162794  mov     eax, ebx
0x180162796  add     rsp, 0B8h
0x18016279d  pop     rdi
0x18016279e  pop     rsi
0x18016279f  pop     rbp
0x1801627a0  pop     rbx
0x1801627a1  retn
```
