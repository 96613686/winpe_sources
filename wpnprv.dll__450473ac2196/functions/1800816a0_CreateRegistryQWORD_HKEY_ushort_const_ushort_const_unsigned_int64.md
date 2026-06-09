# CreateRegistryQWORD(HKEY__ *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x1800816a0`
- end: `0x180081852`
- name: `?CreateRegistryQWORD@@YAJPEAUHKEY__@@PEBG1_K@Z`
- size: `434`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004245c`
- `0x180043ee0`

## callees

- `0x18000fe54`
- `0x1800133b0`
- `0x18002f59c`
- `0x180081674`
- `0x1800816a0`
- `0x180082120`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180081759`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180081759`

## pseudocode

```c
__int64 __fastcall CreateRegistryQWORD(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4)
{
  int v7; // ebx
  bool v8; // cc
  int v9; // eax
  PVOID *v10; // rcx
  int v11; // edx
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v14[3]; // [rsp+58h] [rbp-18h] BYREF
  HKEY dwDisposition; // [rsp+90h] [rbp+20h] BYREF

  dwDisposition = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_I(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids, a4);
  }
  memset(v14, 0, sizeof(v14));
  LODWORD(dwDisposition) = 0;
  phkResult = 0;
  v7 = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 0x20006u, 0, &phkResult, (LPDWORD)&dwDisposition);
  if ( v7 )
  {
    v8 = v7 < 0;
  }
  else
  {
    v7 = ATL::CRegKey::Close((ATL::CRegKey *)v14);
    v14[0] = phkResult;
    v8 = v7 <= 0;
    if ( !v7 )
    {
      v9 = ATL::CRegKey::SetQWORDValue((ATL::CRegKey *)v14, a3, a4);
      if ( !v9 )
      {
LABEL_23:
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_24;
      }
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      else
        v7 = v9;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 44;
LABEL_22:
          WPP_SF_Sd(
            (unsigned int)v10[2],
            v11,
            (unsigned int)WPP_648969bf7a6635c96a81885b185e83e0_Traceguids,
            (_DWORD)a3,
            v7);
          goto LABEL_23;
        }
        goto LABEL_24;
      }
      goto LABEL_28;
    }
  }
  if ( !v8 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 43;
      goto LABEL_22;
    }
LABEL_24:
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      WPP_SF_d(v10[2], 45, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids, (unsigned int)v7);
  }
