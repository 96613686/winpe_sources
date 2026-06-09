# DavRestartContext

- ea: `0x18000ca80`
- end: `0x18000cc7e`
- name: `DavRestartContext`
- size: `510`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b89c`
- `0x18000ca80`
- `0x18000d910`
- `0x18000d974`
- `0x180028440`
- `0x180028f90`
- `0x180029000`
- `0x180029654`
- `0x1800296e8`
- `0x18002e010`

## import_xrefs

- `ntdll!NtClose` at `0x18000cbcb`
- `ntdll!NtClose` at `0x18000cbcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ca92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ca92`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc38`

## pseudocode

```c
void __fastcall DavRestartContext(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  __int64 (__fastcall *v2)(PVOID); // rbx
  DWORD CurrentThreadId; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // eax
  __int64 v8; // r8
  int v9; // r14d
  DWORD v10; // r14d
  __int64 v11; // rbx
  DWORD v12; // eax
  int v13; // edi
  __int64 v14; // rbx
  DWORD v15; // eax
  __int64 v16; // rbx
  DWORD v17; // eax
  void **v18; // [rsp+78h] [rbp+10h] BYREF

  v2 = (__int64 (__fastcall *)(PVOID))*((_QWORD *)Context + 8);
  CurrentThreadId = GetCurrentThreadId();
  *((_DWORD *)Context + 121) = CurrentThreadId;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_qdD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, Context, *((_DWORD *)Context + 12), CurrentThreadId);
  v7 = v2(Context);
  if ( v7
    && v7 != 997
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_qdqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, v2, v7, Context, *((_DWORD *)Context + 12));
  }
  v18 = 0;
  v9 = UMReflectorOpenWorker(DavReflectorHandle, &v18);
  if ( !v9 )
  {
    if ( v18 )
    {
      v10 = UMReflectorSendResponse((__int64)v18, (DWORD *)Context);
      if ( v10
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v12 = GetCurrentThreadId();
        WPP_SF_Dd(v11, 20, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids, v12, v10);
      }
      if ( *((_DWORD *)Context + 6) )
      {
        if ( *((_DWORD *)Context + 12) )
        {
          if ( *((_DWORD *)Context + 12) == 2 )
          {
            DavFinalizeFileAttributesList(*((HLOCAL *)Context + 289));
            *((_QWORD *)Context + 289) = 0;
          }
        }
        else
        {
          NtClose(*((HANDLE *)Context + 682));
          *((_QWORD *)Context + 682) = 0;
        }
      }
      v13 = UMReflectorCompleteWorkItem(v18, Context);
      if ( v13
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v15 = GetCurrentThreadId();
        WPP_SF_Dd(v14, 21, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids, v15, v13);
      }
      goto LABEL_28;
    }
    v9 = 1359;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    v16 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v17 = GetCurrentThreadId();
    WPP_SF_Dd(v16, 19, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids, v17, v9);
  }
LABEL_28:
  if ( v18 )
    UMReflectorCloseWorker(v18);
  _InterlockedDecrement(&DavOutstandingWorkerRequests);
}

```

## disassembly

