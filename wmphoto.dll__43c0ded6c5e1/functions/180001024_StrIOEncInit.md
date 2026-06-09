# StrIOEncInit

- ea: `0x180001024`
- end: `0x180001295`
- name: `StrIOEncInit`
- size: `625`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000129c`

## callees

- `0x180001024`
- `0x18000fcf0`
- `0x18002dbd0`
- `0x180031340`
- `0x180032610`
- `0x180035e50`
- `0x180036ba4`
- `0x18003de50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800010a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000110c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000115b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800010a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000110c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000115b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800011b7`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800011b7`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000118a`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000118a`

## pseudocode

```c
__int64 __fastcall StrIOEncInit(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rcx
  void *v4; // rax
  void *v5; // rax
  unsigned __int64 i; // rdi
  __int64 v7; // rsi
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // edx
  char v11; // cl
  __int64 v12; // rax
  char v13; // r10
  __int64 v14; // rax
  int WS_List; // eax
  ULONGLONG pullResult[2]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR PathName[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( *(_DWORD *)(a1 + 168) || (v2 = 0, *(_DWORD *)(a1 + 216) + *(_DWORD *)(a1 + 16604)) )
    v2 = 1;
  *(_DWORD *)(a1 + 34228) = v2;
  if ( !(unsigned int)allocateBitIOInfo(a1) )
  {
    attachISWrite(*(_QWORD *)(a1 + 34368), *(_QWORD *)(a1 + 200));
    v3 = *(_QWORD *)(a1 + 34480);
    if ( !v3 )
      return 0;
    pullResult[0] = 0;
    v4 = malloc(8 * v3);
    *(_QWORD *)(a1 + 35656) = v4;
    if ( v4 )
    {
      memset_0(v4, 0, 8LL * *(_QWORD *)(a1 + 34480));
      if ( ULongLongMult(*(_QWORD *)(a1 + 34552), *(_QWORD *)(a1 + 176) * *(_QWORD *)(a1 + 34544), pullResult) >= 0 )
      {
        if ( pullResult[0] < 0x4000000 )
          goto LABEL_11;
        v5 = malloc(8LL * *(_QWORD *)(a1 + 34480));
        *(_QWORD *)(a1 + 35936) = v5;
        if ( v5 )
        {
          memset_0(v5, 0, 8LL * *(_QWORD *)(a1 + 34480));
LABEL_11:
          for ( i = 0; i < *(_QWORD *)(a1 + 34480); ++i )
          {
            if ( pullResult[0] < 0x4000000 )
            {
              WS_List = CreateWS_List((_QWORD *)(*(_QWORD *)(a1 + 35656) + 8 * i));
            }
            else
            {
              *(_QWORD *)(*(_QWORD *)(a1 + 35936) + 8 * i) = malloc(0x208u);
              v7 = *(_QWORD *)(*(_QWORD *)(a1 + 35936) + 8 * i);
              if ( !v7
                || (unsigned int)GetTempPath2W(260, PathName) - 1 > 0x102
                || !GetTempFileNameW(PathName, L"wdp", 0, *(LPWSTR *)(*(_QWORD *)(a1 + 35936) + 8 * i)) )
              {
                return 0xFFFFFFFFLL;
              }
              v8 = 0;
              v9 = 0;
              v10 = 0;
              do
              {
                if ( !*(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 35936) + 8 * i) + 2LL * (unsigned int)v8) )
                  break;
                v11 = *(_BYTE *)((unsigned int)v9 + v7);
                if ( v11 )
                {
                  v12 = v10++;
                  *(_BYTE *)(v12 + v7) = v11;
                }
                v13 = *(_BYTE *)((unsigned int)(v9 + 1) + v7);
                if ( v13 )
                {
                  v14 = v10++;
                  *(_BYTE *)(v14 + v7) = v13;
                }
                v8 = (unsigned int)(v8 + 1);
                v9 = (unsigned int)(v9 + 2);
              }
              while ( (unsigned int)v8 < 0x104 );
              *(_BYTE *)((unsigned int)v8 + v7) = 0;
              WS_List = CreateWS_File(*(_QWORD *)(a1 + 35656) + 8 * i, v7, v8, v9);
            }
            if ( WS_List )
              return 0xFFFFFFFFLL;
            attachISWrite(*(_QWORD *)(*(_QWORD *)(a1 + 34472) + 8 * i), *(_QWORD *)(*(_QWORD *)(a1 + 35656) + 8 * i));
          }
          return 0;
        }
      }
    }
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180001024  push    rbx
0x180001026  push    rbp
0x180001027  push    rsi
0x180001028  push    rdi
0x180001029  sub     rsp, 258h
0x180001030  mov     rax, cs:__security_cookie
0x180001037  xor     rax, rsp
0x18000103a  mov     [rsp+278h+var_38], rax
0x180001042  xor     ebp, ebp
0x180001044  mov     rbx, rcx
0x180001047  cmp     [rcx+0A8h], ebp
0x18000104d  jnz     short loc_18000105F
0x18000104f  mov     eax, [rcx+40DCh]
0x180001055  add     eax, [rcx+0D8h]
0x18000105b  mov     eax, ebp
0x18000105d  jz      short loc_180001064
0x18000105f  mov     eax, 1
0x180001064  mov     [rcx+85B4h], eax
0x18000106a  call    allocateBitIOInfo
0x18000106f  test    eax, eax
0x180001071  jnz     loc_180001276
0x180001077  mov     rdx, [rbx+0C8h]
0x18000107e  mov     rcx, [rbx+8640h]
0x180001085  call    attachISWrite
0x18000108a  mov     rcx, [rbx+86B0h]
0x180001091  test    rcx, rcx
0x180001094  jz      loc_180001272
0x18000109a  shl     rcx, 3; Size
0x18000109e  mov     [rsp+278h+pullResult], rbp
0x1800010a3  call    cs:__imp_malloc
0x1800010a9  mov     [rbx+8B48h], rax
0x1800010b0  test    rax, rax
0x1800010b3  jz      loc_180001276
0x1800010b9  mov     r8, [rbx+86B0h]
0x1800010c0  xor     edx, edx; Val
0x1800010c2  shl     r8, 3; Size
0x1800010c6  mov     rcx, rax; void *
0x1800010c9  call    memset_0
0x1800010ce  mov     rdx, [rbx+86F0h]
0x1800010d5  lea     r8, [rsp+278h+pullResult]; pullResult
0x1800010da  imul    rdx, [rbx+0B0h]; ullMultiplier
0x1800010e2  mov     rcx, [rbx+86F8h]; ullMultiplicand
0x1800010e9  call    ULongLongMult
0x1800010ee  test    eax, eax
0x1800010f0  js      loc_180001276
0x1800010f6  cmp     [rsp+278h+pullResult], 4000000h
0x1800010ff  jb      short loc_180001137
0x180001101  mov     rcx, [rbx+86B0h]
0x180001108  shl     rcx, 3; Size
0x18000110c  call    cs:__imp_malloc
0x180001112  mov     [rbx+8C60h], rax
0x180001119  test    rax, rax
0x18000111c  jz      loc_180001276
0x180001122  mov     r8, [rbx+86B0h]
0x180001129  xor     edx, edx; Val
0x18000112b  shl     r8, 3; Size
0x18000112f  mov     rcx, rax; void *
0x180001132  call    memset_0
0x180001137  mov     rdi, rbp
0x18000113a  cmp     [rbx+86B0h], rbp
0x180001141  jbe     loc_180001272
0x180001147  cmp     [rsp+278h+pullResult], 4000000h
0x180001150  jb      loc_180001233
0x180001156  mov     ecx, 208h; Size
0x18000115b  call    cs:__imp_malloc
0x180001161  mov     rcx, [rbx+8C60h]
0x180001168  mov     [rcx+rdi*8], rax
0x18000116c  mov     rax, [rbx+8C60h]
0x180001173  mov     rsi, [rax+rdi*8]
0x180001177  test    rsi, rsi
0x18000117a  jz      loc_180001276
0x180001180  lea     rdx, [rsp+278h+PathName]
0x180001185  mov     ecx, 104h
0x18000118a  call    cs:__imp_GetTempPath2W
0x180001190  dec     eax
0x180001192  cmp     eax, 102h
0x180001197  ja      loc_180001276
0x18000119d  mov     r9, [rbx+8C60h]
0x1800011a4  lea     rdx, PrefixString; "wdp"
0x1800011ab  xor     r8d, r8d; uUnique
0x1800011ae  lea     rcx, [rsp+278h+PathName]; lpPathName
0x1800011b3  mov     r9, [r9+rdi*8]; lpTempFileName
0x1800011b7  call    cs:__imp_GetTempFileNameW
0x1800011bd  test    eax, eax
0x1800011bf  jz      loc_180001276
0x1800011c5  mov     r8d, ebp
0x1800011c8  mov     r9d, ebp
0x1800011cb  mov     edx, ebp
0x1800011cd  mov     rax, [rbx+8C60h]
0x1800011d4  mov     ecx, r8d
0x1800011d7  mov     rax, [rax+rdi*8]
0x1800011db  cmp     [rax+rcx*2], bp
0x1800011df  jz      short loc_180001217
0x1800011e1  mov     eax, r9d
0x1800011e4  mov     cl, [rax+rsi]
0x1800011e7  test    cl, cl
0x1800011e9  jz      short loc_1800011F2
0x1800011eb  mov     eax, edx
0x1800011ed  inc     edx
0x1800011ef  mov     [rax+rsi], cl
0x1800011f2  lea     eax, [r9+1]
0x1800011f6  mov     r10b, [rax+rsi]
0x1800011fa  test    r10b, r10b
0x1800011fd  jz      short loc_180001207
0x1800011ff  mov     eax, edx
0x180001201  inc     edx
0x180001203  mov     [rax+rsi], r10b
0x180001207  inc     r8d
0x18000120a  add     r9d, 2
0x18000120e  cmp     r8d, 104h
0x180001215  jb      short loc_1800011CD
0x180001217  mov     eax, r8d
0x18000121a  mov     rdx, rsi
0x18000121d  mov     [rax+rsi], bpl
0x180001221  mov     rax, [rbx+8B48h]
0x180001228  lea     rcx, [rax+rdi*8]
0x18000122c  call    CreateWS_File
0x180001231  jmp     short loc_180001243
0x180001233  mov     rax, [rbx+8B48h]
0x18000123a  lea     rcx, [rax+rdi*8]
0x18000123e  call    CreateWS_List
0x180001243  test    eax, eax
0x180001245  jnz     short loc_180001276
0x180001247  mov     rdx, [rbx+8B48h]
0x18000124e  mov     rcx, [rbx+86A8h]
0x180001255  mov     rdx, [rdx+rdi*8]
0x180001259  mov     rcx, [rcx+rdi*8]
0x18000125d  call    attachISWrite
0x180001262  inc     rdi
0x180001265  cmp     rdi, [rbx+86B0h]
0x18000126c  jb      loc_180001147
0x180001272  xor     eax, eax
0x180001274  jmp     short loc_180001279
0x180001276  or      eax, 0FFFFFFFFh
0x180001279  mov     rcx, [rsp+278h+var_38]
0x180001281  xor     rcx, rsp; StackCookie
0x180001284  call    __security_check_cookie
0x180001289  add     rsp, 258h
0x180001290  pop     rdi
0x180001291  pop     rsi
0x180001292  pop     rbp
0x180001293  pop     rbx
0x180001294  retn
```
