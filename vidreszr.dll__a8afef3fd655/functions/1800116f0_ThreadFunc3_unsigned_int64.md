# ThreadFunc3(unsigned __int64)

- ea: `0x1800116f0`
- end: `0x18001181f`
- name: `?ThreadFunc3@@YAX_K@Z`
- size: `303`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800116f0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011749`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800117b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180011749`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800117b9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800117a4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001180e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800117a4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001180e`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180011722`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x180011722`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180011735`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x180011735`

## pseudocode

```c
DWORD __fastcall ThreadFunc3(LPVOID lpThreadParameter)
{
  void *v2; // rcx
  int v3; // eax
  DWORD result; // eax

  if ( lpThreadParameter )
  {
    v2 = (void *)*((_QWORD *)lpThreadParameter + 85);
    v3 = *((_DWORD *)lpThreadParameter + 33);
    if ( v2 )
    {
      if ( !v3 )
        AvRevertMmThreadCharacteristics(v2);
    }
    else if ( v3 )
    {
      *((_QWORD *)lpThreadParameter + 85) = AvSetMmThreadCharacteristicsW(
                                              (LPCWSTR)lpThreadParameter + 68,
                                              (LPDWORD)lpThreadParameter + 162);
    }
  }
  while ( 1 )
  {
    do
      result = WaitForSingleObject(*((HANDLE *)lpThreadParameter + 7), 0xFFFFFFFF);
    while ( result );
    if ( *((_DWORD *)lpThreadParameter + 30) )
      break;
    if ( *((_DWORD *)lpThreadParameter + 31) )
      (*((void (__fastcall **)(LPVOID, _QWORD, _QWORD))lpThreadParameter + 86))(
        lpThreadParameter,
        ((unsigned int)(3 * *((_DWORD *)lpThreadParameter + 178)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE,
        ((unsigned int)(4 * *((_DWORD *)lpThreadParameter + 178)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE);
    SetEvent(*((HANDLE *)lpThreadParameter + 8));
    while ( WaitForSingleObject(*((HANDLE *)lpThreadParameter + 7), 0xFFFFFFFF) )
      ;
    if ( *((_DWORD *)lpThreadParameter + 32) )
      (*((void (__fastcall **)(LPVOID, _QWORD, _QWORD))lpThreadParameter + 87))(
        lpThreadParameter,
        ((unsigned int)(3 * *((_DWORD *)lpThreadParameter + 180)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE,
        ((unsigned int)(4 * *((_DWORD *)lpThreadParameter + 180)) / *((_DWORD *)lpThreadParameter + 176)) & 0xFFFFFFFE);
    SetEvent(*((HANDLE *)lpThreadParameter + 8));
  }
  return result;
}

```

## disassembly

```asm
0x1800116f0  push    rbx
0x1800116f2  sub     rsp, 20h
0x1800116f6  mov     rbx, rcx
0x1800116f9  test    rcx, rcx
0x1800116fc  jz      short loc_180011740
0x1800116fe  mov     rcx, [rcx+2A8h]; AvrtHandle
0x180011705  mov     eax, [rbx+84h]
0x18001170b  test    rcx, rcx
0x18001170e  jnz     short loc_180011731
0x180011710  test    eax, eax
0x180011712  jz      short loc_180011740
0x180011714  lea     rdx, [rbx+288h]; TaskIndex
0x18001171b  lea     rcx, [rbx+88h]; TaskName
0x180011722  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x180011728  mov     [rbx+2A8h], rax
0x18001172f  jmp     short loc_180011740
0x180011731  test    eax, eax
0x180011733  jnz     short loc_180011740
0x180011735  call    cs:__imp_AvRevertMmThreadCharacteristics
0x18001173b  nop     dword ptr [rax+rax+00h]
0x180011740  mov     rcx, [rbx+38h]; hHandle
0x180011744  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180011749  call    cs:__imp_WaitForSingleObject
0x18001174f  test    eax, eax
0x180011751  jnz     short loc_180011740
0x180011753  cmp     [rbx+78h], eax
0x180011756  jnz     loc_180011819
0x18001175c  cmp     [rbx+7Ch], eax
0x18001175f  jz      short loc_1800117A0
0x180011761  mov     ecx, [rbx+2C8h]
0x180011767  xor     edx, edx
0x180011769  mov     r8d, [rbx+2C0h]
0x180011770  lea     eax, ds:0[rcx*4]
0x180011777  div     r8d
0x18001177a  xor     edx, edx
0x18001177c  mov     r9d, eax
0x18001177f  lea     eax, [rcx+rcx*2]
0x180011782  div     r8d
0x180011785  and     r9d, 0FFFFFFFEh
0x180011789  mov     rcx, rbx
0x18001178c  and     eax, 0FFFFFFFEh
0x18001178f  mov     r8d, r9d
0x180011792  mov     edx, eax
0x180011794  mov     rax, [rbx+2B0h]
0x18001179b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a0  mov     rcx, [rbx+40h]; hEvent
0x1800117a4  call    cs:__imp_SetEvent
0x1800117aa  nop     word ptr [rax+rax+00h]
0x1800117b0  mov     rcx, [rbx+38h]; hHandle
0x1800117b4  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800117b9  call    cs:__imp_WaitForSingleObject
0x1800117bf  test    eax, eax
0x1800117c1  jnz     short loc_1800117B0
0x1800117c3  cmp     [rbx+80h], eax
0x1800117c9  jz      short loc_18001180A
0x1800117cb  mov     ecx, [rbx+2D0h]
0x1800117d1  xor     edx, edx
0x1800117d3  mov     r8d, [rbx+2C0h]
0x1800117da  lea     eax, ds:0[rcx*4]
0x1800117e1  div     r8d
0x1800117e4  xor     edx, edx
0x1800117e6  mov     r9d, eax
0x1800117e9  lea     eax, [rcx+rcx*2]
0x1800117ec  div     r8d
0x1800117ef  and     r9d, 0FFFFFFFEh
0x1800117f3  mov     rcx, rbx
0x1800117f6  and     eax, 0FFFFFFFEh
0x1800117f9  mov     r8d, r9d
0x1800117fc  mov     edx, eax
0x1800117fe  mov     rax, [rbx+2B8h]
0x180011805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001180a  mov     rcx, [rbx+40h]; hEvent
0x18001180e  call    cs:__imp_SetEvent
0x180011814  jmp     loc_180011740
0x180011819  add     rsp, 20h
0x18001181d  pop     rbx
0x18001181e  retn
```
