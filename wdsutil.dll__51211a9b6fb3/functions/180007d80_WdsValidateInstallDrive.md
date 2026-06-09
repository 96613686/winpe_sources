# WdsValidateInstallDrive

- ea: `0x180007d80`
- end: `0x180007f40`
- name: `WdsValidateInstallDrive`
- size: `448`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180007a90`
- `0x180007b20`
- `0x180007d80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007e7e`
- `KERNEL32!GetLastError` at `0x180007e9c`
- `KERNEL32!GetLastError` at `0x180007eed`
- `KERNEL32!GetLastError` at `0x180007f0b`
- `KERNEL32!GetLastError` at `0x180007e7e`
- `KERNEL32!GetLastError` at `0x180007e9c`
- `KERNEL32!GetLastError` at `0x180007eed`
- `KERNEL32!GetLastError` at `0x180007f0b`
- `WDSCORE!WdsInitializeDataUInt32` at `0x180007e34`
- `WDSCORE!WdsInitializeDataUInt32` at `0x180007e34`
- `WDSCORE!WdsFreeCollection` at `0x180007edf`
- `WDSCORE!WdsFreeCollection` at `0x180007edf`
- `WDSCORE!WdsPackCollection` at `0x180007e11`
- `WDSCORE!WdsPackCollection` at `0x180007e11`
- `WDSCORE!WdsAllocCollection` at `0x180007db0`
- `WDSCORE!WdsAllocCollection` at `0x180007db0`
- `WDSCORE!WdsFreeData` at `0x180007ebf`
- `WDSCORE!WdsFreeData` at `0x180007ed0`
- `WDSCORE!WdsFreeData` at `0x180007ebf`
- `WDSCORE!WdsFreeData` at `0x180007ed0`
- `WDSCORE!WdsPublishImmediateEx` at `0x180007e5f`
- `WDSCORE!WdsPublishImmediateEx` at `0x180007e5f`

## pseudocode

```c
__int64 __fastcall WdsValidateInstallDrive(__int64 a1, int a2, __int64 a3, _DWORD *a4)
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
      if ( (unsigned int)WdsPublishImmediateEx(a1, L"DriveInformation", 589826, v19, &v18) == 1 && (_DWORD)v18 == 4 )
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
0x180007d80  push    rbx
0x180007d82  push    rbp
0x180007d83  push    rsi
0x180007d84  push    rdi
0x180007d85  push    r14
0x180007d87  push    r15
0x180007d89  sub     rsp, 58h
0x180007d8d  mov     rdi, r9
0x180007d90  mov     r14, r8
0x180007d93  mov     ebp, edx
0x180007d95  mov     r15, rcx
0x180007d98  test    edx, edx
0x180007d9a  js      loc_180007F2D
0x180007da0  test    r9, r9
0x180007da3  jz      loc_180007F2D
0x180007da9  mov     dword ptr [r9], 80004005h
0x180007db0  call    cs:__imp_WdsAllocCollection
0x180007db7  nop     dword ptr [rax+rax+00h]
0x180007dbc  mov     rsi, rax
0x180007dbf  test    rax, rax
0x180007dc2  jz      loc_180007EED
0x180007dc8  xorps   xmm0, xmm0
0x180007dcb  lea     rdx, aDisknumber; "DiskNumber"
0x180007dd2  mov     r8d, ebp
0x180007dd5  mov     rcx, rax
0x180007dd8  movups  [rsp+88h+var_48], xmm0
0x180007ddd  xor     ebx, ebx
0x180007ddf  call    WdsCollectionAddUInt32
0x180007de4  lea     ebp, [rbx+1]
0x180007de7  cmp     eax, ebp
0x180007de9  jnz     loc_180007ECB
0x180007def  mov     r8, r14
0x180007df2  lea     rdx, aPartoffset; "PartOffset"
0x180007df9  mov     rcx, rsi
0x180007dfc  call    WdsCollectionAddUInt64
0x180007e01  cmp     eax, ebp
0x180007e03  jnz     loc_180007ECB
0x180007e09  lea     rdx, [rsp+88h+var_48]
0x180007e0e  mov     rcx, rsi
0x180007e11  call    cs:__imp_WdsPackCollection
0x180007e18  nop     dword ptr [rax+rax+00h]
0x180007e1d  cmp     eax, ebp
0x180007e1f  jnz     loc_180007ECB
0x180007e25  xorps   xmm0, xmm0
0x180007e28  lea     rcx, [rsp+88h+var_58]
0x180007e2d  mov     edx, ebp
0x180007e2f  movups  [rsp+88h+var_58], xmm0
0x180007e34  call    cs:__imp_WdsInitializeDataUInt32
0x180007e3b  nop     dword ptr [rax+rax+00h]
0x180007e40  lea     rax, [rsp+88h+var_58]
0x180007e45  mov     r8d, 90002h
0x180007e4b  lea     r9, [rsp+88h+var_48]
0x180007e50  mov     [rsp+88h+var_68], rax
0x180007e55  lea     rdx, aDriveinformati; "DriveInformation"
0x180007e5c  mov     rcx, r15
0x180007e5f  call    cs:__imp_WdsPublishImmediateEx
0x180007e66  nop     dword ptr [rax+rax+00h]
0x180007e6b  cmp     eax, ebp
0x180007e6d  jnz     short loc_180007E7E
0x180007e6f  cmp     dword ptr [rsp+88h+var_58], 4
0x180007e74  jnz     short loc_180007E7E
0x180007e76  mov     eax, dword ptr [rsp+88h+var_58+8]
0x180007e7a  mov     [rdi], eax
0x180007e7c  jmp     short loc_180007EBA
0x180007e7e  call    cs:__imp_GetLastError
0x180007e85  nop     dword ptr [rax+rax+00h]
0x180007e8a  mov     edi, 80070000h
0x180007e8f  test    eax, eax
0x180007e91  jle     short loc_180007E9A
0x180007e93  movzx   eax, ax
0x180007e96  or      eax, edi
0x180007e98  test    eax, eax
0x180007e9a  jns     short loc_180007EB5
0x180007e9c  call    cs:__imp_GetLastError
0x180007ea3  nop     dword ptr [rax+rax+00h]
0x180007ea8  mov     ebx, eax
0x180007eaa  test    eax, eax
0x180007eac  jle     short loc_180007EBA
0x180007eae  movzx   ebx, ax
0x180007eb1  or      ebx, edi
0x180007eb3  jmp     short loc_180007EBA
0x180007eb5  mov     ebx, 80004005h
0x180007eba  lea     rcx, [rsp+88h+var_58]
0x180007ebf  call    cs:__imp_WdsFreeData
0x180007ec6  nop     dword ptr [rax+rax+00h]
0x180007ecb  lea     rcx, [rsp+88h+var_48]
0x180007ed0  call    cs:__imp_WdsFreeData
0x180007ed7  nop     dword ptr [rax+rax+00h]
0x180007edc  mov     rcx, rsi
0x180007edf  call    cs:__imp_WdsFreeCollection
0x180007ee6  nop     dword ptr [rax+rax+00h]
0x180007eeb  jmp     short loc_180007F29
0x180007eed  call    cs:__imp_GetLastError
0x180007ef4  nop     dword ptr [rax+rax+00h]
0x180007ef9  mov     edi, 80070000h
0x180007efe  test    eax, eax
0x180007f00  jle     short loc_180007F09
0x180007f02  movzx   eax, ax
0x180007f05  or      eax, edi
0x180007f07  test    eax, eax
0x180007f09  jns     short loc_180007F24
0x180007f0b  call    cs:__imp_GetLastError
0x180007f12  nop     dword ptr [rax+rax+00h]
0x180007f17  mov     ebx, eax
0x180007f19  test    eax, eax
0x180007f1b  jle     short loc_180007F29
0x180007f1d  movzx   ebx, ax
0x180007f20  or      ebx, edi
0x180007f22  jmp     short loc_180007F29
0x180007f24  mov     ebx, 80004005h
0x180007f29  mov     eax, ebx
0x180007f2b  jmp     short loc_180007F32
0x180007f2d  mov     eax, 80070057h
0x180007f32  add     rsp, 58h
0x180007f36  pop     r15
0x180007f38  pop     r14
0x180007f3a  pop     rdi
0x180007f3b  pop     rsi
0x180007f3c  pop     rbp
0x180007f3d  pop     rbx
0x180007f3e  retn
```
