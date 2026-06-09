# StrIOEncInit

- ea: `0x180001024`
- end: `0x1800012b4`
- name: `StrIOEncInit`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800012bc`

## callees

- `0x180001024`
- `0x18000fe6c`
- `0x18002ded0`
- `0x18003169c`
- `0x180032aa4`
- `0x180036420`
- `0x180037174`
- `0x18003e5d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800010a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001112`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001167`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800010a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001112`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001167`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800011cf`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1800011cf`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000119c`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000119c`

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
  if ( !(unsigned int)allocateBitIOInfo() )
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
              WS_List = CreateWS_List(*(_QWORD *)(a1 + 35656) + 8 * i);
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
0x180001071  jnz     loc_180001294
0x180001077  mov     rdx, [rbx+0C8h]
0x18000107e  mov     rcx, [rbx+8640h]
0x180001085  call    attachISWrite
0x18000108a  mov     rcx, [rbx+86B0h]
0x180001091  test    rcx, rcx
0x180001094  jz      loc_180001290
0x18000109a  shl     rcx, 3; Size
0x18000109e  mov     [rsp+278h+pullResult], rbp
0x1800010a3  call    cs:__imp_malloc
0x1800010aa  nop     dword ptr [rax+rax+00h]
0x1800010af  mov     [rbx+8B48h], rax
0x1800010b6  test    rax, rax
0x1800010b9  jz      loc_180001294
0x1800010bf  mov     r8, [rbx+86B0h]
0x1800010c6  xor     edx, edx; Val
0x1800010c8  shl     r8, 3; Size
0x1800010cc  mov     rcx, rax; void *
0x1800010cf  call    memset_0
0x1800010d4  mov     rdx, [rbx+86F0h]
0x1800010db  lea     r8, [rsp+278h+pullResult]; pullResult
0x1800010e0  imul    rdx, [rbx+0B0h]; ullMultiplier
0x1800010e8  mov     rcx, [rbx+86F8h]; ullMultiplicand
0x1800010ef  call    ULongLongMult
0x1800010f4  test    eax, eax
0x1800010f6  js      loc_180001294
0x1800010fc  cmp     [rsp+278h+pullResult], 4000000h
0x180001105  jb      short loc_180001143
0x180001107  mov     rcx, [rbx+86B0h]
0x18000110e  shl     rcx, 3; Size
0x180001112  call    cs:__imp_malloc
0x180001119  nop     dword ptr [rax+rax+00h]
0x18000111e  mov     [rbx+8C60h], rax
0x180001125  test    rax, rax
0x180001128  jz      loc_180001294
0x18000112e  mov     r8, [rbx+86B0h]
0x180001135  xor     edx, edx; Val
0x180001137  shl     r8, 3; Size
0x18000113b  mov     rcx, rax; void *
0x18000113e  call    memset_0
0x180001143  mov     rdi, rbp
0x180001146  cmp     [rbx+86B0h], rbp
0x18000114d  jbe     loc_180001290
0x180001153  cmp     [rsp+278h+pullResult], 4000000h
0x18000115c  jb      loc_180001251
0x180001162  mov     ecx, 208h; Size
0x180001167  call    cs:__imp_malloc
0x18000116e  nop     dword ptr [rax+rax+00h]
0x180001173  mov     rcx, [rbx+8C60h]
0x18000117a  mov     [rcx+rdi*8], rax
0x18000117e  mov     rax, [rbx+8C60h]
0x180001185  mov     rsi, [rax+rdi*8]
0x180001189  test    rsi, rsi
0x18000118c  jz      loc_180001294
0x180001192  lea     rdx, [rsp+278h+PathName]
0x180001197  mov     ecx, 104h
0x18000119c  call    cs:__imp_GetTempPath2W
0x1800011a3  nop     dword ptr [rax+rax+00h]
0x1800011a8  dec     eax
0x1800011aa  cmp     eax, 102h
0x1800011af  ja      loc_180001294
0x1800011b5  mov     r9, [rbx+8C60h]
0x1800011bc  lea     rdx, PrefixString; "wdp"
0x1800011c3  xor     r8d, r8d; uUnique
0x1800011c6  lea     rcx, [rsp+278h+PathName]; lpPathName
0x1800011cb  mov     r9, [r9+rdi*8]; lpTempFileName
0x1800011cf  call    cs:__imp_GetTempFileNameW
0x1800011d6  nop     dword ptr [rax+rax+00h]
0x1800011db  test    eax, eax
0x1800011dd  jz      loc_180001294
0x1800011e3  mov     r8d, ebp
0x1800011e6  mov     r9d, ebp
0x1800011e9  mov     edx, ebp
0x1800011eb  mov     rax, [rbx+8C60h]
0x1800011f2  mov     ecx, r8d
0x1800011f5  mov     rax, [rax+rdi*8]
0x1800011f9  cmp     [rax+rcx*2], bp
0x1800011fd  jz      short loc_180001235
0x1800011ff  mov     eax, r9d
0x180001202  mov     cl, [rax+rsi]
0x180001205  test    cl, cl
0x180001207  jz      short loc_180001210
0x180001209  mov     eax, edx
0x18000120b  inc     edx
0x18000120d  mov     [rax+rsi], cl
0x180001210  lea     eax, [r9+1]
0x180001214  mov     r10b, [rax+rsi]
0x180001218  test    r10b, r10b
0x18000121b  jz      short loc_180001225
0x18000121d  mov     eax, edx
0x18000121f  inc     edx
0x180001221  mov     [rax+rsi], r10b
0x180001225  inc     r8d
0x180001228  add     r9d, 2
0x18000122c  cmp     r8d, 104h
0x180001233  jb      short loc_1800011EB
0x180001235  mov     eax, r8d
0x180001238  mov     rdx, rsi
0x18000123b  mov     [rax+rsi], bpl
0x18000123f  mov     rax, [rbx+8B48h]
0x180001246  lea     rcx, [rax+rdi*8]
0x18000124a  call    CreateWS_File
0x18000124f  jmp     short loc_180001261
0x180001251  mov     rax, [rbx+8B48h]
0x180001258  lea     rcx, [rax+rdi*8]
0x18000125c  call    CreateWS_List
0x180001261  test    eax, eax
0x180001263  jnz     short loc_180001294
0x180001265  mov     rdx, [rbx+8B48h]
0x18000126c  mov     rcx, [rbx+86A8h]
0x180001273  mov     rdx, [rdx+rdi*8]
0x180001277  mov     rcx, [rcx+rdi*8]
0x18000127b  call    attachISWrite
0x180001280  inc     rdi
0x180001283  cmp     rdi, [rbx+86B0h]
0x18000128a  jb      loc_180001153
0x180001290  xor     eax, eax
0x180001292  jmp     short loc_180001297
0x180001294  or      eax, 0FFFFFFFFh
0x180001297  mov     rcx, [rsp+278h+var_38]
0x18000129f  xor     rcx, rsp; StackCookie
0x1800012a2  call    __security_check_cookie
0x1800012a7  add     rsp, 258h
0x1800012ae  pop     rdi
0x1800012af  pop     rsi
0x1800012b0  pop     rbp
0x1800012b1  pop     rbx
0x1800012b2  retn
```
