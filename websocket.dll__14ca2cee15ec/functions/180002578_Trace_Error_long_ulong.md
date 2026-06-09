# Trace::Error(long,ulong,...)

- ea: `0x180002578`
- end: `0x1800026ac`
- name: `?Error@Trace@@SAJJKZZ`
- size: `308`
- prototype: `static int(int, unsigned int, ...)`
- caller_count: `26`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800093c4`
- `0x180009710`
- `0x180009780`
- `0x180009800`
- `0x180009870`
- `0x1800098e0`
- `0x1800099e0`
- `0x180009a50`
- `0x18000a13c`
- `0x18000a2cc`
- `0x18000a438`
- `0x18000a78c`
- `0x18000a8a0`
- `0x18000abd0`
- `0x18000ac20`
- `0x18000b194`
- `0x18000b4f4`
- `0x18000b8d8`
- `0x18000bb2c`
- `0x18000c030`
- `0x18000c300`
- `0x18000c8f0`
- `0x18000d174`
- `0x18000d51c`
- `0x18000d7b8`
- `0x18000d954`

## callees

- `0x180001670`
- `0x180002578`
- `0x180002a00`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800025fd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800025fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002607`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000268c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000268c`

## pseudocode

```c
__int64 Trace::Error(unsigned int a1, DWORD a2, ...)
{
  DWORD LastError; // edi
  __int64 v4; // r8
  const wchar_t *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int v9; // [rsp+48h] [rbp-19h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-11h] BYREF
  WCHAR Buffer[4]; // [rsp+58h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+60h] [rbp-1h] BYREF
  const wchar_t *v13; // [rsp+70h] [rbp+Fh]
  int v14; // [rsp+78h] [rbp+17h]
  int v15; // [rsp+7Ch] [rbp+1Bh]
  int *v16; // [rsp+80h] [rbp+1Fh]
  __int64 v17; // [rsp+88h] [rbp+27h]
  __int64 v18; // [rsp+D8h] [rbp+77h] BYREF
  va_list va; // [rsp+D8h] [rbp+77h]
  va_list va1; // [rsp+E0h] [rbp+7Fh] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v18 = va_arg(va1, _QWORD);
  *(_QWORD *)Buffer = 0;
  Arguments = 0;
  if ( Trace::s_fInitialized && (Microsoft_Windows_Websocket_Protocol_ComponentEnableBits & 1) != 0 )
  {
    va_copy(Arguments, va);
    LastError = 0;
    if ( !FormatMessageW(0x900u, Trace::s_hModule, a2, 0x400u, Buffer, 0, &Arguments) )
      LastError = GetLastError();
    Arguments = 0;
    if ( !LastError && (Microsoft_Windows_Websocket_Protocol_ComponentEnableBits & 1) != 0 )
    {
      v5 = *(const wchar_t **)Buffer;
      v9 = a1;
      if ( *(_QWORD *)Buffer )
      {
        v6 = -1;
        do
          ++v6;
        while ( *(_WORD *)(*(_QWORD *)Buffer + 2 * v6) );
        v7 = (unsigned int)(2 * v6 + 2);
      }
      else
      {
        v5 = L"NULL";
        v7 = 10;
      }
      v13 = v5;
      v14 = v7;
      v16 = (int *)&v9;
      v15 = 0;
      v17 = 4;
      McGenEventWrite_EventWriteTransfer(v7, (const EVENT_DESCRIPTOR *)WSPC_OPERATION_ERROR, v4, 3u, &v12);
    }
    if ( *(_QWORD *)Buffer )
      LocalFree(*(HLOCAL *)Buffer);
  }
  return a1;
}

