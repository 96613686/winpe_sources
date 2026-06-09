# WdiGetScenarioInstanceFilePath

- ea: `0x18000bff0`
- end: `0x18000c1da`
- name: `WdiGetScenarioInstanceFilePath`
- size: `490`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x1800072f0`
- `0x1800093d0`
- `0x180009444`
- `0x180009540`
- `0x18000bff0`

## string_xrefs

- `0x18000c02b`: `WdiGetScenarioInstanceFilePath`

## pseudocode

```c
__int64 __fastcall WdiGetScenarioInstanceFilePath(__int64 a1, unsigned int a2, unsigned __int16 *a3, unsigned int *a4)
{
  unsigned __int16 *v4; // rsi
  __int64 v5; // rax
  int v8; // r8d
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  int Args; // eax
  HRESULT v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  unsigned __int64 v19[7]; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  v5 = a2;
  v19[0] = 0;
  v20 = 0;
  if ( !a1 )
  {
    v8 = 1543;
LABEL_3:
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioInstanceFilePath",
      v8,
      (int)L"Error = %d",
      87);
    goto LABEL_31;
  }
  if ( !a4 )
  {
    v8 = 1544;
    goto LABEL_3;
  }
  v10 = *(_QWORD *)(a1 + 168);
  if ( !v10 )
  {
    v8 = 1545;
    goto LABEL_3;
  }
  if ( *(_DWORD *)(a1 + 16) == 1 )
  {
    if ( (unsigned int)v5 >= *(_DWORD *)(a1 + 156) )
    {
      v8 = 1558;
      goto LABEL_3;
    }
    v11 = v10 + 104 * v5;
    if ( (*(_BYTE *)(v11 + 68) & 2) != 0 )
    {
      v9 = -2147020579;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
        (int)L"WdiGetScenarioInstanceFilePath",
        1571,
        (int)L"Error = %d",
        221);
    }
    else
    {
      v12 = (unsigned __int16 *)WdipAlloc(2048);
      v4 = v12;
      if ( v12 )
      {
        Args = WdipVerifyDirectory(v11 + 16, v11, v12, 0x400u);
        v9 = Args;
        if ( Args >= 0 )
        {
          v14 = StringCchLengthW(v4, 0x7FFFFFFFu, v19);
          v9 = v14;
          if ( v14 >= 0 )
          {
            v15 = ULongLongToULong(v19[0], &v20);
            v9 = v15;
            if ( v15 >= 0 )
            {
              v16 = v20 + 1;
              if ( v20 == -1 )
              {
                v9 = -2147024362;
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
                  (int)L"WdiGetScenarioInstanceFilePath",
                  1595,
                  (int)L"Error = %d",
                  22);
              }
              else if ( a3 )
              {
                if ( *a4 >= v16 )
                {
                  v17 = StringCchCopyW(a3, v16, v4);
                  v9 = v17;
                  if ( v17 < 0 )
                    WdipTraceError(
                      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
                      (int)L"WdiGetScenarioInstanceFilePath",
                      1614,
                      (int)L"Error = %d",
                      v17);
                }
                else
                {
                  *a4 = v16;
                  v9 = -2147024662;
                  WdipTraceError(
                    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
                    (int)L"WdiGetScenarioInstanceFilePath",
                    1607,
                    (int)L"Error = %d",
                    234);
                }
              }
              else
              {
                *a4 = v16;
              }
            }
            else
            {
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
                (int)L"WdiGetScenarioInstanceFilePath",
                1590,
                (int)L"Error = %d",
                v15);
            }
          }
          else
          {
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
              (int)L"WdiGetScenarioInstanceFilePath",
              1587,
              (int)L"Error = %d",
              v14);
          }
        }
        else
        {
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
            (int)L"WdiGetScenarioInstanceFilePath",
            1581,
            (int)L"Error = %d",
            Args);
        }
      }
      else
      {
        v9 = -2147024882;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
          (int)L"WdiGetScenarioInstanceFilePath",
          1574,
          (int)L"Error = %d",
          14);
      }
    }
  }
  else
  {
    v9 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioInstanceFilePath",
      1550,
      (int)L"Error = %d",
      221);
  }
LABEL_31:
  WdipFree(v4);
  return v9;
}

