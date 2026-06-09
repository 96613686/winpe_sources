# WdiGetInstanceFilePath

- ea: `0x1800098e0`
- end: `0x180009af2`
- name: `WdiGetInstanceFilePath`
- size: `530`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned int *)`
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
- `0x1800098e0`

## string_xrefs

- `0x18000991f`: `WdiGetInstanceFilePath`

## pseudocode

```c
__int64 __fastcall WdiGetInstanceFilePath(__int64 a1, unsigned __int16 *a2, unsigned int *a3)
{
  const unsigned __int16 *v3; // rdi
  int v7; // r8d
  unsigned int v8; // ebx
  unsigned __int16 *v9; // rax
  int v10; // ecx
  int Args; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v19; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v20; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v20 = 0;
  v19 = 0;
  if ( !a1 )
  {
    v7 = 1895;
LABEL_3:
    v8 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiGetInstanceFilePath",
      v7,
      (int)L"Error = %d",
      87);
    goto LABEL_33;
  }
  if ( !a3 )
  {
    v7 = 1896;
    goto LABEL_3;
  }
  v9 = (unsigned __int16 *)WdipAlloc(2048);
  v3 = v9;
  if ( v9 )
  {
    v10 = *(_DWORD *)(a1 + 16);
    if ( v10 )
    {
      if ( v10 != 1 )
      {
        v8 = -2147020579;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
          (int)L"WdiGetInstanceFilePath",
          1937,
          (int)L"Error = %d",
          221);
        goto LABEL_33;
      }
      if ( !*(_QWORD *)(a1 + 88) && !*(_QWORD *)(a1 + 96) )
      {
        v8 = -2147020579;
        goto LABEL_33;
      }
      Args = WdipVerifyDirectory(a1 + 88, a1 + 40, v9, 0x400u);
      v8 = Args;
      if ( Args < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
          (int)L"WdiGetInstanceFilePath",
          1918,
          (int)L"Error = %d",
          Args);
        goto LABEL_33;
      }
    }
    else
    {
      v12 = *(_QWORD *)(a1 + 40);
      if ( !v12 )
      {
        v7 = 1924;
        goto LABEL_3;
      }
      v13 = WdipVerifyDirectory(v12 + 48, v12 + 64, v9, 0x400u);
      v8 = v13;
      if ( v13 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
          (int)L"WdiGetInstanceFilePath",
          1931,
          (int)L"Error = %d",
          v13);
        goto LABEL_33;
      }
    }
    v14 = StringCchLengthW(v3, 0x7FFFFFFFu, &v20);
    v8 = v14;
    if ( v14 >= 0 )
    {
      v15 = ULongLongToULong(v20, &v19);
      v8 = v15;
      if ( v15 >= 0 )
      {
        v16 = v19 + 1;
        if ( v19 == -1 )
        {
          v8 = -2147024362;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
            (int)L"WdiGetInstanceFilePath",
            1953,
            (int)L"Error = %d",
            22);
        }
        else if ( a2 )
        {
          if ( *a3 >= v16 )
          {
            v17 = StringCchCopyW(a2, v16, v3);
            v8 = v17;
            if ( v17 < 0 )
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
                (int)L"WdiGetInstanceFilePath",
                1968,
                (int)L"Error = %d",
                v17);
          }
          else
          {
            *a3 = v16;
            v8 = -2147024662;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
              (int)L"WdiGetInstanceFilePath",
              1961,
              (int)L"Error = %d",
              234);
          }
        }
        else
        {
          *a3 = v16;
        }
      }
      else
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
          (int)L"WdiGetInstanceFilePath",
          1948,
          (int)L"Error = %d",
          v15);
      }
    }
    else
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
        (int)L"WdiGetInstanceFilePath",
        1945,
        (int)L"Error = %d",
        v14);
    }
  }
  else
  {
    v8 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\library.cpp",
      (int)L"WdiGetInstanceFilePath",
      1898,
      (int)L"Error = %d",
      14);
  }
LABEL_33:
  WdipFree(v3);
  return v8;
}

