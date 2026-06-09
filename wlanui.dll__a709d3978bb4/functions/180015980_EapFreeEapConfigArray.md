# EapFreeEapConfigArray

- ea: `0x180015980`
- end: `0x180015a3e`
- name: `EapFreeEapConfigArray`
- size: `190`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015020`
- `0x180015a44`

## callees

- `0x180015980`

## import_xrefs

- `MobileNetworking!FreeMemory` at `0x1800159c8`
- `MobileNetworking!FreeMemory` at `0x1800159f8`
- `MobileNetworking!FreeMemory` at `0x180015a21`
- `MobileNetworking!FreeMemory` at `0x1800159c8`
- `MobileNetworking!FreeMemory` at `0x1800159f8`
- `MobileNetworking!FreeMemory` at `0x180015a21`

## string_xrefs

- `0x1800159c1`: `EapFreeEapConfigArray`
- `0x1800159f1`: `EapFreeEapConfigArray`
- `0x180015a17`: `EapFreeEapConfigArray`

## pseudocode

```c
__int64 __fastcall EapFreeEapConfigArray(__int64 a1)
{
  _QWORD *v1; // rbx
  __int64 v3; // rsi
  _QWORD *v4; // rcx
  _QWORD *v5; // rcx
  __int64 result; // rax

  v1 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 8) && *(_DWORD *)(a1 + 4) )
  {
    v3 = 0;
    do
    {
      v4 = (_QWORD *)(*v1 + 16LL + 40 * v3);
      if ( *v4 )
      {
        FreeMemory(v4, "EapFreeEapConfigArray", 62);
        *(_QWORD *)(*v1 + 40 * v3 + 16) = 0;
      }
      v5 = (_QWORD *)(*v1 + 24LL + 40 * v3);
      if ( *v5 )
      {
        FreeMemory(v5, "EapFreeEapConfigArray", 67);
        *(_QWORD *)(*v1 + 40 * v3 + 16) = 0;
      }
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (unsigned int)v3 < *(_DWORD *)(a1 + 4) );
    result = FreeMemory(v1, "EapFreeEapConfigArray", 71);
    *v1 = 0;
    *(_DWORD *)(a1 + 4) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015980  push    rbx
0x180015982  push    rbp
0x180015983  push    rsi
0x180015984  push    rdi
0x180015985  sub     rsp, 28h
0x180015989  lea     rbx, [rcx+8]
0x18001598d  mov     rdi, rcx
0x180015990  cmp     qword ptr [rbx], 0
0x180015994  jz      loc_180015A35
0x18001599a  cmp     dword ptr [rcx+4], 0
0x18001599e  jbe     loc_180015A35
0x1800159a4  xor     esi, esi
0x1800159a6  mov     rcx, [rbx]
0x1800159a9  lea     rbp, [rsi+rsi*4]
0x1800159ad  add     rcx, 10h
0x1800159b1  lea     rcx, [rcx+rbp*8]
0x1800159b5  cmp     qword ptr [rcx], 0
0x1800159b9  jz      short loc_1800159DA
0x1800159bb  mov     r8d, 3Eh ; '>'
0x1800159c1  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x1800159c8  call    cs:__imp_FreeMemory
0x1800159ce  mov     rax, [rbx]
0x1800159d1  mov     qword ptr [rax+rbp*8+10h], 0
0x1800159da  mov     rcx, [rbx]
0x1800159dd  add     rcx, 18h
0x1800159e1  lea     rcx, [rcx+rbp*8]
0x1800159e5  cmp     qword ptr [rcx], 0
0x1800159e9  jz      short loc_180015A0A
0x1800159eb  mov     r8d, 43h ; 'C'
0x1800159f1  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x1800159f8  call    cs:__imp_FreeMemory
0x1800159fe  mov     rax, [rbx]
0x180015a01  mov     qword ptr [rax+rbp*8+10h], 0
0x180015a0a  inc     esi
0x180015a0c  cmp     esi, [rdi+4]
0x180015a0f  jb      short loc_1800159A6
0x180015a11  mov     r8d, 47h ; 'G'
0x180015a17  lea     rdx, aEapfreeeapconf; "EapFreeEapConfigArray"
0x180015a1e  mov     rcx, rbx
0x180015a21  call    cs:__imp_FreeMemory
0x180015a27  mov     qword ptr [rbx], 0
0x180015a2e  mov     dword ptr [rdi+4], 0
0x180015a35  add     rsp, 28h
0x180015a39  pop     rdi
0x180015a3a  pop     rsi
0x180015a3b  pop     rbp
0x180015a3c  pop     rbx
0x180015a3d  retn
```
