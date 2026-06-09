# WaCreateHttpApiSession

- ea: `0x1800780f4`
- end: `0x180078318`
- name: `WaCreateHttpApiSession`
- size: `548`
- prototype: `__int64 __fastcall(NET_IF_COMPARTMENT_ID CompartmentId)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180074548`

## callees

- `0x1800180e0`
- `0x18002e460`
- `0x1800648a0`
- `0x1800722f0`
- `0x1800780f4`
- `0x180080674`
- `0x1800971ec`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007828b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007829b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007828b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18007829b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800782cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800782cb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x180078254`
- `api-ms-win-core-kernel32-legacy-l1-1-0!SetFileCompletionNotificationModes` at `0x180078254`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180078178`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800781be`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180078178`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800781be`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18007815e`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18007815e`

## pseudocode

```c
__int64 __fastcall WaCreateHttpApiSession(NET_IF_COMPARTMENT_ID CompartmentId, __int64 a2)
{
  unsigned int LastError; // ebx
  unsigned int v5; // r15d
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // esi
  __int64 v7; // r8
  NTSTATUS v8; // eax
  __int64 v9; // r8
  struct _TP_IO *v10; // rcx
  PTP_IO pio; // [rsp+30h] [rbp-40h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v14; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v15[16]; // [rsp+48h] [rbp-28h] BYREF
  unsigned int *v16; // [rsp+58h] [rbp-18h]
  __int64 v17; // [rsp+60h] [rbp-10h]

  FileHandle = 0;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  pio = 0;
  *(_OWORD *)(a2 + 32) = 0;
  LastError = WapHttpApiDynamicInit();
  if ( !LastError )
  {
    v5 = 0;
    v14 = 2;
    if ( CompartmentId )
    {
      CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
      if ( CurrentThreadCompartmentId != CompartmentId )
      {
        v5 = LastError + 1;
        LastError = SetCurrentThreadCompartmentId(CompartmentId);
        if ( LastError )
          goto LABEL_24;
      }
    }
    else
    {
      CurrentThreadCompartmentId = 0;
    }
    LastError = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, HANDLE *))WaHttpClientVTable)(
                  v14,
                  0,
                  0,
                  2,
                  &FileHandle);
    if ( v5 )
    {
      v8 = SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
      if ( v8 )
        __fastfail(v8);
    }
    if ( LastError == 430 )
    {
      if ( (BYTE3(xmmword_1800AD710) & 4) != 0 )
        WPP_SF_d(538, 12, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids, 430);
      if ( (Microsoft_Windows_WebIOEnableBits & 0x1000000) != 0 )
      {
        v14 = -2146893007;
        v16 = &v14;
        v17 = 4;
        McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, QuicTls13Disabled, v7, 2, v15);
      }
      WaHttp3Disabled = 1;
    }
    else if ( !LastError )
    {
      if ( SetFileCompletionNotificationModes(FileHandle, 1u) )
      {
        LastError = WaTpRegisterCompletionRoutine(FileHandle, WapHttpApiThreadPoolCompletionRoutine, v9, &pio);
        if ( LastError )
        {
          v10 = pio;
        }
        else
        {
          InitializeSRWLock((PSRWLOCK)(a2 + 16));
          InitializeSRWLock((PSRWLOCK)(a2 + 32));
          v10 = 0;
          *(_QWORD *)a2 = FileHandle;
          *(_QWORD *)(a2 + 8) = pio;
          FileHandle = 0;
        }
        if ( v10 )
          CloseThreadpoolIo(v10);
      }
      else
      {
        LastError = WaGetLastError();
      }
    }
  }
LABEL_24:
  if ( FileHandle )
    (*(void (**)(void))(WaHttpClientVTable + 8))();
  return LastError;
}

