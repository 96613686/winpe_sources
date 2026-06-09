# GetChassisTypeStringFromEnum(__MIDL___MIDL_itf_wdsmgmt_0000_0000_0034,ushort * *)

- ea: `0x180026b30`
- end: `0x180026dc3`
- name: `?GetChassisTypeStringFromEnum@@YAKW4__MIDL___MIDL_itf_wdsmgmt_0000_0000_0034@@PEAPEAG@Z`
- size: `659`
- prototype: `unsigned int __high(enum __MIDL___MIDL_itf_wdsmgmt_0000_0000_0034, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180015830`
- `0x180026b30`
- `0x180031010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180026da9`
- `KERNEL32!SetLastError` at `0x180026da9`
- `KERNEL32!GetLastError` at `0x180026d1f`
- `KERNEL32!GetLastError` at `0x180026d6e`
- `KERNEL32!GetLastError` at `0x180026d1f`
- `KERNEL32!GetLastError` at `0x180026d6e`

## string_xrefs

- `0x180026d3b`: `onecore\base\eco\wds\wdslib\common\src\wdsmgmtutil.cpp`
- `0x180026d87`: `onecore\base\eco\wds\wdslib\common\src\wdsmgmtutil.cpp`
- `0x180026cef`: `rackmountchassis`
- `0x180026ce6`: `sealedcasecomputer`
- `0x180026cd4`: `compactpci`

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
      &dword_18003572C,
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
      &dword_18003572C,
      v23);
    goto LABEL_64;
  }
  return v23;
}

