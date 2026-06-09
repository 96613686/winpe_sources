# PrintRawJob(_PRINTPROCESSORDATA *,ushort *,uint)

- ea: `0x180001590`
- end: `0x1800017be`
- name: `?PrintRawJob@@YAHPEAU_PRINTPROCESSORDATA@@PEAGI@Z`
- size: `558`
- prototype: `__int64 __fastcall(struct _PRINTPROCESSORDATA *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061f0`

## callees

- `0x180001590`
- `0x180005610`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180001637`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180001637`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000166f`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000166f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001773`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180001773`
- `WINSPOOL!ClosePrinter` at `0x18000171a`
- `WINSPOOL!ClosePrinter` at `0x18000171a`
- `WINSPOOL!EndDocPrinter` at `0x18000167e`
- `WINSPOOL!EndDocPrinter` at `0x18000167e`
- `WINSPOOL!StartDocPrinterW` at `0x1800015f0`
- `WINSPOOL!StartDocPrinterW` at `0x1800015f0`
- `WINSPOOL!OpenPrinterW` at `0x180001662`
- `WINSPOOL!OpenPrinterW` at `0x180001662`
- `WINSPOOL!WritePrinter` at `0x1800016e9`
- `WINSPOOL!WritePrinter` at `0x1800017b3`
- `WINSPOOL!WritePrinter` at `0x1800016e9`
- `WINSPOOL!WritePrinter` at `0x1800017b3`
- `WINSPOOL!ReadPrinter` at `0x1800016b6`
- `WINSPOOL!ReadPrinter` at `0x180001700`
- `WINSPOOL!ReadPrinter` at `0x1800016b6`
- `WINSPOOL!ReadPrinter` at `0x180001700`

## pseudocode

```c
__int64 __fastcall PrintRawJob(struct _PRINTPROCESSORDATA *a1, unsigned __int16 *a2, int a3)
{
  __int64 v5; // rax
  unsigned int v6; // r12d
  void *v7; // rcx
  int v8; // r14d
  int v9; // r13d
  unsigned __int8 *v10; // rdi
  int v11; // r15d
  DWORD v13; // r8d
  DWORD v14; // esi
  unsigned __int8 *i; // r14
  HANDLE phPrinter; // [rsp+20h] [rbp-60h] BYREF
  BYTE pDocInfo[8]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v18; // [rsp+30h] [rbp-50h]
  __int64 v19; // [rsp+38h] [rbp-48h]
  __int128 v20; // [rsp+40h] [rbp-40h] BYREF
  __int128 v21; // [rsp+50h] [rbp-30h]
  __int64 v22; // [rsp+60h] [rbp-20h]
  DWORD pNoBytesRead; // [rsp+B0h] [rbp+30h] BYREF
  LPWSTR pPrinterName; // [rsp+B8h] [rbp+38h]
  DWORD pcWritten; // [rsp+C8h] [rbp+48h] BYREF

  pPrinterName = a2;
  v22 = 0;
  *(_QWORD *)pDocInfo = *((_QWORD *)a1 + 7);
  v18 = *((_QWORD *)a1 + 8);
  v5 = *((_QWORD *)a1 + 9);
  v6 = 0;
  v7 = (void *)*((_QWORD *)a1 + 5);
  v19 = v5;
  pNoBytesRead = 0;
  pcWritten = 0;
  phPrinter = 0;
  v20 = 0;
  v21 = 0;
  if ( StartDocPrinterW(v7, 1u, pDocInfo) )
  {
    if ( (unsigned int)(a3 - 1) > 1 )
    {
      a3 = v22;
      v9 = 0;
      v8 = HIDWORD(v21);
    }
    else
    {
      LODWORD(v20) = 0;
      v8 = 0;
      *((_QWORD *)&v20 + 1) = 0;
      v9 = 1;
      HIDWORD(v21) = 0;
      LODWORD(v22) = a3;
    }
    v10 = (unsigned __int8 *)LocalAlloc(0x40u, 0x40000u);
    if ( v10 )
    {
      v11 = *((_DWORD *)a1 + 23);
      while ( v11 )
      {
        if ( !OpenPrinterW(pPrinterName, &phPrinter, 0) )
          goto LABEL_8;
        --v11;
        if ( ReadPrinter(phPrinter, v10, 0x40000u, &pNoBytesRead) )
        {
          do
          {
            v13 = pNoBytesRead;
            if ( !pNoBytesRead )
              break;
            if ( v9 )
            {
              v14 = 0;
              for ( i = v10; v14 < pNoBytesRead; ++v14 )
              {
                CheckFormFeedStream((struct dci *)&v20, *i);
                v13 = pNoBytesRead;
                ++i;
              }
            }
            if ( (*((_BYTE *)a1 + 16) & 8) != 0 )
            {
              WaitForSingleObject(*((HANDLE *)a1 + 3), 0xFFFFFFFF);
              v13 = pNoBytesRead;
            }
            if ( (*((_BYTE *)a1 + 16) & 1) != 0 )
              break;
            WritePrinter(*((HANDLE *)a1 + 5), v10, v13, &pcWritten);
          }
          while ( ReadPrinter(phPrinter, v10, 0x40000u, &pNoBytesRead) );
          a3 = v22;
          v8 = HIDWORD(v21);
        }
        if ( v9 && (unsigned int)(v8 - 2) > 1 && (a3 == 1 || a3 == 2 && !v8) )
          WritePrinter(*((HANDLE *)a1 + 5), &abyFF, 1u, &pcWritten);
        ClosePrinter(phPrinter);
      }
      v6 = 1;
LABEL_8:
      LocalFree(v10);
    }
    EndDocPrinter(*((HANDLE *)a1 + 5));
  }
  return v6;
}

