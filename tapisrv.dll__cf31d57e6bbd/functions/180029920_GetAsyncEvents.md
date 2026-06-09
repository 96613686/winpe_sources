# GetAsyncEvents

- ea: `0x180029920`
- end: `0x180029d00`
- name: `GetAsyncEvents`
- size: `992`
- prototype: `void __fastcall(unsigned __int64, __int64, unsigned int, char *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180028100`

## callees

- `0x18001f494`
- `0x180029920`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180029bf1`
- `KERNEL32!ResetEvent` at `0x180029c42`
- `KERNEL32!ResetEvent` at `0x180029bf1`
- `KERNEL32!ResetEvent` at `0x180029c42`
- `KERNEL32!GetTickCount` at `0x180029cb6`
- `KERNEL32!GetTickCount` at `0x180029cb6`
- `KERNEL32!GetCurrentThreadId` at `0x18002993d`
- `KERNEL32!GetCurrentThreadId` at `0x18002993d`
- `KERNEL32!LeaveCriticalSection` at `0x180029cae`
- `KERNEL32!LeaveCriticalSection` at `0x180029ce9`
- `KERNEL32!LeaveCriticalSection` at `0x180029cae`
- `KERNEL32!LeaveCriticalSection` at `0x180029ce9`
- `KERNEL32!EnterCriticalSection` at `0x180029c7e`
- `KERNEL32!EnterCriticalSection` at `0x180029c7e`

## pseudocode

```c
void __fastcall GetAsyncEvents(unsigned __int64 a1, __int64 a2, unsigned int a3, char *a4, _DWORD *a5)
{
  DWORD CurrentThreadId; // eax
  __int64 v10; // r12
  unsigned int v11; // ecx
  const void *v12; // rdx
  int v13; // ebx
  unsigned int v14; // ebp
  unsigned int v15; // ebx
  unsigned int v16; // r15d
  unsigned int v17; // edi
  unsigned int *v18; // rdx
  __int64 v19; // rbx
  char *v20; // rcx
  int v21; // edx
  unsigned int v22; // r8d
  unsigned int *v23; // rcx
  unsigned int v24; // edi
  __int64 v25; // rbx
  unsigned int i; // ebx
  __int64 v27; // rax
  unsigned __int64 v28; // rax
  _QWORD *v29; // rax
  __int64 v30; // rdx
  DWORD TickCount; // eax
  unsigned int v32; // [rsp+90h] [rbp+18h]

  CurrentThreadId = GetCurrentThreadId();
  TRACELogPrint(524290, "GetAsyncEvents: enter (TID=%d)", CurrentThreadId);
  TRACELogPrint(
    262146,
    "M ebfused:x%lx  pEvtBuf: 0x%p  pDataOut:0x%p  pDataIn:0x%p",
    *(_DWORD *)(a1 + 140),
    *(const void **)(a1 + 144),
    *(const void **)(a1 + 160),
    *(const void **)(a1 + 152));
  if ( *(_DWORD *)(a2 + 8) > a3 )
  {
    *(_DWORD *)a2 = -2147483576;
    return;
  }
  LODWORD(v10) = 0;
  if ( WaitForExclusiveClientAccess(a1) )
  {
    while ( 1 )
    {
      v11 = *(_DWORD *)(a1 + 140);
      if ( !v11 )
      {
        if ( (*(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFFFEuLL) != 0xFFFFFFFFFFFFFFFEuLL && *(_QWORD *)(a1 + 8) != -3 )
          ResetEvent(*(HANDLE *)(a1 + 128));
        *(_QWORD *)(a2 + 12) = 0;
        *a5 = 60;
        *(_DWORD *)(a1 + 216) &= ~2u;
        goto LABEL_39;
      }
      v12 = *(const void **)(a1 + 160);
      v13 = *(_DWORD *)(a1 + 152);
      if ( (unsigned __int64)v12 >= *(_QWORD *)(a1 + 152) )
      {
        v14 = *(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 144) - (_DWORD)v12;
        v15 = v13 - *(_DWORD *)(a1 + 144);
      }
      else
      {
        v14 = v13 - (_DWORD)v12;
        v15 = 0;
      }
      v16 = *(_DWORD *)(a2 + 8);
      if ( v11 <= v16 )
      {
        memcpy_0(a4, v12, v14);
        if ( v15 )
          memcpy_0(&a4[v14], *(const void **)(a1 + 144), v15);
        v27 = *(_QWORD *)(a1 + 144);
        *(_DWORD *)(a1 + 216) &= ~2u;
        *(_QWORD *)(a1 + 152) = v27;
        *(_QWORD *)(a1 + 160) = v27;
        v28 = *(_QWORD *)(a1 + 8) & 0xFFFFFFFFFFFFFFFEuLL;
        *(_DWORD *)(a1 + 140) = 0;
        if ( v28 != -2 && *(_QWORD *)(a1 + 8) != -3 )
          ResetEvent(*(HANDLE *)(a1 + 128));
        *(_DWORD *)(a2 + 16) = v15 + v14;
        *(_DWORD *)(a2 + 12) = v15 + v14;
        *a5 = v15 + v14 + 60;
        TRACELogPrint(524290, "GetAsyncEvents: return dwUsedBufferSize:x%lx", *(_DWORD *)(a2 + 16));
        goto LABEL_39;
      }
      v32 = v14;
      v17 = 0;
      TRACELogPrint(524290, "GetAsyncEvents: event data exceeds client buffer", (unsigned int)v12);
      *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 140);
      while ( 1 )
      {
        v18 = (unsigned int *)(v17 + *(_QWORD *)(a1 + 160));
        v19 = *v18;
        if ( (unsigned int)v19 > v16 )
          break;
        v16 -= v19;
        v20 = &a4[v17];
        if ( (unsigned int)v19 > v14 )
        {
          memcpy_0(v20, v18, v14);
          v24 = v14 + v17;
          v25 = (unsigned int)v19 - v14;
          memcpy_0(&a4[v24], *(const void **)(a1 + 144), (unsigned int)v25);
          v17 = v25 + v24;
          v23 = (unsigned int *)(v25 + *(_QWORD *)(a1 + 144));
          goto LABEL_22;
        }
        memcpy_0(v20, v18, (unsigned int)v19);
        v17 += v19;
        if ( v17 >= v32 )
        {
          v23 = *(unsigned int **)(a1 + 144);
LABEL_22:
          *(_QWORD *)(a1 + 160) = v23;
          for ( i = *v23; i <= v16; i = *(unsigned int *)((char *)v23 + v10) )
          {
            memcpy_0(&a4[v17], (char *)v23 + (unsigned int)v10, i);
            v23 = *(unsigned int **)(a1 + 160);
            v10 = i + (unsigned int)v10;
            v17 += i;
            v16 -= i;
          }
          *(_DWORD *)(a1 + 140) -= v17;
          *(_QWORD *)(a1 + 160) = (char *)v23 + (unsigned int)v10;
          *(_DWORD *)(a2 + 16) = v17;
          *a5 = v17 + 60;
LABEL_39:
          if ( *(_QWORD *)(a1 + 224) )
          {
            if ( *(_DWORD *)(a1 + 140) )
            {
              TickCount = GetTickCount();
              *(_DWORD *)(a1 + 244) = TickCount;
              *(_DWORD *)(a1 + 240) = TickCount + 3000;
            }
            else
            {
              EnterCriticalSection(&gDgClientMsgPendingCritSec);
              v29 = *(_QWORD **)(a1 + 232);
              v30 = *(_QWORD *)(a1 + 224);
              *v29 = v30;
              *(_QWORD *)(v30 + 8) = v29;
              *(_QWORD *)(a1 + 232) = 0;
              *(_QWORD *)(a1 + 224) = 0;
              LeaveCriticalSection(&gDgClientMsgPendingCritSec);
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)gLockTable + ((unsigned int)gdwPointerToLockTableIndexBits & (a1 >> 4)));
          return;
        }
        v14 -= v19;
      }
      LODWORD(v10) = 0;
      *(_DWORD *)(a2 + 16) = v17;
      if ( v17 )
        break;
      v21 = *(_DWORD *)(a1 + 216);
      if ( (v21 & 2) == 0 )
      {
        *(_DWORD *)(a1 + 216) = v21 | 2;
LABEL_28:
        *a5 = *(_DWORD *)(a2 + 16) + 60;
        goto LABEL_39;
      }
      v22 = *(_DWORD *)(a1 + 136) + *(_DWORD *)(a1 + 144) - *(_DWORD *)(a1 + 160);
      *(_DWORD *)(a1 + 216) = v21 & 0xFFFFFFFD;
      if ( (unsigned int)v19 <= v22 )
        *(_QWORD *)(a1 + 160) += v19;
      else
        *(_QWORD *)(a1 + 160) = *(_QWORD *)(a1 + 144) + (unsigned int)v19 - v22;
      *(_DWORD *)(a1 + 140) -= v19;
    }
    *(_DWORD *)(a1 + 140) -= v17;
    *(_QWORD *)(a1 + 160) += v17;
    goto LABEL_28;
  }
}

