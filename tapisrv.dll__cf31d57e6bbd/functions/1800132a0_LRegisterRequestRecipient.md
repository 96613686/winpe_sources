# LRegisterRequestRecipient

- ea: `0x1800132a0`
- end: `0x18001354d`
- name: `LRegisterRequestRecipient`
- size: `685`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x180006c14`
- `0x1800132a0`
- `0x18001abb8`
- `0x18001f514`
- `0x18002c8d4`
- `0x18003dc84`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180013336`
- `KERNEL32!HeapAlloc` at `0x180013336`
- `KERNEL32!LeaveCriticalSection` at `0x1800133bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800134c1`
- `KERNEL32!LeaveCriticalSection` at `0x180013512`
- `KERNEL32!LeaveCriticalSection` at `0x1800133bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800134c1`
- `KERNEL32!LeaveCriticalSection` at `0x180013512`
- `KERNEL32!EnterCriticalSection` at `0x180013371`
- `KERNEL32!EnterCriticalSection` at `0x180013415`
- `KERNEL32!EnterCriticalSection` at `0x180013371`
- `KERNEL32!EnterCriticalSection` at `0x180013415`

## string_xrefs

- `0x1800132f4`: `App is already registered for mediacall`
- `0x1800133d2`: `App is already registered for makecall`

## pseudocode

```c
__int64 __fastcall LRegisterRequestRecipient(__int64 a1, _DWORD *a2)
{
  unsigned __int64 v3; // rdi
  int v4; // eax
  int v5; // ebp
  int v6; // ebx
  _DWORD *v7; // rax
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 HighestPriorityRequestRecipient; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rbx
  int v19; // eax

  v3 = WaitForExclusiveLineAppAccess((unsigned int)a2[2], a1);
  if ( !v3 )
  {
    *a2 = dword_180051918 != 0 ? -2147483628 : -2147483568;
    return TRACELogPrint(524290, "lineRegisterRequestRecipient: exit, returning x%x", *a2);
  }
  v4 = a2[4];
  if ( (v4 & 3) == 0 || (v4 & 0xFFFFFFFC) != 0 )
  {
    *a2 = -2147483592;
    goto LABEL_45;
  }
  v5 = a2[4] & 2;
  if ( !a2[5] )
  {
    if ( (v4 & 2) == 0 || *(_DWORD *)(v3 + 52) )
    {
      if ( (v4 & 1) != 0 )
      {
        v12 = *(_QWORD **)(v3 + 56);
        if ( v12 )
        {
          EnterCriticalSection(&gPriorityListCritSec);
          v13 = v12[3];
          if ( v13 )
            *(_QWORD *)(v13 + 16) = v12[2];
          v14 = v12[2];
          if ( v14 )
            *(_QWORD *)(v14 + 24) = v12[3];
          else
            qword_180051938 = v12[3];
          ServerFree(v12);
          *(_QWORD *)(v3 + 56) = 0;
          HighestPriorityRequestRecipient = GetHighestPriorityRequestRecipient(v15);
          v17 = lpMem;
          qword_180051940 = HighestPriorityRequestRecipient;
          if ( lpMem )
          {
            if ( HighestPriorityRequestRecipient )
            {
              NotifyHighestPriorityRequestRecipient(lpMem);
            }
            else
            {
              qword_180051950 = 0;
              lpMem = 0;
              if ( v17 )
              {
                do
                {
                  v18 = (_QWORD *)v17[60];
                  ServerFree(v17);
                  v17 = v18;
                }
                while ( v18 );
              }
              TRACELogPrint(262146, "LRegisterRequestRecipient: deleting pending MakeCall requests");
            }
          }
          LeaveCriticalSection(&gPriorityListCritSec);
        }
        else
        {
          TRACELogPrint(65538, "App is not registered for makecall");
          *a2 = -2147483576;
        }
      }
      if ( v5 )
        v19 = 0;
      else
        v19 = *(_DWORD *)(v3 + 52);
      *(_DWORD *)(v3 + 52) = v19;
      goto LABEL_45;
    }
    TRACELogPrint(65538, "App is not registered for mediacall");
    goto LABEL_8;
  }
  if ( (v4 & 2) == 0 || !*(_DWORD *)(v3 + 52) )
  {
    v6 = 1;
    if ( (v4 & 1) != 0 )
    {
      if ( *(_QWORD *)(v3 + 56) )
      {
        TRACELogPrint(65538, "App is already registered for makecall");
        goto LABEL_8;
      }
      v7 = HeapAlloc(ghTapisrvHeap, 8u, 0x20u);
      v8 = (__int64)v7;
      if ( !v7 )
      {
        TRACELogPrint(65538, "Failed alloc for requestrecip struct");
        *a2 = -2147483580;
        goto LABEL_45;
      }
      *(_QWORD *)v7 = v3;
      v7[2] = a2[3];
      EnterCriticalSection(&gPriorityListCritSec);
      v10 = qword_180051938;
      *(_QWORD *)(v8 + 24) = qword_180051938;
      if ( qword_180051938 )
        *(_QWORD *)(v10 + 16) = v8;
      qword_180051938 = v8;
      *(_QWORD *)(v3 + 56) = v8;
      qword_180051940 = GetHighestPriorityRequestRecipient(v9);
      if ( lpMem )
        NotifyHighestPriorityRequestRecipient(v11);
      LeaveCriticalSection(&gPriorityListCritSec);
    }
    if ( !v5 )
      v6 = *(_DWORD *)(v3 + 52);
    *(_DWORD *)(v3 + 52) = v6;
    goto LABEL_45;
  }
  TRACELogPrint(65538, "App is already registered for mediacall");
LABEL_8:
  *a2 = -2147483576;
LABEL_45:
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (v3 >> 4)));
  return TRACELogPrint(524290, "lineRegisterRequestRecipient: exit, returning x%x", *a2);
}

```

