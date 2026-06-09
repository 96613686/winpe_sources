# InitiateCallContextCleanup

- ea: `0x180002aac`
- end: `0x180002f4a`
- name: `InitiateCallContextCleanup`
- size: `1182`
- prototype: ``
- caller_count: `20`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800011b0`
- `0x1800012b0`
- `0x180001b40`
- `0x180001fe0`
- `0x180002320`
- `0x180002aac`
- `0x180003010`
- `0x18000530c`
- `0x1800059f0`
- `0x1800071cc`
- `0x18000a59c`
- `0x18000a710`
- `0x18000adb8`
- `0x18000afb0`
- `0x18000b9c8`
- `0x18000c4c4`
- `0x18000ca68`
- `0x18000d978`
- `0x18000ebd0`
- `0x18000f6e0`

## callees

- `0x180002aac`
- `0x180002f50`
- `0x180002f80`
- `0x1800089dc`
- `0x180008b90`
- `0x18000a59c`
- `0x18000adb8`
- `0x18000d978`
- `0x18000da7c`
- `0x18001d1da`
- `0x18001d210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002eb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002b9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002c79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002d8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002e9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002eb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002db3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002eda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ef4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002c55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002d77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002db3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002e85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002eda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ef4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002f0e`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180002d21`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180002d21`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002df8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002e1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002df8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180002e1b`

## pseudocode

