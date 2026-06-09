# sd_dzip_init

- ea: `0x18009fc00`
- end: `0x1800a01f5`
- name: `sd_dzip_init`
- size: `1525`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180005d94`
- `0x180006244`

## callees

- `0x18009f5dc`
- `0x18009f878`
- `0x18009f9c8`
- `0x18009fa48`
- `0x18009fc00`
- `0x1800a18a8`
- `0x1800a1c48`
- `0x1800a236c`
- `0x1800a2458`
- `0x1800a2834`
- `0x1800a2f88`
- `0x1800a445c`
- `0x1800a72b0`
- `0x1800cf368`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18009ffb9`
- `KERNEL32!lstrlenA` at `0x1800a00e1`
- `KERNEL32!lstrlenA` at `0x1800a0155`
- `KERNEL32!lstrlenA` at `0x18009ffb9`
- `KERNEL32!lstrlenA` at `0x1800a00e1`
- `KERNEL32!lstrlenA` at `0x1800a0155`
- `KERNEL32!GetCurrentThreadId` at `0x18009fffa`
- `KERNEL32!GetCurrentThreadId` at `0x18009fffa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009fc45`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009fc68`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009fe6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009fc45`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009fc68`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009fe6b`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a009f`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800a009f`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryA` at `0x18009fdfc`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryA` at `0x18009fdfc`

## pseudocode

