# P2P_HASH_REQUEST::OnReceiveHashes(ulong)

- ea: `0x18008bb60`
- end: `0x18008bc66`
- name: `?OnReceiveHashes@P2P_HASH_REQUEST@@AEAAKK@Z`
- size: `262`
- prototype: `unsigned int __fastcall(P2P_HASH_REQUEST *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18008be30`

## callees

- `0x18008bb60`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bbb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bbb5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008bba0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008bba0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008bc4a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008bc4a`

## pseudocode

```c
DWORD __fastcall P2P_HASH_REQUEST::OnReceiveHashes(P2P_HASH_REQUEST *this, unsigned int a2)
{
  bool v2; // zf
  __int64 v3; // rdi
  DWORD result; // eax
  HANDLE EventW; // rax
  unsigned __int64 v7; // rdx
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  HANDLE hHandle[2]; // [rsp+40h] [rbp-18h]

  v2 = *((_QWORD *)this + 2) == 0;
  v8 = 0;
  v3 = a2;
  *(_OWORD *)hHandle = 0;
  if ( v2 )
    return 6;
  EventW = (HANDLE)*((_QWORD *)this + 12);
  if ( !EventW )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 12) = EventW;
    if ( !EventW )
      return GetLastError();
  }
  v7 = *((_QWORD *)this + 14);
  hHandle[1] = EventW;
  if ( (_DWORD)v3 )
  {
    *((_QWORD *)this + 14) = v7 + v3;
    if ( v7 > v7 + v3 )
      return 534;
    result = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, __int128 *))qword_1800AE638)(
               *(_QWORD *)(*((_QWORD *)this + 2) + 16LL),
               *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
               (unsigned int)v3,
               *((_QWORD *)this + 6),
               &v8);
  }
  else
  {
    if ( !v7 )
      return 1359;
    result = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int128 *))qword_1800AE640)(
               *(_QWORD *)(*((_QWORD *)this + 2) + 16LL),
               *(_QWORD *)(*((_QWORD *)this + 2) + 8LL),
               &v8);
  }
  if ( result == 997 )
  {
    WaitForSingleObject(hHandle[1], 0xFFFFFFFF);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18008bb60  mov     [rsp+arg_0], rbx
0x18008bb65  push    rdi
0x18008bb66  sub     rsp, 50h
0x18008bb6a  cmp     qword ptr [rcx+10h], 0
0x18008bb6f  xorps   xmm0, xmm0
0x18008bb72  movups  [rsp+58h+var_28], xmm0
0x18008bb77  mov     edi, edx
0x18008bb79  mov     rbx, rcx
0x18008bb7c  movups  xmmword ptr [rsp+58h+hHandle], xmm0
0x18008bb81  jnz     short loc_18008BB8D
0x18008bb83  mov     eax, 6
0x18008bb88  jmp     loc_18008BC5A
0x18008bb8d  mov     rax, [rcx+60h]
0x18008bb91  test    rax, rax
0x18008bb94  jnz     short loc_18008BBC6
0x18008bb96  xor     r9d, r9d; lpName
0x18008bb99  xor     r8d, r8d; bInitialState
0x18008bb9c  xor     edx, edx; bManualReset
0x18008bb9e  xor     ecx, ecx; lpEventAttributes
0x18008bba0  call    cs:__imp_CreateEventW
0x18008bba7  nop     dword ptr [rax+rax+00h]
0x18008bbac  mov     [rbx+60h], rax
0x18008bbb0  test    rax, rax
0x18008bbb3  jnz     short loc_18008BBC6
0x18008bbb5  call    cs:__imp_GetLastError
0x18008bbbc  nop     dword ptr [rax+rax+00h]
0x18008bbc1  jmp     loc_18008BC5A
0x18008bbc6  mov     rdx, [rbx+70h]
0x18008bbca  mov     [rsp+58h+hHandle+8], rax
0x18008bbcf  test    edi, edi
0x18008bbd1  jz      short loc_18008BC12
0x18008bbd3  lea     rcx, [rdx+rdi]
0x18008bbd7  mov     [rbx+70h], rcx
0x18008bbdb  cmp     rdx, rcx
0x18008bbde  jbe     short loc_18008BBE7
0x18008bbe0  mov     eax, 216h
0x18008bbe5  jmp     short loc_18008BC5A
0x18008bbe7  mov     rcx, [rbx+10h]
0x18008bbeb  lea     rax, [rsp+58h+var_28]
0x18008bbf0  mov     r9, [rbx+30h]
0x18008bbf4  mov     r8d, edi
0x18008bbf7  mov     [rsp+58h+var_38], rax
0x18008bbfc  mov     rax, cs:qword_1800AE638
0x18008bc03  mov     rdx, [rcx+8]
0x18008bc07  mov     rcx, [rcx+10h]
0x18008bc0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc10  jmp     short loc_18008BC3B
0x18008bc12  test    rdx, rdx
0x18008bc15  jnz     short loc_18008BC1E
0x18008bc17  mov     eax, 54Fh
0x18008bc1c  jmp     short loc_18008BC5A
0x18008bc1e  mov     rcx, [rbx+10h]
0x18008bc22  lea     r8, [rsp+58h+var_28]
0x18008bc27  mov     rax, cs:qword_1800AE640
0x18008bc2e  mov     rdx, [rcx+8]
0x18008bc32  mov     rcx, [rcx+10h]
0x18008bc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc3b  cmp     eax, 3E5h
0x18008bc40  jnz     short loc_18008BC5A
0x18008bc42  mov     rcx, [rsp+58h+hHandle+8]; hHandle
0x18008bc47  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18008bc4a  call    cs:__imp_WaitForSingleObject
0x18008bc51  nop     dword ptr [rax+rax+00h]
0x18008bc56  mov     eax, dword ptr [rsp+58h+var_28]
0x18008bc5a  mov     rbx, [rsp+58h+arg_0]
0x18008bc5f  add     rsp, 50h
0x18008bc63  pop     rdi
0x18008bc64  retn
```
