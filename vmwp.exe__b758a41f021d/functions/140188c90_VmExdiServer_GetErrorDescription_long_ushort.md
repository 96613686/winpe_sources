# VmExdiServer::GetErrorDescription(long,ushort * *)

- ea: `0x140188c90`
- end: `0x140188e4b`
- name: `?GetErrorDescription@VmExdiServer@@UEAAJJPEAPEAG@Z`
- size: `443`
- prototype: `__int64 __fastcall(VmExdiServer *__hidden this, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140188c90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140188e2c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140188e2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140188e09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140188e09`

## string_xrefs

- `0x140188daa`: `The target was already halted.`
- `0x140188d2d`: `The target was not halted (before single step command issue).`
- `0x140188d45`: `Communication error between host driver and target.`
- `0x140188d39`: `No exception occured already, cannot return last.`
- `0x140188db3`: `The target was already running.`
- `0x140188d09`: `Access violation on at least one element in address range specified by the operation.`
- `0x140188d51`: `Cannot proceed immediately because resource is already used by concurrent thread.`

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
0x140188c90  mov     [rsp+arg_0], rbx
0x140188c95  mov     [rsp+arg_8], rsi
0x140188c9a  push    rdi
0x140188c9b  sub     rsp, 20h
0x140188c9f  mov     eax, 0E082000Ah
0x140188ca4  mov     rsi, r8
0x140188ca7  cmp     edx, eax
0x140188ca9  jg      loc_140188D5D
0x140188caf  jz      loc_140188D51
0x140188cb5  cmp     edx, 80004005h
0x140188cbb  jz      loc_140188DBC
0x140188cc1  cmp     edx, 0E0820001h
0x140188cc7  jz      short loc_140188D45
0x140188cc9  cmp     edx, 0E0820002h
0x140188ccf  jz      short loc_140188D39
0x140188cd1  cmp     edx, 0E0820005h
0x140188cd7  jz      short loc_140188D2D
0x140188cd9  cmp     edx, 0E0820006h
0x140188cdf  jz      short loc_140188D21
0x140188ce1  cmp     edx, 0E0820007h
0x140188ce7  jz      short loc_140188D15
0x140188ce9  cmp     edx, 0E0820008h
0x140188cef  jz      short loc_140188D09
0x140188cf1  cmp     edx, 0E0820009h
0x140188cf7  jnz     loc_140188DA1
0x140188cfd  lea     rbx, aCannotProceedW; "Cannot proceed while target running. Op"...
0x140188d04  jmp     loc_140188DF0
0x140188d09  lea     rbx, aAccessViolatio; "Access violation on at least one elemen"...
0x140188d10  jmp     loc_140188DF0
0x140188d15  lea     rbx, aTheExternalRes; "The external reset is not available pro"...
0x140188d1c  jmp     loc_140188DF0
0x140188d21  lea     rbx, aNoResourceAvai; "No resource available, cannot instatiat"...
0x140188d28  jmp     loc_140188DF0
0x140188d2d  lea     rbx, aTheTargetWasNo; "The target was not halted (before singl"...
0x140188d34  jmp     loc_140188DF0
0x140188d39  lea     rbx, aNoExceptionOcc; "No exception occured already, cannot re"...
0x140188d40  jmp     loc_140188DF0
0x140188d45  lea     rbx, aCommunicationE; "Communication error between host driver"...
0x140188d4c  jmp     loc_140188DF0
0x140188d51  lea     rbx, aCannotProceedI; "Cannot proceed immediately because reso"...
0x140188d58  jmp     loc_140188DF0
0x140188d5d  cmp     edx, 0E082000Dh
0x140188d63  jz      loc_140188DE9
0x140188d69  cmp     edx, 0E082000Eh
0x140188d6f  jz      short loc_140188DE0
0x140188d71  cmp     edx, 0E0820057h
0x140188d77  jz      short loc_140188DD7
0x140188d79  cmp     edx, 0E0824001h
0x140188d7f  jz      short loc_140188DCE
0x140188d81  cmp     edx, 0E0824004h
0x140188d87  jz      short loc_140188DC5
0x140188d89  cmp     edx, 0E0824005h
0x140188d8f  jz      short loc_140188DBC
0x140188d91  cmp     edx, 60820003h
0x140188d97  jz      short loc_140188DB3
0x140188d99  cmp     edx, 60820004h
0x140188d9f  jz      short loc_140188DAA
0x140188da1  lea     rbx, aUnknownError_0; "Unknown Error."
0x140188da8  jmp     short loc_140188DF0
0x140188daa  lea     rbx, aTheTargetWasAl_0; "The target was already halted."
0x140188db1  jmp     short loc_140188DF0
0x140188db3  lea     rbx, aTheTargetWasAl; "The target was already running."
0x140188dba  jmp     short loc_140188DF0
0x140188dbc  lea     rbx, aUnspecifiedFai; "Unspecified failure."
0x140188dc3  jmp     short loc_140188DF0
0x140188dc5  lea     rbx, aOperationAbort; "Operation aborted."
0x140188dcc  jmp     short loc_140188DF0
0x140188dce  lea     rbx, aNotImplemented; "Not implemented."
0x140188dd5  jmp     short loc_140188DF0
0x140188dd7  lea     rbx, aOneOrMoreArgum; "One or more arguments are invalid."
0x140188dde  jmp     short loc_140188DF0
0x140188de0  lea     rbx, aFailedToAlloca_0; "Failed to allocate necessary memory."
0x140188de7  jmp     short loc_140188DF0
0x140188de9  lea     rbx, aTheServerHasRe; "The server has reached its limit of con"...
0x140188df0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140188df4  mov     rcx, rdi
0x140188df7  inc     rcx
0x140188dfa  cmp     word ptr [rbx+rcx*2], 0
0x140188dff  jnz     short loc_140188DF7
0x140188e01  lea     rcx, ds:2[rcx*2]; cb
0x140188e09  call    cs:__imp_CoTaskMemAlloc
0x140188e10  nop     dword ptr [rax+rax+00h]
0x140188e15  mov     [rsi], rax
0x140188e18  inc     rdi
0x140188e1b  cmp     word ptr [rbx+rdi*2], 0
0x140188e20  jnz     short loc_140188E18
0x140188e22  lea     rdx, [rdi+1]
0x140188e26  mov     r8, rbx
0x140188e29  mov     rcx, rax
0x140188e2c  call    cs:__imp__o_wcscpy_s
0x140188e33  nop     dword ptr [rax+rax+00h]
0x140188e38  mov     rbx, [rsp+28h+arg_0]
0x140188e3d  xor     eax, eax
0x140188e3f  mov     rsi, [rsp+28h+arg_8]
0x140188e44  add     rsp, 20h
0x140188e48  pop     rdi
0x140188e49  retn
```
