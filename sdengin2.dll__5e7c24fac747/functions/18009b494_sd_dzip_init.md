# sd_dzip_init

- ea: `0x18009b494`
- end: `0x18009ba4a`
- name: `sd_dzip_init`
- size: `1462`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180005c94`
- `0x180006134`

## callees

- `0x18009aeb0`
- `0x18009b144`
- `0x18009b270`
- `0x18009b2f0`
- `0x18009b494`
- `0x18009cfc8`
- `0x18009d350`
- `0x18009da0c`
- `0x18009dadc`
- `0x18009de58`
- `0x18009e540`
- `0x18009f8a4`
- `0x1800a24ac`
- `0x1800c9614`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18009b831`
- `KERNEL32!lstrlenA` at `0x18009b947`
- `KERNEL32!lstrlenA` at `0x18009b9b1`
- `KERNEL32!lstrlenA` at `0x18009b831`
- `KERNEL32!lstrlenA` at `0x18009b947`
- `KERNEL32!lstrlenA` at `0x18009b9b1`
- `KERNEL32!GetCurrentThreadId` at `0x18009b86c`
- `KERNEL32!GetCurrentThreadId` at `0x18009b86c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b4d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b4f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b6e9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b4d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b4f6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18009b6e9`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009b90b`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18009b90b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryA` at `0x18009b684`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryA` at `0x18009b684`

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
0x18009b494  mov     [rsp+arg_0], rbx
0x18009b499  push    rbp
0x18009b49a  push    rsi
0x18009b49b  push    rdi
0x18009b49c  push    r12
0x18009b49e  push    r13
0x18009b4a0  push    r14
0x18009b4a2  push    r15
0x18009b4a4  sub     rsp, 60h
0x18009b4a8  mov     rax, cs:__security_cookie
0x18009b4af  xor     rax, rsp
0x18009b4b2  mov     [rsp+98h+var_48], rax
0x18009b4b7  xor     r13d, r13d
0x18009b4ba  mov     r15, r8
0x18009b4bd  mov     r12, rdx
0x18009b4c0  mov     rbp, rcx
0x18009b4c3  test    r8, r8
0x18009b4c6  jz      loc_18009BA20
0x18009b4cc  mov     ecx, cs:dwZIPTlsIndex; dwTlsIndex
0x18009b4d2  or      r14, 0FFFFFFFFFFFFFFFFh
0x18009b4d6  mov     [r8], r14
0x18009b4d9  call    cs:__imp_TlsGetValue
0x18009b4df  mov     rbx, rax
0x18009b4e2  test    rax, rax
0x18009b4e5  jnz     short loc_18009B50E
0x18009b4e7  call    DzipThreadInit
0x18009b4ec  test    eax, eax
0x18009b4ee  jz      short loc_18009B504
0x18009b4f0  mov     ecx, cs:dwZIPTlsIndex; dwTlsIndex
0x18009b4f6  call    cs:__imp_TlsGetValue
0x18009b4fc  mov     rbx, rax
0x18009b4ff  test    rax, rax
0x18009b502  jnz     short loc_18009B50E
0x18009b504  mov     eax, 4
0x18009b509  jmp     loc_18009BA25
0x18009b50e  mov     esi, 1
0x18009b513  cmp     [rbx+0CCh], r13d
0x18009b51a  jz      short loc_18009B525
0x18009b51c  mov     [rbx], esi
0x18009b51e  mov     eax, esi
0x18009b520  jmp     loc_18009BA25
0x18009b525  mov     [rbx+0CCh], rsi
0x18009b52c  lea     rdi, [rbx+5704h]
0x18009b533  mov     [rbx+0D4h], r13d
0x18009b53a  mov     rcx, rdi
0x18009b53d  mov     [rbx+1F8h], r13
0x18009b544  mov     rdx, rbp
0x18009b547  mov     [rbx+208h], r13
0x18009b54e  mov     [rbx+210h], r13
0x18009b555  mov     [rbx+228h], r13d
0x18009b55c  mov     [rbx+258h], r13
0x18009b563  mov     [rbx+260h], r13
0x18009b56a  mov     [rbx+0C58h], r13
0x18009b571  mov     [rbx+0C68h], r13
0x18009b578  mov     [rbx+200h], r13d
0x18009b57f  mov     [rbx+218h], r13
0x18009b586  mov     [rbx+220h], r13
0x18009b58d  mov     [rbx+0B28h], r13b
0x18009b594  mov     [rbx+0A24h], r13b
0x18009b59b  mov     dword ptr [rdi], 42Ch
0x18009b5a1  call    CopyZCS
0x18009b5a6  test    eax, eax
0x18009b5a8  jnz     loc_18009BA0E
0x18009b5ae  mov     rax, [rdi+0C0h]
0x18009b5b5  mov     [rbx+0C58h], rax
0x18009b5bc  mov     rax, [rdi+0C8h]
0x18009b5c3  mov     [rbx+0C68h], rax
0x18009b5ca  cmp     dword ptr [rdi+4], 6
0x18009b5ce  jz      short loc_18009B5DA
0x18009b5d0  cmp     [rdi+8], r13
0x18009b5d4  jz      loc_18009BA0E
0x18009b5da  mov     rdx, [rdi+8]; LPCSTR
0x18009b5de  lea     rbp, [rbx+718h]
0x18009b5e5  mov     rcx, rbp; lpsz
0x18009b5e8  call    dzRemoveDoubleQuotes
0x18009b5ed  movzx   eax, word ptr [rdi+0D0h]
0x18009b5f4  lea     rdx, [rbx+920h]; lpBuffer
0x18009b5fb  mov     [rbx+0E9Ch], ax
0x18009b602  mov     ecx, 104h; nBufferLength
0x18009b607  movzx   eax, word ptr [rdi+0D2h]
0x18009b60e  shr     eax, 1
0x18009b610  and     eax, esi
0x18009b612  mov     [rbx+0D4h], eax
0x18009b618  movzx   eax, word ptr [rdi+0D2h]
0x18009b61f  shr     eax, 4
0x18009b622  and     eax, esi
0x18009b624  mov     [rbx+0FB4h], eax
0x18009b62a  movzx   eax, word ptr [rdi+0D2h]
0x18009b631  shr     eax, 6
0x18009b634  and     eax, esi
0x18009b636  mov     [rbx+258h], eax
0x18009b63c  movzx   eax, word ptr [rdi+0D2h]
0x18009b643  shr     eax, 7
0x18009b646  and     eax, esi
0x18009b648  mov     [rbx+25Ch], eax
0x18009b64e  movzx   eax, word ptr [rdi+0D2h]
0x18009b655  shr     eax, 9
0x18009b658  and     eax, esi
0x18009b65a  mov     [rbx+260h], eax
0x18009b660  movzx   eax, word ptr [rdi+0D2h]
0x18009b667  shr     eax, 0Ah
0x18009b66a  and     eax, esi
0x18009b66c  mov     [rbx+264h], eax
0x18009b672  movzx   eax, word ptr [rdi+0D2h]
0x18009b679  shr     eax, 0Eh
0x18009b67c  and     eax, esi
0x18009b67e  mov     [rbx+268h], eax
0x18009b684  call    cs:__imp_GetCurrentDirectoryA
0x18009b68a  movzx   eax, word ptr [rdi+0D2h]
0x18009b691  and     eax, esi
0x18009b693  mov     [rbx+710h], eax
0x18009b699  cmp     [rdi+0D0h], r13w
0x18009b6a1  jge     short loc_18009B722
0x18009b6a3  mov     rcx, rbp; lpszStart
0x18009b6a6  call    dzDriveFromPath
0x18009b6ab  mov     rdx, rbx
0x18009b6ae  mov     ecx, eax
0x18009b6b0  mov     ebp, eax
0x18009b6b2  call    dzIsMediaRemovable
0x18009b6b7  test    eax, eax
0x18009b6b9  jnz     short loc_18009B6F4
0x18009b6bb  lea     edx, [rax+5]
0x18009b6be  mov     rcx, [rbx+0C60h]
0x18009b6c5  xor     r9d, r9d
0x18009b6c8  xor     r8d, r8d
0x18009b6cb  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], rbx
0x18009b6d0  call    dzMsgCB
0x18009b6d5  mov     edi, 14h
0x18009b6da  mov     ecx, cs:dwZIPTlsIndex; dwTlsIndex
0x18009b6e0  mov     [rbx], edi
0x18009b6e2  mov     [rbx+0CCh], r13d
0x18009b6e9  call    cs:__imp_TlsGetValue
0x18009b6ef  jmp     loc_18009BA1C
0x18009b6f4  cmp     dword ptr [rdi+4], 4
0x18009b6f8  jnz     short loc_18009B6D5
0x18009b6fa  cmp     [rdi+50h], r13d
0x18009b6fe  jnz     short loc_18009B6D5
0x18009b700  cmp     [rdi+54h], r13d
0x18009b704  jnz     short loc_18009B6D5
0x18009b706  cmp     [rdi+60h], r13d
0x18009b70a  jnz     short loc_18009B6D5
0x18009b70c  mov     rdx, [rdi+10h]
0x18009b710  mov     ecx, ebp
0x18009b712  call    IsItemListOnTarget
0x18009b717  test    eax, eax
0x18009b719  jz      short loc_18009B722
0x18009b71b  mov     edx, 6
0x18009b720  jmp     short loc_18009B6BE
0x18009b722  mov     rcx, rbx
0x18009b725  call    init
0x18009b72a  mov     [rbx+0C2Ch], r13d
0x18009b731  mov     [rbx+0C40h], r13d
0x18009b738  mov     [rbx+0C70h], esi
0x18009b73e  mov     rax, [rdi+0E0h]
0x18009b745  mov     [rbx+278h], rax
0x18009b74c  mov     rax, [rdi+0E8h]
0x18009b753  mov     [rbx+280h], rax
0x18009b75a  mov     rax, [rdi+28h]
0x18009b75e  mov     [rbx+0C30h], rax
0x18009b765  mov     rax, [rdi+30h]
0x18009b769  mov     [rbx+0C38h], rax
0x18009b770  mov     rax, [rdi+18h]
0x18009b774  mov     [rbx+0C48h], rax
0x18009b77b  mov     rax, [rdi+20h]
0x18009b77f  mov     [rbx+0C50h], rax
0x18009b786  mov     ecx, [rdi+4]
0x18009b789  sub     ecx, esi
0x18009b78b  jz      short loc_18009B7A9
0x18009b78d  sub     ecx, esi
0x18009b78f  jz      short loc_18009B7A9
0x18009b791  sub     ecx, esi
0x18009b793  jz      short loc_18009B7A9
0x18009b795  sub     ecx, esi
0x18009b797  jz      short loc_18009B7A9
0x18009b799  sub     ecx, esi
0x18009b79b  jz      short loc_18009B7A9
0x18009b79d  sub     ecx, esi
0x18009b79f  jz      short loc_18009B7A9
0x18009b7a1  cmp     ecx, esi
0x18009b7a3  jnz     loc_18009BA04
0x18009b7a9  cmp     [rbx+0E9Ch], r13w
0x18009b7b1  jge     loc_18009B92C
0x18009b7b7  cmp     [rdi+44h], r13d
0x18009b7bb  jz      loc_18009B92C
0x18009b7c1  cmp     [rdi+48h], r13
0x18009b7c5  jz      loc_18009B92C
0x18009b7cb  mov     [rbx+0D8h], r14
0x18009b7d2  lea     r14, [rbx+81Ch]
0x18009b7d9  mov     rdx, [rdi+48h]; LPCSTR
0x18009b7dd  mov     rcx, r14; lpsz
0x18009b7e0  call    dzRemoveDoubleQuotes
0x18009b7e5  mov     rcx, r14; lpszStart
0x18009b7e8  call    dzDriveFromPath
0x18009b7ed  mov     rdx, rbx
0x18009b7f0  mov     ecx, eax
0x18009b7f2  call    dzIsMediaRemovable
0x18009b7f7  test    eax, eax
0x18009b7f9  jnz     loc_18009B918
0x18009b7ff  mov     rcx, r14; pszSrc
0x18009b802  call    RemainingDiskSpace
0x18009b807  cmp     rax, 200000h
0x18009b80d  jl      loc_18009B918
0x18009b813  mov     r8, r14; pszSrc
0x18009b816  lea     rbp, [rbx+0E0h]
0x18009b81d  mov     r14d, 104h
0x18009b823  mov     rcx, rbp; pszDest
0x18009b826  mov     edx, r14d; cchDest
0x18009b829  call    StringCchCopyA
0x18009b82e  mov     rcx, rbp; lpString
0x18009b831  call    cs:__imp_lstrlenA
0x18009b837  movsxd  rcx, eax
0x18009b83a  cmp     byte ptr [rcx+rbx+0DFh], 5Ch ; '\'
0x18009b842  jz      short loc_18009B856
0x18009b844  lea     r8, asc_1800E8550; "\\"
0x18009b84b  mov     edx, r14d; cchDest
0x18009b84e  mov     rcx, rbp; pszDest
0x18009b851  call    StringCchCatA
0x18009b856  lea     r8, aXxxxxx; "@@XXXXXX"
0x18009b85d  mov     edx, 9; cchDest
0x18009b862  lea     rcx, [rsp+98h+pszDest]; pszDest
0x18009b867  call    StringCchCopyA
0x18009b86c  call    cs:__imp_GetCurrentThreadId
0x18009b872  mov     r8d, eax
0x18009b875  mov     r10d, 0BACF914Dh
0x18009b87b  mov     r9d, r8d
0x18009b87e  mov     eax, r10d
0x18009b881  mul     r8d
0x18009b884  mov     eax, r10d
0x18009b887  sub     r9d, edx
0x18009b88a  shr     r9d, 1
0x18009b88d  add     r9d, edx
0x18009b890  shr     r9d, 5
0x18009b894  mul     r9d
0x18009b897  imul    ecx, r9d, 25h ; '%'
0x18009b89b  mov     eax, r9d
0x18009b89e  sub     eax, edx
0x18009b8a0  shr     eax, 1
0x18009b8a2  add     eax, edx
0x18009b8a4  mov     rdx, r14; cchDest
0x18009b8a7  shr     eax, 5
0x18009b8aa  sub     r8d, ecx
0x18009b8ad  imul    eax, 25h ; '%'
0x18009b8b0  mov     ecx, r8d
0x18009b8b3  lea     r8, prefixdigits; "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ_"
0x18009b8ba  mov     cl, [rcx+r8]
0x18009b8be  sub     r9d, eax
0x18009b8c1  mov     [rsp+98h+pszDest], cl
0x18009b8c5  mov     rcx, rbp; pszDest
0x18009b8c8  mov     al, [r9+r8]
0x18009b8cc  lea     r8, [rsp+98h+pszDest]; pszSrc
0x18009b8d1  mov     [rsp+98h+var_57], al
0x18009b8d5  call    StringCchCatA
0x18009b8da  mov     rcx, rbp; FileName
0x18009b8dd  call    MYmktemp
0x18009b8e2  test    rax, rax
0x18009b8e5  jz      short loc_18009B918
0x18009b8e7  xor     r9d, r9d; lpSecurityAttributes
0x18009b8ea  mov     [rsp+98h+hTemplateFile], r13; hTemplateFile
0x18009b8ef  mov     [rsp+98h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18009b8f7  mov     edx, 0C0000000h; dwDesiredAccess
0x18009b8fc  mov     rcx, rbp; lpFileName
0x18009b8ff  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x18009b907  lea     r8d, [r9+3]; dwShareMode
0x18009b90b  call    cs:__imp_CreateFileA
0x18009b911  mov     [rbx+0D8h], rax
0x18009b918  cmp     qword ptr [rbx+0D8h], 0FFFFFFFFFFFFFFFFh
0x18009b920  jnz     short loc_18009B92C
0x18009b922  mov     edi, 0Ah
0x18009b927  jmp     loc_18009B6DA
0x18009b92c  cmp     [rdi+0F8h], r13d
0x18009b933  jl      short loc_18009B973
0x18009b935  cmp     [rdi+0F0h], r13
0x18009b93c  jz      short loc_18009B973
0x18009b93e  mov     rcx, [rdi+10h]; lpString
0x18009b942  test    rcx, rcx
0x18009b945  jz      short loc_18009B973
0x18009b947  call    cs:__imp_lstrlenA
0x18009b94d  test    eax, eax
0x18009b94f  jle     short loc_18009B973
0x18009b951  mov     [rbx+1F8h], esi
0x18009b957  movsxd  rax, dword ptr [rdi+0F8h]
0x18009b95e  mov     [rbx+208h], rax
0x18009b965  mov     rax, [rdi+0F0h]
0x18009b96c  mov     [rbx+210h], rax
0x18009b973  mov     rax, [rdi+0D4h]
0x18009b97a  test    rax, rax
0x18009b97d  jz      short loc_18009B99C
0x18009b97f  mov     rax, [rax+4]
0x18009b983  mov     [rbx+248h], rax
0x18009b98a  mov     rax, [rdi+0D4h]
0x18009b991  mov     rcx, [rax+0Ch]
0x18009b995  mov     [rbx+250h], rcx
0x18009b99c  cmp     dword ptr [rdi+4], 6
0x18009b9a0  jz      short loc_18009BA20
0x18009b9a2  cmp     dword ptr [rdi+4], 7
0x18009b9a6  jnz     short loc_18009B9E0
0x18009b9a8  mov     rcx, [rdi+10h]; lpString
0x18009b9ac  test    rcx, rcx
0x18009b9af  jz      short loc_18009BA04
0x18009b9b1  call    cs:__imp_lstrlenA
  ... truncated ...
```
