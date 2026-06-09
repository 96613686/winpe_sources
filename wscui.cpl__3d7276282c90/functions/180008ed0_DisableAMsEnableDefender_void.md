# DisableAMsEnableDefender(void)

- ea: `0x180008ed0`
- end: `0x1800090af`
- name: `?DisableAMsEnableDefender@@YAJXZ`
- size: `479`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180008030`
- `0x180008170`
- `0x1800081c4`
- `0x180008ed0`
- `0x180009ac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008fd1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009030`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008fd1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009030`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008fc0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000901c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180008fc0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000901c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000907f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000907f`
- `WSCAPI!wscAntiVirusGetStatus` at `0x180008efa`
- `WSCAPI!wscAntiVirusGetStatus` at `0x180008efa`
- `WSCAPI!wscProductInfoFree` at `0x180009089`
- `WSCAPI!wscProductInfoFree` at `0x180009096`
- `WSCAPI!wscProductInfoFree` at `0x180009089`
- `WSCAPI!wscProductInfoFree` at `0x180009096`
- `USER32!LoadCursorW` at `0x180008f8b`
- `USER32!LoadCursorW` at `0x180008f8b`
- `USER32!SetCursor` at `0x180008f97`
- `USER32!SetCursor` at `0x180008fe5`
- `USER32!SetCursor` at `0x180008f97`
- `USER32!SetCursor` at `0x180008fe5`
- `USER32!DestroyCursor` at `0x180008fdc`
- `USER32!DestroyCursor` at `0x180008fdc`

## pseudocode

```c
__int64 __fastcall DisableAMsEnableDefender(PVOID Parameter)
{
  unsigned int v1; // ebx
  HANDLE v2; // r15
  __int64 v3; // rax
  unsigned int v4; // ebx
  HCURSOR CursorW; // r14
  HCURSOR v6; // rsi
  HANDLE v7; // rdi
  DWORD v8; // ebx
  unsigned int Parametera; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v11; // [rsp+68h] [rbp+38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+40h] BYREF

  v12 = 0;
  v11 = 0;
  if ( (unsigned int)wscAntiVirusGetStatus(&v11, &v12) )
  {
    v1 = -2147023834;
  }
  else
  {
    v2 = 0;
    Parametera = 0;
    if ( v11 )
    {
      v3 = 0;
      do
      {
        v4 = *(_DWORD *)(v12 + 80 * v3);
        if ( ((unsigned int)ExtractProductOwner(v4) == 256 || (v4 & 0x40000) != 0)
          && (unsigned int)ExtractProductState(*(unsigned int *)(v12 + 80LL * Parametera)) == 0x4000 )
        {
          if ( !(unsigned int)LaunchThirdPartyRemediationExe(
                                *(LPCWSTR *)(v12 + 80LL * Parametera + 16),
                                (const unsigned __int16 *)(10LL * Parametera))
            || (CursorW = LoadCursorW(0, (LPCWSTR)0x7F02),
                v6 = SetCursor(CursorW),
                v7 = CreateThread(0, 0, PollForAMOff, &Parametera, 0, 0),
                v8 = WaitForSingleObject(v7, 0x2710u),
                DestroyCursor(CursorW),
                SetCursor(v6),
                CloseHandle(v7),
                v8 == 258) )
          {
            v2 = CreateThread(0, 0, HandleDisableFailure, &Parametera, 0, 0);
          }
          if ( v2 )
            WaitForSingleObject(v2, 0xFFFFFFFF);
        }
        v3 = Parametera + 1;
        Parametera = v3;
      }
      while ( (unsigned int)v3 < v11 );
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids);
    v1 = 0;
    if ( v2 )
      CloseHandle(v2);
  }
  wscProductInfoFree(0, 0);
  wscProductInfoFree(v11, v12);
  return v1;
}

