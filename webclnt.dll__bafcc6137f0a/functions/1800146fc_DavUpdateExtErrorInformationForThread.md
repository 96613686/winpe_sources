# DavUpdateExtErrorInformationForThread

- ea: `0x1800146fc`
- end: `0x180014818`
- name: `DavUpdateExtErrorInformationForThread`
- size: `284`
- prototype: `__int64 __fastcall(HINTERNET hRequest, _DWORD *, __int64, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001456c`
- `0x18001507c`
- `0x18001ad0c`

## callees

- `0x18000b7dc`
- `0x180010c48`
- `0x1800114fc`
- `0x18001171c`
- `0x1800146fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800147ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800147ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001476c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001476c`
- `KERNEL32!LocalFree` at `0x180014806`
- `KERNEL32!LocalFree` at `0x180014806`

## pseudocode

```c
__int64 __fastcall DavUpdateExtErrorInformationForThread(
        HINTERNET hRequest,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5)
{
  unsigned int ExtErrorInfo; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12[6]; // [rsp+38h] [rbp-30h] BYREF

  hMem = 0;
  v12[0] = 0;
  if ( (unsigned int)DavGetFBAAuthRequiredExtErrorInfo(hRequest) )
  {
    ExtErrorInfo = DavGetExtErrorInfo(hRequest, &hMem);
    if ( ExtErrorInfo )
      goto LABEL_12;
    if ( hMem )
    {
      EnterCriticalSection(&HashExtErrorTableLock);
      ExtErrorInfo = DavFindOrCreateExtErrorEntry(a2, a3, a4, (__int64)hMem, 1, v12);
      if ( ExtErrorInfo )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            169,
            WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids,
            ExtErrorInfo);
      }
      else if ( a5 )
      {
        *a5 = *(_DWORD *)(v12[0] + 64);
      }
      LeaveCriticalSection(&HashExtErrorTableLock);
      if ( ExtErrorInfo )
      {
LABEL_12:
        if ( hMem )
          LocalFree(hMem);
      }
    }
    return ExtErrorInfo;
  }
  else
  {
    *a5 = 917656;
    return 0;
  }
}

```

## disassembly

```asm
0x1800146fc  push    rbx
0x1800146fe  push    rbp
0x1800146ff  push    rsi
0x180014700  push    r14
0x180014702  sub     rsp, 48h
0x180014706  mov     rsi, r9
0x180014709  mov     [rsp+68h+hMem], 0
0x180014712  mov     rbp, r8
0x180014715  mov     [rsp+68h+var_30], 0
0x18001471e  mov     r14, rdx
0x180014721  mov     rbx, rcx
0x180014724  call    DavGetFBAAuthRequiredExtErrorInfo
0x180014729  test    eax, eax
0x18001472b  jnz     short loc_180014742
0x18001472d  mov     rax, [rsp+68h+arg_20]
0x180014735  mov     dword ptr [rax], 0E0098h
0x18001473b  xor     eax, eax
0x18001473d  jmp     loc_18001480E
0x180014742  lea     rdx, [rsp+68h+hMem]
0x180014747  mov     rcx, rbx; hRequest
0x18001474a  call    DavGetExtErrorInfo
0x18001474f  mov     ebx, eax
0x180014751  test    eax, eax
0x180014753  jnz     loc_1800147F9
0x180014759  cmp     [rsp+68h+hMem], 0
0x18001475f  jz      loc_18001480C
0x180014765  lea     rcx, HashExtErrorTableLock; lpCriticalSection
0x18001476c  call    cs:__imp_EnterCriticalSection
0x180014772  mov     r9, [rsp+68h+hMem]
0x180014777  lea     rax, [rsp+68h+var_30]
0x18001477c  mov     [rsp+68h+var_40], rax
0x180014781  mov     r8, rsi
0x180014784  mov     rdx, rbp
0x180014787  mov     [rsp+68h+var_48], 1
0x18001478f  mov     rcx, r14
0x180014792  call    DavFindOrCreateExtErrorEntry
0x180014797  mov     ebx, eax
0x180014799  test    eax, eax
0x18001479b  jz      short loc_1800147D0
0x18001479d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147a4  lea     rax, WPP_GLOBAL_Control
0x1800147ab  cmp     rcx, rax
0x1800147ae  jz      short loc_1800147E8
0x1800147b0  test    byte ptr [rcx+1Ch], 1
0x1800147b4  jz      short loc_1800147E8
0x1800147b6  mov     rcx, [rcx+10h]
0x1800147ba  lea     r8, WPP_448ddb41b5843cea4b9dc965d1aba9af_Traceguids
0x1800147c1  mov     edx, 0A9h
0x1800147c6  mov     r9d, ebx
0x1800147c9  call    WPP_SF_d
0x1800147ce  jmp     short loc_1800147E8
0x1800147d0  mov     r8, [rsp+68h+arg_20]
0x1800147d8  test    r8, r8
0x1800147db  jz      short loc_1800147E8
0x1800147dd  mov     rax, [rsp+68h+var_30]
0x1800147e2  mov     edx, [rax+40h]
0x1800147e5  mov     [r8], edx
0x1800147e8  lea     rcx, HashExtErrorTableLock; lpCriticalSection
0x1800147ef  call    cs:__imp_LeaveCriticalSection
0x1800147f5  test    ebx, ebx
0x1800147f7  jz      short loc_18001480C
0x1800147f9  cmp     [rsp+68h+hMem], 0
0x1800147ff  jz      short loc_18001480C
0x180014801  mov     rcx, [rsp+68h+hMem]; hMem
0x180014806  call    cs:__imp_LocalFree
0x18001480c  mov     eax, ebx
0x18001480e  add     rsp, 48h
0x180014812  pop     r14
0x180014814  pop     rsi
0x180014815  pop     rbp
0x180014816  pop     rbx
0x180014817  retn
```
