# HTTP2WinHttpTransportChannel::ReadEEInfoFromResponse(long)

- ea: `0x1800114d0`
- end: `0x18001178a`
- name: `?ReadEEInfoFromResponse@HTTP2WinHttpTransportChannel@@AEAAHJ@Z`
- size: `698`
- prototype: `__int64 __fastcall(HTTP2WinHttpTransportChannel *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800081e8`

## callees

- `0x180001fd4`
- `0x180002050`
- `0x180005428`
- `0x180009d58`
- `0x1800114d0`
- `0x1800193b8`
- `0x18001e4a4`
- `0x18002461d`
- `0x180025010`

## import_xrefs

- `ntdll!_strnicmp` at `0x1800116b1`
- `ntdll!_strnicmp` at `0x1800116b1`
- `KERNEL32!GetLastError` at `0x18001158b`
- `KERNEL32!GetLastError` at `0x18001158b`
- `KERNEL32!CreateEventW` at `0x1800114ef`
- `KERNEL32!CreateEventW` at `0x1800114ef`
- `KERNEL32!WaitForSingleObject` at `0x180011579`
- `KERNEL32!WaitForSingleObject` at `0x180011678`
- `KERNEL32!WaitForSingleObject` at `0x180011579`
- `KERNEL32!WaitForSingleObject` at `0x180011678`
- `KERNEL32!CloseHandle` at `0x180011772`
- `KERNEL32!CloseHandle` at `0x180011772`
- `KERNEL32!ResetEvent` at `0x180011616`
- `KERNEL32!ResetEvent` at `0x180011685`
- `KERNEL32!ResetEvent` at `0x180011616`
- `KERNEL32!ResetEvent` at `0x180011685`
- `RPCRT4!I_RpcFree` at `0x1800115ef`
- `RPCRT4!I_RpcFree` at `0x180011735`
- `RPCRT4!I_RpcFree` at `0x180011759`
- `RPCRT4!I_RpcFree` at `0x1800115ef`
- `RPCRT4!I_RpcFree` at `0x180011735`
- `RPCRT4!I_RpcFree` at `0x180011759`
- `RPCRT4!I_RpcAllocate` at `0x1800115cc`
- `RPCRT4!I_RpcAllocate` at `0x1800115f7`
- `RPCRT4!I_RpcAllocate` at `0x1800116fe`
- `RPCRT4!I_RpcAllocate` at `0x1800115cc`
- `RPCRT4!I_RpcAllocate` at `0x1800115f7`
- `RPCRT4!I_RpcAllocate` at `0x1800116fe`
- `RPCRT4!I_RpcLogEvent` at `0x180011552`
- `RPCRT4!I_RpcLogEvent` at `0x18001164c`
- `RPCRT4!I_RpcLogEvent` at `0x180011552`
- `RPCRT4!I_RpcLogEvent` at `0x18001164c`
- `WINHTTP!WinHttpReadData` at `0x180011663`
- `WINHTTP!WinHttpReadData` at `0x180011663`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18001155e`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18001155e`

## pseudocode