```

## disassembly

```asm
0x180008ed0  mov     [rsp-28h+arg_18], rbx
0x180008ed5  push    rbp
0x180008ed6  push    rsi
0x180008ed7  push    rdi
0x180008ed8  push    r14
0x180008eda  push    r15
0x180008edc  mov     rbp, rsp
0x180008edf  sub     rsp, 30h
0x180008ee3  lea     rdx, [rbp+arg_10]
0x180008ee7  mov     [rbp+arg_10], 0
0x180008eef  lea     rcx, [rbp+arg_8]
0x180008ef3  mov     [rbp+arg_8], 0
0x180008efa  call    cs:__imp_wscAntiVirusGetStatus
0x180008f00  test    eax, eax
0x180008f02  jz      short loc_180008F0E
0x180008f04  mov     ebx, 80070426h
0x180008f09  jmp     loc_180009085
0x180008f0e  xor     r15d, r15d
0x180008f11  mov     [rbp+Parameter], r15d
0x180008f15  cmp     [rbp+arg_8], r15d
0x180008f19  jbe     loc_180009047
0x180008f1f  xor     eax, eax
0x180008f21  lea     rcx, [rax+rax*4]
0x180008f25  mov     rax, [rbp+arg_10]
0x180008f29  add     rcx, rcx
0x180008f2c  mov     ebx, [rax+rcx*8]
0x180008f2f  mov     ecx, ebx
0x180008f31  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x180008f36  cmp     eax, 100h
0x180008f3b  jz      short loc_180008F47
0x180008f3d  bt      ebx, 12h
0x180008f41  jnb     loc_180009036
0x180008f47  mov     eax, [rbp+Parameter]
0x180008f4a  mov     rcx, [rbp+arg_10]
0x180008f4e  lea     rdx, [rax+rax*4]
0x180008f52  add     rdx, rdx
0x180008f55  mov     ecx, [rcx+rdx*8]
0x180008f58  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x180008f5d  cmp     eax, 4000h
0x180008f62  jnz     loc_180009036
0x180008f68  mov     eax, [rbp+Parameter]
0x180008f6b  mov     rcx, [rbp+arg_10]
0x180008f6f  lea     rdx, [rax+rax*4]
0x180008f73  add     rdx, rdx; unsigned __int16 *
0x180008f76  mov     rcx, [rcx+rdx*8+10h]; lpSrc
0x180008f7b  call    ?LaunchThirdPartyRemediationExe@@YAHPEAGPEBG@Z; LaunchThirdPartyRemediationExe(ushort *,ushort const *)
0x180008f80  xor     ecx, ecx; hInstance
0x180008f82  test    eax, eax
0x180008f84  jz      short loc_180008FFE
0x180008f86  mov     edx, 7F02h; lpCursorName
0x180008f8b  call    cs:__imp_LoadCursorW
0x180008f91  mov     rcx, rax; hCursor
0x180008f94  mov     r14, rax
0x180008f97  call    cs:__imp_SetCursor
0x180008f9d  lea     r9, [rbp+Parameter]; lpParameter
0x180008fa1  mov     [rsp+30h+lpThreadId], 0; lpThreadId
0x180008faa  lea     r8, ?PollForAMOff@@YAXPEAX@Z; lpStartAddress
0x180008fb1  mov     [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x180008fb9  xor     edx, edx; dwStackSize
0x180008fbb  xor     ecx, ecx; lpThreadAttributes
0x180008fbd  mov     rsi, rax
0x180008fc0  call    cs:__imp_CreateThread
0x180008fc6  mov     rcx, rax; hHandle
0x180008fc9  mov     edx, 2710h; dwMilliseconds
0x180008fce  mov     rdi, rax
0x180008fd1  call    cs:__imp_WaitForSingleObject
0x180008fd7  mov     rcx, r14; hCursor
0x180008fda  mov     ebx, eax
0x180008fdc  call    cs:__imp_DestroyCursor
0x180008fe2  mov     rcx, rsi; hCursor
0x180008fe5  call    cs:__imp_SetCursor
0x180008feb  mov     rcx, rdi; hObject
0x180008fee  call    cs:__imp_CloseHandle
0x180008ff4  cmp     ebx, 102h
0x180008ffa  jnz     short loc_180009025
0x180008ffc  xor     ecx, ecx; lpThreadAttributes
0x180008ffe  mov     [rsp+30h+lpThreadId], 0; lpThreadId
0x180009007  lea     r9, [rbp+Parameter]; lpParameter
0x18000900b  lea     r8, ?HandleDisableFailure@@YAJPEAX@Z; lpStartAddress
0x180009012  mov     [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x18000901a  xor     edx, edx; dwStackSize
0x18000901c  call    cs:__imp_CreateThread
0x180009022  mov     r15, rax
0x180009025  test    r15, r15
0x180009028  jz      short loc_180009036
0x18000902a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000902d  mov     rcx, r15; hHandle
0x180009030  call    cs:__imp_WaitForSingleObject
0x180009036  mov     eax, [rbp+Parameter]
0x180009039  inc     eax
0x18000903b  mov     [rbp+Parameter], eax
0x18000903e  cmp     eax, [rbp+arg_8]
0x180009041  jb      loc_180008F21
0x180009047  mov     rcx, cs:WPP_GLOBAL_Control
0x18000904e  lea     rax, WPP_GLOBAL_Control
0x180009055  cmp     rcx, rax
0x180009058  jz      short loc_180009075
0x18000905a  test    byte ptr [rcx+1Ch], 1
0x18000905e  jz      short loc_180009075
0x180009060  mov     rcx, [rcx+10h]
0x180009064  lea     r8, WPP_cb0f6c3d13033bcf7b6cbf92e57c650f_Traceguids
0x18000906b  mov     edx, 0Ch
0x180009070  call    WPP_SF_
0x180009075  xor     ebx, ebx
0x180009077  test    r15, r15
0x18000907a  jz      short loc_180009085
0x18000907c  mov     rcx, r15; hObject
0x18000907f  call    cs:__imp_CloseHandle
0x180009085  xor     edx, edx
0x180009087  xor     ecx, ecx
0x180009089  call    cs:__imp_wscProductInfoFree
0x18000908f  mov     rdx, [rbp+arg_10]
0x180009093  mov     ecx, [rbp+arg_8]
0x180009096  call    cs:__imp_wscProductInfoFree
0x18000909c  mov     eax, ebx
0x18000909e  mov     rbx, [rsp+30h+arg_18]
0x1800090a3  add     rsp, 30h
0x1800090a7  pop     r15
0x1800090a9  pop     r14
0x1800090ab  pop     rdi
0x1800090ac  pop     rsi
0x1800090ad  pop     rbp
0x1800090ae  retn
```
