# ThreadFunc2(unsigned __int64)

- ea: `0x1800115b0`
- end: `0x1800116db`
- name: `?ThreadFunc2@@YAX_K@Z`
- size: `299`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800115b0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011609`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011679`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011609`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011679`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011660`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800116ca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011660`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800116ca`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800115e2`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800115e2`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800115f5`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800115f5`

## pseudocode

```c
DWORD __fastcall ThreadFunc2(LPVOID lpThreadParameter)
{
  void *v2; // rcx
  int v3; // eax
  DWORD result; // eax

  if ( lpThreadParameter )
  {
    v2 = (void *)*((_QWORD *)lpThreadParameter + 84);
    v3 = *((_DWORD *)lpThreadParameter + 33);
    if ( v2 )
    {
      if ( !v3 )
        AvRevertMmThreadCharacteristics(v2);
    }
    else if ( v3 )
    {
      *((_QWORD *)lpThreadParameter + 84) = AvSetMmThreadCharacteristicsW(
                                              (LPCWSTR)lpThreadParameter + 68,
                                              (LPDWORD)lpThreadParameter + 162);
    }
  }
  while ( 1 )
  {
    do
      result = WaitForSingleObject(*((HANDLE *)lpThreadParameter + 5), 0xFFFFFFFF);
    while ( result );
    if ( *((_DWORD *)lpThreadParameter + 30) )
      break;
    if ( *((_DWORD *)lpThreadParameter + 31) )
      (*((void (__fastcall **)(LPVOID, _QWORD, _QWORD))lpThreadParameter + 86))(
        lpThreadParameter,
        ((unsigned int)(2 * *((_DWORD *)lpThreadParameter + 178)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE,
        ((unsigned int)(3 * *((_DWORD *)lpThreadParameter + 178)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE);
    SetEvent(*((HANDLE *)lpThreadParameter + 6));
    while ( WaitForSingleObject(*((HANDLE *)lpThreadParameter + 5), 0xFFFFFFFF) )
      ;
    if ( *((_DWORD *)lpThreadParameter + 32) )
      (*((void (__fastcall **)(LPVOID, _QWORD, _QWORD))lpThreadParameter + 87))(
        lpThreadParameter,
        ((unsigned int)(2 * *((_DWORD *)lpThreadParameter + 180)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE,
        ((unsigned int)(3 * *((_DWORD *)lpThreadParameter + 180)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE);
    SetEvent(*((HANDLE *)lpThreadParameter + 6));
  }
  return result;
}

```

## disassembly

```asm
0x1800115b0  push    rbx
0x1800115b2  sub     rsp, 20h
0x1800115b6  mov     rbx, rcx
0x1800115b9  test    rcx, rcx
0x1800115bc  jz      short loc_180011600
0x1800115be  mov     rcx, [rcx+2A0h]; AvrtHandle
0x1800115c5  mov     eax, [rbx+84h]
0x1800115cb  test    rcx, rcx
0x1800115ce  jnz     short loc_1800115F1
0x1800115d0  test    eax, eax
0x1800115d2  jz      short loc_180011600
0x1800115d4  lea     rdx, [rbx+288h]; TaskIndex
0x1800115db  lea     rcx, [rbx+88h]; TaskName
0x1800115e2  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1800115e8  mov     [rbx+2A0h], rax
0x1800115ef  jmp     short loc_180011600
0x1800115f1  test    eax, eax
0x1800115f3  jnz     short loc_180011600
0x1800115f5  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1800115fb  nop     dword ptr [rax+rax+00h]
0x180011600  mov     rcx, [rbx+28h]; hHandle
0x180011604  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180011609  call    cs:__imp_WaitForSingleObject
0x18001160f  test    eax, eax
0x180011611  jnz     short loc_180011600
0x180011613  cmp     [rbx+78h], eax
0x180011616  jnz     loc_1800116D5
0x18001161c  cmp     [rbx+7Ch], eax
0x18001161f  jz      short loc_18001165C
0x180011621  mov     ecx, [rbx+2C8h]
0x180011627  xor     edx, edx
0x180011629  mov     r8d, [rbx+2C0h]
0x180011630  lea     eax, [rcx+rcx*2]
0x180011633  div     r8d
0x180011636  xor     edx, edx
0x180011638  mov     r9d, eax
0x18001163b  lea     eax, [rcx+rcx]
0x18001163e  div     r8d
0x180011641  and     r9d, 0FFFFFFFEh
0x180011645  mov     rcx, rbx
0x180011648  and     eax, 0FFFFFFFEh
0x18001164b  mov     r8d, r9d
0x18001164e  mov     edx, eax
0x180011650  mov     rax, [rbx+2B0h]
0x180011657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001165c  mov     rcx, [rbx+30h]; hEvent
0x180011660  call    cs:__imp_SetEvent
0x180011666  nop     word ptr [rax+rax+00000000h]
0x180011670  mov     rcx, [rbx+28h]; hHandle
0x180011674  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180011679  call    cs:__imp_WaitForSingleObject
0x18001167f  test    eax, eax
0x180011681  jnz     short loc_180011670
0x180011683  cmp     [rbx+80h], eax
0x180011689  jz      short loc_1800116C6
0x18001168b  mov     ecx, [rbx+2D0h]
0x180011691  xor     edx, edx
0x180011693  mov     r8d, [rbx+2C0h]
0x18001169a  lea     eax, [rcx+rcx*2]
0x18001169d  div     r8d
0x1800116a0  xor     edx, edx
0x1800116a2  mov     r9d, eax
0x1800116a5  lea     eax, [rcx+rcx]
0x1800116a8  div     r8d
0x1800116ab  and     r9d, 0FFFFFFFEh
0x1800116af  mov     rcx, rbx
0x1800116b2  and     eax, 0FFFFFFFEh
0x1800116b5  mov     r8d, r9d
0x1800116b8  mov     edx, eax
0x1800116ba  mov     rax, [rbx+2B8h]
0x1800116c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116c6  mov     rcx, [rbx+30h]; hEvent
0x1800116ca  call    cs:__imp_SetEvent
0x1800116d0  jmp     loc_180011600
0x1800116d5  add     rsp, 20h
0x1800116d9  pop     rbx
0x1800116da  retn
```