```

## disassembly

```asm
0x180029920  push    rbx
0x180029922  push    rbp
0x180029923  push    rsi
0x180029924  push    rdi
0x180029925  push    r12
0x180029927  push    r13
0x180029929  push    r14
0x18002992b  push    r15
0x18002992d  sub     rsp, 38h
0x180029931  mov     r13, r9
0x180029934  mov     ebx, r8d
0x180029937  mov     r14, rdx
0x18002993a  mov     rsi, rcx
0x18002993d  call    cs:__imp_GetCurrentThreadId
0x180029943  lea     rdx, aGetasyncevents; "GetAsyncEvents: enter (TID=%d)"
0x18002994a  mov     ecx, 80002h
0x18002994f  mov     r8d, eax
0x180029952  call    TRACELogPrint
0x180029957  mov     rax, [rsi+98h]
0x18002995e  lea     rdx, aMEbfusedXLxPev; "M ebfused:x%lx  pEvtBuf: 0x%p  pDataOut"...
0x180029965  mov     r9, [rsi+90h]
0x18002996c  mov     ecx, 40002h
0x180029971  mov     r8d, [rsi+8Ch]
0x180029978  mov     [rsp+78h+var_50], rax
0x18002997d  mov     rax, [rsi+0A0h]
0x180029984  mov     [rsp+78h+var_58], rax
0x180029989  call    TRACELogPrint
0x18002998e  cmp     [r14+8], ebx
0x180029992  jbe     short loc_1800299A0
0x180029994  mov     dword ptr [r14], 80000048h
0x18002999b  jmp     loc_180029CEF
0x1800299a0  mov     rcx, rsi
0x1800299a3  call    WaitForExclusiveClientAccess
0x1800299a8  xor     r12d, r12d
0x1800299ab  test    rax, rax
0x1800299ae  jz      loc_180029CEF
0x1800299b4  mov     ecx, [rsi+8Ch]
0x1800299ba  test    ecx, ecx
0x1800299bc  jz      loc_180029C26
0x1800299c2  mov     rdx, [rsi+0A0h]; Src
0x1800299c9  mov     r8d, edx
0x1800299cc  mov     ebx, [rsi+98h]
0x1800299d2  cmp     rdx, [rsi+98h]
0x1800299d9  jnb     short loc_1800299E4
0x1800299db  sub     ebx, edx
0x1800299dd  mov     ebp, ebx
0x1800299df  mov     ebx, r12d
0x1800299e2  jmp     short loc_1800299F7
0x1800299e4  mov     eax, [rsi+90h]
0x1800299ea  mov     ebp, eax
0x1800299ec  sub     ebp, r8d
0x1800299ef  add     ebp, [rsi+88h]
0x1800299f5  sub     ebx, eax
0x1800299f7  mov     r15d, [r14+8]
0x1800299fb  cmp     ecx, r15d
0x1800299fe  jbe     loc_180029B8E
0x180029a04  lea     rdx, aGetasyncevents_1; "GetAsyncEvents: event data exceeds clie"...
0x180029a0b  mov     [rsp+78h+arg_10], ebp
0x180029a12  mov     ecx, 80002h
0x180029a17  mov     edi, r12d
0x180029a1a  call    TRACELogPrint
0x180029a1f  mov     eax, [rsi+8Ch]
0x180029a25  mov     [r14+0Ch], eax
0x180029a29  mov     rdx, [rsi+0A0h]
0x180029a30  mov     ecx, edi
0x180029a32  add     rdx, rcx; Src
0x180029a35  mov     ebx, [rdx]
0x180029a37  cmp     ebx, r15d
0x180029a3a  ja      short loc_180029A61
0x180029a3c  sub     r15d, ebx
0x180029a3f  add     rcx, r13; void *
0x180029a42  cmp     ebx, ebp
0x180029a44  ja      loc_180029AD2
0x180029a4a  mov     r8d, ebx; Size
0x180029a4d  call    memcpy_0
0x180029a52  add     edi, ebx
0x180029a54  cmp     edi, [rsp+78h+arg_10]
0x180029a5b  jnb     short loc_180029AC9
0x180029a5d  sub     ebp, ebx
0x180029a5f  jmp     short loc_180029A29
0x180029a61  xor     r12d, r12d
0x180029a64  mov     [r14+10h], edi
0x180029a68  test    edi, edi
0x180029a6a  jnz     loc_180029B6B
0x180029a70  mov     edx, [rsi+0D8h]
0x180029a76  test    dl, 2
0x180029a79  jz      loc_180029B60
0x180029a7f  mov     r8d, [rsi+90h]
0x180029a86  and     edx, 0FFFFFFFDh
0x180029a89  sub     r8d, [rsi+0A0h]
0x180029a90  add     r8d, [rsi+88h]
0x180029a97  mov     [rsi+0D8h], edx
0x180029a9d  cmp     ebx, r8d
0x180029aa0  jbe     short loc_180029AB7
0x180029aa2  mov     ecx, ebx
0x180029aa4  sub     ecx, r8d
0x180029aa7  add     rcx, [rsi+90h]
0x180029aae  mov     [rsi+0A0h], rcx
0x180029ab5  jmp     short loc_180029ABE
0x180029ab7  add     [rsi+0A0h], rbx
0x180029abe  sub     [rsi+8Ch], ebx
0x180029ac4  jmp     loc_1800299B4
0x180029ac9  mov     rcx, [rsi+90h]
0x180029ad0  jmp     short loc_180029AFE
0x180029ad2  mov     r8d, ebp; Size
0x180029ad5  call    memcpy_0
0x180029ada  mov     rdx, [rsi+90h]; Src
0x180029ae1  add     edi, ebp
0x180029ae3  mov     ecx, edi
0x180029ae5  sub     ebx, ebp
0x180029ae7  add     rcx, r13; void *
0x180029aea  mov     r8d, ebx; Size
0x180029aed  call    memcpy_0
0x180029af2  mov     rcx, [rsi+90h]
0x180029af9  add     edi, ebx
0x180029afb  add     rcx, rbx
0x180029afe  mov     [rsi+0A0h], rcx
0x180029b05  mov     ebx, [rcx]
0x180029b07  jmp     short loc_180029B2F
0x180029b09  mov     edx, r12d
0x180029b0c  add     rdx, rcx; Src
0x180029b0f  mov     r8d, ebx; Size
0x180029b12  mov     ecx, edi
0x180029b14  add     rcx, r13; void *
0x180029b17  call    memcpy_0
0x180029b1c  mov     rcx, [rsi+0A0h]
0x180029b23  add     r12d, ebx
0x180029b26  add     edi, ebx
0x180029b28  sub     r15d, ebx
0x180029b2b  mov     ebx, [r12+rcx]
0x180029b2f  cmp     ebx, r15d
0x180029b32  jbe     short loc_180029B09
0x180029b34  sub     [rsi+8Ch], edi
0x180029b3a  mov     eax, r12d
0x180029b3d  add     rax, rcx
0x180029b40  lea     ecx, [rdi+3Ch]
0x180029b43  mov     [rsi+0A0h], rax
0x180029b4a  xor     r12d, r12d
0x180029b4d  mov     rax, [rsp+78h+arg_20]
0x180029b55  mov     [r14+10h], edi
0x180029b59  mov     [rax], ecx
0x180029b5b  jmp     loc_180029C65
0x180029b60  or      edx, 2
0x180029b63  mov     [rsi+0D8h], edx
0x180029b69  jmp     short loc_180029B78
0x180029b6b  sub     [rsi+8Ch], edi
0x180029b71  add     [rsi+0A0h], rcx
0x180029b78  mov     ecx, [r14+10h]
0x180029b7c  mov     rax, [rsp+78h+arg_20]
0x180029b84  add     ecx, 3Ch ; '<'
0x180029b87  mov     [rax], ecx
0x180029b89  jmp     loc_180029C65
0x180029b8e  mov     r8d, ebp; Size
0x180029b91  mov     rcx, r13; void *
0x180029b94  mov     edi, ebp
0x180029b96  call    memcpy_0
0x180029b9b  test    ebx, ebx
0x180029b9d  jz      short loc_180029BB2
0x180029b9f  mov     rdx, [rsi+90h]; Src
0x180029ba6  lea     rcx, [rdi+r13]; void *
0x180029baa  mov     r8d, ebx; Size
0x180029bad  call    memcpy_0
0x180029bb2  mov     rax, [rsi+90h]
0x180029bb9  and     dword ptr [rsi+0D8h], 0FFFFFFFDh
0x180029bc0  mov     [rsi+98h], rax
0x180029bc7  mov     [rsi+0A0h], rax
0x180029bce  mov     rax, [rsi+8]
0x180029bd2  and     rax, 0FFFFFFFFFFFFFFFEh
0x180029bd6  mov     [rsi+8Ch], r12d
0x180029bdd  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x180029be1  jz      short loc_180029BF7
0x180029be3  cmp     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFDh
0x180029be8  jz      short loc_180029BF7
0x180029bea  mov     rcx, [rsi+80h]; hEvent
0x180029bf1  call    cs:__imp_ResetEvent
0x180029bf7  mov     rax, [rsp+78h+arg_20]
0x180029bff  lea     edx, [rbx+rbp]
0x180029c02  mov     [r14+10h], edx
0x180029c06  mov     ecx, 80002h
0x180029c0b  mov     [r14+0Ch], edx
0x180029c0f  add     edx, 3Ch ; '<'
0x180029c12  mov     [rax], edx
0x180029c14  lea     rdx, aGetasyncevents_0; "GetAsyncEvents: return dwUsedBufferSize"...
0x180029c1b  mov     r8d, [r14+10h]
0x180029c1f  call    TRACELogPrint
0x180029c24  jmp     short loc_180029C65
0x180029c26  mov     rax, [rsi+8]
0x180029c2a  and     rax, 0FFFFFFFFFFFFFFFEh
0x180029c2e  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x180029c32  jz      short loc_180029C48
0x180029c34  cmp     qword ptr [rsi+8], 0FFFFFFFFFFFFFFFDh
0x180029c39  jz      short loc_180029C48
0x180029c3b  mov     rcx, [rsi+80h]; hEvent
0x180029c42  call    cs:__imp_ResetEvent
0x180029c48  mov     rax, [rsp+78h+arg_20]
0x180029c50  mov     qword ptr [r14+0Ch], 0
0x180029c58  mov     dword ptr [rax], 3Ch ; '<'
0x180029c5e  and     dword ptr [rsi+0D8h], 0FFFFFFFDh
0x180029c65  cmp     [rsi+0E0h], r12
0x180029c6c  jz      short loc_180029CCD
0x180029c6e  cmp     [rsi+8Ch], r12d
0x180029c75  jnz     short loc_180029CB6
0x180029c77  lea     rcx, gDgClientMsgPendingCritSec; lpCriticalSection
0x180029c7e  call    cs:__imp_EnterCriticalSection
0x180029c84  mov     rax, [rsi+0E8h]
0x180029c8b  lea     rcx, gDgClientMsgPendingCritSec; lpCriticalSection
0x180029c92  mov     rdx, [rsi+0E0h]
0x180029c99  mov     [rax], rdx
0x180029c9c  mov     [rdx+8], rax
0x180029ca0  mov     [rsi+0E8h], r12
0x180029ca7  mov     [rsi+0E0h], r12
0x180029cae  call    cs:__imp_LeaveCriticalSection
0x180029cb4  jmp     short loc_180029CCD
0x180029cb6  call    cs:__imp_GetTickCount
0x180029cbc  mov     [rsi+0F4h], eax
0x180029cc2  add     eax, 0BB8h
0x180029cc7  mov     [rsi+0F0h], eax
0x180029ccd  mov     eax, cs:gdwPointerToLockTableIndexBits
0x180029cd3  shr     rsi, 4
0x180029cd7  and     rsi, rax
0x180029cda  mov     rax, cs:gLockTable
0x180029ce1  lea     rcx, [rsi+rsi*4]
0x180029ce5  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180029ce9  call    cs:__imp_LeaveCriticalSection
0x180029cef  add     rsp, 38h
0x180029cf3  pop     r15
0x180029cf5  pop     r14
0x180029cf7  pop     r13
0x180029cf9  pop     r12
0x180029cfb  pop     rdi
0x180029cfc  pop     rsi
0x180029cfd  pop     rbp
0x180029cfe  pop     rbx
0x180029cff  retn
```