```c
__int64 __fastcall InitiateCallContextCleanup(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v6; // rsi
  int v7; // eax
  bool v8; // zf
  unsigned int v9; // eax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rdx
  struct _TP_WORK *v13; // rcx
  struct _TP_WORK *v14; // rcx
  __int64 v15; // r8
  __int64 **v16; // rbx
  __int64 v17; // rcx
  __int64 *v18; // rax
  __int64 *v19; // rdx
  __int64 v20; // rcx
  _QWORD *v21; // rax
  int v23; // [rsp+20h] [rbp-828h] BYREF
  _BYTE v24[2044]; // [rsp+24h] [rbp-824h] BYREF

  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  if ( (byte_18002E903 & 8) != 0 )
  {
    v5 = *(unsigned int *)(a1 + 252);
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"CoId=%hs:InitiateContextCleanup(0x%x)", a1 + 552, v5);
    if ( (byte_18002E903 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v23);
  }
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
  v6 = *(_QWORD *)(a1 + 624);
  if ( v6 )
  {
    *(_QWORD *)(a1 + 624) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 288));
    InitiateCallContextCleanup(v6, a2);
    DereferenceRefCount(v6 + 208);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  }
  if ( !*(_DWORD *)(a1 + 252) )
    goto LABEL_40;
  if ( !*(_BYTE *)(a1 + 435) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 208));
    *(_BYTE *)(a1 + 435) = 1;
  }
  v7 = *(_DWORD *)(a1 + 252);
  if ( (v7 & 0x20) != 0 )
  {
    v7 &= ~0x20u;
    *(_DWORD *)(a1 + 252) = v7;
    if ( a2 == 1 )
    {
      if ( (*(_BYTE *)(a1 + 616) & 2) != 0 )
        goto LABEL_16;
      v7 |= 0x40u;
    }
    else
    {
      if ( a2 )
        goto LABEL_16;
      v7 |= 0x200u;
    }
    *(_DWORD *)(a1 + 252) = v7;
  }
LABEL_16:
  if ( (v7 & 0x10000) != 0 )
  {
    if ( (v7 & 0x200) != 0 )
      goto LABEL_18;
    goto LABEL_40;
  }
  if ( (v7 & 8) != 0 )
  {
    *(_DWORD *)(a1 + 252) = v7 & 0xFFFFBFF7 | 0x4000;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    NotifyMakeCallComplete(a1, *(unsigned int *)(a1 + 268), a1 + 592);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    *(_DWORD *)(a1 + 252) &= ~0x4000u;
    v7 = *(_DWORD *)(a1 + 252);
  }
  if ( (v7 & 0x4000) != 0 )
    goto LABEL_40;
  if ( (v7 & 0x40) == 0 )
  {
    if ( (v7 & 0x800) == 0 )
    {
      if ( (v7 & 0x200) != 0 )
      {
LABEL_18:
        v8 = *(_BYTE *)(a1 + 248) == 0;
        *(_DWORD *)(a1 + 252) = v7 & 0xFFFFDDFF | 0x2000;
        if ( v8 )
          DisconnectServerHttpCallContext(a1);
        else
          DisconnectClientHttpCallContext(a1);
        goto LABEL_41;
      }
      if ( (v7 & 0x2000) == 0 )
      {
        if ( (v7 & 0x400) != 0 )
        {
          *(_DWORD *)(a1 + 252) = v7 & 0xFFFFFBFB | 4;
          LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
          CancelIoEx(*((HANDLE *)SstpSvcGlobals + 35), (LPOVERLAPPED)(a1 + 40));
          goto LABEL_41;
        }
        if ( (v7 & 4) == 0 )
        {
          if ( (v7 & 0x8000) != 0 )
          {
            v7 &= ~0x8000u;
            *(_DWORD *)(a1 + 252) = v7;
          }
          if ( (v7 & 0x100) == 0 && (v7 & 0x80u) == 0 && (v7 & 0x10) != 0 )
          {
            *(_DWORD *)(a1 + 252) = v7 & 0xFFFFFFEF;
            DereferenceRefCount(a1 + 208);
          }
        }
      }
    }
LABEL_40:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    goto LABEL_41;
  }
  LOBYTE(v4) = 0;
  v9 = v7 & 0xFFFFF7BF | 0x800;
  *(_DWORD *)(a1 + 252) = v9;
  if ( (v9 & 0x1000) != 0 )
  {
    LOBYTE(v4) = 1;
    *(_DWORD *)(a1 + 252) = v9 & 0xFFFFEFFF;
  }
  DisconnectSstpCallFromTpi(a1, v4);
LABEL_41:
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
  v10 = (struct _RTL_CRITICAL_SECTION *)(a1 + 288);
  if ( *(_DWORD *)(a1 + 252) == 1 )
  {
    *(_DWORD *)(a1 + 252) = 0;
    LeaveCriticalSection(v10);
    v12 = *(_QWORD *)(a1 + 256);
    if ( v12 )
    {
      LOBYTE(v11) = 1;
      FreeBufferToPool((char *)SstpSvcGlobals + 424, v12, v11);
      *(_QWORD *)(a1 + 256) = 0;
    }
    v13 = *(struct _TP_WORK **)(a1 + 328);
    if ( v13 )
    {
      CloseThreadpoolWork(v13);
      *(_QWORD *)(a1 + 328) = 0;
    }
    v14 = *(struct _TP_WORK **)(a1 + 336);
    if ( v14 )
    {
      CloseThreadpoolWork(v14);
      *(_QWORD *)(a1 + 336) = 0;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    v16 = (__int64 **)(a1 + 416);
    while ( 1 )
    {
      v19 = *v16;
      if ( *v16 == (__int64 *)v16 )
        break;
      v17 = *v19;
      LOBYTE(v15) = 1;
      v18 = (__int64 *)v19[1];
      *v18 = *v19;
      *(_QWORD *)(v17 + 8) = v18;
      FreeBufferToPool((char *)SstpSvcGlobals + 424, v19 - 5, v15);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    v20 = *(_QWORD *)(a1 + 224);
    v21 = *(_QWORD **)(a1 + 232);
    *v21 = v20;
    *(_QWORD *)(v20 + 8) = v21;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 288));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)SstpSvcGlobals + 224));
    DereferenceRefCount(a1 + 208);
  }
  else
  {
    LeaveCriticalSection(v10);
  }
  return DereferenceRefCount(a1 + 208);
}

```

## disassembly