```c
__int64 __fastcall HTTP2WinHttpTransportChannel::ReadEEInfoFromResponse(HTTP2WinHttpTransportChannel *this)
{
  unsigned int v2; // r12d
  HANDLE EventW; // rax
  void *v4; // r14
  unsigned __int8 *v5; // rsi
  unsigned int v6; // r15d
  __int64 v7; // rdx
  __int64 v8; // rcx
  BOOL DataAvailable; // ebx
  DWORD LastError; // eax
  unsigned int v11; // ecx
  unsigned __int8 *v12; // rbx
  unsigned __int8 *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  char *v16; // rbp
  unsigned __int8 *v17; // rbx
  unsigned __int64 v18; // rdx
  unsigned int v19; // ebx
  unsigned __int8 *v20; // rax
  unsigned int v21; // r9d
  unsigned __int8 *v22; // r15
  unsigned int v23; // eax

  v2 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  v4 = EventW;
  if ( EventW )
  {
    v5 = 0;
    *((_QWORD *)this + 21) = EventW;
    v6 = 0;
    while ( !(unsigned int)HTTP2Channel::BeginSimpleSubmitAsync(*((HTTP2Channel **)this + 3)) )
    {
      *((_DWORD *)this + 45) = 8;
      HTTP2WinHttpTransportChannel::SetEEInfoDrainFlag(this);
      LOBYTE(v7) = 111;
      LOBYTE(v8) = 50;
      I_RpcLogEvent(v8, v7, *((_QWORD *)this + 9), 25952278, 0, 0, 0);
      DataAvailable = WinHttpQueryDataAvailable(*((HINTERNET *)this + 9), 0);
      HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)this + 3));
      if ( DataAvailable )
      {
        WaitForSingleObject(v4, 0xFFFFFFFF);
        if ( *((_DWORD *)this + 21) )
          break;
      }
      else
      {
        LastError = GetLastError();
        *((_DWORD *)this + 21) = LastError;
        if ( LastError != 12030 )
          break;
        *((_QWORD *)this + 10) = 0;
      }
      v11 = *((_DWORD *)this + 20);
      if ( !v11 )
      {
        if ( v6 >= 0xB && !_strnicmp((const char *)v5, "RPC EEInfo:", 0xBu) )
        {
          v16 = (char *)(v5 + 11);
          if ( !(unsigned int)InitializeDecodingTableIfNecessary() )
          {
            v17 = v5 + 11;
            v18 = (unsigned __int64)&v16[v6 - 11];
            if ( (unsigned __int64)v16 < v18 )
            {
              do
              {
                if ( DecodingTable[*v17] >= 0x40u )
                  break;
                ++v17;
              }
              while ( (unsigned __int64)v17 < v18 );
            }
            v19 = (_DWORD)v17 - (_DWORD)v16;
            if ( v19 )
            {
              v20 = (unsigned __int8 *)I_RpcAllocate(v19 + 2);
              v22 = v20;
              if ( v20 )
              {
                v23 = RpcpBase64DecodeA(v5 + 11, v20, v19, v21);
                (*((void (__fastcall **)(unsigned __int8 *, _QWORD))pRuntimeImportTable + 68))(v22, v23);
                I_RpcFree(v22);
                CompRpcpErrorAddRecord(0xDu, 0, 0x69Au);
                v2 = 1;
              }
            }
          }
        }
        break;
      }
      if ( v11 > 0xC000 || v11 + v6 > 0xC000 )
        break;
      if ( v5 )
      {
        v12 = v5;
        v13 = (unsigned __int8 *)I_RpcAllocate(v11 + v6);
        v5 = v13;
        if ( !v13 )
        {
          v5 = v12;
          goto LABEL_29;
        }
        memcpy_0(v13, v12, v6);
        I_RpcFree(v12);
      }
      else
      {
        v5 = (unsigned __int8 *)I_RpcAllocate(v11);
        if ( !v5 )
          goto LABEL_30;
      }
      *((_DWORD *)this + 45) = 5;
      ResetEvent(v4);
      if ( (unsigned int)HTTP2Channel::BeginSimpleSubmitAsync(*((HTTP2Channel **)this + 3)) )
        goto LABEL_29;
      LOBYTE(v14) = 111;
      LOBYTE(v15) = 50;
      I_RpcLogEvent(v15, v14, *((_QWORD *)this + 9), 25755670, *((_DWORD *)this + 20), 0, 0);
      WinHttpReadData(*((HINTERNET *)this + 9), &v5[v6], *((_DWORD *)this + 20), 0);
      HTTP2Channel::FinishSubmitAsync(*((HTTP2Channel **)this + 3));
      WaitForSingleObject(v4, 0xFFFFFFFF);
      v6 += *((_DWORD *)this + 20);
      ResetEvent(v4);
    }
    if ( !v5 )
      goto LABEL_30;
LABEL_29:
    I_RpcFree(v5);
  }
LABEL_30:
  *((_QWORD *)this + 21) = 0;
  if ( v4 )
    CloseHandle(v4);
  return v2;
}

```

## disassembly