```

## disassembly

```asm
0x180001590  mov     [rsp-28h+pPrinterName], rdx
0x180001595  push    rbp
0x180001596  push    rbx
0x180001597  push    rsi
0x180001598  push    rdi
0x180001599  push    r12
0x18000159b  mov     rbp, rsp
0x18000159e  sub     rsp, 80h
0x1800015a5  xor     eax, eax
0x1800015a7  xor     edi, edi
0x1800015a9  mov     [rbp+var_20], rax
0x1800015ad  xorps   xmm0, xmm0
0x1800015b0  mov     rax, [rcx+38h]
0x1800015b4  mov     esi, r8d
0x1800015b7  mov     qword ptr [rbp+pDocInfo], rax
0x1800015bb  lea     r8, [rbp+pDocInfo]; pDocInfo
0x1800015bf  mov     rax, [rcx+40h]
0x1800015c3  mov     rbx, rcx
0x1800015c6  mov     [rbp+var_50], rax
0x1800015ca  mov     edx, 1; Level
0x1800015cf  mov     rax, [rcx+48h]
0x1800015d3  mov     r12d, edi
0x1800015d6  mov     rcx, [rcx+28h]; hPrinter
0x1800015da  mov     [rbp+var_48], rax
0x1800015de  mov     [rbp+pNoBytesRead], edi
0x1800015e1  mov     [rbp+pcWritten], edi
0x1800015e4  mov     [rbp+phPrinter], rdi
0x1800015e8  movups  [rbp+var_40], xmm0
0x1800015ec  movups  [rbp+var_30], xmm0
0x1800015f0  call    cs:__imp_StartDocPrinterW
0x1800015f6  test    eax, eax
0x1800015f8  jz      loc_180001691
0x1800015fe  lea     eax, [rsi-1]
0x180001601  mov     [rsp+80h+arg_10], r13
0x180001609  mov     [rsp+80h+var_8], r14
0x18000160e  cmp     eax, 1
0x180001611  ja      loc_180001730
0x180001617  mov     dword ptr [rbp+var_40], edi
0x18000161a  mov     r14d, edi
0x18000161d  mov     qword ptr [rbp+var_40+8], rdi
0x180001621  mov     r13d, 1
0x180001627  mov     dword ptr [rbp+var_30+0Ch], edi
0x18000162a  mov     dword ptr [rbp+var_20], esi
0x18000162d  mov     edx, 40000h; uBytes
0x180001632  mov     ecx, 40h ; '@'; uFlags
0x180001637  call    cs:__imp_LocalAlloc
0x18000163d  mov     rdi, rax
0x180001640  test    rax, rax
0x180001643  jz      short loc_18000167A
0x180001645  mov     [rsp+80h+var_10], r15
0x18000164a  mov     r15d, [rbx+5Ch]
0x18000164e  test    r15d, r15d
0x180001651  jz      loc_180001725
0x180001657  mov     rcx, [rbp+pPrinterName]; pPrinterName
0x18000165b  lea     rdx, [rbp+phPrinter]; phPrinter
0x18000165f  xor     r8d, r8d; pDefault
0x180001662  call    cs:__imp_OpenPrinterW
0x180001668  test    eax, eax
0x18000166a  jnz     short loc_1800016A2
0x18000166c  mov     rcx, rdi; hMem
0x18000166f  call    cs:__imp_LocalFree
0x180001675  mov     r15, [rsp+80h+var_10]
0x18000167a  mov     rcx, [rbx+28h]; hPrinter
0x18000167e  call    cs:__imp_EndDocPrinter
0x180001684  mov     r14, [rsp+80h+var_8]
0x180001689  mov     r13, [rsp+80h+arg_10]
0x180001691  mov     eax, r12d
0x180001694  add     rsp, 80h
0x18000169b  pop     r12
0x18000169d  pop     rdi
0x18000169e  pop     rsi
0x18000169f  pop     rbx
0x1800016a0  pop     rbp
0x1800016a1  retn
0x1800016a2  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800016a6  lea     r9, [rbp+pNoBytesRead]; pNoBytesRead
0x1800016aa  mov     r8d, 40000h; cbBuf
0x1800016b0  mov     rdx, rdi; pBuf
0x1800016b3  dec     r15d
0x1800016b6  call    cs:__imp_ReadPrinter
0x1800016bc  test    eax, eax
0x1800016be  jz      short loc_180001711
0x1800016c0  mov     r8d, [rbp+pNoBytesRead]; cbBuf
0x1800016c4  test    r8d, r8d
0x1800016c7  jz      short loc_18000170A
0x1800016c9  test    r13d, r13d
0x1800016cc  jnz     short loc_18000173F
0x1800016ce  test    byte ptr [rbx+10h], 8
0x1800016d2  jnz     loc_18000176A
0x1800016d8  test    byte ptr [rbx+10h], 1
0x1800016dc  jnz     short loc_18000170A
0x1800016de  mov     rcx, [rbx+28h]; hPrinter
0x1800016e2  lea     r9, [rbp+pcWritten]; pcWritten
0x1800016e6  mov     rdx, rdi; pBuf
0x1800016e9  call    cs:__imp_WritePrinter
0x1800016ef  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800016f3  lea     r9, [rbp+pNoBytesRead]; pNoBytesRead
0x1800016f7  mov     r8d, 40000h; cbBuf
0x1800016fd  mov     rdx, rdi; pBuf
0x180001700  call    cs:__imp_ReadPrinter
0x180001706  test    eax, eax
0x180001708  jnz     short loc_1800016C0
0x18000170a  mov     esi, dword ptr [rbp+var_20]
0x18000170d  mov     r14d, dword ptr [rbp+var_30+0Ch]
0x180001711  test    r13d, r13d
0x180001714  jnz     short loc_180001782
0x180001716  mov     rcx, [rbp+phPrinter]; hPrinter
0x18000171a  call    cs:__imp_ClosePrinter
0x180001720  jmp     loc_18000164E
0x180001725  mov     r12d, 1
0x18000172b  jmp     loc_18000166C
0x180001730  mov     esi, dword ptr [rbp+var_20]
0x180001733  mov     r13d, edi
0x180001736  mov     r14d, dword ptr [rbp+var_30+0Ch]
0x18000173a  jmp     loc_18000162D
0x18000173f  xor     esi, esi
0x180001741  mov     r14, rdi
0x180001744  test    r8d, r8d
0x180001747  jz      short loc_1800016CE
0x180001749  movzx   edx, byte ptr [r14]; unsigned __int8
0x18000174d  lea     rcx, [rbp+var_40]; struct dci *
0x180001751  call    ?CheckFormFeedStream@@YAXPEAUdci@@E@Z; CheckFormFeedStream(dci *,uchar)
0x180001756  mov     r8d, [rbp+pNoBytesRead]
0x18000175a  lea     r14, [r14+1]
0x18000175e  inc     esi
0x180001760  cmp     esi, r8d
0x180001763  jb      short loc_180001749
0x180001765  jmp     loc_1800016CE
0x18000176a  mov     rcx, [rbx+18h]; hHandle
0x18000176e  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180001773  call    cs:__imp_WaitForSingleObject
0x180001779  mov     r8d, [rbp+pNoBytesRead]
0x18000177d  jmp     loc_1800016D8
0x180001782  lea     eax, [r14-2]
0x180001786  cmp     eax, 1
0x180001789  jbe     short loc_180001716
0x18000178b  cmp     esi, 1
0x18000178e  jz      short loc_18000179E
0x180001790  cmp     esi, 2
0x180001793  jnz     short loc_180001716
0x180001795  test    r14d, r14d
0x180001798  jnz     loc_180001716
0x18000179e  mov     rcx, [rbx+28h]; hPrinter
0x1800017a2  lea     r9, [rbp+pcWritten]; pcWritten
0x1800017a6  mov     r8d, 1; cbBuf
0x1800017ac  lea     rdx, ?abyFF@@3PAEA; pBuf
0x1800017b3  call    cs:__imp_WritePrinter
0x1800017b9  jmp     loc_180001716
```