```c
__int64 __fastcall sd_dzip_init(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  DWORD v6; // ecx
  char *Value; // rbx
  __int64 result; // rax
  __int64 v9; // rbp
  int v10; // edx
  unsigned int v11; // edi
  DWORD v12; // ecx
  unsigned int v13; // eax
  DWORD CurrentThreadId; // eax
  const CHAR *v15; // rcx
  __int64 v16; // rax
  const CHAR *v17; // rcx
  __int64 v18; // rax
  char pszDest[16]; // [rsp+40h] [rbp-58h] BYREF

  if ( a3 )
  {
    v6 = dwZIPTlsIndex;
    *a3 = -1;
    Value = (char *)TlsGetValue(v6);
    if ( !Value )
    {
      if ( !(unsigned int)DzipThreadInit() )
        return 4;
      Value = (char *)TlsGetValue(dwZIPTlsIndex);
      if ( !Value )
        return 4;
    }
    if ( *((_DWORD *)Value + 51) )
    {
      *(_DWORD *)Value = 1;
      return 1;
    }
    *(_QWORD *)(Value + 204) = 1;
    *((_DWORD *)Value + 53) = 0;
    *((_QWORD *)Value + 63) = 0;
    *((_QWORD *)Value + 65) = 0;
    *((_QWORD *)Value + 66) = 0;
    *((_DWORD *)Value + 138) = 0;
    *((_QWORD *)Value + 75) = 0;
    *((_QWORD *)Value + 76) = 0;
    *((_QWORD *)Value + 395) = 0;
    *((_QWORD *)Value + 397) = 0;
    *((_DWORD *)Value + 128) = 0;
    *((_QWORD *)Value + 67) = 0;
    *((_QWORD *)Value + 68) = 0;
    Value[2856] = 0;
    Value[2596] = 0;
    *((_DWORD *)Value + 5569) = 1068;
    if ( (unsigned int)CopyZCS(Value + 22276, a1)
      || (*((_QWORD *)Value + 395) = *(_QWORD *)(Value + 22468),
          *((_QWORD *)Value + 397) = *(_QWORD *)(Value + 22476),
          *((_DWORD *)Value + 5570) != 6)
      && !*(_QWORD *)(Value + 22284) )
    {
      v11 = 16;
      *((_DWORD *)Value + 51) = 0;
      *(_DWORD *)Value = 16;
      return v11;
    }
    dzRemoveDoubleQuotes(Value + 1816, *(LPCSTR *)(Value + 22284));
    *((_WORD *)Value + 1870) = *((_WORD *)Value + 11242);
    *((_DWORD *)Value + 53) = (*((unsigned __int16 *)Value + 11243) >> 1) & 1;
    *((_DWORD *)Value + 1005) = (*((unsigned __int16 *)Value + 11243) >> 4) & 1;
    *((_DWORD *)Value + 150) = (*((unsigned __int16 *)Value + 11243) >> 6) & 1;
    *((_DWORD *)Value + 151) = (*((unsigned __int16 *)Value + 11243) >> 7) & 1;
    *((_DWORD *)Value + 152) = (*((unsigned __int16 *)Value + 11243) >> 9) & 1;
    *((_DWORD *)Value + 153) = (*((unsigned __int16 *)Value + 11243) >> 10) & 1;
    *((_DWORD *)Value + 154) = (*((unsigned __int16 *)Value + 11243) >> 14) & 1;
    GetCurrentDirectoryA(0x104u, Value + 2336);
    *((_DWORD *)Value + 452) = *((_WORD *)Value + 11243) & 1;
    if ( *((__int16 *)Value + 11242) < 0 )
    {
      v9 = (unsigned int)dzDriveFromPath(Value + 1816);
      if ( !(unsigned int)dzIsMediaRemovable(v9, Value) )
      {
        v10 = 5;
LABEL_14:
        dzMsgCB(*((_QWORD *)Value + 396), v10, 0, 0);
LABEL_15:
        v11 = 20;
LABEL_16:
        v12 = dwZIPTlsIndex;
        *(_DWORD *)Value = v11;
        *((_DWORD *)Value + 51) = 0;
        TlsGetValue(v12);
        return v11;
      }
      if ( *((_DWORD *)Value + 5570) != 4
        || *((_DWORD *)Value + 5589)
        || *((_DWORD *)Value + 5590)
        || *((_DWORD *)Value + 5593) )
      {
        goto LABEL_15;
      }
      if ( (unsigned int)IsItemListOnTarget((unsigned int)v9, *(_QWORD *)(Value + 22292)) )
      {
        v10 = 6;
        goto LABEL_14;
      }
    }
    init(Value);
    *((_DWORD *)Value + 779) = 0;
    *((_DWORD *)Value + 784) = 0;
    *((_DWORD *)Value + 796) = 1;
    *((_QWORD *)Value + 79) = *(_QWORD *)(Value + 22500);
    *((_QWORD *)Value + 80) = *(_QWORD *)(Value + 22508);
    *((_QWORD *)Value + 390) = *(_QWORD *)(Value + 22316);
    *((_QWORD *)Value + 391) = *(_QWORD *)(Value + 22324);
    *((_QWORD *)Value + 393) = *(_QWORD *)(Value + 22300);
    *((_QWORD *)Value + 394) = *(_QWORD *)(Value + 22308);
    if ( *((_DWORD *)Value + 5570) != 1
      && *((_DWORD *)Value + 5570) != 2
      && *((_DWORD *)Value + 5570) != 3
      && *((_DWORD *)Value + 5570) != 4
      && *((_DWORD *)Value + 5570) != 5
      && (unsigned int)(*((_DWORD *)Value + 5570) - 6) > 1 )
    {
      goto LABEL_56;
    }
    if ( *((__int16 *)Value + 1870) < 0 && *((_DWORD *)Value + 5586) && *(_QWORD *)(Value + 22348) )
    {
      *((_QWORD *)Value + 27) = -1;
      dzRemoveDoubleQuotes(Value + 2076, *(LPCSTR *)(Value + 22348));
      v13 = dzDriveFromPath(Value + 2076);
      if ( !(unsigned int)dzIsMediaRemovable(v13, Value) && RemainingDiskSpace(Value + 2076) >= 0x200000 )
      {
        StringCchCopyA(Value + 224, 0x104u, Value + 2076);
        if ( Value[lstrlenA(Value + 224) + 223] != 92 )
          StringCchCatA(Value + 224, 0x104u, "\\");
        StringCchCopyA(pszDest, 9u, "@@XXXXXX");
        CurrentThreadId = GetCurrentThreadId();
        pszDest[0] = prefixdigits[CurrentThreadId % 0x25];
        pszDest[1] = prefixdigits[CurrentThreadId / 0x25 % 0x25];
        StringCchCatA(Value + 224, 0x104u, pszDest);
        if ( MYmktemp(Value + 224) )
          *((_QWORD *)Value + 27) = CreateFileA(Value + 224, 0xC0000000, 3u, 0, 2u, 0x8000080u, 0);
      }
      if ( *((_QWORD *)Value + 27) == -1 )
      {
        v11 = 10;
        goto LABEL_16;
      }
    }
    if ( *((int *)Value + 5631) >= 0 )
    {
      if ( *(_QWORD *)(Value + 22516) )
      {
        v15 = *(const CHAR **)(Value + 22292);
        if ( v15 )
        {
          if ( lstrlenA(v15) > 0 )
          {
            *((_DWORD *)Value + 126) = 1;
            *((_QWORD *)Value + 65) = *((int *)Value + 5631);
            *((_QWORD *)Value + 66) = *(_QWORD *)(Value + 22516);
          }
        }
      }
    }
    v16 = *((_QWORD *)Value + 2811);
    if ( v16 )
    {
      *((_QWORD *)Value + 73) = *(_QWORD *)(v16 + 4);
      *((_QWORD *)Value + 74) = *(_QWORD *)(*((_QWORD *)Value + 2811) + 12LL);
    }
    if ( *((_DWORD *)Value + 5570) != 6 )
    {
      if ( *((_DWORD *)Value + 5570) != 7 )
        goto LABEL_54;
      v17 = *(const CHAR **)(Value + 22292);
      if ( v17 )
      {
        if ( lstrlenA(v17) > 0 )
        {
          v18 = *((_QWORD *)Value + 2811);
          if ( v18 )
          {
            if ( *(_QWORD *)(v18 + 4) )
            {
              *((_DWORD *)Value + 126) = 1;
              *((_DWORD *)Value + 127) = 1;
              *((_QWORD *)Value + 65) = 0;
LABEL_54:
              if ( !*((_DWORD *)Value + 138) )
              {
                result = sd_iz_init((__int64)(Value + 22276), (unsigned int *)Value);
                *a2 = Value + 22276;
                *a3 = *((_QWORD *)Value + 2920);
                return result;
              }
              return 16;
            }
          }
        }
      }
LABEL_56:
      v11 = 16;
      goto LABEL_16;
    }
  }
  return 16;
}

```

