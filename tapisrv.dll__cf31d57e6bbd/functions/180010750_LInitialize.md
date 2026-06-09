# LInitialize

- ea: `0x180010750`
- end: `0x180010c26`
- name: `LInitialize`
- size: `1238`
- prototype: `__int64 __fastcall(unsigned __int64, _DWORD *, unsigned int, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x180001f50`
- `0x18000443c`
- `0x1800072e4`
- `0x180010750`
- `0x18001c7c0`
- `0x18001c854`
- `0x18001f494`
- `0x18002b25c`
- `0x18002c8d4`
- `0x18002c8fc`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e2f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x180010919`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x180010919`
- `KERNEL32!HeapAlloc` at `0x180010816`
- `KERNEL32!HeapAlloc` at `0x180010816`
- `KERNEL32!GetCurrentThreadId` at `0x180010a2f`
- `KERNEL32!GetCurrentThreadId` at `0x180010aae`
- `KERNEL32!GetCurrentThreadId` at `0x180010bb0`
- `KERNEL32!GetCurrentThreadId` at `0x180010a2f`
- `KERNEL32!GetCurrentThreadId` at `0x180010aae`
- `KERNEL32!GetCurrentThreadId` at `0x180010bb0`
- `KERNEL32!LeaveCriticalSection` at `0x1800109fb`
- `KERNEL32!LeaveCriticalSection` at `0x180010ad0`
- `KERNEL32!LeaveCriticalSection` at `0x180010b2a`
- `KERNEL32!LeaveCriticalSection` at `0x180010bd2`
- `KERNEL32!LeaveCriticalSection` at `0x1800109fb`
- `KERNEL32!LeaveCriticalSection` at `0x180010ad0`
- `KERNEL32!LeaveCriticalSection` at `0x180010b2a`
- `KERNEL32!LeaveCriticalSection` at `0x180010bd2`
- `KERNEL32!lstrlenW` at `0x1800107ac`
- `KERNEL32!lstrlenW` at `0x1800107bb`
- `KERNEL32!lstrlenW` at `0x1800107ac`
- `KERNEL32!lstrlenW` at `0x1800107bb`
- `KERNEL32!EnterCriticalSection` at `0x180010a1f`
- `KERNEL32!EnterCriticalSection` at `0x180010a1f`

## pseudocode