```asm
0x1800114d0  push    rbx
0x1800114d2  push    rbp
0x1800114d3  push    rsi
0x1800114d4  push    rdi
0x1800114d5  push    r12
0x1800114d7  push    r14
0x1800114d9  push    r15
0x1800114db  sub     rsp, 40h
0x1800114df  mov     rdi, rcx
0x1800114e2  xor     r9d, r9d; lpName
0x1800114e5  xor     ecx, ecx; lpEventAttributes
0x1800114e7  xor     r8d, r8d; bInitialState
0x1800114ea  xor     edx, edx; bManualReset
0x1800114ec  xor     r12d, r12d
0x1800114ef  call    cs:__imp_CreateEventW
0x1800114f5  mov     r14, rax
0x1800114f8  test    rax, rax
0x1800114fb  jz      loc_18001175F
0x180011501  xor     esi, esi
0x180011503  mov     [rdi+0A8h], rax
0x18001150a  xor     r15d, r15d
0x18001150d  mov     ebp, 0C000h
0x180011512  mov     rcx, [rdi+18h]; this
0x180011516  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x18001151b  test    eax, eax
0x18001151d  jnz     loc_180011751
0x180011523  mov     rcx, rdi; this
0x180011526  mov     dword ptr [rdi+0B4h], 8
0x180011530  call    ?SetEEInfoDrainFlag@HTTP2WinHttpTransportChannel@@AEAAXXZ; HTTP2WinHttpTransportChannel::SetEEInfoDrainFlag(void)
0x180011535  mov     r8, [rdi+48h]
0x180011539  mov     dl, 6Fh ; 'o'
0x18001153b  mov     [rsp+78h+var_48], r12d
0x180011540  mov     cl, 32h ; '2'
0x180011542  mov     [rsp+78h+var_50], r12d
0x180011547  mov     r9d, 18C0016h
0x18001154d  mov     [rsp+78h+var_58], r12d
0x180011552  call    cs:__imp_I_RpcLogEvent
0x180011558  mov     rcx, [rdi+48h]; hRequest
0x18001155c  xor     edx, edx; lpdwNumberOfBytesAvailable
0x18001155e  call    cs:__imp_WinHttpQueryDataAvailable
0x180011564  mov     rcx, [rdi+18h]; this
0x180011568  mov     ebx, eax
0x18001156a  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x18001156f  test    ebx, ebx
0x180011571  jz      short loc_18001158B
0x180011573  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011576  mov     rcx, r14; hHandle
0x180011579  call    cs:__imp_WaitForSingleObject
0x18001157f  cmp     [rdi+54h], r12d
0x180011583  jnz     loc_180011751
0x180011589  jmp     short loc_1800115A3
0x18001158b  call    cs:__imp_GetLastError
0x180011591  mov     [rdi+54h], eax
0x180011594  cmp     eax, 2EFEh
0x180011599  jnz     loc_180011751
0x18001159f  mov     [rdi+50h], r12
0x1800115a3  mov     ecx, [rdi+50h]; Size
0x1800115a6  test    ecx, ecx
0x1800115a8  jz      loc_180011698
0x1800115ae  cmp     ecx, ebp
0x1800115b0  ja      loc_180011751
0x1800115b6  lea     eax, [rcx+r15]
0x1800115ba  cmp     eax, ebp
0x1800115bc  ja      loc_180011751
0x1800115c2  test    rsi, rsi
0x1800115c5  jz      short loc_1800115F7
0x1800115c7  mov     ecx, eax; Size
0x1800115c9  mov     rbx, rsi
0x1800115cc  call    cs:__imp_I_RpcAllocate
0x1800115d2  mov     rsi, rax
0x1800115d5  test    rax, rax
0x1800115d8  jz      loc_180011690
0x1800115de  mov     r8d, r15d; Size
0x1800115e1  mov     rdx, rbx; Src
0x1800115e4  mov     rcx, rax; void *
0x1800115e7  call    memcpy_0
0x1800115ec  mov     rcx, rbx; Object
0x1800115ef  call    cs:__imp_I_RpcFree
0x1800115f5  jmp     short loc_180011609
0x1800115f7  call    cs:__imp_I_RpcAllocate
0x1800115fd  mov     rsi, rax
0x180011600  test    rax, rax
0x180011603  jz      loc_18001175F
0x180011609  mov     rcx, r14; hEvent
0x18001160c  mov     dword ptr [rdi+0B4h], 5
0x180011616  call    cs:__imp_ResetEvent
0x18001161c  mov     rcx, [rdi+18h]; this
0x180011620  call    ?BeginSimpleSubmitAsync@HTTP2Channel@@QEAAJXZ; HTTP2Channel::BeginSimpleSubmitAsync(void)
0x180011625  test    eax, eax
0x180011627  jnz     loc_180011756
0x18001162d  mov     eax, [rdi+50h]
0x180011630  mov     r9d, 1890016h
0x180011636  mov     r8, [rdi+48h]
0x18001163a  mov     dl, 6Fh ; 'o'
0x18001163c  mov     [rsp+78h+var_48], r12d
0x180011641  mov     cl, 32h ; '2'
0x180011643  mov     [rsp+78h+var_50], r12d
0x180011648  mov     [rsp+78h+var_58], eax
0x18001164c  call    cs:__imp_I_RpcLogEvent
0x180011652  mov     r8d, [rdi+50h]; dwNumberOfBytesToRead
0x180011656  xor     r9d, r9d; lpdwNumberOfBytesRead
0x180011659  mov     rcx, [rdi+48h]; hRequest
0x18001165d  mov     edx, r15d
0x180011660  add     rdx, rsi; lpBuffer
0x180011663  call    cs:__imp_WinHttpReadData
0x180011669  mov     rcx, [rdi+18h]; this
0x18001166d  call    ?FinishSubmitAsync@HTTP2Channel@@QEAAXXZ; HTTP2Channel::FinishSubmitAsync(void)
0x180011672  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011675  mov     rcx, r14; hHandle
0x180011678  call    cs:__imp_WaitForSingleObject
0x18001167e  add     r15d, [rdi+50h]
0x180011682  mov     rcx, r14; hEvent
0x180011685  call    cs:__imp_ResetEvent
0x18001168b  jmp     loc_180011512
0x180011690  mov     rsi, rbx
0x180011693  jmp     loc_180011756
0x180011698  mov     r8d, 0Bh; MaxCount
0x18001169e  cmp     r15d, r8d
0x1800116a1  jb      loc_180011751
0x1800116a7  lea     rdx, aRpcEeinfo; "RPC EEInfo:"
0x1800116ae  mov     rcx, rsi; String1
0x1800116b1  call    cs:__imp__strnicmp
0x1800116b7  test    eax, eax
0x1800116b9  jnz     loc_180011751
0x1800116bf  lea     rbp, [rsi+0Bh]
0x1800116c3  call    ?InitializeDecodingTableIfNecessary@@YAJXZ; InitializeDecodingTableIfNecessary(void)
0x1800116c8  test    eax, eax
0x1800116ca  jnz     loc_180011751
0x1800116d0  lea     edx, [r15-0Bh]
0x1800116d4  mov     rbx, rbp
0x1800116d7  add     rdx, rbp
0x1800116da  cmp     rbp, rdx
0x1800116dd  jnb     short loc_1800116F7
0x1800116df  mov     rcx, cs:?DecodingTable@@3PEAEEA; uchar * DecodingTable
0x1800116e6  movzx   eax, byte ptr [rbx]
0x1800116e9  cmp     byte ptr [rax+rcx], 40h ; '@'
0x1800116ed  jnb     short loc_1800116F7
0x1800116ef  inc     rbx
0x1800116f2  cmp     rbx, rdx
0x1800116f5  jb      short loc_1800116E6
0x1800116f7  sub     ebx, ebp
0x1800116f9  jz      short loc_180011751
0x1800116fb  lea     ecx, [rbx+2]; Size
0x1800116fe  call    cs:__imp_I_RpcAllocate
0x180011704  mov     r15, rax
0x180011707  test    rax, rax
0x18001170a  jz      short loc_180011751
0x18001170c  mov     r8d, ebx; unsigned int
0x18001170f  mov     rdx, rax; unsigned __int8 *
0x180011712  mov     rcx, rbp; unsigned __int8 *
0x180011715  call    ?RpcpBase64DecodeA@@YAKPEAE0KK@Z; RpcpBase64DecodeA(uchar *,uchar *,ulong,ulong)
0x18001171a  mov     edx, eax
0x18001171c  mov     rcx, r15
0x18001171f  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180011726  mov     rax, [rax+220h]
0x18001172d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011732  mov     rcx, r15; Object
0x180011735  call    cs:__imp_I_RpcFree
0x18001173b  xor     edx, edx; unsigned int
0x18001173d  mov     r8d, 69Ah; unsigned __int16
0x180011743  lea     ecx, [rdx+0Dh]; unsigned int
0x180011746  call    ?CompRpcpErrorAddRecord@@YAXKKG@Z; CompRpcpErrorAddRecord(ulong,ulong,ushort)
0x18001174b  mov     r12d, 1
0x180011751  test    rsi, rsi
0x180011754  jz      short loc_18001175F
0x180011756  mov     rcx, rsi; Object
0x180011759  call    cs:__imp_I_RpcFree
0x18001175f  mov     qword ptr [rdi+0A8h], 0
0x18001176a  test    r14, r14
0x18001176d  jz      short loc_180011778
0x18001176f  mov     rcx, r14; hObject
0x180011772  call    cs:__imp_CloseHandle
0x180011778  mov     eax, r12d
0x18001177b  add     rsp, 40h
0x18001177f  pop     r15
0x180011781  pop     r14
0x180011783  pop     r12
0x180011785  pop     rdi
0x180011786  pop     rsi
0x180011787  pop     rbp
0x180011788  pop     rbx
0x180011789  retn
```
