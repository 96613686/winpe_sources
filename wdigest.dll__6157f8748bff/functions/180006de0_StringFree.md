# StringFree

- ea: `0x180006de0`
- end: `0x180006eb2`
- name: `StringFree`
- size: `210`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `27`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a50`
- `0x180004cb0`
- `0x180006260`
- `0x180007aa0`
- `0x180007ca0`
- `0x180008498`
- `0x1800087f4`
- `0x1800088b8`
- `0x18000cca0`
- `0x18001a4b4`
- `0x18001ad3c`
- `0x18001b4b0`
- `0x18001c8e0`
- `0x18001d5e8`
- `0x18001e218`
- `0x18001e4b0`
- `0x1800206d0`
- `0x18002552c`
- `0x180026020`
- `0x1800272f0`
- `0x180028ff0`
- `0x18002940c`
- `0x180029c98`
- `0x18002c364`
- `0x18002e180`
- `0x18002ea3c`
- `0x18002fb80`

## callees

- `0x180006de0`
- `0x1800192a8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e65`

## pseudocode

```c
__int64 __fastcall StringFree(__int64 a1)
{
  void *v2; // rdi
  __int64 result; // rax

  if ( !a1 )
    return 0;
  v2 = *(void **)(a1 + 8);
  if ( !v2 )
    return 0;
  if ( g_NtDigestState == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v2);
    (*(void (__fastcall **)(void *))(*(_QWORD *)&g_LsaFunctions + 48LL))(v2);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_5a1eec0057703498b5d13460810c8614_Traceguids, v2);
    LocalFree(v2);
  }
  result = 0;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180006de0  push    rbx
0x180006de2  sub     rsp, 20h
0x180006de6  mov     rbx, rcx
0x180006de9  test    rcx, rcx
0x180006dec  jz      loc_180006EAE
0x180006df2  mov     [rsp+28h+arg_0], rdi
0x180006df7  mov     rdi, [rcx+8]
0x180006dfb  test    rdi, rdi
0x180006dfe  jz      loc_180006EAA
0x180006e04  cmp     cs:g_NtDigestState, 1
0x180006e0b  jnz     short loc_180006E4F
0x180006e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e14  lea     rax, WPP_GLOBAL_Control
0x180006e1b  cmp     rcx, rax
0x180006e1e  jz      short loc_180006E29
0x180006e20  test    dword ptr [rcx+1Ch], 100h
0x180006e27  jnz     short loc_180006E6D
0x180006e29  mov     rax, cs:g_LsaFunctions
0x180006e30  mov     rcx, rdi
0x180006e33  mov     rax, [rax+30h]
0x180006e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3c  xor     eax, eax
0x180006e3e  mov     [rbx], eax
0x180006e40  mov     [rbx+8], rax
0x180006e44  mov     rdi, [rsp+28h+arg_0]
0x180006e49  add     rsp, 20h
0x180006e4d  pop     rbx
0x180006e4e  retn
0x180006e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e56  lea     rax, WPP_GLOBAL_Control
0x180006e5d  cmp     rcx, rax
0x180006e60  jnz     short loc_180006E87
0x180006e62  mov     rcx, rdi; hMem
0x180006e65  call    cs:__imp_LocalFree
0x180006e6b  jmp     short loc_180006E3C
0x180006e6d  mov     rcx, [rcx+10h]
0x180006e71  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180006e78  mov     edx, 1Eh
0x180006e7d  mov     r9, rdi
0x180006e80  call    WPP_SF_q
0x180006e85  jmp     short loc_180006E29
0x180006e87  test    dword ptr [rcx+1Ch], 100h
0x180006e8e  jz      short loc_180006E62
0x180006e90  mov     rcx, [rcx+10h]
0x180006e94  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180006e9b  mov     edx, 1Fh
0x180006ea0  mov     r9, rdi
0x180006ea3  call    WPP_SF_q
0x180006ea8  jmp     short loc_180006E62
0x180006eaa  xor     eax, eax
0x180006eac  jmp     short loc_180006E44
0x180006eae  xor     eax, eax
0x180006eb0  jmp     short loc_180006E49
```