LABEL_28:
  ATL::CRegKey::Close((ATL::CRegKey *)v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800816a0  mov     [rsp-18h+arg_8], rbx
0x1800816a5  mov     [rsp-18h+arg_10], rsi
0x1800816aa  mov     [rsp-18h+dwDisposition], rcx
0x1800816af  push    rbp
0x1800816b0  push    rdi
0x1800816b1  push    r12
0x1800816b3  mov     rbp, rsp
0x1800816b6  sub     rsp, 70h
0x1800816ba  mov     rdi, r9
0x1800816bd  mov     rsi, r8
0x1800816c0  mov     rbx, rdx
0x1800816c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800816ca  lea     r12, WPP_GLOBAL_Control
0x1800816d1  cmp     rcx, r12
0x1800816d4  jz      short loc_1800816F7
0x1800816d6  test    byte ptr [rcx+1Ch], 20h
0x1800816da  jz      short loc_1800816F7
0x1800816dc  cmp     byte ptr [rcx+19h], 6
0x1800816e0  jb      short loc_1800816F7
0x1800816e2  mov     rcx, [rcx+10h]
0x1800816e6  lea     r8, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids
0x1800816ed  mov     edx, 2Ah ; '*'
0x1800816f2  call    WPP_SF_I
0x1800816f7  lea     rax, [rbp+dwDisposition]
0x1800816fb  mov     [rbp+var_18], 0
0x180081703  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180081708  xor     r9d, r9d; lpClass
0x18008170b  lea     rax, [rbp+var_20]
0x18008170f  mov     [rbp+var_10], 0
0x180081717  mov     [rsp+70h+phkResult], rax; phkResult
0x18008171c  xor     r8d, r8d; Reserved
0x18008171f  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180081728  mov     rdx, rbx; lpSubKey
0x18008172b  mov     [rsp+70h+samDesired], 20006h; samDesired
0x180081733  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008173a  mov     [rsp+70h+dwOptions], 0; dwOptions
0x180081742  mov     [rbp+var_8], 0
0x18008174a  mov     dword ptr [rbp+dwDisposition], 0
0x180081751  mov     [rbp+var_20], 0
0x180081759  call    cs:__imp_RegCreateKeyExW
0x18008175f  mov     ebx, eax
0x180081761  test    eax, eax
0x180081763  jnz     short loc_1800817C1
0x180081765  lea     rcx, [rbp+var_18]; this
0x180081769  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18008176e  mov     ebx, eax
0x180081770  mov     rax, [rbp+var_20]
0x180081774  mov     [rbp+var_18], rax
0x180081778  test    ebx, ebx
0x18008177a  jnz     short loc_1800817C3
0x18008177c  mov     r8, rdi; unsigned __int64
0x18008177f  lea     rcx, [rbp+var_18]; this
0x180081783  mov     rdx, rsi; unsigned __int16 *
0x180081786  call    ?SetQWORDValue@CRegKey@ATL@@QEAAJPEBG_K@Z; ATL::CRegKey::SetQWORDValue(ushort const *,unsigned __int64)
0x18008178b  test    eax, eax
0x18008178d  jz      short loc_180081802
0x18008178f  jg      short loc_180081795
0x180081791  mov     ebx, eax
0x180081793  jmp     short loc_18008179E
0x180081795  movzx   ebx, ax
0x180081798  or      ebx, 80070000h
0x18008179e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800817a5  cmp     rcx, r12
0x1800817a8  jz      loc_180081832
0x1800817ae  test    byte ptr [rcx+1Ch], 20h
0x1800817b2  jz      short loc_180081809
0x1800817b4  cmp     byte ptr [rcx+19h], 2
0x1800817b8  jb      short loc_180081809
0x1800817ba  mov     edx, 2Ch ; ','
0x1800817bf  jmp     short loc_1800817EB
0x1800817c1  test    ebx, ebx
0x1800817c3  jle     short loc_1800817CE
0x1800817c5  movzx   ebx, bx
0x1800817c8  or      ebx, 80070000h
0x1800817ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800817d5  cmp     rcx, r12
0x1800817d8  jz      short loc_180081832
0x1800817da  test    byte ptr [rcx+1Ch], 20h
0x1800817de  jz      short loc_180081809
0x1800817e0  cmp     byte ptr [rcx+19h], 2
0x1800817e4  jb      short loc_180081809
0x1800817e6  mov     edx, 2Bh ; '+'
0x1800817eb  mov     rcx, [rcx+10h]
0x1800817ef  lea     r8, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids
0x1800817f6  mov     r9, rsi
0x1800817f9  mov     [rsp+70h+dwOptions], ebx
0x1800817fd  call    WPP_SF_Sd
0x180081802  mov     rcx, cs:WPP_GLOBAL_Control
0x180081809  cmp     rcx, r12
0x18008180c  jz      short loc_180081832
0x18008180e  test    byte ptr [rcx+1Ch], 20h
0x180081812  jz      short loc_180081832
0x180081814  cmp     byte ptr [rcx+19h], 6
0x180081818  jb      short loc_180081832
0x18008181a  mov     rcx, [rcx+10h]
0x18008181e  lea     r8, WPP_648969bf7a6635c96a81885b185e83e0_Traceguids
0x180081825  mov     edx, 2Dh ; '-'
0x18008182a  mov     r9d, ebx
0x18008182d  call    WPP_SF_d
0x180081832  lea     rcx, [rbp+var_18]; this
0x180081836  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18008183b  lea     r11, [rsp+70h+var_s0]
0x180081840  mov     eax, ebx
0x180081842  mov     rbx, [r11+28h]
0x180081846  mov     rsi, [r11+30h]
0x18008184a  mov     rsp, r11
0x18008184d  pop     r12
0x18008184f  pop     rdi
0x180081850  pop     rbp
0x180081851  retn
```