## disassembly

```asm
0x1800132a0  push    rbx
0x1800132a2  push    rbp
0x1800132a3  push    rsi
0x1800132a4  push    rdi
0x1800132a5  push    r14
0x1800132a7  sub     rsp, 20h
0x1800132ab  mov     rsi, rdx
0x1800132ae  mov     rdx, rcx
0x1800132b1  mov     ecx, [rsi+8]
0x1800132b4  call    WaitForExclusiveLineAppAccess
0x1800132b9  mov     rdi, rax
0x1800132bc  test    rax, rax
0x1800132bf  jz      loc_18001351A
0x1800132c5  mov     eax, [rsi+10h]
0x1800132c8  test    al, 3
0x1800132ca  jz      loc_1800134F0
0x1800132d0  test    eax, 0FFFFFFFCh
0x1800132d5  jnz     loc_1800134F0
0x1800132db  mov     ebp, eax
0x1800132dd  and     ebp, 2
0x1800132e0  cmp     dword ptr [rsi+14h], 0
0x1800132e4  jz      loc_1800133DE
0x1800132ea  test    ebp, ebp
0x1800132ec  jz      short loc_180013310
0x1800132ee  cmp     dword ptr [rdi+34h], 0
0x1800132f2  jz      short loc_180013310
0x1800132f4  lea     rdx, aAppIsAlreadyRe; "App is already registered for mediacall"
0x1800132fb  mov     ecx, 10002h
0x180013300  call    TRACELogPrint
0x180013305  mov     dword ptr [rsi], 80000048h
0x18001330b  jmp     loc_1800134F6
0x180013310  mov     ebx, 1
0x180013315  test    bl, al
0x180013317  jz      loc_1800133C3
0x18001331d  cmp     qword ptr [rdi+38h], 0
0x180013322  jnz     loc_1800133D2
0x180013328  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18001332f  lea     edx, [rbx+7]; dwFlags
0x180013332  lea     r8d, [rbx+1Fh]; dwBytes
0x180013336  call    cs:__imp_HeapAlloc
0x18001333c  mov     r14, rax
0x18001333f  test    rax, rax
0x180013342  jnz     short loc_180013360
0x180013344  lea     rdx, aFailedAllocFor; "Failed alloc for requestrecip struct"
0x18001334b  mov     ecx, 10002h
0x180013350  call    TRACELogPrint
0x180013355  mov     dword ptr [rsi], 80000044h
0x18001335b  jmp     loc_1800134F6
0x180013360  mov     [rax], rdi
0x180013363  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x18001336a  mov     eax, [rsi+0Ch]
0x18001336d  mov     [r14+8], eax
0x180013371  call    cs:__imp_EnterCriticalSection
0x180013377  mov     rax, cs:qword_180051938
0x18001337e  mov     [r14+18h], rax
0x180013382  cmp     cs:qword_180051938, 0
0x18001338a  jz      short loc_180013390
0x18001338c  mov     [rax+10h], r14
0x180013390  mov     cs:qword_180051938, r14
0x180013397  mov     [rdi+38h], r14
0x18001339b  call    GetHighestPriorityRequestRecipient
0x1800133a0  cmp     cs:lpMem, 0
0x1800133a8  mov     cs:qword_180051940, rax
0x1800133af  jz      short loc_1800133B6
0x1800133b1  call    NotifyHighestPriorityRequestRecipient
0x1800133b6  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x1800133bd  call    cs:__imp_LeaveCriticalSection
0x1800133c3  test    ebp, ebp
0x1800133c5  jnz     short loc_1800133CA
0x1800133c7  mov     ebx, [rdi+34h]
0x1800133ca  mov     [rdi+34h], ebx
0x1800133cd  jmp     loc_1800134F6
0x1800133d2  lea     rdx, aAppIsAlreadyRe_0; "App is already registered for makecall"
0x1800133d9  jmp     loc_1800132FB
0x1800133de  test    ebp, ebp
0x1800133e0  jz      short loc_1800133F4
0x1800133e2  cmp     dword ptr [rdi+34h], 0
0x1800133e6  jnz     short loc_1800133F4
0x1800133e8  lea     rdx, aAppIsNotRegist; "App is not registered for mediacall"
0x1800133ef  jmp     loc_1800132FB
0x1800133f4  mov     ebx, 1
0x1800133f9  test    bl, al
0x1800133fb  jz      loc_1800134E0
0x180013401  mov     rbx, [rdi+38h]
0x180013405  test    rbx, rbx
0x180013408  jz      loc_1800134C9
0x18001340e  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x180013415  call    cs:__imp_EnterCriticalSection
0x18001341b  mov     rdx, [rbx+18h]
0x18001341f  test    rdx, rdx
0x180013422  jz      short loc_18001342C
0x180013424  mov     rax, [rbx+10h]
0x180013428  mov     [rdx+10h], rax
0x18001342c  mov     rdx, [rbx+10h]
0x180013430  mov     rax, [rbx+18h]
0x180013434  test    rdx, rdx
0x180013437  jz      short loc_18001343F
0x180013439  mov     [rdx+18h], rax
0x18001343d  jmp     short loc_180013446
0x18001343f  mov     cs:qword_180051938, rax
0x180013446  mov     rcx, rbx; lpMem
0x180013449  call    ServerFree
0x18001344e  mov     qword ptr [rdi+38h], 0
0x180013456  call    GetHighestPriorityRequestRecipient
0x18001345b  mov     rcx, cs:lpMem; lpMem
0x180013462  mov     cs:qword_180051940, rax
0x180013469  test    rcx, rcx
0x18001346c  jz      short loc_1800134BA
0x18001346e  test    rax, rax
0x180013471  jz      short loc_18001347A
0x180013473  call    NotifyHighestPriorityRequestRecipient
0x180013478  jmp     short loc_1800134BA
0x18001347a  mov     cs:qword_180051950, 0
0x180013485  mov     cs:lpMem, 0
0x180013490  test    rcx, rcx
0x180013493  jz      short loc_1800134A9
0x180013495  mov     rbx, [rcx+1E0h]
0x18001349c  call    ServerFree
0x1800134a1  mov     rcx, rbx
0x1800134a4  test    rbx, rbx
0x1800134a7  jnz     short loc_180013495
0x1800134a9  lea     rdx, aLregisterreque; "LRegisterRequestRecipient: deleting pen"...
0x1800134b0  mov     ecx, 40002h
0x1800134b5  call    TRACELogPrint
0x1800134ba  lea     rcx, gPriorityListCritSec; lpCriticalSection
0x1800134c1  call    cs:__imp_LeaveCriticalSection
0x1800134c7  jmp     short loc_1800134E0
0x1800134c9  lea     rdx, aAppIsNotRegist_0; "App is not registered for makecall"
0x1800134d0  mov     ecx, 10002h
0x1800134d5  call    TRACELogPrint
0x1800134da  mov     dword ptr [rsi], 80000048h
0x1800134e0  test    ebp, ebp
0x1800134e2  jz      short loc_1800134E8
0x1800134e4  xor     eax, eax
0x1800134e6  jmp     short loc_1800134EB
0x1800134e8  mov     eax, [rdi+34h]
0x1800134eb  mov     [rdi+34h], eax
0x1800134ee  jmp     short loc_1800134F6
0x1800134f0  mov     dword ptr [rsi], 80000038h
0x1800134f6  mov     eax, cs:gdwPointerToLockTableIndexBits
0x1800134fc  shr     rdi, 4
0x180013500  and     rdi, rax
0x180013503  mov     rax, cs:gLockTable
0x18001350a  lea     rcx, [rdi+rdi*4]
0x18001350e  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180013512  call    cs:__imp_LeaveCriticalSection
0x180013518  jmp     short loc_18001352F
0x18001351a  mov     eax, cs:dword_180051918
0x180013520  neg     eax
0x180013522  sbb     ecx, ecx
0x180013524  and     ecx, 0FFFFFFC4h
0x180013527  add     ecx, 80000050h
0x18001352d  mov     [rsi], ecx
0x18001352f  mov     r8d, [rsi]
0x180013532  lea     rdx, aLineregisterre; "lineRegisterRequestRecipient: exit, ret"...
0x180013539  mov     ecx, 80002h
0x18001353e  add     rsp, 20h
0x180013542  pop     r14
0x180013544  pop     rdi
0x180013545  pop     rsi
0x180013546  pop     rbp
0x180013547  pop     rbx
0x180013548  jmp     TRACELogPrint
```
