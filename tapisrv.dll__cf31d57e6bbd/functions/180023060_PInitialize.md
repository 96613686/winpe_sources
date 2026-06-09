# PInitialize

- ea: `0x180023060`
- end: `0x18002348f`
- name: `PInitialize`
- size: `1071`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x180001f50`
- `0x18000443c`
- `0x1800072e4`
- `0x18001c7c0`
- `0x18001c854`
- `0x18001f494`
- `0x180023060`
- `0x18002b25c`
- `0x18002c8d4`
- `0x18002c8fc`
- `0x18003dc84`
- `0x18003e15c`
- `0x18003e2f0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180023117`
- `KERNEL32!HeapAlloc` at `0x180023117`
- `KERNEL32!GetCurrentThreadId` at `0x1800232ad`
- `KERNEL32!GetCurrentThreadId` at `0x18002332c`
- `KERNEL32!GetCurrentThreadId` at `0x1800233fd`
- `KERNEL32!GetCurrentThreadId` at `0x1800232ad`
- `KERNEL32!GetCurrentThreadId` at `0x18002332c`
- `KERNEL32!GetCurrentThreadId` at `0x1800233fd`
- `KERNEL32!LeaveCriticalSection` at `0x18002327c`
- `KERNEL32!LeaveCriticalSection` at `0x180023352`
- `KERNEL32!LeaveCriticalSection` at `0x1800233ac`
- `KERNEL32!LeaveCriticalSection` at `0x180023423`
- `KERNEL32!LeaveCriticalSection` at `0x18002327c`
- `KERNEL32!LeaveCriticalSection` at `0x180023352`
- `KERNEL32!LeaveCriticalSection` at `0x1800233ac`
- `KERNEL32!LeaveCriticalSection` at `0x180023423`
- `KERNEL32!lstrlenW` at `0x1800230c7`
- `KERNEL32!lstrlenW` at `0x1800230db`
- `KERNEL32!lstrlenW` at `0x1800230c7`
- `KERNEL32!lstrlenW` at `0x1800230db`
- `KERNEL32!EnterCriticalSection` at `0x18002329d`
- `KERNEL32!EnterCriticalSection` at `0x18002329d`

## pseudocode

```c
__int64 __fastcall PInitialize(unsigned __int64 a1, _DWORD *a2, unsigned int a3, __int64 a4, _DWORD *a5)
{
  __int64 v9; // r14
  __int64 v10; // r15
  _DWORD *v11; // rax
  __int64 v12; // rcx
  _DWORD *v13; // rbx
  int v14; // eax
  wchar_t *v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rax
  unsigned __int64 v18; // rax
  size_t v19; // rdx
  int v20; // eax
  int v21; // eax
  size_t v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rax
  size_t v27; // rdx
  __int64 result; // rax
  SIZE_T dwBytes; // [rsp+68h] [rbp+10h] BYREF

  LODWORD(dwBytes) = 0;
  TRACELogPrint(524290, "PInitialize - enter. dwParamsBufferSize %lx, ptClient %p", a3, (const void *)a1);
  if ( !IsBadStringParam(a3, a4, a2[5]) && !IsBadStringParam(a3, a4, a2[7]) )
  {
    v9 = (unsigned int)(2 * lstrlenW((LPCWSTR)(a4 + (unsigned int)a2[5])) + 2);
    v10 = (unsigned int)(2 * lstrlenW((LPCWSTR)(a4 + (unsigned int)a2[7])) + 2);
    if ( (int)DWordAdd3(200, (unsigned int)v9, v10, &dwBytes) < 0
      || (v11 = HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)dwBytes), (v13 = v11) == 0) )
    {
      *a2 = -1879048166;
      return TRACELogPrint(524290, "phoneInitialize: exit, result=x%x", *a2);
    }
    v14 = NewObject(v12, v11, 0);
    v13[1] = v14;
    if ( !v14 )
    {
      *a2 = -1879048166;
      ServerFree(v13);
      return TRACELogPrint(524290, "phoneInitialize: exit, result=x%x", *a2);
    }
    *v13 = 1347436880;
    *((_QWORD *)v13 + 1) = a1;
    v13[4] = a2[4];
    v13[16] = a2[8];
    *((_QWORD *)v13 + 6) = v13 + 50;
    v13[17] = v9;
    StringCbCopyW((STRSAFE_LPWSTR)v13 + 100, (unsigned int)v9, (STRSAFE_LPCWSTR)(a4 + (unsigned int)a2[5]));
    v13[18] = v10;
    v15 = (wchar_t *)((char *)v13 + v9 + 200);
    *((_QWORD *)v13 + 7) = v15;
    StringCbCopyW(v15, (unsigned int)v10, (STRSAFE_LPCWSTR)(a4 + (unsigned int)a2[7]));
    v16 = *(_QWORD *)(a1 + 168);
    if ( !WaitForExclusiveClientAccess(a1) )
    {
      TRACELogPrint(65538, "PInitialize - error2.");
      *a2 = -1879048164;
LABEL_37:
      DereferenceObject(v23, v13[1], 1);
      return TRACELogPrint(524290, "phoneInitialize: exit, result=x%x", *a2);
    }
    if ( v13[16] > 0x30000u )
    {
      *(_OWORD *)(v13 + 19) = *(_OWORD *)(a1 + 252);
      *(_OWORD *)(v13 + 23) = *(_OWORD *)(a1 + 268);
      *(_OWORD *)(v13 + 27) = *(_OWORD *)(a1 + 284);
      *(_OWORD *)(v13 + 31) = *(_OWORD *)(a1 + 300);
      *(_OWORD *)(v13 + 35) = *(_OWORD *)(a1 + 316);
      *(_OWORD *)(v13 + 39) = *(_OWORD *)(a1 + 332);
      *(_OWORD *)(v13 + 43) = *(_OWORD *)(a1 + 348);
      *(_OWORD *)(v13 + 46) = *(_OWORD *)(a1 + 360);
    }
    else
    {
      memset_0(v13 + 19, 255, 0x7Cu);
    }
    v17 = *(_QWORD *)(a1 + 176);
    *((_QWORD *)v13 + 5) = v17;
    if ( v17 )
      *(_QWORD *)(v17 + 32) = v13;
    v18 = (a1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits;
    *(_QWORD *)(a1 + 176) = v13;
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + v18);
    if ( (dword_180051900 & 1) != 0 )
    {
      *a2 = -1879048157;
      goto LABEL_25;
    }
    EnterCriticalSection(&CriticalSection);
    dword_1800519E0 = 4549;
    dword_1800519E4 = GetCurrentThreadId();
    StringCbCopyA(pszDest, v19, "\\server\\phone.c");
    if ( !dword_180051918 && !dword_180051928 && !gbServerInited )
    {
      v20 = ServerInit(0);
      *a2 = v20;
      if ( v20 )
      {
        dword_1800519F8 = 4557;
LABEL_24:
        dword_1800519FC = GetCurrentThreadId();
        StringCbCopyA(byte_1800519E8, v22, "\\server\\phone.c");
        LeaveCriticalSection(&CriticalSection);
LABEL_25:
        if ( WaitForExclusiveClientAccess(a1) )
        {
          v24 = *((_QWORD *)v13 + 5);
          if ( v24 )
            *(_QWORD *)(v24 + 32) = *((_QWORD *)v13 + 4);
          v25 = *((_QWORD *)v13 + 4);
          v26 = *((_QWORD *)v13 + 5);
          if ( v25 )
            *(_QWORD *)(v25 + 40) = v26;
          else
            *(_QWORD *)(a1 + 176) = v26;
          LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((a1 >> 4) & (unsigned int)gdwPointerToLockTableIndexBits));
        }
        goto LABEL_37;
      }
      gbServerInited = 1;
    }
    if ( v16 || (v21 = InitializeClient(a1), (*a2 = v21) == 0) )
    {
      a2[2] = v13[1];
      a2[6] = dword_18005192C;
      if ( (dword_180051900 & 2) != 0 && (*(_BYTE *)(a1 + 216) & 1) == 0 )
        a2[6] = *(_DWORD *)(a1 + 120);
      ++dword_180051928;
      *a5 = 36;
      dword_1800519F8 = 4604;
      dword_1800519FC = GetCurrentThreadId();
      StringCbCopyA(byte_1800519E8, v27, "\\server\\phone.c");
      LeaveCriticalSection(&CriticalSection);
      return TRACELogPrint(524290, "phoneInitialize: exit, result=x%x", *a2);
    }
    dword_1800519F8 = 4570;
    goto LABEL_24;
  }
  result = TRACELogPrint(65538, "PInitialize - error1.");
  *a2 = -1879048164;
  return result;
}