```

## disassembly

```asm
0x1800780f4  mov     [rsp-28h+arg_10], rbx
0x1800780f9  mov     [rsp-28h+arg_18], rsi
0x1800780fe  push    rbp
0x1800780ff  push    rdi
0x180078100  push    r13
0x180078102  push    r14
0x180078104  push    r15
0x180078106  mov     rbp, rsp
0x180078109  sub     rsp, 70h
0x18007810d  mov     rax, cs:__security_cookie
0x180078114  xor     rax, rsp
0x180078117  mov     [rbp+var_8], rax
0x18007811b  xorps   xmm0, xmm0
0x18007811e  mov     [rbp+FileHandle], 0
0x180078126  movups  xmmword ptr [rdx], xmm0
0x180078129  mov     rdi, rdx
0x18007812c  mov     r14d, ecx
0x18007812f  movups  xmmword ptr [rdx+10h], xmm0
0x180078133  mov     [rbp+pio], 0
0x18007813b  movups  xmmword ptr [rdx+20h], xmm0
0x18007813f  call    WapHttpApiDynamicInit
0x180078144  mov     ebx, eax
0x180078146  test    eax, eax
0x180078148  jnz     loc_1800782D7
0x18007814e  xor     r15d, r15d
0x180078151  lea     r13d, [rax+2]
0x180078155  mov     [rbp+var_30], r13d
0x180078159  test    r14d, r14d
0x18007815c  jz      short loc_180078190
0x18007815e  call    cs:__imp_GetCurrentThreadCompartmentId
0x180078165  nop     dword ptr [rax+rax+00h]
0x18007816a  mov     esi, eax
0x18007816c  cmp     eax, r14d
0x18007816f  jz      short loc_180078192
0x180078171  mov     ecx, r14d; CompartmentId
0x180078174  lea     r15d, [rbx+1]
0x180078178  call    cs:__imp_SetCurrentThreadCompartmentId
0x18007817f  nop     dword ptr [rax+rax+00h]
0x180078184  mov     ebx, eax
0x180078186  test    eax, eax
0x180078188  jnz     loc_1800782D7
0x18007818e  jmp     short loc_180078192
0x180078190  xor     esi, esi
0x180078192  mov     rax, cs:WaHttpClientVTable
0x180078199  lea     rcx, [rbp+FileHandle]
0x18007819d  mov     [rsp+70h+var_50], rcx
0x1800781a2  mov     r9d, r13d
0x1800781a5  mov     ecx, [rbp+var_30]
0x1800781a8  xor     r8d, r8d
0x1800781ab  xor     edx, edx
0x1800781ad  mov     rax, [rax]
0x1800781b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781b5  mov     ebx, eax
0x1800781b7  test    r15d, r15d
0x1800781ba  jz      short loc_1800781D2
0x1800781bc  mov     ecx, esi; CompartmentId
0x1800781be  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800781c5  nop     dword ptr [rax+rax+00h]
0x1800781ca  test    eax, eax
0x1800781cc  jz      short loc_1800781D2
0x1800781ce  mov     ecx, eax
0x1800781d0  int     29h; Win8: RtlFailFast(ecx)
0x1800781d2  mov     r9d, 1AEh
0x1800781d8  cmp     ebx, r9d
0x1800781db  jnz     short loc_180078246
0x1800781dd  test    byte ptr cs:xmmword_1800AD710+3, 4
0x1800781e4  jz      short loc_1800781FB
0x1800781e6  mov     edx, 0Ch
0x1800781eb  lea     ecx, [r9+6Ch]
0x1800781ef  lea     r8, WPP_305d602a2c4b3ed688f990a0fb56ab50_Traceguids
0x1800781f6  call    WPP_SF_d
0x1800781fb  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+3, 1
0x180078202  jz      short loc_18007823A
0x180078204  lea     rax, [rbp+var_30]
0x180078208  mov     [rbp+var_30], 80090331h
0x18007820f  mov     [rbp+var_18], rax
0x180078213  lea     rdx, QuicTls13Disabled
0x18007821a  lea     rax, [rbp+var_28]
0x18007821e  mov     [rbp+var_10], 4
0x180078226  mov     r9d, r13d
0x180078229  mov     [rsp+70h+var_50], rax
0x18007822e  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180078235  call    McGenEventWrite_EventWriteTransfer
0x18007823a  mov     cs:WaHttp3Disabled, 1
0x180078241  jmp     loc_1800782D7
0x180078246  test    ebx, ebx
0x180078248  jnz     loc_1800782D7
0x18007824e  mov     rcx, [rbp+FileHandle]; FileHandle
0x180078252  mov     dl, 1; Flags
0x180078254  call    cs:__imp_SetFileCompletionNotificationModes
0x18007825b  nop     dword ptr [rax+rax+00h]
0x180078260  test    eax, eax
0x180078262  jnz     short loc_18007826D
0x180078264  call    WaGetLastError
0x180078269  mov     ebx, eax
0x18007826b  jmp     short loc_1800782D7
0x18007826d  mov     rcx, [rbp+FileHandle]
0x180078271  lea     r9, [rbp+pio]
0x180078275  lea     rdx, WapHttpApiThreadPoolCompletionRoutine
0x18007827c  call    WaTpRegisterCompletionRoutine
0x180078281  mov     ebx, eax
0x180078283  test    eax, eax
0x180078285  jnz     short loc_1800782C2
0x180078287  lea     rcx, [rdi+10h]; SRWLock
0x18007828b  call    cs:__imp_InitializeSRWLock
0x180078292  nop     dword ptr [rax+rax+00h]
0x180078297  lea     rcx, [rdi+20h]; SRWLock
0x18007829b  call    cs:__imp_InitializeSRWLock
0x1800782a2  nop     dword ptr [rax+rax+00h]
0x1800782a7  mov     rax, [rbp+FileHandle]
0x1800782ab  xor     ecx, ecx
0x1800782ad  mov     [rdi], rax
0x1800782b0  mov     rax, [rbp+pio]
0x1800782b4  mov     [rdi+8], rax
0x1800782b8  mov     [rbp+FileHandle], 0
0x1800782c0  jmp     short loc_1800782C6
0x1800782c2  mov     rcx, [rbp+pio]; pio
0x1800782c6  test    rcx, rcx
0x1800782c9  jz      short loc_1800782D7
0x1800782cb  call    cs:__imp_CloseThreadpoolIo
0x1800782d2  nop     dword ptr [rax+rax+00h]
0x1800782d7  mov     rcx, [rbp+FileHandle]
0x1800782db  test    rcx, rcx
0x1800782de  jz      short loc_1800782F0
0x1800782e0  mov     rax, cs:WaHttpClientVTable
0x1800782e7  mov     rax, [rax+8]
0x1800782eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800782f0  mov     eax, ebx
0x1800782f2  mov     rcx, [rbp+var_8]
0x1800782f6  xor     rcx, rsp; StackCookie
0x1800782f9  call    __security_check_cookie
0x1800782fe  lea     r11, [rsp+70h+var_s0]
0x180078303  mov     rbx, [r11+40h]
0x180078307  mov     rsi, [r11+48h]
0x18007830b  mov     rsp, r11
0x18007830e  pop     r15
0x180078310  pop     r14
0x180078312  pop     r13
0x180078314  pop     rdi
0x180078315  pop     rbp
0x180078316  retn
```
