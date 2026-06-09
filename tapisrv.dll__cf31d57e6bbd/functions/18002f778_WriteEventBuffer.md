# WriteEventBuffer

- ea: `0x18002f778`
- end: `0x18002fb6c`
- name: `WriteEventBuffer`
- size: `1012`
- prototype: `void __fastcall(unsigned __int64, unsigned int *)`
- caller_count: `20`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180003498`
- `0x18000469c`
- `0x180004cd0`
- `0x18000fe60`
- `0x180012480`
- `0x180017be0`
- `0x18001abb8`
- `0x18001b1dc`
- `0x18001b4c4`
- `0x18001b7bc`
- `0x18001b958`
- `0x18001bb04`
- `0x18001bd10`
- `0x18001c114`
- `0x180020b64`
- `0x180024fc8`
- `0x180025c28`
- `0x1800281f0`
- `0x18002b890`
- `0x1800330a8`

## callees

- `0x18001ea48`
- `0x18001f494`
- `0x18002c8d4`
- `0x18002f778`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18002f85b`
- `KERNEL32!HeapAlloc` at `0x18002f85b`
- `KERNEL32!WriteFile` at `0x18002fafe`
- `KERNEL32!WriteFile` at `0x18002fafe`
- `KERNEL32!GetTickCount` at `0x18002fa3b`
- `KERNEL32!GetTickCount` at `0x18002fb24`
- `KERNEL32!GetTickCount` at `0x18002fa3b`
- `KERNEL32!GetTickCount` at `0x18002fb24`
- `KERNEL32!SetEvent` at `0x18002f9db`
- `KERNEL32!SetEvent` at `0x18002fb3e`
- `KERNEL32!SetEvent` at `0x18002f9db`
- `KERNEL32!SetEvent` at `0x18002fb3e`
- `KERNEL32!GetLastError` at `0x18002fb08`
- `KERNEL32!GetLastError` at `0x18002fb08`
- `KERNEL32!LeaveCriticalSection` at `0x18002f805`
- `KERNEL32!LeaveCriticalSection` at `0x18002fa33`
- `KERNEL32!LeaveCriticalSection` at `0x18002fa7d`
- `KERNEL32!LeaveCriticalSection` at `0x18002fac4`
- `KERNEL32!LeaveCriticalSection` at `0x18002f805`
- `KERNEL32!LeaveCriticalSection` at `0x18002fa33`
- `KERNEL32!LeaveCriticalSection` at `0x18002fa7d`
- `KERNEL32!LeaveCriticalSection` at `0x18002fac4`
- `KERNEL32!EnterCriticalSection` at `0x18002fa04`
- `KERNEL32!EnterCriticalSection` at `0x18002fa4e`
- `KERNEL32!EnterCriticalSection` at `0x18002fa04`
- `KERNEL32!EnterCriticalSection` at `0x18002fa4e`

## string_xrefs

- `0x18002f798`: `WriteEventBuffer - enter`
- `0x18002f9c3`: `WriteEventBuffer: SetEvent %p for local client`
- `0x18002fb0e`: `WriteEventBuffer: Writefile(mailslot) failed, err=%u`
- `0x18002fb46`: `WriteEventBuffer: - WaitForExclusiveClientAccess returns 0`

## pseudocode

