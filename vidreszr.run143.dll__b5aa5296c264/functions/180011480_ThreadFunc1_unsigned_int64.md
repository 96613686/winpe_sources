# ThreadFunc1(unsigned __int64)

- ea: `0x180011480`
- end: `0x1800115aa`
- name: `?ThreadFunc1@@YAX_K@Z`
- size: `298`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180011480`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800114d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011549`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800114d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011549`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001152f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011599`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001152f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011599`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800114b2`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800114b2`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800114c5`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800114c5`

## pseudocode

```c
DWORD __fastcall ThreadFunc1(LPVOID lpThreadParameter)
{
  void *v2; // rcx
  int v3; // eax
  DWORD result; // eax

  if ( lpThreadParameter )
  {
    v2 = (void *)*((_QWORD *)lpThreadParameter + 83);
    v3 = *((_DWORD *)lpThreadParameter + 33);
    if ( v2 )
    {
      if ( !v3 )
        AvRevertMmThreadCharacteristics(v2);
    }
    else if ( v3 )
    {
      *((_QWORD *)lpThreadParameter + 83) = AvSetMmThreadCharacteristicsW(
                                              (LPCWSTR)lpThreadParameter + 68,
                                              (LPDWORD)lpThreadParameter + 162);
    }
  }
  while ( 1 )
  {
    do
      result = WaitForSingleObject(*((HANDLE *)lpThreadParameter + 3), 0xFFFFFFFF);
    while ( result );
    if ( *((_DWORD *)lpThreadParameter + 30) )
      break;
    if ( *((_DWORD *)lpThreadParameter + 31) )
      (*((void (__fastcall **)(LPVOID, _QWORD, _QWORD))lpThreadParameter + 86))(
        lpThreadParameter,
        (*((_DWORD *)lpThreadParameter + 178) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE,
        ((unsigned int)(2 * *((_DWORD *)lpThreadParameter + 178)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE);
    SetEvent(*((HANDLE *)lpThreadParameter + 4));
    while ( WaitForSingleObject(*((HANDLE *)lpThreadParameter + 3), 0xFFFFFFFF) )
      ;
    if ( *((_DWORD *)lpThreadParameter + 32) )
      (*((void (__fastcall **)(LPVOID, _QWORD, _QWORD))lpThreadParameter + 87))(
        lpThreadParameter,
        (*((_DWORD *)lpThreadParameter + 180) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE,
        ((unsigned int)(2 * *((_DWORD *)lpThreadParameter + 180)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE);
    SetEvent(*((HANDLE *)lpThreadParameter + 4));
  }
  return result;
}

```

## disassembly

```asm
0x180011480  push    rbx
0x180011482  sub     rsp, 20h
0x180011486  mov     rbx, rcx
0x180011489  test    rcx, rcx
0x18001148c  jz      short loc_1800114D0
0x18001148e  mov     rcx, [rcx+298h]; AvrtHandle
0x180011495  mov     eax, [rbx+84h]
0x18001149b  test    rcx, rcx
0x18001149e  jnz     short loc_1800114C1
0x1800114a0  test    eax, eax
0x1800114a2  jz      short loc_1800114D0
0x1800114a4  lea     rdx, [rbx+288h]; TaskIndex
0x1800114ab  lea     rcx, [rbx+88h]; TaskName
0x1800114b2  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1800114b8  mov     [rbx+298h], rax
0x1800114bf  jmp     short loc_1800114D0
0x1800114c1  test    eax, eax
0x1800114c3  jnz     short loc_1800114D0
0x1800114c5  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1800114cb  nop     dword ptr [rax+rax+00h]
0x1800114d0  mov     rcx, [rbx+18h]; hHandle
0x1800114d4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800114d9  call    cs:__imp_WaitForSingleObject
0x1800114df  test    eax, eax
0x1800114e1  jnz     short loc_1800114D0
0x1800114e3  cmp     [rbx+78h], eax
0x1800114e6  jnz     loc_1800115A4
0x1800114ec  cmp     [rbx+7Ch], eax
0x1800114ef  jz      short loc_18001152B
0x1800114f1  mov     ecx, [rbx+2C8h]
0x1800114f7  xor     edx, edx
0x1800114f9  mov     r8d, [rbx+2C0h]
0x180011500  lea     eax, [rcx+rcx]
0x180011503  div     r8d
0x180011506  xor     edx, edx
0x180011508  mov     r9d, eax
0x18001150b  mov     eax, ecx
0x18001150d  div     r8d
0x180011510  and     r9d, 0FFFFFFFEh
0x180011514  mov     rcx, rbx
0x180011517  and     eax, 0FFFFFFFEh
0x18001151a  mov     r8d, r9d
0x18001151d  mov     edx, eax
0x18001151f  mov     rax, [rbx+2B0h]
0x180011526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001152b  mov     rcx, [rbx+20h]; hEvent
0x18001152f  call    cs:__imp_SetEvent
0x180011535  nop     word ptr [rax+rax+00000000h]
0x180011540  mov     rcx, [rbx+18h]; hHandle
0x180011544  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180011549  call    cs:__imp_WaitForSingleObject
0x18001154f  test    eax, eax
0x180011551  jnz     short loc_180011540
0x180011553  cmp     [rbx+80h], eax
0x180011559  jz      short loc_180011595
0x18001155b  mov     ecx, [rbx+2D0h]
0x180011561  xor     edx, edx
0x180011563  mov     r8d, [rbx+2C0h]
0x18001156a  lea     eax, [rcx+rcx]
0x18001156d  div     r8d
0x180011570  xor     edx, edx
0x180011572  mov     r9d, eax
0x180011575  mov     eax, ecx
0x180011577  div     r8d
0x18001157a  and     r9d, 0FFFFFFFEh
0x18001157e  mov     rcx, rbx
0x180011581  and     eax, 0FFFFFFFEh
0x180011584  mov     r8d, r9d
0x180011587  mov     edx, eax
0x180011589  mov     rax, [rbx+2B8h]
0x180011590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011595  mov     rcx, [rbx+20h]; hEvent
0x180011599  call    cs:__imp_SetEvent
0x18001159f  jmp     loc_1800114D0
0x1800115a4  add     rsp, 20h
0x1800115a8  pop     rbx
0x1800115a9  retn
```
