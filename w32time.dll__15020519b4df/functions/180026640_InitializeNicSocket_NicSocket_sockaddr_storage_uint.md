# InitializeNicSocket(NicSocket *,sockaddr_storage *,uint)

- ea: `0x180026640`
- end: `0x180026bdf`
- name: `?InitializeNicSocket@@YAJPEAUNicSocket@@PEAUsockaddr_storage@@I@Z`
- size: `1439`
- prototype: `__int64 __fastcall(struct sockaddr *name, struct sockaddr_storage *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026200`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x180026640`
- `0x18003d270`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800269aa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800269aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026bce`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180026739`
- `api-ms-win-core-handle-l1-1-0!SetHandleInformation` at `0x180026739`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026b93`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026b93`
- `ntdll!RtlReleaseResource` at `0x180026ad6`
- `ntdll!RtlReleaseResource` at `0x180026b64`
- `ntdll!RtlReleaseResource` at `0x180026ad6`
- `ntdll!RtlReleaseResource` at `0x180026b64`
- `ntdll!RtlAcquireResourceShared` at `0x180026a4b`
- `ntdll!RtlAcquireResourceShared` at `0x180026b21`
- `ntdll!RtlAcquireResourceShared` at `0x180026a4b`
- `ntdll!RtlAcquireResourceShared` at `0x180026b21`
- `WS2_32!WSAEventSelect` at `0x1800269d6`
- `WS2_32!WSAEventSelect` at `0x1800269d6`
- `WS2_32!WSAIoctl` at `0x1800267db`
- `WS2_32!WSAIoctl` at `0x180026847`
- `WS2_32!WSAIoctl` at `0x180026899`
- `WS2_32!WSAIoctl` at `0x1800267db`
- `WS2_32!WSAIoctl` at `0x180026847`
- `WS2_32!WSAIoctl` at `0x180026899`
- `WS2_32!__imp_bind` at `0x18002698b`
- `WS2_32!__imp_bind` at `0x180026bb0`
- `WS2_32!__imp_bind` at `0x18002698b`
- `WS2_32!__imp_bind` at `0x180026bb0`
- `WS2_32!__imp_setsockopt` at `0x18002676a`
- `WS2_32!__imp_setsockopt` at `0x1800268d5`
- `WS2_32!__imp_setsockopt` at `0x18002695d`
- `WS2_32!__imp_setsockopt` at `0x18002676a`
- `WS2_32!__imp_setsockopt` at `0x1800268d5`
- `WS2_32!__imp_setsockopt` at `0x18002695d`
- `WS2_32!__imp_socket` at `0x180026711`
- `WS2_32!__imp_socket` at `0x180026711`
- `WS2_32!__imp_WSAGetLastError` at `0x1800268ea`
- `WS2_32!__imp_WSAGetLastError` at `0x1800269fa`
- `WS2_32!__imp_WSAGetLastError` at `0x180026aab`
- `WS2_32!__imp_WSAGetLastError` at `0x1800268ea`
- `WS2_32!__imp_WSAGetLastError` at `0x1800269fa`
- `WS2_32!__imp_WSAGetLastError` at `0x180026aab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InitializeNicSocket(struct sockaddr *name, struct sockaddr_storage *a2, int a3)
{
  struct sockaddr v3; // xmm0
  struct sockaddr v6; // xmm1
  struct sockaddr v7; // xmm0
  struct sockaddr v8; // xmm1
  struct sockaddr v9; // xmm0
  struct sockaddr v10; // xmm1
  void *v11; // rax
  SOCKET v12; // rcx
  SOCKET v13; // rcx
  ADDRESS_FAMILY ss_family; // ax
  int LastError; // eax
  unsigned int v16; // ebx
  int v18; // esi
  DWORD v19; // edi
  HANDLE EventW; // rax
  int v21; // eax
  char v22; // di
  __int64 j; // rdx
  int Error; // eax
  char v25; // si
  __int64 i; // rdx
  DWORD cbBytesReturned; // [rsp+50h] [rbp+7h] BYREF
  char v28[4]; // [rsp+54h] [rbp+Bh] BYREF
  char optval[8]; // [rsp+58h] [rbp+Fh] BYREF
  __int64 vInBuffer; // [rsp+60h] [rbp+17h] BYREF
  _DWORD v31[4]; // [rsp+68h] [rbp+1Fh] BYREF
  _DWORD v32[4]; // [rsp+78h] [rbp+2Fh] BYREF

  v3 = *(struct sockaddr *)&a2->ss_family;
  v31[0] = -158738488;
  *(_DWORD *)optval = 0;
  *name = v3;
  v6 = *(struct sockaddr *)a2->__ss_pad2;
  *(_DWORD *)v28 = 0;
  v31[1] = 1131114271;
  name[1] = v6;
  v31[2] = 1340429194;
  v7 = *(struct sockaddr *)&a2->__ss_pad2[16];
  v31[3] = 583225827;
  v32[0] = -1539184878;
  name[2] = v7;
  v32[1] = 1137341775;
  v8 = *(struct sockaddr *)&a2->__ss_pad2[32];
  v32[2] = -301095036;
  v32[3] = 1835061060;
  name[3] = v8;
  cbBytesReturned = 0;
  v9 = *(struct sockaddr *)&a2->__ss_pad2[48];
  vInBuffer = 0;
  name[4] = v9;
  name[5] = *(struct sockaddr *)&a2->__ss_pad2[64];
  name[6] = *(struct sockaddr *)&a2->__ss_pad2[80];
  v10 = *(struct sockaddr *)&a2->__ss_pad2[96];
  *(_DWORD *)&name[8].sa_family = a3;
  name[7] = v10;
  v11 = (void *)socket(name->sa_family, 2, 17);
  *(_QWORD *)&name[8].sa_data[6] = v11;
  if ( v11 == (void *)-1LL
    || (SetHandleInformation(v11, 1u, 0),
        v12 = *(_QWORD *)&name[8].sa_data[6],
        *(_DWORD *)optval = 1,
        setsockopt(v12, 0xFFFF, -5, optval, 4) == -1) )
  {
    Error = WSAGetLastError();
    v16 = Error;
    if ( Error > 0 )
      return (unsigned __int16)Error | 0x80070000;
  }
  else
  {
    if ( !*((_BYTE *)g_pnpstate + 80) )
    {
      name[9].sa_data[7] = 0;
      if ( (unsigned __int8)FileLogAllowEntry(2) )
        FileLogAdd(L"Iftmstmps disabled\n");
      goto LABEL_6;
    }
    v13 = *(_QWORD *)&name[8].sa_data[6];
    WORD2(vInBuffer) = 20;
    LODWORD(vInBuffer) = 3;
    if ( WSAIoctl(v13, 0x980000EB, &vInBuffer, 8u, 0, 0, &cbBytesReturned, 0, 0) != -1 )
    {
      name[9].sa_data[7] = 1;
      if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
        && _pflstate
        && *((_BYTE *)_pflstate + 315)
        && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
      {
        v25 = 0;
        for ( i = *((_QWORD *)_pflstate + 3); i && *(_DWORD *)i <= 0x7Du; i = *(_QWORD *)(i + 8) )
        {
          if ( (unsigned int)(*(_DWORD *)(i + 4) + *(_DWORD *)i) > 0x7D )
          {
            v25 = 1;
            break;
          }
        }
        RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
        if ( v25 )
          FileLogAdd(L"Iftmstmps allowed.\n");
      }
LABEL_6:
      if ( WSAIoctl(*(_QWORD *)&name[8].sa_data[6], 0xC8000006, v31, 0x10u, &name[10], 8u, &cbBytesReturned, 0, 0) == -1
        || WSAIoctl(
             *(_QWORD *)&name[8].sa_data[6],
             0xC8000006,
             v32,
             0x10u,
             &name[10].sa_data[6],
             8u,
             &cbBytesReturned,
             0,
             0) == -1 )
      {
        goto LABEL_10;
      }
      ss_family = a2->ss_family;
      *(_DWORD *)v28 = 1;
      if ( ss_family == 2 )
      {
        if ( setsockopt(*(_QWORD *)&name[8].sa_data[6], 0, 19, v28, 4) == -1 )
          goto LABEL_10;
      }
      else if ( ss_family == 23 && setsockopt(*(_QWORD *)&name[8].sa_data[6], 41, 19, v28, 4) == -1 )
      {
        goto LABEL_10;
      }
      v18 = 0;
      v19 = 500;
      if ( bind(*(_QWORD *)&name[8].sa_data[6], name, *(_DWORD *)&name[8].sa_family) == -1 )
      {
        while ( v18 < 10000 )
        {
          Sleep(v19);
          v18 += v19;
          v19 += 500;
          if ( bind(*(_QWORD *)&name[8].sa_data[6], name, *(_DWORD *)&name[8].sa_family) != -1 )
            goto LABEL_17;
        }
      }
      else
      {
LABEL_17:
        EventW = CreateEventW(0, 0, 0, 0);
        *(_QWORD *)&name[9].sa_family = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
LABEL_11:
          v16 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
          return v16;
        }
        if ( WSAEventSelect(*(_QWORD *)&name[8].sa_data[6], EventW, 1) != -1 )
        {
          name[9].sa_data[6] = 0;
          return 0;
        }
      }
LABEL_10:
      LastError = WSAGetLastError();
      goto LABEL_11;
    }
    v21 = WSAGetLastError();
    v16 = v21;
    if ( v21 > 0 )
      v16 = (unsigned __int16)v21 | 0x80070000;
    if ( _InterlockedCompareExchange(&_lLoggingEnabled, 0, 0)
      && _pflstate
      && *((_BYTE *)_pflstate + 315)
      && RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
    {
      v22 = 0;
      for ( j = *((_QWORD *)_pflstate + 3); j && !*(_DWORD *)j; j = *(_QWORD *)(j + 8) )
      {
        if ( *(_DWORD *)(j + 4) )
        {
          v22 = 1;
          break;
        }
      }
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
      if ( v22 )
        FileLogAdd(L"WSAIoctl timestamping error:0x%08x\n", v16);
    }
  }
  return v16;
}

