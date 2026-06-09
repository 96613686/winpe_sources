# get_pathname

- ea: `0x18000a038`
- end: `0x18000a170`
- name: `get_pathname`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180009e90`

## callees

- `0x18000a038`
- `0x18000d1c0`
- `0x18000e010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18000a138`
- `KERNEL32!MultiByteToWideChar` at `0x18000a138`
- `SHELL32!DragQueryFileW` at `0x18000a107`
- `SHELL32!DragQueryFileW` at `0x18000a107`
- `SHELL32!DragQueryFileA` at `0x18000a0e6`
- `SHELL32!DragQueryFileA` at `0x18000a116`
- `SHELL32!DragQueryFileA` at `0x18000a0e6`
- `SHELL32!DragQueryFileA` at `0x18000a116`

## pseudocode

```c
__int64 __fastcall get_pathname(__int64 *a1, WCHAR *a2)
{
  __int64 result; // rax
  __int64 v4; // rax
  __int64 (__fastcall *v5)(__int64 *, __int16 *, HDROP *); // rax
  HDROP v6; // rbx
  UINT FileW; // ebx
  __int16 v8; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+32h] [rbp-CEh]
  __int16 v10; // [rsp+36h] [rbp-CAh]
  __int64 v11; // [rsp+38h] [rbp-C8h]
  int v12; // [rsp+40h] [rbp-C0h]
  int v13; // [rsp+44h] [rbp-BCh]
  __int64 v14; // [rsp+48h] [rbp-B8h]
  HDROP hDrop[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  CHAR szFile[272]; // [rsp+70h] [rbp-90h] BYREF

  result = 0;
  *a2 = 0;
  if ( a1 )
  {
    v16 = 0;
    v9 = 0;
    v10 = 0;
    v14 = 1;
    v8 = 15;
    v4 = *a1;
    *(_OWORD *)hDrop = 0;
    v11 = 0;
    v12 = 1;
    v5 = *(__int64 (__fastcall **)(__int64 *, __int16 *, HDROP *))(v4 + 24);
    v13 = -1;
    result = v5(a1, &v8, hDrop);
    if ( (int)result >= 0 )
    {
      v6 = hDrop[1];
      if ( hDrop[1] && DragQueryFileA(hDrop[1], 0xFFFFFFFF, 0, 0) == 1 )
      {
        if ( Global::g_fWindowsNT )
        {
          FileW = DragQueryFileW(v6, 0, a2, 0x104u);
        }
        else
        {
          FileW = DragQueryFileA(v6, 0, szFile, 0x104u);
          MultiByteToWideChar(0, 0, szFile, -1, a2, 260);
        }
        return FileW == 0;
      }
      else
      {
        return 1;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a038  mov     [rsp-8+arg_10], rbx
0x18000a03d  mov     [rsp-8+arg_18], rdi
0x18000a042  push    rbp
0x18000a043  lea     rbp, [rsp-90h]
0x18000a04b  sub     rsp, 190h
0x18000a052  mov     rax, cs:__security_cookie
0x18000a059  xor     rax, rsp
0x18000a05c  mov     [rbp+90h+var_10], rax
0x18000a063  xor     eax, eax
0x18000a065  mov     rdi, rdx
0x18000a068  mov     [rdx], ax
0x18000a06b  test    rcx, rcx
0x18000a06e  jz      loc_18000A14C
0x18000a074  mov     [rsp+190h+var_130], rax
0x18000a079  lea     r8, [rsp+190h+hDrop]
0x18000a07e  mov     [rsp+190h+var_15E], eax
0x18000a082  lea     rdx, [rsp+190h+var_160]
0x18000a087  mov     [rsp+190h+var_15A], ax
0x18000a08c  xorps   xmm0, xmm0
0x18000a08f  mov     eax, 0Fh
0x18000a094  mov     [rsp+190h+var_148], 1
0x18000a09d  mov     [rsp+190h+var_160], ax
0x18000a0a2  mov     rax, [rcx]
0x18000a0a5  movups  xmmword ptr [rsp+190h+hDrop], xmm0
0x18000a0aa  mov     [rsp+190h+var_158], 0
0x18000a0b3  mov     [rsp+190h+var_150], 1
0x18000a0bb  mov     rax, [rax+18h]
0x18000a0bf  mov     [rsp+190h+var_14C], 0FFFFFFFFh
0x18000a0c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0cc  test    eax, eax
0x18000a0ce  js      short loc_18000A14C
0x18000a0d0  mov     rbx, [rsp+190h+hDrop+8]
0x18000a0d5  test    rbx, rbx
0x18000a0d8  jz      short loc_18000A147
0x18000a0da  xor     r9d, r9d; cch
0x18000a0dd  xor     r8d, r8d; lpszFile
0x18000a0e0  or      edx, 0FFFFFFFFh; iFile
0x18000a0e3  mov     rcx, rbx; hDrop
0x18000a0e6  call    cs:__imp_DragQueryFileA
0x18000a0ec  cmp     eax, 1
0x18000a0ef  jnz     short loc_18000A147
0x18000a0f1  xor     edx, edx; iFile
0x18000a0f3  mov     r9d, 104h; cch
0x18000a0f9  cmp     cs:?g_fWindowsNT@Global@@2_NA, dl; bool Global::g_fWindowsNT
0x18000a0ff  mov     rcx, rbx; hDrop
0x18000a102  jz      short loc_18000A111
0x18000a104  mov     r8, rdi; lpszFile
0x18000a107  call    cs:__imp_DragQueryFileW
0x18000a10d  mov     ebx, eax
0x18000a10f  jmp     short loc_18000A13E
0x18000a111  lea     r8, [rsp+190h+szFile]; lpszFile
0x18000a116  call    cs:__imp_DragQueryFileA
0x18000a11c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000a120  mov     [rsp+190h+cchWideChar], 104h; cchWideChar
0x18000a128  lea     r8, [rsp+190h+szFile]; lpMultiByteStr
0x18000a12d  mov     [rsp+190h+lpWideCharStr], rdi; lpWideCharStr
0x18000a132  xor     edx, edx; dwFlags
0x18000a134  xor     ecx, ecx; CodePage
0x18000a136  mov     ebx, eax
0x18000a138  call    cs:__imp_MultiByteToWideChar
0x18000a13e  xor     eax, eax
0x18000a140  test    ebx, ebx
0x18000a142  setz    al
0x18000a145  jmp     short loc_18000A14C
0x18000a147  mov     eax, 1
0x18000a14c  mov     rcx, [rbp+90h+var_10]
0x18000a153  xor     rcx, rsp; StackCookie
0x18000a156  call    __security_check_cookie
0x18000a15b  lea     r11, [rsp+190h+var_s0]
0x18000a163  mov     rbx, [r11+20h]
0x18000a167  mov     rdi, [r11+28h]
0x18000a16b  mov     rsp, r11
0x18000a16e  pop     rbp
0x18000a16f  retn
```