```

## disassembly

```asm
0x180026b30  mov     [rsp+arg_8], rbx
0x180026b35  push    rdi
0x180026b36  sub     rsp, 40h
0x180026b3a  cmp     ecx, 0Eh
0x180026b3d  jg      loc_180026C3C
0x180026b43  jz      loc_180026C30
0x180026b49  cmp     ecx, 7
0x180026b4c  jg      short loc_180026BC6
0x180026b4e  jz      short loc_180026BBA
0x180026b50  sub     ecx, 1
0x180026b53  jz      short loc_180026BAE
0x180026b55  sub     ecx, 1
0x180026b58  jz      short loc_180026BA2
0x180026b5a  sub     ecx, 1
0x180026b5d  jz      short loc_180026B96
0x180026b5f  sub     ecx, 1
0x180026b62  jz      short loc_180026B8A
0x180026b64  sub     ecx, 1
0x180026b67  jz      short loc_180026B7E
0x180026b69  cmp     ecx, 1
0x180026b6c  jnz     loc_180026CC4
0x180026b72  lea     rcx, aMinitower; "minitower"
0x180026b79  jmp     loc_180026CFF
0x180026b7e  lea     rcx, aPizzabox; "pizzabox"
0x180026b85  jmp     loc_180026CFF
0x180026b8a  lea     rcx, aLowprofiledesk; "lowprofiledesktop"
0x180026b91  jmp     loc_180026CFF
0x180026b96  lea     rcx, aDesktop; "desktop"
0x180026b9d  jmp     loc_180026CFF
0x180026ba2  lea     rcx, aUnknownchassis; "unknownchassis"
0x180026ba9  jmp     loc_180026CFF
0x180026bae  lea     rcx, aOther; "other"
0x180026bb5  jmp     loc_180026CFF
0x180026bba  lea     rcx, aTower; "tower"
0x180026bc1  jmp     loc_180026CFF
0x180026bc6  sub     ecx, 8
0x180026bc9  jz      short loc_180026C24
0x180026bcb  sub     ecx, 1
0x180026bce  jz      short loc_180026C18
0x180026bd0  sub     ecx, 1
0x180026bd3  jz      short loc_180026C0C
0x180026bd5  sub     ecx, 1
0x180026bd8  jz      short loc_180026C00
0x180026bda  sub     ecx, 1
0x180026bdd  jz      short loc_180026BF4
0x180026bdf  cmp     ecx, 1
0x180026be2  jnz     loc_180026CC4
0x180026be8  lea     rcx, aAllinone; "allinone"
0x180026bef  jmp     loc_180026CFF
0x180026bf4  lea     rcx, aDockingstation; "dockingstation"
0x180026bfb  jmp     loc_180026CFF
0x180026c00  lea     rcx, aHandheld; "handheld"
0x180026c07  jmp     loc_180026CFF
0x180026c0c  lea     rcx, aNotebook; "notebook"
0x180026c13  jmp     loc_180026CFF
0x180026c18  lea     rcx, aLaptop; "laptop"
0x180026c1f  jmp     loc_180026CFF
0x180026c24  lea     rcx, aPortable; "portable"
0x180026c2b  jmp     loc_180026CFF
0x180026c30  lea     rcx, aSubnotebook; "subnotebook"
0x180026c37  jmp     loc_180026CFF
0x180026c3c  cmp     ecx, 15h
0x180026c3f  jg      short loc_180026CA6
0x180026c41  jz      short loc_180026C9D
0x180026c43  sub     ecx, 0Fh
0x180026c46  jz      short loc_180026C94
0x180026c48  sub     ecx, 1
0x180026c4b  jz      short loc_180026C8B
0x180026c4d  sub     ecx, 1
0x180026c50  jz      short loc_180026C82
0x180026c52  sub     ecx, 1
0x180026c55  jz      short loc_180026C79
0x180026c57  sub     ecx, 1
0x180026c5a  jz      short loc_180026C6D
0x180026c5c  cmp     ecx, 1
0x180026c5f  jnz     short loc_180026CC4
0x180026c61  lea     rcx, aBusexpansionch; "busexpansionchassis"
0x180026c68  jmp     loc_180026CFF
0x180026c6d  lea     rcx, aSubchassis; "subchassis"
0x180026c74  jmp     loc_180026CFF
0x180026c79  lea     rcx, aExpansionchass; "expansionchassis"
0x180026c80  jmp     short loc_180026CFF
0x180026c82  lea     rcx, aMainsystemchas; "mainsystemchassis"
0x180026c89  jmp     short loc_180026CFF
0x180026c8b  lea     rcx, aLunchbox; "lunchbox"
0x180026c92  jmp     short loc_180026CFF
0x180026c94  lea     rcx, aSpacesaving; "spacesaving"
0x180026c9b  jmp     short loc_180026CFF
0x180026c9d  lea     rcx, aPeripheralchas; "peripheralchassis"
0x180026ca4  jmp     short loc_180026CFF
0x180026ca6  sub     ecx, 16h
0x180026ca9  jz      short loc_180026CF8
0x180026cab  sub     ecx, 1
0x180026cae  jz      short loc_180026CEF
0x180026cb0  sub     ecx, 1
0x180026cb3  jz      short loc_180026CE6
0x180026cb5  sub     ecx, 1
0x180026cb8  jz      short loc_180026CDD
0x180026cba  sub     ecx, 1
0x180026cbd  jz      short loc_180026CD4
0x180026cbf  cmp     ecx, 1
0x180026cc2  jz      short loc_180026CCB
0x180026cc4  mov     edi, 57h ; 'W'
0x180026cc9  jmp     short loc_180026D15
0x180026ccb  lea     rcx, aAdvancedtca; "advancedtca"
0x180026cd2  jmp     short loc_180026CFF
0x180026cd4  lea     rcx, aCompactpci; "compactpci"
0x180026cdb  jmp     short loc_180026CFF
0x180026cdd  lea     rcx, aMultisystemcha; "multisystemchassis"
0x180026ce4  jmp     short loc_180026CFF
0x180026ce6  lea     rcx, aSealedcasecomp; "sealedcasecomputer"
0x180026ced  jmp     short loc_180026CFF
0x180026cef  lea     rcx, aRackmountchass; "rackmountchassis"
0x180026cf6  jmp     short loc_180026CFF
0x180026cf8  lea     rcx, aStoragechassis; "storagechassis"
0x180026cff  xor     eax, eax
0x180026d01  mov     r8, rdx; unsigned __int16 **
0x180026d04  mov     edx, eax; int
0x180026d06  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x180026d0b  mov     edi, eax
0x180026d0d  test    eax, eax
0x180026d0f  jz      loc_180026DB5
0x180026d15  cmp     cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA, 0; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180026d1d  jz      short loc_180026D64
0x180026d1f  call    cs:__imp_GetLastError
0x180026d26  nop     dword ptr [rax+rax+00h]
0x180026d2b  lea     r9, dword_18003572C
0x180026d32  mov     [rsp+48h+var_20], edi
0x180026d36  mov     [rsp+48h+var_28], r9
0x180026d3b  lea     r8, aOnecoreBaseEco_12; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180026d42  mov     ebx, eax
0x180026d44  lea     rdx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180026d4b  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180026d52  mov     r9d, 403h
0x180026d58  mov     ecx, 80000h
0x180026d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d62  jmp     short loc_180026DA7
0x180026d64  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180026d6c  jz      short loc_180026DB5
0x180026d6e  call    cs:__imp_GetLastError
0x180026d75  nop     dword ptr [rax+rax+00h]
0x180026d7a  lea     r9, dword_18003572C
0x180026d81  mov     dword ptr [rsp+48h+var_28], edi
0x180026d85  mov     ebx, eax
0x180026d87  lea     rdx, aOnecoreBaseEco_12; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180026d8e  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x180026d95  lea     rcx, aSUExpressionSW; "[%S:%u] Expression: %S, Win32 Error=0x%"...
0x180026d9c  mov     r8d, 403h
0x180026da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026da7  mov     ecx, ebx; dwErrCode
0x180026da9  call    cs:__imp_SetLastError
0x180026db0  nop     dword ptr [rax+rax+00h]
0x180026db5  mov     rbx, [rsp+48h+arg_8]
0x180026dba  mov     eax, edi
0x180026dbc  add     rsp, 40h
0x180026dc0  pop     rdi
0x180026dc1  retn
```
