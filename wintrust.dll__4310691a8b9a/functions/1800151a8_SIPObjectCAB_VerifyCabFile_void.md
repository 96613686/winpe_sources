# SIPObjectCAB_::VerifyCabFile(void)

- ea: `0x1800151a8`
- end: `0x1800152ff`
- name: `?VerifyCabFile@SIPObjectCAB_@@AEAAHXZ`
- size: `343`
- prototype: `__int64 __fastcall(SIPObjectCAB_ *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800150b0`

## callees

- `0x180014f98`
- `0x1800151a8`
- `0x180015308`
- `0x180015444`
- `0x180015564`
- `0x18004deb0`

## import_xrefs

- `msvcrt!free` at `0x1800152b3`
- `msvcrt!free` at `0x1800152c3`
- `msvcrt!free` at `0x1800152b3`
- `msvcrt!free` at `0x1800152c3`
- `msvcrt!malloc` at `0x180015207`
- `msvcrt!malloc` at `0x180015207`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015279`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015279`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180015242`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180015242`

## pseudocode

```c
__int64 __fastcall SIPObjectCAB_::VerifyCabFile(SIPObjectCAB_ *this)
{
  unsigned __int16 v2; // di
  _DWORD *v3; // rbx
  unsigned __int64 i; // r14
  void *v5; // rcx
  DWORD v6; // eax
  int v8; // [rsp+30h] [rbp-40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+34h] [rbp-3Ch] BYREF
  __int128 v10; // [rsp+38h] [rbp-38h] BYREF
  __int128 v11; // [rsp+48h] [rbp-28h]
  int v12; // [rsp+58h] [rbp-18h]

  v10 = 0;
  v12 = 0;
  v11 = 0;
  v8 = 0;
  if ( (unsigned int)SIPObjectCAB_::CheckHeader((HANDLE *)this, (struct CFHEADER *)&v10, (struct CFRESERVE *)&v8) )
  {
    v2 = WORD5(v11);
    NumberOfBytesRead = 0;
    v3 = malloc(8LL * WORD5(v11));
    if ( v3 )
    {
      for ( i = 0; ; ++i )
      {
        v5 = (void *)*((_QWORD *)this + 1);
        if ( i >= v2 )
          break;
        if ( !ReadFile(v5, &v3[2 * i], 8u, &NumberOfBytesRead, 0)
          || NumberOfBytesRead != 8
          || v3[2 * i] >= DWORD2(v10)
          || BYTE2(v8) && !SIPObjectCAB_::SetFilePointerRelative((HANDLE *)this, BYTE2(v8)) )
        {
          goto LABEL_15;
        }
        v2 = WORD5(v11);
      }
      v6 = SetFilePointer(v5, 0, 0, 1u);
      if ( v6 != -1
        && v6 == (_DWORD)v11
        && (unsigned int)SIPObjectCAB_::CheckFiles((HANDLE *)this, (const struct CFHEADER *)&v10)
        && SIPObjectCAB_::CheckData(
             this,
             (const struct CFHEADER *)&v10,
             (const struct CFRESERVE *)&v8,
             (const struct CFFOLDER *const)v3) )
      {
        free(v3);
        return 1;
      }
    }
LABEL_15:
    free(v3);
  }
  return 0;
}

```

## disassembly

