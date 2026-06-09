# GetChassisTypeStringFromEnum(__MIDL___MIDL_itf_wdsmgmt_0000_0000_0034,ushort * *)

- ea: `0x180025a10`
- end: `0x180025ca3`
- name: `?GetChassisTypeStringFromEnum@@YAKW4__MIDL___MIDL_itf_wdsmgmt_0000_0000_0034@@PEAPEAG@Z`
- size: `659`
- prototype: `unsigned int __high(enum __MIDL___MIDL_itf_wdsmgmt_0000_0000_0034, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180014b10`
- `0x180025a10`
- `0x180030010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180025c89`
- `KERNEL32!SetLastError` at `0x180025c89`
- `KERNEL32!GetLastError` at `0x180025bff`
- `KERNEL32!GetLastError` at `0x180025c4e`
- `KERNEL32!GetLastError` at `0x180025bff`
- `KERNEL32!GetLastError` at `0x180025c4e`

## string_xrefs

- `0x180025c1b`: `onecore\base\eco\wds\wdslib\common\src\wdsmgmtutil.cpp`
- `0x180025c67`: `onecore\base\eco\wds\wdslib\common\src\wdsmgmtutil.cpp`
- `0x180025bcf`: `rackmountchassis`
- `0x180025bc6`: `sealedcasecomputer`
- `0x180025bb4`: `compactpci`

## pseudocode

```c
__int64 __fastcall GetChassisTypeStringFromEnum(int a1, unsigned __int16 **a2)
{
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  const unsigned __int16 *v7; // rcx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  unsigned int v23; // edi
  DWORD LastError; // ebx

  if ( a1 > 14 )
  {
    if ( a1 > 21 )
    {
      v18 = a1 - 22;
      if ( v18 )
      {
        v19 = v18 - 1;
        if ( v19 )
        {
          v20 = v19 - 1;
          if ( v20 )
          {
            v21 = v20 - 1;
            if ( v21 )
            {
              v22 = v21 - 1;
              if ( v22 )
              {
                if ( v22 != 1 )
                  goto LABEL_52;
                v7 = L"advancedtca";
              }
              else
              {
                v7 = L"compactpci";
              }
            }
            else
            {
              v7 = L"multisystemchassis";
            }
          }
          else
          {
            v7 = L"sealedcasecomputer";
          }
        }
        else
        {
          v7 = L"rackmountchassis";
        }
      }
      else
      {
        v7 = L"storagechassis";
      }
    }
    else if ( a1 == 21 )
    {
      v7 = L"peripheralchassis";
    }
    else
    {
      v13 = a1 - 15;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 1;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
            {
              v17 = v16 - 1;
              if ( v17 )
              {
                if ( v17 != 1 )
                  goto LABEL_52;
                v7 = L"busexpansionchassis";
              }
              else
              {
                v7 = L"subchassis";
              }
            }
            else
            {
              v7 = L"expansionchassis";
            }
          }
          else
          {
            v7 = L"mainsystemchassis";
          }
        }
        else
        {
          v7 = L"lunchbox";
        }
      }
      else
      {
        v7 = L"spacesaving";
      }
    }
    goto LABEL_59;
  }
  if ( a1 == 14 )
  {
    v7 = L"subnotebook";
    goto LABEL_59;
  }
  if ( a1 > 7 )
  {
    v8 = a1 - 8;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              if ( v12 != 1 )
                goto LABEL_52;
              v7 = L"allinone";
            }
            else
            {
              v7 = L"dockingstation";
            }
          }
          else
          {
            v7 = L"handheld";
          }
        }
        else
        {
          v7 = L"notebook";
        }
      }
      else
      {
        v7 = L"laptop";
      }
    }
    else
    {
      v7 = L"portable";
    }
LABEL_59:
    v23 = DuplicateStringWBom(v7, 0, a2);
    if ( !v23 )
      return v23;
    goto LABEL_60;
  }
  if ( a1 == 7 )
  {
    v7 = L"tower";
    goto LABEL_59;
  }
  v2 = a1 - 1;
  if ( !v2 )
  {
    v7 = L"other";
    goto LABEL_59;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    v7 = L"unknownchassis";
    goto LABEL_59;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v7 = L"desktop";
    goto LABEL_59;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v7 = L"lowprofiledesktop";
    goto LABEL_59;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v7 = L"pizzabox";
    goto LABEL_59;
  }
  if ( v6 == 1 )
  {
    v7 = L"minitower";
    goto LABEL_59;
  }
LABEL_52:
  v23 = 87;
LABEL_60:
  if ( g_ErrLibTraceFunctionEx )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunctionEx(
      0x80000u,
      L"[%S:%u] Expression: %S, Win32 Error=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsmgmtutil.cpp",
      1027,
      &dword_1800331C4,
      v23);
LABEL_64:
    SetLastError(LastError);
    return v23;
  }
  if ( g_ErrLibTraceFunction )
  {
    LastError = GetLastError();
    g_ErrLibTraceFunction(
      L"[%S:%u] Expression: %S, Win32 Error=0x%x",
      "onecore\\base\\eco\\wds\\wdslib\\common\\src\\wdsmgmtutil.cpp",
      1027,
      &dword_1800331C4,
      v23);
    goto LABEL_64;
  }
  return v23;
}

```

