# HTTP_LOG_FILE_CONFIG::CalculateChange(HTTP_LOG_FILE_CONFIG *)

- ea: `0x180006ca8`
- end: `0x180006df1`
- name: `?CalculateChange@HTTP_LOG_FILE_CONFIG@@QEAAXPEAV1@@Z`
- size: `329`
- prototype: `void __fastcall(HTTP_LOG_FILE_CONFIG *__hidden this, struct HTTP_LOG_FILE_CONFIG *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007cf0`
- `0x180008858`

## callees

- `0x180006ca8`

## import_xrefs

- `iisutil!?EqualsNoCase@STRU@@QEBA_NAEBV1@@Z` at `0x180006d56`
- `iisutil!?EqualsNoCase@STRU@@QEBA_NAEBV1@@Z` at `0x180006d56`
- `iisutil!?Equals@MULTISZ@@QEAAHPEAV1@@Z` at `0x180006d83`
- `iisutil!?Equals@MULTISZ@@QEAAHPEAV1@@Z` at `0x180006d83`

## pseudocode

```c
void __fastcall HTTP_LOG_FILE_CONFIG::CalculateChange(HTTP_LOG_FILE_CONFIG *this, struct HTTP_LOG_FILE_CONFIG *a2)
{
  _DWORD *v3; // rcx
  int *v5; // rsi
  int *v6; // r14
  int v7; // eax
  int *v8; // rsi
  int *v9; // rcx

  v3 = (_DWORD *)((char *)this + 228);
  if ( *(_DWORD *)this != *(_DWORD *)a2 )
    *v3 |= 1u;
  if ( *((_DWORD *)this + 1) != *((_DWORD *)a2 + 1) )
    *v3 |= 2u;
  if ( *((_DWORD *)this + 2) != *((_DWORD *)a2 + 2) )
    *v3 |= 4u;
  if ( *((_DWORD *)this + 3) != *((_DWORD *)a2 + 3) )
    *v3 |= 8u;
  if ( *((_DWORD *)this + 4) != *((_DWORD *)a2 + 4) )
    *v3 |= 0x10u;
  if ( *((_DWORD *)this + 5) != *((_DWORD *)a2 + 5) )
    *v3 |= 0x20u;
  if ( *((_DWORD *)this + 6) != *((_DWORD *)a2 + 6) )
    *((_DWORD *)this + 57) = *v3 | 0x40;
  v5 = (int *)((char *)this + 228);
  if ( *((_DWORD *)this + 7) != *((_DWORD *)a2 + 7) )
    *v5 |= 0x80u;
  if ( *((_DWORD *)this + 9) != *((_DWORD *)a2 + 9) )
    *v5 |= 0x100u;
  v6 = (int *)((char *)this + 228);
  if ( *((_DWORD *)this + 10) == *((_DWORD *)a2 + 10) )
    v6 = (int *)((char *)this + 228);
  else
    *v5 |= 0x4000u;
  if ( STRU::EqualsNoCase(
         (HTTP_LOG_FILE_CONFIG *)((char *)this + 104),
         (struct HTTP_LOG_FILE_CONFIG *)((char *)a2 + 104)) )
  {
    v8 = v6;
  }
  else
  {
    v7 = *v5;
    v8 = (int *)((char *)this + 228);
    *v6 = v7 | 0x200;
  }
  if ( MULTISZ::Equals((HTTP_LOG_FILE_CONFIG *)((char *)this + 160), (struct HTTP_LOG_FILE_CONFIG *)((char *)a2 + 160)) )
    v8 = v6;
  else
    *v6 |= 0x400u;
  if ( *((_DWORD *)this + 54) == *((_DWORD *)a2 + 54) )
  {
    v9 = v8;
  }
  else
  {
    v9 = (int *)((char *)this + 228);
    *v8 = *v6 | 0x800;
  }
  if ( *((_DWORD *)this + 55) == *((_DWORD *)a2 + 55) )
    v9 = v8;
  else
    *v8 |= 0x1000u;
  if ( *((_DWORD *)this + 56) != *((_DWORD *)a2 + 56) )
    *v9 = *v8 | 0x2000;
}

```

## disassembly