```c
void __fastcall WriteEventBuffer(unsigned __int64 a1, unsigned int *a2)
{
  unsigned __int64 v2; // r13
  ULONG v4; // r14d
  unsigned __int64 v5; // rcx
  char *v6; // rax
  char *v7; // rbp
  const void **v8; // rbx
  const void **v9; // rsi
  const void *v10; // rdx
  int v11; // r15d
  unsigned int v12; // eax
  unsigned int v13; // r15d
  __int64 v14; // r12
  __int64 v15; // rax
  char *v16; // rcx
  void *v17; // rcx
  int v18; // ebp
  unsigned int v19; // r12d
  void *v20; // r15
  unsigned int v21; // edx
  int v22; // r12d
  size_t v23; // r8
  __int64 v24; // r14
  _DWORD *v25; // r13
  char *v26; // rcx
  __int64 v27; // rax
  int v28; // r8d
  unsigned __int64 v29; // rax
  _QWORD *v30; // rbx
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  __int64 v33; // rax
  DWORD LastError; // eax
  void *Src; // [rsp+78h] [rbp+10h] BYREF
  __int64 pulResult; // [rsp+80h] [rbp+18h] BYREF
  int Buffer; // [rsp+88h] [rbp+20h] BYREF

  Src = a2;
  v2 = *a2;
  Buffer = 0;
  LODWORD(pulResult) = 0;
  TRACELogPrint(524290, "WriteEventBuffer - enter");
  if ( !WaitForExclusiveClientAccess(a1) )
  {
    TRACELogPrint(65538, "WriteEventBuffer: - WaitForExclusiveClientAccess returns 0");
    return;
  }
  v4 = *(_DWORD *)(a1 + 136);
  if ( ULongSub(v4, *(_DWORD *)(a1 + 140), (ULONG *)&pulResult) < 0 )
  {
LABEL_3:
    LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
    return;
  }
  if ( (unsigned int)v2 <= (unsigned int)pulResult )
  {
    v8 = (const void **)(a1 + 160);
    v9 = (const void **)(a1 + 144);
  }
  else
  {
    v5 = 40LL * ((unsigned int)(v2 / 0x28) + 20);
    if ( v5 > 0xFFFFFFFF )
      goto LABEL_3;
    v4 += v5;
    if ( v4 < (unsigned int)v5 )
      goto LABEL_3;
    v6 = (char *)HeapAlloc(ghTapisrvHeap, 8u, v4);
    v7 = v6;
    if ( !v6 )
      goto LABEL_3;
    v8 = (const void **)(a1 + 160);
    v9 = (const void **)(a1 + 144);
    if ( *(_DWORD *)(a1 + 140) )
    {
      v10 = *v8;
      v11 = *(_DWORD *)(a1 + 152);
      if ( *(_QWORD *)(a1 + 152) <= (unsigned __int64)*v8 )
      {
        v12 = *(_DWORD *)v9 + *(_DWORD *)(a1 + 136) - *(_DWORD *)v8;
        v13 = v11 - *(_DWORD *)v9;
      }
      else
      {
        v12 = v11 - (_DWORD)v10;
        v13 = 0;
      }
      v14 = v12;
      memcpy_0(v7, v10, v12);
      v15 = v13;
      pulResult = v13;
      if ( v13 )
      {
        memcpy_0(&v7[v14], *v9, v13);
        v15 = pulResult;
      }
      v16 = &v7[v14 + v15];
    }
    else
    {
      v16 = v6;
    }
    *(_QWORD *)(a1 + 152) = v16;
    ServerFree((LPVOID)*v9);
    *v9 = v7;
    *v8 = v7;
    *(_DWORD *)(a1 + 136) = v4;
  }
  v17 = *(void **)(a1 + 152);
  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( v17 >= *v8 )
  {
    v21 = v4 + *(_DWORD *)v9 - (_DWORD)v17;
    if ( (unsigned int)v2 > v21 )
    {
      v22 = v2;
      LODWORD(v2) = v4 + *(_DWORD *)v9 - (_DWORD)v17;
      v19 = v22 - v21;
    }
  }
  v23 = (unsigned int)v2;
  v24 = (unsigned int)v2;
  v25 = Src;
  memcpy_0(v17, Src, v23);
  v26 = (char *)*v9;
  if ( v19 )
  {
    memcpy_0(v26, (char *)v25 + v24, v19);
    v26 = (char *)*v9 + v19;
  }
  else
  {
    v27 = *(unsigned int *)(a1 + 136);
    *(_QWORD *)(a1 + 152) += v24;
    if ( *(_QWORD *)(a1 + 152) < (unsigned __int64)&v26[v27] )
      goto LABEL_25;
  }
  *(_QWORD *)(a1 + 152) = v26;
LABEL_25:
  v28 = *(_DWORD *)(a1 + 140);
  v29 = *(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFFFEuLL;
  *(_DWORD *)(a1 + 140) = v28 + *v25;
  if ( v29 == -2 || *(_QWORD *)(a1 + 8) == -3 )
  {
    if ( !v28 )
    {
      v30 = (_QWORD *)(a1 + 224);
      if ( *(_QWORD *)(a1 + 8) == -1 )
      {
        EnterCriticalSection(&gCnClientMsgPendingCritSec);
        v31 = (_QWORD *)qword_180051CB8;
        *v30 = &CnClientMsgPendingListHead;
        *(_QWORD *)(a1 + 232) = v31;
        *v31 = v30;
        qword_180051CB8 = a1 + 224;
        LeaveCriticalSection(&gCnClientMsgPendingCritSec);
      }
      else
      {
        *(_DWORD *)(a1 + 244) = GetTickCount();
        EnterCriticalSection(&gDgClientMsgPendingCritSec);
        v32 = (_QWORD *)qword_180051D58;
        *v30 = &DgClientMsgPendingListHead;
        *(_QWORD *)(a1 + 232) = v32;
        *v32 = v30;
        qword_180051D58 = a1 + 224;
        LeaveCriticalSection(&gDgClientMsgPendingCritSec);
        v33 = *(_QWORD *)(a1 + 168);
        v20 = *(void **)(a1 + 128);
        if ( v33 )
          LODWORD(v33) = *(_DWORD *)(v33 + 28);
        Buffer = v33;
      }
      v18 = 1;
    }
  }
  else
  {
    TRACELogPrint(524290, "WriteEventBuffer: SetEvent %p for local client", *(const void **)(a1 + 128));
    SetEvent(*(HANDLE *)(a1 + 128));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
  if ( v18 )
  {
    if ( v20 )
    {
      LODWORD(Src) = 0;
      if ( WriteFile(v20, &Buffer, 4u, (LPDWORD)&Src, 0) )
      {
        *(_DWORD *)(a1 + 240) = GetTickCount() + 2000;
      }
      else
      {
        LastError = GetLastError();
        TRACELogPrint(65538, "WriteEventBuffer: Writefile(mailslot) failed, err=%u", LastError);
      }
    }
    else
    {
      SetEvent(hEvent);
    }
  }
}

```

