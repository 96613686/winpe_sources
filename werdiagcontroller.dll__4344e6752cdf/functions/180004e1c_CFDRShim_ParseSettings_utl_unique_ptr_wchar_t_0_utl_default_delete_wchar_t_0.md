# CFDRShim::ParseSettings(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)

- ea: `0x180004e1c`
- end: `0x180005150`
- name: `?ParseSettings@CFDRShim@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(unsigned int *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180005488`

## callees

- `0x180001400`
- `0x180001cd4`
- `0x180003b58`
- `0x18000462c`
- `0x180004bc8`
- `0x180004e1c`
- `0x18000567c`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180004eae`
- `ntdll!DbgPrintEx` at `0x180004ef3`
- `ntdll!DbgPrintEx` at `0x180004fc4`
- `ntdll!DbgPrintEx` at `0x18000509c`
- `ntdll!DbgPrintEx` at `0x1800050b6`
- `ntdll!DbgPrintEx` at `0x1800050d0`
- `ntdll!DbgPrintEx` at `0x18000511e`
- `ntdll!DbgPrintEx` at `0x180004eae`
- `ntdll!DbgPrintEx` at `0x180004ef3`
- `ntdll!DbgPrintEx` at `0x180004fc4`
- `ntdll!DbgPrintEx` at `0x18000509c`
- `ntdll!DbgPrintEx` at `0x1800050b6`
- `ntdll!DbgPrintEx` at `0x1800050d0`
- `ntdll!DbgPrintEx` at `0x18000511e`

## string_xrefs

- `0x1800050ab`: `WERDIAG: Failed extracting next token from settings string. HRESULT: %08X\n`
- `0x180005091`: `WERDIAG: Failed extracting next pair from the current token. HRESULT: %08X\n`

## pseudocode

```c
__int64 __fastcall CFDRShim::ParseSettings(unsigned int *a1, _QWORD *a2)
{
  unsigned int v2; // ebx
  void *v5; // rsi
  wchar_t **unique_for; // rax
  wchar_t *v7; // r12
  wchar_t **v8; // rax
  wchar_t *v9; // r15
  __int64 v10; // rcx
  int NextToken; // eax
  int v12; // eax
  unsigned int v13; // r9d
  int v14; // eax
  CFDRShim *v15; // rcx
  int updated; // eax
  int v17; // edx
  __m128i v18; // xmm0
  __m128i v19; // xmm1
  unsigned __int16 v20; // ax
  unsigned int v21; // eax
  unsigned int v23; // [rsp+28h] [rbp-41h]
  unsigned int v24; // [rsp+30h] [rbp-39h] BYREF
  void *v25; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v26[28]; // [rsp+40h] [rbp-29h] BYREF
  __m128i v27[2]; // [rsp+60h] [rbp-9h] BYREF

  v2 = 0;
  v25 = 0;
  v24 = 0;
  memset(v27, 0, 28);
  v5 = 0;
  if ( a2 && *a2 )
  {
    unique_for = (wchar_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(v26, 128);
    v7 = *unique_for;
    *unique_for = 0;
    if ( *(_QWORD *)v26 )
      operator delete[](*(void **)v26);
    if ( v7 )
    {
      v8 = (wchar_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(v26, 512);
      v9 = *v8;
      *v8 = 0;
      v10 = *(_QWORD *)v26;
      if ( *(_QWORD *)v26 )
        operator delete[](*(void **)v26);
      if ( v9 )
      {
LABEL_11:
        while ( *a2 )
        {
          NextToken = CFDRShim::GetNextToken(v10, a2, 59, &v25);
          v2 = NextToken;
          if ( NextToken < 0 )
          {
            DbgPrintEx(
              0x96u,
              0,
              "WERDIAG: Failed extracting next token from settings string. HRESULT: %08X\n",
              NextToken);
            goto LABEL_37;
          }
          v2 = 0;
          if ( v25 )
          {
            v27[1].m128i_i64[0] = 0;
            *(_OWORD *)v26 = 0;
            v27[0].m128i_i32[0] = 0;
            v27[0].m128i_i16[2] = _mm_extract_epi16((__m128i)0LL, 2);
            v27[0].m128i_i16[3] = _mm_extract_epi16((__m128i)0LL, 3);
            v27[0].m128i_i64[1] = 0;
            while ( v25 )
            {
              *(_QWORD *)v26 = 0;
              if ( v5 )
                operator delete[](v5);
              v12 = CFDRShim::GetNextToken(v10, &v25, 44, v26);
              v2 = v12;
              if ( v12 < 0 )
              {
                DbgPrintEx(
                  0x96u,
                  0,
                  "WERDIAG: Failed extracting next pair from the current token. HRESULT: %08X\n",
                  v12);
                v5 = *(void **)v26;
                goto LABEL_37;
              }
              v5 = *(void **)v26;
              v2 = 0;
              if ( *(_QWORD *)v26 )
              {
                v14 = CFDRShim::ParsePair((CFDRShim *)v10, *(wchar_t **)v26, v7, v13, v9, v23);
                if ( v14 >= 0 )
                {
                  updated = CFDRShim::UpdateGUIDSettings(v15, v7, v9, (struct GUID_SETTINGS *)v27, &v24);
                  if ( updated < 0 )
                    DbgPrintEx(
                      0x96u,
                      0,
                      "WERDIAG: Failed updating settings; Parsing continues. HRESULT: %08X\n",
                      (unsigned int)updated);
                }
                else
                {
                  DbgPrintEx(
                    0x96u,
                    0,
                    "WERDIAG: Error parsing current pair; Ignoring pair and continuing parsing. HRESULT: %08X\n",
                    (unsigned int)v14);
                }
              }
            }
            v17 = _mm_cvtsi128_si32(v27[0]);
            *(__m128i *)v26 = v27[0];
            *(__m128i *)&v26[12] = *(__m128i *)((char *)v27 + 12);
            if ( !v17
              && !(unsigned __int16)_mm_extract_epi16(v27[0], 2)
              && !(unsigned __int16)_mm_extract_epi16(v27[0], 3) )
            {
              LODWORD(v10) = 0;
              while ( !v26[(unsigned int)v10 + 8] )
              {
                v10 = (unsigned int)(v10 + 1);
                if ( (unsigned int)v10 >= 8 )
                  goto LABEL_11;
              }
            }
            v10 = 28LL * *a1;
            v18 = _mm_srli_si128(*(__m128i *)((char *)v27 + 12), 4);
            v19 = _mm_srli_si128(*(__m128i *)((char *)v27 + 12), 8);
            v20 = *(_WORD *)&v26[4];
            *(unsigned int *)((char *)a1 + v10 + 8) = v17;
            *(unsigned int *)((char *)a1 + v10 + 12) = __PAIR32__(*(unsigned __int16 *)&v26[6], v20);
            *(_QWORD *)((char *)a1 + v10 + 16) = *(_QWORD *)&v26[8];
            v21 = *(_DWORD *)&v26[24];
            *(unsigned int *)((char *)a1 + v10 + 24) = _mm_cvtsi128_si32(v18);
            *(unsigned int *)((char *)a1 + v10 + 28) = _mm_cvtsi128_si32(v19);
            *(unsigned int *)((char *)a1 + v10 + 32) = v21;
            ++*a1;
          }
        }
        if ( v24 )
        {
          a1[1] = v24;
        }
        else
        {
          DbgPrintEx(0x96u, 0, "WERDIAG: Log file size was not specified; Logging will not be enabled\n");
          v2 = -2147467259;
        }
LABEL_37:
        operator delete[](v9);
      }
      else
      {
        DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for string buffer\n");
        v2 = -2147024882;
      }
      operator delete[](v7);
    }
    else
    {
      DbgPrintEx(0x96u, 0, "WERDIAG: Out of resources allocating memory for string buffer\n");
      v2 = -2147024882;
    }
    if ( v25 )
      operator delete[](v25);
    if ( v5 )
      operator delete[](v5);
    return v2;
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: Invalid argument: settins string cannot be NULL\n");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180004e1c  mov     [rsp-8+arg_10], rbx
0x180004e21  push    rbp
0x180004e22  push    rsi
0x180004e23  push    rdi
0x180004e24  push    r12
0x180004e26  push    r13
0x180004e28  push    r14
0x180004e2a  push    r15
0x180004e2c  lea     rbp, [rsp-27h]
0x180004e31  sub     rsp, 90h
0x180004e38  mov     rax, cs:__security_cookie
0x180004e3f  xor     rax, rsp
0x180004e42  mov     [rbp+57h+var_40], rax
0x180004e46  xor     ebx, ebx
0x180004e48  xor     eax, eax
0x180004e4a  mov     [rbp+57h+var_88], rbx
0x180004e4e  xorps   xmm0, xmm0
0x180004e51  mov     [rbp+57h+var_90], ebx
0x180004e54  mov     r14, rdx
0x180004e57  mov     dword ptr [rbp+57h+var_60], ebx
0x180004e5a  mov     r13, rcx
0x180004e5d  mov     [rbp+57h+var_4C], rax
0x180004e61  mov     esi, ebx
0x180004e63  movups  [rbp+57h+var_60+4], xmm0
0x180004e67  test    rdx, rdx
0x180004e6a  jz      loc_180005110
0x180004e70  cmp     [rdx], rbx
0x180004e73  jz      loc_180005110
0x180004e79  mov     edx, 80h
0x180004e7e  lea     rcx, [rbp+57h+var_80]
0x180004e82  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180004e87  mov     r12, [rax]
0x180004e8a  mov     [rax], rbx
0x180004e8d  mov     rcx, [rbp+57h+var_80]; void *
0x180004e91  test    rcx, rcx
0x180004e94  jz      short loc_180004E9B
0x180004e96  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004e9b  test    r12, r12
0x180004e9e  jnz     short loc_180004EBE
0x180004ea0  lea     r8, aWerdiagOutOfRe; "WERDIAG: Out of resources allocating me"...
0x180004ea7  xor     edx, edx; Level
0x180004ea9  mov     ecx, 96h; ComponentId
0x180004eae  call    cs:__imp_DbgPrintEx
0x180004eb4  mov     ebx, 8007000Eh
0x180004eb9  jmp     loc_1800050F1
0x180004ebe  mov     edx, 200h
0x180004ec3  lea     rcx, [rbp+57h+var_80]
0x180004ec7  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x180004ecc  mov     r15, [rax]
0x180004ecf  mov     [rax], rbx
0x180004ed2  mov     rcx, [rbp+57h+var_80]; void *
0x180004ed6  test    rcx, rcx
0x180004ed9  jz      short loc_180004EE0
0x180004edb  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004ee0  test    r15, r15
0x180004ee3  jnz     short loc_180004F03
0x180004ee5  lea     r8, aWerdiagOutOfRe; "WERDIAG: Out of resources allocating me"...
0x180004eec  xor     edx, edx; Level
0x180004eee  mov     ecx, 96h; ComponentId
0x180004ef3  call    cs:__imp_DbgPrintEx
0x180004ef9  mov     ebx, 8007000Eh
0x180004efe  jmp     loc_1800050E9
0x180004f03  mov     edi, 96h
0x180004f08  cmp     [r14], rbx
0x180004f0b  jz      loc_1800050BE
0x180004f11  mov     r8d, 3Bh ; ';'
0x180004f17  lea     r9, [rbp+57h+var_88]
0x180004f1b  mov     rdx, r14
0x180004f1e  call    ?GetNextToken@CFDRShim@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@_W0@Z; CFDRShim::GetNextToken(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,wchar_t,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x180004f23  mov     ebx, eax
0x180004f25  test    eax, eax
0x180004f27  js      loc_1800050A8
0x180004f2d  xor     ebx, ebx
0x180004f2f  cmp     [rbp+57h+var_88], rbx
0x180004f33  jz      short loc_180004F08
0x180004f35  xorps   xmm0, xmm0
0x180004f38  mov     [rbp+7], rbx
0x180004f3c  pextrw  eax, xmm0, 2
0x180004f41  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180004f45  movss   dword ptr [rbp+57h+var_60], xmm0
0x180004f4a  mov     word ptr [rbp+57h+var_60+4], ax
0x180004f4e  pextrw  eax, xmm0, 3
0x180004f53  mov     word ptr [rbp+57h+var_60+6], ax
0x180004f57  mov     rax, [rbp+57h+var_80+8]
0x180004f5b  mov     qword ptr [rbp+57h+var_60+8], rax
0x180004f5f  cmp     [rbp+57h+var_88], rbx
0x180004f63  jz      loc_180004FF5
0x180004f69  mov     [rbp+57h+var_80], rbx
0x180004f6d  test    rsi, rsi
0x180004f70  jz      short loc_180004F7A
0x180004f72  mov     rcx, rsi; void *
0x180004f75  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004f7a  mov     r8d, 2Ch ; ','
0x180004f80  lea     r9, [rbp+57h+var_80]
0x180004f84  lea     rdx, [rbp+57h+var_88]
0x180004f88  call    ?GetNextToken@CFDRShim@@AEAAJPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@_W0@Z; CFDRShim::GetNextToken(utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,wchar_t,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x180004f8d  mov     ebx, eax
0x180004f8f  test    eax, eax
0x180004f91  js      loc_18000508E
0x180004f97  mov     rsi, [rbp+57h+var_80]
0x180004f9b  xor     ebx, ebx
0x180004f9d  test    rsi, rsi
0x180004fa0  jz      short loc_180004F5F
0x180004fa2  mov     r8, r12; wchar_t *
0x180004fa5  mov     [rsp+0C0h+var_A0], r15; wchar_t *
0x180004faa  mov     rdx, rsi; wchar_t *
0x180004fad  call    ?ParsePair@CFDRShim@@AEAAJPEA_W0K0K@Z; CFDRShim::ParsePair(wchar_t *,wchar_t *,ulong,wchar_t *,ulong)
0x180004fb2  test    eax, eax
0x180004fb4  jns     short loc_180004FCC
0x180004fb6  lea     r8, aWerdiagErrorPa; "WERDIAG: Error parsing current pair; Ig"...
0x180004fbd  mov     r9d, eax
0x180004fc0  xor     edx, edx; Level
0x180004fc2  mov     ecx, edi; ComponentId
0x180004fc4  call    cs:__imp_DbgPrintEx
0x180004fca  jmp     short loc_180004F5F
0x180004fcc  lea     rax, [rbp+57h+var_90]
0x180004fd0  mov     r8, r15; wchar_t *
0x180004fd3  lea     r9, [rbp+57h+var_60]; struct GUID_SETTINGS *
0x180004fd7  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x180004fdc  mov     rdx, r12; wchar_t *
0x180004fdf  call    ?UpdateGUIDSettings@CFDRShim@@AEAAJPEB_W0PEAUGUID_SETTINGS@@PEAK@Z; CFDRShim::UpdateGUIDSettings(wchar_t const *,wchar_t const *,GUID_SETTINGS *,ulong *)
0x180004fe4  test    eax, eax
0x180004fe6  jns     loc_180004F5F
0x180004fec  lea     r8, aWerdiagFailedU; "WERDIAG: Failed updating settings; Pars"...
0x180004ff3  jmp     short loc_180004FBD
0x180004ff5  movups  xmm0, [rbp+57h+var_60]
0x180004ff9  movups  xmm1, [rbp+57h+var_60+0Ch]
0x180004ffd  movd    edx, xmm0
0x180005001  movaps  xmmword ptr [rbp+57h+var_80], xmm0
0x180005005  movups  xmmword ptr [rbp+57h+var_80+0Ch], xmm1
0x180005009  test    edx, edx
0x18000500b  jnz     short loc_180005037
0x18000500d  pextrw  eax, xmm0, 2
0x180005012  test    ax, ax
0x180005015  jnz     short loc_180005037
0x180005017  pextrw  eax, xmm0, 3
0x18000501c  test    ax, ax
0x18000501f  jnz     short loc_180005037
0x180005021  mov     ecx, ebx
0x180005023  mov     eax, ecx
0x180005025  cmp     byte ptr [rbp+rax+57h+var_80+8], bl
0x180005029  jnz     short loc_180005037
0x18000502b  inc     ecx
0x18000502d  cmp     ecx, 8
0x180005030  jb      short loc_180005023
0x180005032  jmp     loc_180004F08
0x180005037  mov     eax, [r13+0]
0x18000503b  movdqa  xmm0, xmm1
0x18000503f  imul    rcx, rax, 1Ch
0x180005043  psrldq  xmm0, 4
0x180005048  psrldq  xmm1, 8
0x18000504d  movzx   eax, word ptr [rbp+57h+var_80+4]
0x180005051  mov     [rcx+r13+8], edx
0x180005056  mov     [rcx+r13+0Ch], ax
0x18000505c  movzx   eax, word ptr [rbp+57h+var_80+6]
0x180005060  mov     [rcx+r13+0Eh], ax
0x180005066  mov     rax, [rbp+57h+var_80+8]
0x18000506a  mov     [rcx+r13+10h], rax
0x18000506f  mov     eax, [rbp+57h+var_68]
0x180005072  movd    dword ptr [rcx+r13+18h], xmm0
0x180005079  movd    dword ptr [rcx+r13+1Ch], xmm1
0x180005080  mov     [rcx+r13+20h], eax
0x180005085  inc     dword ptr [r13+0]
0x180005089  jmp     loc_180004F08
0x18000508e  mov     r9d, eax
0x180005091  lea     r8, aWerdiagFailedE_1; "WERDIAG: Failed extracting next pair fr"...
0x180005098  xor     edx, edx; Level
0x18000509a  mov     ecx, edi; ComponentId
0x18000509c  call    cs:__imp_DbgPrintEx
0x1800050a2  mov     rsi, [rbp+57h+var_80]
0x1800050a6  jmp     short loc_1800050E1
0x1800050a8  mov     r9d, eax
0x1800050ab  lea     r8, aWerdiagFailedE_0; "WERDIAG: Failed extracting next token f"...
0x1800050b2  xor     edx, edx; Level
0x1800050b4  mov     ecx, edi; ComponentId
0x1800050b6  call    cs:__imp_DbgPrintEx
0x1800050bc  jmp     short loc_1800050E1
0x1800050be  mov     eax, [rbp+57h+var_90]
0x1800050c1  test    eax, eax
0x1800050c3  jnz     short loc_1800050DD
0x1800050c5  lea     r8, aWerdiagLogFile; "WERDIAG: Log file size was not specifie"...
0x1800050cc  xor     edx, edx; Level
0x1800050ce  mov     ecx, edi; ComponentId
0x1800050d0  call    cs:__imp_DbgPrintEx
0x1800050d6  mov     ebx, 80004005h
0x1800050db  jmp     short loc_1800050E1
0x1800050dd  mov     [r13+4], eax
0x1800050e1  mov     rcx, r15; void *
0x1800050e4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800050e9  mov     rcx, r12; void *
0x1800050ec  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800050f1  mov     rcx, [rbp+57h+var_88]; void *
0x1800050f5  test    rcx, rcx
0x1800050f8  jz      short loc_1800050FF
0x1800050fa  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800050ff  test    rsi, rsi
0x180005102  jz      short loc_18000510C
0x180005104  mov     rcx, rsi; void *
0x180005107  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000510c  mov     eax, ebx
0x18000510e  jmp     short loc_180005129
0x180005110  lea     r8, aWerdiagInvalid_2; "WERDIAG: Invalid argument: settins stri"...
0x180005117  xor     edx, edx; Level
0x180005119  mov     ecx, 96h; ComponentId
0x18000511e  call    cs:__imp_DbgPrintEx
0x180005124  mov     eax, 80070057h
0x180005129  mov     rcx, [rbp+57h+var_40]
0x18000512d  xor     rcx, rsp; StackCookie
0x180005130  call    __security_check_cookie
0x180005135  mov     rbx, [rsp+0C0h+arg_10]
0x18000513d  add     rsp, 90h
0x180005144  pop     r15
0x180005146  pop     r14
0x180005148  pop     r13
0x18000514a  pop     r12
0x18000514c  pop     rdi
0x18000514d  pop     rsi
0x18000514e  pop     rbp
0x18000514f  retn
```