```

## disassembly

```asm
0x18000bff0  push    rbx
0x18000bff2  push    rbp
0x18000bff3  push    rsi
0x18000bff4  push    rdi
0x18000bff5  sub     rsp, 48h
0x18000bff9  xor     esi, esi
0x18000bffb  mov     eax, edx
0x18000bffd  mov     [rsp+68h+var_38], rsi
0x18000c002  mov     rdi, r9
0x18000c005  mov     [rsp+68h+arg_0], esi
0x18000c009  mov     rbp, r8
0x18000c00c  test    rcx, rcx
0x18000c00f  jnz     short loc_18000C043
0x18000c011  mov     r8d, 607h; int
0x18000c017  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000c01f  mov     ebx, 80070057h
0x18000c024  lea     r9, aErrorD_0; "Error = %d"
0x18000c02b  lea     rdx, aWdigetscenario_8; "WdiGetScenarioInstanceFilePath"
0x18000c032  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000c039  call    WdipTraceError
0x18000c03e  jmp     loc_18000C1C7
0x18000c043  test    rdi, rdi
0x18000c046  jnz     short loc_18000C050
0x18000c048  mov     r8d, 608h
0x18000c04e  jmp     short loc_18000C017
0x18000c050  mov     rdx, [rcx+0A8h]
0x18000c057  test    rdx, rdx
0x18000c05a  jnz     short loc_18000C064
0x18000c05c  mov     r8d, 609h
0x18000c062  jmp     short loc_18000C017
0x18000c064  cmp     dword ptr [rcx+10h], 1
0x18000c068  jz      short loc_18000C07F
0x18000c06a  mov     ebx, 800710DDh
0x18000c06f  mov     dword ptr [rsp+68h+Args], 10DDh
0x18000c077  mov     r8d, 60Eh
0x18000c07d  jmp     short loc_18000C024
0x18000c07f  cmp     eax, [rcx+9Ch]
0x18000c085  jb      short loc_18000C08F
0x18000c087  mov     r8d, 616h
0x18000c08d  jmp     short loc_18000C017
0x18000c08f  imul    rbx, rax, 68h ; 'h'
0x18000c093  add     rbx, rdx
0x18000c096  test    byte ptr [rbx+44h], 2
0x18000c09a  jz      short loc_18000C0B4
0x18000c09c  mov     ebx, 800710DDh
0x18000c0a1  mov     dword ptr [rsp+68h+Args], 10DDh
0x18000c0a9  mov     r8d, 623h
0x18000c0af  jmp     loc_18000C024
0x18000c0b4  mov     ecx, 800h
0x18000c0b9  call    WdipAlloc
0x18000c0be  mov     rsi, rax
0x18000c0c1  test    rax, rax
0x18000c0c4  jnz     short loc_18000C0DE
0x18000c0c6  mov     ebx, 8007000Eh
0x18000c0cb  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000c0d3  mov     r8d, 626h
0x18000c0d9  jmp     loc_18000C024
0x18000c0de  lea     rcx, [rbx+10h]
0x18000c0e2  mov     r9d, 400h
0x18000c0e8  mov     r8, rsi
0x18000c0eb  mov     rdx, rbx
0x18000c0ee  call    WdipVerifyDirectory
0x18000c0f3  mov     ebx, eax
0x18000c0f5  test    eax, eax
0x18000c0f7  jns     short loc_18000C10B
0x18000c0f9  movzx   ecx, ax
0x18000c0fc  mov     r8d, 62Dh
0x18000c102  mov     dword ptr [rsp+68h+Args], ecx
0x18000c106  jmp     loc_18000C024
0x18000c10b  lea     r8, [rsp+68h+var_38]; unsigned __int64 *
0x18000c110  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000c115  mov     rcx, rsi; unsigned __int16 *
0x18000c118  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000c11d  mov     ebx, eax
0x18000c11f  test    eax, eax
0x18000c121  jns     short loc_18000C135
0x18000c123  movzx   eax, ax
0x18000c126  mov     r8d, 633h
0x18000c12c  mov     dword ptr [rsp+68h+Args], eax
0x18000c130  jmp     loc_18000C024
0x18000c135  mov     rcx, [rsp+68h+var_38]; unsigned __int64
0x18000c13a  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x18000c13f  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000c144  mov     ebx, eax
0x18000c146  test    eax, eax
0x18000c148  jns     short loc_18000C15C
0x18000c14a  movzx   eax, ax
0x18000c14d  mov     r8d, 636h
0x18000c153  mov     dword ptr [rsp+68h+Args], eax
0x18000c157  jmp     loc_18000C024
0x18000c15c  mov     eax, [rsp+68h+arg_0]
0x18000c160  add     eax, 1
0x18000c163  jnz     short loc_18000C17D
0x18000c165  mov     ebx, 80070216h
0x18000c16a  mov     dword ptr [rsp+68h+Args], 216h
0x18000c172  mov     r8d, 63Bh
0x18000c178  jmp     loc_18000C024
0x18000c17d  test    rbp, rbp
0x18000c180  jz      short loc_18000C1C5
0x18000c182  cmp     [rdi], eax
0x18000c184  jnb     short loc_18000C1A0
0x18000c186  mov     [rdi], eax
0x18000c188  mov     ebx, 800700EAh
0x18000c18d  mov     dword ptr [rsp+68h+Args], 0EAh
0x18000c195  mov     r8d, 647h
0x18000c19b  jmp     loc_18000C024
0x18000c1a0  mov     edx, eax; unsigned __int64
0x18000c1a2  mov     r8, rsi; unsigned __int16 *
0x18000c1a5  mov     rcx, rbp; unsigned __int16 *
0x18000c1a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c1ad  mov     ebx, eax
0x18000c1af  test    eax, eax
0x18000c1b1  jns     short loc_18000C1C7
0x18000c1b3  movzx   eax, ax
0x18000c1b6  mov     r8d, 64Eh
0x18000c1bc  mov     dword ptr [rsp+68h+Args], eax
0x18000c1c0  jmp     loc_18000C024
0x18000c1c5  mov     [rdi], eax
0x18000c1c7  mov     rcx, rsi
0x18000c1ca  call    WdipFree
0x18000c1cf  mov     eax, ebx
0x18000c1d1  add     rsp, 48h
0x18000c1d5  pop     rdi
0x18000c1d6  pop     rsi
0x18000c1d7  pop     rbp
0x18000c1d8  pop     rbx
0x18000c1d9  retn
```
