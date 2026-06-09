# CDFPositionAtGroupTag(CRYPTCATCDF_ *,ushort const *)

- ea: `0x18003b3d0`
- end: `0x18003b491`
- name: `?CDFPositionAtGroupTag@@YAHPEAUCRYPTCATCDF_@@PEBG@Z`
- size: `193`
- prototype: `__int64 __fastcall(struct CRYPTCATCDF_ *, const unsigned __int16 *Buf2)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003b498`
- `0x18003bb40`
- `0x18003bd30`

## callees

- `0x18003ac4c`
- `0x18003ac7c`
- `0x18003b3d0`
- `0x18004deb0`

## import_xrefs

- `msvcrt!_memicmp` at `0x18003b459`
- `msvcrt!_memicmp` at `0x18003b459`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003b406`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18003b406`

## pseudocode

```c
__int64 __fastcall CDFPositionAtGroupTag(struct CRYPTCATCDF_ *a1, const unsigned __int16 *Buf2)
{
  unsigned int v4; // eax
  __int64 v5; // r8
  unsigned __int16 Buf1[1032]; // [rsp+20h] [rbp-828h] BYREF

  if ( SetFilePointer(a1->hFile, 0, 0, 0) != -1 )
  {
    while ( 1 )
    {
      v4 = CDFGetLine(a1, Buf1);
      if ( !v4 )
        break;
      if ( Buf1[0] != 35 )
      {
        CDFEOLOut(Buf1, v4);
        if ( Buf1[0] == 91 )
        {
          v5 = -1;
          do
            ++v5;
          while ( Buf2[v5] );
          if ( !_memicmp(Buf1, Buf2, 2 * v5) )
            return 1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003b3d0  mov     [rsp+arg_10], rbx
0x18003b3d5  mov     [rsp+arg_18], rsi
0x18003b3da  push    rdi
0x18003b3db  sub     rsp, 840h
0x18003b3e2  mov     rax, cs:__security_cookie
0x18003b3e9  xor     rax, rsp
0x18003b3ec  mov     [rsp+848h+var_18], rax
0x18003b3f4  mov     rbx, rdx
0x18003b3f7  mov     rdi, rcx
0x18003b3fa  mov     rcx, [rcx+8]; hFile
0x18003b3fe  xor     edx, edx; lDistanceToMove
0x18003b400  xor     r9d, r9d; dwMoveMethod
0x18003b403  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003b406  call    cs:__imp_SetFilePointer
0x18003b40c  cmp     eax, 0FFFFFFFFh
0x18003b40f  jz      short loc_18003B46A
0x18003b411  xor     esi, esi
0x18003b413  lea     rdx, [rsp+848h+Buf1]; unsigned __int16 *
0x18003b418  mov     rcx, rdi; struct CRYPTCATCDF_ *
0x18003b41b  call    ?CDFGetLine@@YAKPEAUCRYPTCATCDF_@@PEAGK@Z; CDFGetLine(CRYPTCATCDF_ *,ushort *,ulong)
0x18003b420  test    eax, eax
0x18003b422  jz      short loc_18003B46A
0x18003b424  cmp     [rsp+848h+Buf1], 23h ; '#'
0x18003b42a  jz      short loc_18003B413
0x18003b42c  mov     edx, eax; unsigned int
0x18003b42e  lea     rcx, [rsp+848h+Buf1]; unsigned __int16 *
0x18003b433  call    ?CDFEOLOut@@YAXPEAGK@Z; CDFEOLOut(ushort *,ulong)
0x18003b438  cmp     [rsp+848h+Buf1], 5Bh ; '['
0x18003b43e  jnz     short loc_18003B413
0x18003b440  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b444  inc     r8
0x18003b447  cmp     [rbx+r8*2], si
0x18003b44c  jnz     short loc_18003B444
0x18003b44e  add     r8, r8; Size
0x18003b451  lea     rcx, [rsp+848h+Buf1]; Buf1
0x18003b456  mov     rdx, rbx; Buf2
0x18003b459  call    cs:__imp__memicmp
0x18003b45f  test    eax, eax
0x18003b461  jnz     short loc_18003B413
0x18003b463  mov     eax, 1
0x18003b468  jmp     short loc_18003B46C
0x18003b46a  xor     eax, eax
0x18003b46c  mov     rcx, [rsp+848h+var_18]
0x18003b474  xor     rcx, rsp; StackCookie
0x18003b477  call    __security_check_cookie
0x18003b47c  lea     r11, [rsp+848h+var_8]
0x18003b484  mov     rbx, [r11+20h]
0x18003b488  mov     rsi, [r11+28h]
0x18003b48c  mov     rsp, r11
0x18003b48f  pop     rdi
0x18003b490  retn
```