## disassembly

```asm
0x18002f778  mov     rax, rsp
0x18002f77b  mov     [rax+8], rbx
0x18002f77f  mov     [rax+10h], rdx
0x18002f783  push    rbp
0x18002f784  push    rsi
0x18002f785  push    rdi
0x18002f786  push    r12
0x18002f788  push    r13
0x18002f78a  push    r14
0x18002f78c  push    r15
0x18002f78e  sub     rsp, 30h
0x18002f792  mov     r13d, [rdx]
0x18002f795  mov     rdi, rcx
0x18002f798  lea     rdx, aWriteeventbuff_1; "WriteEventBuffer - enter"
0x18002f79f  mov     dword ptr [rax+20h], 0
0x18002f7a6  mov     ecx, 80002h
0x18002f7ab  mov     dword ptr [rax+18h], 0
0x18002f7b2  call    TRACELogPrint
0x18002f7b7  mov     rcx, rdi
0x18002f7ba  call    WaitForExclusiveClientAccess
0x18002f7bf  test    rax, rax
0x18002f7c2  jz      loc_18002FB46
0x18002f7c8  mov     r14d, [rdi+88h]
0x18002f7cf  lea     r8, [rsp+68h+pulResult]; pulResult
0x18002f7d7  mov     edx, [rdi+8Ch]; ulSubtrahend
0x18002f7dd  mov     ecx, r14d; ulMinuend
0x18002f7e0  call    ULongSub
0x18002f7e5  test    eax, eax
0x18002f7e7  jns     short loc_18002F810
0x18002f7e9  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002f7ef  shr     rdi, 4
0x18002f7f3  and     rdi, rax
0x18002f7f6  mov     rax, cs:gLockTable
0x18002f7fd  lea     rcx, [rdi+rdi*4]
0x18002f801  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002f805  call    cs:__imp_LeaveCriticalSection
0x18002f80b  jmp     loc_18002FB57
0x18002f810  cmp     r13d, dword ptr [rsp+68h+pulResult]
0x18002f818  jbe     loc_18002F90A
0x18002f81e  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18002f828  mul     r13
0x18002f82b  mov     eax, 0FFFFFFFFh
0x18002f830  shr     rdx, 5
0x18002f834  add     edx, 14h
0x18002f837  lea     rcx, [rdx+rdx*4]
0x18002f83b  shl     rcx, 3
0x18002f83f  cmp     rcx, rax
0x18002f842  ja      short loc_18002F7E9
0x18002f844  add     r14d, ecx
0x18002f847  cmp     r14d, ecx
0x18002f84a  jb      short loc_18002F7E9
0x18002f84c  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002f853  mov     edx, 8; dwFlags
0x18002f858  mov     r8d, r14d; dwBytes
0x18002f85b  call    cs:__imp_HeapAlloc
0x18002f861  mov     rbp, rax
0x18002f864  test    rax, rax
0x18002f867  jz      short loc_18002F7E9
0x18002f869  cmp     dword ptr [rdi+8Ch], 0
0x18002f870  lea     rbx, [rdi+0A0h]
0x18002f877  lea     rsi, [rdi+90h]
0x18002f87e  jz      short loc_18002F8E9
0x18002f880  mov     rdx, [rbx]; Src
0x18002f883  mov     r15d, [rdi+98h]
0x18002f88a  cmp     [rdi+98h], rdx
0x18002f891  jbe     short loc_18002F89E
0x18002f893  sub     r15d, edx
0x18002f896  mov     eax, r15d
0x18002f899  xor     r15d, r15d
0x18002f89c  jmp     short loc_18002F8AB
0x18002f89e  mov     eax, [rdi+88h]
0x18002f8a4  sub     eax, [rbx]
0x18002f8a6  add     eax, [rsi]
0x18002f8a8  sub     r15d, [rsi]
0x18002f8ab  mov     r8d, eax; Size
0x18002f8ae  mov     rcx, rbp; void *
0x18002f8b1  mov     r12d, eax
0x18002f8b4  call    memcpy_0
0x18002f8b9  mov     eax, r15d
0x18002f8bc  mov     [rsp+68h+pulResult], rax
0x18002f8c4  test    r15d, r15d
0x18002f8c7  jz      short loc_18002F8E0
0x18002f8c9  mov     rdx, [rsi]; Src
0x18002f8cc  lea     rcx, [r12+rbp]; void *
0x18002f8d0  mov     r8d, eax; Size
0x18002f8d3  call    memcpy_0
0x18002f8d8  mov     rax, [rsp+68h+pulResult]
0x18002f8e0  lea     rcx, [r12+rax]
0x18002f8e4  add     rcx, rbp
0x18002f8e7  jmp     short loc_18002F8EC
0x18002f8e9  mov     rcx, rbp
0x18002f8ec  mov     [rdi+98h], rcx
0x18002f8f3  mov     rcx, [rsi]; lpMem
0x18002f8f6  call    ServerFree
0x18002f8fb  mov     [rsi], rbp
0x18002f8fe  mov     [rbx], rbp
0x18002f901  mov     [rdi+88h], r14d
0x18002f908  jmp     short loc_18002F918
0x18002f90a  lea     rbx, [rdi+0A0h]
0x18002f911  lea     rsi, [rdi+90h]
0x18002f918  mov     rcx, [rdi+98h]; void *
0x18002f91f  xor     ebp, ebp
0x18002f921  xor     r12d, r12d
0x18002f924  xor     r15d, r15d
0x18002f927  cmp     rcx, [rbx]
0x18002f92a  jb      short loc_18002F941
0x18002f92c  mov     edx, [rsi]
0x18002f92e  sub     edx, ecx
0x18002f930  add     edx, r14d
0x18002f933  cmp     r13d, edx
0x18002f936  jbe     short loc_18002F941
0x18002f938  mov     r12d, r13d
0x18002f93b  mov     r13d, edx
0x18002f93e  sub     r12d, edx
0x18002f941  mov     r8d, r13d; Size
0x18002f944  mov     r14d, r13d
0x18002f947  mov     r13, [rsp+68h+Src]
0x18002f94c  mov     rdx, r13; Src
0x18002f94f  call    memcpy_0
0x18002f954  mov     rcx, [rsi]; void *
0x18002f957  test    r12d, r12d
0x18002f95a  jz      short loc_18002F973
0x18002f95c  lea     rdx, [r14+r13]; Src
0x18002f960  mov     r8d, r12d; Size
0x18002f963  mov     ebx, r12d
0x18002f966  call    memcpy_0
0x18002f96b  mov     rcx, [rsi]
0x18002f96e  add     rcx, rbx
0x18002f971  jmp     short loc_18002F98C
0x18002f973  mov     eax, [rdi+88h]
0x18002f979  add     [rdi+98h], r14
0x18002f980  add     rax, rcx
0x18002f983  cmp     [rdi+98h], rax
0x18002f98a  jb      short loc_18002F993
0x18002f98c  mov     [rdi+98h], rcx
0x18002f993  mov     edx, [r13+0]
0x18002f997  mov     r8d, [rdi+8Ch]
0x18002f99e  add     edx, r8d
0x18002f9a1  mov     rax, [rdi+8]
0x18002f9a5  and     rax, 0FFFFFFFFFFFFFFFEh
0x18002f9a9  mov     [rdi+8Ch], edx
0x18002f9af  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18002f9b3  jz      short loc_18002F9E6
0x18002f9b5  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFDh
0x18002f9ba  jz      short loc_18002F9E6
0x18002f9bc  mov     r8, [rdi+80h]
0x18002f9c3  lea     rdx, aWriteeventbuff_0; "WriteEventBuffer: SetEvent %p for local"...
0x18002f9ca  mov     ecx, 80002h
0x18002f9cf  call    TRACELogPrint
0x18002f9d4  mov     rcx, [rdi+80h]; hEvent
0x18002f9db  call    cs:__imp_SetEvent
0x18002f9e1  jmp     loc_18002FAA5
0x18002f9e6  test    r8d, r8d
0x18002f9e9  jnz     loc_18002FAA5
0x18002f9ef  cmp     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18002f9f4  lea     rbx, [rdi+0E0h]
0x18002f9fb  jnz     short loc_18002FA3B
0x18002f9fd  lea     rcx, gCnClientMsgPendingCritSec; lpCriticalSection
0x18002fa04  call    cs:__imp_EnterCriticalSection
0x18002fa0a  mov     rax, cs:qword_180051CB8
0x18002fa11  lea     rdx, CnClientMsgPendingListHead
0x18002fa18  mov     [rbx], rdx
0x18002fa1b  lea     rcx, gCnClientMsgPendingCritSec; lpCriticalSection
0x18002fa22  mov     [rdi+0E8h], rax
0x18002fa29  mov     [rax], rbx
0x18002fa2c  mov     cs:qword_180051CB8, rbx
0x18002fa33  call    cs:__imp_LeaveCriticalSection
0x18002fa39  jmp     short loc_18002FAA0
0x18002fa3b  call    cs:__imp_GetTickCount
0x18002fa41  lea     rcx, gDgClientMsgPendingCritSec; lpCriticalSection
0x18002fa48  mov     [rdi+0F4h], eax
0x18002fa4e  call    cs:__imp_EnterCriticalSection
0x18002fa54  mov     rax, cs:qword_180051D58
0x18002fa5b  lea     rdx, DgClientMsgPendingListHead
0x18002fa62  mov     [rbx], rdx
0x18002fa65  lea     rcx, gDgClientMsgPendingCritSec; lpCriticalSection
0x18002fa6c  mov     [rdi+0E8h], rax
0x18002fa73  mov     [rax], rbx
0x18002fa76  mov     cs:qword_180051D58, rbx
0x18002fa7d  call    cs:__imp_LeaveCriticalSection
0x18002fa83  mov     rax, [rdi+0A8h]
0x18002fa8a  mov     r15, [rdi+80h]
0x18002fa91  test    rax, rax
0x18002fa94  jz      short loc_18002FA99
0x18002fa96  mov     eax, [rax+1Ch]
0x18002fa99  mov     [rsp+68h+Buffer], eax
0x18002faa0  mov     ebp, 1
0x18002faa5  mov     eax, cs:gdwPointerToLockTableIndexBits
0x18002faab  mov     rcx, rdi
0x18002faae  shr     rcx, 4
0x18002fab2  and     rcx, rax
0x18002fab5  mov     rax, cs:gLockTable
0x18002fabc  lea     rdx, [rcx+rcx*4]
0x18002fac0  lea     rcx, [rax+rdx*8]; lpCriticalSection
0x18002fac4  call    cs:__imp_LeaveCriticalSection
0x18002faca  test    ebp, ebp
0x18002facc  jz      loc_18002FB57
0x18002fad2  test    r15, r15
0x18002fad5  jz      short loc_18002FB37
0x18002fad7  lea     r9, [rsp+68h+Src]; lpNumberOfBytesWritten
0x18002fadc  mov     dword ptr [rsp+68h+Src], 0
0x18002fae4  mov     r8d, 4; nNumberOfBytesToWrite
0x18002faea  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x18002faf3  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x18002fafb  mov     rcx, r15; hFile
0x18002fafe  call    cs:__imp_WriteFile
0x18002fb04  test    eax, eax
0x18002fb06  jnz     short loc_18002FB24
0x18002fb08  call    cs:__imp_GetLastError
0x18002fb0e  lea     rdx, aWriteeventbuff; "WriteEventBuffer: Writefile(mailslot) f"...
0x18002fb15  mov     ecx, 10002h
0x18002fb1a  mov     r8d, eax
0x18002fb1d  call    TRACELogPrint
0x18002fb22  jmp     short loc_18002FB57
0x18002fb24  call    cs:__imp_GetTickCount
0x18002fb2a  add     eax, 7D0h
0x18002fb2f  mov     [rdi+0F0h], eax
0x18002fb35  jmp     short loc_18002FB57
0x18002fb37  mov     rcx, cs:hEvent; hEvent
0x18002fb3e  call    cs:__imp_SetEvent
0x18002fb44  jmp     short loc_18002FB57
0x18002fb46  lea     rdx, aWriteeventbuff_2; "WriteEventBuffer: - WaitForExclusiveCli"...
0x18002fb4d  mov     ecx, 10002h
0x18002fb52  call    TRACELogPrint
0x18002fb57  mov     rbx, [rsp+68h+arg_0]
0x18002fb5c  add     rsp, 30h
0x18002fb60  pop     r15
0x18002fb62  pop     r14
0x18002fb64  pop     r13
0x18002fb66  pop     r12
0x18002fb68  pop     rdi
0x18002fb69  pop     rsi
0x18002fb6a  pop     rbp
0x18002fb6b  retn
```
