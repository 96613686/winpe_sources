# TraceUpdateConsoleOwner

- ea: `0x1800026d0`
- end: `0x1800027a3`
- name: `TraceUpdateConsoleOwner`
- size: `211`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180001010`
- `0x180001fa0`
- `0x180005e98`
- `0x180009838`

## callees

- `0x1800026d0`
- `0x180003530`

## import_xrefs

- `api-ms-win-core-console-l2-1-0!SetConsoleActiveScreenBuffer` at `0x18000275b`
- `api-ms-win-core-console-l2-1-0!SetConsoleActiveScreenBuffer` at `0x18000275b`

## pseudocode

```c
__int64 __fastcall TraceUpdateConsoleOwner(__int64 a1, int a2)
{
  __int64 v2; // r8
  __int64 v3; // rdi
  __int64 v5; // r10
  int v6; // ecx
  __int64 v7; // rbx

  v2 = *(unsigned int *)(a1 + 64);
  v3 = 0;
  if ( (_DWORD)v2 == 60 )
    v5 = 0;
  else
    v5 = *(_QWORD *)(a1 + 8 * v2 + 352);
  v6 = 0;
  v7 = ((int)v2 + a2 + 60) % 0x3Cu;
  while ( (_DWORD)v7 != (_DWORD)v2 )
  {
    v3 = *(_QWORD *)(a1 + 8 * v7 + 352);
    if ( v3 && (*(_BYTE *)(v3 + 56) & 4) != 0 )
      goto LABEL_11;
    ++v6;
    v7 = (a2 + (int)v7 + 60) % 0x3Cu;
    if ( v6 >= 60 )
      break;
  }
  if ( v3 && (*(_BYTE *)(v3 + 56) & 4) != 0 )
  {
LABEL_11:
    SetConsoleActiveScreenBuffer(*(HANDLE *)(v3 + 264));
    *(_DWORD *)(a1 + 64) = v7;
    TraceUpdateConsoleTitleA(v3);
    return 0;
  }
  if ( !v5 || (*(_BYTE *)(v5 + 56) & 4) == 0 )
    *(_DWORD *)(a1 + 64) = 60;
  return 0;
}

```

## disassembly

```asm
0x1800026d0  mov     [rsp+arg_0], rbx
0x1800026d5  mov     [rsp+arg_8], rsi
0x1800026da  push    rdi
0x1800026db  sub     rsp, 20h
0x1800026df  mov     r8d, [rcx+40h]
0x1800026e3  xor     edi, edi
0x1800026e5  mov     r9d, edx
0x1800026e8  mov     rsi, rcx
0x1800026eb  cmp     r8d, 3Ch ; '<'
0x1800026ef  jz      short loc_1800026FB
0x1800026f1  mov     r10, [rcx+r8*8+160h]
0x1800026f9  jmp     short loc_1800026FE
0x1800026fb  xor     r10d, r10d
0x1800026fe  lea     ebx, [rdx+3Ch]
0x180002701  mov     eax, 88888889h
0x180002706  add     ebx, r8d
0x180002709  xor     ecx, ecx
0x18000270b  mul     ebx
0x18000270d  shr     edx, 5
0x180002710  imul    eax, edx, 3Ch ; '<'
0x180002713  sub     ebx, eax
0x180002715  cmp     ebx, r8d
0x180002718  jz      short loc_180002749
0x18000271a  mov     rdi, [rsi+rbx*8+160h]
0x180002722  test    rdi, rdi
0x180002725  jz      short loc_18000272D
0x180002727  test    byte ptr [rdi+38h], 4
0x18000272b  jnz     short loc_180002754
0x18000272d  add     ebx, 3Ch ; '<'
0x180002730  mov     eax, 88888889h
0x180002735  add     ebx, r9d
0x180002738  inc     ecx
0x18000273a  mul     ebx
0x18000273c  shr     edx, 5
0x18000273f  imul    eax, edx, 3Ch ; '<'
0x180002742  sub     ebx, eax
0x180002744  cmp     ecx, 3Ch ; '<'
0x180002747  jl      short loc_180002715
0x180002749  test    rdi, rdi
0x18000274c  jz      short loc_18000277E
0x18000274e  test    byte ptr [rdi+38h], 4
0x180002752  jz      short loc_18000277E
0x180002754  mov     rcx, [rdi+108h]; hConsoleOutput
0x18000275b  call    cs:__imp_SetConsoleActiveScreenBuffer
0x180002761  mov     rcx, rdi
0x180002764  mov     [rsi+40h], ebx
0x180002767  call    TraceUpdateConsoleTitleA
0x18000276c  xor     eax, eax
0x18000276e  mov     rbx, [rsp+28h+arg_0]
0x180002773  mov     rsi, [rsp+28h+arg_8]
0x180002778  add     rsp, 20h
0x18000277c  pop     rdi
0x18000277d  retn
0x18000277e  test    r10, r10
0x180002781  jz      short loc_18000278A
0x180002783  test    byte ptr [r10+38h], 4
0x180002788  jnz     short loc_180002791
0x18000278a  mov     dword ptr [rsi+40h], 3Ch ; '<'
0x180002791  mov     rbx, [rsp+28h+arg_0]
0x180002796  xor     eax, eax
0x180002798  mov     rsi, [rsp+28h+arg_8]
0x18000279d  add     rsp, 20h
0x1800027a1  pop     rdi
0x1800027a2  retn
```
