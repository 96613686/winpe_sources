# WdsPickTempDriveBasedOnInstallDrive

- ea: `0x180007bb0`
- end: `0x180007d70`
- name: `WdsPickTempDriveBasedOnInstallDrive`
- size: `448`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180007a90`
- `0x180007b20`
- `0x180007bb0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007cae`
- `KERNEL32!GetLastError` at `0x180007ccc`
- `KERNEL32!GetLastError` at `0x180007d1d`
- `KERNEL32!GetLastError` at `0x180007d3b`
- `KERNEL32!GetLastError` at `0x180007cae`
- `KERNEL32!GetLastError` at `0x180007ccc`
- `KERNEL32!GetLastError` at `0x180007d1d`
- `KERNEL32!GetLastError` at `0x180007d3b`
- `WDSCORE!WdsInitializeDataUInt32` at `0x180007c64`
- `WDSCORE!WdsInitializeDataUInt32` at `0x180007c64`
- `WDSCORE!WdsFreeCollection` at `0x180007d0f`
- `WDSCORE!WdsFreeCollection` at `0x180007d0f`
- `WDSCORE!WdsPackCollection` at `0x180007c41`
- `WDSCORE!WdsPackCollection` at `0x180007c41`
- `WDSCORE!WdsAllocCollection` at `0x180007be0`
- `WDSCORE!WdsAllocCollection` at `0x180007be0`
- `WDSCORE!WdsFreeData` at `0x180007cef`
- `WDSCORE!WdsFreeData` at `0x180007d00`
- `WDSCORE!WdsFreeData` at `0x180007cef`
- `WDSCORE!WdsFreeData` at `0x180007d00`
- `WDSCORE!WdsPublishImmediateEx` at `0x180007c8f`
- `WDSCORE!WdsPublishImmediateEx` at `0x180007c8f`

## string_xrefs

- `0x180007c85`: `PickTempDrive`

## pseudocode

```c
__int64 __fastcall WdsPickTempDriveBasedOnInstallDrive(__int64 a1, int a2, __int64 a3, _DWORD *a4)
{
  __int64 v8; // rax
  __int64 v9; // rsi
  unsigned int v10; // ebx
  signed int LastError; // eax
  bool v12; // sf
  signed int v13; // eax
  signed int v14; // eax
  bool v15; // sf
  signed int v16; // eax
  __int128 v18; // [rsp+30h] [rbp-58h] BYREF
  _OWORD v19[4]; // [rsp+40h] [rbp-48h] BYREF

  if ( a2 < 0 || !a4 )
    return 2147942487LL;
  *a4 = -2147467259;
  v8 = WdsAllocCollection();
  v9 = v8;
  if ( v8 )
  {
    v19[0] = 0;
    v10 = 0;
    if ( (unsigned int)WdsCollectionAddUInt32(v8, L"DiskNumber", (unsigned int)a2) == 1
      && (unsigned int)WdsCollectionAddUInt64(v9, L"PartOffset", a3) == 1
      && (unsigned int)WdsPackCollection(v9, v19) == 1 )
    {
      v18 = 0;
      WdsInitializeDataUInt32(&v18, 1);
      if ( (unsigned int)WdsPublishImmediateEx(a1, L"PickTempDrive", 3735553, v19, &v18) == 1 && (_DWORD)v18 == 4 )
      {
        *a4 = DWORD2(v18);
      }
      else
      {
        LastError = GetLastError();
        v12 = LastError < 0;
        if ( LastError > 0 )
          v12 = 1;
        if ( v12 )
        {
          v13 = GetLastError();
          v10 = v13;
          if ( v13 > 0 )
            v10 = (unsigned __int16)v13 | 0x80070000;
        }
        else
        {
          v10 = -2147467259;
        }
      }
      WdsFreeData(&v18);
    }
    WdsFreeData(v19);
    WdsFreeCollection(v9);
  }
  else
  {
    v14 = GetLastError();
    v15 = v14 < 0;
    if ( v14 > 0 )
      v15 = 1;
    if ( v15 )
    {
      v16 = GetLastError();
      v10 = v16;
      if ( v16 > 0 )
        return (unsigned __int16)v16 | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180007bb0  push    rbx
0x180007bb2  push    rbp
0x180007bb3  push    rsi
0x180007bb4  push    rdi
0x180007bb5  push    r14
0x180007bb7  push    r15
0x180007bb9  sub     rsp, 58h
0x180007bbd  mov     rdi, r9
0x180007bc0  mov     r14, r8
0x180007bc3  mov     ebp, edx
0x180007bc5  mov     r15, rcx
0x180007bc8  test    edx, edx
0x180007bca  js      loc_180007D5D
0x180007bd0  test    r9, r9
0x180007bd3  jz      loc_180007D5D
0x180007bd9  mov     dword ptr [r9], 80004005h
0x180007be0  call    cs:__imp_WdsAllocCollection
0x180007be7  nop     dword ptr [rax+rax+00h]
0x180007bec  mov     rsi, rax
0x180007bef  test    rax, rax
0x180007bf2  jz      loc_180007D1D
0x180007bf8  xorps   xmm0, xmm0
0x180007bfb  lea     rdx, aDisknumber; "DiskNumber"
0x180007c02  mov     r8d, ebp
0x180007c05  mov     rcx, rax
0x180007c08  movups  [rsp+88h+var_48], xmm0
0x180007c0d  xor     ebx, ebx
0x180007c0f  call    WdsCollectionAddUInt32
0x180007c14  lea     ebp, [rbx+1]
0x180007c17  cmp     eax, ebp
0x180007c19  jnz     loc_180007CFB
0x180007c1f  mov     r8, r14
0x180007c22  lea     rdx, aPartoffset; "PartOffset"
0x180007c29  mov     rcx, rsi
0x180007c2c  call    WdsCollectionAddUInt64
0x180007c31  cmp     eax, ebp
0x180007c33  jnz     loc_180007CFB
0x180007c39  lea     rdx, [rsp+88h+var_48]
0x180007c3e  mov     rcx, rsi
0x180007c41  call    cs:__imp_WdsPackCollection
0x180007c48  nop     dword ptr [rax+rax+00h]
0x180007c4d  cmp     eax, ebp
0x180007c4f  jnz     loc_180007CFB
0x180007c55  xorps   xmm0, xmm0
0x180007c58  lea     rcx, [rsp+88h+var_58]
0x180007c5d  mov     edx, ebp
0x180007c5f  movups  [rsp+88h+var_58], xmm0
0x180007c64  call    cs:__imp_WdsInitializeDataUInt32
0x180007c6b  nop     dword ptr [rax+rax+00h]
0x180007c70  lea     rax, [rsp+88h+var_58]
0x180007c75  mov     r8d, 390001h
0x180007c7b  lea     r9, [rsp+88h+var_48]
0x180007c80  mov     [rsp+88h+var_68], rax
0x180007c85  lea     rdx, aPicktempdrive; "PickTempDrive"
0x180007c8c  mov     rcx, r15
0x180007c8f  call    cs:__imp_WdsPublishImmediateEx
0x180007c96  nop     dword ptr [rax+rax+00h]
0x180007c9b  cmp     eax, ebp
0x180007c9d  jnz     short loc_180007CAE
0x180007c9f  cmp     dword ptr [rsp+88h+var_58], 4
0x180007ca4  jnz     short loc_180007CAE
0x180007ca6  mov     eax, dword ptr [rsp+88h+var_58+8]
0x180007caa  mov     [rdi], eax
0x180007cac  jmp     short loc_180007CEA
0x180007cae  call    cs:__imp_GetLastError
0x180007cb5  nop     dword ptr [rax+rax+00h]
0x180007cba  mov     edi, 80070000h
0x180007cbf  test    eax, eax
0x180007cc1  jle     short loc_180007CCA
0x180007cc3  movzx   eax, ax
0x180007cc6  or      eax, edi
0x180007cc8  test    eax, eax
0x180007cca  jns     short loc_180007CE5
0x180007ccc  call    cs:__imp_GetLastError
0x180007cd3  nop     dword ptr [rax+rax+00h]
0x180007cd8  mov     ebx, eax
0x180007cda  test    eax, eax
0x180007cdc  jle     short loc_180007CEA
0x180007cde  movzx   ebx, ax
0x180007ce1  or      ebx, edi
0x180007ce3  jmp     short loc_180007CEA
0x180007ce5  mov     ebx, 80004005h
0x180007cea  lea     rcx, [rsp+88h+var_58]
0x180007cef  call    cs:__imp_WdsFreeData
0x180007cf6  nop     dword ptr [rax+rax+00h]
0x180007cfb  lea     rcx, [rsp+88h+var_48]
0x180007d00  call    cs:__imp_WdsFreeData
0x180007d07  nop     dword ptr [rax+rax+00h]
0x180007d0c  mov     rcx, rsi
0x180007d0f  call    cs:__imp_WdsFreeCollection
0x180007d16  nop     dword ptr [rax+rax+00h]
0x180007d1b  jmp     short loc_180007D59
0x180007d1d  call    cs:__imp_GetLastError
0x180007d24  nop     dword ptr [rax+rax+00h]
0x180007d29  mov     edi, 80070000h
0x180007d2e  test    eax, eax
0x180007d30  jle     short loc_180007D39
0x180007d32  movzx   eax, ax
0x180007d35  or      eax, edi
0x180007d37  test    eax, eax
0x180007d39  jns     short loc_180007D54
0x180007d3b  call    cs:__imp_GetLastError
0x180007d42  nop     dword ptr [rax+rax+00h]
0x180007d47  mov     ebx, eax
0x180007d49  test    eax, eax
0x180007d4b  jle     short loc_180007D59
0x180007d4d  movzx   ebx, ax
0x180007d50  or      ebx, edi
0x180007d52  jmp     short loc_180007D59
0x180007d54  mov     ebx, 80004005h
0x180007d59  mov     eax, ebx
0x180007d5b  jmp     short loc_180007D62
0x180007d5d  mov     eax, 80070057h
0x180007d62  add     rsp, 58h
0x180007d66  pop     r15
0x180007d68  pop     r14
0x180007d6a  pop     rdi
0x180007d6b  pop     rsi
0x180007d6c  pop     rbp
0x180007d6d  pop     rbx
0x180007d6e  retn
```