```asm
0x180006ca8  push    rbx
0x180006caa  push    rsi
0x180006cab  push    rdi
0x180006cac  push    r14
0x180006cae  sub     rsp, 28h
0x180006cb2  mov     eax, [rdx]
0x180006cb4  mov     rbx, rcx
0x180006cb7  add     rcx, 0E4h
0x180006cbe  mov     rdi, rdx
0x180006cc1  cmp     [rbx], eax
0x180006cc3  jz      short loc_180006CC8
0x180006cc5  or      dword ptr [rcx], 1
0x180006cc8  mov     eax, [rdx+4]
0x180006ccb  cmp     [rbx+4], eax
0x180006cce  jz      short loc_180006CD3
0x180006cd0  or      dword ptr [rcx], 2
0x180006cd3  mov     eax, [rdx+8]
0x180006cd6  cmp     [rbx+8], eax
0x180006cd9  jz      short loc_180006CDE
0x180006cdb  or      dword ptr [rcx], 4
0x180006cde  mov     eax, [rdx+0Ch]
0x180006ce1  cmp     [rbx+0Ch], eax
0x180006ce4  jz      short loc_180006CE9
0x180006ce6  or      dword ptr [rcx], 8
0x180006ce9  mov     eax, [rdx+10h]
0x180006cec  cmp     [rbx+10h], eax
0x180006cef  jz      short loc_180006CF4
0x180006cf1  or      dword ptr [rcx], 10h
0x180006cf4  mov     eax, [rdx+14h]
0x180006cf7  cmp     [rbx+14h], eax
0x180006cfa  jz      short loc_180006CFF
0x180006cfc  or      dword ptr [rcx], 20h
0x180006cff  mov     eax, [rdx+18h]
0x180006d02  cmp     [rbx+18h], eax
0x180006d05  jz      short loc_180006D12
0x180006d07  mov     eax, [rcx]
0x180006d09  or      eax, 40h
0x180006d0c  mov     [rbx+0E4h], eax
0x180006d12  mov     eax, [rdx+1Ch]
0x180006d15  lea     rsi, [rbx+0E4h]
0x180006d1c  cmp     [rbx+1Ch], eax
0x180006d1f  jz      short loc_180006D25
0x180006d21  bts     dword ptr [rsi], 7
0x180006d25  mov     eax, [rdx+24h]
0x180006d28  cmp     [rbx+24h], eax
0x180006d2b  jz      short loc_180006D3A
0x180006d2d  bts     dword ptr [rsi], 8
0x180006d31  lea     r14, [rbx+0E4h]
0x180006d38  jmp     short loc_180006D3D
0x180006d3a  mov     r14, rsi
0x180006d3d  mov     eax, [rdx+28h]
0x180006d40  cmp     [rbx+28h], eax
0x180006d43  jz      short loc_180006D4B
0x180006d45  bts     dword ptr [rsi], 0Eh
0x180006d49  jmp     short loc_180006D4E
0x180006d4b  mov     r14, rsi
0x180006d4e  add     rdx, 68h ; 'h'
0x180006d52  lea     rcx, [rbx+68h]
0x180006d56  call    cs:__imp_?EqualsNoCase@STRU@@QEBA_NAEBV1@@Z; STRU::EqualsNoCase(STRU const &)
0x180006d5c  test    al, al
0x180006d5e  jnz     short loc_180006D72
0x180006d60  mov     eax, [rsi]
0x180006d62  lea     rsi, [rbx+0E4h]
0x180006d69  bts     eax, 9
0x180006d6d  mov     [r14], eax
0x180006d70  jmp     short loc_180006D75
0x180006d72  mov     rsi, r14
0x180006d75  lea     rdx, [rdi+0A0h]
0x180006d7c  lea     rcx, [rbx+0A0h]
0x180006d83  call    cs:__imp_?Equals@MULTISZ@@QEAAHPEAV1@@Z; MULTISZ::Equals(MULTISZ *)
0x180006d89  test    eax, eax
0x180006d8b  jnz     short loc_180006D94
0x180006d8d  bts     dword ptr [r14], 0Ah
0x180006d92  jmp     short loc_180006D97
0x180006d94  mov     rsi, r14
0x180006d97  mov     eax, [rdi+0D8h]
0x180006d9d  cmp     [rbx+0D8h], eax
0x180006da3  jz      short loc_180006DB7
0x180006da5  mov     eax, [r14]
0x180006da8  lea     rcx, [rbx+0E4h]
0x180006daf  bts     eax, 0Bh
0x180006db3  mov     [rsi], eax
0x180006db5  jmp     short loc_180006DBA
0x180006db7  mov     rcx, rsi
0x180006dba  mov     eax, [rdi+0DCh]
0x180006dc0  cmp     [rbx+0DCh], eax
0x180006dc6  jz      short loc_180006DCE
0x180006dc8  bts     dword ptr [rsi], 0Ch
0x180006dcc  jmp     short loc_180006DD1
0x180006dce  mov     rcx, rsi
0x180006dd1  mov     eax, [rdi+0E0h]
0x180006dd7  cmp     [rbx+0E0h], eax
0x180006ddd  jz      short loc_180006DE7
0x180006ddf  mov     eax, [rsi]
0x180006de1  bts     eax, 0Dh
0x180006de5  mov     [rcx], eax
0x180006de7  add     rsp, 28h
0x180006deb  pop     r14
0x180006ded  pop     rdi
0x180006dee  pop     rsi
0x180006def  pop     rbx
0x180006df0  retn
```