```asm
0x18000ca80  push    rbx
0x18000ca82  push    rdi
0x18000ca83  push    r12
0x18000ca85  push    r14
0x18000ca87  sub     rsp, 48h
0x18000ca8b  mov     rbx, [rdx+40h]
0x18000ca8f  mov     rdi, rdx
0x18000ca92  call    cs:__imp_GetCurrentThreadId
0x18000ca98  mov     [rdi+1E4h], eax
0x18000ca9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caa5  lea     r12, WPP_GLOBAL_Control
0x18000caac  cmp     rcx, r12
0x18000caaf  jz      short loc_18000CACE
0x18000cab1  test    byte ptr [rcx+1Ch], 2
0x18000cab5  jz      short loc_18000CACE
0x18000cab7  mov     rcx, [rcx+10h]
0x18000cabb  mov     r9, rdi
0x18000cabe  mov     dword ptr [rsp+68h+var_40], eax
0x18000cac2  mov     eax, [rdi+30h]
0x18000cac5  mov     [rsp+68h+var_48], eax
0x18000cac9  call    WPP_SF_qdD
0x18000cace  mov     rcx, rdi
0x18000cad1  mov     rax, rbx
0x18000cad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cad9  mov     edx, eax
0x18000cadb  test    eax, eax
0x18000cadd  jz      short loc_18000CB14
0x18000cadf  cmp     eax, 3E5h
0x18000cae4  jz      short loc_18000CB14
0x18000cae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000caed  cmp     rcx, r12
0x18000caf0  jz      short loc_18000CB14
0x18000caf2  test    byte ptr [rcx+1Ch], 2
0x18000caf6  jz      short loc_18000CB14
0x18000caf8  mov     eax, [rdi+30h]
0x18000cafb  mov     r9, rbx
0x18000cafe  mov     rcx, [rcx+10h]
0x18000cb02  mov     [rsp+68h+var_38], eax
0x18000cb06  mov     [rsp+68h+var_40], rdi
0x18000cb0b  mov     [rsp+68h+var_48], edx
0x18000cb0f  call    WPP_SF_qdqd
0x18000cb14  mov     rcx, cs:DavReflectorHandle
0x18000cb1b  lea     rdx, [rsp+68h+arg_8]
0x18000cb20  mov     [rsp+68h+arg_8], 0
0x18000cb29  call    UMReflectorOpenWorker
0x18000cb2e  mov     r14d, eax
0x18000cb31  test    eax, eax
0x18000cb33  jnz     loc_18000CC1F
0x18000cb39  cmp     [rsp+68h+arg_8], 0
0x18000cb3f  jz      loc_18000CC19
0x18000cb45  mov     rcx, [rsp+68h+arg_8]
0x18000cb4a  mov     rdx, rdi
0x18000cb4d  call    UMReflectorSendResponse
0x18000cb52  mov     r14d, eax
0x18000cb55  test    eax, eax
0x18000cb57  jz      short loc_18000CB94
0x18000cb59  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cb60  cmp     rbx, r12
0x18000cb63  jz      short loc_18000CB94
0x18000cb65  test    dword ptr [rbx+1Ch], 1000h
0x18000cb6c  jz      short loc_18000CB94
0x18000cb6e  mov     rbx, [rbx+10h]
0x18000cb72  call    cs:__imp_GetCurrentThreadId
0x18000cb78  mov     edx, 14h
0x18000cb7d  mov     [rsp+68h+var_48], r14d
0x18000cb82  mov     r9d, eax
0x18000cb85  lea     r8, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids
0x18000cb8c  mov     rcx, rbx
0x18000cb8f  call    WPP_SF_Dd
0x18000cb94  cmp     dword ptr [rdi+18h], 0
0x18000cb98  jz      short loc_18000CBDC
0x18000cb9a  cmp     dword ptr [rdi+30h], 0
0x18000cb9e  jz      short loc_18000CBC4
0x18000cba0  cmp     dword ptr [rdi+30h], 2
0x18000cba4  jnz     short loc_18000CBDC
0x18000cba6  mov     rcx, [rdi+908h]; hMem
0x18000cbad  mov     edx, 1
0x18000cbb2  call    DavFinalizeFileAttributesList
0x18000cbb7  mov     qword ptr [rdi+908h], 0
0x18000cbc2  jmp     short loc_18000CBDC
0x18000cbc4  mov     rcx, [rdi+1550h]; Handle
0x18000cbcb  call    cs:__imp_NtClose
0x18000cbd1  mov     qword ptr [rdi+1550h], 0
0x18000cbdc  mov     rcx, [rsp+68h+arg_8]
0x18000cbe1  mov     rdx, rdi
0x18000cbe4  call    UMReflectorCompleteWorkItem
0x18000cbe9  mov     edi, eax
0x18000cbeb  test    eax, eax
0x18000cbed  jz      short loc_18000CC5A
0x18000cbef  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cbf6  cmp     rbx, r12
0x18000cbf9  jz      short loc_18000CC5A
0x18000cbfb  test    dword ptr [rbx+1Ch], 1000h
0x18000cc02  jz      short loc_18000CC5A
0x18000cc04  mov     rbx, [rbx+10h]
0x18000cc08  call    cs:__imp_GetCurrentThreadId
0x18000cc0e  mov     edx, 15h
0x18000cc13  mov     [rsp+68h+var_48], edi
0x18000cc17  jmp     short loc_18000CC48
0x18000cc19  mov     r14d, 54Fh
0x18000cc1f  mov     rbx, cs:WPP_GLOBAL_Control
0x18000cc26  cmp     rbx, r12
0x18000cc29  jz      short loc_18000CC5A
0x18000cc2b  test    dword ptr [rbx+1Ch], 1000h
0x18000cc32  jz      short loc_18000CC5A
0x18000cc34  mov     rbx, [rbx+10h]
0x18000cc38  call    cs:__imp_GetCurrentThreadId
0x18000cc3e  mov     edx, 13h
0x18000cc43  mov     [rsp+68h+var_48], r14d
0x18000cc48  mov     r9d, eax
0x18000cc4b  lea     r8, WPP_788794445e0d336c1137d10bf28c55d3_Traceguids
0x18000cc52  mov     rcx, rbx
0x18000cc55  call    WPP_SF_Dd
0x18000cc5a  cmp     [rsp+68h+arg_8], 0
0x18000cc60  jz      short loc_18000CC6C
0x18000cc62  mov     rcx, [rsp+68h+arg_8]
0x18000cc67  call    UMReflectorCloseWorker
0x18000cc6c  lock dec cs:DavOutstandingWorkerRequests
0x18000cc73  add     rsp, 48h
0x18000cc77  pop     r14
0x18000cc79  pop     r12
0x18000cc7b  pop     rdi
0x18000cc7c  pop     rbx
0x18000cc7d  retn
```