```c
__int64 __fastcall LInitialize(unsigned __int64 a1, _DWORD *a2, unsigned int a3, __int64 a4, _DWORD *a5)
{
  __int64 result; // rax
  int v10; // r15d
  unsigned int v11; // eax
  unsigned __int64 v12; // rbp
  __int64 v13; // r15
  _DWORD *v14; // rax
  _DWORD *v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  _WORD *v18; // rax
  __int64 v19; // r14
  __int64 v20; // rcx
  __int64 v21; // rax
  unsigned __int64 v22; // rax
  size_t v23; // rdx
  int v24; // eax
  int v25; // eax
  size_t v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // r8d
  int v31; // r8d
  int v32; // r8d
  size_t v33; // rdx
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF

  LODWORD(dwBytes) = 0;
  result = IsBadStringParam(a3, a4, a2[5]);
  if ( !(_DWORD)result )
  {
    result = IsBadStringParam(a3, a4, a2[7]);
    if ( !(_DWORD)result )
    {
      v10 = lstrlenW((LPCWSTR)(a4 + (unsigned int)a2[5]));
      v11 = lstrlenW((LPCWSTR)(a4 + (unsigned int)a2[7])) + 2;
      if ( v11 < 2
        || (v12 = 2LL * v11, v12 > 0xFFFFFFFF)
        || (v13 = (unsigned int)(2 * v10 + 2), (int)DWordAdd3(216, (unsigned int)v13, (unsigned int)v12, &dwBytes) < 0)
        || (v14 = HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)dwBytes), (v15 = v14) == 0) )
      {
        *a2 = -2147483580;
        return TRACELogPrint(524290, "lineInitialize: exit, result=x%x", *a2);
      }
      TRACELogPrint(262146, "LInitialize: calling NewObject ptLineApp %p, pParams->InitContext %lx", v14, a2[4]);
      v17 = NewObject(v16, v15, 0);
      v15[6] = v17;
      if ( !v17 )
      {
        *a2 = -2147483580;
        ServerFree(v15);
        return TRACELogPrint(524290, "lineInitialize: exit, result=x%x", *a2);
      }
      TRACELogPrint(262146, "LInitialize: NewObject returned hLineApp %lx", v17);
      *v15 = 1347436876;
      *((_QWORD *)v15 + 1) = a1;
      TRACELogPrint(262146, "LInitialize: initializing ptLineApp->InitContext with %lx", a2[4]);
      v15[7] = a2[4];
      v15[12] = a2[8];
      TRACELogPrint(262146, "LInitialize: initialized ptLineApp->dwAPIVersion with %lx", a2[8]);
      v15[16] = v13;
      *((_QWORD *)v15 + 9) = v15 + 54;
      StringCbCopyW((STRSAFE_LPWSTR)v15 + 108, (unsigned int)v13, (STRSAFE_LPCWSTR)(a4 + (unsigned int)a2[5]));
      v15[51] = v12;
      v18 = (_WORD *)((char *)v15 + v13 + 216);
      *((_QWORD *)v15 + 26) = v18;
      *v18 = 34;
      StringCbCopyW(
        (STRSAFE_LPWSTR)(*((_QWORD *)v15 + 26) + 2LL),
        (unsigned int)v12 - 2LL,
        (STRSAFE_LPCWSTR)(a4 + (unsigned int)a2[7]));
      _o__wcsupr(*((_QWORD *)v15 + 26) + 2LL);
      v19 = *(_QWORD *)(a1 + 168);
      if ( !WaitForExclusiveClientAccess(a1) )
      {
        *a2 = -2147483576;
LABEL_39:
        DereferenceObject(v20, v15[6], 1);
        return TRACELogPrint(524290, "lineInitialize: exit, result=x%x", *a2);
      }
      if ( v15[12] > 0x30000u )
      {
        *((_OWORD *)v15 + 5) = *(_OWORD *)(a1 + 252);
        *((_OWORD *)v15 + 6) = *(_OWORD *)(a1 + 268);
        *((_OWORD *)v15 + 7) = *(_OWORD *)(a1 + 284);
        *((_OWORD *)v15 + 8) = *(_OWORD *)(a1 + 300);
        *((_OWORD *)v15 + 9) = *(_OWORD *)(a1 + 316);
        *((_OWORD *)v15 + 10) = *(_OWORD *)(a1 + 332);
        *((_OWORD *)v15 + 11) = *(_OWORD *)(a1 + 348);
        *(_OWORD *)(v15 + 47) = *(_OWORD *)(a1 + 360);
      }
      else
      {
        memset_0(v15 + 20, 255, 0x7Cu);
      }
      v21 = *(_QWORD *)(a1 + 168);
      *((_QWORD *)v15 + 5) = v21;
      if ( v21 )
        *(_QWORD *)(v21 + 32) = v15;
      v22 = (a1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits;
      *(_QWORD *)(a1 + 168) = v15;
      LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + v22);
      if ( (dword_180051900 & 1) != 0 )
      {
        *a2 = -2147483566;
        goto LABEL_27;
      }
      EnterCriticalSection(&CriticalSection);
      dword_1800519E0 = 23374;
      dword_1800519E4 = GetCurrentThreadId();
      StringCbCopyA(pszDest, v23, "i\\server\\line.c");
      if ( !dword_180051918 && !dword_180051928 && !gbServerInited )
      {
        v24 = ServerInit(0);
        *a2 = v24;
        if ( v24 )
        {
          dword_1800519F8 = 23383;
LABEL_26:
          dword_1800519FC = GetCurrentThreadId();
          StringCbCopyA(byte_1800519E8, v26, "i\\server\\line.c");
          LeaveCriticalSection(&CriticalSection);
LABEL_27:
          if ( WaitForExclusiveClientAccess(a1) )
          {
            v27 = *((_QWORD *)v15 + 5);
            if ( v27 )
              *(_QWORD *)(v27 + 32) = *((_QWORD *)v15 + 4);
            v28 = *((_QWORD *)v15 + 4);
            v29 = *((_QWORD *)v15 + 5);
            if ( v28 )
              *(_QWORD *)(v28 + 40) = v29;
            else
              *(_QWORD *)(a1 + 168) = v29;
            LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a1 >> 4)
                                                                 & (unsigned int)gdwPointerToLockTableIndexBits));
          }
          goto LABEL_39;
        }
        gbServerInited = 1;
      }
      if ( v19 || (v25 = InitializeClient(a1), (*a2 = v25) == 0) )
      {
        v30 = v15[6];
        a2[2] = v30;
        TRACELogPrint(262146, "LInitialize: returning pParams->hLineApp %u", v30);
        v31 = dword_18005191C;
        a2[6] = dword_18005191C;
        TRACELogPrint(262146, "LInitialize: returning pParams->dwNumDevs %u", v31);
        if ( (dword_180051900 & 2) != 0 && (*(_BYTE *)(a1 + 216) & 1) == 0 )
        {
          v32 = *(_DWORD *)(a1 + 96);
          a2[6] = v32;
          TRACELogPrint(524290, "LInitialize: returning pParams->dwNumDevs %u (again)", v32);
        }
        ++dword_180051918;
        *a5 = 36;
        dword_1800519F8 = 23434;
        dword_1800519FC = GetCurrentThreadId();
        StringCbCopyA(byte_1800519E8, v33, "i\\server\\line.c");
        LeaveCriticalSection(&CriticalSection);
        return TRACELogPrint(524290, "lineInitialize: exit, result=x%x", *a2);
      }
      dword_1800519F8 = 23394;
      goto LABEL_26;
    }
  }
  *a2 = -2147483576;
  return result;
}

```