```

## disassembly

```asm
0x180026640  mov     [rsp-8+arg_10], rbx
0x180026645  mov     [rsp-8+arg_18], rdi
0x18002664a  push    rbp
0x18002664b  push    r14
0x18002664d  push    r15
0x18002664f  lea     rbp, [rsp-47h]
0x180026654  sub     rsp, 90h
0x18002665b  mov     rax, cs:__security_cookie
0x180026662  xor     rax, rsp
0x180026665  mov     [rbp+57h+var_18], rax
0x180026669  movups  xmm0, xmmword ptr [rdx]
0x18002666c  xor     r14d, r14d
0x18002666f  mov     [rbp+57h+var_38], 0F689D7C8h
0x180026676  mov     rdi, rdx
0x180026679  mov     dword ptr [rbp+57h+optval], r14d
0x18002667d  movups  xmmword ptr [rcx], xmm0
0x180026680  mov     rbx, rcx
0x180026683  mov     r15d, 2
0x180026689  movups  xmm1, xmmword ptr [rdx+10h]
0x18002668d  mov     dword ptr [rbp+57h+var_4C], r14d
0x180026691  mov     [rbp+57h+var_34], 436B6F1Fh
0x180026698  movups  xmmword ptr [rcx+10h], xmm1
0x18002669c  mov     [rbp+57h+var_30], 4FE5538Ah
0x1800266a3  movups  xmm0, xmmword ptr [rdx+20h]
0x1800266a7  mov     [rbp+57h+var_2C], 22C351E3h
0x1800266ae  mov     [rbp+57h+var_28], 0A441E712h
0x1800266b5  movups  xmmword ptr [rcx+20h], xmm0
0x1800266b9  mov     [rbp+57h+var_24], 43CA754Fh
0x1800266c0  movups  xmm1, xmmword ptr [rdx+30h]
0x1800266c4  mov     [rbp+57h+var_20], 0EE0DA784h
0x1800266cb  mov     [rbp+57h+var_1C], 6D60CF44h
0x1800266d2  movups  xmmword ptr [rcx+30h], xmm1
0x1800266d6  mov     [rbp+57h+cbBytesReturned], r14d
0x1800266da  movups  xmm0, xmmword ptr [rdx+40h]
0x1800266de  mov     [rbp+57h+vInBuffer], r14
0x1800266e2  movups  xmmword ptr [rcx+40h], xmm0
0x1800266e6  movups  xmm1, xmmword ptr [rdx+50h]
0x1800266ea  movups  xmmword ptr [rcx+50h], xmm1
0x1800266ee  movups  xmm0, xmmword ptr [rdx+60h]
0x1800266f2  movups  xmmword ptr [rcx+60h], xmm0
0x1800266f6  movups  xmm1, xmmword ptr [rdx+70h]
0x1800266fa  mov     [rcx+80h], r8d
0x180026701  mov     edx, r15d; type
0x180026704  mov     r8d, 11h; protocol
0x18002670a  movups  xmmword ptr [rcx+70h], xmm1
0x18002670e  movzx   ecx, word ptr [rcx]; af
0x180026711  call    cs:__imp_socket
0x180026718  nop     dword ptr [rax+rax+00h]
0x18002671d  mov     [rbx+88h], rax
0x180026724  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026728  jz      loc_180026AAB
0x18002672e  xor     r8d, r8d; dwFlags
0x180026731  mov     edx, 1; dwMask
0x180026736  mov     rcx, rax; hObject
0x180026739  call    cs:__imp_SetHandleInformation
0x180026740  nop     dword ptr [rax+rax+00h]
0x180026745  mov     rcx, [rbx+88h]; s
0x18002674c  lea     r9, [rbp+57h+optval]; optval
0x180026750  mov     edx, 0FFFFh; level
0x180026755  mov     dword ptr [rbp+57h+optval], 1
0x18002675c  mov     r8d, 0FFFFFFFBh; optname
0x180026762  mov     [rsp+0A0h+optlen], 4; optlen
0x18002676a  call    cs:__imp_setsockopt
0x180026771  nop     dword ptr [rax+rax+00h]
0x180026776  cmp     eax, 0FFFFFFFFh
0x180026779  jz      loc_180026AAB
0x18002677f  mov     rax, cs:?g_pnpstate@@3PEAU_NtpProvState@@EA; _NtpProvState * g_pnpstate
0x180026786  mov     [rsp+0A0h+arg_8], rsi
0x18002678e  cmp     [rax+50h], r14b
0x180026792  jz      loc_180026A83
0x180026798  mov     rcx, [rbx+88h]; s
0x18002679f  lea     r8, [rbp+57h+vInBuffer]; lpvInBuffer
0x1800267a3  mov     [rsp+0A0h+lpCompletionRoutine], r14; lpCompletionRoutine
0x1800267a8  mov     eax, 14h
0x1800267ad  mov     [rsp+0A0h+lpOverlapped], r14; lpOverlapped
0x1800267b2  mov     r9d, 8; cbInBuffer
0x1800267b8  mov     word ptr [rbp+57h+vInBuffer+4], ax
0x1800267bc  mov     edx, 980000EBh; dwIoControlCode
0x1800267c1  lea     rax, [rbp+57h+cbBytesReturned]
0x1800267c5  mov     dword ptr [rbp+57h+vInBuffer], 3
0x1800267cc  mov     [rsp+0A0h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800267d1  mov     [rsp+0A0h+cbOutBuffer], r14d; cbOutBuffer
0x1800267d6  mov     qword ptr [rsp+0A0h+optlen], r14; lpvOutBuffer
0x1800267db  call    cs:__imp_WSAIoctl
0x1800267e2  nop     dword ptr [rax+rax+00h]
0x1800267e7  cmp     eax, 0FFFFFFFFh
0x1800267ea  jz      loc_1800269FA
0x1800267f0  mov     byte ptr [rbx+99h], 1
0x1800267f7  mov     ecx, r14d
0x1800267fa  xor     eax, eax
0x1800267fc  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x180026804  jnz     loc_180026AFE
0x18002680a  mov     [rsp+0A0h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18002680f  lea     rcx, [rbp+57h+cbBytesReturned]
0x180026813  mov     [rsp+0A0h+lpOverlapped], r14; lpOverlapped
0x180026818  lea     rax, [rbx+0A0h]
0x18002681f  mov     [rsp+0A0h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x180026824  lea     r8, [rbp+57h+var_38]; lpvInBuffer
0x180026828  mov     rcx, [rbx+88h]; s
0x18002682f  mov     r9d, 10h; cbInBuffer
0x180026835  mov     [rsp+0A0h+cbOutBuffer], 8; cbOutBuffer
0x18002683d  mov     edx, 0C8000006h; dwIoControlCode
0x180026842  mov     qword ptr [rsp+0A0h+optlen], rax; lpvOutBuffer
0x180026847  call    cs:__imp_WSAIoctl
0x18002684e  nop     dword ptr [rax+rax+00h]
0x180026853  cmp     eax, 0FFFFFFFFh
0x180026856  jz      loc_1800268EA
0x18002685c  mov     [rsp+0A0h+lpCompletionRoutine], r14; lpCompletionRoutine
0x180026861  lea     rcx, [rbp+57h+cbBytesReturned]
0x180026865  mov     [rsp+0A0h+lpOverlapped], r14; lpOverlapped
0x18002686a  lea     rax, [rbx+0A8h]
0x180026871  mov     [rsp+0A0h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x180026876  lea     r8, [rbp+57h+var_28]; lpvInBuffer
0x18002687a  mov     rcx, [rbx+88h]; s
0x180026881  mov     r9d, 10h; cbInBuffer
0x180026887  mov     [rsp+0A0h+cbOutBuffer], 8; cbOutBuffer
0x18002688f  mov     edx, 0C8000006h; dwIoControlCode
0x180026894  mov     qword ptr [rsp+0A0h+optlen], rax; lpvOutBuffer
0x180026899  call    cs:__imp_WSAIoctl
0x1800268a0  nop     dword ptr [rax+rax+00h]
0x1800268a5  cmp     eax, 0FFFFFFFFh
0x1800268a8  jz      short loc_1800268EA
0x1800268aa  movzx   eax, word ptr [rdi]
0x1800268ad  mov     dword ptr [rbp+57h+var_4C], 1
0x1800268b4  cmp     r15w, ax
0x1800268b8  jnz     short loc_180026935
0x1800268ba  mov     rcx, [rbx+88h]; s
0x1800268c1  lea     r9, [rbp+57h+var_4C]; optval
0x1800268c5  xor     edx, edx; level
0x1800268c7  mov     [rsp+0A0h+optlen], 4; optlen
0x1800268cf  mov     r8d, 13h; optname
0x1800268d5  call    cs:__imp_setsockopt
0x1800268dc  nop     dword ptr [rax+rax+00h]
0x1800268e1  cmp     eax, 0FFFFFFFFh
0x1800268e4  jnz     loc_180026972
0x1800268ea  call    cs:__imp_WSAGetLastError
0x1800268f1  nop     dword ptr [rax+rax+00h]
0x1800268f6  mov     ebx, eax
0x1800268f8  test    eax, eax
0x1800268fa  jle     short loc_180026905
0x1800268fc  movzx   ebx, ax
0x1800268ff  or      ebx, 80070000h
0x180026905  mov     rsi, [rsp+0A0h+arg_8]
0x18002690d  mov     eax, ebx
0x18002690f  mov     rcx, [rbp+57h+var_18]
0x180026913  xor     rcx, rsp; StackCookie
0x180026916  call    __security_check_cookie
0x18002691b  lea     r11, [rsp+0A0h+var_10]
0x180026923  mov     rbx, [r11+30h]
0x180026927  mov     rdi, [r11+38h]
0x18002692b  mov     rsp, r11
0x18002692e  pop     r15
0x180026930  pop     r14
0x180026932  pop     rbp
0x180026933  retn
0x180026935  mov     ecx, 17h
0x18002693a  cmp     cx, ax
0x18002693d  jnz     short loc_180026972
0x18002693f  mov     rcx, [rbx+88h]; s
0x180026946  lea     r9, [rbp+57h+var_4C]; optval
0x18002694a  mov     edx, 29h ; ')'; level
0x18002694f  mov     [rsp+0A0h+optlen], 4; optlen
0x180026957  mov     r8d, 13h; optname
0x18002695d  call    cs:__imp_setsockopt
0x180026964  nop     dword ptr [rax+rax+00h]
0x180026969  cmp     eax, 0FFFFFFFFh
0x18002696c  jz      loc_1800268EA
0x180026972  mov     r8d, [rbx+80h]; namelen
0x180026979  mov     rdx, rbx; name
0x18002697c  mov     rcx, [rbx+88h]; s
0x180026983  mov     esi, r14d
0x180026986  mov     edi, 1F4h
0x18002698b  call    cs:__imp_bind
0x180026992  nop     dword ptr [rax+rax+00h]
0x180026997  cmp     eax, 0FFFFFFFFh
0x18002699a  jz      loc_180026B85
0x1800269a0  xor     r9d, r9d; lpName
0x1800269a3  xor     r8d, r8d; bInitialState
0x1800269a6  xor     edx, edx; bManualReset
0x1800269a8  xor     ecx, ecx; lpEventAttributes
0x1800269aa  call    cs:__imp_CreateEventW
0x1800269b1  nop     dword ptr [rax+rax+00h]
0x1800269b6  mov     [rbx+90h], rax
0x1800269bd  test    rax, rax
0x1800269c0  jz      loc_180026BCE
0x1800269c6  mov     rcx, [rbx+88h]; s
0x1800269cd  mov     r8d, 1; lNetworkEvents
0x1800269d3  mov     rdx, rax; hEventObject
0x1800269d6  call    cs:__imp_WSAEventSelect
0x1800269dd  nop     dword ptr [rax+rax+00h]
0x1800269e2  cmp     eax, 0FFFFFFFFh
0x1800269e5  jz      loc_1800268EA
0x1800269eb  mov     [rbx+98h], r14b
0x1800269f2  mov     ebx, r14d
0x1800269f5  jmp     loc_180026905
0x1800269fa  call    cs:__imp_WSAGetLastError
0x180026a01  nop     dword ptr [rax+rax+00h]
0x180026a06  mov     ebx, eax
0x180026a08  test    eax, eax
0x180026a0a  jle     short loc_180026A15
0x180026a0c  movzx   ebx, ax
0x180026a0f  or      ebx, 80070000h
0x180026a15  mov     ecx, r14d
0x180026a18  xor     eax, eax
0x180026a1a  lock cmpxchg cs:?_lLoggingEnabled@@3JC, ecx; long volatile _lLoggingEnabled
0x180026a22  jz      loc_180026905
0x180026a28  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180026a2f  test    rcx, rcx
0x180026a32  jz      loc_180026905
0x180026a38  cmp     [rcx+13Bh], r14b
0x180026a3f  jz      loc_180026905
0x180026a45  add     rcx, 50h ; 'P'; Resource
0x180026a49  mov     dl, 1; Wait
0x180026a4b  call    cs:__imp_RtlAcquireResourceShared
0x180026a52  nop     dword ptr [rax+rax+00h]
0x180026a57  test    al, al
0x180026a59  jz      loc_180026905
0x180026a5f  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180026a66  xor     dil, dil
0x180026a69  mov     rdx, [r8+18h]
0x180026a6d  test    rdx, rdx
0x180026a70  jz      short loc_180026AD2
0x180026a72  mov     ecx, [rdx]
0x180026a74  test    ecx, ecx
0x180026a76  jnz     short loc_180026AD2
0x180026a78  add     ecx, [rdx+4]
0x180026a7b  jnz     short loc_180026ACF
0x180026a7d  mov     rdx, [rdx+8]
0x180026a81  jmp     short loc_180026A6D
0x180026a83  mov     ecx, r15d
0x180026a86  mov     [rbx+99h], r14b
0x180026a8d  call    FileLogAllowEntry
0x180026a92  test    al, al
0x180026a94  jz      loc_18002680A
0x180026a9a  lea     rcx, aIftmstmpsDisab; "Iftmstmps disabled\n"
0x180026aa1  call    FileLogAdd
0x180026aa6  jmp     loc_18002680A
0x180026aab  call    cs:__imp_WSAGetLastError
0x180026ab2  nop     dword ptr [rax+rax+00h]
0x180026ab7  mov     ebx, eax
0x180026ab9  test    eax, eax
0x180026abb  jle     loc_18002690D
0x180026ac1  movzx   ebx, ax
0x180026ac4  or      ebx, 80070000h
0x180026aca  jmp     loc_18002690D
0x180026acf  mov     dil, 1
0x180026ad2  lea     rcx, [r8+50h]; Resource
0x180026ad6  call    cs:__imp_RtlReleaseResource
0x180026add  nop     dword ptr [rax+rax+00h]
0x180026ae2  test    dil, dil
0x180026ae5  jz      loc_180026905
0x180026aeb  mov     edx, ebx
0x180026aed  lea     rcx, aWsaioctlTimest; "WSAIoctl timestamping error:0x%08x\n"
0x180026af4  call    FileLogAdd
0x180026af9  jmp     loc_180026905
0x180026afe  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180026b05  test    rcx, rcx
0x180026b08  jz      loc_18002680A
0x180026b0e  cmp     [rcx+13Bh], r14b
0x180026b15  jz      loc_18002680A
0x180026b1b  add     rcx, 50h ; 'P'; Resource
0x180026b1f  mov     dl, 1; Wait
0x180026b21  call    cs:__imp_RtlAcquireResourceShared
0x180026b28  nop     dword ptr [rax+rax+00h]
0x180026b2d  test    al, al
0x180026b2f  jz      loc_18002680A
0x180026b35  mov     r8, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180026b3c  xor     sil, sil
0x180026b3f  mov     rdx, [r8+18h]
0x180026b43  test    rdx, rdx
0x180026b46  jz      short loc_180026B60
0x180026b48  mov     ecx, [rdx]
0x180026b4a  cmp     ecx, 7Dh ; '}'
0x180026b4d  ja      short loc_180026B60
0x180026b4f  add     ecx, [rdx+4]
0x180026b52  cmp     ecx, 7Dh ; '}'
0x180026b55  ja      short loc_180026B5D
0x180026b57  mov     rdx, [rdx+8]
0x180026b5b  jmp     short loc_180026B43
0x180026b5d  mov     sil, 1
0x180026b60  lea     rcx, [r8+50h]; Resource
0x180026b64  call    cs:__imp_RtlReleaseResource
0x180026b6b  nop     dword ptr [rax+rax+00h]
0x180026b70  test    sil, sil
0x180026b73  jz      loc_18002680A
0x180026b79  lea     rcx, aIftmstmpsAllow; "Iftmstmps allowed.\n"
0x180026b80  jmp     loc_180026AA1
0x180026b85  cmp     esi, 2710h
0x180026b8b  jge     loc_1800268EA
0x180026b91  mov     ecx, edi; dwMilliseconds
0x180026b93  call    cs:__imp_Sleep
0x180026b9a  nop     dword ptr [rax+rax+00h]
0x180026b9f  mov     r8d, [rbx+80h]; namelen
0x180026ba6  mov     rdx, rbx; name
0x180026ba9  mov     rcx, [rbx+88h]; s
0x180026bb0  call    cs:__imp_bind
0x180026bb7  nop     dword ptr [rax+rax+00h]
0x180026bbc  add     esi, edi
0x180026bbe  add     edi, 1F4h
0x180026bc4  cmp     eax, 0FFFFFFFFh
  ... truncated ...
```