```

## disassembly

```asm
0x180023060  push    rbx
0x180023062  push    rbp
0x180023063  push    rsi
0x180023064  push    rdi
0x180023065  push    r14
0x180023067  push    r15
0x180023069  sub     rsp, 28h
0x18002306d  mov     rbp, r9
0x180023070  mov     dword ptr [rsp+58h+dwBytes], 0
0x180023078  mov     r9, rcx
0x18002307b  mov     rdi, rdx
0x18002307e  mov     rsi, rcx
0x180023081  lea     rdx, aPinitializeEnt; "PInitialize - enter. dwParamsBufferSize"...
0x180023088  mov     ecx, 80002h
0x18002308d  mov     ebx, r8d
0x180023090  call    TRACELogPrint
0x180023095  mov     r8d, [rdi+14h]
0x180023099  mov     rdx, rbp
0x18002309c  mov     ecx, ebx
0x18002309e  call    IsBadStringParam
0x1800230a3  test    eax, eax
0x1800230a5  jnz     loc_18002346B
0x1800230ab  mov     r8d, [rdi+1Ch]
0x1800230af  mov     rdx, rbp
0x1800230b2  mov     ecx, ebx
0x1800230b4  call    IsBadStringParam
0x1800230b9  test    eax, eax
0x1800230bb  jnz     loc_18002346B
0x1800230c1  mov     ecx, [rdi+14h]
0x1800230c4  add     rcx, rbp; lpString
0x1800230c7  call    cs:__imp_lstrlenW
0x1800230cd  mov     ecx, [rdi+1Ch]
0x1800230d0  add     rcx, rbp; lpString
0x1800230d3  lea     r14d, ds:2[rax*2]
0x1800230db  call    cs:__imp_lstrlenW
0x1800230e1  lea     r9, [rsp+58h+dwBytes]
0x1800230e6  mov     edx, r14d
0x1800230e9  mov     ecx, 0C8h
0x1800230ee  lea     r15d, ds:2[rax*2]
0x1800230f6  mov     r8d, r15d
0x1800230f9  call    DWordAdd3
0x1800230fe  test    eax, eax
0x180023100  js      loc_18002344F
0x180023106  mov     r8d, dword ptr [rsp+58h+dwBytes]; dwBytes
0x18002310b  mov     edx, 8; dwFlags
0x180023110  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180023117  call    cs:__imp_HeapAlloc
0x18002311d  mov     rbx, rax
0x180023120  test    rax, rax
0x180023123  jz      loc_18002344F
0x180023129  xor     r8d, r8d
0x18002312c  mov     rdx, rax
0x18002312f  call    NewObject
0x180023134  mov     [rbx+4], eax
0x180023137  test    eax, eax
0x180023139  jnz     short loc_18002314E
0x18002313b  mov     rcx, rbx; lpMem
0x18002313e  mov     dword ptr [rdi], 9000001Ah
0x180023144  call    ServerFree
0x180023149  jmp     loc_180023455
0x18002314e  mov     dword ptr [rbx], 50504150h
0x180023154  lea     rcx, [rbx+0C8h]; pszDest
0x18002315b  mov     [rbx+8], rsi
0x18002315f  mov     eax, [rdi+10h]
0x180023162  mov     [rbx+10h], eax
0x180023165  mov     eax, [rdi+20h]
0x180023168  mov     [rbx+40h], eax
0x18002316b  mov     [rbx+30h], rcx
0x18002316f  mov     [rbx+44h], r14d
0x180023173  mov     r8d, [rdi+14h]
0x180023177  add     r8, rbp; pszSrc
0x18002317a  mov     edx, r14d; cbDest
0x18002317d  call    StringCbCopyW
0x180023182  mov     [rbx+48h], r15d
0x180023186  lea     rcx, [r14+0C8h]
0x18002318d  add     rcx, rbx; pszDest
0x180023190  mov     edx, r15d; cbDest
0x180023193  mov     [rbx+38h], rcx
0x180023197  mov     r8d, [rdi+1Ch]
0x18002319b  add     r8, rbp; pszSrc
0x18002319e  call    StringCbCopyW
0x1800231a3  mov     r14, [rsi+0A8h]
0x1800231aa  mov     rcx, rsi
0x1800231ad  call    WaitForExclusiveClientAccess
0x1800231b2  mov     r15d, 1
0x1800231b8  test    rax, rax
0x1800231bb  jz      loc_18002342B
0x1800231c1  cmp     dword ptr [rbx+40h], 30000h
0x1800231c8  ja      short loc_1800231DE
0x1800231ca  mov     edx, 0FFh; Val
0x1800231cf  lea     r8d, [r15+7Bh]; Size
0x1800231d3  lea     rcx, [rbx+4Ch]; void *
0x1800231d7  call    memset_0
0x1800231dc  jmp     short loc_180023242
0x1800231de  movups  xmm0, xmmword ptr [rsi+0FCh]
0x1800231e5  movups  xmmword ptr [rbx+4Ch], xmm0
0x1800231e9  movups  xmm1, xmmword ptr [rsi+10Ch]
0x1800231f0  movups  xmmword ptr [rbx+5Ch], xmm1
0x1800231f4  movups  xmm0, xmmword ptr [rsi+11Ch]
0x1800231fb  movups  xmmword ptr [rbx+6Ch], xmm0
0x1800231ff  movups  xmm1, xmmword ptr [rsi+12Ch]
0x180023206  movups  xmmword ptr [rbx+7Ch], xmm1
0x18002320a  movups  xmm0, xmmword ptr [rsi+13Ch]
0x180023211  movups  xmmword ptr [rbx+8Ch], xmm0
0x180023218  movups  xmm1, xmmword ptr [rsi+14Ch]
0x18002321f  movups  xmmword ptr [rbx+9Ch], xmm1
0x180023226  movups  xmm0, xmmword ptr [rsi+15Ch]
0x18002322d  movups  xmmword ptr [rbx+0ACh], xmm0
0x180023234  movups  xmm1, xmmword ptr [rsi+168h]
0x18002323b  movups  xmmword ptr [rbx+0B8h], xmm1
0x180023242  mov     rax, [rsi+0B0h]
0x180023249  mov     [rbx+28h], rax
0x18002324d  test    rax, rax
0x180023250  jz      short loc_180023256
0x180023252  mov     [rax+20h], rbx
0x180023256  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002325c  mov     rbp, rsi
0x18002325f  shr     rbp, 4
0x180023263  and     rax, rbp
0x180023266  mov     [rsi+0B0h], rbx
0x18002326d  lea     rcx, [rax+rax*4]
0x180023271  mov     rax, cs:gLockTable
0x180023278  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002327c  call    cs:__imp_LeaveCriticalSection
0x180023282  test    byte ptr cs:dword_180051900, r15b
0x180023289  jz      short loc_180023296
0x18002328b  mov     dword ptr [rdi], 90000023h
0x180023291  jmp     loc_180023358
0x180023296  lea     rcx, CriticalSection; lpCriticalSection
0x18002329d  call    cs:__imp_EnterCriticalSection
0x1800232a3  mov     cs:dword_1800519E0, 11C5h
0x1800232ad  call    cs:__imp_GetCurrentThreadId
0x1800232b3  lea     r8, aPrintscanTapiS_2+0Eh; pszSrc
0x1800232ba  mov     cs:dword_1800519E4, eax
0x1800232c0  lea     rcx, pszDest; pszDest
0x1800232c7  call    StringCbCopyA
0x1800232cc  cmp     cs:dword_180051918, 0
0x1800232d3  jnz     short loc_180023307
0x1800232d5  cmp     cs:dword_180051928, 0
0x1800232dc  jnz     short loc_180023307
0x1800232de  cmp     cs:gbServerInited, 0
0x1800232e5  jnz     short loc_180023307
0x1800232e7  xor     ecx, ecx
0x1800232e9  call    ServerInit
0x1800232ee  mov     [rdi], eax
0x1800232f0  test    eax, eax
0x1800232f2  jz      short loc_180023300
0x1800232f4  mov     cs:dword_1800519F8, 11CDh
0x1800232fe  jmp     short loc_18002332C
0x180023300  mov     cs:gbServerInited, r15d
0x180023307  test    r14, r14
0x18002330a  jnz     loc_1800233B7
0x180023310  mov     rcx, rsi
0x180023313  call    InitializeClient
0x180023318  mov     [rdi], eax
0x18002331a  test    eax, eax
0x18002331c  jz      loc_1800233B7
0x180023322  mov     cs:dword_1800519F8, 11DAh
0x18002332c  call    cs:__imp_GetCurrentThreadId
0x180023332  lea     r8, aPrintscanTapiS_2+0Eh; pszSrc
0x180023339  mov     cs:dword_1800519FC, eax
0x18002333f  lea     rcx, byte_1800519E8; pszDest
0x180023346  call    StringCbCopyA
0x18002334b  lea     rcx, CriticalSection; lpCriticalSection
0x180023352  call    cs:__imp_LeaveCriticalSection
0x180023358  mov     rcx, rsi
0x18002335b  call    WaitForExclusiveClientAccess
0x180023360  test    rax, rax
0x180023363  jz      loc_180023442
0x180023369  mov     rcx, [rbx+28h]
0x18002336d  test    rcx, rcx
0x180023370  jz      short loc_18002337A
0x180023372  mov     rax, [rbx+20h]
0x180023376  mov     [rcx+20h], rax
0x18002337a  mov     rcx, [rbx+20h]
0x18002337e  mov     rax, [rbx+28h]
0x180023382  test    rcx, rcx
0x180023385  jz      short loc_18002338D
0x180023387  mov     [rcx+28h], rax
0x18002338b  jmp     short loc_180023394
0x18002338d  mov     [rsi+0B0h], rax
0x180023394  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002339a  and     rax, rbp
0x18002339d  lea     rcx, [rax+rax*4]
0x1800233a1  mov     rax, cs:gLockTable
0x1800233a8  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800233ac  call    cs:__imp_LeaveCriticalSection
0x1800233b2  jmp     loc_180023442
0x1800233b7  mov     eax, [rbx+4]
0x1800233ba  mov     [rdi+8], eax
0x1800233bd  mov     eax, cs:dword_18005192C
0x1800233c3  mov     [rdi+18h], eax
0x1800233c6  test    byte ptr cs:dword_180051900, 2
0x1800233cd  jz      short loc_1800233DE
0x1800233cf  test    [rsi+0D8h], r15b
0x1800233d6  jnz     short loc_1800233DE
0x1800233d8  mov     eax, [rsi+78h]
0x1800233db  mov     [rdi+18h], eax
0x1800233de  mov     rax, [rsp+58h+arg_20]
0x1800233e6  add     cs:dword_180051928, r15d
0x1800233ed  mov     dword ptr [rax], 24h ; '$'
0x1800233f3  mov     cs:dword_1800519F8, 11FCh
0x1800233fd  call    cs:__imp_GetCurrentThreadId
0x180023403  lea     r8, aPrintscanTapiS_2+0Eh; pszSrc
0x18002340a  mov     cs:dword_1800519FC, eax
0x180023410  lea     rcx, byte_1800519E8; pszDest
0x180023417  call    StringCbCopyA
0x18002341c  lea     rcx, CriticalSection; lpCriticalSection
0x180023423  call    cs:__imp_LeaveCriticalSection
0x180023429  jmp     short loc_180023455
0x18002342b  lea     rdx, aPinitializeErr_0; "PInitialize - error2."
0x180023432  mov     ecx, 10002h
0x180023437  call    TRACELogPrint
0x18002343c  mov     dword ptr [rdi], 9000001Ch
0x180023442  mov     edx, [rbx+4]
0x180023445  mov     r8d, r15d
0x180023448  call    DereferenceObject
0x18002344d  jmp     short loc_180023455
0x18002344f  mov     dword ptr [rdi], 9000001Ah
0x180023455  mov     r8d, [rdi]
0x180023458  lea     rdx, aPhoneinitializ; "phoneInitialize: exit, result=x%x"
0x18002345f  mov     ecx, 80002h
0x180023464  call    TRACELogPrint
0x180023469  jmp     short loc_180023482
0x18002346b  lea     rdx, aPinitializeErr; "PInitialize - error1."
0x180023472  mov     ecx, 10002h
0x180023477  call    TRACELogPrint
0x18002347c  mov     dword ptr [rdi], 9000001Ch
0x180023482  add     rsp, 28h
0x180023486  pop     r15
0x180023488  pop     r14
0x18002348a  pop     rdi
0x18002348b  pop     rsi
0x18002348c  pop     rbp
0x18002348d  pop     rbx
0x18002348e  retn
```