## disassembly

```asm
0x180010750  mov     [rsp+arg_0], rbx
0x180010755  mov     [rsp+arg_10], rbp
0x18001075a  push    rsi
0x18001075b  push    rdi
0x18001075c  push    r13
0x18001075e  push    r14
0x180010760  push    r15
0x180010762  sub     rsp, 20h
0x180010766  mov     ebx, r8d
0x180010769  mov     dword ptr [rsp+48h+dwBytes], 0
0x180010771  mov     r8d, [rdx+14h]
0x180010775  mov     rdi, rdx
0x180010778  mov     rsi, rcx
0x18001077b  mov     rdx, r9
0x18001077e  mov     ecx, ebx
0x180010780  mov     r14, r9
0x180010783  call    IsBadStringParam
0x180010788  test    eax, eax
0x18001078a  jnz     loc_180010C09
0x180010790  mov     r8d, [rdi+1Ch]
0x180010794  mov     rdx, r14
0x180010797  mov     ecx, ebx
0x180010799  call    IsBadStringParam
0x18001079e  test    eax, eax
0x1800107a0  jnz     loc_180010C09
0x1800107a6  mov     ecx, [rdi+14h]
0x1800107a9  add     rcx, r14; lpString
0x1800107ac  call    cs:__imp_lstrlenW
0x1800107b2  mov     ecx, [rdi+1Ch]
0x1800107b5  mov     r15d, eax
0x1800107b8  add     rcx, r14; lpString
0x1800107bb  call    cs:__imp_lstrlenW
0x1800107c1  add     eax, 2
0x1800107c4  cmp     eax, 2
0x1800107c7  jb      loc_180010BED
0x1800107cd  mov     ebp, eax
0x1800107cf  mov     eax, 0FFFFFFFFh
0x1800107d4  add     rbp, rbp
0x1800107d7  cmp     rbp, rax
0x1800107da  ja      loc_180010BED
0x1800107e0  lea     r15d, ds:2[r15*2]
0x1800107e8  mov     r8d, ebp
0x1800107eb  mov     edx, r15d
0x1800107ee  lea     r9, [rsp+48h+dwBytes]
0x1800107f3  mov     ecx, 0D8h
0x1800107f8  call    DWordAdd3
0x1800107fd  test    eax, eax
0x1800107ff  js      loc_180010BED
0x180010805  mov     r8d, dword ptr [rsp+48h+dwBytes]; dwBytes
0x18001080a  mov     edx, 8; dwFlags
0x18001080f  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180010816  call    cs:__imp_HeapAlloc
0x18001081c  mov     rbx, rax
0x18001081f  test    rax, rax
0x180010822  jz      loc_180010BED
0x180010828  mov     r9d, [rdi+10h]
0x18001082c  lea     rdx, aLinitializeCal; "LInitialize: calling NewObject ptLineAp"...
0x180010833  mov     r13d, 40002h
0x180010839  mov     r8, rax
0x18001083c  mov     ecx, r13d
0x18001083f  call    TRACELogPrint
0x180010844  xor     r8d, r8d
0x180010847  mov     rdx, rbx
0x18001084a  call    NewObject
0x18001084f  mov     [rbx+18h], eax
0x180010852  test    eax, eax
0x180010854  jnz     short loc_180010869
0x180010856  mov     rcx, rbx; lpMem
0x180010859  mov     dword ptr [rdi], 80000044h
0x18001085f  call    ServerFree
0x180010864  jmp     loc_180010BF3
0x180010869  mov     r8d, eax
0x18001086c  lea     rdx, aLinitializeNew; "LInitialize: NewObject returned hLineAp"...
0x180010873  mov     ecx, r13d
0x180010876  call    TRACELogPrint
0x18001087b  mov     dword ptr [rbx], 5050414Ch
0x180010881  lea     rdx, aLinitializeIni_0; "LInitialize: initializing ptLineApp->In"...
0x180010888  mov     [rbx+8], rsi
0x18001088c  mov     ecx, r13d
0x18001088f  mov     r8d, [rdi+10h]
0x180010893  call    TRACELogPrint
0x180010898  mov     eax, [rdi+10h]
0x18001089b  lea     rdx, aLinitializeIni; "LInitialize: initialized ptLineApp->dwA"...
0x1800108a2  mov     [rbx+1Ch], eax
0x1800108a5  mov     ecx, r13d
0x1800108a8  mov     eax, [rdi+20h]
0x1800108ab  mov     [rbx+30h], eax
0x1800108ae  mov     r8d, [rdi+20h]
0x1800108b2  call    TRACELogPrint
0x1800108b7  lea     rcx, [rbx+0D8h]; pszDest
0x1800108be  mov     [rbx+40h], r15d
0x1800108c2  mov     [rbx+48h], rcx
0x1800108c6  mov     r8d, [rdi+14h]
0x1800108ca  add     r8, r14; pszSrc
0x1800108cd  mov     edx, r15d; cbDest
0x1800108d0  call    StringCbCopyW
0x1800108d5  mov     [rbx+0CCh], ebp
0x1800108db  lea     rax, [r15+0D8h]
0x1800108e2  add     rax, rbx
0x1800108e5  mov     edx, ebp
0x1800108e7  mov     [rbx+0D0h], rax
0x1800108ee  sub     rdx, 2; cbDest
0x1800108f2  mov     word ptr [rax], 22h ; '"'
0x1800108f7  mov     r8d, [rdi+1Ch]
0x1800108fb  mov     rcx, [rbx+0D0h]
0x180010902  add     r8, r14; pszSrc
0x180010905  add     rcx, 2; pszDest
0x180010909  call    StringCbCopyW
0x18001090e  mov     rcx, [rbx+0D0h]
0x180010915  add     rcx, 2
0x180010919  call    cs:__imp__o__wcsupr
0x18001091f  mov     r14, [rsi+0A8h]
0x180010926  mov     rcx, rsi
0x180010929  call    WaitForExclusiveClientAccess
0x18001092e  mov     r15d, 1
0x180010934  test    rax, rax
0x180010937  jz      loc_180010BDA
0x18001093d  cmp     dword ptr [rbx+30h], 30000h
0x180010944  ja      short loc_18001095A
0x180010946  mov     edx, 0FFh; Val
0x18001094b  lea     r8d, [r15+7Bh]; Size
0x18001094f  lea     rcx, [rbx+50h]; void *
0x180010953  call    memset_0
0x180010958  jmp     short loc_1800109C1
0x18001095a  movups  xmm0, xmmword ptr [rsi+0FCh]
0x180010961  movups  xmmword ptr [rbx+50h], xmm0
0x180010965  movups  xmm1, xmmword ptr [rsi+10Ch]
0x18001096c  movups  xmmword ptr [rbx+60h], xmm1
0x180010970  movups  xmm0, xmmword ptr [rsi+11Ch]
0x180010977  movups  xmmword ptr [rbx+70h], xmm0
0x18001097b  movups  xmm1, xmmword ptr [rsi+12Ch]
0x180010982  movups  xmmword ptr [rbx+80h], xmm1
0x180010989  movups  xmm0, xmmword ptr [rsi+13Ch]
0x180010990  movups  xmmword ptr [rbx+90h], xmm0
0x180010997  movups  xmm1, xmmword ptr [rsi+14Ch]
0x18001099e  movups  xmmword ptr [rbx+0A0h], xmm1
0x1800109a5  movups  xmm0, xmmword ptr [rsi+15Ch]
0x1800109ac  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800109b3  movups  xmm1, xmmword ptr [rsi+168h]
0x1800109ba  movups  xmmword ptr [rbx+0BCh], xmm1
0x1800109c1  mov     rax, [rsi+0A8h]
0x1800109c8  mov     [rbx+28h], rax
0x1800109cc  test    rax, rax
0x1800109cf  jz      short loc_1800109D5
0x1800109d1  mov     [rax+20h], rbx
0x1800109d5  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800109db  mov     rbp, rsi
0x1800109de  shr     rbp, 4
0x1800109e2  and     rax, rbp
0x1800109e5  mov     [rsi+0A8h], rbx
0x1800109ec  lea     rcx, [rax+rax*4]
0x1800109f0  mov     rax, cs:gLockTable
0x1800109f7  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800109fb  call    cs:__imp_LeaveCriticalSection
0x180010a01  test    byte ptr cs:dword_180051900, r15b
0x180010a08  jz      short loc_180010A15
0x180010a0a  mov     dword ptr [rdi], 80000052h
0x180010a10  jmp     loc_180010AD6
0x180010a15  lea     r13, CriticalSection
0x180010a1c  mov     rcx, r13; lpCriticalSection
0x180010a1f  call    cs:__imp_EnterCriticalSection
0x180010a25  mov     cs:dword_1800519E0, 5B4Eh
0x180010a2f  call    cs:__imp_GetCurrentThreadId
0x180010a35  lea     r8, aPrintscanTapiS_4+0Dh; pszSrc
0x180010a3c  mov     cs:dword_1800519E4, eax
0x180010a42  lea     rcx, pszDest; pszDest
0x180010a49  call    StringCbCopyA
0x180010a4e  cmp     cs:dword_180051918, 0
0x180010a55  jnz     short loc_180010A89
0x180010a57  cmp     cs:dword_180051928, 0
0x180010a5e  jnz     short loc_180010A89
0x180010a60  cmp     cs:gbServerInited, 0
0x180010a67  jnz     short loc_180010A89
0x180010a69  xor     ecx, ecx
0x180010a6b  call    ServerInit
0x180010a70  mov     [rdi], eax
0x180010a72  test    eax, eax
0x180010a74  jz      short loc_180010A82
0x180010a76  mov     cs:dword_1800519F8, 5B57h
0x180010a80  jmp     short loc_180010AAE
0x180010a82  mov     cs:gbServerInited, r15d
0x180010a89  test    r14, r14
0x180010a8c  jnz     loc_180010B35
0x180010a92  mov     rcx, rsi
0x180010a95  call    InitializeClient
0x180010a9a  mov     [rdi], eax
0x180010a9c  test    eax, eax
0x180010a9e  jz      loc_180010B35
0x180010aa4  mov     cs:dword_1800519F8, 5B62h
0x180010aae  call    cs:__imp_GetCurrentThreadId
0x180010ab4  lea     r8, aPrintscanTapiS_4+0Dh; pszSrc
0x180010abb  mov     cs:dword_1800519FC, eax
0x180010ac1  lea     rcx, byte_1800519E8; pszDest
0x180010ac8  call    StringCbCopyA
0x180010acd  mov     rcx, r13; lpCriticalSection
0x180010ad0  call    cs:__imp_LeaveCriticalSection
0x180010ad6  mov     rcx, rsi
0x180010ad9  call    WaitForExclusiveClientAccess
0x180010ade  test    rax, rax
0x180010ae1  jz      loc_180010BE0
0x180010ae7  mov     rcx, [rbx+28h]
0x180010aeb  test    rcx, rcx
0x180010aee  jz      short loc_180010AF8
0x180010af0  mov     rax, [rbx+20h]
0x180010af4  mov     [rcx+20h], rax
0x180010af8  mov     rcx, [rbx+20h]
0x180010afc  mov     rax, [rbx+28h]
0x180010b00  test    rcx, rcx
0x180010b03  jz      short loc_180010B0B
0x180010b05  mov     [rcx+28h], rax
0x180010b09  jmp     short loc_180010B12
0x180010b0b  mov     [rsi+0A8h], rax
0x180010b12  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180010b18  and     rax, rbp
0x180010b1b  lea     rcx, [rax+rax*4]
0x180010b1f  mov     rax, cs:gLockTable
0x180010b26  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180010b2a  call    cs:__imp_LeaveCriticalSection
0x180010b30  jmp     loc_180010BE0
0x180010b35  mov     r8d, [rbx+18h]
0x180010b39  lea     rdx, aLinitializeRet_1; "LInitialize: returning pParams->hLineAp"...
0x180010b40  mov     ebx, 40002h
0x180010b45  mov     [rdi+8], r8d
0x180010b49  mov     ecx, ebx
0x180010b4b  call    TRACELogPrint
0x180010b50  mov     r8d, cs:dword_18005191C
0x180010b57  lea     rdx, aLinitializeRet; "LInitialize: returning pParams->dwNumDe"...
0x180010b5e  mov     ecx, ebx
0x180010b60  mov     [rdi+18h], r8d
0x180010b64  call    TRACELogPrint
0x180010b69  test    byte ptr cs:dword_180051900, 2
0x180010b70  jz      short loc_180010B94
0x180010b72  test    [rsi+0D8h], r15b
0x180010b79  jnz     short loc_180010B94
0x180010b7b  mov     r8d, [rsi+60h]
0x180010b7f  lea     rdx, aLinitializeRet_0; "LInitialize: returning pParams->dwNumDe"...
0x180010b86  mov     ecx, 80002h
0x180010b8b  mov     [rdi+18h], r8d
0x180010b8f  call    TRACELogPrint
0x180010b94  mov     rax, [rsp+48h+arg_20]
0x180010b99  add     cs:dword_180051918, r15d
0x180010ba0  mov     dword ptr [rax], 24h ; '$'
0x180010ba6  mov     cs:dword_1800519F8, 5B8Ah
0x180010bb0  call    cs:__imp_GetCurrentThreadId
0x180010bb6  lea     r8, aPrintscanTapiS_4+0Dh; pszSrc
0x180010bbd  mov     cs:dword_1800519FC, eax
0x180010bc3  lea     rcx, byte_1800519E8; pszDest
0x180010bca  call    StringCbCopyA
0x180010bcf  mov     rcx, r13; lpCriticalSection
0x180010bd2  call    cs:__imp_LeaveCriticalSection
0x180010bd8  jmp     short loc_180010BF3
0x180010bda  mov     dword ptr [rdi], 80000048h
0x180010be0  mov     edx, [rbx+18h]
0x180010be3  mov     r8d, r15d
0x180010be6  call    DereferenceObject
0x180010beb  jmp     short loc_180010BF3
0x180010bed  mov     dword ptr [rdi], 80000044h
0x180010bf3  mov     r8d, [rdi]
0x180010bf6  lea     rdx, aLineinitialize; "lineInitialize: exit, result=x%x"
0x180010bfd  mov     ecx, 80002h
0x180010c02  call    TRACELogPrint
0x180010c07  jmp     short loc_180010C0F
0x180010c09  mov     dword ptr [rdi], 80000048h
0x180010c0f  mov     rbx, [rsp+48h+arg_0]
0x180010c14  mov     rbp, [rsp+48h+arg_10]
0x180010c19  add     rsp, 20h
0x180010c1d  pop     r15
0x180010c1f  pop     r14
0x180010c21  pop     r13
0x180010c23  pop     rdi
0x180010c24  pop     rsi
0x180010c25  retn
```