```asm
0x180002aac  mov     [rsp+arg_10], rbx
0x180002ab1  push    rbp
0x180002ab2  push    rsi
0x180002ab3  push    rdi
0x180002ab4  sub     rsp, 830h
0x180002abb  mov     rax, cs:__security_cookie
0x180002ac2  xor     rax, rsp
0x180002ac5  mov     [rsp+848h+var_28], rax
0x180002acd  mov     ebp, edx
0x180002acf  mov     rdi, rcx
0x180002ad2  xor     eax, eax
0x180002ad4  lea     rcx, [rsp+848h+var_824]; void *
0x180002ad9  xor     edx, edx; Val
0x180002adb  mov     [rsp+848h+var_828], eax
0x180002adf  mov     r8d, 7FCh; Size
0x180002ae5  call    memset_0
0x180002aea  test    cs:byte_18002E903, 8
0x180002af1  jz      short loc_180002B3A
0x180002af3  mov     r9d, [rdi+0FCh]
0x180002afa  lea     r8, [rdi+228h]
0x180002b01  xor     eax, eax
0x180002b03  lea     rdx, aCoidHsInitiate; "CoId=%hs:InitiateContextCleanup(0x%x)"
0x180002b0a  lea     rcx, [rsp+848h+var_828]
0x180002b0f  mov     word ptr [rsp+848h+var_828], ax
0x180002b14  call    FormatRRASErrorString
0x180002b19  test    cs:byte_18002E903, 8
0x180002b20  jz      short loc_180002B3A
0x180002b22  lea     r8, [rsp+848h+var_828]
0x180002b27  lea     rdx, RasSSTPSvcTraceError
0x180002b2e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002b35  call    McTemplateU0z_EventWriteTransfer
0x180002b3a  lock inc dword ptr [rdi+0D0h]
0x180002b41  mov     rsi, [rdi+270h]
0x180002b48  test    rsi, rsi
0x180002b4b  jz      short loc_180002BA6
0x180002b4d  lea     rbx, [rdi+120h]
0x180002b54  mov     qword ptr [rdi+270h], 0
0x180002b5f  mov     rcx, rbx; lpCriticalSection
0x180002b62  call    cs:__imp_LeaveCriticalSection
0x180002b69  nop     dword ptr [rax+rax+00h]
0x180002b6e  lea     rcx, [rsi+120h]; lpCriticalSection
0x180002b75  call    cs:__imp_EnterCriticalSection
0x180002b7c  nop     dword ptr [rax+rax+00h]
0x180002b81  mov     edx, ebp
0x180002b83  mov     rcx, rsi
0x180002b86  call    InitiateCallContextCleanup
0x180002b8b  lea     rcx, [rsi+0D0h]
0x180002b92  call    DereferenceRefCount
0x180002b97  mov     rcx, rbx; lpCriticalSection
0x180002b9a  call    cs:__imp_EnterCriticalSection
0x180002ba1  nop     dword ptr [rax+rax+00h]
0x180002ba6  cmp     dword ptr [rdi+0FCh], 0
0x180002bad  jz      loc_180002D70
0x180002bb3  cmp     byte ptr [rdi+1B3h], 0
0x180002bba  jnz     short loc_180002BCA
0x180002bbc  lock inc dword ptr [rdi+0D0h]
0x180002bc3  mov     byte ptr [rdi+1B3h], 1
0x180002bca  mov     eax, [rdi+0FCh]
0x180002bd0  mov     esi, 200h
0x180002bd5  test    al, 20h
0x180002bd7  jz      short loc_180002C01
0x180002bd9  and     eax, 0FFFFFFDFh
0x180002bdc  mov     [rdi+0FCh], eax
0x180002be2  cmp     ebp, 1
0x180002be5  jnz     short loc_180002BF5
0x180002be7  test    byte ptr [rdi+268h], 2
0x180002bee  jnz     short loc_180002C01
0x180002bf0  or      eax, 40h
0x180002bf3  jmp     short loc_180002BFB
0x180002bf5  test    ebp, ebp
0x180002bf7  jnz     short loc_180002C01
0x180002bf9  or      eax, esi
0x180002bfb  mov     [rdi+0FCh], eax
0x180002c01  bt      eax, 10h
0x180002c05  jnb     short loc_180002C37
0x180002c07  test    esi, eax
0x180002c09  jz      loc_180002D70
0x180002c0f  btr     eax, 9
0x180002c13  bts     eax, 0Dh
0x180002c17  cmp     byte ptr [rdi+0F8h], 0
0x180002c1e  mov     [rdi+0FCh], eax
0x180002c24  jnz     loc_180002D2F
0x180002c2a  mov     rcx, rdi
0x180002c2d  call    DisconnectServerHttpCallContext
0x180002c32  jmp     loc_180002D83
0x180002c37  mov     ebp, 4000h
0x180002c3c  test    al, 8
0x180002c3e  jz      short loc_180002C93
0x180002c40  and     eax, 0FFFFFFF7h
0x180002c43  lea     rbx, [rdi+120h]
0x180002c4a  or      eax, ebp
0x180002c4c  mov     rcx, rbx; lpCriticalSection
0x180002c4f  mov     [rdi+0FCh], eax
0x180002c55  call    cs:__imp_LeaveCriticalSection
0x180002c5c  nop     dword ptr [rax+rax+00h]
0x180002c61  mov     edx, [rdi+10Ch]
0x180002c67  lea     r8, [rdi+250h]
0x180002c6e  mov     rcx, rdi
0x180002c71  call    NotifyMakeCallComplete
0x180002c76  mov     rcx, rbx; lpCriticalSection
0x180002c79  call    cs:__imp_EnterCriticalSection
0x180002c80  nop     dword ptr [rax+rax+00h]
0x180002c85  btr     dword ptr [rdi+0FCh], 0Eh
0x180002c8d  mov     eax, [rdi+0FCh]
0x180002c93  test    ebp, eax
0x180002c95  jnz     loc_180002D70
0x180002c9b  test    al, 40h
0x180002c9d  jz      short loc_180002CCD
0x180002c9f  and     eax, 0FFFFFFBFh
0x180002ca2  xor     dl, dl
0x180002ca4  bts     eax, 0Bh
0x180002ca8  mov     [rdi+0FCh], eax
0x180002cae  bt      eax, 0Ch
0x180002cb2  jnb     short loc_180002CC0
0x180002cb4  btr     eax, 0Ch
0x180002cb8  mov     dl, 1
0x180002cba  mov     [rdi+0FCh], eax
0x180002cc0  mov     rcx, rdi
0x180002cc3  call    DisconnectSstpCallFromTpi
0x180002cc8  jmp     loc_180002D83
0x180002ccd  bt      eax, 0Bh
0x180002cd1  jb      loc_180002D70
0x180002cd7  test    esi, eax
0x180002cd9  jnz     loc_180002C0F
0x180002cdf  bt      eax, 0Dh
0x180002ce3  jb      loc_180002D70
0x180002ce9  bt      eax, 0Ah
0x180002ced  jnb     short loc_180002D39
0x180002cef  btr     eax, 0Ah
0x180002cf3  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002cfa  or      eax, 4
0x180002cfd  mov     [rdi+0FCh], eax
0x180002d03  call    cs:__imp_LeaveCriticalSection
0x180002d0a  nop     dword ptr [rax+rax+00h]
0x180002d0f  mov     rcx, cs:SstpSvcGlobals
0x180002d16  lea     rdx, [rdi+28h]; lpOverlapped
0x180002d1a  mov     rcx, [rcx+118h]; hFile
0x180002d21  call    cs:__imp_CancelIoEx
0x180002d28  nop     dword ptr [rax+rax+00h]
0x180002d2d  jmp     short loc_180002D83
0x180002d2f  mov     rcx, rdi
0x180002d32  call    DisconnectClientHttpCallContext
0x180002d37  jmp     short loc_180002D83
0x180002d39  test    al, 4
0x180002d3b  jnz     short loc_180002D70
0x180002d3d  bt      eax, 0Fh
0x180002d41  jnb     short loc_180002D4D
0x180002d43  btr     eax, 0Fh
0x180002d47  mov     [rdi+0FCh], eax
0x180002d4d  bt      eax, 8
0x180002d51  jb      short loc_180002D70
0x180002d53  test    al, al
0x180002d55  js      short loc_180002D70
0x180002d57  test    al, 10h
0x180002d59  jz      short loc_180002D70
0x180002d5b  and     eax, 0FFFFFFEFh
0x180002d5e  lea     rcx, [rdi+0D0h]
0x180002d65  mov     [rdi+0FCh], eax
0x180002d6b  call    DereferenceRefCount
0x180002d70  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002d77  call    cs:__imp_LeaveCriticalSection
0x180002d7e  nop     dword ptr [rax+rax+00h]
0x180002d83  lea     rbx, [rdi+120h]
0x180002d8a  mov     rcx, rbx; lpCriticalSection
0x180002d8d  call    cs:__imp_EnterCriticalSection
0x180002d94  nop     dword ptr [rax+rax+00h]
0x180002d99  cmp     dword ptr [rdi+0FCh], 1
0x180002da0  mov     rcx, rbx; lpCriticalSection
0x180002da3  jnz     loc_180002F0E
0x180002da9  mov     dword ptr [rdi+0FCh], 0
0x180002db3  call    cs:__imp_LeaveCriticalSection
0x180002dba  nop     dword ptr [rax+rax+00h]
0x180002dbf  mov     rdx, [rdi+100h]
0x180002dc6  test    rdx, rdx
0x180002dc9  jz      short loc_180002DEC
0x180002dcb  mov     rcx, cs:SstpSvcGlobals
0x180002dd2  mov     r8b, 1
0x180002dd5  add     rcx, 1A8h
0x180002ddc  call    FreeBufferToPool
0x180002de1  mov     qword ptr [rdi+100h], 0
0x180002dec  mov     rcx, [rdi+148h]; pwk
0x180002df3  test    rcx, rcx
0x180002df6  jz      short loc_180002E0F
0x180002df8  call    cs:__imp_CloseThreadpoolWork
0x180002dff  nop     dword ptr [rax+rax+00h]
0x180002e04  mov     qword ptr [rdi+148h], 0
0x180002e0f  mov     rcx, [rdi+150h]; pwk
0x180002e16  test    rcx, rcx
0x180002e19  jz      short loc_180002E32
0x180002e1b  call    cs:__imp_CloseThreadpoolWork
0x180002e22  nop     dword ptr [rax+rax+00h]
0x180002e27  mov     qword ptr [rdi+150h], 0
0x180002e32  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002e39  call    cs:__imp_EnterCriticalSection
0x180002e40  nop     dword ptr [rax+rax+00h]
0x180002e45  lea     rbx, [rdi+1A0h]
0x180002e4c  jmp     short loc_180002E76
0x180002e4e  mov     rcx, [rdx]
0x180002e51  mov     r8b, 1
0x180002e54  mov     rax, [rdx+8]
0x180002e58  add     rdx, 0FFFFFFFFFFFFFFD8h
0x180002e5c  mov     [rax], rcx
0x180002e5f  mov     [rcx+8], rax
0x180002e63  mov     rcx, cs:SstpSvcGlobals
0x180002e6a  add     rcx, 1A8h
0x180002e71  call    FreeBufferToPool
0x180002e76  mov     rdx, [rbx]
0x180002e79  cmp     rdx, rbx
0x180002e7c  jnz     short loc_180002E4E
0x180002e7e  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002e85  call    cs:__imp_LeaveCriticalSection
0x180002e8c  nop     dword ptr [rax+rax+00h]
0x180002e91  mov     rcx, cs:SstpSvcGlobals
0x180002e98  add     rcx, 0E0h; lpCriticalSection
0x180002e9f  call    cs:__imp_EnterCriticalSection
0x180002ea6  nop     dword ptr [rax+rax+00h]
0x180002eab  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002eb2  call    cs:__imp_EnterCriticalSection
0x180002eb9  nop     dword ptr [rax+rax+00h]
0x180002ebe  mov     rcx, [rdi+0E0h]
0x180002ec5  mov     rax, [rdi+0E8h]
0x180002ecc  mov     [rax], rcx
0x180002ecf  mov     [rcx+8], rax
0x180002ed3  lea     rcx, [rdi+120h]; lpCriticalSection
0x180002eda  call    cs:__imp_LeaveCriticalSection
0x180002ee1  nop     dword ptr [rax+rax+00h]
0x180002ee6  mov     rcx, cs:SstpSvcGlobals
0x180002eed  add     rcx, 0E0h; lpCriticalSection
0x180002ef4  call    cs:__imp_LeaveCriticalSection
0x180002efb  nop     dword ptr [rax+rax+00h]
0x180002f00  lea     rcx, [rdi+0D0h]
0x180002f07  call    DereferenceRefCount
0x180002f0c  jmp     short loc_180002F1A
0x180002f0e  call    cs:__imp_LeaveCriticalSection
0x180002f15  nop     dword ptr [rax+rax+00h]
0x180002f1a  lea     rcx, [rdi+0D0h]
0x180002f21  call    DereferenceRefCount
0x180002f26  mov     rcx, [rsp+848h+var_28]
0x180002f2e  xor     rcx, rsp; StackCookie
0x180002f31  call    __security_check_cookie
0x180002f36  mov     rbx, [rsp+848h+arg_10]
0x180002f3e  add     rsp, 830h
0x180002f45  pop     rdi
0x180002f46  pop     rsi
0x180002f47  pop     rbp
0x180002f48  retn
```
