# ThreadFunc0(unsigned __int64)

- ea: `0x180011380`
- end: `0x180011475`
- name: `?ThreadFunc0@@YAX_K@Z`
- size: `245`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011380`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800113d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011429`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800113d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011429`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001141a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011464`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001141a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011464`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800113b2`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800113b2`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800113c5`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800113c5`

## pseudocode

```c
DWORD __fastcall ThreadFunc0(LPVOID lpThreadParameter)
{
  void *v2; // rcx
  int v3; // eax
  DWORD result; // eax

  if ( lpThreadParameter )
  {
    v2 = (void *)*((_QWORD *)lpThreadParameter + 82);
    v3 = *((_DWORD *)lpThreadParameter + 33);
    if ( v2 )
    {
      if ( !v3 )
        AvRevertMmThreadCharacteristics(v2);
    }
    else if ( v3 )
    {
      *((_QWORD *)lpThreadParameter + 82) = AvSetMmThreadCharacteristicsW(
                                              (LPCWSTR)lpThreadParameter + 68,
                                              (LPDWORD)lpThreadParameter + 162);
    }
  }
  while ( 1 )
  {
    do
      result = WaitForSingleObject(*((HANDLE *)lpThreadParameter + 1), 0xFFFFFFFF);
    while ( result );
    if ( *((_DWORD *)lpThreadParameter + 30) )
      break;
    if ( *((_DWORD *)lpThreadParameter + 31) )
      (*((void (__fastcall **)(LPVOID, _QWORD, _QWORD))lpThreadParameter + 86))(
        lpThreadParameter,
        0,
        (*((_DWORD *)lpThreadParameter + 178) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE);
    SetEvent(*((HANDLE *)lpThreadParameter + 2));
    while ( WaitForSingleObject(*((HANDLE *)lpThreadParameter + 1), 0xFFFFFFFF) )
      ;
    if ( *((_DWORD *)lpThreadParameter + 32) )
      (*((void (__fastcall **)(LPVOID, _QWORD, _QWORD))lpThreadParameter + 87))(
        lpThreadParameter,
        0,
        (*((_DWORD *)lpThreadParameter + 180) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE);
    SetEvent(*((HANDLE *)lpThreadParameter + 2));
  }
  return result;
}

```

## disassembly

```asm
0x180011380  push    rbx
0x180011382  sub     rsp, 20h
0x180011386  mov     rbx, rcx
0x180011389  test    rcx, rcx
0x18001138c  jz      short loc_1800113D0
0x18001138e  mov     rcx, [rcx+290h]; AvrtHandle
0x180011395  mov     eax, [rbx+84h]
0x18001139b  test    rcx, rcx
0x18001139e  jnz     short loc_1800113C1
0x1800113a0  test    eax, eax
0x1800113a2  jz      short loc_1800113D0
0x1800113a4  lea     rdx, [rbx+288h]; TaskIndex
0x1800113ab  lea     rcx, [rbx+88h]; TaskName
0x1800113b2  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1800113b8  mov     [rbx+290h], rax
0x1800113bf  jmp     short loc_1800113D0
0x1800113c1  test    eax, eax
0x1800113c3  jnz     short loc_1800113D0
0x1800113c5  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1800113cb  nop     dword ptr [rax+rax+00h]
0x1800113d0  mov     rcx, [rbx+8]; hHandle
0x1800113d4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800113d9  call    cs:__imp_WaitForSingleObject
0x1800113df  test    eax, eax
0x1800113e1  jnz     short loc_1800113D0
0x1800113e3  cmp     [rbx+78h], eax
0x1800113e6  jnz     loc_18001146F
0x1800113ec  cmp     [rbx+7Ch], eax
0x1800113ef  jz      short loc_180011416
0x1800113f1  mov     eax, [rbx+2C8h]
0x1800113f7  xor     edx, edx
0x1800113f9  div     dword ptr [rbx+2C0h]
0x1800113ff  xor     edx, edx
0x180011401  mov     rcx, rbx
0x180011404  and     eax, 0FFFFFFFEh
0x180011407  mov     r8d, eax
0x18001140a  mov     rax, [rbx+2B0h]
0x180011411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011416  mov     rcx, [rbx+10h]; hEvent
0x18001141a  call    cs:__imp_SetEvent
0x180011420  mov     rcx, [rbx+8]; hHandle
0x180011424  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180011429  call    cs:__imp_WaitForSingleObject
0x18001142f  test    eax, eax
0x180011431  jnz     short loc_180011420
0x180011433  cmp     [rbx+80h], eax
0x180011439  jz      short loc_180011460
0x18001143b  mov     eax, [rbx+2D0h]
0x180011441  xor     edx, edx
0x180011443  div     dword ptr [rbx+2C0h]
0x180011449  xor     edx, edx
0x18001144b  mov     rcx, rbx
0x18001144e  and     eax, 0FFFFFFFEh
0x180011451  mov     r8d, eax
0x180011454  mov     rax, [rbx+2B8h]
0x18001145b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011460  mov     rcx, [rbx+10h]; hEvent
0x180011464  call    cs:__imp_SetEvent
0x18001146a  jmp     loc_1800113D0
0x18001146f  add     rsp, 20h
0x180011473  pop     rbx
0x180011474  retn
```