## disassembly

```asm
0x18009fc00  mov     [rsp+arg_0], rbx
0x18009fc05  push    rbp
0x18009fc06  push    rsi
0x18009fc07  push    rdi
0x18009fc08  push    r12
0x18009fc0a  push    r13
0x18009fc0c  push    r14
0x18009fc0e  push    r15
0x18009fc10  sub     rsp, 60h
0x18009fc14  mov     rax, cs:__security_cookie
0x18009fc1b  xor     rax, rsp
0x18009fc1e  mov     [rsp+98h+var_48], rax
0x18009fc23  xor     r13d, r13d
0x18009fc26  mov     r15, r8
0x18009fc29  mov     r12, rdx
0x18009fc2c  mov     rbp, rcx
0x18009fc2f  test    r8, r8
0x18009fc32  jz      loc_1800A01CA
0x18009fc38  mov     ecx, cs:dwZIPTlsIndex; dwTlsIndex
0x18009fc3e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009fc42  mov     [r8], r14
0x18009fc45  call    cs:__imp_TlsGetValue
0x18009fc4c  nop     dword ptr [rax+rax+00h]
0x18009fc51  mov     rbx, rax
0x18009fc54  test    rax, rax
0x18009fc57  jnz     short loc_18009FC86
0x18009fc59  call    DzipThreadInit
0x18009fc5e  test    eax, eax
0x18009fc60  jz      short loc_18009FC7C
0x18009fc62  mov     ecx, cs:dwZIPTlsIndex; dwTlsIndex
0x18009fc68  call    cs:__imp_TlsGetValue
0x18009fc6f  nop     dword ptr [rax+rax+00h]
0x18009fc74  mov     rbx, rax
0x18009fc77  test    rax, rax
0x18009fc7a  jnz     short loc_18009FC86
0x18009fc7c  mov     eax, 4
0x18009fc81  jmp     loc_1800A01CF
0x18009fc86  mov     esi, 1
0x18009fc8b  cmp     [rbx+0CCh], r13d
0x18009fc92  jz      short loc_18009FC9D
0x18009fc94  mov     [rbx], esi
0x18009fc96  mov     eax, esi
0x18009fc98  jmp     loc_1800A01CF
0x18009fc9d  mov     [rbx+0CCh], rsi
0x18009fca4  lea     rdi, [rbx+5704h]
0x18009fcab  mov     [rbx+0D4h], r13d
0x18009fcb2  mov     rcx, rdi
0x18009fcb5  mov     [rbx+1F8h], r13
0x18009fcbc  mov     rdx, rbp
0x18009fcbf  mov     [rbx+208h], r13
0x18009fcc6  mov     [rbx+210h], r13
0x18009fccd  mov     [rbx+228h], r13d
0x18009fcd4  mov     [rbx+258h], r13
0x18009fcdb  mov     [rbx+260h], r13
0x18009fce2  mov     [rbx+0C58h], r13
0x18009fce9  mov     [rbx+0C68h], r13
0x18009fcf0  mov     [rbx+200h], r13d
0x18009fcf7  mov     [rbx+218h], r13
0x18009fcfe  mov     [rbx+220h], r13
0x18009fd05  mov     [rbx+0B28h], r13b
0x18009fd0c  mov     [rbx+0A24h], r13b
0x18009fd13  mov     dword ptr [rdi], 42Ch
0x18009fd19  call    CopyZCS
0x18009fd1e  test    eax, eax
0x18009fd20  jnz     loc_1800A01B8
0x18009fd26  mov     rax, [rdi+0C0h]
0x18009fd2d  mov     [rbx+0C58h], rax
0x18009fd34  mov     rax, [rdi+0C8h]
0x18009fd3b  mov     [rbx+0C68h], rax
0x18009fd42  cmp     dword ptr [rdi+4], 6
0x18009fd46  jz      short loc_18009FD52
0x18009fd48  cmp     [rdi+8], r13
0x18009fd4c  jz      loc_1800A01B8
0x18009fd52  mov     rdx, [rdi+8]; LPCSTR
0x18009fd56  lea     rbp, [rbx+718h]
0x18009fd5d  mov     rcx, rbp; lpsz
0x18009fd60  call    dzRemoveDoubleQuotes
0x18009fd65  movzx   eax, word ptr [rdi+0D0h]
0x18009fd6c  lea     rdx, [rbx+920h]; lpBuffer
0x18009fd73  mov     [rbx+0E9Ch], ax
0x18009fd7a  mov     ecx, 104h; nBufferLength
0x18009fd7f  movzx   eax, word ptr [rdi+0D2h]
0x18009fd86  shr     eax, 1
0x18009fd88  and     eax, esi
0x18009fd8a  mov     [rbx+0D4h], eax
0x18009fd90  movzx   eax, word ptr [rdi+0D2h]
0x18009fd97  shr     eax, 4
0x18009fd9a  and     eax, esi
0x18009fd9c  mov     [rbx+0FB4h], eax
0x18009fda2  movzx   eax, word ptr [rdi+0D2h]
0x18009fda9  shr     eax, 6
0x18009fdac  and     eax, esi
0x18009fdae  mov     [rbx+258h], eax
0x18009fdb4  movzx   eax, word ptr [rdi+0D2h]
0x18009fdbb  shr     eax, 7
0x18009fdbe  and     eax, esi
0x18009fdc0  mov     [rbx+25Ch], eax
0x18009fdc6  movzx   eax, word ptr [rdi+0D2h]
0x18009fdcd  shr     eax, 9
0x18009fdd0  and     eax, esi
0x18009fdd2  mov     [rbx+260h], eax
0x18009fdd8  movzx   eax, word ptr [rdi+0D2h]
0x18009fddf  shr     eax, 0Ah
0x18009fde2  and     eax, esi
0x18009fde4  mov     [rbx+264h], eax
0x18009fdea  movzx   eax, word ptr [rdi+0D2h]
0x18009fdf1  shr     eax, 0Eh
0x18009fdf4  and     eax, esi
0x18009fdf6  mov     [rbx+268h], eax
0x18009fdfc  call    cs:__imp_GetCurrentDirectoryA
0x18009fe03  nop     dword ptr [rax+rax+00h]
0x18009fe08  movzx   eax, word ptr [rdi+0D2h]
0x18009fe0f  and     eax, esi
0x18009fe11  mov     [rbx+710h], eax
0x18009fe17  cmp     [rdi+0D0h], r13w
0x18009fe1f  jge     loc_18009FEAA
0x18009fe25  mov     rcx, rbp; lpszStart
0x18009fe28  call    dzDriveFromPath
0x18009fe2d  mov     rdx, rbx
0x18009fe30  mov     ecx, eax
0x18009fe32  mov     ebp, eax
0x18009fe34  call    dzIsMediaRemovable
0x18009fe39  test    eax, eax
0x18009fe3b  jnz     short loc_18009FE7C
0x18009fe3d  lea     edx, [rax+5]
0x18009fe40  mov     rcx, [rbx+0C60h]
0x18009fe47  xor     r9d, r9d
0x18009fe4a  xor     r8d, r8d
0x18009fe4d  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rbx
0x18009fe52  call    dzMsgCB
0x18009fe57  mov     edi, 14h
0x18009fe5c  mov     ecx, cs:dwZIPTlsIndex; dwTlsIndex
0x18009fe62  mov     [rbx], edi
0x18009fe64  mov     [rbx+0CCh], r13d
0x18009fe6b  call    cs:__imp_TlsGetValue
0x18009fe72  nop     dword ptr [rax+rax+00h]
0x18009fe77  jmp     loc_1800A01C6
0x18009fe7c  cmp     dword ptr [rdi+4], 4
0x18009fe80  jnz     short loc_18009FE57
0x18009fe82  cmp     [rdi+50h], r13d
0x18009fe86  jnz     short loc_18009FE57
0x18009fe88  cmp     [rdi+54h], r13d
0x18009fe8c  jnz     short loc_18009FE57
0x18009fe8e  cmp     [rdi+60h], r13d
0x18009fe92  jnz     short loc_18009FE57
0x18009fe94  mov     rdx, [rdi+10h]
0x18009fe98  mov     ecx, ebp
0x18009fe9a  call    IsItemListOnTarget
0x18009fe9f  test    eax, eax
0x18009fea1  jz      short loc_18009FEAA
0x18009fea3  mov     edx, 6
0x18009fea8  jmp     short loc_18009FE40
0x18009feaa  mov     rcx, rbx
0x18009fead  call    init
0x18009feb2  mov     [rbx+0C2Ch], r13d
0x18009feb9  mov     [rbx+0C40h], r13d
0x18009fec0  mov     [rbx+0C70h], esi
0x18009fec6  mov     rax, [rdi+0E0h]
0x18009fecd  mov     [rbx+278h], rax
0x18009fed4  mov     rax, [rdi+0E8h]
0x18009fedb  mov     [rbx+280h], rax
0x18009fee2  mov     rax, [rdi+28h]
0x18009fee6  mov     [rbx+0C30h], rax
0x18009feed  mov     rax, [rdi+30h]
0x18009fef1  mov     [rbx+0C38h], rax
0x18009fef8  mov     rax, [rdi+18h]
0x18009fefc  mov     [rbx+0C48h], rax
0x18009ff03  mov     rax, [rdi+20h]
0x18009ff07  mov     [rbx+0C50h], rax
0x18009ff0e  mov     ecx, [rdi+4]
0x18009ff11  sub     ecx, esi
0x18009ff13  jz      short loc_18009FF31
0x18009ff15  sub     ecx, esi
0x18009ff17  jz      short loc_18009FF31
0x18009ff19  sub     ecx, esi
0x18009ff1b  jz      short loc_18009FF31
0x18009ff1d  sub     ecx, esi
0x18009ff1f  jz      short loc_18009FF31
0x18009ff21  sub     ecx, esi
0x18009ff23  jz      short loc_18009FF31
0x18009ff25  sub     ecx, esi
0x18009ff27  jz      short loc_18009FF31
0x18009ff29  cmp     ecx, esi
0x18009ff2b  jnz     loc_1800A01AE
0x18009ff31  cmp     [rbx+0E9Ch], r13w
0x18009ff39  jge     loc_1800A00C6
0x18009ff3f  cmp     [rdi+44h], r13d
0x18009ff43  jz      loc_1800A00C6
0x18009ff49  cmp     [rdi+48h], r13
0x18009ff4d  jz      loc_1800A00C6
0x18009ff53  mov     [rbx+0D8h], r14
0x18009ff5a  lea     r14, [rbx+81Ch]
0x18009ff61  mov     rdx, [rdi+48h]; LPCSTR
0x18009ff65  mov     rcx, r14; lpsz
0x18009ff68  call    dzRemoveDoubleQuotes
0x18009ff6d  mov     rcx, r14; lpszStart
0x18009ff70  call    dzDriveFromPath
0x18009ff75  mov     rdx, rbx
0x18009ff78  mov     ecx, eax
0x18009ff7a  call    dzIsMediaRemovable
0x18009ff7f  test    eax, eax
0x18009ff81  jnz     loc_1800A00B2
0x18009ff87  mov     rcx, r14; pszSrc
0x18009ff8a  call    RemainingDiskSpace
0x18009ff8f  cmp     rax, 200000h
0x18009ff95  jl      loc_1800A00B2
0x18009ff9b  mov     r8, r14; pszSrc
0x18009ff9e  lea     rbp, [rbx+0E0h]
0x18009ffa5  mov     r14d, 104h
0x18009ffab  mov     rcx, rbp; pszDest
0x18009ffae  mov     edx, r14d; cchDest
0x18009ffb1  call    StringCchCopyA
0x18009ffb6  mov     rcx, rbp; lpString
0x18009ffb9  call    cs:__imp_lstrlenA
0x18009ffc0  nop     dword ptr [rax+rax+00h]
0x18009ffc5  movsxd  rcx, eax
0x18009ffc8  cmp     byte ptr [rcx+rbx+0DFh], 5Ch ; '\'
0x18009ffd0  jz      short loc_18009FFE4
0x18009ffd2  lea     r8, asc_1800EE530; "\\"
0x18009ffd9  mov     edx, r14d; cchDest
0x18009ffdc  mov     rcx, rbp; pszDest
0x18009ffdf  call    StringCchCatA
0x18009ffe4  lea     r8, aXxxxxx; "@@XXXXXX"
0x18009ffeb  mov     edx, 9; cchDest
0x18009fff0  lea     rcx, [rsp+98h+pszDest]; pszDest
0x18009fff5  call    StringCchCopyA
0x18009fffa  call    cs:__imp_GetCurrentThreadId
0x1800a0001  nop     dword ptr [rax+rax+00h]
0x1800a0006  mov     r8d, eax
0x1800a0009  mov     r10d, 0BACF914Dh
0x1800a000f  mov     r9d, r8d
0x1800a0012  mov     eax, r10d
0x1800a0015  mul     r8d
0x1800a0018  mov     eax, r10d
0x1800a001b  sub     r9d, edx
0x1800a001e  shr     r9d, 1
0x1800a0021  add     r9d, edx
0x1800a0024  shr     r9d, 5
0x1800a0028  mul     r9d
0x1800a002b  imul    ecx, r9d, 25h ; '%'
0x1800a002f  mov     eax, r9d
0x1800a0032  sub     eax, edx
0x1800a0034  shr     eax, 1
0x1800a0036  add     eax, edx
0x1800a0038  mov     rdx, r14; cchDest
0x1800a003b  shr     eax, 5
0x1800a003e  sub     r8d, ecx
0x1800a0041  imul    eax, 25h ; '%'
0x1800a0044  mov     ecx, r8d
0x1800a0047  lea     r8, prefixdigits; "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ_"
0x1800a004e  mov     cl, [rcx+r8]
0x1800a0052  sub     r9d, eax
0x1800a0055  mov     [rsp+98h+pszDest], cl
0x1800a0059  mov     rcx, rbp; pszDest
0x1800a005c  mov     al, [r9+r8]
0x1800a0060  lea     r8, [rsp+98h+pszDest]; pszSrc
0x1800a0065  mov     [rsp+98h+var_57], al
0x1800a0069  call    StringCchCatA
0x1800a006e  mov     rcx, rbp; FileName
0x1800a0071  call    MYmktemp
0x1800a0076  test    rax, rax
0x1800a0079  jz      short loc_1800A00B2
0x1800a007b  xor     r9d, r9d; lpSecurityAttributes
0x1800a007e  mov     [rsp+98h+hTemplateFile], r13; hTemplateFile
0x1800a0083  mov     [rsp+98h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x1800a008b  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a0090  mov     rcx, rbp; lpFileName
0x1800a0093  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x1800a009b  lea     r8d, [r9+3]; dwShareMode
0x1800a009f  call    cs:__imp_CreateFileA
0x1800a00a6  nop     dword ptr [rax+rax+00h]
0x1800a00ab  mov     [rbx+0D8h], rax
0x1800a00b2  cmp     qword ptr [rbx+0D8h], 0FFFFFFFFFFFFFFFFh
0x1800a00ba  jnz     short loc_1800A00C6
0x1800a00bc  mov     edi, 0Ah
0x1800a00c1  jmp     loc_18009FE5C
0x1800a00c6  cmp     [rdi+0F8h], r13d
0x1800a00cd  jl      short loc_1800A0113
0x1800a00cf  cmp     [rdi+0F0h], r13
0x1800a00d6  jz      short loc_1800A0113
0x1800a00d8  mov     rcx, [rdi+10h]; lpString
0x1800a00dc  test    rcx, rcx
0x1800a00df  jz      short loc_1800A0113
0x1800a00e1  call    cs:__imp_lstrlenA
0x1800a00e8  nop     dword ptr [rax+rax+00h]
0x1800a00ed  test    eax, eax
0x1800a00ef  jle     short loc_1800A0113
0x1800a00f1  mov     [rbx+1F8h], esi
0x1800a00f7  movsxd  rax, dword ptr [rdi+0F8h]
0x1800a00fe  mov     [rbx+208h], rax
0x1800a0105  mov     rax, [rdi+0F0h]
0x1800a010c  mov     [rbx+210h], rax
0x1800a0113  mov     rax, [rdi+0D4h]
0x1800a011a  test    rax, rax
0x1800a011d  jz      short loc_1800A013C
0x1800a011f  mov     rax, [rax+4]
0x1800a0123  mov     [rbx+248h], rax
0x1800a012a  mov     rax, [rdi+0D4h]
0x1800a0131  mov     rcx, [rax+0Ch]
0x1800a0135  mov     [rbx+250h], rcx
  ... truncated ...
```
