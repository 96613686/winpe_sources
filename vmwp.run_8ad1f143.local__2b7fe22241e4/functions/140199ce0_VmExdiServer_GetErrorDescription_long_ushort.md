# VmExdiServer::GetErrorDescription(long,ushort * *)

- ea: `0x140199ce0`
- end: `0x140199e9b`
- name: `?GetErrorDescription@VmExdiServer@@UEAAJJPEAPEAG@Z`
- size: `443`
- prototype: `__int64 __fastcall(VmExdiServer *__hidden this, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140199ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140199e7c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140199e7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140199e59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140199e59`

## string_xrefs

- `0x140199d89`: `No exception occured already, cannot return last.`
- `0x140199e03`: `The target was already running.`
- `0x140199dfa`: `The target was already halted.`
- `0x140199d7d`: `The target was not halted (before single step command issue).`
- `0x140199d95`: `Communication error between host driver and target.`
- `0x140199da1`: `Cannot proceed immediately because resource is already used by concurrent thread.`
- `0x140199d59`: `Access violation on at least one element in address range specified by the operation.`

## pseudocode

```c
__int64 __fastcall VmExdiServer::GetErrorDescription(VmExdiServer *this, int a2, unsigned __int16 **a3)
{
  const wchar_t *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rcx
  unsigned __int16 *v7; // rax

  if ( a2 > -528351222 )
  {
    switch ( a2 )
    {
      case -528351219:
        v4 = L"The server has reached its limit of connections and cannot accept any more.";
        goto LABEL_36;
      case -528351218:
        v4 = L"Failed to allocate necessary memory.";
        goto LABEL_36;
      case -528351145:
        v4 = L"One or more arguments are invalid.";
        goto LABEL_36;
      case -528334847:
        v4 = L"Not implemented.";
        goto LABEL_36;
      case -528334844:
        v4 = L"Operation aborted.";
        goto LABEL_36;
    }
    if ( a2 != -528334843 )
    {
      if ( a2 == 1619132419 )
      {
        v4 = L"The target was already running.";
        goto LABEL_36;
      }
      if ( a2 == 1619132420 )
      {
        v4 = L"The target was already halted.";
        goto LABEL_36;
      }
      goto LABEL_27;
    }
LABEL_30:
    v4 = L"Unspecified failure.";
    goto LABEL_36;
  }
  switch ( a2 )
  {
    case -528351222:
      v4 = L"Cannot proceed immediately because resource is already used by concurrent thread.";
      goto LABEL_36;
    case -2147467259:
      goto LABEL_30;
    case -528351231:
      v4 = L"Communication error between host driver and target.";
      goto LABEL_36;
    case -528351230:
      v4 = L"No exception occured already, cannot return last.";
      goto LABEL_36;
    case -528351227:
      v4 = L"The target was not halted (before single step command issue).";
      goto LABEL_36;
    case -528351226:
      v4 = L"No resource available, cannot instatiate breakpoint (in the kind requested).";
      goto LABEL_36;
    case -528351225:
      v4 = L"The external reset is not available programatically.";
      goto LABEL_36;
    case -528351224:
      v4 = L"Access violation on at least one element in address range specified by the operation.";
      goto LABEL_36;
  }
  if ( a2 != -528351223 )
  {
LABEL_27:
    v4 = L"Unknown Error.";
    goto LABEL_36;
  }
  v4 = L"Cannot proceed while target running. Operation not supported on the fly.";
LABEL_36:
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( v4[v6] );
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6 + 2);
  *a3 = v7;
  do
    ++v5;
  while ( v4[v5] );
  _o_wcscpy_s(v7, v5 + 1, v4);
  return 0;
}

```

## disassembly

