# DecompressQuery

- ea: `0x180002310`
- end: `0x1800023e3`
- name: `DecompressQuery`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cc0`
- `0x180002028`

## callees

- `0x180002310`
- `0x1800024dc`

## pseudocode

```c
__int64 __fastcall DecompressQuery(__int64 a1, _DWORD *a2, __int64 a3)
{
  int v6; // eax
  int v7; // ecx

  if ( !a2 )
    return 4294967294LL;
  if ( !(unsigned int)ValidateBitmapInfoHeader(a2) )
    return 4294967294LL;
  v6 = a2[4];
  if ( v6 != 825308249 && v6 != 842150995 && v6 != 961893977 && v6 != 808596564 )
    return 4294967294LL;
  v7 = 1;
  if ( (unsigned int)(a2[2] - 1) > 0x4E1F || (unsigned int)(a2[1] - 1) > 0x4E1F )
    return 4294967294LL;
  if ( !a3 )
    return 0;
  if ( *(_DWORD *)(a3 + 16) )
  {
    if ( *(_DWORD *)(a3 + 16) != 3
      || *(_WORD *)(a3 + 14) != 16
      || *(_DWORD *)(a3 + 40) != 63488
      || *(_DWORD *)(a3 + 44) != 2016
      || *(_DWORD *)(a3 + 48) != 31 )
    {
      return 4294967294LL;
    }
  }
  else
  {
    v7 = 0;
  }
  *(_DWORD *)(a1 + 16) = v7;
  if ( *(_DWORD *)(a3 + 4) == a2[1] && *(_DWORD *)(a3 + 8) == a2[2] && *(_WORD *)(a3 + 14) == 16 )
    return 0;
  return 4294967294LL;
}

```

## disassembly

```asm
0x180002310  mov     [rsp+arg_0], rbx
0x180002315  mov     [rsp+arg_8], rsi
0x18000231a  push    rdi
0x18000231b  sub     rsp, 20h
0x18000231f  mov     rbx, r8
0x180002322  mov     rdi, rdx
0x180002325  mov     rsi, rcx
0x180002328  test    rdx, rdx
0x18000232b  jz      loc_1800023CE
0x180002331  mov     rcx, rdx
0x180002334  call    ValidateBitmapInfoHeader
0x180002339  test    eax, eax
0x18000233b  jz      loc_1800023CE
0x180002341  mov     eax, [rdi+10h]
0x180002344  cmp     eax, 31313459h
0x180002349  jz      short loc_180002360
0x18000234b  cmp     eax, 32323453h
0x180002350  jz      short loc_180002360
0x180002352  cmp     eax, 39555659h
0x180002357  jz      short loc_180002360
0x180002359  cmp     eax, 30323454h
0x18000235e  jnz     short loc_1800023CE
0x180002360  mov     eax, [rdi+8]
0x180002363  mov     ecx, 1
0x180002368  sub     eax, ecx
0x18000236a  mov     edx, 4E1Fh
0x18000236f  cmp     eax, edx
0x180002371  ja      short loc_1800023CE
0x180002373  mov     eax, [rdi+4]
0x180002376  sub     eax, ecx
0x180002378  cmp     eax, edx
0x18000237a  ja      short loc_1800023CE
0x18000237c  test    rbx, rbx
0x18000237f  jnz     short loc_180002385
0x180002381  xor     eax, eax
0x180002383  jmp     short loc_1800023D3
0x180002385  cmp     dword ptr [rbx+10h], 0
0x180002389  jnz     short loc_18000238F
0x18000238b  xor     ecx, ecx
0x18000238d  jmp     short loc_1800023B4
0x18000238f  cmp     dword ptr [rbx+10h], 3
0x180002393  jnz     short loc_1800023CE
0x180002395  cmp     word ptr [rbx+0Eh], 10h
0x18000239a  jnz     short loc_1800023CE
0x18000239c  cmp     dword ptr [rbx+28h], 0F800h
0x1800023a3  jnz     short loc_1800023CE
0x1800023a5  cmp     dword ptr [rbx+2Ch], 7E0h
0x1800023ac  jnz     short loc_1800023CE
0x1800023ae  cmp     dword ptr [rbx+30h], 1Fh
0x1800023b2  jnz     short loc_1800023CE
0x1800023b4  mov     [rsi+10h], ecx
0x1800023b7  mov     eax, [rdi+4]
0x1800023ba  cmp     [rbx+4], eax
0x1800023bd  jnz     short loc_1800023CE
0x1800023bf  mov     eax, [rdi+8]
0x1800023c2  cmp     [rbx+8], eax
0x1800023c5  jnz     short loc_1800023CE
0x1800023c7  cmp     word ptr [rbx+0Eh], 10h
0x1800023cc  jz      short loc_180002381
0x1800023ce  mov     eax, 0FFFFFFFEh
0x1800023d3  mov     rbx, [rsp+28h+arg_0]
0x1800023d8  mov     rsi, [rsp+28h+arg_8]
0x1800023dd  add     rsp, 20h
0x1800023e1  pop     rdi
0x1800023e2  retn
```