```asm
0x1800151a8  mov     [rsp-18h+arg_8], rbx
0x1800151ad  mov     [rsp-18h+arg_10], rsi
0x1800151b2  push    rbp
0x1800151b3  push    rdi
0x1800151b4  push    r14
0x1800151b6  mov     rbp, rsp
0x1800151b9  sub     rsp, 70h
0x1800151bd  mov     rax, cs:__security_cookie
0x1800151c4  xor     rax, rsp
0x1800151c7  mov     [rbp+var_10], rax
0x1800151cb  xorps   xmm0, xmm0
0x1800151ce  lea     r8, [rbp+var_40]; struct CFRESERVE *
0x1800151d2  xor     eax, eax
0x1800151d4  lea     rdx, [rbp+var_38]; lpBuffer
0x1800151d8  movups  [rbp+var_38], xmm0
0x1800151dc  mov     [rbp+var_18], eax
0x1800151df  mov     rsi, rcx
0x1800151e2  movups  [rbp+var_28], xmm0
0x1800151e6  mov     [rbp+var_40], eax
0x1800151e9  call    ?CheckHeader@SIPObjectCAB_@@AEAAHPEAUCFHEADER@@PEAUCFRESERVE@@@Z; SIPObjectCAB_::CheckHeader(CFHEADER *,CFRESERVE *)
0x1800151ee  test    eax, eax
0x1800151f0  jz      loc_1800152C9
0x1800151f6  movzx   edi, word ptr [rbp+var_28+0Ah]
0x1800151fa  mov     ecx, edi
0x1800151fc  mov     [rbp+NumberOfBytesRead], 0
0x180015203  shl     rcx, 3; Size
0x180015207  call    cs:__imp_malloc
0x18001520d  mov     rbx, rax
0x180015210  test    rax, rax
0x180015213  jz      loc_1800152C0
0x180015219  xor     r14d, r14d
0x18001521c  movzx   ecx, di
0x18001521f  cmp     r14, rcx
0x180015222  mov     rcx, [rsi+8]; hFile
0x180015226  jnb     short loc_18001526E
0x180015228  lea     rdi, [rbx+r14*8]
0x18001522c  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x180015235  mov     rdx, rdi; lpBuffer
0x180015238  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001523c  mov     r8d, 8; nNumberOfBytesToRead
0x180015242  call    cs:__imp_ReadFile
0x180015248  test    eax, eax
0x18001524a  jz      short loc_1800152C0
0x18001524c  cmp     [rbp+NumberOfBytesRead], 8
0x180015250  jnz     short loc_1800152C0
0x180015252  mov     eax, dword ptr [rbp+var_38+8]
0x180015255  cmp     [rdi], eax
0x180015257  jnb     short loc_1800152C0
0x180015259  movzx   eax, byte ptr [rbp+var_40+2]
0x18001525d  test    al, al
0x18001525f  jnz     loc_1800152EC
0x180015265  movzx   edi, word ptr [rbp+var_28+0Ah]
0x180015269  inc     r14
0x18001526c  jmp     short loc_18001521C
0x18001526e  mov     r9d, 1; dwMoveMethod
0x180015274  xor     r8d, r8d; lpDistanceToMoveHigh
0x180015277  xor     edx, edx; lDistanceToMove
0x180015279  call    cs:__imp_SetFilePointer
0x18001527f  cmp     eax, 0FFFFFFFFh
0x180015282  jz      short loc_1800152C0
0x180015284  cmp     eax, dword ptr [rbp+var_28]
0x180015287  jnz     short loc_1800152C0
0x180015289  lea     rdx, [rbp+var_38]; struct CFHEADER *
0x18001528d  mov     rcx, rsi; this
0x180015290  call    ?CheckFiles@SIPObjectCAB_@@AEAAHAEBUCFHEADER@@@Z; SIPObjectCAB_::CheckFiles(CFHEADER const &)
0x180015295  test    eax, eax
0x180015297  jz      short loc_1800152C0
0x180015299  mov     r9, rbx; struct CFFOLDER *
0x18001529c  lea     r8, [rbp+var_40]; struct CFRESERVE *
0x1800152a0  lea     rdx, [rbp+var_38]; struct CFHEADER *
0x1800152a4  mov     rcx, rsi; this
0x1800152a7  call    ?CheckData@SIPObjectCAB_@@AEAAHAEBUCFHEADER@@AEBUCFRESERVE@@QEBUCFFOLDER@@@Z; SIPObjectCAB_::CheckData(CFHEADER const &,CFRESERVE const &,CFFOLDER const * const)
0x1800152ac  test    eax, eax
0x1800152ae  jz      short loc_1800152C0
0x1800152b0  mov     rcx, rbx; Block
0x1800152b3  call    cs:__imp_free
0x1800152b9  mov     eax, 1
0x1800152be  jmp     short loc_1800152CB
0x1800152c0  mov     rcx, rbx; Block
0x1800152c3  call    cs:__imp_free
0x1800152c9  xor     eax, eax
0x1800152cb  mov     rcx, [rbp+var_10]
0x1800152cf  xor     rcx, rsp; StackCookie
0x1800152d2  call    __security_check_cookie
0x1800152d7  lea     r11, [rsp+70h+var_s0]
0x1800152dc  mov     rbx, [r11+28h]
0x1800152e0  mov     rsi, [r11+30h]
0x1800152e4  mov     rsp, r11
0x1800152e7  pop     r14
0x1800152e9  pop     rdi
0x1800152ea  pop     rbp
0x1800152eb  retn
0x1800152ec  mov     edx, eax; int
0x1800152ee  mov     rcx, rsi; this
0x1800152f1  call    ?SetFilePointerRelative@SIPObjectCAB_@@AEAAHJ@Z; SIPObjectCAB_::SetFilePointerRelative(long)
0x1800152f6  test    eax, eax
0x1800152f8  jz      short loc_1800152C0
0x1800152fa  jmp     loc_180015265
```