## disassembly

```asm
0x180025a10  mov     [rsp+arg_8], rbx
0x180025a15  push    rdi
0x180025a16  sub     rsp, 40h
0x180025a1a  cmp     ecx, 0Eh
0x180025a1d  jg      loc_180025B1C
0x180025a23  jz      loc_180025B10
0x180025a29  cmp     ecx, 7
0x180025a2c  jg      short loc_180025AA6
0x180025a2e  jz      short loc_180025A9A
0x180025a30  sub     ecx, 1
0x180025a33  jz      short loc_180025A8E
0x180025a35  sub     ecx, 1
0x180025a38  jz      short loc_180025A82
0x180025a3a  sub     ecx, 1
0x180025a3d  jz      short loc_180025A76
0x180025a3f  sub     ecx, 1
0x180025a42  jz      short loc_180025A6A
0x180025a44  sub     ecx, 1
0x180025a47  jz      short loc_180025A5E
0x180025a49  cmp     ecx, 1
0x180025a4c  jnz     loc_180025BA4
0x180025a52  lea     rcx, aMinitower; "minitower"
0x180025a59  jmp     loc_180025BDF
0x180025a5e  lea     rcx, aPizzabox; "pizzabox"
0x180025a65  jmp     loc_180025BDF
0x180025a6a  lea     rcx, aLowprofiledesk; "lowprofiledesktop"
0x180025a71  jmp     loc_180025BDF
0x180025a76  lea     rcx, aDesktop; "desktop"
0x180025a7d  jmp     loc_180025BDF
0x180025a82  lea     rcx, aUnknownchassis; "unknownchassis"
0x180025a89  jmp     loc_180025BDF
0x180025a8e  lea     rcx, aOther; "other"
0x180025a95  jmp     loc_180025BDF
0x180025a9a  lea     rcx, aTower; "tower"
0x180025aa1  jmp     loc_180025BDF
0x180025aa6  sub     ecx, 8
0x180025aa9  jz      short loc_180025B04
0x180025aab  sub     ecx, 1
0x180025aae  jz      short loc_180025AF8
0x180025ab0  sub     ecx, 1
0x180025ab3  jz      short loc_180025AEC
0x180025ab5  sub     ecx, 1
0x180025ab8  jz      short loc_180025AE0
0x180025aba  sub     ecx, 1
0x180025abd  jz      short loc_180025AD4
0x180025abf  cmp     ecx, 1
0x180025ac2  jnz     loc_180025BA4
0x180025ac8  lea     rcx, aAllinone; "allinone"
0x180025acf  jmp     loc_180025BDF
0x180025ad4  lea     rcx, aDockingstation; "dockingstation"
0x180025adb  jmp     loc_180025BDF
0x180025ae0  lea     rcx, aHandheld; "handheld"
0x180025ae7  jmp     loc_180025BDF
0x180025aec  lea     rcx, aNotebook; "notebook"
0x180025af3  jmp     loc_180025BDF
0x180025af8  lea     rcx, aLaptop; "laptop"
0x180025aff  jmp     loc_180025BDF
0x180025b04  lea     rcx, aPortable; "portable"
0x180025b0b  jmp     loc_180025BDF
0x180025b10  lea     rcx, aSubnotebook; "subnotebook"
0x180025b17  jmp     loc_180025BDF
0x180025b1c  cmp     ecx, 15h
0x180025b1f  jg      short loc_180025B86
0x180025b21  jz      short loc_180025B7D
0x180025b23  sub     ecx, 0Fh
0x180025b26  jz      short loc_180025B74
0x180025b28  sub     ecx, 1
0x180025b2b  jz      short loc_180025B6B
0x180025b2d  sub     ecx, 1
0x180025b30  jz      short loc_180025B62
0x180025b32  sub     ecx, 1
0x180025b35  jz      short loc_180025B59
0x180025b37  sub     ecx, 1
0x180025b3a  jz      short loc_180025B4D
0x180025b3c  cmp     ecx, 1
0x180025b3f  jnz     short loc_180025BA4
0x180025b41  lea     rcx, aBusexpansionch; "busexpansionchassis"
0x180025b48  jmp     loc_180025BDF
0x180025b4d  lea     rcx, aSubchassis; "subchassis"
0x180025b54  jmp     loc_180025BDF
0x180025b59  lea     rcx, aExpansionchass; "expansionchassis"
0x180025b60  jmp     short loc_180025BDF
0x180025b62  lea     rcx, aMainsystemchas; "mainsystemchassis"
0x180025b69  jmp     short loc_180025BDF
0x180025b6b  lea     rcx, aLunchbox; "lunchbox"
0x180025b72  jmp     short loc_180025BDF
0x180025b74  lea     rcx, aSpacesaving; "spacesaving"
0x180025b7b  jmp     short loc_180025BDF
0x180025b7d  lea     rcx, aPeripheralchas; "peripheralchassis"
0x180025b84  jmp     short loc_180025BDF
0x180025b86  sub     ecx, 16h
0x180025b89  jz      short loc_180025BD8
0x180025b8b  sub     ecx, 1
0x180025b8e  jz      short loc_180025BCF
0x180025b90  sub     ecx, 1
0x180025b93  jz      short loc_180025BC6
0x180025b95  sub     ecx, 1
0x180025b98  jz      short loc_180025BBD
0x180025b9a  sub     ecx, 1
0x180025b9d  jz      short loc_180025BB4
0x180025b9f  cmp     ecx, 1
0x180025ba2  jz      short loc_180025BAB
0x180025ba4  mov     edi, 57h ; 'W'
0x180025ba9  jmp     short loc_180025BF5
0x180025bab  lea     rcx, aAdvancedtca; "advancedtca"
0x180025bb2  jmp     short loc_180025BDF
0x180025bb4  lea     rcx, aCompactpci; "compactpci"
0x180025bbb  jmp     short loc_180025BDF
0x180025bbd  lea     rcx, aMultisystemcha; "multisystemchassis"
0x180025bc4  jmp     short loc_180025BDF
0x180025bc6  lea     rcx, aSealedcasecomp; "sealedcasecomputer"
0x180025bcd  jmp     short loc_180025BDF
0x180025bcf  lea     rcx, aRackmountchass; "rackmountchassis"
0x180025bd6  jmp     short loc_180025BDF
0x180025bd8  lea     rcx, aStoragechassis; "storagechassis"
0x180025bdf  xor     eax, eax
0x180025be1  mov     r8, rdx; unsigned __int16 **
0x180025be4  mov     edx, eax; int
0x180025be6  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x180025beb  mov     edi, eax
0x180025bed  test    eax, eax
0x180025bef  jz      loc_180025C95
0x180025bf5  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025bfd  jz      short loc_180025C44
0x180025bff  call    cs:__imp_GetLastError
0x180025c06  nop     dword ptr [rax+rax+00h]
0x180025c0b  lea     r9, dword_1800331C4
0x180025c12  mov     [rsp+48h+var_20], edi
0x180025c16  mov     [rsp+48h+var_28], r9
0x180025c1b  lea     r8, aOnecoreBaseEco_13; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180025c22  mov     ebx, eax
0x180025c24  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180025c2b  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180025c32  mov     r9d, 403h
0x180025c38  mov     ecx, 80000h
0x180025c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c42  jmp     short loc_180025C87
0x180025c44  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025c4c  jz      short loc_180025C95
0x180025c4e  call    cs:__imp_GetLastError
0x180025c55  nop     dword ptr [rax+rax+00h]
0x180025c5a  lea     r9, dword_1800331C4
0x180025c61  mov     dword ptr [rsp+48h+var_28], edi
0x180025c65  mov     ebx, eax
0x180025c67  lea     rdx, aOnecoreBaseEco_13; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180025c6e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180025c75  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180025c7c  mov     r8d, 403h
0x180025c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c87  mov     ecx, ebx; dwErrCode
0x180025c89  call    cs:__imp_SetLastError
0x180025c90  nop     dword ptr [rax+rax+00h]
0x180025c95  mov     rbx, [rsp+48h+arg_8]
0x180025c9a  mov     eax, edi
0x180025c9c  add     rsp, 40h
0x180025ca0  pop     rdi
0x180025ca1  retn
```