```asm
0x140199ce0  mov     [rsp+arg_0], rbx
0x140199ce5  mov     [rsp+arg_8], rsi
0x140199cea  push    rdi
0x140199ceb  sub     rsp, 20h
0x140199cef  mov     eax, 0E082000Ah
0x140199cf4  mov     rsi, r8
0x140199cf7  cmp     edx, eax
0x140199cf9  jg      loc_140199DAD
0x140199cff  jz      loc_140199DA1
0x140199d05  cmp     edx, 80004005h
0x140199d0b  jz      loc_140199E0C
0x140199d11  cmp     edx, 0E0820001h
0x140199d17  jz      short loc_140199D95
0x140199d19  cmp     edx, 0E0820002h
0x140199d1f  jz      short loc_140199D89
0x140199d21  cmp     edx, 0E0820005h
0x140199d27  jz      short loc_140199D7D
0x140199d29  cmp     edx, 0E0820006h
0x140199d2f  jz      short loc_140199D71
0x140199d31  cmp     edx, 0E0820007h
0x140199d37  jz      short loc_140199D65
0x140199d39  cmp     edx, 0E0820008h
0x140199d3f  jz      short loc_140199D59
0x140199d41  cmp     edx, 0E0820009h
0x140199d47  jnz     loc_140199DF1
0x140199d4d  lea     rbx, aCannotProceedW; "Cannot proceed while target running. Op"...
0x140199d54  jmp     loc_140199E40
0x140199d59  lea     rbx, aAccessViolatio; "Access violation on at least one elemen"...
0x140199d60  jmp     loc_140199E40
0x140199d65  lea     rbx, aTheExternalRes; "The external reset is not available pro"...
0x140199d6c  jmp     loc_140199E40
0x140199d71  lea     rbx, aNoResourceAvai; "No resource available, cannot instatiat"...
0x140199d78  jmp     loc_140199E40
0x140199d7d  lea     rbx, aTheTargetWasNo; "The target was not halted (before singl"...
0x140199d84  jmp     loc_140199E40
0x140199d89  lea     rbx, aNoExceptionOcc; "No exception occured already, cannot re"...
0x140199d90  jmp     loc_140199E40
0x140199d95  lea     rbx, aCommunicationE; "Communication error between host driver"...
0x140199d9c  jmp     loc_140199E40
0x140199da1  lea     rbx, aCannotProceedI; "Cannot proceed immediately because reso"...
0x140199da8  jmp     loc_140199E40
0x140199dad  cmp     edx, 0E082000Dh
0x140199db3  jz      loc_140199E39
0x140199db9  cmp     edx, 0E082000Eh
0x140199dbf  jz      short loc_140199E30
0x140199dc1  cmp     edx, 0E0820057h
0x140199dc7  jz      short loc_140199E27
0x140199dc9  cmp     edx, 0E0824001h
0x140199dcf  jz      short loc_140199E1E
0x140199dd1  cmp     edx, 0E0824004h
0x140199dd7  jz      short loc_140199E15
0x140199dd9  cmp     edx, 0E0824005h
0x140199ddf  jz      short loc_140199E0C
0x140199de1  cmp     edx, 60820003h
0x140199de7  jz      short loc_140199E03
0x140199de9  cmp     edx, 60820004h
0x140199def  jz      short loc_140199DFA
0x140199df1  lea     rbx, aUnknownError_0; "Unknown Error."
0x140199df8  jmp     short loc_140199E40
0x140199dfa  lea     rbx, aTheTargetWasAl_0; "The target was already halted."
0x140199e01  jmp     short loc_140199E40
0x140199e03  lea     rbx, aTheTargetWasAl; "The target was already running."
0x140199e0a  jmp     short loc_140199E40
0x140199e0c  lea     rbx, aUnspecifiedFai; "Unspecified failure."
0x140199e13  jmp     short loc_140199E40
0x140199e15  lea     rbx, aOperationAbort; "Operation aborted."
0x140199e1c  jmp     short loc_140199E40
0x140199e1e  lea     rbx, aNotImplemented; "Not implemented."
0x140199e25  jmp     short loc_140199E40
0x140199e27  lea     rbx, aOneOrMoreArgum; "One or more arguments are invalid."
0x140199e2e  jmp     short loc_140199E40
0x140199e30  lea     rbx, aFailedToAlloca_0; "Failed to allocate necessary memory."
0x140199e37  jmp     short loc_140199E40
0x140199e39  lea     rbx, aTheServerHasRe; "The server has reached its limit of con"...
0x140199e40  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140199e44  mov     rcx, rdi
0x140199e47  inc     rcx
0x140199e4a  cmp     word ptr [rbx+rcx*2], 0
0x140199e4f  jnz     short loc_140199E47
0x140199e51  lea     rcx, ds:2[rcx*2]; cb
0x140199e59  call    cs:__imp_CoTaskMemAlloc
0x140199e60  nop     dword ptr [rax+rax+00h]
0x140199e65  mov     [rsi], rax
0x140199e68  inc     rdi
0x140199e6b  cmp     word ptr [rbx+rdi*2], 0
0x140199e70  jnz     short loc_140199E68
0x140199e72  lea     rdx, [rdi+1]
0x140199e76  mov     r8, rbx
0x140199e79  mov     rcx, rax
0x140199e7c  call    cs:__imp__o_wcscpy_s
0x140199e83  nop     dword ptr [rax+rax+00h]
0x140199e88  mov     rbx, [rsp+28h+arg_0]
0x140199e8d  xor     eax, eax
0x140199e8f  mov     rsi, [rsp+28h+arg_8]
0x140199e94  add     rsp, 20h
0x140199e98  pop     rdi
0x140199e99  retn
```