```

## disassembly

```asm
0x180002578  mov     rax, rsp
0x18000257b  mov     [rax+10h], edx
0x18000257e  mov     [rax+18h], r8
0x180002582  mov     [rax+20h], r9
0x180002586  push    rbp
0x180002587  push    rbx
0x180002588  push    rsi
0x180002589  push    rdi
0x18000258a  lea     rbp, [rax-5Fh]
0x18000258e  sub     rsp, 98h
0x180002595  mov     rax, cs:__security_cookie
0x18000259c  xor     rax, rsp
0x18000259f  mov     [rbp+57h+var_28], rax
0x1800025a3  xor     esi, esi
0x1800025a5  mov     ebx, ecx
0x1800025a7  cmp     cs:?s_fInitialized@Trace@@0HA, esi; int Trace::s_fInitialized
0x1800025ad  mov     qword ptr [rbp+57h+Buffer], rsi
0x1800025b1  mov     [rbp+57h+Arguments], rsi
0x1800025b5  jz      loc_180002692
0x1800025bb  test    cs:Microsoft_Windows_Websocket_Protocol_ComponentEnableBits, 1
0x1800025c2  jz      loc_180002692
0x1800025c8  lea     rax, [rbp+57h+arg_10]
0x1800025cc  mov     r8d, edx; dwMessageId
0x1800025cf  mov     rdx, cs:?s_hModule@Trace@@0PEAUHINSTANCE__@@EA; lpSource
0x1800025d6  mov     r9d, 400h; dwLanguageId
0x1800025dc  mov     [rbp+57h+Arguments], rax
0x1800025e0  mov     ecx, 900h; dwFlags
0x1800025e5  lea     rax, [rbp+57h+Arguments]
0x1800025e9  mov     edi, esi
0x1800025eb  mov     [rsp+30h], rax; Arguments
0x1800025f0  lea     rax, [rbp+57h+Buffer]
0x1800025f4  mov     [rsp+0B0h+nSize], esi; nSize
0x1800025f8  mov     [rsp+0B0h+lpBuffer], rax; lpBuffer
0x1800025fd  call    cs:__imp_FormatMessageW
0x180002603  test    eax, eax
0x180002605  jnz     short loc_18000260F
0x180002607  call    cs:__imp_GetLastError
0x18000260d  mov     edi, eax
0x18000260f  mov     [rbp+57h+Arguments], rsi
0x180002613  test    edi, edi
0x180002615  jnz     short loc_180002683
0x180002617  test    cs:Microsoft_Windows_Websocket_Protocol_ComponentEnableBits, 1
0x18000261e  jz      short loc_180002683
0x180002620  mov     rax, qword ptr [rbp+57h+Buffer]
0x180002624  mov     [rbp+57h+var_70], ebx
0x180002627  test    rax, rax
0x18000262a  jz      short loc_180002642
0x18000262c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180002630  inc     rcx
0x180002633  cmp     [rax+rcx*2], si
0x180002637  jnz     short loc_180002630
0x180002639  lea     ecx, ds:2[rcx*2]
0x180002640  jmp     short loc_18000264E
0x180002642  lea     rax, aNull; "NULL"
0x180002649  mov     ecx, 0Ah
0x18000264e  mov     [rbp+57h+var_48], rax
0x180002652  lea     rdx, WSPC_OPERATION_ERROR
0x180002659  lea     rax, [rbp+57h+var_70]
0x18000265d  mov     [rbp+57h+var_40], ecx
0x180002660  mov     [rbp+57h+var_38], rax
0x180002664  mov     r9d, 3
0x18000266a  lea     rax, [rbp+57h+var_58]
0x18000266e  mov     [rbp+57h+var_3C], esi
0x180002671  mov     [rsp+0B0h+lpBuffer], rax
0x180002676  mov     [rbp+57h+var_30], 4
0x18000267e  call    McGenEventWrite_EventWriteTransfer
0x180002683  mov     rcx, qword ptr [rbp+57h+Buffer]; hMem
0x180002687  test    rcx, rcx
0x18000268a  jz      short loc_180002692
0x18000268c  call    cs:__imp_LocalFree
0x180002692  mov     eax, ebx
0x180002694  mov     rcx, [rbp+57h+var_28]
0x180002698  xor     rcx, rsp; StackCookie
0x18000269b  call    __security_check_cookie
0x1800026a0  add     rsp, 98h
0x1800026a7  pop     rdi
0x1800026a8  pop     rsi
0x1800026a9  pop     rbx
0x1800026aa  pop     rbp
0x1800026ab  retn
```