```

## disassembly

```asm
0x1800098e0  mov     [rsp+arg_8], rbx
0x1800098e5  push    rbp
0x1800098e6  push    rsi
0x1800098e7  push    rdi
0x1800098e8  sub     rsp, 30h
0x1800098ec  xor     edi, edi
0x1800098ee  mov     rsi, r8
0x1800098f1  mov     [rsp+48h+arg_18], rdi
0x1800098f6  mov     rbp, rdx
0x1800098f9  mov     [rsp+48h+arg_0], edi
0x1800098fd  mov     rbx, rcx
0x180009900  test    rcx, rcx
0x180009903  jnz     short loc_180009937
0x180009905  mov     r8d, 767h; int
0x18000990b  mov     ebx, 80070057h
0x180009910  mov     dword ptr [rsp+48h+Args], 57h ; 'W'; Args
0x180009918  lea     r9, aErrorD_0; "Error = %d"
0x18000991f  lea     rdx, aWdigetinstance_1; "WdiGetInstanceFilePath"
0x180009926  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000992d  call    WdipTraceError
0x180009932  jmp     loc_180009ADB
0x180009937  test    rsi, rsi
0x18000993a  jnz     short loc_180009944
0x18000993c  mov     r8d, 768h
0x180009942  jmp     short loc_18000990B
0x180009944  mov     ecx, 800h
0x180009949  call    WdipAlloc
0x18000994e  mov     rdi, rax
0x180009951  test    rax, rax
0x180009954  jnz     short loc_18000996B
0x180009956  mov     ebx, 8007000Eh
0x18000995b  mov     dword ptr [rsp+48h+Args], 0Eh
0x180009963  mov     r8d, 76Ah
0x180009969  jmp     short loc_180009918
0x18000996b  mov     ecx, [rbx+10h]
0x18000996e  test    ecx, ecx
0x180009970  jz      short loc_1800099DD
0x180009972  cmp     ecx, 1
0x180009975  jz      short loc_18000998C
0x180009977  mov     ebx, 800710DDh
0x18000997c  mov     dword ptr [rsp+48h+Args], 10DDh
0x180009984  mov     r8d, 791h
0x18000998a  jmp     short loc_180009918
0x18000998c  lea     rcx, [rbx+58h]
0x180009990  mov     rax, [rcx]
0x180009993  cmp     rax, cs:qword_180011870
0x18000999a  jnz     short loc_1800099B3
0x18000999c  mov     rax, [rcx+8]
0x1800099a0  cmp     rax, cs:qword_180011878
0x1800099a7  jnz     short loc_1800099B3
0x1800099a9  mov     ebx, 800710DDh
0x1800099ae  jmp     loc_180009ADB
0x1800099b3  lea     rdx, [rbx+28h]
0x1800099b7  mov     r9d, 400h
0x1800099bd  mov     r8, rdi
0x1800099c0  call    WdipVerifyDirectory
0x1800099c5  mov     ebx, eax
0x1800099c7  test    eax, eax
0x1800099c9  jns     short loc_180009A1F
0x1800099cb  movzx   ecx, ax
0x1800099ce  mov     r8d, 77Eh
0x1800099d4  mov     dword ptr [rsp+48h+Args], ecx
0x1800099d8  jmp     loc_180009918
0x1800099dd  mov     rcx, [rbx+28h]
0x1800099e1  test    rcx, rcx
0x1800099e4  jnz     short loc_1800099F1
0x1800099e6  mov     r8d, 784h
0x1800099ec  jmp     loc_18000990B
0x1800099f1  lea     rdx, [rcx+40h]
0x1800099f5  mov     r9d, 400h
0x1800099fb  add     rcx, 30h ; '0'
0x1800099ff  mov     r8, rdi
0x180009a02  call    WdipVerifyDirectory
0x180009a07  mov     ebx, eax
0x180009a09  test    eax, eax
0x180009a0b  jns     short loc_180009A1F
0x180009a0d  movzx   eax, ax
0x180009a10  mov     r8d, 78Bh
0x180009a16  mov     dword ptr [rsp+48h+Args], eax
0x180009a1a  jmp     loc_180009918
0x180009a1f  lea     r8, [rsp+48h+arg_18]; unsigned __int64 *
0x180009a24  mov     edx, 7FFFFFFFh; unsigned __int64
0x180009a29  mov     rcx, rdi; unsigned __int16 *
0x180009a2c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180009a31  mov     ebx, eax
0x180009a33  test    eax, eax
0x180009a35  jns     short loc_180009A49
0x180009a37  movzx   eax, ax
0x180009a3a  mov     r8d, 799h
0x180009a40  mov     dword ptr [rsp+48h+Args], eax
0x180009a44  jmp     loc_180009918
0x180009a49  mov     rcx, [rsp+48h+arg_18]; unsigned __int64
0x180009a4e  lea     rdx, [rsp+48h+arg_0]; unsigned int *
0x180009a53  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180009a58  mov     ebx, eax
0x180009a5a  test    eax, eax
0x180009a5c  jns     short loc_180009A70
0x180009a5e  movzx   eax, ax
0x180009a61  mov     r8d, 79Ch
0x180009a67  mov     dword ptr [rsp+48h+Args], eax
0x180009a6b  jmp     loc_180009918
0x180009a70  mov     eax, [rsp+48h+arg_0]
0x180009a74  add     eax, 1
0x180009a77  jnz     short loc_180009A91
0x180009a79  mov     ebx, 80070216h
0x180009a7e  mov     dword ptr [rsp+48h+Args], 216h
0x180009a86  mov     r8d, 7A1h
0x180009a8c  jmp     loc_180009918
0x180009a91  test    rbp, rbp
0x180009a94  jz      short loc_180009AD9
0x180009a96  cmp     [rsi], eax
0x180009a98  jnb     short loc_180009AB4
0x180009a9a  mov     [rsi], eax
0x180009a9c  mov     ebx, 800700EAh
0x180009aa1  mov     dword ptr [rsp+48h+Args], 0EAh
0x180009aa9  mov     r8d, 7A9h
0x180009aaf  jmp     loc_180009918
0x180009ab4  mov     edx, eax; unsigned __int64
0x180009ab6  mov     r8, rdi; unsigned __int16 *
0x180009ab9  mov     rcx, rbp; unsigned __int16 *
0x180009abc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009ac1  mov     ebx, eax
0x180009ac3  test    eax, eax
0x180009ac5  jns     short loc_180009ADB
0x180009ac7  movzx   eax, ax
0x180009aca  mov     r8d, 7B0h
0x180009ad0  mov     dword ptr [rsp+48h+Args], eax
0x180009ad4  jmp     loc_180009918
0x180009ad9  mov     [rsi], eax
0x180009adb  mov     rcx, rdi
0x180009ade  call    WdipFree
0x180009ae3  mov     eax, ebx
0x180009ae5  mov     rbx, [rsp+48h+arg_8]
0x180009aea  add     rsp, 30h
0x180009aee  pop     rdi
0x180009aef  pop     rsi
0x180009af0  pop     rbp
0x180009af1  retn
```
